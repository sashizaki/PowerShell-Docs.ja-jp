---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC 環境リソース
ms.openlocfilehash: d6d3b4a2086be28fbfa2bf200acef9b13b7b7825
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71954719"
---
# <a name="dsc-environment-resource"></a><span data-ttu-id="6162c-103">DSC 環境リソース</span><span class="sxs-lookup"><span data-stu-id="6162c-103">DSC Environment Resource</span></span>

> <span data-ttu-id="6162c-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="6162c-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="6162c-105">Windows PowerShell Desired State Configuration (DSC) の **Environment** リソースは、システム環境変数を管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="6162c-105">The **Environment** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage system environment variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="6162c-106">構文</span><span class="sxs-lookup"><span data-stu-id="6162c-106">Syntax</span></span>

```Syntax
Environment [string] #ResourceName
{
    Name = [string]
    [ Path = [bool] ]
    [ Value = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="6162c-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6162c-107">Properties</span></span>

|<span data-ttu-id="6162c-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6162c-108">Property</span></span> |<span data-ttu-id="6162c-109">説明</span><span class="sxs-lookup"><span data-stu-id="6162c-109">Description</span></span> |
|---|---|
|<span data-ttu-id="6162c-110">名前</span><span class="sxs-lookup"><span data-stu-id="6162c-110">Name</span></span> |<span data-ttu-id="6162c-111">特定の状態を保証する環境変数の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="6162c-111">Indicates the name of the environment variable for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="6162c-112">パス</span><span class="sxs-lookup"><span data-stu-id="6162c-112">Path</span></span> |<span data-ttu-id="6162c-113">構成されている環境変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="6162c-113">Defines the environment variable that is being configured.</span></span> <span data-ttu-id="6162c-114">変数が **Path** 変数である場合は、このプロパティを `$true` に設定します。それ以外の場合は、`$false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="6162c-114">Set this property to `$true` if the variable is the **Path** variable; otherwise, set it to `$false`.</span></span> <span data-ttu-id="6162c-115">既定値は `$false` です。</span><span class="sxs-lookup"><span data-stu-id="6162c-115">The default is `$false`.</span></span> <span data-ttu-id="6162c-116">構成されている変数が **Path** 変数である場合は、**Value** プロパティによって提供される値が既存の値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="6162c-116">If the variable being configured is the **Path** variable, the value provided through the **Value** property will be appended to the existing value.</span></span> |
|<span data-ttu-id="6162c-117">値</span><span class="sxs-lookup"><span data-stu-id="6162c-117">Value</span></span> |<span data-ttu-id="6162c-118">環境変数に割り当てる値。</span><span class="sxs-lookup"><span data-stu-id="6162c-118">The value to assign to the environment variable.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="6162c-119">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="6162c-119">Common properties</span></span>

|<span data-ttu-id="6162c-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6162c-120">Property</span></span> |<span data-ttu-id="6162c-121">説明</span><span class="sxs-lookup"><span data-stu-id="6162c-121">Description</span></span> |
|---|---|
|<span data-ttu-id="6162c-122">DependsOn</span><span class="sxs-lookup"><span data-stu-id="6162c-122">DependsOn</span></span> |<span data-ttu-id="6162c-123">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="6162c-123">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="6162c-124">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="6162c-124">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="6162c-125">Ensure</span><span class="sxs-lookup"><span data-stu-id="6162c-125">Ensure</span></span> |<span data-ttu-id="6162c-126">変数が存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6162c-126">Indicates if a variable exists.</span></span> <span data-ttu-id="6162c-127">環境変数が存在しない場合に作成する場合、または環境変数が既に存在する場合にその値が **Value** プロパティによって提供される値と一致することを保証するには、このプロパティを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="6162c-127">Set this property to **Present** to create the environment variable if it does not exist or to ensure that its value matches what is provided through the **Value** property if the variable already exists.</span></span> <span data-ttu-id="6162c-128">環境変数が存在する場合に削除するには、**Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="6162c-128">Set it to **Absent** to delete the variable if it exists.</span></span> |
|<span data-ttu-id="6162c-129">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="6162c-129">PsDscRunAsCredential</span></span> |<span data-ttu-id="6162c-130">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="6162c-130">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="6162c-131">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="6162c-131">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="6162c-132">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6162c-132">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="6162c-133">例</span><span class="sxs-lookup"><span data-stu-id="6162c-133">Example</span></span>

<span data-ttu-id="6162c-134">次の例では、TestEnvironmentVariable が存在し、その値が _TestValue_ であることを保証します。</span><span class="sxs-lookup"><span data-stu-id="6162c-134">The following example ensures that TestEnvironmentVariable is present and it has the value _TestValue_.</span></span> <span data-ttu-id="6162c-135">この環境変数が存在しない場合は、作成されます。</span><span class="sxs-lookup"><span data-stu-id="6162c-135">If it is not present, it creates it.</span></span>

```powershell
Environment EnvironmentExample
{
    Ensure = "Present"  # You can also set Ensure to "Absent"
    Name = "TestEnvironmentVariable"
    Value = "TestValue"
}
```