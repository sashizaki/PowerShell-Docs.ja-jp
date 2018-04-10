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
# <a name="items-with-compatible-powershell-editions"></a>互換性のある PowerShell エディションが含まれる項目
バージョン 5.1 から、PowerShell はさまざまな機能セットとプラットフォーム互換性を備える別のエディションで使用できます。

- **デスクトップ エディション:** .NET Framework 上に構築されており、Server Core や Windows Desktop などの Windows の完全エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。
- **コア エディション:** .NET Core 上に構築されており、Nano Server や Windows IoT などの Windows の縮小エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。

## <a name="powershell-gallery-extracts-supported-pseditions-metadata-and-allows-you-to-filters-the-items-compatible-for-specific-powershell-editions"></a>PowerShell ギャラリーは、サポートされている PSEditions メタデータを抽出するため、特定のPowerShell のエディションと互換性のある項目をフィルター処理できます。

項目が指定した PSEditions と互換性がある場合、'PowerShell Editions' の一部として項目の表示ページ、および項目結果に表示されます。
![PSEditions での項目表示ページ](Images/ItemDisplayPageWithPSEditions.PNG)

## <a name="search-for-items-in-the-gallery-ui-which-works-on-powershellcore"></a>PowerShellCore で機能するギャラリー UI の項目を検索します。
Tags:"PSEdition_Desktop" と Tags:"PSEdition_Core" を使用して PowerShell ギャラリー上の項目をフィルター処理します。

### <a name="use-tagspseditioncore-to-search-items-compatible-with-powershell-core-edition"></a>Tags:"PSEdition_Core" を使用して PowerShell Core エディションと互換性のある項目を検索します。
![Core PSEdition と互換性のある項目の検索](Images/SearchResultsWithPSEditions.PNG)

### <a name="use-tagspseditiondesktop-to-search-items-compatible-with-powershell-desktop-edition"></a>Tags:"PSEdition_Desktop" を使用して PowerShell Desktop エディションと互換性のある項目を検索します。
![Desktop PSEdition と互換性のある項目の検索](Images/SearchResultsWithPSEdition_Desktop.PNG)

## <a name="more-details-on-authoring-and-finding-the-items-with-compatible-powershell-editions"></a>互換性のある PowerShell エディションが含まれる項目の作成と検索に関する詳細
### <a name="modules-with-pseditionspsgetmodulemodulewithpseditionsupportmd"></a>[PSEditions が含まれるモジュール](../psget/module/modulewithpseditionsupport.md)
### <a name="scripts-with-pseditionspsgetscriptscriptwithpseditionsupportmd"></a>[PSEditions のスクリプト](../psget/script/scriptwithpseditionsupport.md)