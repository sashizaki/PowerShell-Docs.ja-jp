# 構成 ID を使用したプル クライアントのセットアップ

> 適用先: Windows PowerShell 5.0

各ターゲット ノードに対し、プル モードを使用するように指示し、プル サーバーに接続して構成を取得するための URL を指定する必要があります。 これを行うには、必要な情報を備えるようにローカル構成マネージャー (LCM) を構成する必要があります。 LCM を構成するには、**DSCLocalConfigurationManager** 属性で修飾された特別な種類の構成を作成します。 LCM の構成の詳細については、「[ローカル構成マネージャーの構成](metaConfig.md)」を参照してください。

> **注**: このトピックは、PowerShell 5.0 に適用されます。 PowerShell 4.0 でのプル クライアントのセットアップについては、「[PowerShell 4.0 での構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID4.md)」を参照してください。

次のスクリプトは、"CONTOSO-PullSrv" という名前のサーバーから構成をプルするように LCM を構成します。

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = 1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30 
            RebootNodeIfNeeded = $true
        }
        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            
        }      
    }
}
PullClientConfigID
```

このスクリプトでは、**ConfigurationRepositoryWeb** ブロックにプル サーバーを定義しています。 **ServerURL**

このスクリプトを実行すると、**PullClientConfigID** という名前の新しい出力フォルダーが作成され、そこにメタ構成 MOF ファイルが格納されます。 この場合、メタ構成 MOF ファイルの名前は `localhost.meta.mof` になります。

構成を適用するには、**Path** をメタ構成 MOF ファイルの場所に設定して **Set-DscLocalConfigurationManager** コマンドレットを呼び出します。 たとえば次のようになります。`Set-DSCLocalConfigurationManager localhost –Path .\PullClientConfigID –Verbose.`

## 構成 ID

このスクリプトは、LCM の **ConfigurationID** プロパティをこの目的で以前に作成した GUID に設定します (GUID を作成するには、**New-Guid** コマンドレットを使用します)。 **ConfigurationID** は、LCM がプル サーバーで適切な構成を検索する場合に使用します。 プル サーバー上の構成 MOF ファイルは、_ConfigurationID_.mof という名前である必要があります。ここで、_ConfigurationID_ はターゲット ノードの LCM の **ConfigurationID** プロパティの値です。

## SMB プル サーバー

SMB サーバーから構成をプルするようにクライアントをセットアップするには、**ConfigurationRepositoryShare** ブロックを使用します。 **ConfigurationRepositoryShare** ブロックでは、**SourcePath** プロパティを設定して、サーバーへのパスを指定します。 次のメタ構成は、**SMBPullServer** という名前の SMB プル サーバーからプルするようにターゲット ノードを構成します。

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30 
            RebootNodeIfNeeded = $true
        }
        ConfigurationRepositoryWeb SMBPullServer
        {
            SourcePath = '\\SMBPullServer\PullSource'
            
        }     
    }
}
PullClientConfigID
```

## リソースおよびレポート サーバー

既定では、クライアント ノードは構成プル サーバーから必要なリソースを取得し、構成プル サーバーに状態をレポートします。 ただし、リソース用とレポート用にそれぞれ異なるプル サーバーを指定できます。
リソース サーバーを指定するには、**ResourceRepositoryWeb** (Web プル サーバーの場合) または **ResourceRepositoryShare** ブロック (SMB プル サーバーの場合) を使用します。
レポート サーバーを指定するには、**ReportRepositoryWeb** ブロックを使用します。 レポート サーバーを SMB サーバーにすることはできません。
次のメタ構成は、**CONTOSO-PullSrv** から構成を取得し、**CONTOSO-ResourceSrv** からリソースを取得し、**CONTOSO-ReportSrv** に状態レポートを送信するように、プル クライアントを構成します。

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30 
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            
        }
        
        ResourceRepositoryWeb CONTOSO-ResourceSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }

        ReportServerWeb CONTOSO-ReportSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

## 参照

* [構成名を使用したプル クライアントのセットアップ](pullClientConfigNames.md)<!--HONumber=Feb16_HO4-->
