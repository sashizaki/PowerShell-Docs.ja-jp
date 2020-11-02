---
ms.date: 07/16/2020
ms.topic: reference
title: DSC WaitForAny リソース
description: DSC WaitForAny リソース
ms.openlocfilehash: d997176c81ec390b9e58f5a28cae1814ee3dbcde
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2020
ms.locfileid: "93143128"
---
# <a name="dsc-waitforany-resource"></a><span data-ttu-id="f83d3-103">DSC WaitForAny リソース</span><span class="sxs-lookup"><span data-stu-id="f83d3-103">DSC WaitForAny Resource</span></span>

> <span data-ttu-id="f83d3-104">適用先:Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="f83d3-104">Applies To: Windows PowerShell 5.1</span></span>

<span data-ttu-id="f83d3-105">**WaitForAny** Desired State Configuration (DSC) リソースを [DSC 構成](../../../configurations/configurations.md)のノード ブロック内で使用して、他のノードの構成の依存関係を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f83d3-105">The **WaitForAny** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](../../../configurations/configurations.md) to specify dependencies on configurations on other nodes.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

<span data-ttu-id="f83d3-106">このリソースは、 **ResourceName** プロパティで指定されたリソースが、 **NodeName** プロパティで定義された任意のターゲット ノードで目的の状態になった場合に成功します。</span><span class="sxs-lookup"><span data-stu-id="f83d3-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on any target nodes defined in the **NodeName** property.</span></span>

> [!NOTE]
> <span data-ttu-id="f83d3-107">**WaitForAny** リソースでは、Windows リモート管理を使用して他のノードの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="f83d3-107">**WaitForAny** resource uses Windows Remote Management to check the state of other Nodes.</span></span> <span data-ttu-id="f83d3-108">WinRM でのポートとセキュリティ要件の詳細については、「[PowerShell リモート処理のセキュリティに関する考慮事項](/powershell/scripting/learn/remoting/winrmsecurity)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f83d3-108">For more information about port and security requirements for WinRM, see [PowerShell Remoting Security Considerations](/powershell/scripting/learn/remoting/winrmsecurity).</span></span>

## <a name="syntax"></a><span data-ttu-id="f83d3-109">構文</span><span class="sxs-lookup"><span data-stu-id="f83d3-109">Syntax</span></span>

```Syntax
WaitForAny [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string[]]
    [ RetryIntervalSec = [Uint64] ]
    [ RetryCount = [Uint32] ]
    [ ThrottleLimit = [Uint32]]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="f83d3-110">Properties</span><span class="sxs-lookup"><span data-stu-id="f83d3-110">Properties</span></span>

|<span data-ttu-id="f83d3-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f83d3-111">Property</span></span> |<span data-ttu-id="f83d3-112">説明</span><span class="sxs-lookup"><span data-stu-id="f83d3-112">Description</span></span> |
|---|---|
|<span data-ttu-id="f83d3-113">ResourceName</span><span class="sxs-lookup"><span data-stu-id="f83d3-113">ResourceName</span></span> |<span data-ttu-id="f83d3-114">依存するリソースの名前。</span><span class="sxs-lookup"><span data-stu-id="f83d3-114">The resource name to depend on.</span></span> <span data-ttu-id="f83d3-115">このリソースが別の構成に属している場合は、名前を `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]` という書式に設定します。</span><span class="sxs-lookup"><span data-stu-id="f83d3-115">If this resource belongs to a different configuration, format the name as `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`.</span></span> |
|<span data-ttu-id="f83d3-116">NodeName</span><span class="sxs-lookup"><span data-stu-id="f83d3-116">NodeName</span></span> |<span data-ttu-id="f83d3-117">依存するリソースのターゲット ノード。</span><span class="sxs-lookup"><span data-stu-id="f83d3-117">The target nodes of the resource to depend on.</span></span> |
|<span data-ttu-id="f83d3-118">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="f83d3-118">RetryIntervalSec</span></span> |<span data-ttu-id="f83d3-119">再試行するまでの秒数。</span><span class="sxs-lookup"><span data-stu-id="f83d3-119">The number of seconds before retrying.</span></span> <span data-ttu-id="f83d3-120">最小値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="f83d3-120">Minimum is 1.</span></span> |
|<span data-ttu-id="f83d3-121">RetryCount</span><span class="sxs-lookup"><span data-stu-id="f83d3-121">RetryCount</span></span> |<span data-ttu-id="f83d3-122">再試行の回数の最大数。</span><span class="sxs-lookup"><span data-stu-id="f83d3-122">The maximum number of times to retry.</span></span> |
|<span data-ttu-id="f83d3-123">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="f83d3-123">ThrottleLimit</span></span> |<span data-ttu-id="f83d3-124">同時に接続するコンピューターの数。</span><span class="sxs-lookup"><span data-stu-id="f83d3-124">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="f83d3-125">既定値は、`New-CimSession` の既定値です。</span><span class="sxs-lookup"><span data-stu-id="f83d3-125">Default is `New-CimSession` default.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="f83d3-126">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="f83d3-126">Common properties</span></span>

|<span data-ttu-id="f83d3-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f83d3-127">Property</span></span> |<span data-ttu-id="f83d3-128">説明</span><span class="sxs-lookup"><span data-stu-id="f83d3-128">Description</span></span> |
|---|---|
|<span data-ttu-id="f83d3-129">DependsOn</span><span class="sxs-lookup"><span data-stu-id="f83d3-129">DependsOn</span></span> |<span data-ttu-id="f83d3-130">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="f83d3-130">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="f83d3-131">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="f83d3-131">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="f83d3-132">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="f83d3-132">PsDscRunAsCredential</span></span> |<span data-ttu-id="f83d3-133">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="f83d3-133">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="f83d3-134">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="f83d3-134">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="f83d3-135">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f83d3-135">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="f83d3-136">例</span><span class="sxs-lookup"><span data-stu-id="f83d3-136">Example</span></span>

<span data-ttu-id="f83d3-137">このリソースを使用する方法の例は、「[ノードの相互依存関係の指定](../../../configurations/crossNodeDependencies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f83d3-137">For an example of how to use this resource, see [Specifying cross-node dependencies](../../../configurations/crossNodeDependencies.md)</span></span>
