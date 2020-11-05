---
ms.date: 12/11/2018
title: 互換性のある PowerShell エディションまたはオペレーティング システムが含まれるパッケージ
description: この記事では、特定のプラットフォームやエディションとの互換性を条件にして PowerShell ギャラリーを検索する方法について説明します。
ms.openlocfilehash: 9806c09c85febfd74bb69adf3d294fb4f559ff23
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92661247"
---
# <a name="packages-with-compatible-powershell-editions-or-operating-systems"></a><span data-ttu-id="4d016-103">互換性のある PowerShell エディションまたはオペレーティング システムが含まれるパッケージ</span><span class="sxs-lookup"><span data-stu-id="4d016-103">Packages with compatible PowerShell Editions or Operating Systems</span></span>

<span data-ttu-id="4d016-104">バージョン 5.1 以降、機能セットとプラットフォーム互換性が異なる別エディションの PowerShell が用意されています。</span><span class="sxs-lookup"><span data-stu-id="4d016-104">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibilities.</span></span>

## <a name="searching-by-powershell-edition"></a><span data-ttu-id="4d016-105">PowerShell エディションで検索する</span><span class="sxs-lookup"><span data-stu-id="4d016-105">Searching by PowerShell Edition</span></span>

<span data-ttu-id="4d016-106">PowerShell の 2 つのエディション:</span><span class="sxs-lookup"><span data-stu-id="4d016-106">The two editions of PowerShell are:</span></span>

- <span data-ttu-id="4d016-107">**Desktop Edition:** .NET Framework 上に構築され、Windows の完全フットプリント エディション (Server Core、Windows Desktop など) で実行される PowerShell のバージョンをターゲットとするスクリプトおよびモジュールと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="4d016-107">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="4d016-108">**Core Edition:** .NET Core 上に構築されており、Nano Server や Windows IoT などの Windows の縮小エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。</span><span class="sxs-lookup"><span data-stu-id="4d016-108">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

### <a name="powershell-gallery-allows-you-to-filter-packages-compatible-for-specific-powershell-editions"></a><span data-ttu-id="4d016-109">PowerShell ギャラリーでは、特定の PowerShell エディションに対して互換性のあるパッケージをフィルタリングできます</span><span class="sxs-lookup"><span data-stu-id="4d016-109">PowerShell Gallery allows you to filter packages compatible for specific PowerShell Editions</span></span>

<span data-ttu-id="4d016-110">パッケージが指定された PSEditions と互換性がある場合、'PowerShell Editions' の一部としてパッケージの表示ページおよびパッケージ結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d016-110">If a package has compatible PSEditions specified, they are listed as part of 'PowerShell Editions' in the package display page and also in packages results.</span></span>
<span data-ttu-id="4d016-111">PowerShell を使用して互換性のあるパッケージを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="4d016-111">You can also search for compatible packages using PowerShell.</span></span>

![PSEditions での項目表示ページ](media/searching-by-compatibility/packagedisplaypagewithpseditions.PNG)

### <a name="search-for-packages-in-the-gallery-ui-that-work-on-powershell-core"></a><span data-ttu-id="4d016-113">PowerShell Core で機能するギャラリー UI のパッケージを検索する</span><span class="sxs-lookup"><span data-stu-id="4d016-113">Search for packages in the gallery UI that work on PowerShell Core</span></span>

<span data-ttu-id="4d016-114">Tags:"PSEdition_Desktop" と Tags:"PSEdition_Core" を使用して PowerShell ギャラリー上のパッケージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="4d016-114">Use Tags:"PSEdition_Desktop" and Tags:"PSEdition_Core" to filters the packages on PowerShell Gallery.</span></span>

### <a name="use-tagspsedition_core-to-search-items-compatible-with-powershell-core-edition"></a><span data-ttu-id="4d016-115">Tags:"PSEdition_Core" を使用して PowerShell Core エディションと互換性のある項目を検索します</span><span class="sxs-lookup"><span data-stu-id="4d016-115">Use Tags:"PSEdition_Core" to search items compatible with PowerShell Core Edition</span></span>

![Core PSEdition と互換性のある項目の検索](media/searching-by-compatibility/searchresultswithpseditions.PNG)

### <a name="use-tagspsedition_desktop-to-search-items-compatible-with-powershell-desktop-edition"></a><span data-ttu-id="4d016-117">Tags:"PSEdition_Desktop" を使用して PowerShell Desktop エディションと互換性のある項目を検索します</span><span class="sxs-lookup"><span data-stu-id="4d016-117">Use Tags:"PSEdition_Desktop" to search items compatible with PowerShell Desktop Edition</span></span>

![Desktop PSEdition と互換性のある項目の検索](media/searching-by-compatibility/searchresultswithpseditionsdesktop.PNG)

### <a name="search-for-packages-to-find-compatible-editions-using-powershell"></a><span data-ttu-id="4d016-119">PowerShell を使用し、パッケージの中から互換性のあるエディションを見つける</span><span class="sxs-lookup"><span data-stu-id="4d016-119">Search for packages to find compatible editions using PowerShell</span></span>

<span data-ttu-id="4d016-120">PowerShell エディションと OS のタグを指定してフィルタリングできます。</span><span class="sxs-lookup"><span data-stu-id="4d016-120">You can specify tags to filter for the PowerShell edition and OS.</span></span> <span data-ttu-id="4d016-121">`Find-Package` コマンドレットを指定します。`-Tag` パラメーターを指定し、対象のエディション (と OS) を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d016-121">You use the `Find-Package` cmdlet specifying the `-Tag` parameter to specify the edition (and OS) you are targeting.</span></span> <span data-ttu-id="4d016-122">例:</span><span class="sxs-lookup"><span data-stu-id="4d016-122">Like this:</span></span>

```powershell
# Find modules compatible with PowerShell Core:
Find-Module -Tag PSEdition_Core

# Find modules compatible with PowerShell Core on Linux:
Find-Module -Tag PSEdition_Core, Linux
```

## <a name="searching-by-operating-system"></a><span data-ttu-id="4d016-123">オペレーティング システムで検索する</span><span class="sxs-lookup"><span data-stu-id="4d016-123">Searching by Operating System</span></span>

<span data-ttu-id="4d016-124">PowerShell Core は Windows、Linux、MacOS で利用できるため、ギャラリーのパッケージは、それらの OS の組み合わせに合わせて設計されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="4d016-124">Since PowerShell Core is available for Windows, Linux, and MacOS, packages in the Gallery may be designed for any combination of these operating systems.</span></span> <span data-ttu-id="4d016-125">ギャラリー UI では、次の検索タグを使用し、オペレーティング システムのタグが付けられたパッケージを見つけます。</span><span class="sxs-lookup"><span data-stu-id="4d016-125">In the gallery UI use the following searchs tags to find packages tagged by operating system:</span></span>

- <span data-ttu-id="4d016-126">タグ:"Windows"</span><span class="sxs-lookup"><span data-stu-id="4d016-126">Tags: "Windows"</span></span>
- <span data-ttu-id="4d016-127">タグ:"Linux"</span><span class="sxs-lookup"><span data-stu-id="4d016-127">Tags: "Linux"</span></span>
- <span data-ttu-id="4d016-128">タグ:"MacOS"</span><span class="sxs-lookup"><span data-stu-id="4d016-128">Tags: "MacOS"</span></span>

<span data-ttu-id="4d016-129">`Find-Module` (と PowerShellGet モジュールのその他のコマンドレット) でこれらのタグを指定できます。例:</span><span class="sxs-lookup"><span data-stu-id="4d016-129">You can specify these tags on `Find-Module` (and other cmdlets in the PowerShellGet module), like this:</span></span>

```powershell
# Find Modules compatible with Windows
Find-Module -Tag Linux
```

## <a name="searching-for-multiple-compatibilities"></a><span data-ttu-id="4d016-130">複数の互換性の検索</span><span class="sxs-lookup"><span data-stu-id="4d016-130">Searching for Multiple Compatibilities</span></span>

<span data-ttu-id="4d016-131">次の構文を使用し、互換性が複数あるパッケージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="4d016-131">You can look for a package that has multiple compatibilities by using the syntax:</span></span>

<span data-ttu-id="4d016-132">タグ:"Compatibility1" "Compatibility2"</span><span class="sxs-lookup"><span data-stu-id="4d016-132">Tags: "Compatibility1" "Compatibility2"</span></span>

<span data-ttu-id="4d016-133">たとえば、Windows コンピューターと Linux コンピューターの両方で実行される PowerShell Core Compatibility が与えられたパッケージを検索する場合、次の検索タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="4d016-133">For example, if you are looking for a package with PowerShell Core Compatibility that runs on both my Windows and Linux machines, use the search tags:</span></span>

<span data-ttu-id="4d016-134">タグ:"PSEdition_Core" "Windows" "Linux"</span><span class="sxs-lookup"><span data-stu-id="4d016-134">Tags: "PSEdition_Core" "Windows" "Linux"</span></span>

<span data-ttu-id="4d016-135">PowerShell を使用して検索するには、`Find-Module` (と PowerShellGet モジュールのその他のコマンドレット) を使用できます。例:</span><span class="sxs-lookup"><span data-stu-id="4d016-135">To search using PowerShell, you can use the `Find-Module` (and the other cmdlets in the PowerShellGet module), like this:</span></span>

```powershell
# Find scripts compatible with PowerShell Core, Windows, and Linux
Find-Script -Tag PSEdition_Core,Linux,Windows

# Find modules compatible with PowerSHellCore and MacOS
Find-Module -Tag PSEdition_Core,MacOS
```

## <a name="more-details-on-authoring-and-finding-the-packages-with-compatible-powershell-editions"></a><span data-ttu-id="4d016-136">互換性のある PowerShell エディションが含まれるパッケージの作成と検索に関する詳細</span><span class="sxs-lookup"><span data-stu-id="4d016-136">More details on authoring and finding the packages with compatible PowerShell Editions</span></span>

- [<span data-ttu-id="4d016-137">PSEditions が含まれるモジュール</span><span class="sxs-lookup"><span data-stu-id="4d016-137">Modules with PSEditions</span></span>](../../concepts/module-psedition-support.md)
- [<span data-ttu-id="4d016-138">PSEditions のスクリプト</span><span class="sxs-lookup"><span data-stu-id="4d016-138">Scripts with PSEditions</span></span>](../../concepts/script-psedition-support.md)
