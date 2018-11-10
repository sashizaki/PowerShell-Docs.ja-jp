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
# <a name="packages-with-compatible-powershell-editions"></a>互換性のある PowerShell エディションが含まれるパッケージ

バージョン 5.1 から、PowerShell はさまざまな機能セットとプラットフォーム互換性を備える別のエディションで使用できます。

- **デスクトップ エディション:** .NET Framework 上に構築されており、Server Core や Windows Desktop などの Windows の完全エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。
- **コア エディション:** .NET Core 上に構築されており、Nano Server や Windows IoT などの Windows の縮小エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。

## <a name="powershell-gallery-extracts-supported-pseditions-metadata-and-allows-you-to-filters-the-packages-compatible-for-specific-powershell-editions"></a>PowerShell ギャラリーでサポートされている PSEditions メタデータを抽出し、特定の PowerShell エディションと互換性のあるパッケージをフィルター処理できるようにする

パッケージが指定された PSEditions と互換性がある場合、'PowerShell Editions' の一部としてパッケージの表示ページ、およびパッケージ結果に表示されます。

![PSEditions での項目表示ページ](../../Images/manual_package_download.png)

## <a name="search-for-packages-in-the-gallery-ui-which-works-on-powershellcore"></a>PowerShellCore で機能するギャラリー UI のパッケージを検索する

Tags:"PSEdition_Desktop" と Tags:"PSEdition_Core" を使用して PowerShell ギャラリー上のパッケージをフィルター処理します。

### <a name="use-tagspseditioncore-to-search-items-compatible-with-powershell-core-edition"></a>Tags:"PSEdition_Core" を使用して PowerShell Core エディションと互換性のある項目を検索します。

![Core PSEdition と互換性のある項目の検索](../../Images/SearchResultsWithPSEditions.PNG)

### <a name="use-tagspseditiondesktop-to-search-items-compatible-with-powershell-desktop-edition"></a>Tags:"PSEdition_Desktop" を使用して PowerShell Desktop エディションと互換性のある項目を検索します。

![Desktop PSEdition と互換性のある項目の検索](../../Images/SearchResultsWithPSEdition-Desktop.PNG)

## <a name="more-details-on-authoring-and-finding-the-packages-with-compatible-powershell-editions"></a>互換性のある PowerShell エディションが含まれるパッケージの作成と検索に関する詳細

- [PSEditions が含まれるモジュール](../../concepts/module-psedition-support.md)
- [PSEditions のスクリプト](../../concepts/script-psedition-support.md)
