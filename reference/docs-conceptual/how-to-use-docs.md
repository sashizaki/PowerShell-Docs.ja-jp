---
ms.date: 09/25/2019
keywords: PowerShell, コマンドレット
title: PowerShell ドキュメントの使用方法
ms.openlocfilehash: 9e3d5828d6bdb4ef14701994f146354a041efaea
ms.sourcegitcommit: a80bb79b85deab8ae3c21de56d1ee432fdd92628
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2019
ms.locfileid: "72281654"
---
# <a name="how-to-use-the-powershell-documentation"></a>PowerShell ドキュメントの使用方法

PowerShell のオンライン ドキュメントへようこそ。 このサイトには、次のバージョンの PowerShell のコマンドレット リファレンスが含まれています。

- PowerShell 7 (プレビュー)
- PowerShell 6
- PowerShell 5.1
- PowerShell 5.0
- PowerShell 4.0
- PowerShell 3.0

## <a name="selecting-your-version"></a>バージョンの選択

既定では、このサイトには PowerShell の最新リリース バージョンのドキュメントが表示されます。 コマンドレットの中には、PowerShell のバージョンによって動作が異なるものがあります。 使用している PowerShell のバージョンのドキュメントを表示していることを確認してください。

ページの上部にあるバージョン ピッカーを使用し、目的の PowerShell のバージョンを選択します。

![バージョン ピッカー](images/how-to-use-docs/picker-vall.gif)

`$PSversionTable.PSVersion` の値を調べることで、お客様が使用している PowerShell のバージョンを確認できます。 次の例は、Windows PowerShell v5.1 に対する出力を示しています。

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      18362  145
```

## <a name="searching-for-articles"></a>記事の検索

ドキュメントでコンテンツを検索する方法が 2 とおりあります。最も簡単な方法は、バージョン セレクターの下にあるフィルター ボックスを使用することです。 記事のタイトルに表示される単語を入力してください。 一致する記事の一覧がページに表示されます。 その一覧からサイト全体を検索するオプションを選択することもできます。

![フィルター ボックス](images/how-to-use-docs/filter-search.gif)
