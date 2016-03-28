# ノードを複数の構成部分 (部分的な構成) で構成する

WMF 5.0 では、ノードに対して構成ドキュメントをフラグメントとして提供できます。 構成ドキュメントの複数のフラグメントをノードが受け取るには、想定されるフラグメントを指定するように、そのノードのローカル構成マネージャー (LCM) を設定する必要があります。次の例をご覧ください。

```powershell
[DSCLocalConfigurationManager()]
configuration SQLServerDSCSettings
{
    Node localhost
    {
        Settings
        {
            ConfigurationModeFrequencyMins = 30
        }

        ConfigurationRepositoryWeb OSConfigServer
        {
            ServerURL = "https://corp.contoso.com/OSConfigServer/PSDSCPullServer.svc"
        }

        ConfigurationRepositoryWeb SQLConfigServer
        {
            ServerURL = "https://corp.contoso.com/SQLConfigServer/PSDSCPullServer.svc"
        }

        PartialConfiguration OSConfig
        {
            Description = 'Configuration for the Base OS'
            ExclusiveResources = 'PSDesiredStateConfiguration\*'
            ConfigurationSource = '[ConfigurationRepositoryWeb]OSConfigServer'
        }

        PartialConfiguration SQLConfig
        {
            Description = 'Configuration for the SQL Server'
            ConfigurationSource = '[ConfigurationRepositoryWeb]SQLConfigServer'
            DependsOn = '[PartialConfiguration]OSConfig'
        }
    }
}
```

部分的な構成では、構成の名前は、LCM で定義されている名前と一致する必要があります。 上記の例では、構成の名前は `OSConfig` と `SQLConfig` にする必要があります。

部分的な構成に対応できるように LCM を設定すると、構成を調整できるようになりますが、セキュリティ機能は提供されません。<!--HONumber=Mar16_HO2-->
