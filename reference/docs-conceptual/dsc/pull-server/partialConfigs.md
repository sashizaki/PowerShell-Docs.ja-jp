---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: PowerShell Desired State Configuration の部分構成
description: DSC によって、複数のソースからフラグメントで構成を配信できます。 ターゲット ノード上の LCM によって、フラグメントがまとめられ、1 つの構成として適用されます。
ms.openlocfilehash: 3afe5d684cabec9c8ab528347610b6dd00c5d4e9
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92661607"
---
# <a name="powershell-desired-state-configuration-partial-configurations"></a><span data-ttu-id="01d39-105">PowerShell Desired State Configuration の部分構成</span><span class="sxs-lookup"><span data-stu-id="01d39-105">PowerShell Desired State Configuration partial configurations</span></span>

> <span data-ttu-id="01d39-106">適用先: Windows PowerShell 5.0 以降。</span><span class="sxs-lookup"><span data-stu-id="01d39-106">Applies To: Windows PowerShell 5.0 and later.</span></span>

<span data-ttu-id="01d39-107">PowerShell 5.0 では、Desired State Configuration (DSC) によって、複数のソースからフラグメントで構成を配信できます。</span><span class="sxs-lookup"><span data-stu-id="01d39-107">In PowerShell 5.0, Desired State Configuration (DSC) allows configurations to be delivered in fragments and from multiple sources.</span></span> <span data-ttu-id="01d39-108">ターゲット ノード上のローカル構成マネージャー (LCM) によって、フラグメントがまとめられ、1 つの構成として適用されます。</span><span class="sxs-lookup"><span data-stu-id="01d39-108">The Local Configuration Manager (LCM) on the target node puts the fragments together before applying them as a single configuration.</span></span> <span data-ttu-id="01d39-109">この機能により、チームまたは個人間で構成の制御を共有できます。</span><span class="sxs-lookup"><span data-stu-id="01d39-109">This capability allows sharing control of configuration between teams or individuals.</span></span> <span data-ttu-id="01d39-110">たとえば、2 つ以上開発者のチームがサービスで共同作業を行っている場合、それぞれがサービスの自身の一部を管理する構成を作成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="01d39-110">For example, if two or more teams of developers are collaborating on a service, they might each want to create configurations to manage their part of the service.</span></span> <span data-ttu-id="01d39-111">これらの構成は、それぞれ異なるプル サーバーからプルされ、開発の異なる段階で追加される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="01d39-111">Each of these configurations could be pulled from different pull servers, and they could be added at different stages of development.</span></span> <span data-ttu-id="01d39-112">部分構成では、1 つの構成ドキュメントの編集を調整することなく、さまざまな個人またはチームが構成ノードのさまざまな側面を制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="01d39-112">Partial configurations also allow different individuals or teams to control different aspects of configuring nodes without having to coordinate the editing of a single configuration document.</span></span> <span data-ttu-id="01d39-113">たとえば、1 つのチームが VM とオペレーティング システムの展開を担当し、別のチームがその VM に別のアプリケーションとサービスを展開する場合があります。</span><span class="sxs-lookup"><span data-stu-id="01d39-113">For example, one team might be responsible for deploying a VM and operating system, while another team might deploy other applications and services on that VM.</span></span> <span data-ttu-id="01d39-114">部分構成を使用すると、各チームが、不必要に複雑になることなく、独自の構成を作成できます。</span><span class="sxs-lookup"><span data-stu-id="01d39-114">With partial configurations, each team can create its own configuration, without either of them being unnecessarily complicated.</span></span>

<span data-ttu-id="01d39-115">プッシュ モード、プル モード、または 2 つの組み合わせで部分構成を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="01d39-115">You can use partial configurations in push mode, pull mode, or a combination of the two.</span></span>

## <a name="partial-configurations-in-push-mode"></a><span data-ttu-id="01d39-116">プッシュ モードでの部分構成</span><span class="sxs-lookup"><span data-stu-id="01d39-116">Partial configurations in push mode</span></span>

<span data-ttu-id="01d39-117">部分構成をプッシュ モードで使用するには、ターゲット ノードで、部分構成を受信する LCM を構成します。</span><span class="sxs-lookup"><span data-stu-id="01d39-117">To use partial configurations in push mode, you configure the LCM on the target node to receive the partial configurations.</span></span> <span data-ttu-id="01d39-118">各部分構成は、`Publish-DSCConfiguration` コマンドレットを使用して、ターゲットにプッシュされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d39-118">Each partial configuration must be pushed to the target by using the `Publish-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="01d39-119">その後、ターゲット ノードによって、部分構成が 1 つの構成に結合されます。また、[Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) コマンドレットを呼び出して、構成を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="01d39-119">The target node then combines the partial configuration into a single configuration, and you can apply the configuration by calling the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

### <a name="configuring-the-lcm-for-push-mode-partial-configurations"></a><span data-ttu-id="01d39-120">プッシュ モードの部分構成用の LCM の構成</span><span class="sxs-lookup"><span data-stu-id="01d39-120">Configuring the LCM for push-mode partial configurations</span></span>

<span data-ttu-id="01d39-121">プッシュ モードの部分構成用の LCM を構成するには、各部分構成に 1 つの **PartialConfiguration** ブロックを使用して **DSCLocalConfigurationManager** 構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="01d39-121">To configure the LCM for partial configurations in push mode, you create a **DSCLocalConfigurationManager** configuration with one **PartialConfiguration** block for each partial configuration.</span></span> <span data-ttu-id="01d39-122">LCM の構成の詳細については、「[ローカル構成マネージャーの構成](../managing-nodes/metaConfig.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="01d39-122">For more information about configuring the LCM, see [Windows Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md).</span></span> <span data-ttu-id="01d39-123">次の例では、OS を展開する部分構成と SharePoint を展開および構成する部分構成の 2 つの部分構成が必要な LCM 構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="01d39-123">The following example shows an LCM configuration that expects two partial configurations—one that deploys the OS, and one that deploys and configures SharePoint.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PartialConfigDemo
{
    Node localhost
    {

        PartialConfiguration ServiceAccountConfig
        {
            Description = 'Configuration to add the SharePoint service account to the Administrators group.'
            RefreshMode = 'Push'
        }
           PartialConfiguration SharePointConfig
        {
            Description = 'Configuration for the SharePoint server'
            RefreshMode = 'Push'
        }
    }
}

PartialConfigDemo
```

<span data-ttu-id="01d39-124">各部分構成の **RefreshMode** は、"Push" に設定されています。</span><span class="sxs-lookup"><span data-stu-id="01d39-124">The **RefreshMode** for each partial configuration is set to "Push".</span></span> <span data-ttu-id="01d39-125">**PartialConfiguration** ブロックの名前 (この例では "ServiceAccountConfig" と "SharePointConfig") はターゲット ノードにプッシュされる構成の名前と正確に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d39-125">The names of the **PartialConfiguration** blocks (in this case, "ServiceAccountConfig" and "SharePointConfig") must match exactly the names of the configurations that are pushed to the target node.</span></span>

> [!Note]
> <span data-ttu-id="01d39-126">各 **PartialConfiguration** ブロックの名前は、構成スクリプトに指定されているように、構成の実際の名前と一致する必要があります。MOF ファイルの名前ではなく、ターゲット ノードまたは `localhost` の名前でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="01d39-126">The named of each **PartialConfiguration** block must match the actual name of the configuration as it is specified in the configuration script, not the name of the MOF file, which should be either the name of the target node or `localhost`.</span></span>

### <a name="publishing-and-starting-push-mode-partial-configurations"></a><span data-ttu-id="01d39-127">プッシュ モードの部分構成の公開および開始</span><span class="sxs-lookup"><span data-stu-id="01d39-127">Publishing and starting push-mode partial configurations</span></span>

<span data-ttu-id="01d39-128">次に構成ごとに [Publish-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration) を呼び出して、構成ドキュメントを含むフォルダーを **Path** パラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="01d39-128">You then call [Publish-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration) for each configuration, passing the folders that contain the configuration documents as the **Path** parameters.</span></span> <span data-ttu-id="01d39-129">`Publish-DSCConfiguration` は、構成 MOF ファイルをターゲット ノードに配置します。</span><span class="sxs-lookup"><span data-stu-id="01d39-129">`Publish-DSCConfiguration`places the configuration MOF files to the target nodes.</span></span> <span data-ttu-id="01d39-130">両方の構成の発行後に、ターゲット ノードで `Start-DSCConfiguration –UseExisting` を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="01d39-130">After publishing both configurations, you can call `Start-DSCConfiguration –UseExisting` on the target node.</span></span>

<span data-ttu-id="01d39-131">たとえば、オーサリング ノードで以下の構成 MOF ドキュメントをコンパイルした場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="01d39-131">For example, if you have compiled the following configuration MOF documents on the authoring node:</span></span>

```powershell
Get-ChildItem -Recurse
```

```output
    Directory: C:\PartialConfigTest

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        8/11/2016   1:55 PM                ServiceAccountConfig
d-----       11/17/2016   4:14 PM                SharePointConfig

    Directory: C:\PartialConfigTest\ServiceAccountConfig

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        8/11/2016   2:02 PM           2034 TestVM.mof

    Directory: C:\PartialConfigTest\SharePointConfig

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----       11/17/2016   4:14 PM           1930 TestVM.mof
```

<span data-ttu-id="01d39-132">次のように構成を公開し、実行します。</span><span class="sxs-lookup"><span data-stu-id="01d39-132">You would publish and run the configurations as follows:</span></span>

```powershell
Publish-DscConfiguration .\ServiceAccountConfig -ComputerName 'TestVM'
Publish-DscConfiguration .\SharePointConfig -ComputerName 'TestVM'
Start-DscConfiguration -UseExisting -ComputerName 'TestVM'
```

```output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
17     Job17           Configuratio... Running       True            TestVM            Start-DscConfiguration...
```

> [!Note]
> <span data-ttu-id="01d39-133">[Publish-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration) コマンドレットを実行しているユーザーには、ターゲットノードに対する管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="01d39-133">The user running the [Publish-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration) cmdlet must have administrator privileges on the target node.</span></span>

## <a name="partial-configurations-in-pull-mode"></a><span data-ttu-id="01d39-134">プル モードでの部分構成</span><span class="sxs-lookup"><span data-stu-id="01d39-134">Partial configurations in pull mode</span></span>

<span data-ttu-id="01d39-135">部分構成は、1 つ以上のプル サーバーからプルできます。プル サーバーの詳細については、「[DSC Web プル サーバーのセットアップ](pullServer.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="01d39-135">Partial configurations can be pulled from one or more pull servers (for more information about pull servers, see [Windows PowerShell Desired State Configuration Pull Servers](pullServer.md).</span></span> <span data-ttu-id="01d39-136">これを行うには、ターゲット ノードで、部分構成をプルし、プル サーバーで構成ドキュメントを適切に名前付けおよび配置する LCM を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d39-136">To do this, you have to configure the LCM on the target node to pull the partial configurations, and name and locate the configuration documents properly on the pull servers.</span></span>

### <a name="configuring-the-lcm-for-pull-node-configurations"></a><span data-ttu-id="01d39-137">プル ノード構成用の LCM の構成</span><span class="sxs-lookup"><span data-stu-id="01d39-137">Configuring the LCM for pull node configurations</span></span>

<span data-ttu-id="01d39-138">プル サーバーから部分構成をプルする LCM を構成するには、 **ConfigurationRepositoryWeb** (HTTP プル サーバーの場合) ブロックまたは **ConfigurationRepositoryShare** (SMB プル サーバーの場合) ブロックのいずれかでプル サーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="01d39-138">To configure the LCM to pull partial configurations from a pull server, you define the pull server in either a **ConfigurationRepositoryWeb** (for an HTTP pull server) or **ConfigurationRepositoryShare** (for an SMB pull server) block.</span></span> <span data-ttu-id="01d39-139">その後、 **ConfigurationSource** プロパティを使用して、プル サーバーを参照する **PartialConfiguration** ブロックを作成します。</span><span class="sxs-lookup"><span data-stu-id="01d39-139">You then create **PartialConfiguration** blocks that refer to the pull server by using the **ConfigurationSource** property.</span></span> <span data-ttu-id="01d39-140">また、LCM がプル モードを使用することを指定する **Settings** ブロックを作成し、プル サーバーとターゲット ノードで構成の識別に使用される **ConfigurationNames** または **ConfigurationID** を指定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="01d39-140">You also need to create a **Settings** block to specify that the LCM uses pull mode, and to specify the **ConfigurationNames** or **ConfigurationID** that the pull server and target node use to identify the configurations.</span></span> <span data-ttu-id="01d39-141">次のメタ構成では、CONTOSO-PullSrv という HTTP プル サーバーとこのプル サーバーを使用する 2 つの部分構成が定義されています。</span><span class="sxs-lookup"><span data-stu-id="01d39-141">The following meta-configuration defines an HTTP pull server named CONTOSO-PullSrv and two partial configurations that use that pull server.</span></span>

<span data-ttu-id="01d39-142">**ConfigurationNames** を使用した LCM の構成については、「 [構成名を使用したプル クライアントのセットアップ](pullClientConfigNames.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="01d39-142">For more information about configuring the LCM using **ConfigurationNames** , see [Setting up a pull client using configuration names](pullClientConfigNames.md).</span></span> <span data-ttu-id="01d39-143">**ConfigurationID** を使用した LCM の構成については、「 [構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="01d39-143">For information about configuring the LCM using **ConfigurationID** , see [Setting up a pull client using configuration ID](pullClientConfigID.md).</span></span>

#### <a name="configuring-the-lcm-for-pull-mode-configurations-using-configuration-names"></a><span data-ttu-id="01d39-144">構成名を使用したプル モードの構成用の LCM の構成</span><span class="sxs-lookup"><span data-stu-id="01d39-144">Configuring the LCM for pull mode configurations using configuration names</span></span>

```powershell
[DscLocalConfigurationManager()]
Configuration PartialConfigDemoConfigNames
{
        Settings
        {
            RefreshFrequencyMins            = 30;
            RefreshMode                     = "PULL";
            ConfigurationMode               ="ApplyAndAutocorrect";
            AllowModuleOverwrite            = $true;
            RebootNodeIfNeeded              = $true;
            ConfigurationModeFrequencyMins  = 60;
        }
        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL                       = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey                 = 5b41f4e6-5e6d-45f5-8102-f2227468ef38
            ConfigurationNames              = @("ServiceAccountConfig", "SharePointConfig")
        }

        PartialConfiguration ServiceAccountConfig
        {
            Description                     = "ServiceAccountConfig"
            ConfigurationSource             = @("[ConfigurationRepositoryWeb]CONTOSO-PullSrv")
        }

        PartialConfiguration SharePointConfig
        {
            Description                     = "SharePointConfig"
            ConfigurationSource             = @("[ConfigurationRepositoryWeb]CONTOSO-PullSrv")
            DependsOn                       = '[PartialConfiguration]ServiceAccountConfig'
        }
}
```

#### <a name="configuring-the-lcm-for-pull-mode-configurations-using-configurationid"></a><span data-ttu-id="01d39-145">構成 ID を使用したプル モードの構成用の LCM の構成</span><span class="sxs-lookup"><span data-stu-id="01d39-145">Configuring the LCM for pull mode configurations using ConfigurationID</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PartialConfigDemoConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode                     = 'Pull'
            ConfigurationID                 = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins            = 30
            RebootNodeIfNeeded              = $true
        }
        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL                       = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }

           PartialConfiguration ServiceAccountConfig
        {
            Description                     = 'Configuration for the Base OS'
            ConfigurationSource             = '[ConfigurationRepositoryWeb]CONTOSO-PullSrv'
            RefreshMode                     = 'Pull'
        }
           PartialConfiguration SharePointConfig
        {
            Description                     = 'Configuration for the Sharepoint Server'
            ConfigurationSource             = '[ConfigurationRepositoryWeb]CONTOSO-PullSrv'
            DependsOn                       = '[PartialConfiguration]ServiceAccountConfig'
            RefreshMode                     = 'Pull'
        }
    }
}
PartialConfigDemo
```

<span data-ttu-id="01d39-146">複数のプル サーバーから部分構成をプルすることができます。このためには、各プル サーバーを定義し、各 **PartialConfiguration** ブロックで適切なプル サーバーを参照することのみが必要となります。</span><span class="sxs-lookup"><span data-stu-id="01d39-146">You can pull partial configurations from more than one pull server—you would just need to define each pull server, and then refer to the appropriate pull server in each **PartialConfiguration** block.</span></span>

<span data-ttu-id="01d39-147">メタ構成を作成したら、それを実行して構成ドキュメント (MOF ファイル) を作成し、[Set-DscLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) を呼び出して LCM を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01d39-147">After creating the meta-configuration, you must run it to create a configuration document (a MOF file), and then call [Set-DscLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) to configure the LCM.</span></span>

### <a name="naming-and-placing-the-configuration-documents-on-the-pull-server-configurationnames"></a><span data-ttu-id="01d39-148">プル サーバーでの構成ドキュメントの名前付けおよび配置 (ConfigurationNames)</span><span class="sxs-lookup"><span data-stu-id="01d39-148">Naming and placing the configuration documents on the pull server (ConfigurationNames)</span></span>

<span data-ttu-id="01d39-149">部分構成ドキュメントは、プル サーバーの `web.config` ファイルで **ConfigurationPath** として指定されたフォルダーに配置する必要があります (通常 `C:\Program
Files\WindowsPowerShell\DscService\Configuration`)。</span><span class="sxs-lookup"><span data-stu-id="01d39-149">The partial configuration documents must be placed in the folder specified as the **ConfigurationPath** in the `web.config` file for the pull server (typically `C:\Program
Files\WindowsPowerShell\DscService\Configuration`).</span></span>

#### <a name="naming-configuration-documents-on-the-pull-server-in-powershell-51"></a><span data-ttu-id="01d39-150">PowerShell 5.1 のプル サーバーでの構成ドキュメントの名前付け</span><span class="sxs-lookup"><span data-stu-id="01d39-150">Naming configuration documents on the pull server in PowerShell 5.1</span></span>

<span data-ttu-id="01d39-151">個々のプル サーバーから部分構成を 1 つだけプルする場合、構成ドキュメントに任意の名前を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="01d39-151">If you are pulling only one partial configuration from an individual pull server, the configuration document can have any name.</span></span> <span data-ttu-id="01d39-152">プル サーバーから複数の部分構成をプルする場合、構成ドキュメントの名前は `<ConfigurationName>.mof` ( *ConfigurationName* は部分構成の名前)、または `<ConfigurationName>.<NodeName>.mof` ( *ConfigurationName* は部分構成の名前、 *NodeName* はターゲット ノードの名前) のどちらかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="01d39-152">If you are pulling more than one partial configuration from a pull server, the configuration document can be named either `<ConfigurationName>.mof`, where *ConfigurationName* is the name of the partial configuration, or `<ConfigurationName>.<NodeName>.mof`, where *ConfigurationName* is the name of the partial configuration, and *NodeName* is the name of the target node.</span></span> <span data-ttu-id="01d39-153">これにより、Azure Automation DSC プル サーバーから構成をプルすることができます。</span><span class="sxs-lookup"><span data-stu-id="01d39-153">This allows you to pull configurations from Azure Automation DSC pull server.</span></span>

#### <a name="naming-configuration-documents-on-the-pull-server-in-powershell-50"></a><span data-ttu-id="01d39-154">PowerShell 5.0 のプル サーバーでの構成ドキュメントの名前付け</span><span class="sxs-lookup"><span data-stu-id="01d39-154">Naming configuration documents on the pull server in PowerShell 5.0</span></span>

<span data-ttu-id="01d39-155">構成ドキュメントは次のように名前を付ける必要があります。 *ConfigurationName* が部分構成の名前である場合、`ConfigurationName.mof` です。</span><span class="sxs-lookup"><span data-stu-id="01d39-155">The configuration documents must be named as follows: `ConfigurationName.mof`, where *ConfigurationName* is the name of the partial configuration.</span></span> <span data-ttu-id="01d39-156">この例では、構成ドキュメントの名前は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="01d39-156">For our example, the configuration documents should be named as follows:</span></span>

```
ServiceAccountConfig.mof
ServiceAccountConfig.mof.checksum
SharePointConfig.mof
SharePointConfig.mof.checksum
```

### <a name="naming-and-placing-the-configuration-documents-on-the-pull-server-configurationid"></a><span data-ttu-id="01d39-157">プル サーバーでの構成ドキュメントの名前付けおよび配置 (ConfigurationID)</span><span class="sxs-lookup"><span data-stu-id="01d39-157">Naming and placing the configuration documents on the pull server (ConfigurationID)</span></span>

<span data-ttu-id="01d39-158">部分構成ドキュメントは、プル サーバーの `web.config` ファイルで **ConfigurationPath** として指定されたフォルダーに配置する必要があります (通常 `C:\Program Files\WindowsPowerShell\DscService\Configuration`)。</span><span class="sxs-lookup"><span data-stu-id="01d39-158">The partial configuration documents must be placed in the folder specified as the **ConfigurationPath** in the `web.config` file for the pull server (typically `C:\Program Files\WindowsPowerShell\DscService\Configuration`).</span></span> <span data-ttu-id="01d39-159">構成ドキュメントの名前は `<ConfigurationName>.<ConfigurationID>.mof` のようになっている必要があります。 _ConfigurationName_ は部分構成の名前であり、 _ConfigurationID_ はターゲット ノードの LCM で定義されている構成 ID です。</span><span class="sxs-lookup"><span data-stu-id="01d39-159">The configuration documents must be named as follows: `<ConfigurationName>.<ConfigurationID>.mof`, where _ConfigurationName_ is the name of the partial configuration and _ConfigurationID_ is the configuration ID defined in the LCM on the target node.</span></span> <span data-ttu-id="01d39-160">この例では、構成ドキュメントの名前は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="01d39-160">For our example, the configuration documents should be named as follows:</span></span>

```
ServiceAccountConfig.1d545e3b-60c3-47a0-bf65-5afc05182fd0.mof
ServiceAccountConfig.1d545e3b-60c3-47a0-bf65-5afc05182fd0.mof.checksum
SharePointConfig.1d545e3b-60c3-47a0-bf65-5afc05182fd0.mof
SharePointConfig.1d545e3b-60c3-47a0-bf65-5afc05182fd0.mof.checksum
```

### <a name="running-partial-configurations-from-a-pull-server"></a><span data-ttu-id="01d39-161">プル サーバーからの部分構成の実行</span><span class="sxs-lookup"><span data-stu-id="01d39-161">Running partial configurations from a pull server</span></span>

<span data-ttu-id="01d39-162">ターゲット ノードで LCM を構成し、プル サーバーで構成ドキュメントを作成して適切に名前を付けた後に、ターゲット ノードによって、部分構成がプルされ、それらが結合されて、LCM の **RefreshFrequencyMins** プロパティによって指定されているように定期的に結果の構成が適用されます。</span><span class="sxs-lookup"><span data-stu-id="01d39-162">After the LCM on the target node has been configured, and the configuration documents have been created and properly named on the pull server, the target node will pull the partial configurations, combine them, and apply the resulting configuration at regular intervals as specified by the **RefreshFrequencyMins** property of the LCM.</span></span> <span data-ttu-id="01d39-163">強制的に更新する場合は、[Update-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Update-DscConfiguration) コマンドレットを呼び出して、構成をプルし、`Start-DSCConfiguration –UseExisting` を呼び出して、その構成を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="01d39-163">If you want to force a refresh, you can call the [Update-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Update-DscConfiguration) cmdlet, to pull the configurations, and then `Start-DSCConfiguration –UseExisting` to apply them.</span></span>

## <a name="partial-configurations-in-mixed-push-and-pull-modes"></a><span data-ttu-id="01d39-164">プッシュとプルの混在モードでの部分構成</span><span class="sxs-lookup"><span data-stu-id="01d39-164">Partial configurations in mixed push and pull modes</span></span>

<span data-ttu-id="01d39-165">部分構成のプッシュ モードとプル モードを混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="01d39-165">You can also mix push and pull modes for partial configurations.</span></span> <span data-ttu-id="01d39-166">つまり、プル サーバーからプルされた部分構成とプッシュされた別の部分構成を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="01d39-166">That is, you could have one partial configuration that is pulled from a pull server, while another partial configuration is pushed.</span></span> <span data-ttu-id="01d39-167">前のセクションで説明したように、それぞれの部分構成に対して更新モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="01d39-167">Specify the refresh mode for each partial configuration as described in the previous sections.</span></span> <span data-ttu-id="01d39-168">たとえば、次のメタ構成では、プル モードの `ServiceAccountConfig` 部分構成とプッシュ モードの `SharePointConfig` 部分構成がある同じ例が記述されています。</span><span class="sxs-lookup"><span data-stu-id="01d39-168">For example, the following meta-configuration describes the same example, with the `ServiceAccountConfig` partial configuration in pull mode and the `SharePointConfig` partial configuration in push mode.</span></span>

### <a name="mixed-push-and-pull-modes-using-configurationnames"></a><span data-ttu-id="01d39-169">ConfigurationNames を使用したプッシュとプルの混在モード</span><span class="sxs-lookup"><span data-stu-id="01d39-169">Mixed push and pull modes using ConfigurationNames</span></span>

```powershell
[DscLocalConfigurationManager()]
Configuration PartialConfigDemoConfigNames
{
        Settings
        {
            RefreshFrequencyMins            = 30;
            RefreshMode                     = "PULL";
            ConfigurationMode               = "ApplyAndAutocorrect";
            AllowModuleOverwrite            = $true;
            RebootNodeIfNeeded              = $true;
            ConfigurationModeFrequencyMins  = 60;
        }
        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL                       = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey                 = 5b41f4e6-5e6d-45f5-8102-f2227468ef38
            ConfigurationNames              = @("ServiceAccountConfig", "SharePointConfig")
        }

        PartialConfiguration ServiceAccountConfig
        {
            Description                     = "ServiceAccountConfig"
            ConfigurationSource             = @("[ConfigurationRepositoryWeb]CONTOSO-PullSrv")
            RefreshMode                     = 'Pull'
        }

        PartialConfiguration SharePointConfig
        {
            Description                     = "SharePointConfig"
            DependsOn                       = '[PartialConfiguration]ServiceAccountConfig'
            RefreshMode                     = 'Push'
        }

}
```

### <a name="mixed-push-and-pull-modes-using-configurationid"></a><span data-ttu-id="01d39-170">ConfigurationID を使用したプッシュとプルの混在モード</span><span class="sxs-lookup"><span data-stu-id="01d39-170">Mixed push and pull modes using ConfigurationID</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PartialConfigDemo
{
    Node localhost
    {
        Settings
        {
            RefreshMode             = 'Pull'
            ConfigurationID         = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins    = 30
            RebootNodeIfNeeded      = $true
        }
        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL               = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }

           PartialConfiguration ServiceAccountConfig
        {
            Description             = 'Configuration for the Base OS'
            ConfigurationSource     = '[ConfigurationRepositoryWeb]CONTOSO-PullSrv'
            RefreshMode             = 'Pull'
        }
           PartialConfiguration SharePointConfig
        {
            Description             = 'Configuration for the Sharepoint Server'
            DependsOn               = '[PartialConfiguration]ServiceAccountConfig'
            RefreshMode             = 'Push'
        }
    }
}
PartialConfigDemo
```

<span data-ttu-id="01d39-171">なお、Settings ブロックで指定されている **RefreshMode** は "Pull" ですが、`SharePointConfig` 部分構成の **RefreshMode** は "Push" です。</span><span class="sxs-lookup"><span data-stu-id="01d39-171">Note that the **RefreshMode** specified in the Settings block is "Pull", but the **RefreshMode** for the `SharePointConfig` partial configuration is "Push".</span></span>

<span data-ttu-id="01d39-172">それぞれの更新モードの前述の説明に従って、構成 MOF ファイルの名前付けおよび配置を行います。</span><span class="sxs-lookup"><span data-stu-id="01d39-172">Name and locate the configuration MOF files as described above for their respective refresh modes.</span></span>
<span data-ttu-id="01d39-173">`Publish-DSCConfiguration` を呼び出して、`SharePointConfig` 部分構成を公開し、`ServiceAccountConfig` 構成がプル サーバーからプルされることを待機するか、または [Update-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Update-DscConfiguration) を呼び出して強制的に更新します。</span><span class="sxs-lookup"><span data-stu-id="01d39-173">Call `Publish-DSCConfiguration` to publish the `SharePointConfig` partial configuration, and either wait for the `ServiceAccountConfig` configuration to be pulled from the pull server, or force a refresh by calling [Update-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Update-DscConfiguration).</span></span>

## <a name="example-serviceaccountconfig-partial-configuration"></a><span data-ttu-id="01d39-174">ServiceAccountConfig 部分構成の例</span><span class="sxs-lookup"><span data-stu-id="01d39-174">Example ServiceAccountConfig Partial Configuration</span></span>

```powershell
Configuration ServiceAccountConfig
{
    Param (
        [Parameter(Mandatory,
                   HelpMessage="Domain credentials required to add domain\sharepoint_svc to the local Administrators group.")]
        [ValidateNotNullOrEmpty()]
        [pscredential]$Credential
    )

    Import-DscResource -ModuleName PSDesiredStateConfiguration

    Node localhost
    {
        Group LocalAdmins
        {
            GroupName           = 'Administrators'
            MembersToInclude    = 'domain\sharepoint_svc',
                                  'admins@example.domain'
            Ensure              = 'Present'
            Credential          = $Credential
        }

        WindowsFeature Telnet
        {
            Name                = 'Telnet-Server'
            Ensure              = 'Absent'
        }
    }
}
ServiceAccountConfig
```

## <a name="example-sharepointconfig-partial-configuration"></a><span data-ttu-id="01d39-175">SharePointConfig 部分構成の例</span><span class="sxs-lookup"><span data-stu-id="01d39-175">Example SharePointConfig Partial Configuration</span></span>

```powershell
Configuration SharePointConfig
{
    Param (
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [pscredential]$ProductKey
    )

    Import-DscResource -ModuleName xSharePoint

    Node localhost
    {
        xSPInstall SharePointDefault
        {
            Ensure      = 'Present'
            BinaryDir   = '\\FileServer\Installers\Sharepoint\'
            ProductKey  = $ProductKey
        }
    }
}
SharePointConfig
```

## <a name="see-also"></a><span data-ttu-id="01d39-176">参照</span><span class="sxs-lookup"><span data-stu-id="01d39-176">See Also</span></span>

[<span data-ttu-id="01d39-177">Windows PowerShell Desired State Configuration プル サーバー</span><span class="sxs-lookup"><span data-stu-id="01d39-177">Windows PowerShell Desired State Configuration Pull Servers</span></span>](pullServer.md)

[<span data-ttu-id="01d39-178">ローカル構成マネージャーの構成</span><span class="sxs-lookup"><span data-stu-id="01d39-178">Windows Configuring the Local Configuration Manager</span></span>](../managing-nodes/metaConfig.md)
