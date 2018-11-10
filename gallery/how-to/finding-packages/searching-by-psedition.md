---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: 互換性のある PowerShell エディションが含まれるパッケージ
ms.openlocfilehash: e16cfb0ee30e344c9399bec2985baafc5a252fd7
ms.sourcegitcommit: 98b7cfd8ad5718efa8e320526ca76c3cc4141d78
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50003785"
---
# <a name="packages-with-compatible-powershell-editions"></a><span data-ttu-id="f86a0-103">互換性のある PowerShell エディションが含まれるパッケージ</span><span class="sxs-lookup"><span data-stu-id="f86a0-103">Packages with compatible PowerShell Editions</span></span>

<span data-ttu-id="f86a0-104">バージョン 5.1 から、PowerShell はさまざまな機能セットとプラットフォーム互換性を備える別のエディションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f86a0-104">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="f86a0-105">**デスクトップ エディション:** .NET Framework 上に構築されており、Server Core や Windows Desktop などの Windows の完全エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。</span><span class="sxs-lookup"><span data-stu-id="f86a0-105">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="f86a0-106">**コア エディション:** .NET Core 上に構築されており、Nano Server や Windows IoT などの Windows の縮小エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。</span><span class="sxs-lookup"><span data-stu-id="f86a0-106">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

## <a name="powershell-gallery-extracts-supported-pseditions-metadata-and-allows-you-to-filters-the-packages-compatible-for-specific-powershell-editions"></a><span data-ttu-id="f86a0-107">PowerShell ギャラリーでサポートされている PSEditions メタデータを抽出し、特定の PowerShell エディションと互換性のあるパッケージをフィルター処理できるようにする</span><span class="sxs-lookup"><span data-stu-id="f86a0-107">PowerShell Gallery extracts supported PSEditions metadata and allows you to filters the packages compatible for specific PowerShell Editions</span></span>

<span data-ttu-id="f86a0-108">パッケージが指定された PSEditions と互換性がある場合、'PowerShell Editions' の一部としてパッケージの表示ページ、およびパッケージ結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f86a0-108">If a package has compatible PSEditions specified, they will be listed as part of 'PowerShell Editions' in the package display page and also in packages results.</span></span>

![PSEditions での項目表示ページ](../../Images/manual_package_download.png)

## <a name="search-for-packages-in-the-gallery-ui-which-works-on-powershellcore"></a><span data-ttu-id="f86a0-110">PowerShellCore で機能するギャラリー UI のパッケージを検索する</span><span class="sxs-lookup"><span data-stu-id="f86a0-110">Search for packages in the gallery UI which works on PowerShellCore</span></span>

<span data-ttu-id="f86a0-111">Tags:"PSEdition_Desktop" と Tags:"PSEdition_Core" を使用して PowerShell ギャラリー上のパッケージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="f86a0-111">Use Tags:"PSEdition_Desktop" and Tags:"PSEdition_Core" to filters the packages on PowerShell Gallery.</span></span>

### <a name="use-tagspseditioncore-to-search-items-compatible-with-powershell-core-edition"></a><span data-ttu-id="f86a0-112">Tags:"PSEdition_Core" を使用して PowerShell Core エディションと互換性のある項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="f86a0-112">Use Tags:"PSEdition_Core" to search items compatible with PowerShell Core Edition.</span></span>

![Core PSEdition と互換性のある項目の検索](../../Images/SearchResultsWithPSEditions.PNG)

### <a name="use-tagspseditiondesktop-to-search-items-compatible-with-powershell-desktop-edition"></a><span data-ttu-id="f86a0-114">Tags:"PSEdition_Desktop" を使用して PowerShell Desktop エディションと互換性のある項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="f86a0-114">Use Tags:"PSEdition_Desktop" to search items compatible with PowerShell Desktop Edition.</span></span>

![Desktop PSEdition と互換性のある項目の検索](../../Images/SearchResultsWithPSEdition-Desktop.PNG)

## <a name="more-details-on-authoring-and-finding-the-packages-with-compatible-powershell-editions"></a><span data-ttu-id="f86a0-116">互換性のある PowerShell エディションが含まれるパッケージの作成と検索に関する詳細</span><span class="sxs-lookup"><span data-stu-id="f86a0-116">More details on authoring and finding the packages with compatible PowerShell Editions</span></span>

- [<span data-ttu-id="f86a0-117">PSEditions が含まれるモジュール</span><span class="sxs-lookup"><span data-stu-id="f86a0-117">Modules with PSEditions</span></span>](../../concepts/module-psedition-support.md)
- [<span data-ttu-id="f86a0-118">PSEditions のスクリプト</span><span class="sxs-lookup"><span data-stu-id="f86a0-118">Scripts with PSEditions</span></span>](../../concepts/script-psedition-support.md)
