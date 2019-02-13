---
ms.date: 1/17/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: ノードを再起動する
ms.openlocfilehash: 33ecd98aa62c3dc94a8ff2213fd3e68bf0c05cb7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "55680741"
---
# <a name="reboot-a-node"></a><span data-ttu-id="2ac7d-103">ノードを再起動する</span><span class="sxs-lookup"><span data-stu-id="2ac7d-103">Reboot a Node</span></span>

> [!NOTE]
> <span data-ttu-id="2ac7d-104">このトピックでは、ノードを再起動する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-104">This topic talks about how to reboot a Node.</span></span> <span data-ttu-id="2ac7d-105">成功するために再起動するために、 **ActionAfterReboot**と**RebootNodeIfNeeded** LCM 設定が適切に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-105">In order for the reboot to be successful the **ActionAfterReboot** and **RebootNodeIfNeeded** LCM settings need to be configured properly.</span></span>
> <span data-ttu-id="2ac7d-106">詳細については、ローカル構成マネージャー設定を参照してください。[ローカル構成マネージャーを構成する](../managing-nodes/metaConfig.md)、または[ローカル構成マネージャー (v4) の構成](../managing-nodes/metaConfig4.md)します。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-106">To read about Local Configuration Manager settings, see [Configure the Local Configuration Manager](../managing-nodes/metaConfig.md), or [Configure the Local Configuration Manager (v4)](../managing-nodes/metaConfig4.md).</span></span>

<span data-ttu-id="2ac7d-107">ノードを再起動できるから、リソースを使用して、`$global:DSCMachineStatus`フラグ。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-107">Nodes can be rebooted from within a resource, by using the `$global:DSCMachineStatus` flag.</span></span> <span data-ttu-id="2ac7d-108">このフラグを設定`1`で、`Set-TargetResource`関数はすぐ後にノードを再起動するように LCM、**設定**現在のリソースのメソッド。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-108">Setting this flag to `1` in the `Set-TargetResource` function forces the LCM to reboot the Node directly after the **Set** method of the current resource.</span></span> <span data-ttu-id="2ac7d-109">このフラグを使用して、 **xPendingReboot**かどうか、再起動が保留中にリソースが検出した DSC の外部でします。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-109">Using this flag, the **xPendingReboot** resource detects if a reboot is pending outside of DSC.</span></span>

<span data-ttu-id="2ac7d-110">[構成](configurations.md)を再起動するノードを必要とするための手順を実行することがあります。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-110">Your [configurations](configurations.md) may perform steps that require the Node to reboot.</span></span> <span data-ttu-id="2ac7d-111">これは、ことなどがあります。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-111">This could include things such as:</span></span>

- <span data-ttu-id="2ac7d-112">Windows: 更新プログラム</span><span class="sxs-lookup"><span data-stu-id="2ac7d-112">Windows updates</span></span>
- <span data-ttu-id="2ac7d-113">ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="2ac7d-113">Software install</span></span>
- <span data-ttu-id="2ac7d-114">ファイルの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-114">File renames</span></span>
- <span data-ttu-id="2ac7d-115">コンピューター名の変更</span><span class="sxs-lookup"><span data-stu-id="2ac7d-115">Computer rename</span></span>

<span data-ttu-id="2ac7d-116">**XPendingReboot**リソースは、再起動が保留中であるかどうかを特定のコンピューターの場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-116">The **xPendingReboot** resource checks specific computer locations to determine if a reboot is pending.</span></span> <span data-ttu-id="2ac7d-117">ノードが、DSC の外部で再起動が必要な場合、 **xPendingReboot**リソース セット、`$global:DSCMachineStatus`フラグを`1`強制的に再起動して、保留中の条件を解決します。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-117">If the Node requires a reboot outside of DSC, the **xPendingReboot** resource sets the `$global:DSCMachineStatus` flag to `1` forcing a reboot and resolving the pending condition.</span></span>

> [!NOTE]
> <span data-ttu-id="2ac7d-118">すべての DSC リソースでこのフラグを設定してノードを再起動するように LCM を指示できます、`Set-TargetResource`関数。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-118">Any DSC resource can instruct the LCM to reboot the node by setting this flag in the `Set-TargetResource` function.</span></span> <span data-ttu-id="2ac7d-119">詳細については、次を参照してください。 [MOF を使用したカスタム DSC リソースの記述](../resources/authoringResourceMOF.md)します。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-119">For more information, see [Writing a custom DSC resource with MOF](../resources/authoringResourceMOF.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="2ac7d-120">構文</span><span class="sxs-lookup"><span data-stu-id="2ac7d-120">Syntax</span></span>

```
xPendingReboot [String] #ResourceName
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

## <a name="properties"></a><span data-ttu-id="2ac7d-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2ac7d-121">Properties</span></span>

| <span data-ttu-id="2ac7d-122">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2ac7d-122">Property</span></span> | <span data-ttu-id="2ac7d-123">説明</span><span class="sxs-lookup"><span data-stu-id="2ac7d-123">Description</span></span> |
| --- | --- |
| <span data-ttu-id="2ac7d-124">名前</span><span class="sxs-lookup"><span data-stu-id="2ac7d-124">Name</span></span>| <span data-ttu-id="2ac7d-125">必須のパラメーターです、構成内でリソースのインスタンスごとに一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-125">Required parameter that must be unique per instance of the resource within a configuration.</span></span>|
| <span data-ttu-id="2ac7d-126">SkipComponentBasedServicing</span><span class="sxs-lookup"><span data-stu-id="2ac7d-126">SkipComponentBasedServicing</span></span> | <span data-ttu-id="2ac7d-127">コンポーネント ベース サービシング コンポーネントによってトリガーされるスキップ再起動します。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-127">Skip reboots triggered by the Component-Based Servicing component.</span></span> |
| <span data-ttu-id="2ac7d-128">SkipWindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="2ac7d-128">SkipWindowsUpdate</span></span> | <span data-ttu-id="2ac7d-129">Windows Update によってトリガーされるスキップ再起動します。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-129">Skip reboots triggered by Windows Update.</span></span>|
| <span data-ttu-id="2ac7d-130">SkipPendingFileRename</span><span class="sxs-lookup"><span data-stu-id="2ac7d-130">SkipPendingFileRename</span></span> | <span data-ttu-id="2ac7d-131">保留中のファイル名の変更の再起動をスキップします。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-131">Skip pending file rename reboots.</span></span> |
| <span data-ttu-id="2ac7d-132">SkipCcmClientSDK</span><span class="sxs-lookup"><span data-stu-id="2ac7d-132">SkipCcmClientSDK</span></span> | <span data-ttu-id="2ac7d-133">ConfigMgr クライアントによってトリガーされるスキップ再起動します。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-133">Skip reboots triggered by the ConfigMgr client.</span></span> |
| <span data-ttu-id="2ac7d-134">SkipComputerRename</span><span class="sxs-lookup"><span data-stu-id="2ac7d-134">SkipComputerRename</span></span> | <span data-ttu-id="2ac7d-135">Skip は、コンピューター名の変更によってトリガーされたを再起動します。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-135">Skip reboots triggerd by Computer renames.</span></span> |
| <span data-ttu-id="2ac7d-136">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="2ac7d-136">PSDSCRunAsCredential</span></span> | <span data-ttu-id="2ac7d-137">V5 でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-137">Supported in v5.</span></span> <span data-ttu-id="2ac7d-138">指定したユーザーとしてリソースを実行します。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-138">Executes the resource as the specified user.</span></span> |
| <span data-ttu-id="2ac7d-139">DependsOn</span><span class="sxs-lookup"><span data-stu-id="2ac7d-139">DependsOn</span></span> | <span data-ttu-id="2ac7d-140">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-140">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="2ac7d-141">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-141">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> <span data-ttu-id="2ac7d-142">詳細については、次を参照してください[DependsOn の使用。](resource-depends-on.md)</span><span class="sxs-lookup"><span data-stu-id="2ac7d-142">For more information, see [Using DependsOn](resource-depends-on.md)</span></span>|

## <a name="example"></a><span data-ttu-id="2ac7d-143">例</span><span class="sxs-lookup"><span data-stu-id="2ac7d-143">Example</span></span>

<span data-ttu-id="2ac7d-144">次の例は、Microsoft Exchange を使用してをインストール、 [xExchange](https://github.com/PowerShell/xExchange)リソース。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-144">The following example installs Microsoft Exchange using the [xExchange](https://github.com/PowerShell/xExchange) resource.</span></span>
<span data-ttu-id="2ac7d-145">インストール全体にわたって、 **xPendingReboot**リソースを使用して、ノードを再起動します。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-145">Throughout the install, the **xPendingReboot** resource is used to reboot the Node.</span></span>

> [!NOTE]
> <span data-ttu-id="2ac7d-146">この例では、フォレストに Exchange サーバーを追加する権限を持つアカウントの資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-146">This example requires the credential of an account that has rights to add an Exchange server to the forest.</span></span> <span data-ttu-id="2ac7d-147">DSC での資格情報の使用の詳細については、次を参照してください[DSC での資格情報の処理。](../configurations/configDataCredentials.md)</span><span class="sxs-lookup"><span data-stu-id="2ac7d-147">For more information on using credentials in DSC, see [Handling Credentials in DSC](../configurations/configDataCredentials.md)</span></span>

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
    Import-DscResource -Module xPendingReboot

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
        xPendingReboot BeforeExchangeInstall
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
            DependsOn  = '[xPendingReboot]BeforeExchangeInstall'
        }

        # See if a reboot is required after installing Exchange
        xPendingReboot AfterExchangeInstall
        {
            Name      = 'AfterExchangeInstall'
            DependsOn = '[xExchInstall]InstallExchange'
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="2ac7d-148">この例では、再起動を許可し、再起動後に構成を続行する、ローカル構成マネージャーが構成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-148">This example assumes that you have configured your Local Configuration Manager to allow reboots and continue the configuration after a reboot.</span></span>

## <a name="where-to-download"></a><span data-ttu-id="2ac7d-149">ダウンロードする場所</span><span class="sxs-lookup"><span data-stu-id="2ac7d-149">Where to Download</span></span>

<span data-ttu-id="2ac7d-150">または、PowerShell ギャラリーを使用して、次の場所では、このトピックで使用されるリソースをダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="2ac7d-150">You can download the resources used in this topic at the following locations, or by using the PowerShell gallery.</span></span>

- [<span data-ttu-id="2ac7d-151">xPendingReboot</span><span class="sxs-lookup"><span data-stu-id="2ac7d-151">xPendingReboot</span></span>](https://github.com/PowerShell/xPendingReboot)
- [<span data-ttu-id="2ac7d-152">xExchange</span><span class="sxs-lookup"><span data-stu-id="2ac7d-152">xExchange</span></span>](https://github.com/PowerShell/xExchange)
