---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WaitForSome リソース
ms.openlocfilehash: 08a5b96bee0b1b4475470e0d857dca79dee2b02e
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="dsc-waitforsome-resource"></a><span data-ttu-id="eb869-103">DSC WaitForSome リソース</span><span class="sxs-lookup"><span data-stu-id="eb869-103">DSC WaitForSome Resource</span></span>

> <span data-ttu-id="eb869-104">適用先: Windows PowerShell 5.0 以降</span><span class="sxs-lookup"><span data-stu-id="eb869-104">Applies To: Windows PowerShell 5.0 and later</span></span>

<span data-ttu-id="eb869-105">**WaitForAny** Desired State Configuration (DSC) リソースを [DSC 構成](configurations.md)のノード ブロック内で使用して、他のノードの構成の依存関係を指定できます。</span><span class="sxs-lookup"><span data-stu-id="eb869-105">The **WaitForAny** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](configurations.md) to specify dependencies on configurations on other nodes.</span></span>

<span data-ttu-id="eb869-106">このリソースは、**ResourceName** プロパティで指定されたリソースが、**NodeName** プロパティで定義された最小数 (**NodeCount** で指定) のノードで目的の状態になった場合に成功します。</span><span class="sxs-lookup"><span data-stu-id="eb869-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on a minimum number of nodes (specified by **NodeCount**) defined by the **NodeName** property.</span></span>


## <a name="syntax"></a><span data-ttu-id="eb869-107">構文</span><span class="sxs-lookup"><span data-stu-id="eb869-107">Syntax</span></span>

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

## <a name="properties"></a><span data-ttu-id="eb869-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="eb869-108">Properties</span></span>

|  <span data-ttu-id="eb869-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="eb869-109">Property</span></span>  |  <span data-ttu-id="eb869-110">説明</span><span class="sxs-lookup"><span data-stu-id="eb869-110">Description</span></span>   |
|---|---|
| <span data-ttu-id="eb869-111">NodeCount</span><span class="sxs-lookup"><span data-stu-id="eb869-111">NodeCount</span></span>| <span data-ttu-id="eb869-112">このリソースが成功するために、目的の状態にする必要があるノードの最小数。</span><span class="sxs-lookup"><span data-stu-id="eb869-112">The minimum number of nodes that must be in the desired state for this resource to succeed.</span></span>|
| <span data-ttu-id="eb869-113">NodeName</span><span class="sxs-lookup"><span data-stu-id="eb869-113">NodeName</span></span>| <span data-ttu-id="eb869-114">依存するリソースのターゲット ノード。</span><span class="sxs-lookup"><span data-stu-id="eb869-114">The target nodes of the resource to depend on.</span></span>|
| <span data-ttu-id="eb869-115">ResourceName</span><span class="sxs-lookup"><span data-stu-id="eb869-115">ResourceName</span></span>| <span data-ttu-id="eb869-116">依存するリソースの名前。</span><span class="sxs-lookup"><span data-stu-id="eb869-116">The resource name to depend on.</span></span> <span data-ttu-id="eb869-117">このリソースが別の構成に属している場合は、"[__リソースの種類__]__リソース名__::[__構成名__]::[__構成名__]" という形式で名前を指定してください。</span><span class="sxs-lookup"><span data-stu-id="eb869-117">If this resource belongs to a different configuration, format the name as "[__ResourceType__]__ResourceName__::[__ConfigurationName__]::[__ConfigurationName__]"</span></span>|
| <span data-ttu-id="eb869-118">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="eb869-118">RetryIntervalSec</span></span>| <span data-ttu-id="eb869-119">再試行するまでの秒数。</span><span class="sxs-lookup"><span data-stu-id="eb869-119">The number of seconds before retrying.</span></span> <span data-ttu-id="eb869-120">最小値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="eb869-120">Minimum is 1.</span></span>|
| <span data-ttu-id="eb869-121">RetryCount</span><span class="sxs-lookup"><span data-stu-id="eb869-121">RetryCount</span></span>| <span data-ttu-id="eb869-122">再試行の回数の最大数。</span><span class="sxs-lookup"><span data-stu-id="eb869-122">The maximum number of times to retry.</span></span>|
| <span data-ttu-id="eb869-123">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="eb869-123">ThrottleLimit</span></span>| <span data-ttu-id="eb869-124">同時に接続するコンピューターの数。</span><span class="sxs-lookup"><span data-stu-id="eb869-124">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="eb869-125">既定では、new-cimsession の既定値です。</span><span class="sxs-lookup"><span data-stu-id="eb869-125">Default is new-cimsession default.</span></span>|
| <span data-ttu-id="eb869-126">DependsOn</span><span class="sxs-lookup"><span data-stu-id="eb869-126">DependsOn</span></span> | <span data-ttu-id="eb869-127">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="eb869-127">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="eb869-128">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="eb869-128">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|
| <span data-ttu-id="eb869-129">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="eb869-129">PsDscRunAsCredential</span></span> | <span data-ttu-id="eb869-130">[ユーザーの資格情報を指定した DSC の使用](https://docs.microsoft.com/powershell/dsc/runasuser)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb869-130">See [Using DSC with User Credentials](https://docs.microsoft.com/powershell/dsc/runasuser)</span></span> |


## <a name="example"></a><span data-ttu-id="eb869-131">例</span><span class="sxs-lookup"><span data-stu-id="eb869-131">Example</span></span>

<span data-ttu-id="eb869-132">このリソースを使用する方法の例は、「[ノードの相互依存関係の指定](crossNodeDependencies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb869-132">For an example of how to use this resource, see [Specifying cross-node dependencies](crossNodeDependencies.md)</span></span>