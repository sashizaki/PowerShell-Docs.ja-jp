---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: 検索結果のフィルター処理
ms.openlocfilehash: eafbc993a37eaee7413102ef9d669a6b07d6ff6e
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="filtering-search-results"></a>検索結果のフィルター処理

[[項目] タブ](https://www.powershellgallery.com/items)には、PowerShell ギャラリーで利用可能なすべての項目が表示されます。

項目のフィルター、並べ替え、検索には、複数の方法があります。
特定の項目に関する詳細情報を表示するには、項目をクリックします。

## <a name="filter-by"></a>フィルター条件

[フィルター条件] の下にあるドロップダウンでは、結果を次の条件でフィルター処理できます。
- プレリリースを含める
- 安定版パッケージのみ

"プレリリース" と "安定版パッケージ" の詳細については、PowerShell チームのブログの「[Prerelease Versioning Added to PowerShellGet and PowerShell Gallery (PowerShellGet と PowerShell ギャラリーにプレリリースのバージョン管理が追加)](https://blogs.msdn.microsoft.com/powershell/2017/12/05/prerelease-versioning-added-to-powershellget-and-powershell-gallery/)」をご覧ください。

ドロップダウンの下にあるチェック ボックスでは、結果を次の条件でフィルター処理できます。
- アイテムの種類
  - モジュール
  - スクリプト
- ［カテゴリ］
  - コマンドレット
  - DSC リソース
  - 機能
  - ロールの機能
  - ワークフロー

PowerShell ギャラリー内のモジュールのみを表示するには、[アイテムの種類] の [モジュール] をオンにします。
同様に、PowerShell ギャラリー内のスクリプトのみを表示するには、[アイテムの種類] の [スクリプト] をオンにします。

> [!NOTE]
> フィルターは包含です。
> 例: [コマンドレット] または [関数] \(またはその両方) をオンにした場合、コマンドレットと関数の両方を含む項目が表示されます。
> 選択されていない場合、項目は表示されません。
> 同様に、すべてのカテゴリが選択されている場合は、これらのカテゴリのいずれかを含む項目のみが表示されます。
> **これらのどのカテゴリにも属していない項目は表示されません。**

## <a name="sort-by"></a>並べ替え条件

[並べ替え条件] ドロップダウンでは、結果を次の条件で並べ替えることができます。
- [人気度] - 人気度はダウンロード数によって決定します
- [A - Z] - 項目名のアルファベット順です
- [最近使った項目] - 公開日に応じて項目が表示されます

## <a name="search-box"></a>[検索] ボックス

[検索] ボックスでは、キーワードで項目を検索することができます。
詳細については、「[ギャラリー検索構文](search-syntax.md)」をご覧ください。