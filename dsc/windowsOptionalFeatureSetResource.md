---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "DSC WindowsOptionalFeatureSet リソース"
ms.openlocfilehash: 3bf6a993d0ec9ce71c1e9222ddaa3bb429accb15
ms.sourcegitcommit: 79e8f03afb8d0b0bb0a167e56464929b27f51990
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2017
---
# <a name="dsc-windowsoptionalfeatureset-resource"></a><span data-ttu-id="44251-103">DSC WindowsOptionalFeatureSet リソース</span><span class="sxs-lookup"><span data-stu-id="44251-103">DSC WindowsOptionalFeatureSet Resource</span></span>

> <span data-ttu-id="44251-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="44251-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="44251-105">Windows PowerShell Desired State Configuration (DSC) の **WindowsOptionalFeatureSet** リソースは、オプション機能をターゲット ノードで有効にするためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="44251-105">The **WindowsOptionalFeatureSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that optional features are enabled on a target node.</span></span> <span data-ttu-id="44251-106">このリソースは[複合リソース](authoringResourceComposite.md)であり、`Name` プロパティに指定されている機能ごとに [WindowsOptionalFeature リソース](windowsOptionalFeatureResource.md)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="44251-106">This resource is a [composite resource](authoringResourceComposite.md) that calls the [WindowsOptionalFeature resource](windowsOptionalFeatureResource.md) for each feature specified in the `Name` property.</span></span>

<span data-ttu-id="44251-107">Windows のオプション機能の数を同じ状態に構成するときにこのリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="44251-107">Use this resource when you want to configure a number of Windows optional features to the same state.</span></span>

## <a name="syntax"></a><span data-ttu-id="44251-108">構文</span><span class="sxs-lookup"><span data-stu-id="44251-108">Syntax</span></span>

```
WindowsOptionalFeature [string] #ResourceName
{
    Name = [string[]]
    [ Ensure = [string] { Enable | Disable }  ]
    [ Source = [string] ] 
    [ RemoveFilesOnDisable = [bool] ]  
    [ LogPath = [string] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ DependsOn = [string[]] ]
    
}
```

## <a name="properties"></a><span data-ttu-id="44251-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="44251-109">Properties</span></span>

|  <span data-ttu-id="44251-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="44251-110">Property</span></span>  |  <span data-ttu-id="44251-111">説明</span><span class="sxs-lookup"><span data-stu-id="44251-111">Description</span></span>   | 
|---|---| 
| <span data-ttu-id="44251-112">名前</span><span class="sxs-lookup"><span data-stu-id="44251-112">Name</span></span>| <span data-ttu-id="44251-113">有効または無効にする機能の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="44251-113">Indicates the name of the features that you want to ensure are enabled or disabled.</span></span>| 
| <span data-ttu-id="44251-114">Ensure</span><span class="sxs-lookup"><span data-stu-id="44251-114">Ensure</span></span>| <span data-ttu-id="44251-115">機能が有効化かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="44251-115">Specifies whether the features are enabled.</span></span> <span data-ttu-id="44251-116">機能を確実に有効にするには、このプロパティを "Enable" に設定します。機能を確実に無効にするには、このプロパティを "Disable" に設定します。</span><span class="sxs-lookup"><span data-stu-id="44251-116">To ensure that the features are enabled, set this property to "Enable" To ensure that the features are disabled, set the property to "Disable".</span></span>|
| <span data-ttu-id="44251-117">ソース</span><span class="sxs-lookup"><span data-stu-id="44251-117">Source</span></span>| <span data-ttu-id="44251-118">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="44251-118">Not implemented.</span></span>|
| <span data-ttu-id="44251-119">NoWindowsUpdateCheck</span><span class="sxs-lookup"><span data-stu-id="44251-119">NoWindowsUpdateCheck</span></span>| <span data-ttu-id="44251-120">機能を有効にするソース ファイルを検索するとき、DISM が Windows Update (WU) を確認するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="44251-120">Specifies whether DISM contacts Windows Update (WU) when searching for the source files to enable features.</span></span> <span data-ttu-id="44251-121">$true の場合、DISM は WU を確認しません。</span><span class="sxs-lookup"><span data-stu-id="44251-121">If $true, DISM does not contact WU.</span></span>|
| <span data-ttu-id="44251-122">RemoveFilesOnDisable</span><span class="sxs-lookup"><span data-stu-id="44251-122">RemoveFilesOnDisable</span></span>| <span data-ttu-id="44251-123">**[$true]** に設定すると、無効時に (つまり、**[Ensure]** が "Absent" に設定されているとき)、機能に関連付けられているすべてのファイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="44251-123">Set to **$true** to remove all files associated with the features when they are disabled (that is, when **Ensure** is set to "Absent").</span></span>|
| <span data-ttu-id="44251-124">ログ レベル</span><span class="sxs-lookup"><span data-stu-id="44251-124">LogLevel</span></span>| <span data-ttu-id="44251-125">ログに表示される最大の出力レベル。</span><span class="sxs-lookup"><span data-stu-id="44251-125">The maximum output level shown in the logs.</span></span> <span data-ttu-id="44251-126">有効な値は "ErrorsOnly" (エラーのみが記録されます)、"ErrorsAndWarning" (エラーと警告が記録されます)、"ErrorsAndWarningAndInformation" (エラー、警告、デバッグ情報が記録されます) です。</span><span class="sxs-lookup"><span data-stu-id="44251-126">The accepted values are: "ErrorsOnly" (only errors are logged), "ErrorsAndWarning" (errors and warnings are logged), and "ErrorsAndWarningAndInformation" (errors, warnings, and debug information are logged).</span></span>|
| <span data-ttu-id="44251-127">LogPath</span><span class="sxs-lookup"><span data-stu-id="44251-127">LogPath</span></span>| <span data-ttu-id="44251-128">リソース プロバイダーの操作を記録するログ ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="44251-128">The path to a log file where you want the resource provider to log the operation.</span></span>| 
| <span data-ttu-id="44251-129">DependsOn</span><span class="sxs-lookup"><span data-stu-id="44251-129">DependsOn</span></span>| <span data-ttu-id="44251-130">このリソースを構成する前に、他のリソースの構成を実行する必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="44251-130">Specifies that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="44251-131">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="44251-131">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>| 
 



