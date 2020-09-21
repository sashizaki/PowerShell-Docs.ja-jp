---
ms.date: 07/29/2020
keywords: powershell,コマンドレット
title: PowerShell ドキュメントの使用方法
ms.openlocfilehash: 1cfeb9eea564e7618062e1b8ada4948bd9e22969
ms.sourcegitcommit: 9f9eb95bc859e9e0fed48101327a602b2ced351d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87821531"
---
# <a name="how-to-use-the-powershell-documentation"></a>PowerShell ドキュメントの使用方法

PowerShell のオンライン ドキュメントへようこそ。 このサイトには、次のバージョンの PowerShell のコマンドレット リファレンスが含まれています。

- PowerShell 7
- PowerShell 6
- PowerShell 5.1

## <a name="finding-articles-and-selecting-a-version"></a>記事の検索とバージョンの選択

ドキュメントでコンテンツを検索する方法が 2 とおりあります。最も簡単な方法は、バージョン セレクターの下にあるフィルター ボックスを使用することです。 記事のタイトルに表示される単語を入力してください。 一致する記事の一覧がページに表示されます。 その一覧からサイト全体を検索するオプションを選択することもできます。

既定では、このサイトには PowerShell の最新リリース バージョンのドキュメントが表示されます。 コマンドレットの中には、PowerShell のバージョンによって動作が異なるものがあります。 使用している PowerShell のバージョンのドキュメントを表示していることを確認してください。

ページの上部にあるバージョン ピッカーを使用し、目的の PowerShell のバージョンを選択します。

![バージョン ピッカーの使用](media/how-to-use-docs/version-search.gif)

`$PSversionTable.PSVersion` の値を調べることで、お客様が使用している PowerShell のバージョンを確認できます。 次の例は、Windows PowerShell 5.1 に対する出力を示しています。

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      19041  1
```

PowerShell を初めて使用する場合に、コマンドの構文を理解するためにヘルプが必要な場合は、「[コマンド構文について](/powershell/module/microsoft.powershell.core/about/about_command_syntax)」を参照してください。

## <a name="finding-articles-for-previous-versions"></a>以前のバージョンの記事の検索

PowerShell の以前のバージョンのドキュメントは、[以前のバージョン](https://aka.ms/PSLegacyDocs)のサイトにアーカイブされています。

このサイトには、次のトピックのドキュメントが含まれています。

- PowerShell 3.0
- PowerShell 4.0
- PowerShell 5.0
- PowerShell ワークフロー
- PowerShell Web Access
