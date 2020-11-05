---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC レポート サーバーの使用
description: 構成の状態に関するレポートをプル サーバーに送信するように、ノードのローカル構成マネージャー (LCM) を構成できます。これにより、プル サーバーに対してクエリを実行してデータを取得できるようになります。
ms.openlocfilehash: 58ff1684bbe1d23fa68296aa56dd94ba6bc5b148
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92653711"
---
# <a name="using-a-dsc-report-server"></a><span data-ttu-id="f31fd-104">DSC レポート サーバーの使用</span><span class="sxs-lookup"><span data-stu-id="f31fd-104">Using a DSC report server</span></span>

<span data-ttu-id="f31fd-105">適用先:Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="f31fd-105">Applies To: Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f31fd-106">プル サーバー (Windows Feature *DSC-Service* ) は、Windows Server のサポート対象のコンポーネントですが、新機能がオファーされる予定はありません。</span><span class="sxs-lookup"><span data-stu-id="f31fd-106">The Pull Server (Windows Feature *DSC-Service* ) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="f31fd-107">管理対象のクライアントは、(Windows Server のプル サーバー以降の機能が含まれる) [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) または、[こちら](pullserver.md#community-solutions-for-pull-service)に列挙されているコミュニティ ソリューションのいずれかに切り替えを開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f31fd-107">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>
>
> [!NOTE]
> <span data-ttu-id="f31fd-108">このトピックで説明しているレポート サーバーは、PowerShell 4.0 では使用できません。</span><span class="sxs-lookup"><span data-stu-id="f31fd-108">The report server described in this topic is not available in PowerShell 4.0.</span></span>

<span data-ttu-id="f31fd-109">構成の状態に関するレポートをプル サーバーに送信するように、ノードのローカル構成マネージャー (LCM) を構成できます。これにより、プル サーバーに対してクエリを実行してデータを取得できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f31fd-109">The Local Configuration Manager (LCM) of a node can be configured to send reports about its configuration status to a pull server that can then be queried to retrieve that data.</span></span> <span data-ttu-id="f31fd-110">ノードは、構成を確認して適用するたびに、レポート サーバーにレポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="f31fd-110">Each time the node checks and applies a configuration, it sends a report to the report server.</span></span> <span data-ttu-id="f31fd-111">これらのレポートは、サーバー上のデータベースに格納され、レポート Web サービスを呼び出すことで取得できます。</span><span class="sxs-lookup"><span data-stu-id="f31fd-111">These reports are stored in a database on the server, and can be retrieved by calling the reporting web service.</span></span>
<span data-ttu-id="f31fd-112">各レポートには、適用された構成の内容、構成適用の成否、使用されたリソース、スローされたエラー、開始時刻と終了時刻などの情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f31fd-112">Each report contains information such as what configurations were applied and whether they succeeded, the resources used, any errors that were thrown, and start and finish times.</span></span>

## <a name="configuring-a-node-to-send-reports"></a><span data-ttu-id="f31fd-113">レポートを送信するようにするためのノードの構成</span><span class="sxs-lookup"><span data-stu-id="f31fd-113">Configuring a node to send reports</span></span>

<span data-ttu-id="f31fd-114">ノードがサーバーにレポートを送信するようにするには、そのノードの LCM 構成で **ReportServerWeb** ブロックを使用します (LCM の構成については、「 [ローカル構成マネージャーの構成](../managing-nodes/metaConfig.md)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="f31fd-114">You tell a node to send reports to a server by using a **ReportServerWeb** block in the node's LCM configuration (for information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md)).</span></span> <span data-ttu-id="f31fd-115">ノードのレポート送信先になるサーバーは、Web プル サーバーとしてセットアップする必要があります (SMB 共有にレポートを送信することはできません)。</span><span class="sxs-lookup"><span data-stu-id="f31fd-115">The server to which the node sends reports must be set up as a web pull server (you cannot send reports to an SMB share).</span></span> <span data-ttu-id="f31fd-116">プル サーバーのセットアップについては、「[DSC Web プル サーバーのセットアップ](pullServer.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f31fd-116">For information about setting up a pull server, see [Setting up a DSC web pull server](pullServer.md).</span></span> <span data-ttu-id="f31fd-117">レポート サーバーは、ノードが構成をプルしてリソースを取得するのと同じサービスにすることも、別のサービスにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f31fd-117">The report server can be the same service from which the node pulls configurations and gets resources, or it can be a different service.</span></span>

<span data-ttu-id="f31fd-118">**ReportServerWeb** ブロックには、プル サービスの URL と、サーバーに認識されている登録キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f31fd-118">In the **ReportServerWeb** block, you specify the URL of the pull service and a registration key that is known to the server.</span></span>

<span data-ttu-id="f31fd-119">次の構成では、あるサービスから構成をプルし、別のサーバー上のサービスにレポートを送信するようにノードを構成しています。</span><span class="sxs-lookup"><span data-stu-id="f31fd-119">The following configuration configures a node to pull configurations from one service, and send reports to a service on a different server.</span></span>

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
            ServerURL               = 'http://CONTOSO-REPORT:8080/PSDSCPullServer.svc'
            RegistrationKey         = 'ba39daaa-96c5-4f2f-9149-f95c46460faa'
            AllowUnsecureConnection = $true
        }
    }
}

ReportClientConfig
```

<span data-ttu-id="f31fd-120">次の構成では、構成、リソース、およびレポートに 1 つのサーバーを使用するためのノードを構成します。</span><span class="sxs-lookup"><span data-stu-id="f31fd-120">The following configuration configures a node to use a single server for configurations, resources, and reporting.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfig
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }



        ReportServerWeb CONTOSO-ReportSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfig
```

> [!NOTE]
> <span data-ttu-id="f31fd-121">プル サーバーを設定するとき、Web サービスには任意の名前を指定できますが、 **ServerURL** プロパティはサービス名と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f31fd-121">You can name the web service whatever you want when you set up a pull server, but the **ServerURL** property must match the service name.</span></span>

## <a name="getting-report-data"></a><span data-ttu-id="f31fd-122">レポート データの取得</span><span class="sxs-lookup"><span data-stu-id="f31fd-122">Getting report data</span></span>

<span data-ttu-id="f31fd-123">プル サーバーに送信されたレポートは、サーバー上のデータベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="f31fd-123">Reports sent to the pull server are entered into a database on the server.</span></span> <span data-ttu-id="f31fd-124">これらのレポートは、Web サービスを呼び出すことで利用できます。</span><span class="sxs-lookup"><span data-stu-id="f31fd-124">The reports are available through calls to the web service.</span></span> <span data-ttu-id="f31fd-125">特定のノードのレポートを取得するには、次の形式でレポート Web サービスに HTTP 要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="f31fd-125">To retrieve reports for a specific node, send an HTTP request to the report web service in the following form:</span></span>

`http://CONTOSO-REPORT:8080/PSDSCReportServer.svc/Nodes(AgentId='MyNodeAgentId')/Reports`

<span data-ttu-id="f31fd-126">ここで、`MyNodeAgentId` はレポートを取得するノードの AgentId です。</span><span class="sxs-lookup"><span data-stu-id="f31fd-126">Where `MyNodeAgentId` is the AgentId of the node for which you want to get reports.</span></span> <span data-ttu-id="f31fd-127">ノードの AgentID を取得するには、そのノードで [Get-DscLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f31fd-127">You can get the AgentID for a node by calling [Get-DscLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager) on that node.</span></span>

<span data-ttu-id="f31fd-128">レポートは、JSON オブジェクトの配列として返されます。</span><span class="sxs-lookup"><span data-stu-id="f31fd-128">The reports are returned as an array of JSON objects.</span></span>

<span data-ttu-id="f31fd-129">次のスクリプトは、実行元のノードのレポートを返します。</span><span class="sxs-lookup"><span data-stu-id="f31fd-129">The following script returns the reports for the node on which it is run:</span></span>

```powershell
function GetReport
{
    param
    (
        $AgentId = "$((glcm).AgentId)",
        $serviceURL = "http://CONTOSO-REPORT:8080/PSDSCPullServer.svc"
    )

    $requestUri = "$serviceURL/Nodes(AgentId= '$AgentId')/Reports"
    $request = Invoke-WebRequest -Uri $requestUri  -ContentType "application/json;odata=minimalmetadata;streaming=true;charset=utf-8" `
               -UseBasicParsing -Headers @{Accept = "application/json";ProtocolVersion = "2.0"} `
               -ErrorAction SilentlyContinue -ErrorVariable ev
    $object = ConvertFrom-Json $request.content
    return $object.value
}
```

## <a name="viewing-report-data"></a><span data-ttu-id="f31fd-130">レポート データの表示</span><span class="sxs-lookup"><span data-stu-id="f31fd-130">Viewing report data</span></span>

<span data-ttu-id="f31fd-131">**GetReport** 関数の結果を変数に設定すると、返される配列の要素を個別のフィールドで表示できます。</span><span class="sxs-lookup"><span data-stu-id="f31fd-131">If you set a variable to the result of the **GetReport** function, you can view the individual fields in an element of the array that is returned:</span></span>

```powershell
$reports = GetReport
$reports[1]
```

```output
JobId                : 019dfbe5-f99f-11e5-80c6-001dd8b8065c
OperationType        : Consistency
RefreshMode          : Pull
Status               : Success
ReportFormatVersion  : 2.0
ConfigurationVersion : 2.0.0
StartTime            : 04/03/2016 06:21:43
EndTime              : 04/03/2016 06:22:04
RebootRequested      : False
Errors               : {}
StatusData           : {{"StartDate":"2016-04-03T06:21:43.7220000-07:00","IPV6Addresses":["2001:4898:d8:f2f2:852b:b255:b071:283b","fe80::852b:b255:b071
                       :283b%12","::2000:0:0:0","::1","::2000:0:0:0"],"DurationInSeconds":"21","JobID":"{019DFBE5-F99F-11E5-80C6-001DD8B8065C}","Curren
                       tChecksum":"A7797571CB9C3AF4D74C39A0FDA11DAF33273349E1182385528FFC1E47151F7F","MetaData":"Author: configAuthor; Name:
                       Sample_ArchiveFirewall; Version: 2.0.0; GenerationDate: 04/01/2016 15:23:30; GenerationHost: CONTOSO-PullSrv;","RebootRequested":"False
                       ","Status":"Success","IPV4Addresses":["10.240.179.151","127.0.0.1"],"LCMVersion":"2.0","ResourcesNotInDesiredState":[{"SourceInf
                       o":"C:\\ReportTest\\Sample_xFirewall_AddFirewallRule.ps1::23::9::xFirewall","ModuleName":"xNetworking","DurationInSeconds":"8.785",
                       "InstanceName":"Firewall","StartDate":"2016-04-03T06:21:56.4650000-07:00","ResourceName":"xFirewall","ModuleVersion":"2.7.0.0","
                       RebootRequested":"False","ResourceId":"[xFirewall]Firewall","ConfigurationName":"Sample_ArchiveFirewall","InDesiredState":"False
                       "}],"NumberOfResources":"2","Type":"Consistency","HostName":"CONTOSO-PULLCLI","ResourcesInDesiredState":[{"SourceInfo":"C:\\ReportTest\\Sample_xFirewall_AddFirewallRule.ps1::16::9::Archive","ModuleName":"PSDesiredStateConfiguration","DurationInSeconds":"1.848",
                       "InstanceName":"ArchiveExample","StartDate":"2016-04-03T06:21:56.4650000-07:00","ResourceName":"Archive","ModuleVersion":"1.1","
                       RebootRequested":"False","ResourceId":"[Archive]ArchiveExample","ConfigurationName":"Sample_ArchiveFirewall","InDesiredState":"T
                       rue"}],"MACAddresses":["00-1D-D8-B8-06-5C","00-00-00-00-00-00-00-E0"],"MetaConfiguration":{"AgentId":"52DA826D-00DE-4166-8ACB-73F2B46A7E00",
                       "ConfigurationDownloadManagers":[{"SourceInfo":"C:\\ReportTest\\LCMConfig.ps1::14::9::ConfigurationRepositoryWeb","A
                       llowUnsecureConnection":"True","ServerURL":"http://CONTOSO-PullSrv:8080/PSDSCPullServer.svc","RegistrationKey":"","ResourceId":"[Config
                       urationRepositoryWeb]CONTOSO-PullSrv","ConfigurationNames":["ClientConfig"]}],"ActionAfterReboot":"ContinueConfiguration","LCMCo
                       mpatibleVersions":["1.0","2.0"],"LCMState":"Idle","ResourceModuleManagers":[],"ReportManagers":[{"AllowUnsecureConnection":"True
                       ","RegistrationKey":"","ServerURL":"http://CONTOSO-PullSrv:8080/PSDSCPullServer.svc","ResourceId":"[ReportServerWeb]CONTOSO-PullSrv","S
                       ourceInfo":"C:\\ReportTest\\LCMConfig.ps1::24::9::ReportServerWeb"}],"StatusRetentionTimeInDays":"10","LCMVersion":"2.0","Config
                       urationMode":"ApplyAndMonitor","RefreshFrequencyMins":"30","RebootNodeIfNeeded":"True","RefreshMode":"Pull","DebugMode":["NONE"]
                       ,"LCMStateDetail":"","AllowModuleOverwrite":"False","ConfigurationModeFrequencyMins":"15"},"Locale":"en-US","Mode":"Pull"}}
AdditionalData       : {}
```

<span data-ttu-id="f31fd-132">既定では、レポートは **JobID** 順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="f31fd-132">By default, the reports are sorted by **JobID**.</span></span> <span data-ttu-id="f31fd-133">最新のレポートを取得するには、 **StartTime** プロパティを降順にしてレポートを並べ替えることができます。そして、配列の最初の要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="f31fd-133">To get the most recent report, you can sort the reports by descending **StartTime** property, and then get the first element of the array:</span></span>

```powershell
$reportsByStartTime = $reports | Sort-Object {$_."StartTime" -as [DateTime] } -Descending
$reportMostRecent = $reportsByStartTime[0]
```

<span data-ttu-id="f31fd-134">**StatusData** プロパティは、さまざまなプロパティを持つオブジェクトであることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="f31fd-134">Notice that the **StatusData** property is an object with a number of properties.</span></span> <span data-ttu-id="f31fd-135">これは、レポート データの多くがある場所です。</span><span class="sxs-lookup"><span data-stu-id="f31fd-135">This is where much of the reporting data is.</span></span> <span data-ttu-id="f31fd-136">最新のレポートについての **StatusData** プロパティの個々のフィールドを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="f31fd-136">Let's look at the individual fields of the **StatusData** property for the most recent report:</span></span>

```powershell
$statusData = $reportMostRecent.StatusData | ConvertFrom-Json
$statusData
```

```output
StartDate                  : 2016-04-04T11:21:41.2990000-07:00
IPV6Addresses              : {2001:4898:d8:f2f2:852b:b255:b071:283b, fe80::852b:b255:b071:283b%12, ::2000:0:0:0, ::1...}
DurationInSeconds          : 25
JobID                      : {135D230E-FA92-11E5-80C6-001DD8B8065C}
CurrentChecksum            : A7797571CB9C3AF4D74C39A0FDA11DAF33273349E1182385528FFC1E47151F7F
MetaData                   : Author: configAuthor; Name: Sample_ArchiveFirewall; Version: 2.0.0; GenerationDate: 04/01/2016 15:23:30; GenerationHost:
                             CONTOSO-PullSrv;
RebootRequested            : False
Status                     : Success
IPV4Addresses              : {10.240.179.151, 127.0.0.1}
LCMVersion                 : 2.0
ResourcesNotInDesiredState : {@{SourceInfo=C:\ReportTest\Sample_xFirewall_AddFirewallRule.ps1::23::9::xFirewall; ModuleName=xNetworking;
                             DurationInSeconds=10.725; InstanceName=Firewall; StartDate=2016-04-04T11:21:55.7200000-07:00; ResourceName=xFirewall;
                             ModuleVersion=2.7.0.0; RebootRequested=False; ResourceId=[xFirewall]Firewall; ConfigurationName=Sample_ArchiveFirewall;
                             InDesiredState=False}}
NumberOfResources          : 2
Type                       : Consistency
HostName                   : CONTOSO-PULLCLI
ResourcesInDesiredState    : {@{SourceInfo=C:\ReportTest\Sample_xFirewall_AddFirewallRule.ps1::16::9::Archive; ModuleName=PSDesiredStateConfiguration;
                             DurationInSeconds=2.672; InstanceName=ArchiveExample; StartDate=2016-04-04T11:21:55.7200000-07:00; ResourceName=Archive;
                             ModuleVersion=1.1; RebootRequested=False; ResourceId=[Archive]ArchiveExample; ConfigurationName=Sample_ArchiveFirewall;
                             InDesiredState=True}}
MACAddresses               : {00-1D-D8-B8-06-5C, 00-00-00-00-00-00-00-E0}
MetaConfiguration          : @{AgentId=52DA826D-00DE-4166-8ACB-73F2B46A7E00; ConfigurationDownloadManagers=System.Object[];
                             ActionAfterReboot=ContinueConfiguration; LCMCompatibleVersions=System.Object[]; LCMState=Idle;
                             ResourceModuleManagers=System.Object[]; ReportManagers=System.Object[]; StatusRetentionTimeInDays=10; LCMVersion=2.0;
                             ConfigurationMode=ApplyAndMonitor; RefreshFrequencyMins=30; RebootNodeIfNeeded=True; RefreshMode=Pull;
                             DebugMode=System.Object[]; LCMStateDetail=; AllowModuleOverwrite=False; ConfigurationModeFrequencyMins=15}
Locale                     : en-US
Mode                       : Pull
```

<span data-ttu-id="f31fd-137">特にこれは、最新の構成が 2 つのリソースを呼び出したことを示しています。期待した状態になっているのはいずれか片方で、もう一方はそうなっていません。</span><span class="sxs-lookup"><span data-stu-id="f31fd-137">Among other things, this shows that the most recent configuration called two resources, and that one of them was in the desired state, and one of them was not.</span></span> <span data-ttu-id="f31fd-138">**ResourcesNotInDesiredState** プロパティのみを使用すると、より読みやすい出力を取得できます。</span><span class="sxs-lookup"><span data-stu-id="f31fd-138">You can get a more readable output of just the **ResourcesNotInDesiredState** property:</span></span>

```powershell
$statusData.ResourcesInDesiredState
```

```output
SourceInfo        : C:\ReportTest\Sample_xFirewall_AddFirewallRule.ps1::16::9::Archive
ModuleName        : PSDesiredStateConfiguration
DurationInSeconds : 2.672
InstanceName      : ArchiveExample
StartDate         : 2016-04-04T11:21:55.7200000-07:00
ResourceName      : Archive
ModuleVersion     : 1.1
RebootRequested   : False
ResourceId        : [Archive]ArchiveExample
ConfigurationName : Sample_ArchiveFirewall
InDesiredState    : True
```

<span data-ttu-id="f31fd-139">これらの例は、レポート データを使用してどのようなことができるかを理解するためのものです。</span><span class="sxs-lookup"><span data-stu-id="f31fd-139">Note that these examples are meant to give you an idea of what you can do with report data.</span></span> <span data-ttu-id="f31fd-140">PowerShell での JSON の使用方法については、「[Playing with JSON and PowerShell (PowerShell での JSON の使用)](https://devblogs.microsoft.com/scripting/playing-with-json-and-powershell/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f31fd-140">For an introduction on working with JSON in PowerShell, see [Playing with JSON and PowerShell](https://devblogs.microsoft.com/scripting/playing-with-json-and-powershell/).</span></span>

## <a name="see-also"></a><span data-ttu-id="f31fd-141">参照</span><span class="sxs-lookup"><span data-stu-id="f31fd-141">See Also</span></span>

[<span data-ttu-id="f31fd-142">ローカル構成マネージャーの構成</span><span class="sxs-lookup"><span data-stu-id="f31fd-142">Configuring the Local Configuration Manager</span></span>](../managing-nodes/metaConfig.md)

[<span data-ttu-id="f31fd-143">DSC Web プル サーバーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="f31fd-143">Setting up a DSC web pull server</span></span>](pullServer.md)

[<span data-ttu-id="f31fd-144">構成名を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="f31fd-144">Setting up a pull client using configuration names</span></span>](pullClientConfigNames.md)
