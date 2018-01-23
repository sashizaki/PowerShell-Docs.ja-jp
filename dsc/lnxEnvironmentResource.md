---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "Linux 用 DSC の nxEnvironment リソース"
ms.openlocfilehash: 61e0c7e77e486cea878351f1929d73f1f80710d8
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="dsc-for-linux-nxenvironment-resource"></a><span data-ttu-id="ae837-103">Linux 用 DSC の nxEnvironment リソース</span><span class="sxs-lookup"><span data-stu-id="ae837-103">DSC for Linux nxEnvironment Resource</span></span>

<span data-ttu-id="ae837-104">PowerShell Desired State Configuration (DSC) の **nxEnvironment** リソースは、Linux ノード上でシステム環境変数を管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="ae837-104">The **nxEnvironment** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to to manage system environment variables on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="ae837-105">構文</span><span class="sxs-lookup"><span data-stu-id="ae837-105">Syntax</span></span>

```
nxEnvironment <string> #ResourceName
{
    Name = <string>
    [ Value = <string>
    [ Ensure = <string> { Absent | Present }  ]
    [ Path = <bool> }
    [ DependsOn = <string[]> ]

}
```

## <a name="properties"></a><span data-ttu-id="ae837-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ae837-106">Properties</span></span>

|  <span data-ttu-id="ae837-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ae837-107">Property</span></span> |  <span data-ttu-id="ae837-108">説明</span><span class="sxs-lookup"><span data-stu-id="ae837-108">Description</span></span> | 
|---|---|
| <span data-ttu-id="ae837-109">名前</span><span class="sxs-lookup"><span data-stu-id="ae837-109">Name</span></span>| <span data-ttu-id="ae837-110">特定の状態を保証する環境変数の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="ae837-110">Indicates the name of the environment variable for which you want to ensure a specific state.</span></span>| 
| <span data-ttu-id="ae837-111">値</span><span class="sxs-lookup"><span data-stu-id="ae837-111">Value</span></span>| <span data-ttu-id="ae837-112">環境変数に割り当てる値。</span><span class="sxs-lookup"><span data-stu-id="ae837-112">The value to assign to the environment variable.</span></span>| 
| <span data-ttu-id="ae837-113">Ensure</span><span class="sxs-lookup"><span data-stu-id="ae837-113">Ensure</span></span>| <span data-ttu-id="ae837-114">変数が存在するかどうかをチェックするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="ae837-114">Determines whether to check if the variable exists.</span></span> <span data-ttu-id="ae837-115">変数が存在することを保証するには、このプロパティを "Present" に設定します。</span><span class="sxs-lookup"><span data-stu-id="ae837-115">Set this property to "Present" to ensure the variable exists.</span></span> <span data-ttu-id="ae837-116">変数が存在しないことを保証するには、"Absent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="ae837-116">Set it to "Absent" to ensure the variable does not exist.</span></span> <span data-ttu-id="ae837-117">既定値は "Present" です。</span><span class="sxs-lookup"><span data-stu-id="ae837-117">The default value is "Present".</span></span>| 
| <span data-ttu-id="ae837-118">パス</span><span class="sxs-lookup"><span data-stu-id="ae837-118">Path</span></span>| <span data-ttu-id="ae837-119">構成されている環境変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="ae837-119">Defines the environment variable that is being configured.</span></span> <span data-ttu-id="ae837-120">環境変数が **Path** 変数である場合は、このプロパティを **$true** に設定します。それ以外の場合は、**$false** に設定します。</span><span class="sxs-lookup"><span data-stu-id="ae837-120">Set this property to **$true** if the variable is the **Path** variable; otherwise, set it to **$false**.</span></span> <span data-ttu-id="ae837-121">既定値は **$false** です。</span><span class="sxs-lookup"><span data-stu-id="ae837-121">The default is **$false**.</span></span> <span data-ttu-id="ae837-122">構成されている変数が **Path** 変数である場合は、**Value** プロパティによって提供される値が既存の値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="ae837-122">If the variable being configured is the **Path** variable, the value provided through the **Value** property will be appended to the existing value.</span></span>| 
| <span data-ttu-id="ae837-123">DependsOn</span><span class="sxs-lookup"><span data-stu-id="ae837-123">DependsOn</span></span> | <span data-ttu-id="ae837-124">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="ae837-124">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="ae837-125">たとえば、最初に実行するリソース構成スクリプト ブロックの **ID** が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="ae837-125">For example, if the **ID** of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>| 

## <a name="additional-information"></a><span data-ttu-id="ae837-126">追加情報</span><span class="sxs-lookup"><span data-stu-id="ae837-126">Additional Information</span></span>

* <span data-ttu-id="ae837-127">**Path** がないか、または **$false** に設定されている場合、環境変数は、`/etc/environment` で管理されます。</span><span class="sxs-lookup"><span data-stu-id="ae837-127">If **Path** is absent or set to **$false**, environment variables are managed in `/etc/environment`.</span></span> <span data-ttu-id="ae837-128">プログラムまたはスクリプトに、`/etc/environment` ファイルを取得して、管理対象の環境変数にアクセスする構成が必要である場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae837-128">Your programs or scripts may require configuration to source the `/etc/environment` file to access the managed environment variables.</span></span>
* <span data-ttu-id="ae837-129">**Path** が **$true** に設定されている場合、環境変数はファイル `/etc/profile.d/DSCenvironment.sh` で管理されます。</span><span class="sxs-lookup"><span data-stu-id="ae837-129">If **Path** is set to **$true**, the environment variable is managed in the file `/etc/profile.d/DSCenvironment.sh`.</span></span> <span data-ttu-id="ae837-130">このファイルが存在しない場合は作成されます。</span><span class="sxs-lookup"><span data-stu-id="ae837-130">This file will be created if it does not exist.</span></span> <span data-ttu-id="ae837-131">**Ensure**が "Absent" に設定され、**Path** が **$true** に設定されている場合、既存の環境変数は `/etc/profile.d/DSCenvironment.sh` からのみ削除され、他のファイルからは削除されません。</span><span class="sxs-lookup"><span data-stu-id="ae837-131">If **Ensure** is set to "Absent" and **Path** is set to **$true**, an existing environment variable will only be removed from `/etc/profile.d/DSCenvironment.sh` and not from other files.</span></span>

## <a name="example"></a><span data-ttu-id="ae837-132">例</span><span class="sxs-lookup"><span data-stu-id="ae837-132">Example</span></span>

<span data-ttu-id="ae837-133">次の例は、**nxEnvironment** リソースを使用して、**TestEnvironmentVariable** が存在し、値 "Test-Value" が指定されることを保証する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ae837-133">The following example shows how to use the **nxEnvironment** resource to ensure that **TestEnvironmentVariable** is present and has the value "Test-Value".</span></span> <span data-ttu-id="ae837-134">**TestEnvironmentVariable** が存在しない場合は、作成されます。</span><span class="sxs-lookup"><span data-stu-id="ae837-134">If **TestEnvironmentVariable** is not present, it will be created.</span></span>

```
Import-DSCResource -Module nx 


nxEnvironment EnvironmentExample
{
    Ensure = “Present”
    Name = “TestEnvironmentVariable”
    Value = “TestValue”
}
```


