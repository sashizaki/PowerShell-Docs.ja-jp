---
ms.date: 06/12/2017
contributor: JKeithB
ms.topic: conceptual
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: psgallery_pseditions
ms.openlocfilehash: 0b30c1da53832a6b74be7aa14ed9331b1e9fe643
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="items-with-compatible-powershell-editions"></a><span data-ttu-id="baf72-103">互換性のある PowerShell エディションが含まれる項目</span><span class="sxs-lookup"><span data-stu-id="baf72-103">Items with compatible PowerShell Editions</span></span>
<span data-ttu-id="baf72-104">バージョン 5.1 から、PowerShell はさまざまな機能セットとプラットフォーム互換性を備える別のエディションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="baf72-104">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="baf72-105">**デスクトップ エディション:** .NET Framework 上に構築されており、Server Core や Windows Desktop などの Windows の完全エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。</span><span class="sxs-lookup"><span data-stu-id="baf72-105">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="baf72-106">**コア エディション:** .NET Core 上に構築されており、Nano Server や Windows IoT などの Windows の縮小エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。</span><span class="sxs-lookup"><span data-stu-id="baf72-106">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

## <a name="powershell-gallery-extracts-supported-pseditions-metadata-and-allows-you-to-filters-the-items-compatible-for-specific-powershell-editions"></a><span data-ttu-id="baf72-107">PowerShell ギャラリーは、サポートされている PSEditions メタデータを抽出するため、特定のPowerShell のエディションと互換性のある項目をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="baf72-107">PowerShell Gallery extracts supported PSEditions metadata and allows you to filters the items compatible for specific PowerShell Editions</span></span>

<span data-ttu-id="baf72-108">項目が指定した PSEditions と互換性がある場合、'PowerShell Editions' の一部として項目の表示ページ、および項目結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="baf72-108">If an item has compatible PSEditions specified, they will be listed as part of 'PowerShell Editions' in the item display page and also in items results.</span></span>
<span data-ttu-id="baf72-109">![PSEditions での項目表示ページ](Images/ItemDisplayPageWithPSEditions.PNG)</span><span class="sxs-lookup"><span data-stu-id="baf72-109">![Item display page with PSEditions](Images/ItemDisplayPageWithPSEditions.PNG)</span></span>

## <a name="search-for-items-in-the-gallery-ui-which-works-on-powershellcore"></a><span data-ttu-id="baf72-110">PowerShellCore で機能するギャラリー UI の項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="baf72-110">Search for items in the gallery UI which works on PowerShellCore</span></span>
<span data-ttu-id="baf72-111">Tags:"PSEdition_Desktop" と Tags:"PSEdition_Core" を使用して PowerShell ギャラリー上の項目をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="baf72-111">Use Tags:"PSEdition_Desktop" and Tags:"PSEdition_Core" to filters the items on PowerShell Gallery.</span></span>

### <a name="use-tagspseditioncore-to-search-items-compatible-with-powershell-core-edition"></a><span data-ttu-id="baf72-112">Tags:"PSEdition_Core" を使用して PowerShell Core エディションと互換性のある項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="baf72-112">Use Tags:"PSEdition_Core" to search items compatible with PowerShell Core Edition.</span></span>
![Core PSEdition と互換性のある項目の検索](Images/SearchResultsWithPSEditions.PNG)

### <a name="use-tagspseditiondesktop-to-search-items-compatible-with-powershell-desktop-edition"></a><span data-ttu-id="baf72-114">Tags:"PSEdition_Desktop" を使用して PowerShell Desktop エディションと互換性のある項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="baf72-114">Use Tags:"PSEdition_Desktop" to search items compatible with PowerShell Desktop Edition.</span></span>
![Desktop PSEdition と互換性のある項目の検索](Images/SearchResultsWithPSEdition_Desktop.PNG)

## <a name="more-details-on-authoring-and-finding-the-items-with-compatible-powershell-editions"></a><span data-ttu-id="baf72-116">互換性のある PowerShell エディションが含まれる項目の作成と検索に関する詳細</span><span class="sxs-lookup"><span data-stu-id="baf72-116">More details on authoring and finding the items with compatible PowerShell Editions</span></span>
### <a name="modules-with-pseditionspsgetmodulemodulewithpseditionsupportmd"></a>[<span data-ttu-id="baf72-117">PSEditions が含まれるモジュール</span><span class="sxs-lookup"><span data-stu-id="baf72-117">Modules with PSEditions</span></span>](../psget/module/modulewithpseditionsupport.md)
### <a name="scripts-with-pseditionspsgetscriptscriptwithpseditionsupportmd"></a>[<span data-ttu-id="baf72-118">PSEditions のスクリプト</span><span class="sxs-lookup"><span data-stu-id="baf72-118">Scripts with PSEditions</span></span>](../psget/script/scriptwithpseditionsupport.md)