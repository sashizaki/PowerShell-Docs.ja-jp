---
title: 参照記事の編集
description: この記事では、コマンドレット参照の編集に関する特定の要件と、PowerShell ドキュメントの概要トピックについて説明します。
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: e135f6cc81ba7537a535a08421e1ca9b2b2af573
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81624773"
---
# <a name="editing-reference-articles"></a>参照記事の編集

コマンドレットの参照記事には特定の構造があり、 その構造は [PlatyPS][] によって定義されます。
PlatyPS により、Markdown で PowerShell モジュール用コマンドレット ヘルプが生成されます。 Markdown ファイルの編集後、PlatyPS を使って、`Get-Help` コマンドレットで使用される MAML ヘルプ ファイルが作成されます。

PlatyPS には、コードに書き込まれるコマンドレット参照用のハードコーディングされたスキーマが含まれています。 [platyPS.schema.md][] ドキュメントはこの構造を記述しようとし、 スキーマ違反がある場合はビルド エラーが発生します。コントリビューションを受け入れるには、このエラーを修正しておく必要があります。

## <a name="general-guidelines"></a>一般的なガイドライン

- ヘッダー構造はどれも削除しないでください。 PlatyPS は、特定のヘッダー セットを想定しています。
- **入力型**ヘッダーと**出力型**ヘッダーには型が必要です。 コマンドレットが入力を受け取らない場合、または値を返さない場合は、値 `None` を使用します。
- フェンスされたコード ブロックは、[Examples](#structuring-examples) セクションでのみ許可されています。
- インライン コードの範囲は、任意の段落で使用できます。

## <a name="formatting-about_-files"></a>About_ ファイルの書式設定

`About_*` ファイルは Markdown で記述されますが、プレーン テキスト ファイルとして出荷されます。 Markdown からプレーン テキストへの変換には、[Pandoc][] を使用しています。 `About_*` ファイルは、すべてのバージョンの PowerShell および発行ツールとの最大限の互換性が確保されるように書式設定されています。

基本的な書式設定に関するガイドライン:

- 行は 80 文字に制限します。 Pandoc では一部の Markdown ブロックがインデントされるため、それらのブロックを調整する必要があります。
  - コード ブロックの文字数は 76 文字に制限されます
  - テーブルは 76 文字に制限されます
  - ブロック引用 (およびアラート) は 78 文字に制限されます

- Pandoc 特殊メタ文字 `\`、`$`、および `<` の使用
  - ヘッダー内では、これらの文字は先頭の `\` 文字を使用してエスケープするか、バッククォート (`` ` ``) を使用してコード範囲で囲む必要があります
  - 段落内では、これらの文字はコード範囲内に配置する必要があります。 次に例を示します。

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

- テーブルは 76 文字以内に収める必要があります
  - セルのコンテンツが複数行にわたる場合は手動で折り返します
  - 行ごとに開始および終了 `|` 文字を使用します
  - 次の例では、セル内で複数の行に折り返される情報を含むテーブルを適切に構築する方法を示します。

    ~~~markdown
    ```
    |Operator|Description                |Example                          |
    |--------|---------------------------|---------------------------------|
    |`-is`   |Returns TRUE when the input|`(get-date) -is [DateTime]`      |
    |        |is an instance of the      |`True`                           |
    |        |specified .NET type.       |                                 |
    |`-isNot`|Returns TRUE when the input|`(get-date) -isNot [DateTime]`   |
    |        |not an instance of the     |`False`                          |
    |        |specified.NET type.        |                                 |
    |`-as`   |Converts the input to the  |`"5/7/07" -as [DateTime]`        |
    |        |specified .NET type.       |`Monday, May 7, 2007 12:00:00 AM`|
    ```
    ~~~

    > [!NOTE]
    > 76 列制限は `About_*` トピックにのみ適用されます。 幅広の列は、概念説明またはコマンドレット リファレンスの記事で使用できます。

## <a name="structuring-examples"></a>examples の構造化

PlatyPS スキーマでは、**EXAMPLES** ヘッダーは H2 ヘッダーで、各 example は H3 ヘッダーです。

example 内で、コード ブロックを段落で区切ることはスキーマで許可されていません。 サポートされているスキーマは次のとおりです。

```
### Example #X title

0 or more paragraphs
1 or more code blocks
0 or more paragraphs.
```

各 example に数値を指定し、簡単なタイトルを追加します。

次に例を示します。

### <a name="example-1-get-cmdlets-functions-and-aliases"></a>例 1:コマンドレット、関数、およびエイリアスを取得する

このコマンドは、コンピューターにインストールされている PowerShell コマンドレット、関数、およびエイリアスを取得します。

```powershell
Get-Command
```

### <a name="example-2-get-commands-in-the-current-session"></a>例 2:現在のセッションのコマンドを取得する

```powershell
Get-Command -ListImported
```

## <a name="next-steps"></a>次のステップ

[編集チェックリスト](editorial-checklist.md)

<!-- link references -->
[PlatyPS]: https://github.com/powershell/platyps
[platyPS.schema.md]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[issue1806]: https://github.com/MicrosoftDocs/PowerShell-Docs/issues/1806
[about-example]: /PowerShell/module/Microsoft.PowerShell.Core/About/about_Comparison_Operators
[Pandoc]: https://pandoc.org
