# 新しいメタ構成属性による DSC LCM の構成

`DscLocalConfigurationManager` 属性では、メタ構成として構成ブロックを指定します。その構成ブロックを使って DSC ローカル構成マネージャーが構成されます。 この属性は、DSC ローカル構成マネージャーを構成するアイテムのみが含まれるように、構成を制限します。 処理中に、この構成によって `*.meta.mof` ファイルが生成され、`Set-DscLocalConfigurationManager` コマンドレットを使ってそのファイルが該当するターゲット ノードに送られます。

```powershell
[DscLocalConfigurationManager()]
configuration meta
{
    Node localhost
    {
        Settings
        {
            ConfigurationMode = "ApplyAndAutocorrect"
            ConfigurationID = "5603f952-d6c6-4971-88c4-948636bf5c3f"
            RefreshMode = "Pull"
        }
        ConfigurationRepositoryWeb PullServer
        {
            ServerURL = "https://corp.contoso.com/PSDSCPullServer/PSDSCPullServer.svc"
        }
    }
}
```

上の例では、LCM の更新モードにプル モードを使うように構成し、構成モードを ApplyAndAutocorrect に変更し、プル サーバーの種類と場所を定義しています。

この新しい構成属性は、PowerShell 4.0 の LocalConfigurationManager リソースの機能を拡張して置き換わるものです。 旧バージョンとの互換性のために、この属性を使わない構成ではこの LocalConfigurationManager が引き続きサポートされます。

メタ リソース:

| **リソース名**            | **説明**                                |
|------------------------------|------------------------------------------------|
| LocalConfigurationManager    | DSC エンジンの実行に関するさまざまな設定      |
| PartialConfiguration         | 部分的な構成設定                 |
| ConfigurationRepositoryWeb   | Web ベースの構成リポジトリ             |
| ConfigurationRepositoryShare | ファイル共有ベースの構成リポジトリ      |
| ResourceRepositoryWeb        | Web ベースのリソース リポジトリ                  |
| ResourceRepositoryShare      | ファイル ベースのリソース リポジトリ                 |
| ReportServerWeb              | プル シナリオでの Web ベースのレポート エンドポイント |
<!--HONumber=Mar16_HO2-->
