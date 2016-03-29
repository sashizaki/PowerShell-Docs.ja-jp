# DSC レポート サーバーの使用

> 適用先: Windows PowerShell 5.0

> **注:** このトピックで説明しているレポート サーバーは、PowerShell 4.0 では使用できません。 PowerShell 4.0 でのレポートについては、「Using a DSC compliance server (DSC コンプライアンス サーバーの使用)」を参照してください。

構成の状態に関するレポートをプル サーバーに送信するように、ノードのローカル構成マネージャー (LCM) を構成できます。これにより、プル サーバーに対してクエリを実行してデータを取得できるようになります。 ノードは、構成を確認して適用するたびに、
レポート サーバーにレポートを送信します。 これらのレポートは、サーバー上のデータベースに格納され、レポート Web サービスを呼び出すことで取得できます。 各レポートには、
適用された構成の内容、構成適用の成否、使用されたリソース、スローされたエラー、開始時刻と終了時刻などの情報が含まれています。

## レポートを送信するようにするためのノードの構成

ノードがサーバーにレポートを送信するようにするには、そのノードの LCM 構成で **ReportServerWeb** ブロックを使用します (LCM の構成については、
「[ローカル構成マネージャーの構成](metaConfig.md)」をご参照ください)。 ノードがレポートを送信するサーバーは、Web プル サーバーとしてセットアップする必要があります (
SMB 共有にレポートを送信することはできません)。 プル サーバーのセットアップについては、「[DSC Web プル サーバーのセットアップ](pullServer.md)」を参照してください。 レポート サーバーは、ノードが構成をプルしてリソースを取得するのと同じサービスにすることも、
別のサービスにすることもできます。
 
 **ReportServerWeb** ブロックには、プル サービスの URL と、
サーバーに認識されている登録キーを指定します。
 
  次の構成は、あるサービスから構成をプルし、別のサーバー上のサービスにレポートを送信するように
ノードを構成しています。 
 
```powershell
[DSCLocalConfigurationManager()]
configuration ReportClientConfig
{
    Node localhost
    {
        Settings
        {
            RefreshMode          = 'Pull'
            RefreshFrequencyMins = 30 
            RebootNodeIfNeeded   = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL          = 'https://CONTOSO-PULL:8080/PSDSCPullServer.svc'
            RegistrationKey    = 'bbb9778f-43f2-47de-b61e-a0daff474c6d'
            ConfigurationNames = @('ClientConfig')
        }

        ReportServerWeb CONTOSO-ReportSrv
        {
            ServerURL               = 'http://CONTOSO-REPORT:8080/PSDSCReportServer.svc'
            RegistrationKey         = 'ba39daaa-96c5-4f2f-9149-f95c46460faa'
            AllowUnsecureConnection = $true
        }
    }
}
PullClientConfigID
```

## レポート データの取得

プル サーバーに送信されたレポートは、サーバー上のデータベースに格納されます。 これらのレポートは、Web サービスを呼び出すことで利用できます。 特定のノードのレポートを取得するには、
次の形式でレポート Web サービスに HTTP 要求を送信します。
`http://CONTOSO-REPORT:8080/PSDSCReportServer.svc/Nodes(AgentID = MyNodeAgentId)/Reports`
ここで、`MyNodeAgentId` はレポートを取得するノードの AgentId です。 ノードの AgentID を取得するには、そのノードで [Get-DscLocalConfigurationManager](https://technet.microsoft.com/en-us/library/dn407378.aspx) を
呼び出します。

レポートは、JSON オブジェクトの配列として返されます。

次のスクリプトは、実行元のノードのレポートを返します。

```powershell
function GetReport
{
    param($AgentId = "$((glcm).AgentId)", $serviceURL = "http://CONTOSO-REPORT:8080/PSDSCReportServer.svc")
    $requestUri = "$serviceURL/Nodes(AgentId= '$AgentId')/Reports"
    $request = Invoke-WebRequest -Uri $requestUri  -ContentType "application/json;odata=minimalmetadata;streaming=true;charset=utf-8" `
               -UseBasicParsing -Headers @{Accept = "application/json";ProtocolVersion = "2.0"} `
               -ErrorAction SilentlyContinue -ErrorVariable ev
    $object = ConvertFrom-Json $request.content
    return $object.value
}
```
    
## レポート データの表示

**GetReport** 関数の結果を変数に設定すると、返される配列の要素に個別のフィールドを表示できます。

```powershell
$reports = GetReport
$reports[1]

JobId                : 71515ae8-7294-40a3-8137-fc85bf4b678f
OperationType        : Consistency
RefreshMode          : 
Status               : 
ReportFormatVersion  : 1.0
ConfigurationVersion : 2.0.0
StartTime            : 02/08/2016 01:28:54
EndTime              : 02/08/2016 01:28:57
RebootRequested      : False
Errors               : {}
StatusData           : {{"NumberOfResources":"2","Locale":"en-US","ResourcesInDesiredState":[{"ResourceId":"[WindowsFeature]MyFeatureInstance","SourceI
                       nfo":"C:\\ReportTest\\ClientConfig.ps1::4::9::WindowsFeature","ModuleName":"PsDesiredStateConfiguration","ModuleVersion":"1.0","
                       ConfigurationName":"ClientConfig","ResourceName":"WindowsFeature"},{"ResourceId":"[WindowsFeature]My2ndFeatureInstance","SourceI
                       nfo":"C:\\ReportTest\\ClientConfig.ps1::8::9::WindowsFeature","ModuleName":"PsDesiredStateConfiguration","ModuleVersion":"1.0","
                       ConfigurationName":"ClientConfig","ResourceName":"WindowsFeature"}]}}
```

**StatusData** フィールドは、3 つのプロパティを持つオブジェクトです。**NumberOfResources**、**Locale**、および **ResourcesInDesiredState** です。 **ResourcesInDesiredState**
プロパティは、それそれが多数のプロパティを持つオブジェクトの配列です。 次のスクリプトは、パラメーターとして 1 つのレポートを取得し、その **ResourcesInDesiredState** 配列を反復処理し、
それらをコンソールに書き込みます。
 
```powershell
function GetStatusData
{
    param ($Report)
    $statusData = $Report.StatusData | ConvertFrom-Json

    $Resources = $statusData.ResourcesInDesiredState

    Foreach ($Resource in $Resources)
    {
        Write-Host 'ResourceId: ' $Resource.ResourceId
        Write-Host 'SourceInfo: ' $Resource.SourceInfo
        Write-Host 'ModuleName: ' $Resource.ModuleName
        Write-Host 'ModuleVersion: ' $Resource.ModuleVersion
        Write-Host 'ConfigurationName: ' $Resource.ConfigurationName
        Write-Host 'ResourceName: ' $Resource.ResourceName
        Write-Host
    }
}
```

次に、**GetStatusData** 関数を呼び出した後のサンプル出力を示します。

```powershell
GetStatusData -Report $report[1]

ResourceId:  [WindowsFeature]MyFeatureInstance
SourceInfo:  C:\ReportTest\ClientConfig.ps1::4::9::WindowsFeature
ModuleName:  PsDesiredStateConfiguration
ModuleVersion:  1.0
ConfigurationName:  ClientConfig
ResourceName:  WindowsFeature

ResourceId:  [WindowsFeature]My2ndFeatureInstance
SourceInfo:  C:\ReportTest\ClientConfig.ps1::8::9::WindowsFeature
ModuleName:  PsDesiredStateConfiguration
ModuleVersion:  1.0
ConfigurationName:  ClientConfig
ResourceName:  WindowsFeature
```

これらの例は、レポート データを使用してどのようなことができるかを理解するためのものです。 PowerShell での JSON の使用方法については、
「[JSON と PowerShell での再生](https://blogs.technet.microsoft.com/heyscriptingguy/2015/10/08/playing-with-json-and-powershell/)」をご参照ください。

## 参照
>[ローカル構成マネージャーの構成](metaConfig.md)
>[DSC Web プル サーバーのセットアップ](pullServer.md)
>[構成名を使用したプル クライアントのセットアップ](pullClientConfigNames.md)
<!--HONumber=Feb16_HO4-->
