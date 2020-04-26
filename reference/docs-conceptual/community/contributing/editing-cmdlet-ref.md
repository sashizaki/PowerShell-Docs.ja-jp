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
# <a name="editing-reference-articles"></a><span data-ttu-id="ba62b-103">参照記事の編集</span><span class="sxs-lookup"><span data-stu-id="ba62b-103">Editing reference articles</span></span>

<span data-ttu-id="ba62b-104">コマンドレットの参照記事には特定の構造があり、</span><span class="sxs-lookup"><span data-stu-id="ba62b-104">Cmdlet reference articles have a specific structure.</span></span> <span data-ttu-id="ba62b-105">その構造は [PlatyPS][] によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="ba62b-105">This structure is defined by [PlatyPS][].</span></span>
<span data-ttu-id="ba62b-106">PlatyPS により、Markdown で PowerShell モジュール用コマンドレット ヘルプが生成されます。</span><span class="sxs-lookup"><span data-stu-id="ba62b-106">PlatyPS generates the cmdlet help for PowerShell modules in Markdown.</span></span> <span data-ttu-id="ba62b-107">Markdown ファイルの編集後、PlatyPS を使って、`Get-Help` コマンドレットで使用される MAML ヘルプ ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ba62b-107">After editing the Markdown files, PlatyPS is used create the MAML help files used by the `Get-Help` cmdlet.</span></span>

<span data-ttu-id="ba62b-108">PlatyPS には、コードに書き込まれるコマンドレット参照用のハードコーディングされたスキーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ba62b-108">PlatyPS has a hard-coded schema for cmdlet reference that is written into the code.</span></span> <span data-ttu-id="ba62b-109">[platyPS.schema.md][] ドキュメントはこの構造を記述しようとし、</span><span class="sxs-lookup"><span data-stu-id="ba62b-109">The [platyPS.schema.md][] document attempts to describe this structure.</span></span> <span data-ttu-id="ba62b-110">スキーマ違反がある場合はビルド エラーが発生します。コントリビューションを受け入れるには、このエラーを修正しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba62b-110">Schema violations cause build errors that must be fixed before we can accept your contribution.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="ba62b-111">一般的なガイドライン</span><span class="sxs-lookup"><span data-stu-id="ba62b-111">General guidelines</span></span>

- <span data-ttu-id="ba62b-112">ヘッダー構造はどれも削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="ba62b-112">Do not remove any of the header structures.</span></span> <span data-ttu-id="ba62b-113">PlatyPS は、特定のヘッダー セットを想定しています。</span><span class="sxs-lookup"><span data-stu-id="ba62b-113">PlatyPS expects a specific set of headers.</span></span>
- <span data-ttu-id="ba62b-114">**入力型**ヘッダーと**出力型**ヘッダーには型が必要です。</span><span class="sxs-lookup"><span data-stu-id="ba62b-114">The **Input type** and **Output type** headers must have a type.</span></span> <span data-ttu-id="ba62b-115">コマンドレットが入力を受け取らない場合、または値を返さない場合は、値 `None` を使用します。</span><span class="sxs-lookup"><span data-stu-id="ba62b-115">If the cmdlet does not take input or return a value then use the value `None`.</span></span>
- <span data-ttu-id="ba62b-116">フェンスされたコード ブロックは、[Examples](#structuring-examples) セクションでのみ許可されています。</span><span class="sxs-lookup"><span data-stu-id="ba62b-116">Fenced code blocks are only allowed in the [Examples](#structuring-examples) section.</span></span>
- <span data-ttu-id="ba62b-117">インライン コードの範囲は、任意の段落で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ba62b-117">Inline code spans can be used in any paragraph.</span></span>

## <a name="formatting-about_-files"></a><span data-ttu-id="ba62b-118">About_ ファイルの書式設定</span><span class="sxs-lookup"><span data-stu-id="ba62b-118">Formatting About_ files</span></span>

<span data-ttu-id="ba62b-119">`About_*` ファイルは Markdown で記述されますが、プレーン テキスト ファイルとして出荷されます。</span><span class="sxs-lookup"><span data-stu-id="ba62b-119">`About_*` files are written in Markdown but are shipped as plain text files.</span></span> <span data-ttu-id="ba62b-120">Markdown からプレーン テキストへの変換には、[Pandoc][] を使用しています。</span><span class="sxs-lookup"><span data-stu-id="ba62b-120">We use [Pandoc][] to convert the Markdown to plain text.</span></span> <span data-ttu-id="ba62b-121">`About_*` ファイルは、すべてのバージョンの PowerShell および発行ツールとの最大限の互換性が確保されるように書式設定されています。</span><span class="sxs-lookup"><span data-stu-id="ba62b-121">`About_*` files are formatted for the best compatibility across all versions of PowerShell and with the publishing tools.</span></span>

<span data-ttu-id="ba62b-122">基本的な書式設定に関するガイドライン:</span><span class="sxs-lookup"><span data-stu-id="ba62b-122">Basic formatting guidelines:</span></span>

- <span data-ttu-id="ba62b-123">行は 80 文字に制限します。</span><span class="sxs-lookup"><span data-stu-id="ba62b-123">Limit lines to 80 characters.</span></span> <span data-ttu-id="ba62b-124">Pandoc では一部の Markdown ブロックがインデントされるため、それらのブロックを調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba62b-124">Pandoc indents some Markdown blocks so those block must be adjusted.</span></span>
  - <span data-ttu-id="ba62b-125">コード ブロックの文字数は 76 文字に制限されます</span><span class="sxs-lookup"><span data-stu-id="ba62b-125">Code blocks are limited to 76 characters</span></span>
  - <span data-ttu-id="ba62b-126">テーブルは 76 文字に制限されます</span><span class="sxs-lookup"><span data-stu-id="ba62b-126">Tables are limited 76 characters</span></span>
  - <span data-ttu-id="ba62b-127">ブロック引用 (およびアラート) は 78 文字に制限されます</span><span class="sxs-lookup"><span data-stu-id="ba62b-127">Blockquotes (and Alerts) are limited 78 characters</span></span>

- <span data-ttu-id="ba62b-128">Pandoc 特殊メタ文字 `\`、`$`、および `<` の使用</span><span class="sxs-lookup"><span data-stu-id="ba62b-128">Using Pandoc's special meta-characters `\`,`$`, and `<`</span></span>
  - <span data-ttu-id="ba62b-129">ヘッダー内では、これらの文字は先頭の `\` 文字を使用してエスケープするか、バッククォート (`` ` ``) を使用してコード範囲で囲む必要があります</span><span class="sxs-lookup"><span data-stu-id="ba62b-129">Within a header - these characters must be escaped using a leading `\` character or enclosed in code spans using backticks (`` ` ``)</span></span>
  - <span data-ttu-id="ba62b-130">段落内では、これらの文字はコード範囲内に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba62b-130">Within a paragraph, these characters should be put into code spans.</span></span> <span data-ttu-id="ba62b-131">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ba62b-131">For example:</span></span>

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

- <span data-ttu-id="ba62b-132">テーブルは 76 文字以内に収める必要があります</span><span class="sxs-lookup"><span data-stu-id="ba62b-132">Tables need to fit within 76 characters</span></span>
  - <span data-ttu-id="ba62b-133">セルのコンテンツが複数行にわたる場合は手動で折り返します</span><span class="sxs-lookup"><span data-stu-id="ba62b-133">Manually wrap contents of cells across multiple lines</span></span>
  - <span data-ttu-id="ba62b-134">行ごとに開始および終了 `|` 文字を使用します</span><span class="sxs-lookup"><span data-stu-id="ba62b-134">Use opening and closing `|` characters on each line</span></span>
  - <span data-ttu-id="ba62b-135">次の例では、セル内で複数の行に折り返される情報を含むテーブルを適切に構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ba62b-135">The following example illustrates how to properly construct a table that contains information that wraps on multiple lines within a cell.</span></span>

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
    > <span data-ttu-id="ba62b-136">76 列制限は `About_*` トピックにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="ba62b-136">The 76-column limitation applies only to `About_*` topics.</span></span> <span data-ttu-id="ba62b-137">幅広の列は、概念説明またはコマンドレット リファレンスの記事で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ba62b-137">You can use wide columns in conceptual or cmdlet reference articles.</span></span>

## <a name="structuring-examples"></a><span data-ttu-id="ba62b-138">examples の構造化</span><span class="sxs-lookup"><span data-stu-id="ba62b-138">Structuring examples</span></span>

<span data-ttu-id="ba62b-139">PlatyPS スキーマでは、**EXAMPLES** ヘッダーは H2 ヘッダーで、各 example は H3 ヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="ba62b-139">In the PlatyPS schema, the **EXAMPLES** header is an H2 header and each example is an H3 header.</span></span>

<span data-ttu-id="ba62b-140">example 内で、コード ブロックを段落で区切ることはスキーマで許可されていません。</span><span class="sxs-lookup"><span data-stu-id="ba62b-140">Within an example, the schema does not allow code blocks to be separated by paragraphs.</span></span> <span data-ttu-id="ba62b-141">サポートされているスキーマは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ba62b-141">The supported schema is:</span></span>

```
### Example #X title

0 or more paragraphs
1 or more code blocks
0 or more paragraphs.
```

<span data-ttu-id="ba62b-142">各 example に数値を指定し、簡単なタイトルを追加します。</span><span class="sxs-lookup"><span data-stu-id="ba62b-142">Number each example and add a brief title.</span></span>

<span data-ttu-id="ba62b-143">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ba62b-143">For example:</span></span>

### <a name="example-1-get-cmdlets-functions-and-aliases"></a><span data-ttu-id="ba62b-144">例 1:コマンドレット、関数、およびエイリアスを取得する</span><span class="sxs-lookup"><span data-stu-id="ba62b-144">Example 1: Get cmdlets, functions, and aliases</span></span>

<span data-ttu-id="ba62b-145">このコマンドは、コンピューターにインストールされている PowerShell コマンドレット、関数、およびエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="ba62b-145">This command gets the PowerShell cmdlets, functions, and aliases that are installed on the computer.</span></span>

```powershell
Get-Command
```

### <a name="example-2-get-commands-in-the-current-session"></a><span data-ttu-id="ba62b-146">例 2:現在のセッションのコマンドを取得する</span><span class="sxs-lookup"><span data-stu-id="ba62b-146">Example 2: Get commands in the current session</span></span>

```powershell
Get-Command -ListImported
```

## <a name="next-steps"></a><span data-ttu-id="ba62b-147">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ba62b-147">Next steps</span></span>

[<span data-ttu-id="ba62b-148">編集チェックリスト</span><span class="sxs-lookup"><span data-stu-id="ba62b-148">Editorial checklist</span></span>](editorial-checklist.md)

<!-- link references -->
[PlatyPS]: https://github.com/powershell/platyps
[platyPS.schema.md]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[issue1806]: https://github.com/MicrosoftDocs/PowerShell-Docs/issues/1806
[about-example]: /PowerShell/module/Microsoft.PowerShell.Core/About/about_Comparison_Operators
[Pandoc]: https://pandoc.org
