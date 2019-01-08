---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WaitForAny リソース
ms.openlocfilehash: 39e90f0df3459b8891ed46e02ae82c45a285e7f5
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047654"
---
# <a name="dsc-waitforany-resource"></a><span data-ttu-id="da1fe-103">DSC WaitForAny リソース</span><span class="sxs-lookup"><span data-stu-id="da1fe-103">DSC WaitForAny Resource</span></span>

> <span data-ttu-id="da1fe-104">適用先:Windows PowerShell 5.1 以降</span><span class="sxs-lookup"><span data-stu-id="da1fe-104">Applies To: Windows PowerShell 5.1 and later</span></span>

<span data-ttu-id="da1fe-105">**WaitForSome** Desired State Configuration (DSC) リソースを [DSC 構成](../../../configurations/configurations.md)のノード ブロック内で使用して、他のノードの構成の依存関係を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="da1fe-105">The **WaitForSome** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](../../../configurations/configurations.md) to specify dependencies on configurations on other nodes.</span></span>

<span data-ttu-id="da1fe-106">このリソースは、**ResourceName** プロパティで指定されたリソースが、**NodeName** プロパティで定義された任意のターゲット ノードで目的の状態になった場合に成功します。</span><span class="sxs-lookup"><span data-stu-id="da1fe-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on any target nodes defined in the **NodeName** property.</span></span>


## <a name="syntax"></a><span data-ttu-id="da1fe-107">構文</span><span class="sxs-lookup"><span data-stu-id="da1fe-107">Syntax</span></span>

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

## <a name="properties"></a><span data-ttu-id="da1fe-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="da1fe-108">Properties</span></span>

|  <span data-ttu-id="da1fe-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="da1fe-109">Property</span></span>  |  <span data-ttu-id="da1fe-110">説明</span><span class="sxs-lookup"><span data-stu-id="da1fe-110">Description</span></span>   |
|---|---|
| <span data-ttu-id="da1fe-111">ResourceName</span><span class="sxs-lookup"><span data-stu-id="da1fe-111">ResourceName</span></span>| <span data-ttu-id="da1fe-112">依存するリソースの名前。</span><span class="sxs-lookup"><span data-stu-id="da1fe-112">The resource name to depend on.</span></span> <span data-ttu-id="da1fe-113">このリソースが別の構成に属している場合は、"[__リソースの種類__]__リソース名__::[__構成名__]::[__構成名__]" という形式で名前を指定してください。</span><span class="sxs-lookup"><span data-stu-id="da1fe-113">If this resource belongs to a different configuration, format the name as "[__ResourceType__]__ResourceName__::[__ConfigurationName__]::[__ConfigurationName__]"</span></span>|
| <span data-ttu-id="da1fe-114">NodeName</span><span class="sxs-lookup"><span data-stu-id="da1fe-114">NodeName</span></span>| <span data-ttu-id="da1fe-115">依存するリソースのターゲット ノード。</span><span class="sxs-lookup"><span data-stu-id="da1fe-115">The target nodes of the resource to depend on.</span></span>|
| <span data-ttu-id="da1fe-116">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="da1fe-116">RetryIntervalSec</span></span>| <span data-ttu-id="da1fe-117">再試行するまでの秒数。</span><span class="sxs-lookup"><span data-stu-id="da1fe-117">The number of seconds before retrying.</span></span> <span data-ttu-id="da1fe-118">最小値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="da1fe-118">Minimum is 1.</span></span>|
| <span data-ttu-id="da1fe-119">RetryCount</span><span class="sxs-lookup"><span data-stu-id="da1fe-119">RetryCount</span></span>| <span data-ttu-id="da1fe-120">再試行の回数の最大数。</span><span class="sxs-lookup"><span data-stu-id="da1fe-120">The maximum number of times to retry.</span></span>|
| <span data-ttu-id="da1fe-121">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="da1fe-121">ThrottleLimit</span></span>| <span data-ttu-id="da1fe-122">同時に接続するコンピューターの数。</span><span class="sxs-lookup"><span data-stu-id="da1fe-122">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="da1fe-123">既定では、new-cimsession の既定値です。</span><span class="sxs-lookup"><span data-stu-id="da1fe-123">Default is new-cimsession default.</span></span>|
| <span data-ttu-id="da1fe-124">DependsOn</span><span class="sxs-lookup"><span data-stu-id="da1fe-124">DependsOn</span></span> | <span data-ttu-id="da1fe-125">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="da1fe-125">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="da1fe-126">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="da1fe-126">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|

## <a name="example"></a><span data-ttu-id="da1fe-127">例</span><span class="sxs-lookup"><span data-stu-id="da1fe-127">Example</span></span>

<span data-ttu-id="da1fe-128">このリソースを使用する方法の例は、「[ノードの相互依存関係の指定](../../../configurations/crossNodeDependencies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da1fe-128">For an example of how to use this resource, see [Specifying cross-node dependencies](../../../configurations/crossNodeDependencies.md)</span></span>
