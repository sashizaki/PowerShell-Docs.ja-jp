---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Package リソース
ms.openlocfilehash: 9285df71a303c9a53dd50d450272575a64e962e7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62077196"
---
# <a name="dsc-package-resource"></a><span data-ttu-id="0fab4-103">DSC Package リソース</span><span class="sxs-lookup"><span data-stu-id="0fab4-103">DSC Package Resource</span></span>

<span data-ttu-id="0fab4-104">_適用先:Windows PowerShell 4.0、Windows PowerShell 5.0_</span><span class="sxs-lookup"><span data-stu-id="0fab4-104">_Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0_</span></span>

<span data-ttu-id="0fab4-105">Windows PowerShell Desired State Configuration (DSC) の **Package** リソースは、Windows インストーラーや setup.exe パッケージなど、ターゲット ノードでパッケージをインストールまたはアンインストールするメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="0fab4-105">The **Package** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall packages, such as Windows Installer and setup.exe packages, on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="0fab4-106">構文</span><span class="sxs-lookup"><span data-stu-id="0fab4-106">Syntax</span></span>

```
Package [string] #ResourceName
{
    Name = [string]
    Path = [string]
    ProductId = [string]
    [ Arguments = [string] ]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ ReturnCode = [UInt32[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="0fab4-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0fab4-107">Properties</span></span>

| <span data-ttu-id="0fab4-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0fab4-108">Property</span></span> | <span data-ttu-id="0fab4-109">説明</span><span class="sxs-lookup"><span data-stu-id="0fab4-109">Description</span></span> |
| --- | --- |
| <span data-ttu-id="0fab4-110">名前</span><span class="sxs-lookup"><span data-stu-id="0fab4-110">Name</span></span>| <span data-ttu-id="0fab4-111">特定の状態を保証するパッケージの名前を示します。</span><span class="sxs-lookup"><span data-stu-id="0fab4-111">Indicates the name of the package for which you want to ensure a specific state.</span></span>|
| <span data-ttu-id="0fab4-112">パス</span><span class="sxs-lookup"><span data-stu-id="0fab4-112">Path</span></span>| <span data-ttu-id="0fab4-113">パッケージが存在するパスを示します。</span><span class="sxs-lookup"><span data-stu-id="0fab4-113">Indicates the path where the package resides.</span></span>|
| <span data-ttu-id="0fab4-114">ProductId</span><span class="sxs-lookup"><span data-stu-id="0fab4-114">ProductId</span></span>| <span data-ttu-id="0fab4-115">パッケージを一意に識別する製品 ID を示します。</span><span class="sxs-lookup"><span data-stu-id="0fab4-115">Indicates the product ID that uniquely identifies the package.</span></span>|
| <span data-ttu-id="0fab4-116">引数</span><span class="sxs-lookup"><span data-stu-id="0fab4-116">Arguments</span></span>| <span data-ttu-id="0fab4-117">指定されたとおりにパッケージに渡される引数の文字列を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="0fab4-117">Lists a string of arguments that will be passed to the package exactly as provided.</span></span>|
| <span data-ttu-id="0fab4-118">Credential</span><span class="sxs-lookup"><span data-stu-id="0fab4-118">Credential</span></span>| <span data-ttu-id="0fab4-119">リモート ソースのパッケージへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0fab4-119">Provides access to the package on a remote source.</span></span> <span data-ttu-id="0fab4-120">このプロパティは、パッケージのインストールには使用されません。</span><span class="sxs-lookup"><span data-stu-id="0fab4-120">This property is not used to install the package.</span></span> <span data-ttu-id="0fab4-121">パッケージは常に、ローカル システムにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="0fab4-121">The package is always installed on the local system.</span></span>|
| <span data-ttu-id="0fab4-122">Ensure</span><span class="sxs-lookup"><span data-stu-id="0fab4-122">Ensure</span></span>| <span data-ttu-id="0fab4-123">パッケージがインストールされるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0fab4-123">Indicates if the package is installed.</span></span> <span data-ttu-id="0fab4-124">このプロパティを "Absent" に設定すると、パッケージはインストールされません (またはパッケージがインストールされている場合はアンインストールされます)。</span><span class="sxs-lookup"><span data-stu-id="0fab4-124">Set this property to "Absent" to ensure the package is not installed (or uninstall the package if it is installed).</span></span> <span data-ttu-id="0fab4-125">パッケージがインストールされるようにするには、"Present" に設定します (既定値)。</span><span class="sxs-lookup"><span data-stu-id="0fab4-125">Set it to "Present" (the default value) to ensure the package is installed.</span></span>|
| <span data-ttu-id="0fab4-126">LogPath</span><span class="sxs-lookup"><span data-stu-id="0fab4-126">LogPath</span></span>| <span data-ttu-id="0fab4-127">プロバイダーがパッケージをインストールまたはアンインストールするためのログ ファイルを保存する場所の完全パスを示します。</span><span class="sxs-lookup"><span data-stu-id="0fab4-127">Indicates the full path where you want the provider to save a log file to install or uninstall the package.</span></span>|
| <span data-ttu-id="0fab4-128">DependsOn</span><span class="sxs-lookup"><span data-stu-id="0fab4-128">DependsOn</span></span> | <span data-ttu-id="0fab4-129">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="0fab4-129">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="0fab4-130">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="0fab4-130">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|
| <span data-ttu-id="0fab4-131">ReturnCode</span><span class="sxs-lookup"><span data-stu-id="0fab4-131">ReturnCode</span></span>| <span data-ttu-id="0fab4-132">想定されるリターン コードを示します。</span><span class="sxs-lookup"><span data-stu-id="0fab4-132">Indicates the expected return code.</span></span> <span data-ttu-id="0fab4-133">実際のリターン コードがここで指定される想定される値と一致しない場合、構成はエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="0fab4-133">If the actual return code does not match the expected value provided here, the configuration will return an error.</span></span>|

## <a name="example"></a><span data-ttu-id="0fab4-134">例</span><span class="sxs-lookup"><span data-stu-id="0fab4-134">Example</span></span>

<span data-ttu-id="0fab4-135">この例では、指定されたパスに配置され、指定された製品 ID が割り当てられている .msi インストーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="0fab4-135">This example runs the .msi installer that is located at the specified path and has the specified product ID.</span></span>

```powershell
Configuration PackageTest
{
    Package PackageExample
    {
        Ensure      = "Present"  # You can also set Ensure to "Absent"
        Path        = "$Env:SystemDrive\TestFolder\TestProject.msi"
        Name        = "TestPackage"
        ProductId   = "ACDDCDAF-80C6-41E6-A1B9-8ABD8A05027E"
    }
}
```