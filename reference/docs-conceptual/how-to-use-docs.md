---
ms.date: 10/20/2019
keywords: powershell,コマンドレット
title: PowerShell ドキュメントの使用方法
ms.openlocfilehash: 7b73bc82f32e3ce1e6015822e0cc82078183931b
ms.sourcegitcommit: 01c60c0c97542dbad48ae34339cddbd813f1353b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2020
ms.locfileid: "78279310"
---
# <a name="how-to-use-the-powershell-documentation"></a>PowerShell ドキュメントの使用方法

PowerShell のオンライン ドキュメントへようこそ。 このサイトには、次のバージョンの PowerShell のコマンドレット リファレンスが含まれています。

- PowerShell 7 (プレビュー)
- PowerShell 6
- PowerShell 5.1

## <a name="finding-articles-and-selecting-a-version"></a>記事の検索とバージョンの選択

ドキュメントでコンテンツを検索する方法が 2 とおりあります。最も簡単な方法は、バージョン セレクターの下にあるフィルター ボックスを使用することです。 記事のタイトルに表示される単語を入力してください。 一致する記事の一覧がページに表示されます。 その一覧からサイト全体を検索するオプションを選択することもできます。

既定では、このサイトには PowerShell の最新リリース バージョンのドキュメントが表示されます。 コマンドレットの中には、PowerShell のバージョンによって動作が異なるものがあります。 使用している PowerShell のバージョンのドキュメントを表示していることを確認してください。

ページの上部にあるバージョン ピッカーを使用し、目的の PowerShell のバージョンを選択します。

![バージョン ピッカー](media/how-to-use-docs/version-search.gif)

`$PSversionTable.PSVersion` の値を調べることで、お客様が使用している PowerShell のバージョンを確認できます。 次の例は、Windows PowerShell v5.1 に対する出力を示しています。

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      18362  145
```
