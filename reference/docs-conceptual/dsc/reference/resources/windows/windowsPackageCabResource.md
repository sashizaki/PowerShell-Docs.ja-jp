---
ms.date: 07/16/2020
ms.topic: reference
title: DSC WindowsPackageCab リソース
description: DSC WindowsPackageCab リソース
ms.openlocfilehash: 3ac10eb2a7da502b8cac23ab8bfee869a4e26fd3
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2020
ms.locfileid: "93143026"
---
# <a name="dsc-windowspackagecab-resource"></a><span data-ttu-id="65135-103">DSC WindowsPackageCab リソース</span><span class="sxs-lookup"><span data-stu-id="65135-103">DSC WindowsPackageCab Resource</span></span>

> <span data-ttu-id="65135-104">適用先:Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="65135-104">Applies To: Windows PowerShell 5.1</span></span>

<span data-ttu-id="65135-105">Windows PowerShell Desired State Configuration (DSC) の **WindowsPackageCab** リソースは、ターゲット ノードで Windows cabinet (.cab) パッケージをインストールまたはアンインストールするメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="65135-105">The **WindowsPackageCab** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall Windows cabinet (.cab) packages on a target node.</span></span>

<span data-ttu-id="65135-106">ターゲット ノードには DISM PowerShell モジュールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65135-106">The target node must have the DISM PowerShell module installed.</span></span> <span data-ttu-id="65135-107">詳細については、「[Use DISM in Windows PowerShell (Windows PowerShell の DISM の使用)](/windows-hardware/manufacture/desktop/use-dism-in-windows-powershell-s14)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65135-107">For information, see [Use DISM in Windows PowerShell](/windows-hardware/manufacture/desktop/use-dism-in-windows-powershell-s14).</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="65135-108">構文</span><span class="sxs-lookup"><span data-stu-id="65135-108">Syntax</span></span>

```Syntax
{
    Name = [string]
    SourcePath = [string]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    Ensure = [string] { Absent | Present }
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="65135-109">Properties</span><span class="sxs-lookup"><span data-stu-id="65135-109">Properties</span></span>

|<span data-ttu-id="65135-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="65135-110">Property</span></span> |<span data-ttu-id="65135-111">説明</span><span class="sxs-lookup"><span data-stu-id="65135-111">Description</span></span> |
|---|---|
|<span data-ttu-id="65135-112">名前</span><span class="sxs-lookup"><span data-stu-id="65135-112">Name</span></span> |<span data-ttu-id="65135-113">特定の状態を保証するパッケージの名前を示します。</span><span class="sxs-lookup"><span data-stu-id="65135-113">Indicates the name of the package for you want to ensure a specific state.</span></span> |
|<span data-ttu-id="65135-114">SourcePath</span><span class="sxs-lookup"><span data-stu-id="65135-114">SourcePath</span></span> |<span data-ttu-id="65135-115">パッケージが存在するパスを示します。</span><span class="sxs-lookup"><span data-stu-id="65135-115">Indicates the path where the package resides.</span></span> |
|<span data-ttu-id="65135-116">LogPath</span><span class="sxs-lookup"><span data-stu-id="65135-116">LogPath</span></span> |<span data-ttu-id="65135-117">プロバイダーがパッケージをインストールまたはアンインストールするためのログ ファイルを保存する場所の完全パスを示します。</span><span class="sxs-lookup"><span data-stu-id="65135-117">Indicates the full path where you want the provider to save a log file to install or uninstall the package.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="65135-118">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="65135-118">Common properties</span></span>

|<span data-ttu-id="65135-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="65135-119">Property</span></span> |<span data-ttu-id="65135-120">説明</span><span class="sxs-lookup"><span data-stu-id="65135-120">Description</span></span> |
|---|---|
|<span data-ttu-id="65135-121">DependsOn</span><span class="sxs-lookup"><span data-stu-id="65135-121">DependsOn</span></span> |<span data-ttu-id="65135-122">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="65135-122">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="65135-123">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="65135-123">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="65135-124">Ensure</span><span class="sxs-lookup"><span data-stu-id="65135-124">Ensure</span></span> |<span data-ttu-id="65135-125">パッケージがインストールされるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="65135-125">Indicates if the package is installed.</span></span> <span data-ttu-id="65135-126">パッケージが確実にインストールされないようにする (またはパッケージがインストールされている場合はアンインストールされるようにする) には、このプロパティを **Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="65135-126">Set this property to **Absent** to ensure the package is not installed (or uninstall the package if it is installed).</span></span> <span data-ttu-id="65135-127">パッケージが確実にインストールされるようにするには、これを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="65135-127">Set it to **Present** to ensure the package is installed.</span></span> <span data-ttu-id="65135-128">**WindowsPackageCab** リソースでは、 **Ensure** は必須のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="65135-128">**Ensure** is a required property on the **WindowsPackageCab** resource.</span></span> |
|<span data-ttu-id="65135-129">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="65135-129">PsDscRunAsCredential</span></span> |<span data-ttu-id="65135-130">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="65135-130">Sets the credential for running the entire resource as.</span></span> |

## <a name="example"></a><span data-ttu-id="65135-131">例</span><span class="sxs-lookup"><span data-stu-id="65135-131">Example</span></span>

<span data-ttu-id="65135-132">次の例の構成は入力パラメーターを必要とし、`$Name` パラメーターで指定された .cab ファイルが確実にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="65135-132">The following example configuration takes input parameters, and ensures that the .cab file specified by the `$Name` parameter is installed.</span></span>

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
