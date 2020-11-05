---
ms.date: 01/17/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: ノードを再起動する
description: 多くの構成設定では、構成の変更を完了するために、コンピューターの再起動が必要になることがあります。 この記事では、構成での再起動の管理方法について説明します。
ms.openlocfilehash: d2b0f77c34ebcb006821da1f4f8d7c4b046f7a95
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92645116"
---
# <a name="reboot-a-node"></a><span data-ttu-id="f0fd4-105">ノードを再起動する</span><span class="sxs-lookup"><span data-stu-id="f0fd4-105">Reboot a Node</span></span>

> [!NOTE]
> <span data-ttu-id="f0fd4-106">このトピックでは、ノードの再起動方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-106">This topic talks about how to reboot a Node.</span></span> <span data-ttu-id="f0fd4-107">再起動を成功させるために、 **ActionAfterReboot** と **RebootNodeIfNeeded** の LCM 設定は適切に構成される必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-107">In order for the reboot to be successful the **ActionAfterReboot** and **RebootNodeIfNeeded** LCM settings need to be configured properly.</span></span> <span data-ttu-id="f0fd4-108">ローカル構成マネージャーの設定については、「[ローカル構成マネージャーの構成](../managing-nodes/metaConfig.md)」または[ローカル構成マネージャー (v4) の構成](../managing-nodes/metaConfig4.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-108">To read about Local Configuration Manager settings, see [Configure the Local Configuration Manager](../managing-nodes/metaConfig.md), or [Configure the Local Configuration Manager (v4)](../managing-nodes/metaConfig4.md).</span></span>

<span data-ttu-id="f0fd4-109">ノードは、`$global:DSCMachineStatus` フラグを使用することで、リソース内から再起動できます。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-109">Nodes can be rebooted from within a resource, by using the `$global:DSCMachineStatus` flag.</span></span> <span data-ttu-id="f0fd4-110">`Set-TargetResource` 関数でこのフラグを `1` に設定すると、現在のリソースの **Set** メソッドの直後に、LCM によってノードが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-110">Setting this flag to `1` in the `Set-TargetResource` function forces the LCM to reboot the Node directly after the **Set** method of the current resource.</span></span> <span data-ttu-id="f0fd4-111">このフラグを使用して、 [ComputerManagementDsc](https://github.com/PowerShell/ComputerManagementDsc) DSC リソース モジュールの **PendingReboot** リソースで、DSC の外部で再起動が保留されているかどうかを検出します。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-111">Using this flag, the **PendingReboot** resource in the [ComputerManagementDsc](https://github.com/PowerShell/ComputerManagementDsc) DSC Resource module detects if a reboot is pending outside of DSC.</span></span>

<span data-ttu-id="f0fd4-112">ご利用の[構成](configurations.md)では、ノードの再起動を必要とするステップを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-112">Your [configurations](configurations.md) may perform steps that require the Node to reboot.</span></span> <span data-ttu-id="f0fd4-113">これには次のような内容を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-113">This could include things such as:</span></span>

- <span data-ttu-id="f0fd4-114">Windows の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="f0fd4-114">Windows updates</span></span>
- <span data-ttu-id="f0fd4-115">ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="f0fd4-115">Software install</span></span>
- <span data-ttu-id="f0fd4-116">ファイル名の変更</span><span class="sxs-lookup"><span data-stu-id="f0fd4-116">File renames</span></span>
- <span data-ttu-id="f0fd4-117">コンピューター名の変更</span><span class="sxs-lookup"><span data-stu-id="f0fd4-117">Computer rename</span></span>

<span data-ttu-id="f0fd4-118">**PendingReboot** リソースでは、特定のコンピューターの場所を確認して、再起動が保留中かどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-118">The **PendingReboot** resource checks specific computer locations to determine if a reboot is pending.</span></span> <span data-ttu-id="f0fd4-119">ノードで DSC の外部で再起動が必要な場合、 **PendingReboot** リソースでは `$global:DSCMachineStatus` フラグに `1` を設定して、再起動が強制され、保留中の状態が解決されます。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-119">If the Node requires a reboot outside of DSC, the **PendingReboot** resource sets the `$global:DSCMachineStatus` flag to `1` forcing a reboot and resolving the pending condition.</span></span>

> [!NOTE]
> <span data-ttu-id="f0fd4-120">任意の DSC リソースにより、`Set-TargetResource` 関数にこのフラグを設定することで、LCM にノードを再起動するように指示できます。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-120">Any DSC resource can instruct the LCM to reboot the node by setting this flag in the `Set-TargetResource` function.</span></span> <span data-ttu-id="f0fd4-121">詳細については、「[MOF を使用したカスタム DSC リソースの記述](../resources/authoringResourceMOF.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-121">For more information, see [Writing a custom DSC resource with MOF](../resources/authoringResourceMOF.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="f0fd4-122">構文</span><span class="sxs-lookup"><span data-stu-id="f0fd4-122">Syntax</span></span>

```
PendingReboot [String] #ResourceName
{
    Name = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
    [SkipCcmClientSDK = [bool]]
    [SkipComponentBasedServicing = [bool]]
    [SkipPendingComputerRename = [bool]]
    [SkipPendingFileRename = [bool]]
    [SkipWindowsUpdate = [bool]]
}
```

## <a name="properties"></a><span data-ttu-id="f0fd4-123">Properties</span><span class="sxs-lookup"><span data-stu-id="f0fd4-123">Properties</span></span>

| <span data-ttu-id="f0fd4-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f0fd4-124">Property</span></span> | <span data-ttu-id="f0fd4-125">説明</span><span class="sxs-lookup"><span data-stu-id="f0fd4-125">Description</span></span> |
| --- | --- |
| <span data-ttu-id="f0fd4-126">名前</span><span class="sxs-lookup"><span data-stu-id="f0fd4-126">Name</span></span>| <span data-ttu-id="f0fd4-127">構成内のリソースのインスタンスごとに一意である必要がある必須のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-127">Required parameter that must be unique per instance of the resource within a configuration.</span></span>|
| <span data-ttu-id="f0fd4-128">SkipComponentBasedServicing</span><span class="sxs-lookup"><span data-stu-id="f0fd4-128">SkipComponentBasedServicing</span></span> | <span data-ttu-id="f0fd4-129">コンポーネント ベース サービシング コンポーネントによってトリガーされた再起動がスキップされます。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-129">Skip reboots triggered by the Component-Based Servicing component.</span></span> |
| <span data-ttu-id="f0fd4-130">SkipWindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="f0fd4-130">SkipWindowsUpdate</span></span> | <span data-ttu-id="f0fd4-131">Windows の更新プログラムによってトリガーされた再起動がスキップされます。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-131">Skip reboots triggered by Windows Update.</span></span>|
| <span data-ttu-id="f0fd4-132">SkipPendingFileRename</span><span class="sxs-lookup"><span data-stu-id="f0fd4-132">SkipPendingFileRename</span></span> | <span data-ttu-id="f0fd4-133">保留中のファイル名の変更による再起動がスキップされます。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-133">Skip pending file rename reboots.</span></span> |
| <span data-ttu-id="f0fd4-134">SkipCcmClientSDK</span><span class="sxs-lookup"><span data-stu-id="f0fd4-134">SkipCcmClientSDK</span></span> | <span data-ttu-id="f0fd4-135">ConfigMgr クライアントによってトリガーされた再起動がスキップされます。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-135">Skip reboots triggered by the ConfigMgr client.</span></span> |
| <span data-ttu-id="f0fd4-136">SkipComputerRename</span><span class="sxs-lookup"><span data-stu-id="f0fd4-136">SkipComputerRename</span></span> | <span data-ttu-id="f0fd4-137">コンピューター名の変更によってトリガーされた再起動がスキップされます。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-137">Skip reboots triggered by Computer renames.</span></span> |
| <span data-ttu-id="f0fd4-138">PSDSCRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="f0fd4-138">PSDSCRunAsCredential</span></span> | <span data-ttu-id="f0fd4-139">v5 でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-139">Supported in v5.</span></span> <span data-ttu-id="f0fd4-140">特定のユーザーとしてリソースを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-140">Executes the resource as the specified user.</span></span> |
| <span data-ttu-id="f0fd4-141">DependsOn</span><span class="sxs-lookup"><span data-stu-id="f0fd4-141">DependsOn</span></span> | <span data-ttu-id="f0fd4-142">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-142">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="f0fd4-143">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-143">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType** , the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> <span data-ttu-id="f0fd4-144">詳細については、[DependsOn の使用](resource-depends-on.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-144">For more information, see [Using DependsOn](resource-depends-on.md)</span></span>|

## <a name="example"></a><span data-ttu-id="f0fd4-145">例</span><span class="sxs-lookup"><span data-stu-id="f0fd4-145">Example</span></span>

<span data-ttu-id="f0fd4-146">次の例では、[xExchange](https://github.com/PowerShell/xExchange) リソースを使用して Microsoft Exchange をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-146">The following example installs Microsoft Exchange using the [xExchange](https://github.com/PowerShell/xExchange) resource.</span></span> <span data-ttu-id="f0fd4-147">インストールの間中、 **PendingReboot** リソースはノードの再起動に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-147">Throughout the install, the **PendingReboot** resource is used to reboot the Node.</span></span>

> [!NOTE]
> <span data-ttu-id="f0fd4-148">この例には、Exchange サーバーをフォレストに追加する権限を持つ、アカウントの資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-148">This example requires the credential of an account that has rights to add an Exchange server to the forest.</span></span> <span data-ttu-id="f0fd4-149">DSC での資格情報の使用に関する詳細については、「[DSC での資格情報の処理](../configurations/configDataCredentials.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-149">For more information on using credentials in DSC, see [Handling Credentials in DSC](../configurations/configDataCredentials.md)</span></span>

```powershell
$ConfigurationData = @{
    AllNodes = @(
        @{
            NodeName                    = '*'
            PSDSCAllowPlainTextPassword = $true
        },
        @{
            NodeName = 'DSCPULL-1'
        }
    )
}

Configuration Example
{
    param
    (
        [Parameter(Mandatory = $true)]
        [System.Management.Automation.PSCredential]
        $ExchangeAdminCredential
    )

    Import-DscResource -Module xExchange
    Import-DscResource -Module ComputerManagementDsc

    Node $AllNodes.NodeName
    {
        # Copy the Exchange setup files locally
        File ExchangeBinaries
        {
            Ensure          = 'Present'
            Type            = 'Directory'
            Recurse         = $true
            SourcePath      = '\\rras-1\Binaries\E15CU6'
            DestinationPath = 'C:\Binaries\E15CU6'
        }

        # Check if a reboot is needed before installing Exchange
        PendingReboot BeforeExchangeInstall
        {
            Name       = 'BeforeExchangeInstall'
            DependsOn  = '[File]ExchangeBinaries'
        }

        # Do the Exchange install
        xExchInstall InstallExchange
        {
            Path       = 'C:\Binaries\E15CU6\Setup.exe'
            Arguments  = '/mode:Install /role:Mailbox /Iacceptexchangeserverlicenseterms'
            Credential = $ExchangeAdminCredential
            DependsOn  = '[PendingReboot]BeforeExchangeInstall'
        }

        # See if a reboot is required after installing Exchange
        PendingReboot AfterExchangeInstall
        {
            Name      = 'AfterExchangeInstall'
            DependsOn = '[xExchInstall]InstallExchange'
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="f0fd4-150">この例では、再起動と、再起動後に構成を継続できるように、ローカル構成マネージャーを構成しているとします。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-150">This example assumes that you have configured your Local Configuration Manager to allow reboots and continue the configuration after a reboot.</span></span>

## <a name="where-to-download"></a><span data-ttu-id="f0fd4-151">ダウンロードする場所</span><span class="sxs-lookup"><span data-stu-id="f0fd4-151">Where to Download</span></span>

<span data-ttu-id="f0fd4-152">次の場所でこのトピックで使用したリソースをダウンロードできます。PowerShell ギャラリーを使用してダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f0fd4-152">You can download the resources used in this topic at the following locations, or by using the PowerShell gallery.</span></span>

- [<span data-ttu-id="f0fd4-153">ComputerManagementDsc</span><span class="sxs-lookup"><span data-stu-id="f0fd4-153">ComputerManagementDsc</span></span>](https://github.com/PowerShell/ComputerManagementDsc)
- [<span data-ttu-id="f0fd4-154">xExchange</span><span class="sxs-lookup"><span data-stu-id="f0fd4-154">xExchange</span></span>](https://github.com/PowerShell/xExchange)
