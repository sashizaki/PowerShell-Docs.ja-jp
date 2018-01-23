---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "DSC 環境リソース"
ms.openlocfilehash: 9c166d719ba3f168c936278acd6fb5fb7658613e
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="dsc-environment-resource"></a><span data-ttu-id="6c660-103">DSC 環境リソース</span><span class="sxs-lookup"><span data-stu-id="6c660-103">DSC Environment Resource</span></span>

> <span data-ttu-id="6c660-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="6c660-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="6c660-105">Windows PowerShell Desired State Configuration (DSC) の __Environment__ リソースは、システム環境変数を管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="6c660-105">The __Environment__ resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage system environment variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="6c660-106">構文</span><span class="sxs-lookup"><span data-stu-id="6c660-106">Syntax</span></span>
``` mof
Environment [string] #ResourceName
{
    Name = [string]
    [ Ensure = [string] { Absent | Present }  ]
    [ Path = [bool] ]
    [ DependsOn = [string[]] ]
    [ Value = [string] ]
}
```

## <a name="properties"></a><span data-ttu-id="6c660-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6c660-107">Properties</span></span>

|  <span data-ttu-id="6c660-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6c660-108">Property</span></span>  |  <span data-ttu-id="6c660-109">説明</span><span class="sxs-lookup"><span data-stu-id="6c660-109">Description</span></span>   | 
|---|---| 
| <span data-ttu-id="6c660-110">名前</span><span class="sxs-lookup"><span data-stu-id="6c660-110">Name</span></span>| <span data-ttu-id="6c660-111">特定の状態を保証する環境変数の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="6c660-111">Indicates the name of the environment variable for which you want to ensure a specific state.</span></span>| 
| <span data-ttu-id="6c660-112">Ensure</span><span class="sxs-lookup"><span data-stu-id="6c660-112">Ensure</span></span>| <span data-ttu-id="6c660-113">変数が存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6c660-113">Indicates if a variable exists.</span></span> <span data-ttu-id="6c660-114">環境変数が存在しない場合に作成する場合、または環境変数が既に存在する場合にその値が __Value__ プロパティによって提供される値と一致することを保証するには、このプロパティを __Present__ に設定します。</span><span class="sxs-lookup"><span data-stu-id="6c660-114">Set this property to __Present__ to create the environment variable if it does not exist or to ensure that its value matches what is provided through the __Value__ property if the variable already exists.</span></span> <span data-ttu-id="6c660-115">環境変数が存在する場合に削除するには、__Absent__ に設定します。</span><span class="sxs-lookup"><span data-stu-id="6c660-115">Set it to __Absent__ to delete the variable if it exists.</span></span>| 
| <span data-ttu-id="6c660-116">パス</span><span class="sxs-lookup"><span data-stu-id="6c660-116">Path</span></span>| <span data-ttu-id="6c660-117">構成されている環境変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="6c660-117">Defines the environment variable that is being configured.</span></span> <span data-ttu-id="6c660-118">環境変数が __Path__ 変数である場合は、このプロパティを __$true__ に設定します。それ以外の場合は、__$false__ に設定します。</span><span class="sxs-lookup"><span data-stu-id="6c660-118">Set this property to __$true__ if the variable is the __Path__ variable; otherwise, set it to __$false__.</span></span> <span data-ttu-id="6c660-119">既定値は __$false__ です。</span><span class="sxs-lookup"><span data-stu-id="6c660-119">The default is __$false__.</span></span> <span data-ttu-id="6c660-120">構成されている変数が __Path__ 変数である場合は、__Value__ プロパティによって提供される値が既存の値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="6c660-120">If the variable being configured is the __Path__ variable, the value provided through the __Value__ property will be appended to the existing value.</span></span>| 
| <span data-ttu-id="6c660-121">DependsOn</span><span class="sxs-lookup"><span data-stu-id="6c660-121">DependsOn</span></span> | <span data-ttu-id="6c660-122">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="6c660-122">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="6c660-123">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="6c660-123">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>| 
| <span data-ttu-id="6c660-124">値</span><span class="sxs-lookup"><span data-stu-id="6c660-124">Value</span></span>| <span data-ttu-id="6c660-125">環境変数に割り当てる値。</span><span class="sxs-lookup"><span data-stu-id="6c660-125">The value to assign to the environment variable.</span></span>| 

## <a name="example"></a><span data-ttu-id="6c660-126">例</span><span class="sxs-lookup"><span data-stu-id="6c660-126">Example</span></span>

<span data-ttu-id="6c660-127">次の例では、__TestEnvironmentVariable__ が存在し、その値が __TestValue__ であることを保証します。</span><span class="sxs-lookup"><span data-stu-id="6c660-127">The following example ensures that __TestEnvironmentVariable__ is present and it has the value __TestValue__.</span></span> <span data-ttu-id="6c660-128">この環境変数が存在しない場合は、作成されます。</span><span class="sxs-lookup"><span data-stu-id="6c660-128">If it is not present, it creates it.</span></span>

```powershell
Environment EnvironmentExample
{
    Ensure = "Present"  # You can also set Ensure to "Absent"
    Name = "TestEnvironmentVariable"
    Value = "TestValue"
}
```

