---
ms.date: 12/11/2018
contributor: JKeithB, SydneyhSmith
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: 互換性のある PowerShell エディションまたはオペレーティング システムを使用してパッケージ
ms.openlocfilehash: 8230866561d3021379a48cc2c83fb4104a4058c1
ms.sourcegitcommit: d396d0e4cfe3d279f399c17e7337380a31d373ac
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2018
ms.locfileid: "53747706"
---
# <a name="packages-with-compatible-powershell-editions-or-operating-systems"></a><span data-ttu-id="beea6-103">互換性のある PowerShell エディションまたはオペレーティング システムを使用してパッケージ</span><span class="sxs-lookup"><span data-stu-id="beea6-103">Packages with compatible PowerShell Editions or Operating Systems</span></span>

<span data-ttu-id="beea6-104">バージョン 5.1 以降、機能セットとプラットフォーム互換性が異なる別エディションの PowerShell が用意されています。</span><span class="sxs-lookup"><span data-stu-id="beea6-104">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibilities.</span></span>

## <a name="searching-by-powershell-edition"></a><span data-ttu-id="beea6-105">PowerShell のエディションでの検索</span><span class="sxs-lookup"><span data-stu-id="beea6-105">Searching by PowerShell Edition</span></span> 
<span data-ttu-id="beea6-106">Powershell の 2 つのエディションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="beea6-106">The two editions of Powershell are:</span></span>
- <span data-ttu-id="beea6-107">**Desktop Edition:** .NET Framework 上に構築され、Windows の完全フットプリント エディション (Server Core、Windows Desktop など) で実行される PowerShell のバージョンをターゲットとするスクリプトおよびモジュールと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="beea6-107">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="beea6-108">**コア エディション:**.NET Core 上に構築され、スクリプトおよび Nano Server などの Windows や Windows IoT の縮小エディションで実行されている PowerShell のバージョンを対象とするモジュールとの互換性を提供します。</span><span class="sxs-lookup"><span data-stu-id="beea6-108">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

### <a name="powershell-gallery-allows-you-to-filter-packages-compatible-for-specific-powershell-editions"></a><span data-ttu-id="beea6-109">PowerShell ギャラリーでは、特定の PowerShell エディションの互換性のあるパッケージをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="beea6-109">PowerShell Gallery allows you to filter packages compatible for specific PowerShell Editions</span></span>

<span data-ttu-id="beea6-110">パッケージが互換性のある場合は、指定した PSEditions ' PowerShell Editions' の一部として表示されているページを表示するパッケージとパッケージの結果。</span><span class="sxs-lookup"><span data-stu-id="beea6-110">If a package has compatible PSEditions specified, they are listed as part of 'PowerShell Editions' in the package display page and also in packages results.</span></span>
<span data-ttu-id="beea6-111">PowerShell を使用して互換性のあるパッケージを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="beea6-111">You can also search for compatible packages using PowerShell.</span></span>

![PSEditions での項目表示ページ](../../Images/packagedisplaypagewithpseditions.PNG)

### <a name="search-for-packages-in-the-gallery-ui-that-work-on-powershell-core"></a><span data-ttu-id="beea6-113">PowerShell Core で機能するギャラリー UI でのパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="beea6-113">Search for packages in the gallery UI that work on PowerShell Core</span></span>

<span data-ttu-id="beea6-114">Tags:"PSEdition_Desktop" と Tags:"PSEdition_Core" を使用して PowerShell ギャラリー上のパッケージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="beea6-114">Use Tags:"PSEdition_Desktop" and Tags:"PSEdition_Core" to filters the packages on PowerShell Gallery.</span></span>

### <a name="use-tagspseditioncore-to-search-items-compatible-with-powershell-core-edition"></a><span data-ttu-id="beea6-115">Tags:"PSEdition_Core" を使用して PowerShell Core エディションと互換性のある項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="beea6-115">Use Tags:"PSEdition_Core" to search items compatible with PowerShell Core Edition.</span></span>

![Core PSEdition と互換性のある項目の検索](../../Images/searchresultswithpseditions.PNG)

### <a name="use-tagspseditiondesktop-to-search-items-compatible-with-powershell-desktop-edition"></a><span data-ttu-id="beea6-117">Tags:"PSEdition_Desktop" を使用して PowerShell Desktop エディションと互換性のある項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="beea6-117">Use Tags:"PSEdition_Desktop" to search items compatible with PowerShell Desktop Edition.</span></span>

![Desktop PSEdition と互換性のある項目の検索](../../Images/searchresultswithpseditionsdesktop.PNG)

### <a name="search-for-packages-to-find-compatible-editions-using-powershell"></a><span data-ttu-id="beea6-119">PowerShell を使用して互換性のあるエディションを検索するパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="beea6-119">Search for packages to find compatible editions using PowerShell</span></span>
<span data-ttu-id="beea6-120">PowerShell のエディションと OS のフィルター処理するタグを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="beea6-120">You can specify tags to filter for the PowerShell edition and OS.</span></span> <span data-ttu-id="beea6-121">使用する、`Find-Package`コマンドレットを指定する、 `-Tag` edition (およびの OS) を指定するパラメーター対象としています。</span><span class="sxs-lookup"><span data-stu-id="beea6-121">You use the `Find-Package` cmdlet specifying the `-Tag` parameter to specify the edition (and OS) you are targeting.</span></span>
<span data-ttu-id="beea6-122">このように：</span><span class="sxs-lookup"><span data-stu-id="beea6-122">Like this:</span></span>

```powershell
# Find modules compatible with PowerShell Core:
Find-Module -Tag PSEdition_Core

# Find modules compatible with PowerShell Core on Linux:
Find-Module -Tag PSEdition_Core, Linux
```

## <a name="searching-by-operating-system"></a><span data-ttu-id="beea6-123">オペレーティング システムでの検索</span><span class="sxs-lookup"><span data-stu-id="beea6-123">Searching by Operating System</span></span> 

<span data-ttu-id="beea6-124">PowerShell Core は、Windows、Linux、および MacOS の使用可能なであるために、これらのオペレーティング システムの任意の組み合わせのギャラリー内のパッケージを設計する場合があります。</span><span class="sxs-lookup"><span data-stu-id="beea6-124">Since PowerShell Core is available for Windows, Linux, and MacOS, packages in the Gallery may be designed for any combination of these operating systems.</span></span> <span data-ttu-id="beea6-125">ギャラリー UI には、オペレーティング システムでタグ付けされたパッケージを検索するのに searchs に次のタグを使用します。</span><span class="sxs-lookup"><span data-stu-id="beea6-125">In the gallery UI use the following searchs tags to find packages tagged by operating system:</span></span>

- <span data-ttu-id="beea6-126">タグ:"Windows"</span><span class="sxs-lookup"><span data-stu-id="beea6-126">Tags: "Windows"</span></span>
- <span data-ttu-id="beea6-127">タグ:"Linux"</span><span class="sxs-lookup"><span data-stu-id="beea6-127">Tags: "Linux"</span></span>
- <span data-ttu-id="beea6-128">タグ:"MacOS"</span><span class="sxs-lookup"><span data-stu-id="beea6-128">Tags: "MacOS"</span></span> 

<span data-ttu-id="beea6-129">これらのタグを指定することができます`Find-Module`(およびその他の PowerShellGet モジュールのコマンドレット) 次のようにします。</span><span class="sxs-lookup"><span data-stu-id="beea6-129">You can specify these tags on `Find-Module` (and other cmdlets in the PowerShellGet module), like this:</span></span>

```powershell
# Find Modules compatible with Windows
Find-Module -Tag Linux
```

## <a name="searching-for-multiple-compatibilities"></a><span data-ttu-id="beea6-130">複数の互換性の検索</span><span class="sxs-lookup"><span data-stu-id="beea6-130">Searching for Multiple Compatibilities</span></span>

<span data-ttu-id="beea6-131">構文を使用して複数の互換性のあるパッケージを探すことができます。</span><span class="sxs-lookup"><span data-stu-id="beea6-131">You can look for a package that has multiple compatibilities by using the syntax:</span></span> 

<span data-ttu-id="beea6-132">タグ"Compatibility1""Compatibility2"</span><span class="sxs-lookup"><span data-stu-id="beea6-132">Tags: "Compatibility1" "Compatibility2"</span></span> 

<span data-ttu-id="beea6-133">たとえば、Windows と Linux の両方のマシンで実行される PowerShell Core の互換性を持つパッケージを探している場合は、検索タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="beea6-133">For example, if you are looking for a package with PowerShell Core Compatibility that runs on both my Windows and Linux machines, use the search tags:</span></span>

<span data-ttu-id="beea6-134">タグ"PSEdition_Core""Linux"の"Windows"</span><span class="sxs-lookup"><span data-stu-id="beea6-134">Tags: "PSEdition_Core" "Windows" "Linux"</span></span> 

<span data-ttu-id="beea6-135">PowerShell を使用して検索するに使用することができます、 `Find-Module` (および PowerShellGet モジュールの他のコマンドレット) 次のようにします。</span><span class="sxs-lookup"><span data-stu-id="beea6-135">To search using PowerShell, you can use the `Find-Module` (and the other cmdlets in the PowerShellGet module), like this:</span></span>

```powewrshell
# Find scripts compatible with PowerShell Core, Windows, and Linux
Find-Script -Tag PSEdition_Core,Linux,Windows

# Find modules compatible with PowerSHellCore and MacOS
Find-Module -Tag PSEdition_Core,MacOS
```

## <a name="more-details-on-authoring-and-finding-the-packages-with-compatible-powershell-editions"></a><span data-ttu-id="beea6-136">互換性のある PowerShell エディションが含まれるパッケージの作成と検索に関する詳細</span><span class="sxs-lookup"><span data-stu-id="beea6-136">More details on authoring and finding the packages with compatible PowerShell Editions</span></span>

- [<span data-ttu-id="beea6-137">PSEditions が含まれるモジュール</span><span class="sxs-lookup"><span data-stu-id="beea6-137">Modules with PSEditions</span></span>](../../concepts/module-psedition-support.md)
- [<span data-ttu-id="beea6-138">PSEditions のスクリプト</span><span class="sxs-lookup"><span data-stu-id="beea6-138">Scripts with PSEditions</span></span>](../../concepts/script-psedition-support.md)
