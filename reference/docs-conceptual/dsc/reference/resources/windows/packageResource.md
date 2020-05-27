---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Package リソース
ms.openlocfilehash: ff2eae712b4117da9bca915f52e18caed7c4885d
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83559932"
---
# <a name="dsc-package-resource"></a><span data-ttu-id="e757f-103">DSC Package リソース</span><span class="sxs-lookup"><span data-stu-id="e757f-103">DSC Package Resource</span></span>

> <span data-ttu-id="e757f-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="e757f-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="e757f-105">Windows PowerShell Desired State Configuration (DSC) の **Package** リソースは、Windows インストーラーや setup.exe パッケージなど、ターゲット ノードでパッケージをインストールまたはアンインストールするメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="e757f-105">The **Package** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall packages, such as Windows Installer and setup.exe packages, on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="e757f-106">構文</span><span class="sxs-lookup"><span data-stu-id="e757f-106">Syntax</span></span>

```Syntax
Package [string] #ResourceName
{
    Name = [string]
    Path = [string]
    ProductId = [string]
    [ Arguments = [string] ]
    [ Credential = [PSCredential] ]
    [ LogPath = [string] ]
    [ ReturnCode = [UInt32[]] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="e757f-107">Properties</span><span class="sxs-lookup"><span data-stu-id="e757f-107">Properties</span></span>

|<span data-ttu-id="e757f-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e757f-108">Property</span></span> |<span data-ttu-id="e757f-109">説明</span><span class="sxs-lookup"><span data-stu-id="e757f-109">Description</span></span> |
|---|---|
|<span data-ttu-id="e757f-110">名前</span><span class="sxs-lookup"><span data-stu-id="e757f-110">Name</span></span> |<span data-ttu-id="e757f-111">特定の状態を保証するパッケージの名前を示します。</span><span class="sxs-lookup"><span data-stu-id="e757f-111">Indicates the name of the package for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="e757f-112">Path</span><span class="sxs-lookup"><span data-stu-id="e757f-112">Path</span></span> |<span data-ttu-id="e757f-113">パッケージが存在するパスを示します。</span><span class="sxs-lookup"><span data-stu-id="e757f-113">Indicates the path where the package resides.</span></span> |
|<span data-ttu-id="e757f-114">ProductId</span><span class="sxs-lookup"><span data-stu-id="e757f-114">ProductId</span></span> |<span data-ttu-id="e757f-115">パッケージを一意に識別する製品 ID を示します。</span><span class="sxs-lookup"><span data-stu-id="e757f-115">Indicates the product ID that uniquely identifies the package.</span></span> |
|<span data-ttu-id="e757f-116">引数</span><span class="sxs-lookup"><span data-stu-id="e757f-116">Arguments</span></span> |<span data-ttu-id="e757f-117">指定されたとおりにパッケージに渡される引数の文字列を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e757f-117">Lists a string of arguments that will be passed to the package exactly as provided.</span></span> |
|<span data-ttu-id="e757f-118">資格情報</span><span class="sxs-lookup"><span data-stu-id="e757f-118">Credential</span></span> |<span data-ttu-id="e757f-119">リモート ソースのパッケージへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e757f-119">Provides access to the package on a remote source.</span></span> <span data-ttu-id="e757f-120">このプロパティは、パッケージのインストールには使用されません。</span><span class="sxs-lookup"><span data-stu-id="e757f-120">This property is not used to install the package.</span></span> <span data-ttu-id="e757f-121">パッケージは常に、ローカル システムにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e757f-121">The package is always installed on the local system.</span></span> |
|<span data-ttu-id="e757f-122">LogPath</span><span class="sxs-lookup"><span data-stu-id="e757f-122">LogPath</span></span> |<span data-ttu-id="e757f-123">プロバイダーがパッケージをインストールまたはアンインストールするためのログ ファイルを保存する場所の完全パスを示します。</span><span class="sxs-lookup"><span data-stu-id="e757f-123">Indicates the full path where you want the provider to save a log file to install or uninstall the package.</span></span> |
|<span data-ttu-id="e757f-124">ReturnCode</span><span class="sxs-lookup"><span data-stu-id="e757f-124">ReturnCode</span></span> |<span data-ttu-id="e757f-125">想定されるリターン コードを示します。</span><span class="sxs-lookup"><span data-stu-id="e757f-125">Indicates the expected return code.</span></span> <span data-ttu-id="e757f-126">実際のリターン コードがここで指定される想定される値と一致しない場合、構成はエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="e757f-126">If the actual return code does not match the expected value provided here, the configuration will return an error.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="e757f-127">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="e757f-127">Common properties</span></span>

|<span data-ttu-id="e757f-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e757f-128">Property</span></span> |<span data-ttu-id="e757f-129">説明</span><span class="sxs-lookup"><span data-stu-id="e757f-129">Description</span></span> |
|---|---|
|<span data-ttu-id="e757f-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="e757f-130">DependsOn</span></span> |<span data-ttu-id="e757f-131">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="e757f-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="e757f-132">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="e757f-132">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="e757f-133">Ensure</span><span class="sxs-lookup"><span data-stu-id="e757f-133">Ensure</span></span> |<span data-ttu-id="e757f-134">パッケージがインストールされるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e757f-134">Indicates if the package is installed.</span></span> <span data-ttu-id="e757f-135">パッケージが確実にインストールされないようにする (またはパッケージがインストールされている場合はアンインストールされるようにする) には、このプロパティを **Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e757f-135">Set this property to **Absent** to ensure the package is not installed (or uninstall the package if it is installed).</span></span> <span data-ttu-id="e757f-136">パッケージが確実にインストールされるようにするには、これを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e757f-136">Set it to **Present** to ensure the package is installed.</span></span> <span data-ttu-id="e757f-137">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="e757f-137">The default value is **Present**.</span></span> |
|<span data-ttu-id="e757f-138">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="e757f-138">PsDscRunAsCredential</span></span> |<span data-ttu-id="e757f-139">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="e757f-139">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="e757f-140">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="e757f-140">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="e757f-141">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e757f-141">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="e757f-142">例</span><span class="sxs-lookup"><span data-stu-id="e757f-142">Example</span></span>

<span data-ttu-id="e757f-143">この例では、指定されたパスに配置され、指定された製品 ID が割り当てられている .msi インストーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="e757f-143">This example runs the .msi installer that is located at the specified path and has the specified product ID.</span></span>

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
