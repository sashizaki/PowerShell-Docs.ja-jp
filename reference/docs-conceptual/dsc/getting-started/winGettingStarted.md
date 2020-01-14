---
ms.date: 08/15/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: Windows 用 Desired State Configuration (DSC) の概要
ms.openlocfilehash: 2add2c936e60c0c9446bf4b398fbf7b4bd6407f7
ms.sourcegitcommit: 1b88c280dd0799f225242608f0cbdab485357633
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75416159"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-windows"></a><span data-ttu-id="ca4c0-103">Windows 用 Desired State Configuration (DSC) の概要</span><span class="sxs-lookup"><span data-stu-id="ca4c0-103">Get started with Desired State Configuration (DSC) for Windows</span></span>

<span data-ttu-id="ca4c0-104">このトピックでは、Windows 用 PowerShell Desired State Configuration (DSC) の使用を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-104">This topic explains how to get started using PowerShell Desired State Configuration (DSC) for Windows.</span></span>
<span data-ttu-id="ca4c0-105">DSC に関する一般的な情報については、「[Windows PowerShell Desired State Configuration の概要](../overview/overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-105">For general information about DSC, see [Get Started with Windows PowerShell Desired State Configuration](../overview/overview.md).</span></span>

## <a name="supported-windows-operation-system-versions"></a><span data-ttu-id="ca4c0-106">サポートされている Windows オペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="ca4c0-106">Supported Windows operation system versions</span></span>

<span data-ttu-id="ca4c0-107">次のバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-107">The following versions are supported:</span></span>

- <span data-ttu-id="ca4c0-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="ca4c0-108">Windows Server 2019</span></span>
- <span data-ttu-id="ca4c0-109">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="ca4c0-109">Windows Server 2016</span></span>
- <span data-ttu-id="ca4c0-110">Windows Server 2012R2</span><span class="sxs-lookup"><span data-stu-id="ca4c0-110">Windows Server 2012R2</span></span>
- <span data-ttu-id="ca4c0-111">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ca4c0-111">Windows Server 2012</span></span>
- <span data-ttu-id="ca4c0-112">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="ca4c0-112">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="ca4c0-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="ca4c0-113">Windows 10</span></span>
- <span data-ttu-id="ca4c0-114">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ca4c0-114">Windows 8.1</span></span>
- <span data-ttu-id="ca4c0-115">Windows 7</span><span class="sxs-lookup"><span data-stu-id="ca4c0-115">Windows 7</span></span>

<span data-ttu-id="ca4c0-116">[Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) のスタンドアロン製品 SKU には、Desired State Configuration の実装が含まれていないため、PowerShell DSC または Azure Automation State Configuration で管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-116">The [Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) standalone product sku doesn't contain an implementation of Desired State Configuration so it cannot be managed by PowerShell DSC or Azure Automation State Configuration.</span></span>

## <a name="installing-dsc"></a><span data-ttu-id="ca4c0-117">DSC のインストール</span><span class="sxs-lookup"><span data-stu-id="ca4c0-117">Installing DSC</span></span>

<span data-ttu-id="ca4c0-118">PowerShell Desired State Configuration は Windows に含まれており、Windows Management Framework を通じて更新されます。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-118">PowerShell Desired State Configuration is included in Windows and updated through Windows Management Framework.</span></span> <span data-ttu-id="ca4c0-119">最新バージョンは [Windows Management Framework 5.1](https://www.microsoft.com/en-us/download/details.aspx?id=54616) です。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-119">The latest version is [Windows Management Framework 5.1](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span></span>

> [!NOTE]
> <span data-ttu-id="ca4c0-120">DSC を使ってコンピューターを管理するために、Windows Server の 'DSC-Service' 機能を有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-120">You do not need to enable the Windows Server feature 'DSC-Service' to manage a machine using DSC.</span></span>
> <span data-ttu-id="ca4c0-121">この機能は、Windows プル サーバー インスタンスを構築する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-121">That feature is only needed when building a Windows Pull Server instance.</span></span>

## <a name="using-dsc-for-windows"></a><span data-ttu-id="ca4c0-122">Windows 用 DSC の使用</span><span class="sxs-lookup"><span data-stu-id="ca4c0-122">Using DSC for Windows</span></span>

<span data-ttu-id="ca4c0-123">次のセクションでは、Windows コンピューター上で DSC 構成を作成し、実行する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-123">The following sections explain how to create and run DSC configurations on Windows computers.</span></span>

### <a name="creating-a-configuration-mof-document"></a><span data-ttu-id="ca4c0-124">構成 MOF ドキュメントの作成</span><span class="sxs-lookup"><span data-stu-id="ca4c0-124">Creating a configuration MOF document</span></span>

<span data-ttu-id="ca4c0-125">構成を作成するには、Windows PowerShell の `Configuration` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-125">The Windows PowerShell `Configuration` keyword is used to create a configuration.</span></span>
<span data-ttu-id="ca4c0-126">以下の手順では、Windows PowerShell を使って構成ドキュメントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-126">The following steps describe the creation of a configuration document using Windows PowerShell.</span></span>

#### <a name="define-a-configuration-and-generate-the-configuration-document"></a><span data-ttu-id="ca4c0-127">構成を定義し、構成ドキュメントを生成します。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-127">Define a configuration and generate the configuration document:</span></span>

```powershell
Configuration EnvironmentVariable_Path
{
    param ()

    Import-DscResource -ModuleName 'PSDscResources'

    Node localhost
    {
        Environment CreatePathEnvironmentVariable
        {
            Name = 'TestPathEnvironmentVariable'
            Value = 'TestValue'
            Ensure = 'Present'
            Path = $true
            Target = @('Process', 'Machine')
        }
    }
}

EnvironmentVariable_Path -OutputPath:"C:\EnvironmentVariable_Path"
```

#### <a name="install-a-module-containing-dsc-resources"></a><span data-ttu-id="ca4c0-128">DSC リソースを含むモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="ca4c0-128">Install a module containing DSC resources</span></span>

<span data-ttu-id="ca4c0-129">Windows PowerShell Desired State Configuration には、DSC リソースを含んだ組み込みモジュールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-129">Windows PowerShell Desired State Configuration includes built-in modules containing DSC resources.</span></span>
<span data-ttu-id="ca4c0-130">PowerShellGet コマンドレットを使って、PowerShell ギャラリーなどの外部ソースからモジュールを読み込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-130">You can also load modules from external sources such as the PowerShell Gallery, using the PowerShellGet cmdlets.</span></span>

```PowerShell
Install-Module 'PSDscResources' -Verbose
```

#### <a name="apply-the-configuration-to-the-machine"></a><span data-ttu-id="ca4c0-131">構成をコンピューターに適用する</span><span class="sxs-lookup"><span data-stu-id="ca4c0-131">Apply the configuration to the machine</span></span>

> [!NOTE]
> <span data-ttu-id="ca4c0-132">DSC が実行できるようにするには、`localhost` の構成を実行している場合でも PowerShell のリモート コマンドを受信するように、Windows を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-132">To allow DSC to run, Windows needs to be configured to receive PowerShell remote commands even when you're running a `localhost` configuration.</span></span> <span data-ttu-id="ca4c0-133">環境を簡単に正しく構成するには、管理者特権の PowerShell ターミナルで `Set-WsManQuickConfig -Force` を実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-133">To easily configure your environment correctly, just run `Set-WsManQuickConfig -Force` in an elevated PowerShell Terminal.</span></span>

<span data-ttu-id="ca4c0-134">[Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) コマンドレットを使用して、構成ドキュメント (MOF ファイル) をコンピューターに適用できます。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-134">Configuration documents (MOF files) can be applied to the machineusing the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

```powershell
Start-DscConfiguration -Path 'C:\EnvironmentVariable_Path' -Wait -Verbose
```

#### <a name="get-the-current-state-of-the-configuration"></a><span data-ttu-id="ca4c0-135">構成の現在の状態を取得する</span><span class="sxs-lookup"><span data-stu-id="ca4c0-135">Get the current state of the configuration</span></span>

<span data-ttu-id="ca4c0-136">[Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) コマンドレットを使うと、コンピューターの現在の状態が照会され、構成の現在の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-136">The [Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet queries the current status of the machine and returns the current values for the configuration.</span></span>

```powershell
Get-DscConfiguration
```

<span data-ttu-id="ca4c0-137">[Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) コマンドレットを使うと、コンピューターに適用されている現在のメタ構成が返されます。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-137">The [Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) cmdlet returns the current meta-configuration applied to the machine.</span></span>

```powershell
Get-DscLocalConfigurationManager
```

#### <a name="remove-the-current-configuration-from-a-machine"></a><span data-ttu-id="ca4c0-138">コンピューターから現在の構成を削除する</span><span class="sxs-lookup"><span data-stu-id="ca4c0-138">Remove the current configuration from a machine</span></span>

<span data-ttu-id="ca4c0-139">[Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument)</span><span class="sxs-lookup"><span data-stu-id="ca4c0-139">The [Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument)</span></span>

```powershell
Remove-DscConfigurationDocument -Stage Current -Verbose
```

#### <a name="configure-settings-in-local-configuration-manager"></a><span data-ttu-id="ca4c0-140">ローカル構成マネージャーで設定を構成する</span><span class="sxs-lookup"><span data-stu-id="ca4c0-140">Configure settings in Local Configuration Manager</span></span>

<span data-ttu-id="ca4c0-141">[Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) コマンドレットを使って、コンピューターにメタ構成 MOF ファイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-141">Apply a Meta Configuration MOF file to the machine using the [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) cmdlet.</span></span>
<span data-ttu-id="ca4c0-142">メタ構成 MOF へのパスが必要です。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-142">Requires the path to the Meta Configuration MOF.</span></span>

```powershell
Set-DSCLocalConfigurationManager -Path 'c:\metaconfig\localhost.meta.mof' -Verbose
```

## <a name="windows-powershell-desired-state-configuration-log-files"></a><span data-ttu-id="ca4c0-143">Windows PowerShell Desired State Configuration のログ ファイル</span><span class="sxs-lookup"><span data-stu-id="ca4c0-143">Windows PowerShell Desired State Configuration log files</span></span>

<span data-ttu-id="ca4c0-144">DSC のログは、パス `Microsoft-Windows-Dsc/Operational` にある Windows イベント ログに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-144">Logs for DSC are written to Windows Event Log in the path `Microsoft-Windows-Dsc/Operational`.</span></span>
<span data-ttu-id="ca4c0-145">デバッグ用の追加のログを有効にするには、「[DSC イベント ログの場所](/powershell/scripting/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs)」に記載されている手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="ca4c0-145">Additional logs for debugging purposes can be enabled following the steps in [Where Are DSC Event Logs](/powershell/scripting/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs).</span></span>
