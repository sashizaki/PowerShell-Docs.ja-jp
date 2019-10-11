---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: ノードの相互依存関係の指定
ms.openlocfilehash: 62e553d894897ae1908745c2788b7b7b9cbe50ff
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954109"
---
# <a name="specifying-cross-node-dependencies"></a><span data-ttu-id="2ea8d-103">ノードの相互依存関係の指定</span><span class="sxs-lookup"><span data-stu-id="2ea8d-103">Specifying cross-node dependencies</span></span>

> <span data-ttu-id="2ea8d-104">適用先:Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="2ea8d-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="2ea8d-105">DSC には、**WaitForAll**、**WaitForAny**、**WaitForSome** などの特別なリソースが用意されています。このリソースを構成で使用すると、他のノードの構成への依存関係を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-105">DSC provides special resources, **WaitForAll**, **WaitForAny**, and **WaitForSome** that can be used in configurations to specify dependencies on configurations on other nodes.</span></span> <span data-ttu-id="2ea8d-106">これらのリソースの動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-106">The behavior of these resources is as follows:</span></span>

- <span data-ttu-id="2ea8d-107">**WaitForAll**: **NodeName** プロパティで定義されているすべてのターゲット ノードで、指定されたリソースが目的の状態である場合に成功します。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-107">**WaitForAll**: Succeeds if the specified resource is in the desired state on all target nodes defined in the **NodeName** property.</span></span>
- <span data-ttu-id="2ea8d-108">**WaitForAny**: **NodeName** プロパティで定義されているターゲット ノードの少なくとも 1 つで、指定されたリソースが目的の状態である場合に成功します。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-108">**WaitForAny**: Succeeds if the specified resource is in the desired state on at least one of the target nodes defined in the **NodeName** property.</span></span>
- <span data-ttu-id="2ea8d-109">**WaitForSome**: **NodeName** プロパティのほか、**NodeCount** プロパティも指定します。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-109">**WaitForSome**: Specifies a **NodeCount** property in addition to a **NodeName** property.</span></span> <span data-ttu-id="2ea8d-110">リソースは、**NodeName** プロパティで定義されたノードの最小数 (**NodeCount** で指定) で目的の状態になった場合に成功します。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-110">The resource succeeds if the resource is in the desired state on a minimum number of nodes (specified by **NodeCount**) defined by the **NodeName** property.</span></span>

## <a name="syntax"></a><span data-ttu-id="2ea8d-111">構文</span><span class="sxs-lookup"><span data-stu-id="2ea8d-111">Syntax</span></span>

<span data-ttu-id="2ea8d-112">**WaitForAll** リソースと **WaitForAny** リソースは構文が同じです。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-112">The **WaitForAll** and **WaitForAny** resources share the same syntax.</span></span> <span data-ttu-id="2ea8d-113">次の例の \<ResourceType\> を、**WaitForAny** または **WaitForAll** に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-113">Replace \<ResourceType\> in the example below with either **WaitForAny** or **WaitForAll**.</span></span>
<span data-ttu-id="2ea8d-114">**DependsOn** キーワードと同じように、名前は "[ResourceType]ResourceName" という形式にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-114">Like the **DependsOn** keyword, you will need to format the name as "[ResourceType]ResourceName".</span></span> <span data-ttu-id="2ea8d-115">リソースが異なる [Configuration](configurations.md) に属している場合は、**ConfigurationName** を書式設定する文字列 "[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]" に含めます。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-115">If the resource belongs to a separate [Configuration](configurations.md), include the **ConfigurationName** in the formatted string "[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]".</span></span> <span data-ttu-id="2ea8d-116">**NodeName** は、現在のリソースが待機する必要があるコンピューターまたはノードです。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-116">The **NodeName** is the computer, or Node, on which the current resource should wait.</span></span>

```
<ResourceType> [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential]]
    [ RetryCount = [Uint32] ]
    [ RetryIntervalSec = [Uint64] ]
    [ ThrottleLimit = [Uint32]]
}
```

<span data-ttu-id="2ea8d-117">**WaitForSome** リソースは上の例と似た構文ですが、**NodeCount** キーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-117">The **WaitForSome** resource has a similar syntax to the example above, but adds the **NodeCount** key.</span></span> <span data-ttu-id="2ea8d-118">**NodeCount** は、現在のリソースが待機する必要のあるノードの数を示します。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-118">The **NodeCount** indicates how many Nodes the current resource should wait on.</span></span>

```
WaitForSome [String] #ResourceName
{
    NodeCount = [UInt32]
    NodeName = [string[]]
    ResourceName = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
    [RetryCount = [UInt32]]
    [RetryIntervalSec = [UInt64]]
    [ThrottleLimit = [UInt32]]
}
```

<span data-ttu-id="2ea8d-119">すべての **WaitForXXXX** が次の構文キーを共有します。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-119">All **WaitForXXXX** share the following syntax keys.</span></span>

|<span data-ttu-id="2ea8d-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2ea8d-120">Property</span></span>|  <span data-ttu-id="2ea8d-121">説明</span><span class="sxs-lookup"><span data-stu-id="2ea8d-121">Description</span></span>   |
|---------|---------------------|
| <span data-ttu-id="2ea8d-122">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="2ea8d-122">RetryIntervalSec</span></span>| <span data-ttu-id="2ea8d-123">再試行するまでの秒数。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-123">The number of seconds before retrying.</span></span> <span data-ttu-id="2ea8d-124">最小値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-124">Minimum is 1.</span></span>|
| <span data-ttu-id="2ea8d-125">RetryCount</span><span class="sxs-lookup"><span data-stu-id="2ea8d-125">RetryCount</span></span>| <span data-ttu-id="2ea8d-126">再試行の回数の最大数。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-126">The maximum number of times to retry.</span></span>|
| <span data-ttu-id="2ea8d-127">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="2ea8d-127">ThrottleLimit</span></span>| <span data-ttu-id="2ea8d-128">同時に接続するコンピューターの数。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-128">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="2ea8d-129">既定値は、`New-CimSession` の既定値です。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-129">Default is `New-CimSession` default.</span></span>|
| <span data-ttu-id="2ea8d-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="2ea8d-130">DependsOn</span></span> | <span data-ttu-id="2ea8d-131">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="2ea8d-132">詳細については、[DependsOn](resource-depends-on.md) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-132">For more information, see [DependsOn](resource-depends-on.md)</span></span>|
| <span data-ttu-id="2ea8d-133">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="2ea8d-133">PsDscRunAsCredential</span></span> | <span data-ttu-id="2ea8d-134">[ユーザーの資格情報を指定した DSC の使用](./runAsUser.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-134">See [Using DSC with User Credentials](./runAsUser.md)</span></span> |

## <a name="using-waitforxxxx-resources"></a><span data-ttu-id="2ea8d-135">WaitForXXXX リソースの使用</span><span class="sxs-lookup"><span data-stu-id="2ea8d-135">Using WaitForXXXX resources</span></span>

<span data-ttu-id="2ea8d-136">各 **WaitForXXXX** リソースは、指定されたノードで指定された数のリソースが完了するのを待機します。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-136">Each **WaitForXXXX** resource waits for the specified resources to complete on the specified Node.</span></span>
<span data-ttu-id="2ea8d-137">同じ Configuration の他のリソースは、**DependsOn** キーを使用して **WaitForXXXX** リソースに "*依存する*" ことができます。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-137">Other resources in the same Configuration can then *depend on* the **WaitForXXXX** resource using the **DependsOn** key.</span></span>

<span data-ttu-id="2ea8d-138">たとえば、次の構成では、ターゲット ノードは **MyDC** ノード上の **xADDomain** リソースが完了するまで 15 秒間隔で最大 30 回試行しながら待機した後、ドメインに参加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-138">For example, in the following configuration, the target node is waiting for the **xADDomain** resource to finish on the **MyDC** node with maximum number of 30 retries, at 15-second intervals, before the target node can join the domain.</span></span>

<span data-ttu-id="2ea8d-139">既定では、**WaitForXXX** リソースは 1 回試行してから失敗します。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-139">By default the **WaitForXXX** resources try one time and then fail.</span></span> <span data-ttu-id="2ea8d-140">これは必須ではありませんが、通常は、**RetryCount** と **RetryIntervalSec** を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-140">Although it is not required, you will typically want to specify a **RetryCount** and **RetryIntervalSec**.</span></span>

```powershell
Configuration JoinDomain
{
    Import-DscResource -Module xComputerManagement, xActiveDirectory

    Node myDC
    {
        WindowsFeature InstallAD
        {
            Ensure = 'Present'
            Name = 'AD-Domain-Services'
        }

        xADDomain NewDomain
        {
            DomainName = 'Contoso.com'
            DomainAdministratorCredential = (Get-Credential)
            SafemodeAdministratorPassword = (Get-Credential)
            DatabasePath = "C:\Windows\NTDS"
            LogPath = "C:\Windows\NTDS"
            SysvolPath = "C:\Windows\Sysvol"
        }
    }

    Node myDomainJoinedServer
    {
        WaitForAll DC
        {
            ResourceName      = '[xADDomain]NewDomain'
            NodeName          = 'MyDC'
            RetryIntervalSec  = 15
            RetryCount        = 30
        }

        xComputer JoinDomain
        {
            Name             = 'myPC'
            DomainName       = 'Contoso.com'
            Credential       = (Get-Credential)
            DependsOn        ='[WaitForAll]DC'
        }
    }
}
```

<span data-ttu-id="2ea8d-141">Configuration をコンパイルすると、2 つの ".mof" ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-141">When you compile the Configuration, two ".mof" files are generated.</span></span> <span data-ttu-id="2ea8d-142">[Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) コマンドレットを使って、両方の ".mof" ファイルをターゲットの Node に適用します</span><span class="sxs-lookup"><span data-stu-id="2ea8d-142">Apply both ".mof" files to the target Nodes using the [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet</span></span>

> [!NOTE]
> <span data-ttu-id="2ea8d-143">**WaitForXXX** リソースでは、Windows リモート管理を使用して他のノードの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-143">**WaitForXXX** resources use Windows Remote Management to check the state of other Nodes.</span></span>
> <span data-ttu-id="2ea8d-144">WinRM でのポートとセキュリティ要件の詳細については、「[PowerShell リモート処理のセキュリティに関する考慮事項](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ea8d-144">For more information about port and security requirements for WinRM, see [PowerShell Remoting Security Considerations](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span></span>

## <a name="see-also"></a><span data-ttu-id="2ea8d-145">参照</span><span class="sxs-lookup"><span data-stu-id="2ea8d-145">See Also</span></span>

- [<span data-ttu-id="2ea8d-146">DSC 構成</span><span class="sxs-lookup"><span data-stu-id="2ea8d-146">DSC Configurations</span></span>](configurations.md)
- [<span data-ttu-id="2ea8d-147">リソースの依存関係を使用する</span><span class="sxs-lookup"><span data-stu-id="2ea8d-147">Use Resource Dependencies</span></span>](resource-depends-on.md)
- [<span data-ttu-id="2ea8d-148">DSC リソース</span><span class="sxs-lookup"><span data-stu-id="2ea8d-148">DSC Resources</span></span>](../resources/resources.md)
- [<span data-ttu-id="2ea8d-149">ローカル構成マネージャーの構成</span><span class="sxs-lookup"><span data-stu-id="2ea8d-149">Configuring The Local Configuration Manager</span></span>](../managing-nodes/metaConfig.md)
