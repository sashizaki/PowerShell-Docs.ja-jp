---
ms.date: 07/17/2020
ms.topic: reference
title: Linux 用 DSC の nxPackage リソース
description: Linux 用 DSC の nxPackage リソース
ms.openlocfilehash: b84c7963297e8a88e729cd67611245b017c27fb7
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648846"
---
# <a name="dsc-for-linux-nxpackage-resource"></a><span data-ttu-id="0c33e-103">Linux 用 DSC の nxPackage リソース</span><span class="sxs-lookup"><span data-stu-id="0c33e-103">DSC for Linux nxPackage Resource</span></span>

<span data-ttu-id="0c33e-104">PowerShell Desired State Configuration (DSC) の **nxPackage** リソースは、Linux ノード上でパッケージを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="0c33e-104">The **nxPackage** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage packages on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="0c33e-105">構文</span><span class="sxs-lookup"><span data-stu-id="0c33e-105">Syntax</span></span>

```Syntax
nxPackage <string> #ResourceName
{
    Name = <string>
    [ PackageManager = <string> { Yum | Apt | Zypper } ]
    [ PackageGroup = <bool>]
    [ Arguments = <string> ]
    [ ReturnCode = <uint32> ]
    [ FilePath = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a><span data-ttu-id="0c33e-106">Properties</span><span class="sxs-lookup"><span data-stu-id="0c33e-106">Properties</span></span>

|<span data-ttu-id="0c33e-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0c33e-107">Property</span></span> |<span data-ttu-id="0c33e-108">説明</span><span class="sxs-lookup"><span data-stu-id="0c33e-108">Description</span></span> |
|---|---|
|<span data-ttu-id="0c33e-109">名前</span><span class="sxs-lookup"><span data-stu-id="0c33e-109">Name</span></span> |<span data-ttu-id="0c33e-110">特定の状態を保証するパッケージの名前。</span><span class="sxs-lookup"><span data-stu-id="0c33e-110">The name of the package for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="0c33e-111">PackageManager</span><span class="sxs-lookup"><span data-stu-id="0c33e-111">PackageManager</span></span> |<span data-ttu-id="0c33e-112">サポートされている値は、 **yum** 、 **apt** 、 **zypper** です。</span><span class="sxs-lookup"><span data-stu-id="0c33e-112">Supported values are **yum** , **apt** , and **zypper** .</span></span> <span data-ttu-id="0c33e-113">パッケージのインストール時に使用するパッケージ マネージャーを指定します。</span><span class="sxs-lookup"><span data-stu-id="0c33e-113">Specifies the package manager to use when installing packages.</span></span> <span data-ttu-id="0c33e-114">**FilePath** を指定した場合、その指定したパスを使用してパッケージがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="0c33e-114">If **FilePath** is specified, the provided path will be used to install the package.</span></span> <span data-ttu-id="0c33e-115">それ以外の場合、パッケージ マネージャーを使用して、事前に構成されているリポジトリからパッケージがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="0c33e-115">Otherwise, a Package Manager will be used to install the package from a pre-configured repository.</span></span> <span data-ttu-id="0c33e-116">**PackageManager** も **FilePath** も指定しない場合は、システムの既定のパッケージ マネージャーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="0c33e-116">If neither **PackageManager** nor **FilePath** are provided, the default package manager for the system will be used.</span></span> |
|<span data-ttu-id="0c33e-117">PackageGroup</span><span class="sxs-lookup"><span data-stu-id="0c33e-117">PackageGroup</span></span> |<span data-ttu-id="0c33e-118">`$true` の場合、 **Name** は **PackageManager** で使用されるパッケージ グループの名前であるものとみなされます。</span><span class="sxs-lookup"><span data-stu-id="0c33e-118">If `$true`, the **Name** is expected to be the name of a package group for use with a **PackageManager** .</span></span> <span data-ttu-id="0c33e-119">**PackageGroup** は、 **FilePath** を指定したときには使用できません。</span><span class="sxs-lookup"><span data-stu-id="0c33e-119">**PackageGroup** is not valid when providing a **FilePath** .</span></span> |
|<span data-ttu-id="0c33e-120">引数</span><span class="sxs-lookup"><span data-stu-id="0c33e-120">Arguments</span></span> |<span data-ttu-id="0c33e-121">指定されたとおりにパッケージに渡される引数の文字列。</span><span class="sxs-lookup"><span data-stu-id="0c33e-121">A string of arguments that will be passed to the package exactly as provided.</span></span> |
|<span data-ttu-id="0c33e-122">ReturnCode</span><span class="sxs-lookup"><span data-stu-id="0c33e-122">ReturnCode</span></span> |<span data-ttu-id="0c33e-123">想定されるリターン コード。</span><span class="sxs-lookup"><span data-stu-id="0c33e-123">The expected return code.</span></span> <span data-ttu-id="0c33e-124">実際のリターン コードがここで指定される想定される値と一致しない場合、構成はエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="0c33e-124">If the actual return code does not match the expected value provided here, the configuration will return an error.</span></span> |
|<span data-ttu-id="0c33e-125">FilePath</span><span class="sxs-lookup"><span data-stu-id="0c33e-125">FilePath</span></span> |<span data-ttu-id="0c33e-126">パッケージが存在するファイル パス。</span><span class="sxs-lookup"><span data-stu-id="0c33e-126">The file path where the package resides.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="0c33e-127">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="0c33e-127">Common properties</span></span>

|<span data-ttu-id="0c33e-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0c33e-128">Property</span></span> |<span data-ttu-id="0c33e-129">説明</span><span class="sxs-lookup"><span data-stu-id="0c33e-129">Description</span></span> |
|---|---|
|<span data-ttu-id="0c33e-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="0c33e-130">DependsOn</span></span> |<span data-ttu-id="0c33e-131">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="0c33e-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="0c33e-132">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="0c33e-132">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="0c33e-133">Ensure</span><span class="sxs-lookup"><span data-stu-id="0c33e-133">Ensure</span></span> |<span data-ttu-id="0c33e-134">パッケージが存在するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="0c33e-134">Determines whether to check if the package exists.</span></span> <span data-ttu-id="0c33e-135">パッケージの存在を保証するには、このプロパティを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="0c33e-135">Set this property to **Present** to ensure the package exists.</span></span> <span data-ttu-id="0c33e-136">パッケージが存在しないことを保証するには、 **Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="0c33e-136">Set it to **Absent** to ensure the package does not exist.</span></span> <span data-ttu-id="0c33e-137">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="0c33e-137">The default value is **Present** .</span></span> |

## <a name="example"></a><span data-ttu-id="0c33e-138">例</span><span class="sxs-lookup"><span data-stu-id="0c33e-138">Example</span></span>

<span data-ttu-id="0c33e-139">次の例では、"Yum" パッケージ マネージャーを使用して、Linux コンピューターに "httpd" という名前のパッケージが確実にインストールされるようにしています。</span><span class="sxs-lookup"><span data-stu-id="0c33e-139">The following example ensures that the package named "httpd" is installed on a Linux computer, using the "Yum" package manager.</span></span>

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxPackage httpd
    {
        Name = "httpd"
        Ensure = "Present"
        PackageManager = "Yum"
    }
}
```
