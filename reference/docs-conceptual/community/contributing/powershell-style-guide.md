---
title: PowerShell ドキュメントのスタイル ガイド
description: この記事では、PowerShell ドキュメントを記述するためのスタイル規則について説明します。
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 32df641f7cafa2a5bfcf1bcbf94be594aa77c7d0
ms.sourcegitcommit: 105c69ecedfe5180d8c12e8015d667c5f1a71579
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85837445"
---
# <a name="powershell-docs-style-guide"></a><span data-ttu-id="101ab-103">PowerShell ドキュメントのスタイル ガイド</span><span class="sxs-lookup"><span data-stu-id="101ab-103">PowerShell-Docs style guide</span></span>

<span data-ttu-id="101ab-104">この記事では、PowerShell ドキュメントのコンテンツに固有のスタイル ガイダンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="101ab-104">This article provides style guidance specific to the PowerShell-Docs content.</span></span> <span data-ttu-id="101ab-105">これは、[概要](overview.md#get-started-writing-docs)に記載されている情報に基づいています。</span><span class="sxs-lookup"><span data-stu-id="101ab-105">This builds on the information outlined in the [Overview](overview.md#get-started-writing-docs).</span></span>

## <a name="product-terminology"></a><span data-ttu-id="101ab-106">製品に関する用語</span><span class="sxs-lookup"><span data-stu-id="101ab-106">Product Terminology</span></span>

<span data-ttu-id="101ab-107">PowerShell にはいくつかのバリエーションがあります。</span><span class="sxs-lookup"><span data-stu-id="101ab-107">There are several variants of PowerShell.</span></span>

- <span data-ttu-id="101ab-108">**PowerShell** - これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="101ab-108">**PowerShell** - This is the default.</span></span> <span data-ttu-id="101ab-109">PowerShell 7 以降のすべての PowerShell の総称として使用されます。</span><span class="sxs-lookup"><span data-stu-id="101ab-109">We consider PowerShell 7 and beyond to be the one, true PowerShell going forward.</span></span>
- <span data-ttu-id="101ab-110">**PowerShell Core** - .NET Core 上で構築される PowerShell です。</span><span class="sxs-lookup"><span data-stu-id="101ab-110">**PowerShell Core** - PowerShell built on .NET Core.</span></span> <span data-ttu-id="101ab-111">**Core** という用語の使用は、Windows PowerShell と区別する必要がある場合にのみ限定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-111">Usage of the term **Core** should be limited to cases where it is necessary to differentiate it from Windows PowerShell.</span></span>
- <span data-ttu-id="101ab-112">**Windows PowerShell** - .NET Framework 上で構築される PowerShell です。</span><span class="sxs-lookup"><span data-stu-id="101ab-112">**Windows PowerShell** - PowerShell built on .NET Framework.</span></span> <span data-ttu-id="101ab-113">Windows PowerShell は Windows にのみ付属しており、完全な Framework が必要です。</span><span class="sxs-lookup"><span data-stu-id="101ab-113">Windows PowerShell ships only on Windows and requires the complete Framework.</span></span>

  <span data-ttu-id="101ab-114">通常、ドキュメント内の "Windows PowerShell" は、"PowerShell" に読み替えることができます。</span><span class="sxs-lookup"><span data-stu-id="101ab-114">In general, references to "Windows PowerShell" in documentation can be changed to "PowerShell".</span></span>
  <span data-ttu-id="101ab-115">"Windows PowerShell" 固有の動作について説明する場合は、"Windows PowerShell" を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-115">"Windows PowerShell" should be used when "Windows PowerShell"-specific behavior is being discussed.</span></span>

<span data-ttu-id="101ab-116">関連製品</span><span class="sxs-lookup"><span data-stu-id="101ab-116">Related products</span></span>

- <span data-ttu-id="101ab-117">**Visual Studio Code (VS Code)** - これは Microsoft の無料のオープン ソース エディターです。</span><span class="sxs-lookup"><span data-stu-id="101ab-117">**Visual Studio Code (VS Code)** - This is Microsoft's free, open source editor.</span></span> <span data-ttu-id="101ab-118">最初のメンションでは、完全な名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-118">At first mention, the full name should be used.</span></span> <span data-ttu-id="101ab-119">その後で、**VS Code** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="101ab-119">After that you may use **VS Code**.</span></span> <span data-ttu-id="101ab-120">"VSCode" は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="101ab-120">Do not use "VSCode".</span></span>
- <span data-ttu-id="101ab-121">**Visual Studio Code 用の PowerShell 拡張機能** - この拡張機能によって VS Code が PowerShell 用の推奨 IDE に切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="101ab-121">**PowerShell Extension for Visual Studio Code** - The extension turns VS Code into the preferred IDE for PowerShell.</span></span> <span data-ttu-id="101ab-122">最初のメンションでは、完全な名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-122">At first mention, the full name should be used.</span></span> <span data-ttu-id="101ab-123">その後で、**PowerShell 拡張機能**を使用できます。</span><span class="sxs-lookup"><span data-stu-id="101ab-123">After that you may use **PowerShell extension**.</span></span>
- <span data-ttu-id="101ab-124">**Azure PowerShell** - これは、Azure サービスを管理するために使用される PowerShell モジュールのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="101ab-124">**Azure PowerShell** - This is the collection of PowerShell modules used to manage Azure services.</span></span>
- <span data-ttu-id="101ab-125">**Azure Stack PowerShell** - これは、Microsoft のハイブリッド クラウド ソリューションを管理するために使用される PowerShell モジュールのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="101ab-125">**Azure Stack PowerShell** - This is the collection of PowerShell modules used to manage Microsoft's hybrid cloud solution.</span></span>

## <a name="markdown-specifics"></a><span data-ttu-id="101ab-126">Markdown の詳細</span><span class="sxs-lookup"><span data-stu-id="101ab-126">Markdown specifics</span></span>

<span data-ttu-id="101ab-127">Microsoft のドキュメントを構築する Microsoft Open Publishing System (OPS) では、[markdig][] を使用して Markdown ドキュメントが処理されます。</span><span class="sxs-lookup"><span data-stu-id="101ab-127">The Microsoft Open Publishing System (OPS) that builds our documentation uses [markdig][] to process the Markdown documents.</span></span> <span data-ttu-id="101ab-128">markdig では、最新の [CommonMark][] 仕様の規則に基づいてドキュメントが解析されます。</span><span class="sxs-lookup"><span data-stu-id="101ab-128">Markdig parses the documents based on the rules of the latest [CommonMark][] specification.</span></span>

<span data-ttu-id="101ab-129">新しい CommonMark 仕様では、いくつかの Markdown 要素の構築に関する規定が非常に厳密になっています。</span><span class="sxs-lookup"><span data-stu-id="101ab-129">The new CommonMark spec is much stricter about the construction of some Markdown elements.</span></span> <span data-ttu-id="101ab-130">このドキュメントの細部に、細心の注意を払ってください。</span><span class="sxs-lookup"><span data-stu-id="101ab-130">Pay close attention to the details provided in this document.</span></span>

### <a name="blank-lines-spaces-and-tabs"></a><span data-ttu-id="101ab-131">空白行、スペース、およびタブ</span><span class="sxs-lookup"><span data-stu-id="101ab-131">Blank lines, spaces, and tabs</span></span>

<span data-ttu-id="101ab-132">空白行は、Markdown 内のブロックが終わることも示します。</span><span class="sxs-lookup"><span data-stu-id="101ab-132">Blank lines also signal the end of a block in Markdown.</span></span> <span data-ttu-id="101ab-133">異なる種類の Markdown ブロックの間 (段落とリストの間や段落とヘッダーの間など) には、単一の空白行が必要です。</span><span class="sxs-lookup"><span data-stu-id="101ab-133">There should be a single blank between Markdown blocks of different types (for example, between a paragraph and a list or header).</span></span>

<span data-ttu-id="101ab-134">重複する空白行を削除します。</span><span class="sxs-lookup"><span data-stu-id="101ab-134">Remove duplicate blank lines.</span></span> <span data-ttu-id="101ab-135">複数の空白行は HTML では単一の空白行として表示されるため、複数の空白行には目的がありません。</span><span class="sxs-lookup"><span data-stu-id="101ab-135">Multiple blank lines render as a single blank line in HTML so there is no purpose for multiple blank lines.</span></span> <span data-ttu-id="101ab-136">コード ブロック内に複数の空白行があると、コード ブロックが分割されてしまいます。</span><span class="sxs-lookup"><span data-stu-id="101ab-136">Multiple blank lines within a code block break the code block.</span></span>

<span data-ttu-id="101ab-137">行の末尾の余分なスペースを削除してください。</span><span class="sxs-lookup"><span data-stu-id="101ab-137">Remove extra spaces at the end of lines.</span></span>

> [!NOTE]
> <span data-ttu-id="101ab-138">Markdown では、スペースが重要です。</span><span class="sxs-lookup"><span data-stu-id="101ab-138">Spacing is significant in Markdown.</span></span> <span data-ttu-id="101ab-139">常にハード タブではなくスペースを使用してください。</span><span class="sxs-lookup"><span data-stu-id="101ab-139">Always uses spaces instead of hard tabs.</span></span> <span data-ttu-id="101ab-140">Markdown のレンダリング方法は、末尾のスペースによって変更できます。</span><span class="sxs-lookup"><span data-stu-id="101ab-140">Trailing spaces can change how Markdown renders.</span></span>

### <a name="titles-and-headings"></a><span data-ttu-id="101ab-141">タイトルと見出し</span><span class="sxs-lookup"><span data-stu-id="101ab-141">Titles and headings</span></span>

<span data-ttu-id="101ab-142">[ATX 見出し][atx]のみを使用します (`=` または `-` スタイルのヘッダーではなく # スタイルにします)。</span><span class="sxs-lookup"><span data-stu-id="101ab-142">Only use [ATX headings][atx] (# style, as opposed to `=` or `-` style headers).</span></span>

- <span data-ttu-id="101ab-143">文の先頭で大文字を使用する - 固有名詞、タイトル、ヘッダーの 1 文字目のみ大文字にします</span><span class="sxs-lookup"><span data-stu-id="101ab-143">Use sentence case - only proper nouns and the first letter of a title or header should be capitalized</span></span>
- <span data-ttu-id="101ab-144">`#` と見出しの最初の文字の間には単一のスペースが必要</span><span class="sxs-lookup"><span data-stu-id="101ab-144">There must be a single space between the `#` and the first letter of the heading</span></span>
- <span data-ttu-id="101ab-145">見出しの上下は単一の空白行にする</span><span class="sxs-lookup"><span data-stu-id="101ab-145">Headings should be surrounded by a single blank line</span></span>
- <span data-ttu-id="101ab-146">ドキュメントごとの H1 は 1 つのみにする</span><span class="sxs-lookup"><span data-stu-id="101ab-146">Only one H1 per document</span></span>
- <span data-ttu-id="101ab-147">ヘッダーのレベルは 1 つずつ増分する。</span><span class="sxs-lookup"><span data-stu-id="101ab-147">Header levels should increment by one.</span></span> <span data-ttu-id="101ab-148">レベルをスキップしないでください</span><span class="sxs-lookup"><span data-stu-id="101ab-148">Do not skip levels</span></span>
- <span data-ttu-id="101ab-149">ヘッダーに太字またはその他のマークアップを使用しない</span><span class="sxs-lookup"><span data-stu-id="101ab-149">Do not use bold or other markup in headers</span></span>

### <a name="limit-line-length-to-100-characters"></a><span data-ttu-id="101ab-150">行の長さを 100 文字に制限する</span><span class="sxs-lookup"><span data-stu-id="101ab-150">Limit line length to 100 characters</span></span>

<span data-ttu-id="101ab-151">これは、概念記事とコマンドレット リファレンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="101ab-151">This applies to conceptual articles and cmdlet reference.</span></span> <span data-ttu-id="101ab-152">行の長さを制限することで、git diff と履歴が読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="101ab-152">Limiting the line length improves the readability of git diffs and history.</span></span> <span data-ttu-id="101ab-153">さらに、他の執筆者が投稿を簡単に行えるようにします。</span><span class="sxs-lookup"><span data-stu-id="101ab-153">It also makes it easier for other writers to make contributions.</span></span>

<span data-ttu-id="101ab-154">Visual Studio Code の [Reflow Markdown][reflow] 拡張機能を使用すると、規定の行の長さに合うように段落が簡単にリフロ―されます。</span><span class="sxs-lookup"><span data-stu-id="101ab-154">Use the [Reflow Markdown][reflow] extension in Visual Studio Code to easily reflow paragraphs to fit the prescribed line length.</span></span>

<span data-ttu-id="101ab-155">About_topics の長さは 80 文字に制限されます。</span><span class="sxs-lookup"><span data-stu-id="101ab-155">About_topics are limited to 80 characters.</span></span> <span data-ttu-id="101ab-156">詳細については、「[参照記事の編集](./editing-cmdlet-ref.md#formatting-about_-files)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="101ab-156">For more specific information, see [Editing reference articles](./editing-cmdlet-ref.md#formatting-about_-files).</span></span>

### <a name="lists"></a><span data-ttu-id="101ab-157">リスト</span><span class="sxs-lookup"><span data-stu-id="101ab-157">Lists</span></span>

<span data-ttu-id="101ab-158">リストに複数の文または段落が含まれている場合は、リストではなくサブレベルのヘッダーを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="101ab-158">If your list contains multiple sentences or paragraphs, consider using a sub-level header rather than a list.</span></span>

<span data-ttu-id="101ab-159">リストの上下は単一の空白行にします。</span><span class="sxs-lookup"><span data-stu-id="101ab-159">List should be surrounded by a single blank line.</span></span>

#### <a name="unordered-lists"></a><span data-ttu-id="101ab-160">箇条書きリスト</span><span class="sxs-lookup"><span data-stu-id="101ab-160">Unordered lists</span></span>

<span data-ttu-id="101ab-161">リスト項目に複数の文が含まれていない限り、リスト項目にはピリオドをつけないでください。</span><span class="sxs-lookup"><span data-stu-id="101ab-161">Do not end list items with a period unless they contain multiple sentences.</span></span> <span data-ttu-id="101ab-162">リスト項目の箇条書き記号には、ハイフン文字 (`-`) を使用します。</span><span class="sxs-lookup"><span data-stu-id="101ab-162">Use the hyphen character (`-`) for list item bullets.</span></span> <span data-ttu-id="101ab-163">これにより、アスタリスク [`*`] を使用する、太字または斜体のマークアップとの混同を回避できます。</span><span class="sxs-lookup"><span data-stu-id="101ab-163">This avoids confusion with bold or italic markup that uses the asterisk [`*`].</span></span> <span data-ttu-id="101ab-164">段落またはその他の要素を箇条書き項目の下に含めるには、改行を挿入し、インデントを箇条書き記号の後ろの最初の文字に揃えます。</span><span class="sxs-lookup"><span data-stu-id="101ab-164">To include a paragraph or other elements under a bullet item, insert a line break and align indentation with the first character after the bullet.</span></span>

<span data-ttu-id="101ab-165">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="101ab-165">For example:</span></span>

```markdown
This is a list that contain sub-elements under a bullet item.

- First bullet item

  Sentence explaining the first bullet.

  - Sub-bullet item

    Sentence explaining the sub-bullet.

- Second bullet item
- Third bullet item
```

<span data-ttu-id="101ab-166">これは、箇条書き項目の下にサブ要素が含まれているリストです。</span><span class="sxs-lookup"><span data-stu-id="101ab-166">This is a list that contains sub-elements under a bullet item.</span></span>

- <span data-ttu-id="101ab-167">最初の箇条書き項目</span><span class="sxs-lookup"><span data-stu-id="101ab-167">First bullet item</span></span>

  <span data-ttu-id="101ab-168">最初の箇条書きの内容文。</span><span class="sxs-lookup"><span data-stu-id="101ab-168">Sentence explaining the first bullet.</span></span>

  - <span data-ttu-id="101ab-169">サブ箇条書き項目</span><span class="sxs-lookup"><span data-stu-id="101ab-169">Sub-bullet item</span></span>

    <span data-ttu-id="101ab-170">サブ箇条書きの内容文。</span><span class="sxs-lookup"><span data-stu-id="101ab-170">Sentence explaining the sub-bullet.</span></span>

- <span data-ttu-id="101ab-171">2 番目の箇条書き項目</span><span class="sxs-lookup"><span data-stu-id="101ab-171">Second bullet item</span></span>
- <span data-ttu-id="101ab-172">3 番目の箇条書き項目</span><span class="sxs-lookup"><span data-stu-id="101ab-172">Third bullet item</span></span>

#### <a name="ordered-lists"></a><span data-ttu-id="101ab-173">番号付きリスト</span><span class="sxs-lookup"><span data-stu-id="101ab-173">Ordered lists</span></span>

<span data-ttu-id="101ab-174">段落またはその他の要素を番号付き項目の下に含めるには、インデントを項目番号の後ろの最初の文字に揃えます。</span><span class="sxs-lookup"><span data-stu-id="101ab-174">To include a paragraph or other elements under a numbered item, align indentation with the first character after the item number.</span></span> <span data-ttu-id="101ab-175">番号付きリストのすべての項目では、項目ごとに増分される番号ではなく、番号 `1.` を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-175">All items in a numbered listed should use the number `1.` rather than incrementing each item.</span></span> <span data-ttu-id="101ab-176">この値は、Markdown によって自動的に増分されて表示されます。</span><span class="sxs-lookup"><span data-stu-id="101ab-176">Markdown rendering increments the value automatically.</span></span> <span data-ttu-id="101ab-177">これにより、項目を簡単に並べ替えることができ、下位コンテンツのインデントが統一されます。</span><span class="sxs-lookup"><span data-stu-id="101ab-177">This makes reordering items easier and standardizes the indentation of subordinate content.</span></span>

<span data-ttu-id="101ab-178">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="101ab-178">For example:</span></span>

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

<span data-ttu-id="101ab-179">結果の Markdown は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="101ab-179">The resulting Markdown is rendered as follows:</span></span>

1. <span data-ttu-id="101ab-180">最初の要素では、1. の後ろに単一のスペースを挿入します。</span><span class="sxs-lookup"><span data-stu-id="101ab-180">For the first element, insert a single space after the 1.</span></span> <span data-ttu-id="101ab-181">長い文は次の行に折り返す必要があり、次の行の先頭は番号付きリスト マーカーの後ろの最初の文字と揃える必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-181">Long sentences should be wrapped to the next line and must line up with the first character after the numbered list marker.</span></span>

   <span data-ttu-id="101ab-182">(この例のように) 2 つ目の要素を含めるには、1 つ目の要素の後に改行を挿入し、インデントを合わせます。</span><span class="sxs-lookup"><span data-stu-id="101ab-182">To include a second element (like this one), insert a line break after the first and align indentations.</span></span> <span data-ttu-id="101ab-183">2 つ目の要素のインデントは、番号付きリスト マーカーの後ろの最初の文字と揃える必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-183">The indentation of the second element must line up with the first character after the numbered list marker.</span></span> <span data-ttu-id="101ab-184">このような 1 桁の番号の項目では、列 4 にインデントします。</span><span class="sxs-lookup"><span data-stu-id="101ab-184">For single digit items, like this one, you indent to column 4.</span></span> <span data-ttu-id="101ab-185">2 桁の番号の項目 (項目番号 10 など) では、列 5 にインデントします。</span><span class="sxs-lookup"><span data-stu-id="101ab-185">For double digits items, for example item number 10, you indent to column 5.</span></span>

1. <span data-ttu-id="101ab-186">次の番号付き項目は、ここから始まります。</span><span class="sxs-lookup"><span data-stu-id="101ab-186">The next numbered item starts here.</span></span>

### <a name="images"></a><span data-ttu-id="101ab-187">イメージ</span><span class="sxs-lookup"><span data-stu-id="101ab-187">Images</span></span>

<span data-ttu-id="101ab-188">画像を含める構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="101ab-188">The syntax to include an image is:</span></span>

```markdown
![[alt text]](<folderPath>)

Example:
![Introduction](./media/overview/Introduction.png)
```

<span data-ttu-id="101ab-189">`alt text` は画像の簡単な説明であり、`<folder path>` は画像の相対パスです。</span><span class="sxs-lookup"><span data-stu-id="101ab-189">Where `alt text` is a brief description of the image and `<folder path>` is a relative path to the image.</span></span> <span data-ttu-id="101ab-190">代替テキストは、視覚障碍がある読者のために必要です。</span><span class="sxs-lookup"><span data-stu-id="101ab-190">Alternate text is required for screen readers for the visually impaired.</span></span> <span data-ttu-id="101ab-191">サイトのバグで画像を表示できない場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="101ab-191">It is also useful in case there is a site bug where the image cannot be rendered.</span></span>

<span data-ttu-id="101ab-192">画像は、記事が含まれているフォルダー内の `media/<article-name>` フォルダーに格納されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-192">Images should be stored in a `media/<article-name>` folder within the folder containing the article.</span></span>
<span data-ttu-id="101ab-193">複数の記事で画像を共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="101ab-193">Images should not be shared between articles.</span></span> <span data-ttu-id="101ab-194">`media` フォルダーの下に、記事のファイル名と一致するフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="101ab-194">Create a folder that matches the filename of your article under the `media` folder.</span></span> <span data-ttu-id="101ab-195">記事のための画像を、その新しいフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="101ab-195">Copy the images for that article to that new folder.</span></span> <span data-ttu-id="101ab-196">画像が複数の記事で使用される場合は、各画像フォルダーにその画像ファイルのコピーが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-196">If an image is used by multiple articles, each image folder must have a copy of that image file.</span></span> <span data-ttu-id="101ab-197">ある記事内の画像の変更が他の記事に影響するのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="101ab-197">This practice prevents a change to an image in one article affecting another article.</span></span>

<span data-ttu-id="101ab-198">次の種類の画像ファイルがサポートされています。`*.png`、`*.gif`、`*.jpeg`、`*.jpg`、`*.svg`</span><span class="sxs-lookup"><span data-stu-id="101ab-198">The following image file types are supported: `*.png`, `*.gif`, `*.jpeg`, `*.jpg`, `*.svg`</span></span>

### <a name="markdown-extensions-supported-by-open-publishing"></a><span data-ttu-id="101ab-199">Open Publishing でサポートされる Markdown 拡張機能</span><span class="sxs-lookup"><span data-stu-id="101ab-199">Markdown extensions supported by Open Publishing</span></span>

<span data-ttu-id="101ab-200">[Microsoft Docs Authoring Pack](/contribute/how-to-write-docs-auth-pack) には、Microsoft のパブリッシング システム固有の機能をサポートするツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="101ab-200">The [Microsoft Docs Authoring Pack](/contribute/how-to-write-docs-auth-pack) contains tools that support features unique to our publishing system.</span></span> <span data-ttu-id="101ab-201">アラートは、docs.microsoft.com に表示されるブロック引用を、その内容の重要性を強調表示する色とアイコンを使用して作成する Markdown 拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="101ab-201">Alerts are a Markdown extension to create blockquotes that render on docs.microsoft.com with colors and icons that highlight the significance of the content.</span></span> <span data-ttu-id="101ab-202">次のアラートの種類がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="101ab-202">The following alert types are supported:</span></span>

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

<span data-ttu-id="101ab-203">これらのアラートは、docs.microsoft.com に次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="101ab-203">These alerts look like this on docs.microsoft.com:</span></span>

<span data-ttu-id="101ab-204">注意ブロック</span><span class="sxs-lookup"><span data-stu-id="101ab-204">Note block</span></span>

> [!NOTE]
> <span data-ttu-id="101ab-205">流し読みする場合でも、ユーザーが注目する必要がある情報です。</span><span class="sxs-lookup"><span data-stu-id="101ab-205">Information the user should notice even if skimming.</span></span>

<span data-ttu-id="101ab-206">ヒント ブロック</span><span class="sxs-lookup"><span data-stu-id="101ab-206">Tip block</span></span>

> [!TIP]
> <span data-ttu-id="101ab-207">ユーザーの成果を向上させるために役立つオプションの情報です。</span><span class="sxs-lookup"><span data-stu-id="101ab-207">Optional information to help a user be more successful.</span></span>

<span data-ttu-id="101ab-208">重要ブロック</span><span class="sxs-lookup"><span data-stu-id="101ab-208">Important block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="101ab-209">ユーザーが目的を達成するために必要な、非常に重要な情報です。</span><span class="sxs-lookup"><span data-stu-id="101ab-209">Essential information required for user success.</span></span>

<span data-ttu-id="101ab-210">注意事項ブロック</span><span class="sxs-lookup"><span data-stu-id="101ab-210">Caution block</span></span>

> [!CAUTION]
> <span data-ttu-id="101ab-211">アクションの考えられる悪影響です。</span><span class="sxs-lookup"><span data-stu-id="101ab-211">Negative potential consequences of an action.</span></span>

<span data-ttu-id="101ab-212">警告ブロック</span><span class="sxs-lookup"><span data-stu-id="101ab-212">Warning block</span></span>

> [!WARNING]
> <span data-ttu-id="101ab-213">アクションの避けられない危険な影響です。</span><span class="sxs-lookup"><span data-stu-id="101ab-213">Dangerous certain consequences of an action.</span></span>

### <a name="hyperlinks"></a><span data-ttu-id="101ab-214">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="101ab-214">Hyperlinks</span></span>

- <span data-ttu-id="101ab-215">ハイパーリンクには Markdown 構文を使用する必要があります `[friendlyname](url-or-path)`</span><span class="sxs-lookup"><span data-stu-id="101ab-215">Hyperlinks must use Markdown syntax `[friendlyname](url-or-path)`</span></span>
- <span data-ttu-id="101ab-216">可能な場合は、リンクを HTTPS にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-216">Links should be HTTPS when possible.</span></span>
- <span data-ttu-id="101ab-217">リンクにはフレンドリ名が必要です。通常はリンク先のトピックのタイトルを使用します。</span><span class="sxs-lookup"><span data-stu-id="101ab-217">Links must have a friendly name, usually the title of the linked topic</span></span>
- <span data-ttu-id="101ab-218">下部にある「関連リンク」セクションのすべての項目は、ハイパーリンクにする必要があります</span><span class="sxs-lookup"><span data-stu-id="101ab-218">All items in the "related links" section at the bottom should be hyperlinked</span></span>
- <span data-ttu-id="101ab-219">ハイパーリンクの角かっこ内で、バックティック、太字、またはその他のマークアップを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="101ab-219">Do not use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>
- <span data-ttu-id="101ab-220">特定の URI について述べている場合は、URL そのものを使用できます。</span><span class="sxs-lookup"><span data-stu-id="101ab-220">Bare URLs may be used when you are talking about a specific URI.</span></span> <span data-ttu-id="101ab-221">その URI はバックティックで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-221">The URI must be enclosed in backticks.</span></span> <span data-ttu-id="101ab-222">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="101ab-222">For example:</span></span>

  ```markdown
  By default, if you do not specify this parameter, the DMTF standard resource URI
  `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.
  ```

#### <a name="linking-to-other-content"></a><span data-ttu-id="101ab-223">他のコンテンツへのリンク</span><span class="sxs-lookup"><span data-stu-id="101ab-223">Linking to other content</span></span>

<span data-ttu-id="101ab-224">パブリッシング システムでサポートされるハイパーリンクには、</span><span class="sxs-lookup"><span data-stu-id="101ab-224">There are two types of hyperlinks supported by the publishing system:</span></span>

<span data-ttu-id="101ab-225">**URL リンク**では、docs.microsoft.com のルートに対する相対的な URL パスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="101ab-225">A **URL link** can be a URL path that is relative to the root of docs.microsoft.com.</span></span> <span data-ttu-id="101ab-226">または、完全な URL 構文を含む絶対 URL を使用することもできます</span><span class="sxs-lookup"><span data-stu-id="101ab-226">Or an absolute URL that include the full URL syntax.</span></span> <span data-ttu-id="101ab-227">例: `https:/github.com/MicrosoftDocs/PowerShell-Docs`</span><span class="sxs-lookup"><span data-stu-id="101ab-227">For example: `https:/github.com/MicrosoftDocs/PowerShell-Docs`</span></span>

- <span data-ttu-id="101ab-228">PowerShell ドキュメント以外のコンテンツにリンクする場合、または PowerShell ドキュメント内のコマンドレット リファレンスと概念記事の間にリンクを設定する場合は、URL リンクを使用します。相対リンクを作成する最も簡単な方法は、ブラウザーから URL をコピーした後、Markdown に貼り付ける値から `https://docs.microsoft.com/en-us` を削除することです。</span><span class="sxs-lookup"><span data-stu-id="101ab-228">Use URL links when linking to content outside of PowerShell-Docs or between cmdlet reference and conceptual articles within PowerShell-docs. The simplest way to create a relative link is to copy the URL from your browser then remove `https://docs.microsoft.com/en-us` from the value you paste into markdown.</span></span>
- <span data-ttu-id="101ab-229">URL には Microsoft プロパティのロケールを含めないでください (例:</span><span class="sxs-lookup"><span data-stu-id="101ab-229">Do not include locales in URLs on Microsoft properties (eg.</span></span> <span data-ttu-id="101ab-230">URL から `/en-us` を削除する)。</span><span class="sxs-lookup"><span data-stu-id="101ab-230">remove `/en-us` from URL).</span></span>
- <span data-ttu-id="101ab-231">記事の特定のバージョンにリンクする必要がない限り、URL から不要なクエリ パラメーターは削除します。</span><span class="sxs-lookup"><span data-stu-id="101ab-231">Remove any unnecessary query parameters from the URL unless you need to link to a specific version of an article.</span></span> <span data-ttu-id="101ab-232">例 :</span><span class="sxs-lookup"><span data-stu-id="101ab-232">Examples:</span></span>
  - <span data-ttu-id="101ab-233">`?view=powershell-5.1` - PowerShell の特定のバージョンにリンクするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="101ab-233">`?view=powershell-5.1` - this is used to link to a specific version of PowerShell</span></span>
  - <span data-ttu-id="101ab-234">`?redirectedfrom=MSDN` - これは、古い記事からその新しい場所にリダイレクトされると、URL に追加されます。</span><span class="sxs-lookup"><span data-stu-id="101ab-234">`?redirectedfrom=MSDN` - this is added to the URL when you get redirected from an old article to its new location</span></span>
- <span data-ttu-id="101ab-235">ターゲット サイトで無効な場合を除き、外部 Web サイトへのすべての URL には HTTPS を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-235">All URLs to external websites should use HTTPS unless that is not valid for the target site.</span></span>

<span data-ttu-id="101ab-236">ある参照記事から別の参照記事へのリンク、またはある概念記事から別の概念記事へのリンクを設定する場合は、**ファイル リンク**を使用します。</span><span class="sxs-lookup"><span data-stu-id="101ab-236">A **file link** is used to link from one reference article to another, or from one conceptual article to another.</span></span> <span data-ttu-id="101ab-237">PowerShell の特定のバージョン用の参照記事にリンクする必要がある場合は、URL リンクを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-237">If you need to link to a reference article for a specific version of PowerShell, then you must use a URL link.</span></span>

- <span data-ttu-id="101ab-238">ファイル リンクには、相対ファイル パスを含めます (例: `../folder/file.md`)</span><span class="sxs-lookup"><span data-stu-id="101ab-238">File links contain a relative file path (for example: `../folder/file.md`)</span></span>
- <span data-ttu-id="101ab-239">すべてのファイル パスにスラッシュ (`/`) 文字を使用します</span><span class="sxs-lookup"><span data-stu-id="101ab-239">All file paths use forward-slash (`/`) characters</span></span>

<span data-ttu-id="101ab-240">ディープ リンクは、URL リンクとファイルリンクの両方で使用できます。</span><span class="sxs-lookup"><span data-stu-id="101ab-240">Deep linking is allowed on both URL and file links.</span></span> <span data-ttu-id="101ab-241">ターゲット パスの末尾にアンカーを追加します。</span><span class="sxs-lookup"><span data-stu-id="101ab-241">Add the anchor to the end of the target path.</span></span>
<span data-ttu-id="101ab-242">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="101ab-242">For example:</span></span>

- `[about_Splatting](about_Splatting.md#splatting-with-arrays)`
- `[custom key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)`

<span data-ttu-id="101ab-243">詳細については、「[ドキュメントでリンクを使用する](/contribute/how-to-write-links)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="101ab-243">For more information, see [Use links in documentation](/contribute/how-to-write-links).</span></span>

## <a name="formatting-command-syntax-elements"></a><span data-ttu-id="101ab-244">コマンド構文要素の書式設定</span><span class="sxs-lookup"><span data-stu-id="101ab-244">Formatting command syntax elements</span></span>

- <span data-ttu-id="101ab-245">コマンドレットとパラメーターには常に完全名を使用します。</span><span class="sxs-lookup"><span data-stu-id="101ab-245">Always use the full name for cmdlets and parameters.</span></span> <span data-ttu-id="101ab-246">別名について具体的に説明する場合を除いて、別名の使用は避けてください。</span><span class="sxs-lookup"><span data-stu-id="101ab-246">Avoid using aliases unless you are specifically demonstrating the alias.</span></span>

- <span data-ttu-id="101ab-247">プロパティ、パラメーター、オブジェクト、型名、クラス名、クラス メソッドは**太字**にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-247">Property, parameter, object, type names, class names, class methods should be **bold**.</span></span>
  - <span data-ttu-id="101ab-248">プロパティとパラメーターの値は、バックティック (`` ` ``) でラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-248">Property and parameter values should be wrapped in backticks (`` ` ``).</span></span>
  - <span data-ttu-id="101ab-249">かっこで囲まれたスタイルを使用して型を参照する場合は、バックティックを使用します。</span><span class="sxs-lookup"><span data-stu-id="101ab-249">When referring to types using the bracketed style, use backticks.</span></span> <span data-ttu-id="101ab-250">例: `[System.Io.FileInfo]`</span><span class="sxs-lookup"><span data-stu-id="101ab-250">For example: `[System.Io.FileInfo]`</span></span>

- <span data-ttu-id="101ab-251">言語キーワード、コマンドレット名、関数、変数、ネイティブ EXE、ファイル パス、インライン構文の例は、バックティック (`` ` ``) 文字でラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-251">Language keywords, cmdlet names, functions, variables, native EXEs, file paths, and inline syntax examples should be wrapped in backtick (`` ` ``) characters.</span></span>

  <span data-ttu-id="101ab-252">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="101ab-252">For example:</span></span>

  ~~~markdown
  The following code uses `Get-ChildItem` to list the contents of `C:\Windows` and assigns
  the output to the `$files` variable.

  ```powershell
  $files = Get-ChildItem C:\Windows
  ```
  ~~~

  - <span data-ttu-id="101ab-253">パラメーターを名前で参照する場合は、名前を**太字**にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-253">When referring to a parameter by name, the name should be **bold**.</span></span> <span data-ttu-id="101ab-254">ハイフン プレフィックス付きのパラメーターの使用を示す場合は、パラメーターをバックティックで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-254">When illustrating the use of a parameter with the hyphen prefix, the parameter should be wrapped in backticks.</span></span> <span data-ttu-id="101ab-255">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="101ab-255">For example:</span></span>

    ```markdown
    The parameter's name is **Name**, but it is typed as `-Name` when used on the command
    line as a parameter.
    ```

  - <span data-ttu-id="101ab-256">外部コマンドの使用例を示す場合は、例をバックティックで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-256">When showing example usage of an external command, the example should be wrapped in backticks.</span></span>
    <span data-ttu-id="101ab-257">ネイティブ コマンドには、常にファイル拡張子を含めます。</span><span class="sxs-lookup"><span data-stu-id="101ab-257">Always include the file extension in the native command.</span></span> <span data-ttu-id="101ab-258">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="101ab-258">For example:</span></span>

    ```markdown
    To start the spooler service on a remote computer named DC01, you type `sc.exe \\DC01 start spooler`.
    ```

    <span data-ttu-id="101ab-259">ファイル拡張子を含めると、PowerShell のコマンドの優先順位に従って適切なコマンドが確実に実行されます。</span><span class="sxs-lookup"><span data-stu-id="101ab-259">Including the file extension ensures that the correct command is executed according PowerShell's command precedence.</span></span>

- <span data-ttu-id="101ab-260">(参照コンテンツではなく) 概念記事を記述する場合は、最初に出現するコマンドレットの名前に、コマンドレットのドキュメントにリンクされたハイパーリンクを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-260">When writing a conceptual article (as opposed to reference content), the first instance of a cmdlet name should be hyperlinked to the cmdlet documentation.</span></span> <span data-ttu-id="101ab-261">ハイパーリンクの角かっこ内で、バックティック、太字、またはその他のマークアップを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="101ab-261">Do not use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>

  <span data-ttu-id="101ab-262">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="101ab-262">For example:</span></span>

  ```markdown
  This [Write-Host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) cmdlet
  uses the **Object** parameter to ...
  ```

  <span data-ttu-id="101ab-263">詳細については、この記事の「[ハイパーリンク](#hyperlinks)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="101ab-263">For more information, see [Hyperlinks](#hyperlinks) section of this article.</span></span>

## <a name="markdown-for-code-samples"></a><span data-ttu-id="101ab-264">コード サンプルの Markdown</span><span class="sxs-lookup"><span data-stu-id="101ab-264">Markdown for code samples</span></span>

<span data-ttu-id="101ab-265">Markdown では、次の 2 つの異なるコード スタイルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="101ab-265">Markdown supports two different code styles:</span></span>

- <span data-ttu-id="101ab-266">**コード スパン (インライン)** - 単一のバックティック (`` ` ``) 文字でマークされます。</span><span class="sxs-lookup"><span data-stu-id="101ab-266">**Code spans (inline)** - marked by a single backtick (`` ` ``) character.</span></span> <span data-ttu-id="101ab-267">スタンドアロン ブロックとしてではなく、段落内で使用されます。</span><span class="sxs-lookup"><span data-stu-id="101ab-267">Used within a paragraph rather than as a standalone block.</span></span>
- <span data-ttu-id="101ab-268">**コード ブロック** - トリプル バックティック (`` ``` ``) 文字列で囲まれた複数行のまとまりです。</span><span class="sxs-lookup"><span data-stu-id="101ab-268">**Code blocks** - a multi-line block surrounded by triple-backtick (`` ``` ``) strings.</span></span> <span data-ttu-id="101ab-269">コード ブロックでは、バックティックの後ろに言語ラベルを付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="101ab-269">Code blocks may also have a language label following the backticks.</span></span> <span data-ttu-id="101ab-270">言語ラベルを使用して、構文でコード ブロックの内容を強調できます。</span><span class="sxs-lookup"><span data-stu-id="101ab-270">The language label enables syntax highlighting for the contents of the code block.</span></span>

<span data-ttu-id="101ab-271">すべてのコード ブロックは、コード フェンスに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-271">All code blocks should be contained in a code fence.</span></span> <span data-ttu-id="101ab-272">コード ブロックにはインデントを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="101ab-272">Never use indentation for code blocks.</span></span> <span data-ttu-id="101ab-273">Markdown ではこのパターンを使用できますが、問題になる可能性があるため、回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-273">Markdown allows this pattern but it can be problematic and should be avoided.</span></span>

<span data-ttu-id="101ab-274">コード ブロックは、3 つのバックティック (`` ``` ``) コード フェンスで囲まれた 1 行または複数行のコードです。</span><span class="sxs-lookup"><span data-stu-id="101ab-274">A code block is one or more lines of code surrounded by a triple-backtick (`` ``` ``) code fence.</span></span>
<span data-ttu-id="101ab-275">コード フェンス マーカーは、サンプル コードの前と後ろの専用の行に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-275">The code fence markers must be on their own line before and after the code sample.</span></span> <span data-ttu-id="101ab-276">コード ブロックの開始を示すマーカーには、言語ラベルを含めることができます (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="101ab-276">The marker at the start of the code block may have an optional language label.</span></span> <span data-ttu-id="101ab-277">Microsoft の Open Publishing System (OPS) では、言語ラベルを使用した構文の強調機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="101ab-277">Microsoft's Open Publishing System (OPS) uses the language label to support the syntax highlighting feature.</span></span>

<span data-ttu-id="101ab-278">サポートされている言語タグの完全な一覧については、一元化された共同作成者ガイドの「[フェンスされたコード ブロック](/contribute/code-in-docs#fenced-code-blocks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="101ab-278">For a full list of supported language tags, see [Fenced code blocks](/contribute/code-in-docs#fenced-code-blocks) in the centralized contributor guide.</span></span>

<span data-ttu-id="101ab-279">OPS では、コード ブロックの内容をクリップボードにコピーする **[コピー]** ボタンも追加されます。</span><span class="sxs-lookup"><span data-stu-id="101ab-279">OPS also adds a **Copy** button that copies the contents of the code block to the clipboard.</span></span> <span data-ttu-id="101ab-280">これにより、コード サンプルをテストするためのスクリプトにコードを簡単に貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="101ab-280">This allows you to quickly paste the code into a script to test the code sample.</span></span> <span data-ttu-id="101ab-281">ただし、ドキュメントのすべての例がそのとおりに実行されることを目的としているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="101ab-281">However, not all examples in our documentation are intended to be run as-is.</span></span> <span data-ttu-id="101ab-282">一部のコード ブロックは、PowerShell の概念を簡単に説明するものです。</span><span class="sxs-lookup"><span data-stu-id="101ab-282">Some code blocks are simple illustrations of a PowerShell concept.</span></span>

<span data-ttu-id="101ab-283">Microsoft のドキュメントでは、次の 3 種類のコード ブロックが使用されています。</span><span class="sxs-lookup"><span data-stu-id="101ab-283">There are three types code blocks used in our documentation:</span></span>

1. <span data-ttu-id="101ab-284">構文ブロック</span><span class="sxs-lookup"><span data-stu-id="101ab-284">Syntax blocks</span></span>
1. <span data-ttu-id="101ab-285">説明用の例</span><span class="sxs-lookup"><span data-stu-id="101ab-285">Illustrative examples</span></span>
1. <span data-ttu-id="101ab-286">実行可能な例</span><span class="sxs-lookup"><span data-stu-id="101ab-286">Executable examples</span></span>

### <a name="syntax-code-blocks"></a><span data-ttu-id="101ab-287">構文のコード ブロック</span><span class="sxs-lookup"><span data-stu-id="101ab-287">Syntax code blocks</span></span>

<span data-ttu-id="101ab-288">構文のコード ブロックは、コマンドの構文構造を記述するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="101ab-288">Syntax code blocks are used to describe the syntactic structure of a command.</span></span> <span data-ttu-id="101ab-289">コード フェンスに対して言語タグを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="101ab-289">Do not use a language tag on the code fence.</span></span> <span data-ttu-id="101ab-290">次の例は、`Get-Command` コマンドレットで使用できるすべてのパラメーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="101ab-290">This example illustrates all the possible parameters of the `Get-Command` cmdlet.</span></span>

~~~markdown
```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
  [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax]
  [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
  [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```
~~~

<span data-ttu-id="101ab-291">次の例は、`for` ステートメントについて、一般的な用語で説明しています。</span><span class="sxs-lookup"><span data-stu-id="101ab-291">This example describes the `for` statement in generalized terms:</span></span>

~~~markdown
```
for (<init>; <condition>; <repeat>)
{<statement list>}
```
~~~

### <a name="illustrative-examples"></a><span data-ttu-id="101ab-292">説明用の例</span><span class="sxs-lookup"><span data-stu-id="101ab-292">Illustrative examples</span></span>

<span data-ttu-id="101ab-293">説明用の例は、PowerShell の概念を説明するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="101ab-293">Illustrative examples are used to explain a PowerShell concept.</span></span> <span data-ttu-id="101ab-294">これらは、クリップボードにコピーして実行するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="101ab-294">They are not meant to be copied to the clipboard for execution.</span></span> <span data-ttu-id="101ab-295">これらは、入力が簡単で理解しやすいシンプルな例として最も一般的に使用されています。</span><span class="sxs-lookup"><span data-stu-id="101ab-295">These are most commonly used for simple examples that are easy to type and easy to understand.</span></span> <span data-ttu-id="101ab-296">コード ブロックには、PowerShell プロンプトと出力例を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="101ab-296">The code block can include the PowerShell prompt and example output.</span></span>

<span data-ttu-id="101ab-297">PowerShell の比較演算子のシンプルな例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="101ab-297">Here is a simple example illustrating the PowerShell comparison operators.</span></span> <span data-ttu-id="101ab-298">この例では、読者がこの例をコピーして実行することは想定されていません。</span><span class="sxs-lookup"><span data-stu-id="101ab-298">In this case, we don't intend the reader to copy and run this example.</span></span>

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

### <a name="executable-examples"></a><span data-ttu-id="101ab-299">実行可能な例</span><span class="sxs-lookup"><span data-stu-id="101ab-299">Executable examples</span></span>

<span data-ttu-id="101ab-300">複雑な例または、コピーして実行することを目的とした例では、次のブロックスタイルのマークアップを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-300">Complex examples, or examples that are intended to be copied and executed, should use the following block-style markup:</span></span>

~~~markdown
```powershell
<Your PowerShell code goes here>
```
~~~

<span data-ttu-id="101ab-301">構文の強調を防ぐために、PowerShell コマンドによって表示される出力を **Output** コード ブロックに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-301">The output displayed by PowerShell commands should be enclosed in an **Output** code block to prevent syntax highlighting.</span></span> <span data-ttu-id="101ab-302">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="101ab-302">For example:</span></span>

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

<span data-ttu-id="101ab-303">**Output** コード ラベルは、構文強調システムでサポートされている公式の "言語" ではありません。</span><span class="sxs-lookup"><span data-stu-id="101ab-303">The **Output** code label is not an official "language" supported by the syntax highlighting system.</span></span>
<span data-ttu-id="101ab-304">ただし、このラベルが有用なのは、これを使用すると、OPS によって、Web ページ上のコード ボックス フレームに "Output" ラベルが追加されるためです。</span><span class="sxs-lookup"><span data-stu-id="101ab-304">However, this label is useful because OPS adds the "Output" label to the code box frame on the web page.</span></span> <span data-ttu-id="101ab-305">"Output" コード ボックスでは、構文の強調は行われません。</span><span class="sxs-lookup"><span data-stu-id="101ab-305">The "Output" code box has no syntax highlighting.</span></span>

## <a name="coding-style-rules"></a><span data-ttu-id="101ab-306">コーディング スタイルの規則</span><span class="sxs-lookup"><span data-stu-id="101ab-306">Coding style rules</span></span>

### <a name="avoid-line-continuation-in-code-samples"></a><span data-ttu-id="101ab-307">サンプル コードでは行を連結しないようにする</span><span class="sxs-lookup"><span data-stu-id="101ab-307">Avoid line continuation in code samples</span></span>

<span data-ttu-id="101ab-308">PowerShell のコード例では、行連結文字 (`` ` ``) の使用は避けてください。</span><span class="sxs-lookup"><span data-stu-id="101ab-308">Avoid using line continuation characters (`` ` ``) in PowerShell code examples.</span></span> <span data-ttu-id="101ab-309">これらは見えにくく、行末に余分なスペースがあると問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-309">These are hard to see and can cause problems if there are extra spaces at the end of the line.</span></span>

- <span data-ttu-id="101ab-310">PowerShell のスプラッティングを使用して、多数のパラメーターを使用するコマンドレットの行の長さを短くします。</span><span class="sxs-lookup"><span data-stu-id="101ab-310">Use PowerShell splatting to reduce line length for cmdlets that have a lot of parameters.</span></span>
- <span data-ttu-id="101ab-311">パイプ (`|`) 文字、左中かっこ、左丸かっこ、左角かっこなどの PowerShell 本来の改行を活用します。</span><span class="sxs-lookup"><span data-stu-id="101ab-311">Take advantage of PowerShell's natural line break opportunities, like after pipe (`|`) characters, opening braces, parentheses, and brackets.</span></span>

### <a name="avoid-using-powershell-prompts-in-examples"></a><span data-ttu-id="101ab-312">例の中で PowerShell プロンプトを使用しないようにする</span><span class="sxs-lookup"><span data-stu-id="101ab-312">Avoid using PowerShell prompts in examples</span></span>

<span data-ttu-id="101ab-313">プロンプト文字列の使用は推奨されていません。コマンド ラインの使い方を示すシナリオに限定して使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-313">Use of the prompt string is discouraged and should be limited to scenarios that are meant to illustrate command line usage.</span></span> <span data-ttu-id="101ab-314">これらの例の大半では、プロンプト文字列を `PS>` にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-314">For most of these examples, the prompt string should be `PS>`.</span></span> <span data-ttu-id="101ab-315">このプロンプトは OS 固有のインジケーターに依存しません。</span><span class="sxs-lookup"><span data-stu-id="101ab-315">This prompt is independent of OS-specific indicators.</span></span>

<span data-ttu-id="101ab-316">プロンプトが必要なのは、プロンプトを変更するコマンドを例をあげて説明する場合、または説明しているシナリオでパスの表示に意味がある場合です。</span><span class="sxs-lookup"><span data-stu-id="101ab-316">Prompts are required for examples that illustrate commands that alter the prompt or when the path displayed is significant to the scenario being illustrated.</span></span> <span data-ttu-id="101ab-317">次の例では、レジストリ プロバイダーの使用時にプロンプトがどのように変化するかを示しています。</span><span class="sxs-lookup"><span data-stu-id="101ab-317">The following example illustrates how the prompt changes when using the Registry provider.</span></span>

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

### <a name="do-not-use-aliases-in-examples"></a><span data-ttu-id="101ab-318">例の中で別名を使用しない</span><span class="sxs-lookup"><span data-stu-id="101ab-318">Do not use aliases in examples</span></span>

<span data-ttu-id="101ab-319">別名について具体的に説明する場合を除いて、常にすべてのコマンドレットとパラメーターの完全名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-319">You should always use the full name of all cmdlets and parameters unless you are specifically talking about the alias.</span></span> <span data-ttu-id="101ab-320">コマンドレットとパラメーターの名前では、パスカル ケースの適切な名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="101ab-320">Cmdlet and parameter names must use the proper Pascal-cased names.</span></span>

### <a name="using-parameters-in-examples"></a><span data-ttu-id="101ab-321">例でのパラメーターの使用</span><span class="sxs-lookup"><span data-stu-id="101ab-321">Using parameters in examples</span></span>

<span data-ttu-id="101ab-322">位置パラメーターの使用は避けてください。</span><span class="sxs-lookup"><span data-stu-id="101ab-322">Avoid using positional parameters.</span></span> <span data-ttu-id="101ab-323">通常は、パラメーターが位置パラメーターの場合でも、例では常にパラメーターの名前を含めるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="101ab-323">In general, you should always include the parameter name in an example, even if the parameter is positional.</span></span> <span data-ttu-id="101ab-324">これにより、例の中で混同が発生する機会が減少します。</span><span class="sxs-lookup"><span data-stu-id="101ab-324">This reduces the chance of confusion in your examples.</span></span>

## <a name="next-steps"></a><span data-ttu-id="101ab-325">次のステップ</span><span class="sxs-lookup"><span data-stu-id="101ab-325">Next steps</span></span>

[<span data-ttu-id="101ab-326">コマンドレット編集リファレンス</span><span class="sxs-lookup"><span data-stu-id="101ab-326">Editing cmdlet reference</span></span>](editing-cmdlet-ref.md)

<!-- External URLs -->
[platyPS]: https://github.com/PowerShell/platyPS
[markdig]: https://github.com/lunet-io/markdig
[CommonMark]: https://spec.commonmark.org/
[atx]: https://github.github.com/gfm/#atx-headings
[pascal-case]: https://en.wikipedia.org/wiki/PascalCase
[reflow]: https://marketplace.visualstudio.com/items?itemName=marvhen.reflow-markdown
