# DSC リソースの自動 RunAs サポート
DSC RunAs 資格情報のサポート
--------------------------------

WMF 5.0 Preview April 2015 には、PsDscRunAsCredential プロパティを使うことにより、資格情報の指定されたセットの下で**任意の** DSC リソースを実行するためのサポートが含まれています。 これにより、特定のユーザー コンテキストで MSI パッケージをインストールするシナリオ、ユーザーのレジストリ ハイブにアクセスするシナリオ、ユーザーの特定のローカル ディレクトリにアクセスするシナリオ、ネットワーク共有にアクセスするシナリオなどが可能になります。

DSC で PsDscRunAsCredential プロパティを使って、ユーザーのコマンド プロンプトの背景色を変更する例を次に示します。

Configuration ChangeCmdBackGroundColor

{

    Node ("localhost")

    {

        Registry CmdPath

        {

            Key = "HKEY\_CURRENT\_USER\\\\Software\\Microsoft\\\\Command Processor"

            ValueName = "DefaultColor"

            ValueData = '1F'

            ValueType = "DWORD"

            Ensure = "Present"

            Force = $true

            Hex = $true

            PsDscRunAsCredential = get-credential

        }

    }

}

$configData = @{

AllNodes = @(

@{

NodeName="localhost";

CertificateFile = "C:\\publicKeys\\targetNode.cer"

}

)

}

ChangeCmdBackGroundColor -ConfigurationData $configData

## 既知の問題

このリリースでは、DSC RunAs 資格情報の機能について次のような既知の問題があります。

-   WindowsProcess リソースは、RunAs 資格情報をサポートしていません。

<!--HONumber=Mar16_HO2-->
