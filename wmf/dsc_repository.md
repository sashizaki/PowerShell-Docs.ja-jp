# 構成、リソース、およびレポートのリポジトリの分離

今回のリリースでは、1 つ以上の DSC プル サーバーに対してプルおよびレポートするために必要な十分の柔軟性が提供されます。 各エンドポイントは別々に定義できるため、構成を 1 つの場所からプルし、リソースは別の場所からプルし、レポートはさらに別の場所に送るように定義できます。 次のメタ構成では、まさにそのように実行します。

```PowerShell
[DscLocalConfigurationManager()]
Configuration SampleMetaConfig
{
    Settings
    {
        RefreshMode = "PULL";
        AllowModuleOverwrite = $true;
        RebootNodeIfNeeded = $true;
    }

    ConfigurationRepositoryWeb Configurations
    {
        ServerURL = “https://PullServerMachine:8080/psdscpullserver.svc”
        RegistrationKey = "140a952b-b9d6-406b-b416-e0f759c9c0e4"
    }

    ResourceRepositoryWeb Resources
    {
        ServerURL = “https://ResourceServer:8080/psdscpullserver.svc”
        RegistrationKey = "aaaf952b-b9d6-406b-b416-e0f759c6e000"
    }

    ReportServerWeb Reports
    {
        ServerURL = “https://ReportServer:8080/psdscpullserver.svc”
        RegistrationKey = "fefe592b-b9d6-046b-b146-e0f759c0c0c0"
    }
}
```

さらに、これらを任意に組み合わせて使うこともできます。 次のメタ構成では、ターゲット ノードをプッシュ モードで構成しますが、そのノードにまだインストールされていないリソースは 'DSC プル サーバー' からインストールし、そのノードの状態は別の 'DSC プル サーバー' にレポートします。


```PowerShell
[DscLocalConfigurationManager()]
Configuration SampleMetaConfig
{
    Settings
    {
        RefreshMode = "Push";
        RebootNodeIfNeeded = $true;
    }

    ResourceRepositoryWeb Resources
    {
        ServerURL = “https://ResourceServer:8080/psdscpullserver.svc”
        RegistrationKey = "aaaf952b-b9d6-406b-b416-e0f759c6e000"
    }

    ReportServerWeb Reports
    {
        ServerURL = “https://ReportServer:8080/psdscpullserver.svc”
        RegistrationKey = "fefe592b-b9d6-046b-b146-e0f759c0c0c0"
    }
}
```<!--HONumber=Mar16_HO2-->
