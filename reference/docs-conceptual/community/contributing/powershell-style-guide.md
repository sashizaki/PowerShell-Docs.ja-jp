---
title: PowerShell ドキュメントのスタイル ガイド
description: この記事では、PowerShell ドキュメントを記述するためのスタイル規則について説明します。
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 964536c5195c3bb8abd98b5996a96fc7b9362489
ms.sourcegitcommit: c97dcf1e00ef540e7464c36c88f841474060044c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "79402579"
---
# <a name="powershell-docs-style-guide"></a><span data-ttu-id="07a59-103">PowerShell ドキュメントのスタイル ガイド</span><span class="sxs-lookup"><span data-stu-id="07a59-103">PowerShell-Docs style guide</span></span>

<span data-ttu-id="07a59-104">この記事では、PowerShell ドキュメントのコンテンツに固有のスタイル ガイダンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="07a59-104">This article provides style guidance specific to the PowerShell-Docs content.</span></span> <span data-ttu-id="07a59-105">これは、[概要](overview.md#get-started-writing-docs)に記載されている情報に基づいています。</span><span class="sxs-lookup"><span data-stu-id="07a59-105">This builds on the information outlined in the [Overview](overview.md#get-started-writing-docs).</span></span>

## <a name="product-terminology"></a><span data-ttu-id="07a59-106">製品に関する用語</span><span class="sxs-lookup"><span data-stu-id="07a59-106">Product Terminology</span></span>

<span data-ttu-id="07a59-107">PowerShell にはいくつかのバリエーションがあります。</span><span class="sxs-lookup"><span data-stu-id="07a59-107">There are several variants of PowerShell.</span></span>
<span data-ttu-id="07a59-108">次の表に、PowerShell を説明するときに使用される用語の一部について、その定義を示します。</span><span class="sxs-lookup"><span data-stu-id="07a59-108">This table defines some of the different terms used to discuss PowerShell.</span></span>

- <span data-ttu-id="07a59-109">**PowerShell** - これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="07a59-109">**PowerShell** - This is the default.</span></span> <span data-ttu-id="07a59-110">PowerShell 7 以降のすべての PowerShell の総称として使用されます。</span><span class="sxs-lookup"><span data-stu-id="07a59-110">We consider PowerShell 7 and beyond to be the one, true PowerShell going forward.</span></span>

- <span data-ttu-id="07a59-111">**PowerShell Core** - .NET Core 上で構築される PowerShell です。</span><span class="sxs-lookup"><span data-stu-id="07a59-111">**PowerShell Core** - PowerShell built on .NET Core.</span></span> <span data-ttu-id="07a59-112">**Core** という用語の使用は、Windows PowerShell と区別する必要がある場合にのみ限定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-112">Usage of the term **Core** should be limited to cases where it is necessary to differentiate it from Windows PowerShell.</span></span>

- <span data-ttu-id="07a59-113">**Windows PowerShell** - .NET Framework 上で構築される PowerShell です。</span><span class="sxs-lookup"><span data-stu-id="07a59-113">**Windows PowerShell** - PowerShell built on .NET Framework.</span></span> <span data-ttu-id="07a59-114">Windows PowerShell は Windows にのみ付属しており、完全な Framework が必要です。</span><span class="sxs-lookup"><span data-stu-id="07a59-114">Windows PowerShell ships only on Windows and requires the complete Framework.</span></span>

<span data-ttu-id="07a59-115">通常、ドキュメント内の "Windows PowerShell" は、"PowerShell" に読み替えることができます。</span><span class="sxs-lookup"><span data-stu-id="07a59-115">In general, references to "Windows PowerShell" in documentation can be changed to "PowerShell".</span></span>
<span data-ttu-id="07a59-116">Windows 固有のテクノロジについて説明されている場合は、"Windows PowerShell" を読み替えるべきでは**ありません**。</span><span class="sxs-lookup"><span data-stu-id="07a59-116">"Windows PowerShell" should **not** be changed when Windows-specific technology is being discussed.</span></span>

## <a name="markdown-specifics"></a><span data-ttu-id="07a59-117">Markdown の詳細</span><span class="sxs-lookup"><span data-stu-id="07a59-117">Markdown specifics</span></span>

<span data-ttu-id="07a59-118">Microsoft のドキュメントを構築する Microsoft Open Publishing System (OPS) では、[markdig][] を使用して Markdown ドキュメントが処理されます。</span><span class="sxs-lookup"><span data-stu-id="07a59-118">The Microsoft Open Publishing System (OPS) that builds our documentation uses [markdig][] to process the Markdown documents.</span></span> <span data-ttu-id="07a59-119">markdig では、最新の [CommonMark][] 仕様の規則に基づいてドキュメントが解析されます。</span><span class="sxs-lookup"><span data-stu-id="07a59-119">Markdig parses the documents based on the rules of the latest [CommonMark][] specification.</span></span>

<span data-ttu-id="07a59-120">新しい CommonMark 仕様では、いくつかの Markdown 要素の構築に関する規定が非常に厳密になっています。</span><span class="sxs-lookup"><span data-stu-id="07a59-120">The new CommonMark spec is much stricter about the construction of some Markdown elements.</span></span> <span data-ttu-id="07a59-121">このドキュメントの細部に、細心の注意を払ってください。</span><span class="sxs-lookup"><span data-stu-id="07a59-121">Pay close attention to the details provided in this document.</span></span>

### <a name="blank-lines-spaces-and-tabs"></a><span data-ttu-id="07a59-122">空白行、スペース、およびタブ</span><span class="sxs-lookup"><span data-stu-id="07a59-122">Blank lines, spaces, and tabs</span></span>

<span data-ttu-id="07a59-123">重複する空白行を削除します。</span><span class="sxs-lookup"><span data-stu-id="07a59-123">Remove duplicate blank lines.</span></span> <span data-ttu-id="07a59-124">複数の空白行は HTML では単一の空白行として表示されるため、複数の空白行には目的がありません。</span><span class="sxs-lookup"><span data-stu-id="07a59-124">Multiple blank lines render as a single blank line in HTML so there is not purpose for multiple blank lines.</span></span>

<span data-ttu-id="07a59-125">空白行は、Markdown 内のブロックが終わることも示します。</span><span class="sxs-lookup"><span data-stu-id="07a59-125">Blank lines also signal the end of a block in Markdown.</span></span> <span data-ttu-id="07a59-126">異なる種類の Markdown ブロックの間 (段落とリストの間や段落とヘッダーの間など) には、単一の空白行が必要です。</span><span class="sxs-lookup"><span data-stu-id="07a59-126">There should be a single blank between Markdown blocks of different types (for example, between a paragraph and a list or header).</span></span>

> [!NOTE]
> <span data-ttu-id="07a59-127">Markdown では、スペースが重要です。</span><span class="sxs-lookup"><span data-stu-id="07a59-127">Spacing is significant in Markdown.</span></span> <span data-ttu-id="07a59-128">常にハード タブではなくスペースを使用してください。</span><span class="sxs-lookup"><span data-stu-id="07a59-128">Always uses spaces instead of hard tabs.</span></span> <span data-ttu-id="07a59-129">行の末尾の余分なスペースを削除してください。</span><span class="sxs-lookup"><span data-stu-id="07a59-129">Remove extra spaces at the end of lines.</span></span>

### <a name="titles-and-headings"></a><span data-ttu-id="07a59-130">タイトルと見出し</span><span class="sxs-lookup"><span data-stu-id="07a59-130">Titles and headings</span></span>

<span data-ttu-id="07a59-131">[ATX 見出し][atx]のみを使用します (`=` または `-` スタイルのヘッダーではなく # スタイルにします)。</span><span class="sxs-lookup"><span data-stu-id="07a59-131">Only use [ATX headings][atx] (# style, as opposed to `=` or `-` style headers).</span></span>

- <span data-ttu-id="07a59-132">文の先頭で大文字を使用する - 固有名詞、タイトル、ヘッダーの 1 文字目のみ大文字にします</span><span class="sxs-lookup"><span data-stu-id="07a59-132">Use sentence case - only proper nouns and the first letter of a title or header should be capitalized</span></span>
- <span data-ttu-id="07a59-133">`#` と見出しの最初の文字の間には単一のスペースが必要</span><span class="sxs-lookup"><span data-stu-id="07a59-133">There must be a single space between the `#` and the first letter of the heading</span></span>
- <span data-ttu-id="07a59-134">見出しの上下は単一の空白行にする</span><span class="sxs-lookup"><span data-stu-id="07a59-134">Headings should be surrounded by a single blank line</span></span>
- <span data-ttu-id="07a59-135">ドキュメントごとの H1 は 1 つのみにする</span><span class="sxs-lookup"><span data-stu-id="07a59-135">Only one H1 per document</span></span>
- <span data-ttu-id="07a59-136">ヘッダーのレベルは 1 つずつ増分する。</span><span class="sxs-lookup"><span data-stu-id="07a59-136">Header levels should increment by one.</span></span> <span data-ttu-id="07a59-137">レベルをスキップしないでください</span><span class="sxs-lookup"><span data-stu-id="07a59-137">Do not skip levels</span></span>
- <span data-ttu-id="07a59-138">ヘッダーに太字またはその他のマークアップを使用しない</span><span class="sxs-lookup"><span data-stu-id="07a59-138">Do not use bold or other markup in headers</span></span>

### <a name="limit-line-length-to-100-characters"></a><span data-ttu-id="07a59-139">行の長さを 100 文字に制限する</span><span class="sxs-lookup"><span data-stu-id="07a59-139">Limit line length to 100 characters</span></span>

<span data-ttu-id="07a59-140">これは、概念記事とコマンドレット リファレンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="07a59-140">This applies to conceptual articles and cmdlet reference.</span></span> <span data-ttu-id="07a59-141">About_topics の長さは 80 文字に制限されます。</span><span class="sxs-lookup"><span data-stu-id="07a59-141">About_topics are limited to 80 characters.</span></span>
<span data-ttu-id="07a59-142">行の長さを制限することで、git diff と履歴が読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="07a59-142">Limiting the line length improves the readability git diffs and history.</span></span> <span data-ttu-id="07a59-143">さらに、他の執筆者が投稿を簡単に行えるようにします。</span><span class="sxs-lookup"><span data-stu-id="07a59-143">It also makes it easier for other writers to make contributions.</span></span>

<span data-ttu-id="07a59-144">Visual Studio Code の [Reflow Markdown][reflow] 拡張機能を使用すると、規定の行の長さに合うように段落が簡単にリフロ―されます。</span><span class="sxs-lookup"><span data-stu-id="07a59-144">Use the [Reflow Markdown][reflow] extension in Visual Studio Code to easily reflow paragraphs to fit the prescribed line length.</span></span>

### <a name="lists"></a><span data-ttu-id="07a59-145">リスト</span><span class="sxs-lookup"><span data-stu-id="07a59-145">Lists</span></span>

<span data-ttu-id="07a59-146">リストに複数の文または段落が含まれている場合は、リストではなくサブレベルのヘッダーを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="07a59-146">If your list contains multiple sentences or paragraphs, consider using a sub-level header rather than a list.</span></span>

<span data-ttu-id="07a59-147">リストの上下は単一の空白行にします。</span><span class="sxs-lookup"><span data-stu-id="07a59-147">List should be surrounded by a single blank line.</span></span>

#### <a name="unordered-lists"></a><span data-ttu-id="07a59-148">箇条書きリスト</span><span class="sxs-lookup"><span data-stu-id="07a59-148">Unordered lists</span></span>

<span data-ttu-id="07a59-149">リスト項目に複数の文が含まれていない限り、リスト項目にはピリオドをつけないでください。</span><span class="sxs-lookup"><span data-stu-id="07a59-149">Do not end list items with a period unless they contain multiple sentences.</span></span> <span data-ttu-id="07a59-150">リスト項目の箇条書き記号には、ハイフン文字 (`-`) を使用します。</span><span class="sxs-lookup"><span data-stu-id="07a59-150">Use the hyphen character (`-`) for list item bullets.</span></span> <span data-ttu-id="07a59-151">これにより、アスタリスク [`*`] を使用する、太字または斜体のマークアップとの混同を回避できます。</span><span class="sxs-lookup"><span data-stu-id="07a59-151">This avoids confusion with bold or italic markup that uses the asterisk [`*`].</span></span> <span data-ttu-id="07a59-152">段落またはその他の要素を箇条書き項目の下に含めるには、改行を挿入し、インデントを箇条書き記号の後ろの最初の文字に揃えます。</span><span class="sxs-lookup"><span data-stu-id="07a59-152">To include a paragraph or other elements under a bullet item, insert a line break and align indentation with the first character after the bullet.</span></span>

<span data-ttu-id="07a59-153">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="07a59-153">For example:</span></span>

```markdown
This is a list that contain sub-elements under a bullet item.

- First bullet item

  Sentence explaining the first bullet.

  - Sub-bullet item

    Sentence explaining the sub-bullet.

- Second bullet item
- Third bullet item
```

<span data-ttu-id="07a59-154">これは、箇条書き項目の下にサブ要素が含まれているリストです。</span><span class="sxs-lookup"><span data-stu-id="07a59-154">This is a list that contains sub-elements under a bullet item.</span></span>

- <span data-ttu-id="07a59-155">最初の箇条書き項目</span><span class="sxs-lookup"><span data-stu-id="07a59-155">First bullet item</span></span>

  <span data-ttu-id="07a59-156">最初の箇条書きの内容文。</span><span class="sxs-lookup"><span data-stu-id="07a59-156">Sentence explaining the first bullet.</span></span>

  - <span data-ttu-id="07a59-157">サブ箇条書き項目</span><span class="sxs-lookup"><span data-stu-id="07a59-157">Sub-bullet item</span></span>

    <span data-ttu-id="07a59-158">サブ箇条書きの内容文。</span><span class="sxs-lookup"><span data-stu-id="07a59-158">Sentence explaining the sub-bullet.</span></span>

- <span data-ttu-id="07a59-159">2 番目の箇条書き項目</span><span class="sxs-lookup"><span data-stu-id="07a59-159">Second bullet item</span></span>
- <span data-ttu-id="07a59-160">3 番目の箇条書き項目</span><span class="sxs-lookup"><span data-stu-id="07a59-160">Third bullet item</span></span>

#### <a name="ordered-lists"></a><span data-ttu-id="07a59-161">番号付きリスト</span><span class="sxs-lookup"><span data-stu-id="07a59-161">Ordered lists</span></span>

<span data-ttu-id="07a59-162">段落またはその他の要素を番号付き項目の下に含めるには、インデントを項目番号の後ろの最初の文字に揃えます。</span><span class="sxs-lookup"><span data-stu-id="07a59-162">To include a paragraph or other elements under a numbered item, align indentation with the first character after the item number.</span></span> <span data-ttu-id="07a59-163">番号付きリストのすべての項目では、項目ごとに増分される番号ではなく、番号 `1.` を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-163">All items in a numbered listed should use the number `1.` rather than incrementing each item.</span></span> <span data-ttu-id="07a59-164">この値は、Markdown によって自動的に増分されて表示されます。</span><span class="sxs-lookup"><span data-stu-id="07a59-164">Markdown rendering increments the value automatically.</span></span> <span data-ttu-id="07a59-165">これにより、項目を簡単に並べ替えることができ、下位コンテンツのインデントが統一されます。</span><span class="sxs-lookup"><span data-stu-id="07a59-165">This makes reordering items easier and standardizes the indentation of subordinate content.</span></span>

<span data-ttu-id="07a59-166">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="07a59-166">For example:</span></span>

```markdown
1. For the first element, insert a single space after the 1. Long sentences should be
   wrapped to the next line and must line up with the first character after the numbered
   list marker.

   To include a second element (like this one), insert a line break after the first
   and align indentations. The indentation of the second element must line up with
   the first character after the numbered list marker. For single digit items, like
   this one, you indent to column 4. For double digits items, for example item number
   10, you indent to column 5.

1. The next numbered item starts here.
```

<span data-ttu-id="07a59-167">結果の Markdown は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="07a59-167">The resulting Markdown is rendered as follows:</span></span>

1. <span data-ttu-id="07a59-168">最初の要素では、1. の後ろに単一のスペースを挿入します。</span><span class="sxs-lookup"><span data-stu-id="07a59-168">For the first element, insert a single space after the 1.</span></span> <span data-ttu-id="07a59-169">長い文は次の行に折り返す必要があり、次の行の先頭は番号付きリスト マーカーの後ろの最初の文字と揃える必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-169">Long sentences should be wrapped to the next line and must line up with the first character after the numbered list marker.</span></span>

   <span data-ttu-id="07a59-170">(この例のように) 2 つ目の要素を含めるには、1 つ目の要素の後に改行を挿入し、インデントを合わせます。</span><span class="sxs-lookup"><span data-stu-id="07a59-170">To include a second element (like this one), insert a line break after the first and align indentations.</span></span> <span data-ttu-id="07a59-171">2 つ目の要素のインデントは、番号付きリスト マーカーの後ろの最初の文字と揃える必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-171">The indentation of the second element must line up with the first character after the numbered list marker.</span></span> <span data-ttu-id="07a59-172">このような 1 桁の番号の項目では、列 4 にインデントします。</span><span class="sxs-lookup"><span data-stu-id="07a59-172">For single digit items, like this one, you indent to column 4.</span></span> <span data-ttu-id="07a59-173">2 桁の番号の項目 (項目番号 10 など) では、列 5 にインデントします。</span><span class="sxs-lookup"><span data-stu-id="07a59-173">For double digits items, for example item number 10, you indent to column 5.</span></span>

1. <span data-ttu-id="07a59-174">次の番号付き項目は、ここから始まります。</span><span class="sxs-lookup"><span data-stu-id="07a59-174">The next numbered item starts here.</span></span>

### <a name="formatting-command-syntax-elements"></a><span data-ttu-id="07a59-175">コマンド構文要素の書式設定</span><span class="sxs-lookup"><span data-stu-id="07a59-175">Formatting command syntax elements</span></span>

- <span data-ttu-id="07a59-176">コマンドレットとパラメーターには常に完全名を使用します。</span><span class="sxs-lookup"><span data-stu-id="07a59-176">Always use the full name for cmdlets and parameters.</span></span> <span data-ttu-id="07a59-177">別名について具体的に説明する場合を除いて、別名の使用は避けてください。</span><span class="sxs-lookup"><span data-stu-id="07a59-177">Avoid using aliases unless you are specifically demonstrating the alias.</span></span>

- <span data-ttu-id="07a59-178">段落内では、言語キーワード、コマンドレット名、変数、およびファイル パスをバックティック (`` ` ``) 文字で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-178">Within a paragraph, language keywords, cmdlet names, variables, and file paths should be wrapped in backtick (`` ` ``) characters.</span></span> <span data-ttu-id="07a59-179">プロパティ、パラメーター、およびクラス名は、**太字**にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-179">Property, parameter, and class names should be **bold**.</span></span>

  <span data-ttu-id="07a59-180">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="07a59-180">For example:</span></span>

  ~~~markdown
  The following code uses `Get-ChildItem` to list the contents of `C:\Windows` and assigns
  the output to the `$files` variable.

  ```powershell
  $files = Get-ChildItem C:\Windows
  ```
  ~~~

- <span data-ttu-id="07a59-181">パラメーターを名前で参照する場合は、名前を**太字**にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-181">When referring to a parameter by name, the name should be **bold**.</span></span> <span data-ttu-id="07a59-182">ハイフン プレフィックス付きのパラメーターの使用を示す場合は、パラメーターをバックティックで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-182">When illustrating the use of a parameter with the hyphen prefix, the parameter should be wrapped in backticks.</span></span> <span data-ttu-id="07a59-183">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="07a59-183">For example:</span></span>

  ```markdown
  The parameter's name is **Name**, but it is typed as `-Name` when used on the command
  line as a parameter.
  ```

- <span data-ttu-id="07a59-184">外部コマンド (EXE やスクリプトなど) を参照する場合は、コマンド名を太字かつすべて小文字 (文の先頭にある場合は大文字) にし、適切なファイル拡張子を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-184">When referring to external commands (EXEs, scripts, etc.), the command name should be bold, all lowercase (or capitalized if at the beginning of a sentence), and include the appropriate file extension.</span></span> <span data-ttu-id="07a59-185">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="07a59-185">For example:</span></span>

  ```markdown
  For example, on Windows systems, you can use the `net start` and `net stop` commands
  to start and stop a service. **Sc.exe** is another service control tool for Windows.
  That name does not fit into the naming pattern for the **net.exe** service commands.
  ```

- <span data-ttu-id="07a59-186">外部コマンドの使用例を示す場合は、例をバックティックで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-186">When showing example usage of an external command, the example should be wrapped in backticks.</span></span>
  <span data-ttu-id="07a59-187">別名と名前が競合する場合は、コマンド例にファイル拡張子を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-187">When there is a name collisions with an alias you must include the file extension in the command example.</span></span> <span data-ttu-id="07a59-188">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="07a59-188">For example:</span></span>

  ```markdown
  To start the spooler service on a remote computer named DC01, you type `sc.exe \\DC01 start spooler`.
  ```

- <span data-ttu-id="07a59-189">(参照コンテンツではなく) 概念記事を記述する場合は、最初に出現するコマンドレットの名前に、コマンドレットのドキュメントにリンクされたハイパーリンクを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-189">When writing a conceptual article (as opposed to reference content), the first instance of a cmdlet name should be hyperlinked to the cmdlet documentation.</span></span> <span data-ttu-id="07a59-190">ハイパーリンクの角かっこ内で、バックティック、太字、またはその他のマークアップを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="07a59-190">Do not use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>

  <span data-ttu-id="07a59-191">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="07a59-191">For example:</span></span>

  ```markdown
  This [Write-Host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) cmdlet
  uses the **Object** parameter to ...
  ```

  <span data-ttu-id="07a59-192">詳細については、この記事の「[ハイパーリンク](#hyperlinks)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="07a59-192">For more information, see [Hyperlinks](#hyperlinks) section of this article.</span></span>

### <a name="images"></a><span data-ttu-id="07a59-193">イメージ</span><span class="sxs-lookup"><span data-stu-id="07a59-193">Images</span></span>

<span data-ttu-id="07a59-194">画像を含める構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="07a59-194">The syntax to include an image is:</span></span>

```markdown
![[alt text]](<folderPath>)

Example:
![Introduction](./media/overview/Introduction.png)
```

<span data-ttu-id="07a59-195">`alt text` は画像の簡単な説明であり、`<folder path>` は画像の相対パスです。</span><span class="sxs-lookup"><span data-stu-id="07a59-195">Where `alt text` is a brief description of the image and `<folder path>` is a relative path to the image.</span></span> <span data-ttu-id="07a59-196">代替テキストは、視覚障碍がある読者のために必要です。</span><span class="sxs-lookup"><span data-stu-id="07a59-196">Alternate text is required for screen readers for the visually impaired.</span></span> <span data-ttu-id="07a59-197">サイトのバグで画像を表示できない場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="07a59-197">It is also useful in case there is a site bug where the image cannot be rendered.</span></span>

<span data-ttu-id="07a59-198">画像は、記事が含まれているフォルダー内の `media/<article-name>` フォルダーに格納されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-198">Images should be stored in a `media/<article-name>` folder within the folder containing the article.</span></span>
<span data-ttu-id="07a59-199">複数の記事で画像を共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="07a59-199">Images should not be shared between articles.</span></span> <span data-ttu-id="07a59-200">`media` フォルダーの下に、記事のファイル名と一致するフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="07a59-200">Create a folder that matches the filename of your article under the `media` folder.</span></span> <span data-ttu-id="07a59-201">記事のための画像を、その新しいフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="07a59-201">Copy the images for that article to that new folder.</span></span> <span data-ttu-id="07a59-202">画像が複数の記事で使用される場合は、各画像フォルダーにその画像ファイルのコピーが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-202">If an image is used by multiple articles, each image folder must have a copy of that image file.</span></span> <span data-ttu-id="07a59-203">ある記事内の画像の変更が他の記事に影響するのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="07a59-203">This practice prevents a change to an image in one article affecting another article.</span></span>

<span data-ttu-id="07a59-204">次の種類の画像ファイルがサポートされています。`*.png`、`*.gif`、`*.jpeg`、`*.jpg`、`*.svg`</span><span class="sxs-lookup"><span data-stu-id="07a59-204">The following image file types are supported: `*.png`, `*.gif`, `*.jpeg`, `*.jpg`, `*.svg`</span></span>

### <a name="markdown-extensions-supported-by-open-publishing"></a><span data-ttu-id="07a59-205">Open Publishing でサポートされる Markdown 拡張機能</span><span class="sxs-lookup"><span data-stu-id="07a59-205">Markdown extensions supported by Open Publishing</span></span>

<span data-ttu-id="07a59-206">[Microsoft Docs Authoring Pack](/contribute/how-to-write-docs-auth-pack) には、Microsoft のパブリッシング システム固有の機能をサポートするツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="07a59-206">The [Microsoft Docs Authoring Pack](/contribute/how-to-write-docs-auth-pack) contains tools that support features unique to our publishing system.</span></span> <span data-ttu-id="07a59-207">アラートは、docs.microsoft.com に表示されるブロック引用を、その内容の重要性を示す色とアイコンを使用して作成する Markdown 拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="07a59-207">Alerts are a Markdown extension to create block quotes that render on docs.microsoft.com with colors and icons that indicate the significance of the content.</span></span> <span data-ttu-id="07a59-208">次のアラートの種類がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="07a59-208">The following alert types are supported:</span></span>

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

<span data-ttu-id="07a59-209">これらのアラートは、docs.microsoft.com に次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="07a59-209">These alerts look like this on docs.microsoft.com:</span></span>

> [!NOTE]
> <span data-ttu-id="07a59-210">流し読みする場合でも、ユーザーが注目する必要がある情報です。</span><span class="sxs-lookup"><span data-stu-id="07a59-210">Information the user should notice even if skimming.</span></span>

> [!TIP]
> <span data-ttu-id="07a59-211">ユーザーの成果を向上させるために役立つオプションの情報です。</span><span class="sxs-lookup"><span data-stu-id="07a59-211">Optional information to help a user be more successful.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="07a59-212">ユーザーが目的を達成するために必要な、非常に重要な情報です。</span><span class="sxs-lookup"><span data-stu-id="07a59-212">Essential information required for user success.</span></span>

> [!CAUTION]
> <span data-ttu-id="07a59-213">アクションの考えられる悪影響です。</span><span class="sxs-lookup"><span data-stu-id="07a59-213">Negative potential consequences of an action.</span></span>

> [!WARNING]
> <span data-ttu-id="07a59-214">アクションの避けられない危険な影響です。</span><span class="sxs-lookup"><span data-stu-id="07a59-214">Dangerous certain consequences of an action.</span></span>

## <a name="hyperlinks"></a><span data-ttu-id="07a59-215">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="07a59-215">Hyperlinks</span></span>

- <span data-ttu-id="07a59-216">URL そのものの使用は避けてください。</span><span class="sxs-lookup"><span data-stu-id="07a59-216">Avoid using bare URLs.</span></span> <span data-ttu-id="07a59-217">リンクには Markdown 構文 `[friendlyname](url-or-path)` を使用する必要があります</span><span class="sxs-lookup"><span data-stu-id="07a59-217">Links should use Markdown syntax `[friendlyname](url-or-path)`</span></span>
- <span data-ttu-id="07a59-218">必要に応じて URL そのものを使用できますが、バックティックで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-218">Bare URLs may be used when necessary, but should be enclosed in backticks.</span></span> <span data-ttu-id="07a59-219">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="07a59-219">For example:</span></span>

  ```markdown
  By default, if you do not specify this parameter, the DMTF standard resource URI
  `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.
  ```

- <span data-ttu-id="07a59-220">可能な場合は、URL リンクを HTTPS にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-220">URL links should be HTTPS when possible.</span></span>
- <span data-ttu-id="07a59-221">リンクにはフレンドリ名が必要です。通常はリンク先のトピックのタイトルを使用します。</span><span class="sxs-lookup"><span data-stu-id="07a59-221">Links must have a friendly name, usually the title of the linked topic</span></span>
- <span data-ttu-id="07a59-222">下部にある「関連リンク」セクションのすべての項目は、ハイパーリンクにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-222">All items in the "related links" section at the bottom should be hyperlinked.</span></span>
- <span data-ttu-id="07a59-223">ハイパーリンクの角かっこ内で、バックティック、太字、またはその他のマークアップを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="07a59-223">Do not use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>

### <a name="linking-to-other-content"></a><span data-ttu-id="07a59-224">他のコンテンツへのリンク</span><span class="sxs-lookup"><span data-stu-id="07a59-224">Linking to other content</span></span>

<span data-ttu-id="07a59-225">パブリッシング システムでサポートされるハイパーリンクには、URL リンクとファイル リンクの 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-225">There are two types of hyperlinks supported by the publishing system: URLs and file links.</span></span>

<span data-ttu-id="07a59-226">URL リンクでは、docs.microsoft.com のルートに対する相対的な URL パスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="07a59-226">A URL link can be a URL path that is relative to the root of docs.microsoft.com.</span></span> <span data-ttu-id="07a59-227">または、完全な URL 構文を含む絶対 URL を使用することもできます</span><span class="sxs-lookup"><span data-stu-id="07a59-227">Or an absolute URL that include the full URL syntax.</span></span> <span data-ttu-id="07a59-228">(例: `https:/github.com/MicrosoftDocs/PowerShell-Docs`)。</span><span class="sxs-lookup"><span data-stu-id="07a59-228">(For example: `https:/github.com/MicrosoftDocs/PowerShell-Docs`)</span></span>

- <span data-ttu-id="07a59-229">PowerShell ドキュメント以外のコンテンツにリンクする場合、または PowerShell ドキュメント内のコマンドレット リファレンスと概念記事の間にリンクを設定する場合は、URL リンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="07a59-229">Use URL links when linking to content outside of PowerShell-Docs or between cmdlet reference and conceptual articles within PowerShell-docs.</span></span>
- <span data-ttu-id="07a59-230">相対リンクを設定する最も簡単な方法は、ブラウザーから URL をコピーした後、Markdown に貼り付ける値から `https://docs.microsoft.com/en-us` を削除することです。</span><span class="sxs-lookup"><span data-stu-id="07a59-230">The simplest way to link create a relative link is to copy the URL from your browser then remove `https://docs.microsoft.com/en-us` from the value you paste into markdown.</span></span>
   - <span data-ttu-id="07a59-231">URL には Microsoft プロパティのロケールを含めないでください (例:</span><span class="sxs-lookup"><span data-stu-id="07a59-231">Do not include locales in URLs on Microsoft properties (eg.</span></span> <span data-ttu-id="07a59-232">URL から "/en-us" を削除します)。</span><span class="sxs-lookup"><span data-stu-id="07a59-232">remove "/en-us" from URL).</span></span>
- <span data-ttu-id="07a59-233">ターゲット サイトで無効な場合を除き、外部 Web サイトへのすべての URL には HTTPS を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-233">All URLs to external websites should use HTTPS unless that is not valid for the target site.</span></span>

<span data-ttu-id="07a59-234">ある参照記事から別の参照記事へのリンク、またはある概念記事から別の概念記事へのリンクを設定する場合は、ファイル リンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="07a59-234">A file link is used to link from one reference article to another, or from one conceptual article to another.</span></span> <span data-ttu-id="07a59-235">PowerShell の特定のバージョン用の参照記事にリンクする必要がある場合は、URL リンクを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-235">If you need to link to a reference article for a specific version of PowerShell, then you need to use a URL link.</span></span>

- <span data-ttu-id="07a59-236">ファイル リンクには、相対ファイル パスを含めます (例: `../folder/file.md`)</span><span class="sxs-lookup"><span data-stu-id="07a59-236">File links contain a relative file path (for example: `../folder/file.md`)</span></span>
- <span data-ttu-id="07a59-237">すべてのファイル パスにスラッシュ (`/`) 文字を使用します</span><span class="sxs-lookup"><span data-stu-id="07a59-237">All file paths use forward-slash (`/`) characters</span></span>

## <a name="formatting-code-samples"></a><span data-ttu-id="07a59-238">サンプル コードの書式設定</span><span class="sxs-lookup"><span data-stu-id="07a59-238">Formatting code samples</span></span>

<span data-ttu-id="07a59-239">Markdown では、次の 2 つの異なるコード スタイルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="07a59-239">Markdown supports two different code styles:</span></span>

- <span data-ttu-id="07a59-240">コード スパン (インライン) - 単一のバックティック (`` ` ``) 文字でマークされます。</span><span class="sxs-lookup"><span data-stu-id="07a59-240">Code spans (inline) - marked by a single backtick (`` ` ``) character.</span></span> <span data-ttu-id="07a59-241">スタンドアロン ブロックとしてではなく、段落内で使用されます。</span><span class="sxs-lookup"><span data-stu-id="07a59-241">Used within a paragraph rather than as a standalone block.</span></span>
- <span data-ttu-id="07a59-242">コード ブロック - トリプル バックティック (`` ``` ``) 文字列で囲まれた複数行のまとまりです。</span><span class="sxs-lookup"><span data-stu-id="07a59-242">Code blocks - a multi-line block surrounded by triple-backtick (`` ``` ``) strings.</span></span> <span data-ttu-id="07a59-243">コード ブロックでは、バックティックの後ろに言語ラベルを付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="07a59-243">Code blocks may also have a language label following the backticks.</span></span> <span data-ttu-id="07a59-244">言語ラベルを使用して、構文でコード ブロックの内容を強調できます。</span><span class="sxs-lookup"><span data-stu-id="07a59-244">The language label enables syntax highlighting for the contents of the code block.</span></span>

### <a name="using-code-blocks"></a><span data-ttu-id="07a59-245">コード ブロックの使用</span><span class="sxs-lookup"><span data-stu-id="07a59-245">Using code blocks</span></span>

<span data-ttu-id="07a59-246">Markdown では、コード ブロックであることを示すためにインデントすることができますが、このパターンは問題になる可能性があるため、回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-246">Markdown allows for indentation to signify a code block, but this pattern can be problematic and should be avoided.</span></span> <span data-ttu-id="07a59-247">すべてのコード ブロックは、コード フェンスに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-247">All code blocks should be contained in a code fence.</span></span> <span data-ttu-id="07a59-248">コード フェンスは、トリプルバックティック (`` ``` ``) 文字列で囲まれたコードのまとまりです。</span><span class="sxs-lookup"><span data-stu-id="07a59-248">A code fence is a block of code surrounded by triple-backtick (`` ``` ``) strings.</span></span> <span data-ttu-id="07a59-249">コード フェンス マーカーは、サンプル コードの前と後ろの専用の行に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-249">The code fence markers must be on their own line before and after the code sample.</span></span> <span data-ttu-id="07a59-250">コード ブロックの開始を示すマーカーには、言語ラベルを含めることができます (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="07a59-250">The marker at the start of the code block may have an optional language label.</span></span> <span data-ttu-id="07a59-251">Microsoft の Open Publishing System (OPS) では、言語ラベルを使用した構文の強調機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="07a59-251">Microsoft's Open Publishing System (OPS) uses the language label to support the syntax highlighting feature.</span></span>

<span data-ttu-id="07a59-252">OPS では、コード ブロックの内容をクリップボードにコピーする **[コピー]** ボタンも追加されます。</span><span class="sxs-lookup"><span data-stu-id="07a59-252">OPS also adds a **Copy** button that copies the contents of the code block to the clipboard.</span></span> <span data-ttu-id="07a59-253">これにより、コード例をテストするためのスクリプトにコードを簡単に貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="07a59-253">This allows you to quickly paste the code into a script for testing the code example.</span></span> <span data-ttu-id="07a59-254">ただし、ドキュメントのすべての例が実行されることを目的としているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="07a59-254">However, not all examples in our documentation are intended to be run.</span></span> <span data-ttu-id="07a59-255">一部のコード ブロックは、PowerShell の概念を簡単に説明するものです。</span><span class="sxs-lookup"><span data-stu-id="07a59-255">Some code blocks are simple illustrations of a PowerShell concept.</span></span>

<span data-ttu-id="07a59-256">Microsoft のドキュメントでは、次の 2 種類のコード ブロックが使用されています。</span><span class="sxs-lookup"><span data-stu-id="07a59-256">There are two types code blocks used in our documentation:</span></span>

1. <span data-ttu-id="07a59-257">説明用の例</span><span class="sxs-lookup"><span data-stu-id="07a59-257">Illustrative examples</span></span>
2. <span data-ttu-id="07a59-258">実行可能な例</span><span class="sxs-lookup"><span data-stu-id="07a59-258">Executable examples</span></span>

### <a name="syntax-code-blocks"></a><span data-ttu-id="07a59-259">構文のコード ブロック</span><span class="sxs-lookup"><span data-stu-id="07a59-259">Syntax code blocks</span></span>

<span data-ttu-id="07a59-260">次の例は、`Get-Command` コマンドレットで使用できるすべてのパラメーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="07a59-260">This example illustrates all the possible parameters of the `Get-Command` cmdlet.</span></span>

~~~markdown
```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
  [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax] [-ShowCommandInfo]
  [[-ArgumentList] <Object[]>] [-All] [-ListImported] [-ParameterName <String[]>]
  [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```
~~~

<span data-ttu-id="07a59-261">次の例は、`for` ステートメントについて、一般的な用語で説明しています。</span><span class="sxs-lookup"><span data-stu-id="07a59-261">This example describes the `for` statement in generalized terms:</span></span>

~~~markdown
```
for (<init>; <condition>; <repeat>)
{<statement list>}
```
~~~

### <a name="illustrative-examples"></a><span data-ttu-id="07a59-262">説明用の例</span><span class="sxs-lookup"><span data-stu-id="07a59-262">Illustrative examples</span></span>

<span data-ttu-id="07a59-263">説明用の例は、PowerShell の概念を説明するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="07a59-263">Illustrative examples are used to explain a PowerShell concept.</span></span> <span data-ttu-id="07a59-264">これらは、クリップボードにコピーして実行するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="07a59-264">They are not meant to be copied to the clipboard for execution.</span></span> <span data-ttu-id="07a59-265">これらが最も一般的に使用されるのは、簡単に入力できる単純な例としてです。</span><span class="sxs-lookup"><span data-stu-id="07a59-265">These are most commonly used for simple examples that are easy to type.</span></span>
<span data-ttu-id="07a59-266">また、コマンドの構文を示す構文の例としても使用されます。</span><span class="sxs-lookup"><span data-stu-id="07a59-266">They are also used for syntax examples where you are illustrating the syntax of a command.</span></span> <span data-ttu-id="07a59-267">説明されているコマンドからの出力例がコード ブロックに含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-267">The code block may contain example output from the command being illustrated.</span></span>

<span data-ttu-id="07a59-268">PowerShell の比較演算子の簡単な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="07a59-268">Here is a simple example illustrating a PowerShell comparison operators:</span></span>

~~~markdown
```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS>  1,2,3 -eq 2
2

PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```
~~~

<span data-ttu-id="07a59-269">この例では PowerShell プロンプトが簡略化され、結果の出力が示されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="07a59-269">Note that this example has the simplified PowerShell prompt and shows the resulting output.</span></span> <span data-ttu-id="07a59-270">この例では、読者がこの例をコピーして実行することは想定されていません。</span><span class="sxs-lookup"><span data-stu-id="07a59-270">In this case, we don't intend the reader to copy and run this example.</span></span>

### <a name="executable-examples"></a><span data-ttu-id="07a59-271">実行可能な例</span><span class="sxs-lookup"><span data-stu-id="07a59-271">Executable examples</span></span>

<span data-ttu-id="07a59-272">より複雑な例または、コピーして実行するために役立つ例では、次のブロックスタイルのマークアップを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-272">More complex examples or examples that are intended to be useful to copy and execute should use the following block-style markup:</span></span>

~~~markdown
```powershell
<PowerShell code goes here>
```
~~~

<span data-ttu-id="07a59-273">構文の強調を防ぐために、PowerShell コマンドによって表示される出力を **Output** コード ブロックに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-273">The output displayed by PowerShell commands should be enclosed in an **Output** code block to prevent syntax highlighting.</span></span> <span data-ttu-id="07a59-274">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="07a59-274">For example:</span></span>

~~~markdown
```powershell
Get-Command -Module Microsoft.PowerShell.Security
```

```Output
CommandType  Name                        Version    Source
-----------  ----                        -------    ------
Cmdlet       ConvertFrom-SecureString    3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       ConvertTo-SecureString      3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-Acl                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-AuthenticodeSignature   3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-CmsMessage              3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-Credential              3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-ExecutionPolicy         3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-PfxCertificate          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       New-FileCatalog             3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Protect-CmsMessage          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-Acl                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-AuthenticodeSignature   3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-ExecutionPolicy         3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Test-FileCatalog            3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Unprotect-CmsMessage        3.0.0.0    Microsoft.PowerShell.Security
```
~~~

<span data-ttu-id="07a59-275">**Output** コード ラベルは、構文強調システムでサポートされている公式の "言語" ではありません。</span><span class="sxs-lookup"><span data-stu-id="07a59-275">The **Output** code label is not an official "language" supported by the syntax highlighting system.</span></span>
<span data-ttu-id="07a59-276">ただし、このラベルが有用なのは、これを使用すると、OPS によって、Web ページ上のコード ボックス フレームに "Output" ラベルが追加されるためです。</span><span class="sxs-lookup"><span data-stu-id="07a59-276">However, this label is useful because OPS adds the "Output" label to the code box frame on the web page.</span></span> <span data-ttu-id="07a59-277">"Output" コード ボックスでは、構文の強調は行われません。</span><span class="sxs-lookup"><span data-stu-id="07a59-277">The "Output" code box has no syntax highlighting.</span></span>

## <a name="coding-style-rules"></a><span data-ttu-id="07a59-278">コーディング スタイルの規則</span><span class="sxs-lookup"><span data-stu-id="07a59-278">Coding style rules</span></span>

### <a name="avoid-line-continuation-in-code-samples"></a><span data-ttu-id="07a59-279">サンプル コードでは行を連結しないようにする</span><span class="sxs-lookup"><span data-stu-id="07a59-279">Avoid line continuation in code samples</span></span>

<span data-ttu-id="07a59-280">PowerShell のコード例では、行連結文字 (`` ` ``) の使用は避けてください。</span><span class="sxs-lookup"><span data-stu-id="07a59-280">Avoid using line continuation characters (`` ` ``) in PowerShell code examples.</span></span> <span data-ttu-id="07a59-281">これらは見えにくく、行末に余分なスペースがあると問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-281">These are hard to see and can cause problems if there are extra spaces at the end of the line.</span></span>

- <span data-ttu-id="07a59-282">PowerShell のスプラッティングを使用して、多数のパラメーターを使用するコマンドレットの行の長さを短くします。</span><span class="sxs-lookup"><span data-stu-id="07a59-282">Use PowerShell splatting to reduce line length for cmdlets that have a lot of parameters.</span></span>
- <span data-ttu-id="07a59-283">パイプ (`|`) 文字、左中かっこ、左丸かっこ、左角かっこなどの PowerShell 本来の改行を活用します。</span><span class="sxs-lookup"><span data-stu-id="07a59-283">Take advantage of PowerShell's natural line break opportunities, like after pipe (`|`) characters, opening braces, parentheses, and brackets.</span></span>

### <a name="avoid-using-powershell-prompts-in-examples"></a><span data-ttu-id="07a59-284">例の中で PowerShell プロンプトを使用しないようにする</span><span class="sxs-lookup"><span data-stu-id="07a59-284">Avoid using PowerShell prompts in examples</span></span>

<span data-ttu-id="07a59-285">プロンプト文字列の使用は推奨されていません。コマンド ラインの使い方を示すシナリオに限定して使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-285">Use of the prompt string is discouraged and should be limited to scenarios that are meant to illustrate command line usage.</span></span> <span data-ttu-id="07a59-286">これらの例の大半では、プロンプト文字列を `PS>` にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-286">For most of these examples, the prompt string should be `PS>`.</span></span> <span data-ttu-id="07a59-287">このプロンプトは OS 固有のインジケーターに依存しません。</span><span class="sxs-lookup"><span data-stu-id="07a59-287">This prompt is independent of OS-specific indicators.</span></span>

<span data-ttu-id="07a59-288">プロンプトが必要なのは、プロンプトを変更するコマンドを例をあげて説明する場合、または説明しているシナリオでパスの表示に意味がある場合です。</span><span class="sxs-lookup"><span data-stu-id="07a59-288">Prompts are required for examples that illustrate commands that alter the prompt or when the path displayed is significant to the scenario being illustrated.</span></span> <span data-ttu-id="07a59-289">次の例では、レジストリ プロバイダーの使用時にプロンプトがどのように変化するかを示しています。</span><span class="sxs-lookup"><span data-stu-id="07a59-289">The following example illustrates how the prompt changes when using the Registry provider.</span></span>

```powershell
PS C:\> cd HKCU:\System\
PS HKCU:\System\> dir

    Hive: HKEY_CURRENT_USER\System

Name                   Property
----                   --------
CurrentControlSet
GameConfigStore        GameDVR_Enabled                       : 1
                       GameDVR_FSEBehaviorMode               : 2
                       Win32_AutoGameModeDefaultProfile      : {2, 0, 1, 0...}
                       Win32_GameModeRelatedProcesses        : {1, 0, 1, 0...}
                       GameDVR_HonorUserFSEBehaviorMode      : 0
                       GameDVR_DXGIHonorFSEWindowsCompatible : 0
```

### <a name="do-not-use-aliases-in-examples"></a><span data-ttu-id="07a59-290">例の中で別名を使用しない</span><span class="sxs-lookup"><span data-stu-id="07a59-290">Do not use aliases in examples</span></span>

<span data-ttu-id="07a59-291">別名について具体的に説明する場合を除いて、常にすべてのコマンドレットとパラメーターの完全名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-291">You should always use the full name of all cmdlets and parameters unless you are specifically talking about the alias.</span></span> <span data-ttu-id="07a59-292">コマンドレットとパラメーターの名前では、コードに定義されている適切なスペルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a59-292">Cmdlet and parameter names must use the proper spelling defined in the code.</span></span>

### <a name="using-parameters-in-examples"></a><span data-ttu-id="07a59-293">例でのパラメーターの使用</span><span class="sxs-lookup"><span data-stu-id="07a59-293">Using parameters in examples</span></span>

<span data-ttu-id="07a59-294">位置パラメーターの使用は避けてください。</span><span class="sxs-lookup"><span data-stu-id="07a59-294">Avoid using positional parameters.</span></span> <span data-ttu-id="07a59-295">通常は、パラメーターが位置パラメーターの場合でも、例では常にパラメーターの名前を含めるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="07a59-295">In general, you should use always include the parameter name in an example, even if the parameter positional.</span></span> <span data-ttu-id="07a59-296">これにより、例の中で混同が発生する機会が減少します。</span><span class="sxs-lookup"><span data-stu-id="07a59-296">This reduces the chance of confusion in your examples.</span></span>

## <a name="next-steps"></a><span data-ttu-id="07a59-297">次のステップ</span><span class="sxs-lookup"><span data-stu-id="07a59-297">Next steps</span></span>

[<span data-ttu-id="07a59-298">コマンドレット編集リファレンス</span><span class="sxs-lookup"><span data-stu-id="07a59-298">Editing cmdlet reference</span></span>](editing-cmdlet-ref.md)

<!-- External URLs -->
[platyPS]: https://github.com/PowerShell/platyPS
[markdig]: https://github.com/lunet-io/markdig
[CommonMark]: https://spec.commonmark.org/
[atx]: https://github.github.com/gfm/#atx-headings
[pascal-case]: https://en.wikipedia.org/wiki/PascalCase
[reflow]: https://marketplace.visualstudio.com/items?itemName=marvhen.reflow-markdown
