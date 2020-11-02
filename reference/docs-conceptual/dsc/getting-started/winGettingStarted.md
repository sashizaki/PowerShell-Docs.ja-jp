---
ms.date: 08/15/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: Windows 用 Desired State Configuration (DSC) の概要
description: このトピックでは、Windows 用 PowerShell Desired State Configuration (DSC) の使用を開始する方法について説明します。
ms.openlocfilehash: 2b9ddba2023a3933e3ad70d7bfee798ff07f0484
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662814"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-windows"></a><span data-ttu-id="37208-104">Windows 用 Desired State Configuration (DSC) の概要</span><span class="sxs-lookup"><span data-stu-id="37208-104">Get started with Desired State Configuration (DSC) for Windows</span></span>

<span data-ttu-id="37208-105">このトピックでは、Windows 用 PowerShell Desired State Configuration (DSC) の使用を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="37208-105">This topic explains how to get started using PowerShell Desired State Configuration (DSC) for Windows.</span></span> <span data-ttu-id="37208-106">DSC に関する一般的な情報については、「[Windows PowerShell Desired State Configuration の概要](../overview/overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37208-106">For general information about DSC, see [Get Started with Windows PowerShell Desired State Configuration](../overview/overview.md).</span></span>

## <a name="supported-windows-operation-system-versions"></a><span data-ttu-id="37208-107">サポートされている Windows オペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="37208-107">Supported Windows operation system versions</span></span>

<span data-ttu-id="37208-108">次のバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="37208-108">The following versions are supported:</span></span>

- <span data-ttu-id="37208-109">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="37208-109">Windows Server 2019</span></span>
- <span data-ttu-id="37208-110">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="37208-110">Windows Server 2016</span></span>
- <span data-ttu-id="37208-111">Windows Server 2012R2</span><span class="sxs-lookup"><span data-stu-id="37208-111">Windows Server 2012R2</span></span>
- <span data-ttu-id="37208-112">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="37208-112">Windows Server 2012</span></span>
- <span data-ttu-id="37208-113">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="37208-113">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="37208-114">Windows 10</span><span class="sxs-lookup"><span data-stu-id="37208-114">Windows 10</span></span>
- <span data-ttu-id="37208-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="37208-115">Windows 8.1</span></span>
- <span data-ttu-id="37208-116">Windows 7</span><span class="sxs-lookup"><span data-stu-id="37208-116">Windows 7</span></span>

<span data-ttu-id="37208-117">[Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) のスタンドアロン製品 SKU には、Desired State Configuration の実装が含まれていないため、PowerShell DSC または Azure Automation State Configuration で管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="37208-117">The [Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) standalone product sku doesn't contain an implementation of Desired State Configuration so it cannot be managed by PowerShell DSC or Azure Automation State Configuration.</span></span>

## <a name="installing-dsc"></a><span data-ttu-id="37208-118">DSC のインストール</span><span class="sxs-lookup"><span data-stu-id="37208-118">Installing DSC</span></span>

<span data-ttu-id="37208-119">PowerShell Desired State Configuration は Windows に含まれており、Windows Management Framework を通じて更新されます。</span><span class="sxs-lookup"><span data-stu-id="37208-119">PowerShell Desired State Configuration is included in Windows and updated through Windows Management Framework.</span></span> <span data-ttu-id="37208-120">最新バージョンは [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616) です。</span><span class="sxs-lookup"><span data-stu-id="37208-120">The latest version is [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

> [!NOTE]
> <span data-ttu-id="37208-121">DSC を使ってコンピューターを管理するために、Windows Server の 'DSC-Service' 機能を有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="37208-121">You do not need to enable the Windows Server feature 'DSC-Service' to manage a machine using DSC.</span></span>
> <span data-ttu-id="37208-122">この機能は、Windows プル サーバー インスタンスを構築する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="37208-122">That feature is only needed when building a Windows Pull Server instance.</span></span>

## <a name="using-dsc-for-windows"></a><span data-ttu-id="37208-123">Windows 用 DSC の使用</span><span class="sxs-lookup"><span data-stu-id="37208-123">Using DSC for Windows</span></span>

<span data-ttu-id="37208-124">次のセクションでは、Windows コンピューター上で DSC 構成を作成し、実行する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="37208-124">The following sections explain how to create and run DSC configurations on Windows computers.</span></span>

### <a name="creating-a-configuration-mof-document"></a><span data-ttu-id="37208-125">構成 MOF ドキュメントの作成</span><span class="sxs-lookup"><span data-stu-id="37208-125">Creating a configuration MOF document</span></span>

<span data-ttu-id="37208-126">構成を作成するには、Windows PowerShell の `Configuration` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="37208-126">The Windows PowerShell `Configuration` keyword is used to create a configuration.</span></span>
<span data-ttu-id="37208-127">以下の手順では、Windows PowerShell を使って構成ドキュメントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="37208-127">The following steps describe the creation of a configuration document using Windows PowerShell.</span></span>

#### <a name="define-a-configuration-and-generate-the-configuration-document"></a><span data-ttu-id="37208-128">構成を定義し、構成ドキュメントを生成します。</span><span class="sxs-lookup"><span data-stu-id="37208-128">Define a configuration and generate the configuration document:</span></span>

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

#### <a name="install-a-module-containing-dsc-resources"></a><span data-ttu-id="37208-129">DSC リソースを含むモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="37208-129">Install a module containing DSC resources</span></span>

<span data-ttu-id="37208-130">Windows PowerShell Desired State Configuration には、DSC リソースを含んだ組み込みモジュールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="37208-130">Windows PowerShell Desired State Configuration includes built-in modules containing DSC resources.</span></span>
<span data-ttu-id="37208-131">PowerShellGet コマンドレットを使って、PowerShell ギャラリーなどの外部ソースからモジュールを読み込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="37208-131">You can also load modules from external sources such as the PowerShell Gallery, using the PowerShellGet cmdlets.</span></span>

```PowerShell
Install-Module 'PSDscResources' -Verbose
```

#### <a name="apply-the-configuration-to-the-machine"></a><span data-ttu-id="37208-132">構成をコンピューターに適用する</span><span class="sxs-lookup"><span data-stu-id="37208-132">Apply the configuration to the machine</span></span>

> [!NOTE]
> <span data-ttu-id="37208-133">DSC が実行できるようにするには、`localhost` の構成を実行している場合でも PowerShell のリモート コマンドを受信するように、Windows を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37208-133">To allow DSC to run, Windows needs to be configured to receive PowerShell remote commands even when you're running a `localhost` configuration.</span></span> <span data-ttu-id="37208-134">環境を簡単に正しく構成するには、管理者特権の PowerShell ターミナルで `Set-WsManQuickConfig -Force` を実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="37208-134">To easily configure your environment correctly, just run `Set-WsManQuickConfig -Force` in an elevated PowerShell Terminal.</span></span>

<span data-ttu-id="37208-135">[Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) コマンドレットを使用して、構成ドキュメント (MOF ファイル) をコンピューターに適用できます。</span><span class="sxs-lookup"><span data-stu-id="37208-135">Configuration documents (MOF files) can be applied to the machineusing the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

```powershell
Start-DscConfiguration -Path 'C:\EnvironmentVariable_Path' -Wait -Verbose
```

#### <a name="get-the-current-state-of-the-configuration"></a><span data-ttu-id="37208-136">構成の現在の状態を取得する</span><span class="sxs-lookup"><span data-stu-id="37208-136">Get the current state of the configuration</span></span>

<span data-ttu-id="37208-137">[Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) コマンドレットを使うと、コンピューターの現在の状態が照会され、構成の現在の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="37208-137">The [Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet queries the current status of the machine and returns the current values for the configuration.</span></span>

```powershell
Get-DscConfiguration
```

<span data-ttu-id="37208-138">[Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) コマンドレットを使うと、コンピューターに適用されている現在のメタ構成が返されます。</span><span class="sxs-lookup"><span data-stu-id="37208-138">The [Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) cmdlet returns the current meta-configuration applied to the machine.</span></span>

```powershell
Get-DscLocalConfigurationManager
```

#### <a name="remove-the-current-configuration-from-a-machine"></a><span data-ttu-id="37208-139">コンピューターから現在の構成を削除する</span><span class="sxs-lookup"><span data-stu-id="37208-139">Remove the current configuration from a machine</span></span>

<span data-ttu-id="37208-140">[Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument)</span><span class="sxs-lookup"><span data-stu-id="37208-140">The [Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument)</span></span>

```powershell
Remove-DscConfigurationDocument -Stage Current -Verbose
```

#### <a name="configure-settings-in-local-configuration-manager"></a><span data-ttu-id="37208-141">ローカル構成マネージャーで設定を構成する</span><span class="sxs-lookup"><span data-stu-id="37208-141">Configure settings in Local Configuration Manager</span></span>

<span data-ttu-id="37208-142">[Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) コマンドレットを使って、コンピューターにメタ構成 MOF ファイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="37208-142">Apply a Meta Configuration MOF file to the machine using the [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) cmdlet.</span></span> <span data-ttu-id="37208-143">メタ構成 MOF へのパスが必要です。</span><span class="sxs-lookup"><span data-stu-id="37208-143">Requires the path to the Meta Configuration MOF.</span></span>

```powershell
Set-DSCLocalConfigurationManager -Path 'c:\metaconfig\localhost.meta.mof' -Verbose
```

## <a name="windows-powershell-desired-state-configuration-log-files"></a><span data-ttu-id="37208-144">Windows PowerShell Desired State Configuration のログ ファイル</span><span class="sxs-lookup"><span data-stu-id="37208-144">Windows PowerShell Desired State Configuration log files</span></span>

<span data-ttu-id="37208-145">DSC のログは、パス `Microsoft-Windows-Dsc/Operational` にある Windows イベント ログに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="37208-145">Logs for DSC are written to Windows Event Log in the path `Microsoft-Windows-Dsc/Operational`.</span></span>
<span data-ttu-id="37208-146">デバッグ用の追加のログを有効にするには、「[DSC イベント ログの場所](/powershell/scripting/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs)」に記載されている手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="37208-146">Additional logs for debugging purposes can be enabled following the steps in [Where Are DSC Event Logs](/powershell/scripting/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs).</span></span>
