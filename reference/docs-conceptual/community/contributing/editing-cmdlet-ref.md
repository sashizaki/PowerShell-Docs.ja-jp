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
# <a name="editing-reference-articles"></a><span data-ttu-id="1b727-103">参照記事の編集</span><span class="sxs-lookup"><span data-stu-id="1b727-103">Editing reference articles</span></span>

<span data-ttu-id="1b727-104">コマンドレットの参照記事には特定の構造があり、</span><span class="sxs-lookup"><span data-stu-id="1b727-104">Cmdlet reference articles have a specific structure.</span></span> <span data-ttu-id="1b727-105">その構造は [PlatyPS][] によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="1b727-105">This structure is defined by [PlatyPS][].</span></span>
<span data-ttu-id="1b727-106">PlatyPS により、Markdown で PowerShell モジュール用コマンドレット ヘルプが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1b727-106">PlatyPS generates the cmdlet help for PowerShell modules in Markdown.</span></span> <span data-ttu-id="1b727-107">Markdown ファイルの編集後、PlatyPS を使って、`Get-Help` コマンドレットで使用される MAML ヘルプ ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1b727-107">After editing the Markdown files, PlatyPS is used create the MAML help files used by the `Get-Help` cmdlet.</span></span>

<span data-ttu-id="1b727-108">PlatyPS には、コードに書き込まれるコマンドレット参照用のハードコーディングされたスキーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b727-108">PlatyPS has a hard-coded schema for cmdlet reference that is written into the code.</span></span> <span data-ttu-id="1b727-109">[platyPS.schema.md][] ドキュメントはこの構造を記述しようとし、</span><span class="sxs-lookup"><span data-stu-id="1b727-109">The [platyPS.schema.md][] document attempts to describe this structure.</span></span> <span data-ttu-id="1b727-110">スキーマ違反がある場合はビルド エラーが発生します。コントリビューションを受け入れるには、このエラーを修正しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b727-110">Schema violations cause build errors that must be fixed before we can accept your contribution.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="1b727-111">一般的なガイドライン</span><span class="sxs-lookup"><span data-stu-id="1b727-111">General guidelines</span></span>

- <span data-ttu-id="1b727-112">ヘッダー構造はどれも削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="1b727-112">Do not remove any of the header structures.</span></span> <span data-ttu-id="1b727-113">PlatyPS は、特定のヘッダー セットを想定しています。</span><span class="sxs-lookup"><span data-stu-id="1b727-113">PlatyPS expects a specific set of headers.</span></span>
- <span data-ttu-id="1b727-114">**入力型**ヘッダーと**出力型**ヘッダーには型が必要です。</span><span class="sxs-lookup"><span data-stu-id="1b727-114">The **Input type** and **Output type** headers must have a type.</span></span> <span data-ttu-id="1b727-115">コマンドレットが入力を受け取らない場合、または値を返さない場合は、値 `None` を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b727-115">If the cmdlet does not take input or return a value then use the value `None`.</span></span>
- <span data-ttu-id="1b727-116">フェンスされたコード ブロックは、[Examples](#structuring-examples) セクションでのみ許可されています。</span><span class="sxs-lookup"><span data-stu-id="1b727-116">Fenced code blocks are only allowed in the [Examples](#structuring-examples) section.</span></span>
- <span data-ttu-id="1b727-117">インライン コードの範囲は、任意の段落で使用できます。</span><span class="sxs-lookup"><span data-stu-id="1b727-117">Inline code spans can be used in any paragraph.</span></span>

## <a name="formatting-about_-files"></a><span data-ttu-id="1b727-118">About_ ファイルの書式設定</span><span class="sxs-lookup"><span data-stu-id="1b727-118">Formatting About_ files</span></span>

<span data-ttu-id="1b727-119">`About_*` ファイルは、PlatyPS ではなく [Pandoc][] によって処理されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1b727-119">`About_*` files are now processed by [Pandoc][], instead of PlatyPS.</span></span> <span data-ttu-id="1b727-120">`About_*` ファイルは、すべてのバージョンの PowerShell および発行ツールとの最大限の互換性が確保されるように書式設定されています。</span><span class="sxs-lookup"><span data-stu-id="1b727-120">`About_*` files are formatted for the best compatibility across all versions of PowerShell and with the publishing tools.</span></span>

<span data-ttu-id="1b727-121">基本的な書式設定に関するガイドライン:</span><span class="sxs-lookup"><span data-stu-id="1b727-121">Basic formatting guidelines:</span></span>

- <span data-ttu-id="1b727-122">行 は 80 文字に制限します</span><span class="sxs-lookup"><span data-stu-id="1b727-122">Limit lines to 80 characters</span></span>
- <span data-ttu-id="1b727-123">コード ブロックとテーブルについては、テキストへの変換中、Pandoc によってスペース 4 つ分だけインデントされるため、76 文字に制限されます</span><span class="sxs-lookup"><span data-stu-id="1b727-123">Code blocks and tables are limited to 76 characters because Pandoc indents these by four spaces during conversion to plain text</span></span>
- <span data-ttu-id="1b727-124">テーブルは 76 文字以内に収める必要があります</span><span class="sxs-lookup"><span data-stu-id="1b727-124">Tables need to fit within 76 characters</span></span>
  - <span data-ttu-id="1b727-125">セルのコンテンツが複数行にわたる場合は手動で折り返します</span><span class="sxs-lookup"><span data-stu-id="1b727-125">Manually wrap contents of cells across multiple lines</span></span>
  - <span data-ttu-id="1b727-126">行ごとに開始および終了 `|` 文字を使用します</span><span class="sxs-lookup"><span data-stu-id="1b727-126">Use opening and closing `|` characters on each line</span></span>
  - <span data-ttu-id="1b727-127">[about_Comparison_Operators][about-example] の作業例をご覧ください</span><span class="sxs-lookup"><span data-stu-id="1b727-127">See a working example in [about_Comparison_Operators][about-example]</span></span>
- <span data-ttu-id="1b727-128">使用できる Pandoc 特殊文字は `\`、`$`、および `<` です</span><span class="sxs-lookup"><span data-stu-id="1b727-128">Using Pandoc special characters `\`,`$`, and `<`</span></span>
  - <span data-ttu-id="1b727-129">ヘッダー内では、これらの文字は先頭の `\` 文字を使用してエスケープするか、バッククォート (`` ` ``) で囲む必要があります</span><span class="sxs-lookup"><span data-stu-id="1b727-129">Within a header - these characters must be escaped using a leading `\` character or enclosed in backticks (`` ` ``)</span></span>
  - <span data-ttu-id="1b727-130">段落内では、これらの文字はコード範囲内に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b727-130">Within a paragraph, these characters should be put into code spans.</span></span> <span data-ttu-id="1b727-131">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1b727-131">For example:</span></span>

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

## <a name="structuring-examples"></a><span data-ttu-id="1b727-132">examples の構造化</span><span class="sxs-lookup"><span data-stu-id="1b727-132">Structuring examples</span></span>

<span data-ttu-id="1b727-133">PlatyPS スキーマでは、**EXAMPLES** ヘッダーは H2 ヘッダーで、各 example は H3 ヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="1b727-133">In the PlatyPS schema, the **EXAMPLES** header is an H2 header and each example is an H3 header.</span></span>

<span data-ttu-id="1b727-134">example 内で、コード ブロックを段落で区切ることはスキーマで許可されていません。</span><span class="sxs-lookup"><span data-stu-id="1b727-134">Within an example, the schema does not allow code blocks to be separated by paragraphs.</span></span> <span data-ttu-id="1b727-135">サポートされているスキーマは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b727-135">The supported schema is:</span></span>

```
### Example #X title

0 or more paragraphs
1 or more code blocks
0 or more paragraphs.
```

<span data-ttu-id="1b727-136">各 example に数値を指定し、簡単なタイトルを追加します。</span><span class="sxs-lookup"><span data-stu-id="1b727-136">Number each example and add a brief title.</span></span>

<span data-ttu-id="1b727-137">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1b727-137">For example:</span></span>

### <a name="example-1-get-cmdlets-functions-and-aliases"></a><span data-ttu-id="1b727-138">例 1:コマンドレット、関数、およびエイリアスを取得する</span><span class="sxs-lookup"><span data-stu-id="1b727-138">Example 1: Get cmdlets, functions, and aliases</span></span>

<span data-ttu-id="1b727-139">このコマンドは、コンピューターにインストールされている PowerShell コマンドレット、関数、およびエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="1b727-139">This command gets the PowerShell cmdlets, functions, and aliases that are installed on the computer.</span></span>

```powershell
Get-Command
```

### <a name="example-2-get-commands-in-the-current-session"></a><span data-ttu-id="1b727-140">例 2:現在のセッションのコマンドを取得する</span><span class="sxs-lookup"><span data-stu-id="1b727-140">Example 2: Get commands in the current session</span></span>

```powershell
Get-Command -ListImported
```

## <a name="next-steps"></a><span data-ttu-id="1b727-141">次のステップ</span><span class="sxs-lookup"><span data-stu-id="1b727-141">Next steps</span></span>

[<span data-ttu-id="1b727-142">編集チェックリスト</span><span class="sxs-lookup"><span data-stu-id="1b727-142">Editorial checklist</span></span>](editorial-checklist.md)

<!-- link references -->
[PlatyPS]: https://github.com/powershell/platyps
[platyPS.schema.md]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[issue1806]: https://github.com/MicrosoftDocs/PowerShell-Docs/issues/1806
[about-example]: https://github.com/MicrosoftDocs/PowerShell-Docs/reference/5.1/Microsoft.PowerShell.Core/About/about_Comparison_Operators.md
[Pandoc]: https://pandoc.org
