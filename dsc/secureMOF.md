# MOF ファイルのセキュリティ保護

>適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

DSC は、どのような構成が必要であるかをターゲット ノードに指示するために、その情報が含まれた MOF ファイルを各ノードに送信します。各ノードでは、ローカル構成マネージャー (LCM) によって、必要な構成が実装されます。 このファイルには構成の詳細が含まれているため、安全に保つことが重要です。 そのためには、ユーザーの資格情報を確認するようにローカル構成マネージャーを設定します。 このトピックでは、それらの資格情報を証明書で暗号化してターゲット ノードに安全に送信する方法について説明します。

## 前提条件

DSC 構成のセキュリティ保護に使用される資格情報を正常に暗号化するには、次のものが必要になります。

* **証明書を発行して配布するための手段**。 このトピックとその例では、Active Directory 証明機関を使用することを前提としています。 Active Directory 証明書サービスの背景情報の詳細については、「[Active Directory 証明書サービスの概要](https://technet.microsoft.com/library/hh831740.aspx)」と「[Active Directory 証明書サービス](https://technet.microsoft.com/windowsserver/dd448615.aspx)」を参照してください。
* **ターゲット ノードへの管理アクセス**。
* **各ターゲット ノードでは、暗号化可能な証明書がそれぞれの個人用ストアに保存されています**。 Windows PowerShell では、ストアへのパスは Cert:\LocalMachine\My です。 このトピックの例では、"ワークステーション認証" テンプレートを使用します。このテンプレートは、その他の証明書テンプレートと共に、[[既定の証明書テンプレート]](https://technet.microsoft.com/library/cc740061(v=WS.10).aspx) にあります。
* ターゲット ノード以外のコンピューターでこの構成を実行する場合は、**証明書の公開キーをエクスポート**して、構成の実行元であるコンピューターにインポートします。 **公開**キーのみをエクスポートし、秘密キーは安全に保護してください。

## 全体的なプロセス

1. ターゲット ノードごとに証明書のコピーが保持され、構成コンピューターに公開キーと拇印が保持されるように、証明書、キー、および拇印をセットアップします。
1. 公開キーのパスと拇印が含まれた構成データ ブロックを作成します。
1. ターゲット ノードに必要な構成を定義し、ターゲット ノードで暗号化の解除をセットアップする構成スクリプトを作成します。暗号化の解除は、証明書とその拇印を使用して構成データを解読するように、ローカル構成マネージャーに指示することによって行います。
1. 構成を実行すると、ローカル構成マネージャーの設定が行われ、DSC 構成が起動します。

## 構成データ

構成データ ブロックでは、操作対象のターゲット ノード、資格情報を暗号化するかどうか、暗号化の手段、およびその他の情報を定義します。 構成データ ブロックの詳細については、「[Separating Configuration and Environment Data (構成データと環境データの分離)](configData.md)」を参照してください。

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

`Start-DscConfiguration` が機能するようにするには、各ターゲット ノードのローカル構成マネージャーに対して、どの証明書を使用して資格情報の暗号化を解除するかを指示し、CertificateID リソースを使用して証明書の拇印を検証する必要があります。 この例の関数は、適切なローカル証明書を検出します (使用する証明書が正しく検出されるようにカスタマイズすることが必要になる場合もあります)。

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

* *.meta.mof ファイル。ローカル コンピューター ストアに格納され、拇印で識別される証明書を使用して資格情報の暗号化を解除するように、ローカル構成マネージャーを構成します。 Set-DscLocalConfigurationManager は、*.meta.mof ファイルを適用します。
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
```

<!--HONumber=Feb16_HO4-->


