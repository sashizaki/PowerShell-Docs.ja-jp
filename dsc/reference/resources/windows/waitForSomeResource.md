---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WaitForSome リソース
ms.openlocfilehash: 2260f37002171154a6f2c3996b2af1bd9120039d
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67726773"
---
# <a name="dsc-waitforsome-resource"></a><span data-ttu-id="9f0af-103">DSC WaitForSome リソース</span><span class="sxs-lookup"><span data-stu-id="9f0af-103">DSC WaitForSome Resource</span></span>

> <span data-ttu-id="9f0af-104">適用先:Windows PowerShell 5.0 以降</span><span class="sxs-lookup"><span data-stu-id="9f0af-104">Applies To: Windows PowerShell 5.0 and later</span></span>

<span data-ttu-id="9f0af-105">**WaitForSome** Desired State Configuration (DSC) リソースを [DSC 構成](../../../configurations/configurations.md)のノード ブロック内で使用して、他のノードの構成の依存関係を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="9f0af-105">The **WaitForSome** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](../../../configurations/configurations.md) to specify dependencies on configurations on other nodes.</span></span>

<span data-ttu-id="9f0af-106">このリソースは、**ResourceName** プロパティで指定されたリソースが、**NodeName** プロパティで定義された最小数 (**NodeCount** で指定) のノードで目的の状態になった場合に成功します。</span><span class="sxs-lookup"><span data-stu-id="9f0af-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on a minimum number of nodes (specified by **NodeCount**) defined by the **NodeName** property.</span></span>

> [!NOTE]
> <span data-ttu-id="9f0af-107">**WaitForSome** リソースでは、Windows リモート管理を使用して他のノードの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="9f0af-107">**WaitForSome** resource uses Windows Remote Management to check the state of other Nodes.</span></span>
> <span data-ttu-id="9f0af-108">WinRM でのポートとセキュリティ要件の詳細については、「[PowerShell リモート処理のセキュリティに関する考慮事項](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f0af-108">For more information about port and security requirements for WinRM, see [PowerShell Remoting Security Considerations](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span></span>

## <a name="syntax"></a><span data-ttu-id="9f0af-109">構文</span><span class="sxs-lookup"><span data-stu-id="9f0af-109">Syntax</span></span>

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

## <a name="properties"></a><span data-ttu-id="9f0af-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9f0af-110">Properties</span></span>

|  <span data-ttu-id="9f0af-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9f0af-111">Property</span></span>  |  <span data-ttu-id="9f0af-112">説明</span><span class="sxs-lookup"><span data-stu-id="9f0af-112">Description</span></span>   |
|---|---|
| <span data-ttu-id="9f0af-113">NodeCount</span><span class="sxs-lookup"><span data-stu-id="9f0af-113">NodeCount</span></span>| <span data-ttu-id="9f0af-114">このリソースが成功するために、目的の状態にする必要があるノードの最小数。</span><span class="sxs-lookup"><span data-stu-id="9f0af-114">The minimum number of nodes that must be in the desired state for this resource to succeed.</span></span>|
| <span data-ttu-id="9f0af-115">NodeName</span><span class="sxs-lookup"><span data-stu-id="9f0af-115">NodeName</span></span>| <span data-ttu-id="9f0af-116">依存するリソースのターゲット ノード。</span><span class="sxs-lookup"><span data-stu-id="9f0af-116">The target nodes of the resource to depend on.</span></span>|
| <span data-ttu-id="9f0af-117">ResourceName</span><span class="sxs-lookup"><span data-stu-id="9f0af-117">ResourceName</span></span>| <span data-ttu-id="9f0af-118">依存するリソースの名前。</span><span class="sxs-lookup"><span data-stu-id="9f0af-118">The resource name to depend on.</span></span> <span data-ttu-id="9f0af-119">このリソースが別の構成に属している場合は、"[__リソースの種類__]__リソース名__::[__構成名__]::[__構成名__]" という形式で名前を指定してください。</span><span class="sxs-lookup"><span data-stu-id="9f0af-119">If this resource belongs to a different configuration, format the name as "[__ResourceType__]__ResourceName__::[__ConfigurationName__]::[__ConfigurationName__]"</span></span>|
| <span data-ttu-id="9f0af-120">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="9f0af-120">RetryIntervalSec</span></span>| <span data-ttu-id="9f0af-121">再試行するまでの秒数。</span><span class="sxs-lookup"><span data-stu-id="9f0af-121">The number of seconds before retrying.</span></span> <span data-ttu-id="9f0af-122">最小値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="9f0af-122">Minimum is 1.</span></span>|
| <span data-ttu-id="9f0af-123">RetryCount</span><span class="sxs-lookup"><span data-stu-id="9f0af-123">RetryCount</span></span>| <span data-ttu-id="9f0af-124">再試行の回数の最大数。</span><span class="sxs-lookup"><span data-stu-id="9f0af-124">The maximum number of times to retry.</span></span>|
| <span data-ttu-id="9f0af-125">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="9f0af-125">ThrottleLimit</span></span>| <span data-ttu-id="9f0af-126">同時に接続するコンピューターの数。</span><span class="sxs-lookup"><span data-stu-id="9f0af-126">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="9f0af-127">既定では、new-cimsession の既定値です。</span><span class="sxs-lookup"><span data-stu-id="9f0af-127">Default is new-cimsession default.</span></span>|
| <span data-ttu-id="9f0af-128">DependsOn</span><span class="sxs-lookup"><span data-stu-id="9f0af-128">DependsOn</span></span> | <span data-ttu-id="9f0af-129">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="9f0af-129">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="9f0af-130">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="9f0af-130">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|
| <span data-ttu-id="9f0af-131">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="9f0af-131">PsDscRunAsCredential</span></span> | <span data-ttu-id="9f0af-132">[ユーザーの資格情報を指定した DSC の使用](https://docs.microsoft.com/powershell/dsc/runasuser)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f0af-132">See [Using DSC with User Credentials](https://docs.microsoft.com/powershell/dsc/runasuser)</span></span> |

## <a name="example"></a><span data-ttu-id="9f0af-133">例</span><span class="sxs-lookup"><span data-stu-id="9f0af-133">Example</span></span>

<span data-ttu-id="9f0af-134">このリソースを使用する方法の例は、「[ノードの相互依存関係の指定](../../../configurations/crossNodeDependencies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f0af-134">For an example of how to use this resource, see [Specifying cross-node dependencies](../../../configurations/crossNodeDependencies.md)</span></span>
