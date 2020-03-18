---
title: 参照記事の編集
description: この記事では、コマンドレット参照の編集に関する特定の要件と、PowerShell ドキュメントの概要トピックについて説明します。
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 3c6f1b4fc27ca8ece7ec30317daf4ed2a6bc9228
ms.sourcegitcommit: 18d832858a7b8ea094763afa753e0f48f01372e7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2020
ms.locfileid: "79060327"
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

`About_*` ファイルは、PlatyPS ではなく [Pandoc][] によって処理されるようになりました。 `About_*` ファイルは、すべてのバージョンの PowerShell および発行ツールとの最大限の互換性が確保されるように書式設定されています。

基本的な書式設定に関するガイドライン:

- 行 は 80 文字に制限します
- コード ブロックとテーブルについては、テキストへの変換中、Pandoc によってスペース 4 つ分だけインデントされるため、76 文字に制限されます
- テーブルは 76 文字以内に収める必要があります
  - セルのコンテンツが複数行にわたる場合は手動で折り返します
  - 行ごとに開始および終了 `|` 文字を使用します
  - [about_Comparison_Operators][about-example] の作業例をご覧ください
- 使用できる Pandoc 特殊文字は `\`、`$`、および `<` です
  - ヘッダー内では、これらの文字は先頭の `\` 文字を使用してエスケープするか、バッククォート (`` ` ``) で囲む必要があります
  - 段落内では、これらの文字はコード範囲内に配置する必要があります。 次に例を示します。

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

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
[about-example]: https://github.com/MicrosoftDocs/PowerShell-Docs/reference/5.1/Microsoft.PowerShell.Core/About/about_Comparison_Operators.md
[Pandoc]: https://pandoc.org
