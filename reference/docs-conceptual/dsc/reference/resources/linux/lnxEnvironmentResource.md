---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: Linux 用 DSC の nxEnvironment リソース
ms.openlocfilehash: 64de54fbde15f9d4d7fac425af27b6ef11347dce
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560897"
---
# <a name="dsc-for-linux-nxenvironment-resource"></a><span data-ttu-id="e6da0-103">Linux 用 DSC の nxEnvironment リソース</span><span class="sxs-lookup"><span data-stu-id="e6da0-103">DSC for Linux nxEnvironment Resource</span></span>

<span data-ttu-id="e6da0-104">PowerShell Desired State Configuration (DSC) の **nxEnvironment** リソースは、Linux ノード上でシステム環境変数を管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="e6da0-104">The **nxEnvironment** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage system environment variables on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6da0-105">構文</span><span class="sxs-lookup"><span data-stu-id="e6da0-105">Syntax</span></span>

```Syntax
nxEnvironment <string> #ResourceName
{
    Name = <string>
    [ Value = <string>
    [ Path = <bool> }
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a><span data-ttu-id="e6da0-106">Properties</span><span class="sxs-lookup"><span data-stu-id="e6da0-106">Properties</span></span>

|<span data-ttu-id="e6da0-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e6da0-107">Property</span></span> |<span data-ttu-id="e6da0-108">説明</span><span class="sxs-lookup"><span data-stu-id="e6da0-108">Description</span></span> |
|---|---|
|<span data-ttu-id="e6da0-109">名前</span><span class="sxs-lookup"><span data-stu-id="e6da0-109">Name</span></span> |<span data-ttu-id="e6da0-110">特定の状態を保証する環境変数の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="e6da0-110">Indicates the name of the environment variable for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="e6da0-111">値</span><span class="sxs-lookup"><span data-stu-id="e6da0-111">Value</span></span> |<span data-ttu-id="e6da0-112">環境変数に割り当てる値。</span><span class="sxs-lookup"><span data-stu-id="e6da0-112">The value to assign to the environment variable.</span></span> |
|<span data-ttu-id="e6da0-113">Path</span><span class="sxs-lookup"><span data-stu-id="e6da0-113">Path</span></span> |<span data-ttu-id="e6da0-114">構成されている環境変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="e6da0-114">Defines the environment variable that is being configured.</span></span> <span data-ttu-id="e6da0-115">変数が `$true`Path**変数である場合は、このプロパティを** に設定します。それ以外の場合は、`$false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="e6da0-115">Set this property to `$true` if the variable is the **Path** variable; otherwise, set it to `$false`.</span></span> <span data-ttu-id="e6da0-116">既定では、 `$false`です。</span><span class="sxs-lookup"><span data-stu-id="e6da0-116">The default is `$false`.</span></span> <span data-ttu-id="e6da0-117">構成されている変数が **Path** 変数である場合は、**Value** プロパティによって提供される値が既存の値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="e6da0-117">If the variable being configured is the **Path** variable, the value provided through the **Value** property will be appended to the existing value.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="e6da0-118">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="e6da0-118">Common properties</span></span>

|<span data-ttu-id="e6da0-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e6da0-119">Property</span></span> |<span data-ttu-id="e6da0-120">説明</span><span class="sxs-lookup"><span data-stu-id="e6da0-120">Description</span></span> |
|---|---|
|<span data-ttu-id="e6da0-121">DependsOn</span><span class="sxs-lookup"><span data-stu-id="e6da0-121">DependsOn</span></span> |<span data-ttu-id="e6da0-122">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="e6da0-122">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="e6da0-123">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="e6da0-123">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="e6da0-124">Ensure</span><span class="sxs-lookup"><span data-stu-id="e6da0-124">Ensure</span></span> |<span data-ttu-id="e6da0-125">変数が存在するかどうかをチェックするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e6da0-125">Determines whether to check if the variable exists.</span></span> <span data-ttu-id="e6da0-126">変数の存在を保証するには、このプロパティを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e6da0-126">Set this property to **Present** to ensure the variable exists.</span></span> <span data-ttu-id="e6da0-127">変数が存在しないことを保証するには、**Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e6da0-127">Set it to **Absent** to ensure the variable does not exist.</span></span> <span data-ttu-id="e6da0-128">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="e6da0-128">The default value is **Present**.</span></span> |

## <a name="additional-information"></a><span data-ttu-id="e6da0-129">追加情報</span><span class="sxs-lookup"><span data-stu-id="e6da0-129">Additional Information</span></span>

- <span data-ttu-id="e6da0-130">**Path** がないか、または `$false` に設定されている場合、環境変数は、`/etc/environment` で管理されます。</span><span class="sxs-lookup"><span data-stu-id="e6da0-130">If **Path** is absent or set to `$false`, environment variables are managed in `/etc/environment`.</span></span>
  <span data-ttu-id="e6da0-131">プログラムまたはスクリプトに、`/etc/environment` ファイルを取得して、管理対象の環境変数にアクセスする構成が必要である場合があります。</span><span class="sxs-lookup"><span data-stu-id="e6da0-131">Your programs or scripts may require configuration to source the `/etc/environment` file to access the managed environment variables.</span></span>
- <span data-ttu-id="e6da0-132">**Path** が `$true` に設定されている場合、環境変数はファイル `/etc/profile.d/DSCenvironment.sh` で管理されます。</span><span class="sxs-lookup"><span data-stu-id="e6da0-132">If **Path** is set to `$true`, the environment variable is managed in the file `/etc/profile.d/DSCenvironment.sh`.</span></span> <span data-ttu-id="e6da0-133">このファイルが存在しない場合は作成されます。</span><span class="sxs-lookup"><span data-stu-id="e6da0-133">This file will be created if it does not exist.</span></span> <span data-ttu-id="e6da0-134">**Ensure**が **Absent** に設定され、**Path** が `$true` に設定されている場合、既存の環境変数は `/etc/profile.d/DSCenvironment.sh` からのみ削除され、他のファイルからは削除されません。</span><span class="sxs-lookup"><span data-stu-id="e6da0-134">If **Ensure** is set to **Absent** and **Path** is set to `$true`, an existing environment variable will only be removed from `/etc/profile.d/DSCenvironment.sh` and not from other files.</span></span>

## <a name="example"></a><span data-ttu-id="e6da0-135">例</span><span class="sxs-lookup"><span data-stu-id="e6da0-135">Example</span></span>

<span data-ttu-id="e6da0-136">次の例は、**nxEnvironment** リソースを使用して、**TestEnvironmentVariable** が存在し、値 "Test-Value" が指定されることを保証する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e6da0-136">The following example shows how to use the **nxEnvironment** resource to ensure that **TestEnvironmentVariable** is present and has the value "Test-Value".</span></span> <span data-ttu-id="e6da0-137">**TestEnvironmentVariable** が存在しない場合は、作成されます。</span><span class="sxs-lookup"><span data-stu-id="e6da0-137">If **TestEnvironmentVariable** is not present, it will be created.</span></span>

```powershell
Import-DSCResource -Module nx

nxEnvironment EnvironmentExample
{
    Ensure = "Present"
    Name = "TestEnvironmentVariable"
    Value = "TestValue"
}
```
