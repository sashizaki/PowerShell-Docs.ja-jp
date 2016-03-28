# RefreshMode プロパティの追加の値

今回のリリースでは、新しい `RefreshMode` 値として **Disabled** が導入されました。 このモードに設定すると、LCM はドキュメントの管理を行いません。 このモードは、DSC の代わりにサード パーティの構成管理ツールを使うものの、`Invoke-DscResource` コマンドレットで DSC リソースを利用する場合、または単に何かの理由で DSC 処理を停止する必要がある場合に使います。

```powershell
Configuration LCMSettings
{
    Node localhost
    {
        LocalConfigurationManager
        {
           RefreshMode = 'Disabled'
        }
    }
}

LCMSettings -OutputPath .\LCMSettings
Set-DscLocalConfigurationManager -Path .\LCMSettings -Verbose -ComputerName localhost
```
<!--HONumber=Mar16_HO2-->
