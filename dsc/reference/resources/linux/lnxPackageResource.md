---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: Linux 用 DSC の nxPackage リソース
ms.openlocfilehash: 64bb89a95bd6cbaea4e74b8a9979de52428fef3f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62077876"
---
# <a name="dsc-for-linux-nxpackage-resource"></a><span data-ttu-id="a4c0a-103">Linux 用 DSC の nxPackage リソース</span><span class="sxs-lookup"><span data-stu-id="a4c0a-103">DSC for Linux nxPackage Resource</span></span>

<span data-ttu-id="a4c0a-104">PowerShell Desired State Configuration (DSC) の **nxPackage** リソースは、Linux ノード上でパッケージを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="a4c0a-104">The **nxPackage** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage packages on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="a4c0a-105">構文</span><span class="sxs-lookup"><span data-stu-id="a4c0a-105">Syntax</span></span>

```
nxPackage <string> #ResourceName
{
    Name = <string>
    [ Ensure = <string> { Absent | Present }  ]
    [ PackageManager = <string> { Yum | Apt | Zypper } ]
    [ PackageGroup = <bool>]
    [ Arguments = <string> ]
    [ ReturnCode = <uint32> ]
    [ LogPath = <string> ]
    [ DependsOn = <string[]> ]

}
```

## <a name="properties"></a><span data-ttu-id="a4c0a-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a4c0a-106">Properties</span></span>

|  <span data-ttu-id="a4c0a-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a4c0a-107">Property</span></span> |  <span data-ttu-id="a4c0a-108">説明</span><span class="sxs-lookup"><span data-stu-id="a4c0a-108">Description</span></span> |
|---|---|
| <span data-ttu-id="a4c0a-109">名前</span><span class="sxs-lookup"><span data-stu-id="a4c0a-109">Name</span></span>| <span data-ttu-id="a4c0a-110">特定の状態を保証するパッケージの名前。</span><span class="sxs-lookup"><span data-stu-id="a4c0a-110">The name of the package for which you want to ensure a specific state.</span></span>|
| <span data-ttu-id="a4c0a-111">Ensure</span><span class="sxs-lookup"><span data-stu-id="a4c0a-111">Ensure</span></span>| <span data-ttu-id="a4c0a-112">パッケージが存在するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="a4c0a-112">Determines whether to check if the package exists.</span></span> <span data-ttu-id="a4c0a-113">パッケージが存在することを保証するには、このプロパティを "Present" に設定します。</span><span class="sxs-lookup"><span data-stu-id="a4c0a-113">Set this property to "Present" to ensure the package exists.</span></span> <span data-ttu-id="a4c0a-114">パッケージが存在しないことを保証するには、"Absent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="a4c0a-114">Set it to "Absent" to ensure the package does not exist.</span></span> <span data-ttu-id="a4c0a-115">既定値は "Present" です。</span><span class="sxs-lookup"><span data-stu-id="a4c0a-115">The default value is "Present".</span></span>|
| <span data-ttu-id="a4c0a-116">PackageManager</span><span class="sxs-lookup"><span data-stu-id="a4c0a-116">PackageManager</span></span>| <span data-ttu-id="a4c0a-117">サポートされている値は、"yum"、"apt"、および "zypper" です。</span><span class="sxs-lookup"><span data-stu-id="a4c0a-117">Supported values are "yum", "apt", and "zypper".</span></span> <span data-ttu-id="a4c0a-118">パッケージのインストール時に使用するパッケージ マネージャーを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4c0a-118">Specifies the package manager to use when installing packages.</span></span> <span data-ttu-id="a4c0a-119">**FilePath** を指定した場合、その指定したパスを使用してパッケージがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a4c0a-119">If **FilePath** is specified, the provided path will be used to install the package.</span></span> <span data-ttu-id="a4c0a-120">それ以外の場合、パッケージ マネージャーを使用して、事前に構成されているリポジトリからパッケージがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a4c0a-120">Otherwise, a Package Manager will be used to install the package from a pre-configured repository.</span></span> <span data-ttu-id="a4c0a-121">**PackageManager** も **FilePath** も指定しない場合は、システムの既定のパッケージ マネージャーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a4c0a-121">If neither **PackageManager** nor **FilePath** are provided, the default package manager for the system will be used.</span></span>|
| <span data-ttu-id="a4c0a-122">ファイル パス</span><span class="sxs-lookup"><span data-stu-id="a4c0a-122">FilePath</span></span>| <span data-ttu-id="a4c0a-123">パッケージが存在するファイル パス</span><span class="sxs-lookup"><span data-stu-id="a4c0a-123">The file path where the package resides</span></span>|
| <span data-ttu-id="a4c0a-124">PackageGroup</span><span class="sxs-lookup"><span data-stu-id="a4c0a-124">PackageGroup</span></span>| <span data-ttu-id="a4c0a-125">**$true** の場合、**Name** は **PackageManager** で使用されるパッケージ グループの名前であるものとみなされます。</span><span class="sxs-lookup"><span data-stu-id="a4c0a-125">If **$true**, the **Name** is expected to be the name of a package group for use with a **PackageManager**.</span></span> <span data-ttu-id="a4c0a-126">**PacakgeGroup** は、**FilePath** を指定したときには使用できません。</span><span class="sxs-lookup"><span data-stu-id="a4c0a-126">**PacakgeGroup** is not valid when providing a **FilePath**.</span></span>|
| <span data-ttu-id="a4c0a-127">引数</span><span class="sxs-lookup"><span data-stu-id="a4c0a-127">Arguments</span></span>| <span data-ttu-id="a4c0a-128">指定されたとおりにパッケージに渡される引数の文字列。</span><span class="sxs-lookup"><span data-stu-id="a4c0a-128">A string of arguments that will be passed to the package exactly as provided.</span></span>|
| <span data-ttu-id="a4c0a-129">ReturnCode</span><span class="sxs-lookup"><span data-stu-id="a4c0a-129">ReturnCode</span></span>| <span data-ttu-id="a4c0a-130">想定されるリターン コード。</span><span class="sxs-lookup"><span data-stu-id="a4c0a-130">The expected return code.</span></span> <span data-ttu-id="a4c0a-131">実際のリターン コードがここで指定される想定される値と一致しない場合、構成はエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="a4c0a-131">If the actual return code does not match the expected value provided here, the configuration will return an error.</span></span>|
| <span data-ttu-id="a4c0a-132">DependsOn</span><span class="sxs-lookup"><span data-stu-id="a4c0a-132">DependsOn</span></span> | <span data-ttu-id="a4c0a-133">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="a4c0a-133">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="a4c0a-134">たとえば、最初に実行するリソース構成スクリプト ブロックの **ID** が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="a4c0a-134">For example, if the **ID** of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|

## <a name="example"></a><span data-ttu-id="a4c0a-135">例</span><span class="sxs-lookup"><span data-stu-id="a4c0a-135">Example</span></span>

<span data-ttu-id="a4c0a-136">次の例では、"Yum" パッケージ マネージャーを使用して、Linux コンピューターに "httpd" という名前のパッケージがインストールされるようにしています。</span><span class="sxs-lookup"><span data-stu-id="a4c0a-136">The following example ensures that the package named "httpd" is installed on a Linux computer, using the “Yum” package manager.</span></span>

```
Import-DSCResource -Module nx

Node $node {
nxPackage httpd
{
    Name = "httpd"
    Ensure = "Present"
    PackageManager = "Yum"
}
}
```