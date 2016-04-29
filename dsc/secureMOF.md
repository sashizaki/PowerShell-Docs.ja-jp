# MOF ファイルのセキュリティ保護

>適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

DSC は、どのような構成が必要であるかをターゲット ノードに指示するために、その情報が含まれた MOF ファイルを各ノードに送信します。各ノードでは、ローカル構成マネージャー (LCM) によって、必要な構成が実装されます。 
構成の初期化パラメーターを表示します。 このファイルには構成の詳細が含まれているため、安全に保つことが重要です。 そのためには、ユーザーの資格情報を確認するよう LCM を設定します。 
a user. このトピックでは、それらの資格情報を証明書で暗号化してターゲット ノードに安全に送信する方法について説明します。

>**注:** このトピックでは、暗号化に使用する証明書について説明します。 暗号化には、自己署名証明書で十分です。秘密キーは常に秘密に保たれますし、暗号化はドキュメントの信頼性を意味しないからです。 自己署名証明書
>は、認証の目的では、使用するべきでは*ありません*。 認証の目的では、常に信頼された証明機関 (CA) からの証明書を使用する必要があります。

## 前提条件

DSC 構成のセキュリティ保護に使用される資格情報を正常に暗号化するには、次のものが必要になります。

* **証明書を発行して配布するための手段**。 このトピックとその例では、Active Directory 証明機関を使用することを前提としています。 For more background information on 
Active Directory 証明書サービスの背景情報について詳しくは、「Active Directory 証明書サービスの概要」と、 
「[Windows Server 2008 の Active Directory 証明書サービス](https://technet.microsoft.com/windowsserver/dd448615.aspx)」をご覧ください。
* **ターゲット ノードへの管理アクセス**。
* **各ターゲット ノードでは、暗号化可能な証明書がそれぞれの個人用ストアに保存されています**。 Windows PowerShell では、ストアへのパスは Cert:\LocalMachine\My です。 このトピックの例では、 
"ワークステーション認証" テンプレートを使用します。このテンプレートは、その他の証明書テンプレートと共に、[既定の証明書テンプレート] にあります。
* ターゲット ノード以外のコンピューターでこの構成を実行する場合は、**証明書の公開キーをエクスポート**して、構成の実行元であるコンピューターにインポートします。 
configuration from. **公開**キーのみをエクスポートし、秘密キーは安全に保護してください。

## 全体的なプロセス

 1. ターゲット ノードごとに証明書のコピーが保持され、構成コンピューターに公開キーと拇印が保持されるように、証明書、キー、および拇印をセットアップします。
 2. 公開キーのパスと拇印が含まれた構成データ ブロックを作成します。
 3. ターゲット ノードに必要な構成を定義し、ターゲット ノードで暗号化の解除をセットアップする構成スクリプトを作成します。暗号化の解除は、証明書とその拇印を使用して構成データを解読するように、ローカル構成マネージャーに指示することによって行います。
 4. 構成を実行すると、ローカル構成マネージャーの設定が行われ、DSC 構成が起動します。

![Diagram1](images/CredentialEncryptionDiagram1.png)

## 証明書の要件

資格情報の暗号化を指定するには、公開キー証明書が、DSC 構成の作成に使用されているコンピューターから**信頼された**_ターゲット ノード_で使用可能である必要があります。
この公開キー証明書を DSC 資格情報の暗号化に使うには、満たす必要のある特定の要件があります。
 1. **キー使用法**:
   - 含める必要がある: 'KeyEncipherment' と 'DataEncipherment'。
   - 含める_べきではない_: 'Digital Signature'。
 2. **拡張キー使用法**:
   - 含める必要がある: ドキュメントの暗号化 (1.3.6.1.4.1.311.80.1)。
   - 含める_べきではない_: クライアント認証 (1.3.6.1.5.5.7.3.2) とサーバー認証 (1.3.6.1.5.5.7.3.1)。
 3. 証明書の秘密キーが *ターゲット ノード_ で使用可能であること。
 4. 証明書の**プロバイダー**は、"Microsoft RSA SChannel Cryptographic Provider" でなければならない。
 
>**推奨されるベスト プラクティス:** 'Digital Signature' のキー使用法または認証 EKU の 1 つが含まれている証明書は、使用することもできますが、暗号化キーを 
>誤用しやすくなり、攻撃に対して脆弱になります。 したがって、ベスト プラクティスとしては、DSC の資格情報をセキュリティで保護する目的で特別に作成した証明書を使い、その証明書ではこれらのキー使用法と EKU を省略することをお勧めします。 
>EKUs.
  
_ターゲット ノード_にある既存の証明書で、これらの条件を満たしているものがあれば、DSC 資格情報をセキュリティで保護するために使うことができます。
 
## 証明書の作成

秘密キーは、MOF を復号化するのに使用されるため、秘密に保つ必要があります。 そのための最も簡単な方法は、*ターゲット ノード*で秘密キー証明書を作成し、 
DSC 構成を MOF ファイルにコンパイルするために使用されるコンピューターに公開キー証明書をコピーすることです。 次の例は、証明書を作成し、公開キーをエクスポートし、
ローカルの証明書ストアのルートに公開キーをインポートします。

```powershell
# create the cert
$cert = New-SelfSignedCertificate -Type DocumentEncryptionCertLegacyCsp -DnsName 'DscEncryptionCert' 
# export the cert’s public key
$cert | Export-Certificate -FilePath "$env:temp\DscPublicKey.cer"  -Force                                                              
# import the cert’s public key as a trusted root certificate authority so that it is trusted
Import-Certificate -FilePath "$env:temp\DscPublicKey.cer" -CertStoreLocation Cert:\LocalMachine\Root > $null
```

別の方法として、DSC 構成ファイルをコンパイルするために使用されるコンピューター上で秘密キー証明書を作成し、秘密キーと一緒にエクスポートした後、_ターゲット ノード_にインポートすることもできます。 
これは、DSC 資格情報の暗号化を実装するために Nano Server で実行されている現在の手法です。 秘密キーは、転送中にセキュリティで保護される必要があります。

## 構成データ

構成データ ブロックでは、操作対象のターゲット ノード、資格情報を暗号化するかどうか、暗号化の手段、およびその他の情報を定義します。 構成データ ブロックの詳細については、「[Separating Configuration and Environment Data (構成データと環境データの分離)](configData.md)」を参照してください。

資格情報の暗号化に関連するノードごとに構成可能な要素は次のとおりです。
* **NodeName** - 資格情報の暗号化が構成されているターゲット ノードの名前。
* **PsDscAllowPlainTextPassword** - 暗号化されていない資格情報をこのノードに渡してよいかどうか。 これは**推奨されません**。
* **Thumbprint** - _ターゲット ノード_上で DSC 構成に含まれる資格情報を復号化するために使用される証明書の拇印です。 **この証明書は、ターゲット ノード上のローカル コンピューターの証明書ストアに存在する必要があります。**
* **CertificateFile** - _ターゲット ノード_用の証明書を暗号化するために使用する必要のある証明書ファイル (公開キーのみを含む)。 これは、DER Encoded Binary X.509 または Base-64 encoded X.509 のいずれかの形式の証明書ファイルである必要があります。

この例に示す構成データ ブロックでは、処理対象のターゲット ノードの名前を targetNode とし、公開キー証明書ファイル (targetNode.cer という名前) へのパス、および公開キーの拇印を指定しています。

```powershell
$ConfigData= @{ 
    AllNodes = @(     
            @{  
                # The name of the node we are describing 
                NodeName = "targetNode" 

                # The path to the .cer file containing the 
                # public key of the Encryption Certificate 
                # used to encrypt credentials for this node 
                CertificateFile = "C:\publicKeys\targetNode.cer" 

         
                # The thumbprint of the Encryption Certificate 
                # used to decrypt the credentials on target node 
                Thumbprint = "AC23EA3A9E291A75757A556D0B71CBBF8C4F6FD8" 
            }; 
        );    
    }
```

## 構成スクリプト

構成スクリプト自体では、`PsCredential` パラメーターを使用して、できる限り短時間で資格情報が格納されるようにします。 ここに示した例を実行すると、DSC では資格情報の入力を求め、構成データ ブロック内のターゲット ノードに関連付けられている CertificateFile を使用して MOF ファイルを暗号化します。 このコード例では、ユーザーに対してセキュリティ保護された共有からファイルをコピーしています。

```
configuration CredentialEncryptionExample 
{ 
    param( 
        [Parameter(Mandatory=$true)] 
        [ValidateNotNullorEmpty()] 
        [PsCredential] $credential 
        ) 
    

    Node $AllNodes.NodeName 
    { 
        File exampleFile 
        { 
            SourcePath = "\\Server\share\path\file.ext" 
            DestinationPath = "C:\destinationPath" 
            Credential = $credential 
        } 
    } 
}
```

## 暗号化の解除のセットアップ

[`Start-DscConfiguration`](https://technet.microsoft.com/en-us/library/dn521623.aspx) が機能するようにするには、各ターゲット ノードのローカル構成マネージャーに対して、どの証明書を使用して資格情報の暗号化を解除するかを指示し、CertificateID リソースを使用して証明書の拇印を検証する必要があります。 この例の関数は、適切なローカル証明書を検出します (使用する証明書が正しく検出されるようにカスタマイズすることが必要になる場合もあります)。

```powershell
# Get the certificate that works for encryption 
function Get-LocalEncryptionCertificateThumbprint 
{ 
    (dir Cert:\LocalMachine\my) | %{
        # Verify the certificate is for Encryption and valid 
        if ($_.PrivateKey.KeyExchangeAlgorithm -and $_.Verify()) 
        { 
            return $_.Thumbprint 
        } 
    } 
}
```

拇印で証明書を識別する場合は、その値を使用するように構成スクリプトを更新します。

```powershell
configuration CredentialEncryptionExample 
{ 
    param( 
        [Parameter(Mandatory=$true)] 
        [ValidateNotNullorEmpty()] 
        [PsCredential] $credential 
        ) 
    

    Node $AllNodes.NodeName 
    { 
        File exampleFile 
        { 
            SourcePath = "\\Server\share\path\file.ext" 
            DestinationPath = "C:\destinationPath" 
            Credential = $credential 
        } 
        
        LocalConfigurationManager 
        { 
             CertificateId = $node.Thumbprint 
        } 
    } 
}
```

## 構成の実行

この時点では、構成を実行すると、次の 2 つのファイルが出力されます。

 * *.meta.mof ファイル。ローカル コンピューター ストアに格納され、拇印で識別される証明書を使用して資格情報の暗号化を解除するように、ローカル構成マネージャーを構成します。 [`Set-DscLocalConfigurationManager`](https://technet.microsoft.com/en-us/library/dn521621.aspx) は、*.meta.mof ファイルに適用されます。
 * 構成を実際に適用する MOF ファイル。 Start-DscConfiguration は、構成を適用します。

次のコマンドがこれらの手順を実施します。

```powershell
Write-Host "Generate DSC Configuration..."
CredentialEncryptionExample -ConfigurationData $ConfigData -OutputPath .\CredentialEncryptionExample

Write-Host "Setting up LCM to decrypt credentials..."
Set-DscLocalConfigurationManager .\CredentialEncryptionExample -Verbose 
 
Write-Host "Starting Configuration..."
Start-DscConfiguration .\CredentialEncryptionExample -wait -Verbose
```

この例では、DSC 構成をターゲット ノードにプッシュします。
DSC プル サーバーが利用可能な場合は、DSC プル サーバーを使って DSC 構成を適用することもできます。

DSC プル サーバーを使って DSC 構成を適用する方法について詳しくは、[このページ](PullClient.md)を参照してください。

## 資格情報暗号化モジュールの例

次に、これらのすべての手順に加え、公開キーをエクスポートおよびコピーするヘルパー コマンドレットが組み込まれた完全な例を示します。

```powershell
# A simple example of using credentials
configuration CredentialEncryptionExample
{
    param(
        [Parameter(Mandatory=$true)]
        [ValidateNotNullorEmpty()]
        [PsCredential] $credential
        )
    

    Node $AllNodes.NodeName
    {
        File exampleFile
        {
            SourcePath = "\\server\share\file.txt"
            DestinationPath = "C:\Users\user"
            Credential = $credential
        }
        
        LocalConfigurationManager
        {
            CertificateId = $node.Thumbprint
        }
    }
}

# A Helper to invoke the configuration, with the correct public key 
# To encrypt the configuration credentials
function Start-CredentialEncryptionExample
{
    [CmdletBinding()]
    param ($computerName)


    [string] $thumbprint = Get-EncryptionCertificate -computerName $computerName -Verbose
    Write-Verbose "using cert: $thumbprint"

    $certificatePath = join-path -Path "$env:SystemDrive\$script:publicKeyFolder" -childPath "$computername.EncryptionCertificate.cer"         

    $ConfigData=    @{
        AllNodes = @(     
                        @{  
                            # The name of the node we are describing
                            NodeName = "$computerName"

                            # The path to the .cer file containing the
                            # public key of the Encryption Certificate
                            CertificateFile = "$certificatePath"

                            # The thumbprint of the Encryption Certificate
                            # used to decrypt the credentials
                            Thumbprint = $thumbprint
                        };
                    );    
    }

    Write-Verbose "Generate DSC Configuration..."
    CredentialEncryptionExample -ConfigurationData $ConfigData -OutputPath .\CredentialEncryptionExample `
        -credential (Get-Credential -UserName "$env:USERDOMAIN\$env:USERNAME" -Message "Enter credentials for configuration") 

    Write-Verbose "Setting up LCM to decrypt credentials..."
    Set-DscLocalConfigurationManager .\CredentialEncryptionExample -Verbose 

    Write-Verbose "Starting Configuration..."
    Start-DscConfiguration .\CredentialEncryptionExample -wait -Verbose

}


#region HelperFunctions

# The folder name for the exported public keys
$script:publicKeyFolder = "publicKeys"

# Get the certificate that works for encryptions
function Get-EncryptionCertificate
{
    [CmdletBinding()]
    param ($computerName)
    $returnValue= Invoke-Command -ComputerName $computerName -ScriptBlock {
            $certificates = dir Cert:\LocalMachine\my

            $certificates | %{
                    # Verify the certificate is for Encryption and valid
                    if ($_.PrivateKey.KeyExchangeAlgorithm -and $_.Verify())
                    {
                        # Create the folder to hold the exported public key
                        $folder= Join-Path -Path $env:SystemDrive\ -ChildPath $using:publicKeyFolder
                        if (! (Test-Path $folder))
                        {
                            md $folder | Out-Null
                        }

                        # Export the public key to a well known location
                        $certPath = Export-Certificate -Cert $_ -FilePath (Join-Path -path $folder -childPath "EncryptionCertificate.cer") 

                        # Return the thumbprint, and exported certificate path
                        return @($_.Thumbprint,$certPath);
                    }
                  }
        }
    Write-Verbose "Identified and exported cert..."
    # Copy the exported certificate locally
    $destinationPath = join-path -Path "$env:SystemDrive\$script:publicKeyFolder" -childPath "$computername.EncryptionCertificate.cer"
    Copy-Item -Path (join-path -path \\$computername -childPath $returnValue[1].FullName.Replace(":","$"))  $destinationPath | Out-Null

    # Return the thumbprint
    return $returnValue[0]
}

Start-CredentialEncryptionExample
```


<!--HONumber=Mar16_HO5-->


