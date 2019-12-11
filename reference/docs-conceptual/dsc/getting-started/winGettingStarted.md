---
ms.date: 08/15/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: Windows 用 Desired State Configuration (DSC) の概要
ms.openlocfilehash: a9346b96693acdbad9bacbd4b6ca85971e17a3d1
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74417767"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-windows"></a><span data-ttu-id="7d30b-103">Windows 用 Desired State Configuration (DSC) の概要</span><span class="sxs-lookup"><span data-stu-id="7d30b-103">Get started with Desired State Configuration (DSC) for Windows</span></span>

<span data-ttu-id="7d30b-104">このトピックでは、Windows 用 PowerShell Desired State Configuration (DSC) の使用を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d30b-104">This topic explains how to get started using PowerShell Desired State Configuration (DSC) for Windows.</span></span>
<span data-ttu-id="7d30b-105">DSC に関する一般的な情報については、「[Windows PowerShell Desired State Configuration の概要](../overview/overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d30b-105">For general information about DSC, see [Get Started with Windows PowerShell Desired State Configuration](../overview/overview.md).</span></span>

## <a name="supported-windows-operation-system-versions"></a><span data-ttu-id="7d30b-106">サポートされている Windows オペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="7d30b-106">Supported Windows operation system versions</span></span>

<span data-ttu-id="7d30b-107">次のバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7d30b-107">The following versions are supported:</span></span>

- <span data-ttu-id="7d30b-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="7d30b-108">Windows Server 2019</span></span>
- <span data-ttu-id="7d30b-109">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="7d30b-109">Windows Server 2016</span></span>
- <span data-ttu-id="7d30b-110">Windows Server 2012R2</span><span class="sxs-lookup"><span data-stu-id="7d30b-110">Windows Server 2012R2</span></span>
- <span data-ttu-id="7d30b-111">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="7d30b-111">Windows Server 2012</span></span>
- <span data-ttu-id="7d30b-112">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="7d30b-112">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="7d30b-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="7d30b-113">Windows 10</span></span>
- <span data-ttu-id="7d30b-114">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="7d30b-114">Windows 8.1</span></span>
- <span data-ttu-id="7d30b-115">Windows 7</span><span class="sxs-lookup"><span data-stu-id="7d30b-115">Windows 7</span></span>

<span data-ttu-id="7d30b-116">[Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) のスタンドアロン製品 SKU には Desired State Configuraion の実装が含まれていないため、これを PowerShell DSC または Azure Automation State Configuration によって管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="7d30b-116">The [Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) standalone product sku does not contain an implementation of Desired State Configuraion so it cannot be managed by PowerShell DSC or Azure Automation State Configuration.</span></span>

## <a name="installing-dsc"></a><span data-ttu-id="7d30b-117">DSC のインストール</span><span class="sxs-lookup"><span data-stu-id="7d30b-117">Installing DSC</span></span>

<span data-ttu-id="7d30b-118">PowerShell Desired State Configuration は Windows に含まれており、Windows Management Framework を通じて更新されます。</span><span class="sxs-lookup"><span data-stu-id="7d30b-118">PowerShell Desired State Configuration is included in Windows and updated through Windows Management Framework.</span></span>
<span data-ttu-id="7d30b-119">最新バージョンは [Windows Management Framework 5.1](https://www.microsoft.com/en-us/download/details.aspx?id=54616) です。</span><span class="sxs-lookup"><span data-stu-id="7d30b-119">The latest version is [Windows Management Framework 5.1](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span></span>

> [!NOTE]
> <span data-ttu-id="7d30b-120">DSC を使ってコンピューターを管理するために、Windows Server の 'DSC-Service' 機能を有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7d30b-120">You do not need to enable the Windows Server feature 'DSC-Service' to manage a machine using DSC.</span></span>
> <span data-ttu-id="7d30b-121">この機能は、Windows プル サーバー インスタンスを構築する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="7d30b-121">That feature is only needed when building a Windows Pull Server instance.</span></span>

## <a name="using-dsc-for-windows"></a><span data-ttu-id="7d30b-122">Windows 用 DSC の使用</span><span class="sxs-lookup"><span data-stu-id="7d30b-122">Using DSC for Windows</span></span>

<span data-ttu-id="7d30b-123">次のセクションでは、Windows コンピューター上で DSC 構成を作成し、実行する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="7d30b-123">The following sections explain how to create and run DSC configurations on Windows computers.</span></span>

### <a name="creating-a-configuration-mof-document"></a><span data-ttu-id="7d30b-124">構成 MOF ドキュメントの作成</span><span class="sxs-lookup"><span data-stu-id="7d30b-124">Creating a configuration MOF document</span></span>

<span data-ttu-id="7d30b-125">構成を作成するには、Windows PowerShell 構成キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="7d30b-125">The Windows PowerShell Configuration keyword is used to create a configuration.</span></span>
<span data-ttu-id="7d30b-126">以下の手順では、Windows PowerShell を使って構成ドキュメントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d30b-126">The following steps describe the creation of a configuration document using Windows PowerShell.</span></span>

#### <a name="define-a-configuration-and-generate-the-configuration-document"></a><span data-ttu-id="7d30b-127">構成を定義し、構成ドキュメントを生成します。</span><span class="sxs-lookup"><span data-stu-id="7d30b-127">Define a configuration and generate the configuration document:</span></span>

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
#### <a name="install-a-module-containing-dsc-resources"></a><span data-ttu-id="7d30b-128">DSC リソースを含むモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="7d30b-128">Install a module containing DSC resources</span></span>

<span data-ttu-id="7d30b-129">Windows PowerShell Desired State Configuration には、DSC リソースを含んだ組み込みモジュールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7d30b-129">Windows PowerShell Desired State Configuration includes built-in modules containing DSC resources.</span></span>
<span data-ttu-id="7d30b-130">PowerShellGet コマンドレットを使って、PowerShell ギャラリーなどの外部ソースからモジュールを読み込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="7d30b-130">You can also load modules from external sources such as the PowerShell Gallery, using the PowerShellGet cmdlets.</span></span>

`Install-Module 'PSDscResources' -Verbose`

#### <a name="apply-the-configuration-to-the-machine"></a><span data-ttu-id="7d30b-131">構成をコンピューターに適用する</span><span class="sxs-lookup"><span data-stu-id="7d30b-131">Apply the configuration to the machine</span></span>

<span data-ttu-id="7d30b-132">構成ドキュメント (MOF ファイル) をコンピューターに適用するには、[Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) コマンドレットを使います。</span><span class="sxs-lookup"><span data-stu-id="7d30b-132">Configuration documents (MOF files) can be applied to the machine using the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

`Start-DscConfiguration -Path 'C:\EnvironmentVariable_Path' -Wait -Verbose`

#### <a name="get-the-current-state-of-the-configuration"></a><span data-ttu-id="7d30b-133">構成の現在の状態を取得する</span><span class="sxs-lookup"><span data-stu-id="7d30b-133">Get the current state of the configuration</span></span>

<span data-ttu-id="7d30b-134">[Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) コマンドレットを使うと、コンピューターの現在の状態が照会され、構成の現在の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="7d30b-134">The [Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet queries the current status of the machine and returns the current values for the configuration.</span></span>

`Get-DscConfiguration`

<span data-ttu-id="7d30b-135">[Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) コマンドレットを使うと、コンピューターに適用されている現在のメタ構成が返されます。</span><span class="sxs-lookup"><span data-stu-id="7d30b-135">The [Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) cmdlet returns the current meta-configuration applied to the machine.</span></span>

`Get-DscLocalConfigurationManager`

#### <a name="remove-the-current-configuration-from-a-machine"></a><span data-ttu-id="7d30b-136">コンピューターから現在の構成を削除する</span><span class="sxs-lookup"><span data-stu-id="7d30b-136">Remove the current configuration from a machine</span></span>

<span data-ttu-id="7d30b-137">[Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument)</span><span class="sxs-lookup"><span data-stu-id="7d30b-137">The [Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument)</span></span>

`Remove-DscConfigurationDocument -Stage Current -Verbose`

#### <a name="configure-settings-in-local-configuration-manager"></a><span data-ttu-id="7d30b-138">ローカル構成マネージャーで設定を構成する</span><span class="sxs-lookup"><span data-stu-id="7d30b-138">Configure settings in Local Configuration Manager</span></span>

<span data-ttu-id="7d30b-139">[Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) コマンドレットを使って、コンピューターにメタ構成 MOF ファイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="7d30b-139">Apply a Meta Configuration MOF file to the machine using the [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) cmdlet.</span></span>
<span data-ttu-id="7d30b-140">メタ構成 MOF へのパスが必要です。</span><span class="sxs-lookup"><span data-stu-id="7d30b-140">Requires the path to the Meta Configuration MOF.</span></span>

`Set-DSCLocalConfigurationManager -Path 'c:\metaconfig\localhost.meta.mof' -Verbose`

## <a name="windows-powershell-desired-state-configuration-log-files"></a><span data-ttu-id="7d30b-141">Windows PowerShell Desired State Configuration のログ ファイル</span><span class="sxs-lookup"><span data-stu-id="7d30b-141">Windows PowerShell Desired State Configuration log files</span></span>

<span data-ttu-id="7d30b-142">DSC のログは、パス `Microsoft-Windows-Dsc/Operational` にある Windows イベント ログに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="7d30b-142">Logs for DSC are written to Windows Event Log in the path `Microsoft-Windows-Dsc/Operational`.</span></span>
<span data-ttu-id="7d30b-143">デバッグ用の追加のログを有効にするには、「[DSC イベント ログの場所](/powershell/scripting/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs)」に記載されている手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="7d30b-143">Additional logs for debugging purposes can be enabled following the steps in [Where Are DSC Event Logs](/powershell/scripting/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs).</span></span>
