---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: ノードの相互依存関係の指定
ms.openlocfilehash: 1bdfbd9f8a94809d6bf410eff525e1c877fb6aad
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402198"
---
# <a name="specifying-cross-node-dependencies"></a><span data-ttu-id="d6e11-103">ノードの相互依存関係の指定</span><span class="sxs-lookup"><span data-stu-id="d6e11-103">Specifying cross-node dependencies</span></span>

> <span data-ttu-id="d6e11-104">適用先:Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="d6e11-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="d6e11-105">DSC には、**WaitForAll**、**WaitForAny**、**WaitForSome** などの特別なリソースが用意されています。このリソースを構成で使用すると、他のノードの構成への依存関係を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="d6e11-105">DSC provides special resources, **WaitForAll**, **WaitForAny**, and **WaitForSome** that can be used in configurations to specify dependencies on configurations on other nodes.</span></span> <span data-ttu-id="d6e11-106">これらのリソースの動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d6e11-106">The behavior of these resources is as follows:</span></span>

- <span data-ttu-id="d6e11-107">**WaitForAll**:指定されたリソースがで定義されているすべてのターゲット ノードで目的の状態の場合、成功、 **NodeName**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d6e11-107">**WaitForAll**: Succeeds if the specified resource is in the desired state on all target nodes defined in the **NodeName** property.</span></span>
- <span data-ttu-id="d6e11-108">**WaitForAny**:指定されたリソースが目的の状態では、少なくとも 1 つで定義されているターゲット ノードの場合、成功、 **NodeName**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d6e11-108">**WaitForAny**: Succeeds if the specified resource is in the desired state on at least one of the target nodes defined in the **NodeName** property.</span></span>
- <span data-ttu-id="d6e11-109">**WaitForSome**:指定します、 **NodeCount**プロパティに加え、 **NodeName**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d6e11-109">**WaitForSome**: Specifies a **NodeCount** property in addition to a **NodeName** property.</span></span> <span data-ttu-id="d6e11-110">リソースは、**NodeName** プロパティで定義されたノードの最小数 (**NodeCount** で指定) で目的の状態になった場合に成功します。</span><span class="sxs-lookup"><span data-stu-id="d6e11-110">The resource succeeds if the resource is in the desired state on a minimum number of nodes (specified by **NodeCount**) defined by the **NodeName** property.</span></span>

## <a name="syntax"></a><span data-ttu-id="d6e11-111">構文</span><span class="sxs-lookup"><span data-stu-id="d6e11-111">Syntax</span></span>

<span data-ttu-id="d6e11-112">**WaitForAll**と**WaitForAny**リソースが同じ構文を共有します。</span><span class="sxs-lookup"><span data-stu-id="d6e11-112">The **WaitForAll** and **WaitForAny** resources share the same syntax.</span></span> <span data-ttu-id="d6e11-113">置換\<ResourceType\>いずれかでは、次の例で**WaitForAny**または**WaitForAll**します。</span><span class="sxs-lookup"><span data-stu-id="d6e11-113">Replace \<ResourceType\> in the example below with either **WaitForAny** or **WaitForAll**.</span></span>
<span data-ttu-id="d6e11-114">ように、 **DependsOn**キーワード、名前を"[ResourceType] ResourceName"として書式設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6e11-114">Like the **DependsOn** keyword, you will need to format the name as "[ResourceType]ResourceName".</span></span> <span data-ttu-id="d6e11-115">リソースが個別に属している場合[構成](configurations.md)、含める、 **ConfigurationName**書式設定された文字列で"[ResourceType] ResourceName:: [ConfigurationName]:: [ConfigurationName]"。</span><span class="sxs-lookup"><span data-stu-id="d6e11-115">If the resource belongs to a separate [Configuration](configurations.md), include the **ConfigurationName** in the formatted string "[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]".</span></span> <span data-ttu-id="d6e11-116">**NodeName**がコンピューター、またはノードで、現在のリソースが待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6e11-116">The **NodeName** is the computer, or Node, on which the current resource should wait.</span></span>

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

<span data-ttu-id="d6e11-117">**WaitForSome**リソースは追加しますが、上記の例のような構文、 **NodeCount**キー。</span><span class="sxs-lookup"><span data-stu-id="d6e11-117">The **WaitForSome** resource has a similar syntax to the example above, but adds the **NodeCount** key.</span></span> <span data-ttu-id="d6e11-118">**NodeCount**数のノードで、現在のリソースを待機する必要がありますかを示します。</span><span class="sxs-lookup"><span data-stu-id="d6e11-118">The **NodeCount** indicates how many Nodes the current resource should wait on.</span></span>

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

<span data-ttu-id="d6e11-119">すべて**WaitForXXXX**構文の次のキーを共有します。</span><span class="sxs-lookup"><span data-stu-id="d6e11-119">All **WaitForXXXX** share the following syntax keys.</span></span>

<span data-ttu-id="d6e11-120">| プロパティ | 説明 | |RetryIntervalSec |再試行するまでの秒数。</span><span class="sxs-lookup"><span data-stu-id="d6e11-120">|  Property  |  Description   | | RetryIntervalSec| The number of seconds before retrying.</span></span> <span data-ttu-id="d6e11-121">最小値は 1 |。|RetryCount |再試行の回数の最大数 |。|ThrottleLimit |同時に接続するコンピューターの数。</span><span class="sxs-lookup"><span data-stu-id="d6e11-121">Minimum is 1.| | RetryCount| The maximum number of times to retry.| | ThrottleLimit| Number of machines to connect simultaneously.</span></span> <span data-ttu-id="d6e11-122">既定値は`New-CimSession`既定 | |。DependsOn |このリソースを構成する前に、別のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="d6e11-122">Default is `New-CimSession` default.| | DependsOn | Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="d6e11-123">詳細については、次を参照してください[DependsOn](resource-depends-on.md)| |。PsDscRunAsCredential |参照してください[ユーザーの資格情報での DSC の使用](./runAsUser.md) |</span><span class="sxs-lookup"><span data-stu-id="d6e11-123">For more information, see [DependsOn](resource-depends-on.md)| | PsDscRunAsCredential | See [Using DSC with User Credentials](./runAsUser.md) |</span></span>


## <a name="using-waitforxxxx-resources"></a><span data-ttu-id="d6e11-124">WaitForXXXX リソースの使用</span><span class="sxs-lookup"><span data-stu-id="d6e11-124">Using WaitForXXXX resources</span></span>

<span data-ttu-id="d6e11-125">各**WaitForXXXX**リソースが、指定したノードで完了までに、指定されたリソースを待機します。</span><span class="sxs-lookup"><span data-stu-id="d6e11-125">Each **WaitForXXXX** resource waits for the specified resources to complete on the specified Node.</span></span> <span data-ttu-id="d6e11-126">その他のリソースで同じ構成できますし、*に依存して*、 **WaitForXXXX**リソースを使用して、 **DependsOn**キー。</span><span class="sxs-lookup"><span data-stu-id="d6e11-126">Other resources in the same Configuration can then *depend on* the **WaitForXXXX** resource using the **DependsOn** key.</span></span>

<span data-ttu-id="d6e11-127">たとえば、次の構成では、ターゲット ノードは **MyDC** ノード上の **xADDomain** リソースが完了するまで 15 秒間隔で最大 30 回試行しながら待機した後、ドメインに参加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d6e11-127">For example, in the following configuration, the target node is waiting for the **xADDomain** resource to finish on the **MyDC** node with maximum number of 30 retries, at 15-second intervals, before the target node can join the domain.</span></span>

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

<span data-ttu-id="d6e11-128">構成をコンパイルするときに、2 つの".mof"ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d6e11-128">When you compile the Configuration, two ".mof" files are generated.</span></span> <span data-ttu-id="d6e11-129">使用してターゲット ノードに".mof"の両方のファイルを適用、 [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration)コマンドレット</span><span class="sxs-lookup"><span data-stu-id="d6e11-129">Apply both ".mof" files to the target Nodes using the [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet</span></span>

><span data-ttu-id="d6e11-130">**注:** 既定では、WaitForXXX リソースは 1 回試行してから失敗します。</span><span class="sxs-lookup"><span data-stu-id="d6e11-130">**Note:** By default the WaitForXXX resources try one time and then fail.</span></span> <span data-ttu-id="d6e11-131">指定する、通常は必要ありません、 **RetryCount**と**RetryIntervalSec**します。</span><span class="sxs-lookup"><span data-stu-id="d6e11-131">Although it is not required, you will typically want to specify a **RetryCount** and **RetryIntervalSec**.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6e11-132">参照</span><span class="sxs-lookup"><span data-stu-id="d6e11-132">See Also</span></span>

- [<span data-ttu-id="d6e11-133">DSC 構成</span><span class="sxs-lookup"><span data-stu-id="d6e11-133">DSC Configurations</span></span>](configurations.md)
- [<span data-ttu-id="d6e11-134">リソースの依存関係を使用して、</span><span class="sxs-lookup"><span data-stu-id="d6e11-134">Use Resource Dependencies</span></span>](resource-depends-on.md)
- [<span data-ttu-id="d6e11-135">DSC リソース</span><span class="sxs-lookup"><span data-stu-id="d6e11-135">DSC Resources</span></span>](../resources/resources.md)
- [<span data-ttu-id="d6e11-136">ローカル構成マネージャーの構成</span><span class="sxs-lookup"><span data-stu-id="d6e11-136">Configuring The Local Configuration Manager</span></span>](../managing-nodes/metaConfig.md)
