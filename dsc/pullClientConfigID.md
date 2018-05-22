---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: 構成 ID を使用したプル クライアントのセットアップ
ms.openlocfilehash: b4a45c4d014b3c4fc0140ad492f81474b260065a
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="setting-up-a-pull-client-using-configuration-id"></a><span data-ttu-id="d4720-103">構成 ID を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="d4720-103">Setting up a pull client using configuration ID</span></span>

> <span data-ttu-id="d4720-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="d4720-104">Applies To: Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4720-105">プル サーバー (Windows Feature *DSC-Service*) は、Windows Server のサポート対象のコンポーネントですが、新機能が提供される予定はありません。</span><span class="sxs-lookup"><span data-stu-id="d4720-105">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="d4720-106">管理対象のクライアントは、(Windows Server のプル サーバー以降の機能が含まれる) [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) または、[こちら](pullserver.md#community-solutions-for-pull-service)に列挙されているコミュニティ ソリューションのいずれかに切り替えを開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d4720-106">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="d4720-107">各ターゲット ノードに対し、プル モードを使用するように指示し、プル サーバーに接続して構成を取得するための URL を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4720-107">Each target node has to be told to use pull mode and given the URL where it can contact the pull server to get configurations.</span></span> <span data-ttu-id="d4720-108">これを行うには、必要な情報を備えるようにローカル構成マネージャー (LCM) を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4720-108">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="d4720-109">LCM を構成するには、**DSCLocalConfigurationManager** 属性で修飾された特別な種類の構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="d4720-109">To configure the LCM, you create a special type of configuration, decorated with the **DSCLocalConfigurationManager** attribute.</span></span> <span data-ttu-id="d4720-110">LCM の構成の詳細については、「[ローカル構成マネージャーの構成](metaConfig.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d4720-110">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](metaConfig.md).</span></span>

> <span data-ttu-id="d4720-111">**注**: このトピックは、PowerShell 5.0 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d4720-111">**Note**: This topic applies to PowerShell 5.0.</span></span> <span data-ttu-id="d4720-112">PowerShell 4.0 でのプル クライアントのセットアップについては、「[PowerShell 4.0 での構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID4.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d4720-112">For information on setting up a pull client in PowerShell 4.0, see [Setting up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md)</span></span>

<span data-ttu-id="d4720-113">次のスクリプトは、"CONTOSO-PullSrv" という名前のサーバーから構成をプルするように LCM を構成します。</span><span class="sxs-lookup"><span data-stu-id="d4720-113">The following script configures the LCM to pull configurations from a server named "CONTOSO-PullSrv".</span></span>

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
    }
}
PullClientConfigID
```

<span data-ttu-id="d4720-114">このスクリプトでは、**ConfigurationRepositoryWeb** ブロックでプル サーバーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="d4720-114">In the script, the **ConfigurationRepositoryWeb** block defines the pull server.</span></span> <span data-ttu-id="d4720-115">**ServerURL**</span><span class="sxs-lookup"><span data-stu-id="d4720-115">The **ServerURL**</span></span>

<span data-ttu-id="d4720-116">このスクリプトを実行すると、**PullClientConfigID** という名前の新しい出力フォルダーが作成され、そこにメタ構成 MOF ファイルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="d4720-116">After this script runs, it creates a new output folder named **PullClientConfigID** and puts a metaconfiguration MOF file there.</span></span> <span data-ttu-id="d4720-117">この場合、メタ構成 MOF ファイルの名前は `localhost.meta.mof` になります。</span><span class="sxs-lookup"><span data-stu-id="d4720-117">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="d4720-118">構成を適用するには、**Path** をメタ構成 MOF ファイルの場所に設定して **Set-DscLocalConfigurationManager** コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d4720-118">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span> <span data-ttu-id="d4720-119">たとえば次のようになります。`Set-DSCLocalConfigurationManager localhost –Path .\PullClientConfigID –Verbose.`</span><span class="sxs-lookup"><span data-stu-id="d4720-119">For example: `Set-DSCLocalConfigurationManager localhost –Path .\PullClientConfigID –Verbose.`</span></span>

## <a name="configuration-id"></a><span data-ttu-id="d4720-120">構成 ID</span><span class="sxs-lookup"><span data-stu-id="d4720-120">Configuration ID</span></span>

<span data-ttu-id="d4720-121">このスクリプトは、LCM の **ConfigurationID** プロパティをこの目的で以前に作成した GUID に設定します (GUID を作成するには、**New-Guid** コマンドレットを使用します)。</span><span class="sxs-lookup"><span data-stu-id="d4720-121">The script sets the **ConfigurationID** property of LCM to a GUID that had been previously created for this purpose (you can create a GUID by using the **New-Guid** cmdlet).</span></span> <span data-ttu-id="d4720-122">**ConfigurationID** は、LCM がプル サーバーで適切な構成を検索する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d4720-122">The **ConfigurationID** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="d4720-123">プル サーバー上の構成 MOF ファイルは、_ConfigurationID_.mof という名前である必要があります。ここで、_ConfigurationID_ はターゲット ノードの LCM の **ConfigurationID** プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="d4720-123">The configuration MOF file on the pull server must be named _ConfigurationID_.mof, where _ConfigurationID_ is the value of the **ConfigurationID** property of the target node's LCM.</span></span>

## <a name="smb-pull-server"></a><span data-ttu-id="d4720-124">SMB プル サーバー</span><span class="sxs-lookup"><span data-stu-id="d4720-124">SMB pull server</span></span>

<span data-ttu-id="d4720-125">SMB サーバーから構成をプルするようにクライアントをセットアップするには、**ConfigurationRepositoryShare** ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4720-125">To set up a client to pull configurations from an SMB server, use a **ConfigurationRepositoryShare** block.</span></span> <span data-ttu-id="d4720-126">**ConfigurationRepositoryShare** ブロックでは、**SourcePath** プロパティを設定して、サーバーへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4720-126">In a **ConfigurationRepositoryShare** block, you specify the path to the server by setting the **SourcePath** property.</span></span> <span data-ttu-id="d4720-127">次のメタ構成は、**SMBPullServer** という名前の SMB プル サーバーからプルするようにターゲット ノードを構成します。</span><span class="sxs-lookup"><span data-stu-id="d4720-127">The following metaconfiguration configures the target node to pull from an SMB pull server named **SMBPullServer**.</span></span>

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
        ConfigurationRepositoryShare SMBPullServer
        {
            SourcePath = '\\SMBPullServer\PullSource'

        }
    }
}
PullClientConfigID
```

## <a name="resource-and-report-servers"></a><span data-ttu-id="d4720-128">リソースおよびレポート サーバー</span><span class="sxs-lookup"><span data-stu-id="d4720-128">Resource and report servers</span></span>

<span data-ttu-id="d4720-129">LCM 構成で **ConfigurationRepositoryWeb** ブロックまたは **ConfigurationRepositoryShare** ブロックのみを指定した場合 (前の例はこれに当たります)、プル クライアントは、指定されたサーバーからリソースをプルしますが、そのサーバーに対してレポートは送信しません。</span><span class="sxs-lookup"><span data-stu-id="d4720-129">If you specify only a **ConfigurationRepositoryWeb** or **ConfigurationRepositoryShare** block in your LCM configuration (as in the previous example), the pull client will pull resources from the specified server, but it will not send reports to it.</span></span> <span data-ttu-id="d4720-130">構成、リソース、およびレポートについて単一のプル サーバーを使うことができますが、レポートをセットアップするために **ReportRepositoryWeb** ブロックを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4720-130">You can use a single pull server for configurations, resources, and reporting, but you have to create a **ReportRepositoryWeb** block to set up reporting.</span></span>

<span data-ttu-id="d4720-131">次の例は、単一のプル サーバーに対して構成とリソースをプルし、レポート データを送信するようにクライアントを設定するメタ構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="d4720-131">The following example shows a metaconfiguration that sets up a client to pull configurations and resources, and send reporting data, to a single pull server.</span></span>

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


        ReportServerWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

<span data-ttu-id="d4720-132">また、リソース用とレポート用にそれぞれ異なるプル サーバーを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d4720-132">You can also specify different pull servers for resources and reporting.</span></span> <span data-ttu-id="d4720-133">リソース サーバーを指定するには、**ResourceRepositoryWeb** (Web プル サーバーの場合) または **ResourceRepositoryShare** ブロック (SMB プル サーバーの場合) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d4720-133">To specify a resource server, you use either a **ResourceRepositoryWeb** (for a web pull server) or a **ResourceRepositoryShare** block (for an SMB pull server).</span></span>
<span data-ttu-id="d4720-134">レポート サーバーを指定するには、**ReportRepositoryWeb** ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4720-134">To specify a report server, you use a **ReportRepositoryWeb** block.</span></span> <span data-ttu-id="d4720-135">レポート サーバーを SMB サーバーにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d4720-135">A report server cannot be an SMB server.</span></span>
<span data-ttu-id="d4720-136">次のメタ構成は、**CONTOSO-PullSrv** から構成を取得し、**CONTOSO-ResourceSrv** からリソースを取得し、**CONTOSO-ReportSrv** に状態レポートを送信するように、プル クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="d4720-136">The following metaconfiguration configures a pull client to get its configurations from **CONTOSO-PullSrv** and its resources from **CONTOSO-ResourceSrv**, and to send status reports to **CONTOSO-ReportSrv**:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d4720-137">参照</span><span class="sxs-lookup"><span data-stu-id="d4720-137">See Also</span></span>

* [<span data-ttu-id="d4720-138">構成名を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="d4720-138">Setting up a pull client with configuration names</span></span>](pullClientConfigNames.md)