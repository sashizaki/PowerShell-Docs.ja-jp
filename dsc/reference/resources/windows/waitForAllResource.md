---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WaitForAll リソース
ms.openlocfilehash: c1125b7c5b68b9b520ed052800b6a2abf4e53b85
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67726867"
---
# <a name="dsc-waitforall-resource"></a><span data-ttu-id="ce519-103">DSC WaitForAll リソース</span><span class="sxs-lookup"><span data-stu-id="ce519-103">DSC WaitForAll Resource</span></span>

> <span data-ttu-id="ce519-104">適用先:Windows PowerShell 5.0 以降</span><span class="sxs-lookup"><span data-stu-id="ce519-104">Applies To: Windows PowerShell 5.0 and later</span></span>

<span data-ttu-id="ce519-105">**WaitForAll** Desired State Configuration (DSC) リソースを [DSC 構成](../../../configurations/configurations.md)のノード ブロック内で使用して、他のノードの構成の依存関係を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="ce519-105">The **WaitForAll** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](../../../configurations/configurations.md) to specify dependencies on configurations on other nodes.</span></span>

<span data-ttu-id="ce519-106">このリソースは、**ResourceName** プロパティで指定されたリソースが、**NodeName** プロパティで定義されたすべてのターゲット ノード上で目的の状態になった場合に成功します。</span><span class="sxs-lookup"><span data-stu-id="ce519-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on all target nodes defined in the **NodeName** property.</span></span>

> [!NOTE]
> <span data-ttu-id="ce519-107">**WaitForAll** リソースでは、Windows リモート管理を使用して他のノードの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="ce519-107">**WaitForAll** resource uses Windows Remote Management to check the state of other Nodes.</span></span>
> <span data-ttu-id="ce519-108">WinRM でのポートとセキュリティ要件の詳細については、「[PowerShell リモート処理のセキュリティに関する考慮事項](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce519-108">For more information about port and security requirements for WinRM, see [PowerShell Remoting Security Considerations](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span></span>

## <a name="syntax"></a><span data-ttu-id="ce519-109">構文</span><span class="sxs-lookup"><span data-stu-id="ce519-109">Syntax</span></span>

```
WaitForAll [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string]
    [ RetryIntervalSec = [Uint64] ]
    [ RetryCount = [Uint32] ]
    [ ThrottleLimit = [Uint32]]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="ce519-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ce519-110">Properties</span></span>

|  <span data-ttu-id="ce519-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ce519-111">Property</span></span>  |  <span data-ttu-id="ce519-112">説明</span><span class="sxs-lookup"><span data-stu-id="ce519-112">Description</span></span>   |
|---|---|
| <span data-ttu-id="ce519-113">ResourceName</span><span class="sxs-lookup"><span data-stu-id="ce519-113">ResourceName</span></span>| <span data-ttu-id="ce519-114">依存するリソースの名前。</span><span class="sxs-lookup"><span data-stu-id="ce519-114">The resource name to depend on.</span></span> <span data-ttu-id="ce519-115">このリソースが別の構成に属している場合は、"[__リソースの種類__]__リソース名__::[__構成名__]::[__構成名__]" という形式で名前を指定してください。</span><span class="sxs-lookup"><span data-stu-id="ce519-115">If this resource belongs to a different configuration, format the name as "[__ResourceType__]__ResourceName__::[__ConfigurationName__]::[__ConfigurationName__]"</span></span>|
| <span data-ttu-id="ce519-116">NodeName</span><span class="sxs-lookup"><span data-stu-id="ce519-116">NodeName</span></span>| <span data-ttu-id="ce519-117">依存するリソースのターゲット ノード。</span><span class="sxs-lookup"><span data-stu-id="ce519-117">The target nodes of the resource to depend on.</span></span>|
| <span data-ttu-id="ce519-118">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="ce519-118">RetryIntervalSec</span></span>| <span data-ttu-id="ce519-119">再試行するまでの秒数。</span><span class="sxs-lookup"><span data-stu-id="ce519-119">The number of seconds before retrying.</span></span> <span data-ttu-id="ce519-120">最小値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="ce519-120">Minimum is 1.</span></span>|
| <span data-ttu-id="ce519-121">RetryCount</span><span class="sxs-lookup"><span data-stu-id="ce519-121">RetryCount</span></span>| <span data-ttu-id="ce519-122">再試行の回数の最大数。</span><span class="sxs-lookup"><span data-stu-id="ce519-122">The maximum number of times to retry.</span></span>|
| <span data-ttu-id="ce519-123">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="ce519-123">ThrottleLimit</span></span>| <span data-ttu-id="ce519-124">同時に接続するコンピューターの数。</span><span class="sxs-lookup"><span data-stu-id="ce519-124">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="ce519-125">既定では、new-cimsession の既定値です。</span><span class="sxs-lookup"><span data-stu-id="ce519-125">Default is new-cimsession default.</span></span>|
| <span data-ttu-id="ce519-126">DependsOn</span><span class="sxs-lookup"><span data-stu-id="ce519-126">DependsOn</span></span> | <span data-ttu-id="ce519-127">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="ce519-127">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="ce519-128">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="ce519-128">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|

## <a name="example"></a><span data-ttu-id="ce519-129">例</span><span class="sxs-lookup"><span data-stu-id="ce519-129">Example</span></span>

<span data-ttu-id="ce519-130">このリソースを使用する方法の例は、「[ノードの相互依存関係の指定](../../../configurations/crossNodeDependencies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce519-130">For an example of how to use this resource, see [Specifying cross-node dependencies](../../../configurations/crossNodeDependencies.md)</span></span>
