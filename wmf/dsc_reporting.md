# 構成の状態を中央の場所にレポートする

DSC 構成の状態について詳細な情報を、DSC サービスを実行しているサーバーに送信できます。 Get-DscConfigurationStatus コマンドレットによって返されるのと同じ情報が、DSC サービスに送信されます。 メタ構成の中でレポート サーバーを定義すれば、エラーが発生した時、または構成が正常に完了した時に、この状態がサーバーに送信されます。 ノードがプル モードまたはプッシュ モードのどちらで構成されている場合にも、この情報が送信されます。 状態情報は、DSC サービス データベースに格納されます。

## 状態をレポートするメタ構成のサンプル
```PowerShell
[DscLocalConfigurationManager()]
Configuration ReportingClientMetaConfig
{
    Settings
        {
            RefreshFrequencyMins = 30
            RefreshMode = "PUSH"
            ConfigurationModeFrequencyMins = 15
            AllowModuleOverwrite = $true
        }

        ReportServerWeb ReportManager
        {
            ServerUrL = "http://localhost:8080/PSDSCPullServer/PSDSCPullserver.svc"
            AllowUnsecureConnection  = $true
        }           
}
```
この状態情報を公開する DSC サービスでは、新しい OData エンドポイントが作成されます。 構成 ID またはエージェント ID {$guid} をエンドポイントに渡すことにより、ノードのすべての状態を収集して解析できます。

## 構成の状態を収集する Web 要求のサンプル 
```PowerShell
$statusReports = Invoke-WebRequest -Uri "[http://localhost:8080/PSDSCPullserver/PSDSCPullserver.svc/Node(ConfigurationId='$guid')/StatusReport](http://localhost:8080/PSDSCPullserver/psdscpullserver.svc/Node(ConfigurationId='$guid')/StatusReport)s" -UseBasicParsing -UseDefaultCredentials -ContentType "application/json;odata=minimalmetadata;streaming=true;charset=utf-8" -Headers @{Accept = "application/json"; ProtocolVersion = “1.1”}
```<!--HONumber=Mar16_HO2-->
