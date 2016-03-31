# PowerShell 4.0 での構成 ID を使用したプル クライアントのセットアップ

>適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

各ターゲット ノードに対し、プル モードを使用するように指示し、プル サーバーに接続して構成を取得するための URL を指定する必要があります。 これを行うには、必要な情報を備えるようにローカル構成マネージャー (LCM) を構成する必要があります。 LCM を構成するには、"メタ構成" と呼ばれる特殊な種類の構成を作成します。 LCM の構成の詳細については、「[Windows PowerShell 4.0 Desired State Configuration のローカル構成マネージャー (LCM)](metaConfig4.md)」を参照してください。

次のスクリプトは、"PullServer" という名前のサーバーから構成をプルするように LCM を構成します。

```powershell
Configuration SimpleMetaConfigurationForPull 
{ 
    LocalConfigurationManager 
    { 
        ConfigurationID = "1C707B86-EF8E-4C29-B7C1-34DA2190AE24";
        RefreshMode = "PULL";
        DownloadManagerName = "WebDownloadManager";
        RebootNodeIfNeeded = $true;
        RefreshFrequencyMins = 15;
        ConfigurationModeFrequencyMins = 30; 
        ConfigurationMode = "ApplyAndAutoCorrect";
        DownloadManagerCustomData = @{ServerUrl = "http://PullServer:8080/PSDSCPullServer/PSDSCPullServer.svc"; AllowUnsecureConnection = “TRUE”}
    } 
} 
SimpleMetaConfigurationForPull -Output "."
```

このスクリプトでは、**DownloadManagerCustomData** がプル サーバーの URL を渡し、(この例の場合) セキュリティ保護されていない接続を許可します。 

このスクリプトを実行すると、**SimpleMetaConfigurationForPull** という名前の新しい出力フォルダーが作成され、そこにメタ構成 MOF ファイルが格納されます。

構成を適用するには、**ComputerName** ("localhost" を使用) と **Path** (ターゲット ノードの localhost.meta.mof ファイルの場所へのパス) のパラメーターを指定した **Set-DscLocalConfigurationManager** を使用します。 たとえば、次のように入力します。 
```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path . –Verbose.
```

## 構成 ID
このスクリプトは、LCM の **ConfigurationID** プロパティをこの目的で以前に作成した GUID に設定します (GUID を作成するには、**New-Guid** コマンドレットを使用します)。 **ConfigurationID** は、LCM がプル サーバーで適切な構成を検索する場合に使用します。 プル サーバー上の構成 MOF ファイルは、`ConfigurationID.mof` という名前にする必要があります。ここで、*ConfigurationID* はターゲット ノードの LCM の **ConfigurationID** プロパティの値です。


<!--HONumber=Feb16_HO4-->


