---
description: 
manager: carolz
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "powershell,コマンドレット,ギャラリー"
ms.date: 2016-10-14
contributor: manikb
title: psgallery_pseditions
ms.technology: powershell
translationtype: Human Translation
ms.sourcegitcommit: e6c526d1074f61154d03b92b6bf6f599976f5936
ms.openlocfilehash: a2e6f87603795e7781115239b87c73a076e5e6ca

---

# 互換性のある PowerShell エディションが含まれる項目
バージョン 5.1 から、PowerShell はさまざまな機能セットとプラットフォーム互換性を備える別のエディションで使用できます。

- **デスクトップ エディション:** .NET Framework 上に構築されており、Server Core や Windows Desktop などの Windows の完全エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。
- **コア エディション:** .NET Core 上に構築されており、Nano Server や Windows IoT などの Windows の縮小エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。

## PowerShell ギャラリーは、サポートされている PSEditions メタデータを抽出するため、特定のPowerShell のエディションと互換性のある項目をフィルター処理できます。

項目が指定した PSEditions と互換性がある場合、'PowerShell Editions' の一部として項目の表示ページ、および項目結果に表示されます。
![PSEditions での項目表示ページ](Images/ItemDisplayPageWithPSEditions.PNG)

## PowerShellCore で機能するギャラリー UI の項目を検索します。
Tags:"PSEdition_Desktop" と Tags:"PSEdition_Core" を使用して PowerShell ギャラリー上の項目をフィルター処理します。

### Tags:"PSEdition_Core" を使用して PowerShell Core エディションと互換性のある項目を検索します。
![Core PSEdition と互換性のある項目の検索](Images/SearchResultsWithPSEditions.PNG)

### Tags:"PSEdition_Desktop" を使用して PowerShell Desktop エディションと互換性のある項目を検索します。
![Desktop PSEdition と互換性のある項目の検索](Images/SearchResultsWithPSEdition_Desktop.PNG)

## 互換性のある PowerShell エディションが含まれる項目の作成と検索に関する詳細
### [PSEditions が含まれるモジュール](../psget/module/modulewithpseditionsupport.md)
### [PSEditions のスクリプト](../psget/script/scriptwithpseditionsupport.md)




<!--HONumber=Oct16_HO2-->


