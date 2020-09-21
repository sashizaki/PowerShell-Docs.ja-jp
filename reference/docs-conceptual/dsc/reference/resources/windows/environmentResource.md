---
ms.date: 07/16/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC 環境リソース
ms.openlocfilehash: d8519a66d457767dcbc0e08b01a69a9264997479
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464419"
---
# <a name="dsc-environment-resource"></a><span data-ttu-id="7aa1a-103">DSC 環境リソース</span><span class="sxs-lookup"><span data-stu-id="7aa1a-103">DSC Environment Resource</span></span>

> <span data-ttu-id="7aa1a-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="7aa1a-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="7aa1a-105">Windows PowerShell Desired State Configuration (DSC) の **Environment** リソースは、システム環境変数を管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-105">The **Environment** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage system environment variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="7aa1a-106">構文</span><span class="sxs-lookup"><span data-stu-id="7aa1a-106">Syntax</span></span>

```Syntax
Environment [string] #ResourceName
{
    Name = [string]
    [ Path = [bool] ]
    [ Target = [string] { Process | Machine } ]
    [ Value = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="7aa1a-107">Properties</span><span class="sxs-lookup"><span data-stu-id="7aa1a-107">Properties</span></span>

|<span data-ttu-id="7aa1a-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7aa1a-108">Property</span></span> |<span data-ttu-id="7aa1a-109">説明</span><span class="sxs-lookup"><span data-stu-id="7aa1a-109">Description</span></span> |
|---|---|
|<span data-ttu-id="7aa1a-110">名前</span><span class="sxs-lookup"><span data-stu-id="7aa1a-110">Name</span></span> |<span data-ttu-id="7aa1a-111">特定の状態を保証する環境変数の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-111">Indicates the name of the environment variable for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="7aa1a-112">Path</span><span class="sxs-lookup"><span data-stu-id="7aa1a-112">Path</span></span> |<span data-ttu-id="7aa1a-113">構成されている環境変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-113">Defines the environment variable that is being configured.</span></span> <span data-ttu-id="7aa1a-114">変数が **Path** 変数である場合は、このプロパティを `$true` に設定します。それ以外の場合は、`$false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-114">Set this property to `$true` if the variable is the **Path** variable; otherwise, set it to `$false`.</span></span> <span data-ttu-id="7aa1a-115">既定では、 `$false`です。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-115">The default is `$false`.</span></span> <span data-ttu-id="7aa1a-116">構成されている変数が **Path** 変数である場合は、**Value** プロパティによって提供される値が既存の値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-116">If the variable being configured is the **Path** variable, the value provided through the **Value** property will be appended to the existing value.</span></span> |
|<span data-ttu-id="7aa1a-117">移行先</span><span class="sxs-lookup"><span data-stu-id="7aa1a-117">Target</span></span>| <span data-ttu-id="7aa1a-118">変数を取得する場所 (マシンまたはプロセス) を示します。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-118">Indicates where to retrieve the variable: The machine or the process.</span></span> <span data-ttu-id="7aa1a-119">両方が示されている場合は、マシンからの値のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-119">If both are indicated then only the value from the machine is returned.</span></span> <span data-ttu-id="7aa1a-120">既定では両方であり、これは残りのリソースでの既定でもあります。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-120">The default is both since that is the default for the rest of the resource.</span></span> |
|<span data-ttu-id="7aa1a-121">値</span><span class="sxs-lookup"><span data-stu-id="7aa1a-121">Value</span></span> |<span data-ttu-id="7aa1a-122">環境変数に割り当てる値。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-122">The value to assign to the environment variable.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="7aa1a-123">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="7aa1a-123">Common properties</span></span>

|<span data-ttu-id="7aa1a-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7aa1a-124">Property</span></span> |<span data-ttu-id="7aa1a-125">説明</span><span class="sxs-lookup"><span data-stu-id="7aa1a-125">Description</span></span> |
|---|---|
|<span data-ttu-id="7aa1a-126">DependsOn</span><span class="sxs-lookup"><span data-stu-id="7aa1a-126">DependsOn</span></span> |<span data-ttu-id="7aa1a-127">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-127">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="7aa1a-128">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-128">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="7aa1a-129">Ensure</span><span class="sxs-lookup"><span data-stu-id="7aa1a-129">Ensure</span></span> |<span data-ttu-id="7aa1a-130">変数が存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-130">Indicates if a variable exists.</span></span> <span data-ttu-id="7aa1a-131">環境変数が存在しない場合に作成する場合、または環境変数が既に存在する場合にその値が **Value** プロパティによって提供される値と一致することを保証するには、このプロパティを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-131">Set this property to **Present** to create the environment variable if it does not exist or to ensure that its value matches what is provided through the **Value** property if the variable already exists.</span></span> <span data-ttu-id="7aa1a-132">環境変数が存在する場合に削除するには、**Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-132">Set it to **Absent** to delete the variable if it exists.</span></span> |
|<span data-ttu-id="7aa1a-133">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="7aa1a-133">PsDscRunAsCredential</span></span> |<span data-ttu-id="7aa1a-134">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-134">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="7aa1a-135">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-135">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="7aa1a-136">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-136">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="7aa1a-137">例</span><span class="sxs-lookup"><span data-stu-id="7aa1a-137">Example</span></span>

<span data-ttu-id="7aa1a-138">次の例では、TestEnvironmentVariable が存在し、その値が _TestValue_ であることを保証します。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-138">The following example ensures that TestEnvironmentVariable is present and it has the value _TestValue_.</span></span> <span data-ttu-id="7aa1a-139">この環境変数が存在しない場合は、作成されます。</span><span class="sxs-lookup"><span data-stu-id="7aa1a-139">If it is not present, it creates it.</span></span>

```powershell
Environment EnvironmentExample
{
    Ensure = "Present"  # You can also set Ensure to "Absent"
    Name = "TestEnvironmentVariable"
    Value = "TestValue"
}
```
