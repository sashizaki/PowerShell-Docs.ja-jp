---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "DSC WaitForAny リソース"
ms.openlocfilehash: 795c005c67c196ef9afb08af790fe2a1695392ec
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="dsc-waitforany-resource"></a><span data-ttu-id="8096e-103">DSC WaitForAny リソース</span><span class="sxs-lookup"><span data-stu-id="8096e-103">DSC WaitForAny Resource</span></span>

> <span data-ttu-id="8096e-104">適用先: Windows PowerShell 5.1 以降</span><span class="sxs-lookup"><span data-stu-id="8096e-104">Applies To: Windows PowerShell 5.1 and later</span></span>

<span data-ttu-id="8096e-105">**WaitForSome** Desired State Configuration (DSC) リソースを [DSC 構成](configurations.md)のノード ブロック内で使用して、他のノードの構成の依存関係を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="8096e-105">The **WaitForSome** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](configurations.md) to specify dependencies on configurations on other nodes.</span></span>

<span data-ttu-id="8096e-106">このリソースは **ResourceName** プロパティで指定されたリソースが、 **NodeName** プロパティで定義された任意のターゲット ノードで目的の状態になった場合に成功します。</span><span class="sxs-lookup"><span data-stu-id="8096e-106">This resource succeeds if if the resource specified by the **ResourceName** property is in the desired state on any target nodes defined in the **NodeName** property.</span></span>


## <a name="syntax"></a><span data-ttu-id="8096e-107">構文</span><span class="sxs-lookup"><span data-stu-id="8096e-107">Syntax</span></span>

```
WaitForAny [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string]
    [ RetryIntervalSec = [Uint64] ]
    [ RetryCount = [Uint32] ] 
    [ ThrottleLimit = [Uint32]]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="8096e-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8096e-108">Properties</span></span>

|  <span data-ttu-id="8096e-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8096e-109">Property</span></span>  |  <span data-ttu-id="8096e-110">説明</span><span class="sxs-lookup"><span data-stu-id="8096e-110">Description</span></span>   | 
|---|---| 
| <span data-ttu-id="8096e-111">ResourceName</span><span class="sxs-lookup"><span data-stu-id="8096e-111">ResourceName</span></span>| <span data-ttu-id="8096e-112">依存するリソースの名前。</span><span class="sxs-lookup"><span data-stu-id="8096e-112">The resource name to depend on.</span></span>| 
| <span data-ttu-id="8096e-113">NodeName</span><span class="sxs-lookup"><span data-stu-id="8096e-113">NodeName</span></span>| <span data-ttu-id="8096e-114">依存するリソースのターゲット ノード。</span><span class="sxs-lookup"><span data-stu-id="8096e-114">The target nodes of the resource to depend on.</span></span>| 
| <span data-ttu-id="8096e-115">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="8096e-115">RetryIntervalSec</span></span>| <span data-ttu-id="8096e-116">再試行するまでの秒数。</span><span class="sxs-lookup"><span data-stu-id="8096e-116">The number of seconds before retrying.</span></span> <span data-ttu-id="8096e-117">最小値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="8096e-117">Minimum is 1.</span></span>| 
| <span data-ttu-id="8096e-118">RetryCount</span><span class="sxs-lookup"><span data-stu-id="8096e-118">RetryCount</span></span>| <span data-ttu-id="8096e-119">再試行の回数の最大数。</span><span class="sxs-lookup"><span data-stu-id="8096e-119">The maximum number of times to retry.</span></span>| 
| <span data-ttu-id="8096e-120">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="8096e-120">ThrottleLimit</span></span>| <span data-ttu-id="8096e-121">同時に接続するコンピューターの数。</span><span class="sxs-lookup"><span data-stu-id="8096e-121">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="8096e-122">既定では、new-cimsession の既定値です。</span><span class="sxs-lookup"><span data-stu-id="8096e-122">Default is new-cimsession default.</span></span>| 
| <span data-ttu-id="8096e-123">DependsOn</span><span class="sxs-lookup"><span data-stu-id="8096e-123">DependsOn</span></span> | <span data-ttu-id="8096e-124">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="8096e-124">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="8096e-125">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="8096e-125">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|


## <a name="example"></a><span data-ttu-id="8096e-126">例</span><span class="sxs-lookup"><span data-stu-id="8096e-126">Example</span></span>

<span data-ttu-id="8096e-127">このリソースを使用する方法の例は、「[ノードの相互依存関係の指定](crossNodeDependencies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8096e-127">For an example of how to use this resource, see [Specifying cross-node dependencies](crossNodeDependencies.md)</span></span>

