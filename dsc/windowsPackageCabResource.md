---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "DSC WindowsPackageCab リソース"
ms.openlocfilehash: 1d7c8d9bf45d2eda8734daa8877315d219662c75
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="dsc-windowspackagecab-resource"></a><span data-ttu-id="8150d-103">DSC WindowsPackageCab リソース</span><span class="sxs-lookup"><span data-stu-id="8150d-103">DSC WindowsPackageCab Resource</span></span>

> <span data-ttu-id="8150d-104">適用先: Windows PowerShell 5.1 以降</span><span class="sxs-lookup"><span data-stu-id="8150d-104">Applies To: Windows PowerShell 5.1 and later</span></span>

<span data-ttu-id="8150d-105">Windows PowerShell Desired State Configuration (DSC) の **WindowsPackageCab** リソースは、ターゲット ノードで Windows cabinet (.cab) パッケージをインストールまたはアンインストールするメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="8150d-105">The **WindowsPackageCab** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall Windows cabinet (.cab) packages on a target node.</span></span>

<span data-ttu-id="8150d-106">ターゲット ノードには DISM PowerShell モジュールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8150d-106">The target node must have the DISM PowerShell module installed.</span></span> <span data-ttu-id="8150d-107">詳細については、「[Use DISM in Windows PowerShell (Windows PowerShell の DISM の使用)](https://msdn.microsoft.com/en-us/windows/hardware/commercialize/manufacture/desktop/use-dism-in-windows-powershell-s14)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8150d-107">For information, see [Use DISM in Windows PowerShell](https://msdn.microsoft.com/en-us/windows/hardware/commercialize/manufacture/desktop/use-dism-in-windows-powershell-s14).</span></span> 


## <a name="syntax"></a><span data-ttu-id="8150d-108">構文</span><span class="sxs-lookup"><span data-stu-id="8150d-108">Syntax</span></span>

```
{
    Name = [string]
    Ensure = [string] { Absent | Present }
    SourcePath = [string]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="8150d-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8150d-109">Properties</span></span>

|  <span data-ttu-id="8150d-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8150d-110">Property</span></span>  |  <span data-ttu-id="8150d-111">説明</span><span class="sxs-lookup"><span data-stu-id="8150d-111">Description</span></span>   | 
|---|---| 
| <span data-ttu-id="8150d-112">名前</span><span class="sxs-lookup"><span data-stu-id="8150d-112">Name</span></span>| <span data-ttu-id="8150d-113">特定の状態を保証するパッケージの名前を示します。</span><span class="sxs-lookup"><span data-stu-id="8150d-113">Indicates the name of the package for you want to ensure a specific state.</span></span>| 
| <span data-ttu-id="8150d-114">Ensure</span><span class="sxs-lookup"><span data-stu-id="8150d-114">Ensure</span></span>| <span data-ttu-id="8150d-115">パッケージがインストールされるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="8150d-115">Indicates if the package is installed.</span></span> <span data-ttu-id="8150d-116">このプロパティを "Absent" に設定すると、パッケージはインストールされません (またはパッケージがインストールされている場合はアンインストールされます)。</span><span class="sxs-lookup"><span data-stu-id="8150d-116">Set this property to "Absent" to ensure the package is not installed (or uninstall the package if it is installed).</span></span> <span data-ttu-id="8150d-117">パッケージがインストールされるようにするには、"Present" に設定します (既定値)。</span><span class="sxs-lookup"><span data-stu-id="8150d-117">Set it to "Present" (the default value) to ensure the package is installed.</span></span>|
| <span data-ttu-id="8150d-118">パス</span><span class="sxs-lookup"><span data-stu-id="8150d-118">Path</span></span>| <span data-ttu-id="8150d-119">パッケージが存在するパスを示します。</span><span class="sxs-lookup"><span data-stu-id="8150d-119">Indicates the path where the package resides.</span></span>| 
| <span data-ttu-id="8150d-120">LogPath</span><span class="sxs-lookup"><span data-stu-id="8150d-120">LogPath</span></span>| <span data-ttu-id="8150d-121">プロバイダーがパッケージをインストールまたはアンインストールするためのログ ファイルを保存する場所の完全パスを示します。</span><span class="sxs-lookup"><span data-stu-id="8150d-121">Indicates the full path where you want the provider to save a log file to install or uninstall the package.</span></span>| 
| <span data-ttu-id="8150d-122">DependsOn</span><span class="sxs-lookup"><span data-stu-id="8150d-122">DependsOn</span></span> | <span data-ttu-id="8150d-123">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="8150d-123">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="8150d-124">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は DependsOn = "[ResourceType]ResourceName" になります。</span><span class="sxs-lookup"><span data-stu-id="8150d-124">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is \`DependsOn = "[ResourceType]ResourceName"\`\`.</span></span>| 

## <a name="example"></a><span data-ttu-id="8150d-125">例</span><span class="sxs-lookup"><span data-stu-id="8150d-125">Example</span></span>

<span data-ttu-id="8150d-126">次の例の構成は入力パラメーターを必要とし、`$Name` パラメーターで指定された .cab ファイルが確実にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8150d-126">The following example configuration takes input parameters, and ensures that the .cab file specified by the `$Name` parameter is installed.</span></span>

```powershell
Configuration Sample_WindowsPackageCab
{
    param
    (
        [Parameter (Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $Name,

        [Parameter (Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $SourcePath,

        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $LogPath
    )

    Import-DscResource -ModuleName 'PSDscResources'

    WindowsPackageCab WindowsPackageCab1
    {
        Name = $Name
        Ensure = 'Present'
        SourcePath = $SourcePath
        LogPath = $LogPath
    }
}
```

