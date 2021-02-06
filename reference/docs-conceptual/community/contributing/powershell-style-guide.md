---
title: PowerShell ドキュメントのスタイル ガイド
description: この記事では、PowerShell ドキュメントを記述するためのスタイル規則について説明します。
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: 6f23f63cffc9fed9cbbcf84539875bfaf4247732
ms.sourcegitcommit: 61765d08321623743dc5db5367160f6982fe7857
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "99599278"
---
# <a name="powershell-docs-style-guide"></a><span data-ttu-id="6ba2d-103">PowerShell ドキュメントのスタイル ガイド</span><span class="sxs-lookup"><span data-stu-id="6ba2d-103">PowerShell-Docs style guide</span></span>

<span data-ttu-id="6ba2d-104">この記事では、PowerShell ドキュメントのコンテンツに固有のスタイル ガイダンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-104">This article provides style guidance specific to the PowerShell-Docs content.</span></span> <span data-ttu-id="6ba2d-105">[概要](overview.md#get-started-writing-docs)に記載されている情報に基づいています。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-105">It builds on the information outlined in the [Overview](overview.md#get-started-writing-docs).</span></span>

## <a name="product-terminology"></a><span data-ttu-id="6ba2d-106">製品に関する用語</span><span class="sxs-lookup"><span data-stu-id="6ba2d-106">Product Terminology</span></span>

<span data-ttu-id="6ba2d-107">PowerShell にはいくつかのバリエーションがあります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-107">There are several variants of PowerShell.</span></span>

- <span data-ttu-id="6ba2d-108">**PowerShell** - これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-108">**PowerShell** - This is the default.</span></span> <span data-ttu-id="6ba2d-109">PowerShell 7 以降を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-109">We consider PowerShell 7 and beyond to be the one, true PowerShell.</span></span>
- <span data-ttu-id="6ba2d-110">**PowerShell Core** - .NET Core 上で構築される PowerShell です。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-110">**PowerShell Core** - PowerShell built on .NET Core.</span></span> <span data-ttu-id="6ba2d-111">**コア** という用語の使用は、Windows PowerShell と区別する必要がある場合に限定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-111">Usage of the term **Core** should be limited to cases where it's necessary to differentiate it from Windows PowerShell.</span></span>
- <span data-ttu-id="6ba2d-112">**Windows PowerShell** - .NET Framework 上で構築される PowerShell です。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-112">**Windows PowerShell** - PowerShell built on .NET Framework.</span></span> <span data-ttu-id="6ba2d-113">Windows PowerShell は Windows にのみ付属しており、完全な Framework が必要です。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-113">Windows PowerShell ships only on Windows and requires the complete Framework.</span></span>

  <span data-ttu-id="6ba2d-114">一般に、ドキュメント内の "Windows PowerShell" への参照は _PowerShell_ に変更できます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-114">In general, references to "Windows PowerShell" in documentation can be changed to _PowerShell_.</span></span>
  <span data-ttu-id="6ba2d-115">_Windows powershell_ 固有の動作について説明する場合は、"windows powershell" を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-115">"Windows PowerShell" should be used when _Windows PowerShell_-specific behavior is being discussed.</span></span>

<span data-ttu-id="6ba2d-116">関連製品</span><span class="sxs-lookup"><span data-stu-id="6ba2d-116">Related products</span></span>

- <span data-ttu-id="6ba2d-117">**Visual Studio Code (VS Code)** -これは Microsoft の無料のオープンソースエディターです。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-117">**Visual Studio Code (VS Code)** - This is Microsoft's free, open-source editor.</span></span> <span data-ttu-id="6ba2d-118">最初のメンションでは、完全な名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-118">At first mention, the full name should be used.</span></span> <span data-ttu-id="6ba2d-119">その後で、**VS Code** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-119">After that you may use **VS Code**.</span></span> <span data-ttu-id="6ba2d-120">"VSCode" は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-120">Don't use "VSCode".</span></span>
- <span data-ttu-id="6ba2d-121">**Visual Studio Code 用の PowerShell 拡張機能** - この拡張機能によって VS Code が PowerShell 用の推奨 IDE に切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-121">**PowerShell Extension for Visual Studio Code** - The extension turns VS Code into the preferred IDE for PowerShell.</span></span> <span data-ttu-id="6ba2d-122">最初のメンションでは、完全な名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-122">At first mention, the full name should be used.</span></span> <span data-ttu-id="6ba2d-123">その後で、**PowerShell 拡張機能** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-123">After that you may use **PowerShell extension**.</span></span>
- <span data-ttu-id="6ba2d-124">**Azure PowerShell** - これは、Azure サービスを管理するために使用される PowerShell モジュールのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-124">**Azure PowerShell** - This is the collection of PowerShell modules used to manage Azure services.</span></span>
- <span data-ttu-id="6ba2d-125">**Azure Stack PowerShell** - これは、Microsoft のハイブリッド クラウド ソリューションを管理するために使用される PowerShell モジュールのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-125">**Azure Stack PowerShell** - This is the collection of PowerShell modules used to manage Microsoft's hybrid cloud solution.</span></span>

## <a name="markdown-specifics"></a><span data-ttu-id="6ba2d-126">Markdown の詳細</span><span class="sxs-lookup"><span data-stu-id="6ba2d-126">Markdown specifics</span></span>

<span data-ttu-id="6ba2d-127">Microsoft のドキュメントを構築する Microsoft Open Publishing System (OPS) では、[markdig][] を使用して Markdown ドキュメントが処理されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-127">The Microsoft Open Publishing System (OPS) that builds our documentation uses [markdig][] to process the Markdown documents.</span></span> <span data-ttu-id="6ba2d-128">markdig では、最新の [CommonMark][] 仕様の規則に基づいてドキュメントが解析されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-128">Markdig parses the documents based on the rules of the latest [CommonMark][] specification.</span></span>

<span data-ttu-id="6ba2d-129">新しい CommonMark 仕様では、いくつかの Markdown 要素の構築に関する規定が非常に厳密になっています。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-129">The new CommonMark spec is much stricter about the construction of some Markdown elements.</span></span> <span data-ttu-id="6ba2d-130">このドキュメントの細部に、細心の注意を払ってください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-130">Pay close attention to the details provided in this document.</span></span>

### <a name="blank-lines-spaces-and-tabs"></a><span data-ttu-id="6ba2d-131">空白行、スペース、およびタブ</span><span class="sxs-lookup"><span data-stu-id="6ba2d-131">Blank lines, spaces, and tabs</span></span>

<span data-ttu-id="6ba2d-132">空白行は、Markdown 内のブロックが終わることも示します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-132">Blank lines also signal the end of a block in Markdown.</span></span> <span data-ttu-id="6ba2d-133">異なる種類の Markdown ブロックの間 (段落とリストの間や段落とヘッダーの間など) には、単一の空白行が必要です。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-133">There should be a single blank between Markdown blocks of different types (for example, between a paragraph and a list or header).</span></span>

<span data-ttu-id="6ba2d-134">HTML では、連続した複数の空白行が1つの空白行として表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-134">Multiple consecutive blank lines render as a single blank line in HTML.</span></span> <span data-ttu-id="6ba2d-135">目的はありません。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-135">They serve no purpose.</span></span>
<span data-ttu-id="6ba2d-136">コードブロック内では、連続する空白行によってコードブロックが分割されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-136">Within a code block, consecutive blank lines break the code block.</span></span>

<span data-ttu-id="6ba2d-137">行の末尾の余分なスペースを削除してください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-137">Remove extra spaces at the end of lines.</span></span>

> [!NOTE]
> <span data-ttu-id="6ba2d-138">Markdown では、スペースが重要です。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-138">Spacing is significant in Markdown.</span></span> <span data-ttu-id="6ba2d-139">常にハード タブではなくスペースを使用してください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-139">Always uses spaces instead of hard tabs.</span></span> <span data-ttu-id="6ba2d-140">Markdown のレンダリング方法は、末尾のスペースによって変更できます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-140">Trailing spaces can change how Markdown renders.</span></span>

### <a name="titles-and-headings"></a><span data-ttu-id="6ba2d-141">タイトルと見出し</span><span class="sxs-lookup"><span data-stu-id="6ba2d-141">Titles and headings</span></span>

<span data-ttu-id="6ba2d-142">[ATX 見出し][atx]のみを使用します (`=` または `-` スタイルのヘッダーではなく # スタイルにします)。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-142">Only use [ATX headings][atx] (# style, as opposed to `=` or `-` style headers).</span></span>

- <span data-ttu-id="6ba2d-143">文の先頭で大文字を使用する - 固有名詞、タイトル、ヘッダーの 1 文字目のみ大文字にします</span><span class="sxs-lookup"><span data-stu-id="6ba2d-143">Use sentence case - only proper nouns and the first letter of a title or header should be capitalized</span></span>
- <span data-ttu-id="6ba2d-144">`#` と見出しの最初の文字の間には単一のスペースが必要</span><span class="sxs-lookup"><span data-stu-id="6ba2d-144">There must be a single space between the `#` and the first letter of the heading</span></span>
- <span data-ttu-id="6ba2d-145">見出しの上下は単一の空白行にする</span><span class="sxs-lookup"><span data-stu-id="6ba2d-145">Headings should be surrounded by a single blank line</span></span>
- <span data-ttu-id="6ba2d-146">ドキュメントごとの H1 は 1 つのみにする</span><span class="sxs-lookup"><span data-stu-id="6ba2d-146">Only one H1 per document</span></span>
- <span data-ttu-id="6ba2d-147">ヘッダーのレベルは 1 つずつ増分する。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-147">Header levels should increment by one.</span></span> <span data-ttu-id="6ba2d-148">レベルをスキップしない</span><span class="sxs-lookup"><span data-stu-id="6ba2d-148">Don't skip levels</span></span>
- <span data-ttu-id="6ba2d-149">ヘッダーで太字またはその他のマークアップを使用しない</span><span class="sxs-lookup"><span data-stu-id="6ba2d-149">Don't use bold or other markup in headers</span></span>

### <a name="limit-line-length-to-100-characters"></a><span data-ttu-id="6ba2d-150">行の長さを 100 文字に制限する</span><span class="sxs-lookup"><span data-stu-id="6ba2d-150">Limit line length to 100 characters</span></span>

<span data-ttu-id="6ba2d-151">これは、概念記事とコマンドレット リファレンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-151">This applies to conceptual articles and cmdlet reference.</span></span> <span data-ttu-id="6ba2d-152">行の長さを制限することで、git diff と履歴が読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-152">Limiting the line length improves the readability of git diffs and history.</span></span> <span data-ttu-id="6ba2d-153">さらに、他の執筆者が投稿を簡単に行えるようにします。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-153">It also makes it easier for other writers to make contributions.</span></span>

<span data-ttu-id="6ba2d-154">Visual Studio Code の [Reflow Markdown][reflow] 拡張機能を使用すると、規定の行の長さに合うように段落が簡単にリフロ―されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-154">Use the [Reflow Markdown][reflow] extension in Visual Studio Code to easily reflow paragraphs to fit the prescribed line length.</span></span>

<span data-ttu-id="6ba2d-155">About_topics の長さは 80 文字に制限されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-155">About_topics are limited to 80 characters.</span></span> <span data-ttu-id="6ba2d-156">詳細については、「 [About_ ファイルの書式設定](#formatting-about_-files)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-156">For more specific information, see [Formatting About_ files](#formatting-about_-files).</span></span>

### <a name="lists"></a><span data-ttu-id="6ba2d-157">リスト</span><span class="sxs-lookup"><span data-stu-id="6ba2d-157">Lists</span></span>

<span data-ttu-id="6ba2d-158">リストに複数の文または段落が含まれている場合は、リストではなくサブレベルヘッダーを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-158">If your list contains multiple sentences or paragraphs, consider using a sublevel header rather than a list.</span></span>

<span data-ttu-id="6ba2d-159">リストの上下は単一の空白行にします。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-159">List should be surrounded by a single blank line.</span></span>

#### <a name="unordered-lists"></a><span data-ttu-id="6ba2d-160">箇条書きリスト</span><span class="sxs-lookup"><span data-stu-id="6ba2d-160">Unordered lists</span></span>

<span data-ttu-id="6ba2d-161">複数の文が含まれている場合を除き、ピリオドでリスト項目を終了しないでください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-161">Don't end list items with a period unless they contain multiple sentences.</span></span> <span data-ttu-id="6ba2d-162">リスト項目の箇条書き記号には、ハイフン文字 (`-`) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-162">Use the hyphen character (`-`) for list item bullets.</span></span> <span data-ttu-id="6ba2d-163">これにより、アスタリスク [`*`] を使用する、太字または斜体のマークアップとの混同を回避できます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-163">This avoids confusion with bold or italic markup that uses the asterisk [`*`].</span></span> <span data-ttu-id="6ba2d-164">段落またはその他の要素を箇条書き項目の下に含めるには、改行を挿入し、インデントを箇条書き記号の後ろの最初の文字に揃えます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-164">To include a paragraph or other elements under a bullet item, insert a line break and align indentation with the first character after the bullet.</span></span>

<span data-ttu-id="6ba2d-165">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-165">For example:</span></span>

```markdown
This is a list that contain child elements under a bullet item.

- First bullet item

  Sentence explaining the first bullet.

  - Child bullet item

    Sentence explaining the child bullet.

- Second bullet item
- Third bullet item
```

<span data-ttu-id="6ba2d-166">これは箇条書き項目の下にある子要素を含むリストです。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-166">This is a list that contains child elements under a bullet item.</span></span>

- <span data-ttu-id="6ba2d-167">最初の箇条書き項目</span><span class="sxs-lookup"><span data-stu-id="6ba2d-167">First bullet item</span></span>

  <span data-ttu-id="6ba2d-168">最初の箇条書きの内容文。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-168">Sentence explaining the first bullet.</span></span>

  - <span data-ttu-id="6ba2d-169">子の箇条書き項目</span><span class="sxs-lookup"><span data-stu-id="6ba2d-169">Child bullet item</span></span>

    <span data-ttu-id="6ba2d-170">子の箇条書きを説明する文。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-170">Sentence explaining the child bullet.</span></span>

- <span data-ttu-id="6ba2d-171">2 番目の箇条書き項目</span><span class="sxs-lookup"><span data-stu-id="6ba2d-171">Second bullet item</span></span>
- <span data-ttu-id="6ba2d-172">3 番目の箇条書き項目</span><span class="sxs-lookup"><span data-stu-id="6ba2d-172">Third bullet item</span></span>

#### <a name="ordered-lists"></a><span data-ttu-id="6ba2d-173">番号付きリスト</span><span class="sxs-lookup"><span data-stu-id="6ba2d-173">Ordered lists</span></span>

<span data-ttu-id="6ba2d-174">段落またはその他の要素を番号付き項目の下に含めるには、インデントを項目番号の後ろの最初の文字に揃えます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-174">To include a paragraph or other elements under a numbered item, align indentation with the first character after the item number.</span></span> <span data-ttu-id="6ba2d-175">番号付きリストのすべての項目では、項目ごとに増分される番号ではなく、番号 `1.` を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-175">All items in a numbered listed should use the number `1.` rather than incrementing each item.</span></span> <span data-ttu-id="6ba2d-176">この値は、Markdown によって自動的に増分されて表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-176">Markdown rendering increments the value automatically.</span></span> <span data-ttu-id="6ba2d-177">これにより、項目を簡単に並べ替えることができ、下位コンテンツのインデントが統一されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-177">This makes reordering items easier and standardizes the indentation of subordinate content.</span></span>

<span data-ttu-id="6ba2d-178">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-178">For example:</span></span>

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

<span data-ttu-id="6ba2d-179">結果の Markdown は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-179">The resulting Markdown is rendered as follows:</span></span>

1. <span data-ttu-id="6ba2d-180">最初の要素では、1. の後ろに単一のスペースを挿入します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-180">For the first element, insert a single space after the 1.</span></span> <span data-ttu-id="6ba2d-181">長い文は次の行に折り返す必要があり、次の行の先頭は番号付きリスト マーカーの後ろの最初の文字と揃える必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-181">Long sentences should be wrapped to the next line and must line up with the first character after the numbered list marker.</span></span>

   <span data-ttu-id="6ba2d-182">(この例のように) 2 つ目の要素を含めるには、1 つ目の要素の後に改行を挿入し、インデントを合わせます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-182">To include a second element (like this one), insert a line break after the first and align indentations.</span></span> <span data-ttu-id="6ba2d-183">2 つ目の要素のインデントは、番号付きリスト マーカーの後ろの最初の文字と揃える必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-183">The indentation of the second element must line up with the first character after the numbered list marker.</span></span> <span data-ttu-id="6ba2d-184">このような 1 桁の番号の項目では、列 4 にインデントします。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-184">For single digit items, like this one, you indent to column 4.</span></span> <span data-ttu-id="6ba2d-185">2 桁の番号の項目 (項目番号 10 など) では、列 5 にインデントします。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-185">For double digits items, for example item number 10, you indent to column 5.</span></span>

1. <span data-ttu-id="6ba2d-186">次の番号付き項目は、ここから始まります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-186">The next numbered item starts here.</span></span>

### <a name="images"></a><span data-ttu-id="6ba2d-187">イメージ</span><span class="sxs-lookup"><span data-stu-id="6ba2d-187">Images</span></span>

<span data-ttu-id="6ba2d-188">画像を含める構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-188">The syntax to include an image is:</span></span>

```markdown
![[alt text]](<folderPath>)

Example:
![Introduction](./media/overview/Introduction.png)
```

<span data-ttu-id="6ba2d-189">`alt text` は画像の簡単な説明であり、`<folder path>` は画像の相対パスです。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-189">Where `alt text` is a brief description of the image and `<folder path>` is a relative path to the image.</span></span> <span data-ttu-id="6ba2d-190">代替テキストは、視覚障碍がある読者のために必要です。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-190">Alternate text is required for screen readers for the visually impaired.</span></span>

<span data-ttu-id="6ba2d-191">画像は `media/<article-name>` 、アーティクルを含むフォルダー内のフォルダーに格納されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-191">Images should be stored in a `media/<article-name>` folder within the folder containing the article.</span></span>
<span data-ttu-id="6ba2d-192">記事間で画像を共有しないでください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-192">Don't share images between articles.</span></span> <span data-ttu-id="6ba2d-193">`media` フォルダーの下に、記事のファイル名と一致するフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-193">Create a folder that matches the filename of your article under the `media` folder.</span></span> <span data-ttu-id="6ba2d-194">その記事のイメージをその新しいフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-194">Copy the images for that article to that new folder.</span></span> <span data-ttu-id="6ba2d-195">複数の記事でイメージが使用されている場合は、各イメージ フォルダーにそのイメージ ファイルのコピーを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-195">If an image is used by multiple articles, each image folder must have a copy of that image file.</span></span> <span data-ttu-id="6ba2d-196">これにより、ある記事でイメージを変更しても、別の記事に影響を与えることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-196">This practice prevents a change to an image in one article affecting another article.</span></span>

<span data-ttu-id="6ba2d-197">サポートされているイメージファイルの種類は、、、、 `*.png` `*.gif` `*.jpeg` `*.jpg` 、です。 `*.svg`</span><span class="sxs-lookup"><span data-stu-id="6ba2d-197">The following image file types are supported: `*.png`, `*.gif`, `*.jpeg`, `*.jpg`, `*.svg`</span></span>

### <a name="markdown-extensions-supported-by-open-publishing"></a><span data-ttu-id="6ba2d-198">Open Publishing でサポートされる Markdown の拡張機能</span><span class="sxs-lookup"><span data-stu-id="6ba2d-198">Markdown extensions supported by Open Publishing</span></span>

<span data-ttu-id="6ba2d-199">[Microsoft Docs Authoring Pack](/contribute/how-to-write-docs-auth-pack)には、公開システム固有の機能をサポートするツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-199">The [Microsoft Docs Authoring Pack](/contribute/how-to-write-docs-auth-pack) contains tools that support features unique to our publishing system.</span></span> <span data-ttu-id="6ba2d-200">アラートは、コンテンツの有意性を強調する色とアイコンを使用して docs.microsoft.com に表示するブロック引用符を作成するための Markdown 拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-200">Alerts are a Markdown extension to create blockquotes that render on docs.microsoft.com with colors and icons that highlight the significance of the content.</span></span> <span data-ttu-id="6ba2d-201">次の種類のアラートがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-201">The following alert types are supported:</span></span>

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

<span data-ttu-id="6ba2d-202">これらのアラートは docs.microsoft.com 上で次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-202">These alerts look like this on docs.microsoft.com:</span></span>

<span data-ttu-id="6ba2d-203">メモブロック</span><span class="sxs-lookup"><span data-stu-id="6ba2d-203">Note block</span></span>

> [!NOTE]
> <span data-ttu-id="6ba2d-204">Information the user should notice even if skimming.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-204">Information the user should notice even if skimming.</span></span>

<span data-ttu-id="6ba2d-205">ヒントブロック</span><span class="sxs-lookup"><span data-stu-id="6ba2d-205">Tip block</span></span>

> [!TIP]
> <span data-ttu-id="6ba2d-206">Optional information to help a user be more successful.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-206">Optional information to help a user be more successful.</span></span>

<span data-ttu-id="6ba2d-207">重要なブロック</span><span class="sxs-lookup"><span data-stu-id="6ba2d-207">Important block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ba2d-208">Essential information required for user success.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-208">Essential information required for user success.</span></span>

<span data-ttu-id="6ba2d-209">注意ブロック</span><span class="sxs-lookup"><span data-stu-id="6ba2d-209">Caution block</span></span>

> [!CAUTION]
> <span data-ttu-id="6ba2d-210">Negative potential consequences of an action.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-210">Negative potential consequences of an action.</span></span>

<span data-ttu-id="6ba2d-211">警告ブロック</span><span class="sxs-lookup"><span data-stu-id="6ba2d-211">Warning block</span></span>

> [!WARNING]
> <span data-ttu-id="6ba2d-212">Dangerous certain consequences of an action. (ある行動で起こるいくつかの危険な結果。)</span><span class="sxs-lookup"><span data-stu-id="6ba2d-212">Dangerous certain consequences of an action.</span></span>

### <a name="hyperlinks"></a><span data-ttu-id="6ba2d-213">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="6ba2d-213">Hyperlinks</span></span>

- <span data-ttu-id="6ba2d-214">ハイパーリンクには Markdown 構文を使用する必要があり `[friendlyname](url-or-path)` ます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-214">Hyperlinks must use Markdown syntax `[friendlyname](url-or-path)`.</span></span> <span data-ttu-id="6ba2d-215">[リンク参照][linkref] がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-215">[Link references][linkref] are supported.</span></span>
- <span data-ttu-id="6ba2d-216">公開システムでは、次の3種類のリンクがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-216">The publishing system supports three types of links:</span></span>
  - <span data-ttu-id="6ba2d-217">URL リンク</span><span class="sxs-lookup"><span data-stu-id="6ba2d-217">URL links</span></span>
  - <span data-ttu-id="6ba2d-218">ファイルリンク</span><span class="sxs-lookup"><span data-stu-id="6ba2d-218">File links</span></span>
  - <span data-ttu-id="6ba2d-219">相互参照リンク</span><span class="sxs-lookup"><span data-stu-id="6ba2d-219">Cross-reference links</span></span>
- <span data-ttu-id="6ba2d-220">Docs.microsoft.com の他の記事へのリンクは、サイト相対パスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-220">Links to other articles on docs.microsoft.com must be site-relative paths</span></span>
- <span data-ttu-id="6ba2d-221">外部 web サイトへのすべての Url は、ターゲットサイトで有効でない場合を除き、HTTPS を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-221">All URLs to external websites should use HTTPS unless that isn't valid for the target site.</span></span>
- <span data-ttu-id="6ba2d-222">リンクにはフレンドリ名が必要です。通常はリンクアーティクルのタイトルです</span><span class="sxs-lookup"><span data-stu-id="6ba2d-222">Links must have a friendly name, usually the title of the linked article</span></span>
- <span data-ttu-id="6ba2d-223">下部にある [ _関連リンク_ ] セクションのすべての項目はハイパーリンクにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-223">All items in the _Related links_ section at the bottom should be hyperlinked</span></span>
- <span data-ttu-id="6ba2d-224">ハイパーリンクの角かっこ内には、バックティック、太字、またはその他のマークアップを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-224">Don't use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>
- <span data-ttu-id="6ba2d-225">特定の URI をドキュメント化するときに、ベア Url を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-225">Bare URLs may be used when you're documenting a specific URI.</span></span> <span data-ttu-id="6ba2d-226">URI は、バックティックで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-226">The URI must be enclosed in backticks.</span></span> <span data-ttu-id="6ba2d-227">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-227">For example:</span></span>

  ```markdown
  By default, if you don't specify this parameter, the DMTF standard resource URI
  `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.
  ```

#### <a name="linking-to-other-content-on-docsmicrosoftcom"></a><span data-ttu-id="6ba2d-228">Docs.microsoft.com の他のコンテンツへのリンク</span><span class="sxs-lookup"><span data-stu-id="6ba2d-228">Linking to other content on docs.microsoft.com</span></span>

- <span data-ttu-id="6ba2d-229">Docs.microsoft.com の他の記事への **URL リンク** は、サイト相対パスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-229">**URL links** to other articles on docs.microsoft.com must be site-relative paths.</span></span> <span data-ttu-id="6ba2d-230">相対リンクを作成する最も簡単な方法は、ブラウザーから URL をコピーし、 `https://docs.microsoft.com/en-us` markdown に貼り付ける値から削除することです。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-230">The simplest way to create a relative link is to copy the URL from your browser then remove `https://docs.microsoft.com/en-us` from the value you paste into markdown.</span></span> <span data-ttu-id="6ba2d-231">Microsoft のプロパティの Url にロケールを含めないで `/en-us` ください (url から削除)。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-231">Don't include locales in URLs on Microsoft properties (remove `/en-us` from URL).</span></span> <span data-ttu-id="6ba2d-232">URL から不要なクエリパラメーターを削除します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-232">Remove any unnecessary query parameters from the URL.</span></span> <span data-ttu-id="6ba2d-233">削除する必要がある例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-233">Examples that should be removed:</span></span>

  - <span data-ttu-id="6ba2d-234">`?view=powershell-5.1` -PowerShell の特定のバージョンへのリンクに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-234">`?view=powershell-5.1` - used to link to a specific version of PowerShell</span></span>
  - <span data-ttu-id="6ba2d-235">`?redirectedfrom=MSDN` -古い記事から新しい場所にリダイレクトされるときに URL に追加されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-235">`?redirectedfrom=MSDN` - added to the URL when you get redirected from an old article to its new location</span></span>

  <span data-ttu-id="6ba2d-236">ドキュメントの特定のバージョンにリンクする必要がある場合は、クエリ文字列にパラメーターを追加する必要があり `&preserve_view=true` ます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-236">If you need to link to a specific version of a document, then you need to add the `&preserve_view=true` parameter to the query string.</span></span> <span data-ttu-id="6ba2d-237">例: `?view=powershell-5.1&preserve_view=true`</span><span class="sxs-lookup"><span data-stu-id="6ba2d-237">For example: `?view=powershell-5.1&preserve_view=true`</span></span>

- <span data-ttu-id="6ba2d-238">**ファイルリンク** は、ある参照記事から別の参照記事へのリンク、またはある概念記事から別の参照アーティクルへのリンクに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-238">A **file link** is used to link from one reference article to another, or from one conceptual article to another.</span></span> <span data-ttu-id="6ba2d-239">PowerShell の特定のバージョンに関する参照記事にリンクする必要がある場合は、URL リンクを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-239">If you need to link to a reference article for a specific version of PowerShell, then you must use a URL link.</span></span>

  - <span data-ttu-id="6ba2d-240">ファイルリンクには、相対ファイルパスが含まれています (例: `../folder/file.md` )。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-240">File links contain a relative file path (for example: `../folder/file.md`)</span></span>
  - <span data-ttu-id="6ba2d-241">すべてのファイルパスはスラッシュ () 文字を使用します `/`</span><span class="sxs-lookup"><span data-stu-id="6ba2d-241">All file paths use forward-slash (`/`) characters</span></span>

- <span data-ttu-id="6ba2d-242">**相互参照リンク** は、公開システムによってサポートされる特別な機能です。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-242">**Cross-reference links** are a special feature supported by the publishing system.</span></span> <span data-ttu-id="6ba2d-243">概念説明の記事で相互参照リンクを使用して、.NET API またはコマンドレットリファレンスにリンクすることができます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-243">You can use cross-reference links in conceptual articles to link to .NET API or cmdlet reference.</span></span>

  <span data-ttu-id="6ba2d-244">.NET API リファレンスへのリンクについては、中央の共同作成者ガイドの [ドキュメントでリンクを使用する方法](/contribute/how-to-write-links#xref-cross-reference-links) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-244">For links to .NET API reference, see [Use links in documentation](/contribute/how-to-write-links#xref-cross-reference-links) in the central Contributor Guide.</span></span>

  <span data-ttu-id="6ba2d-245">コマンドレットリファレンスへのリンクの形式は次のとおり `xref:<module-name>.<cmdlet-name>` です。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-245">Links to cmdlet reference have the following format: `xref:<module-name>.<cmdlet-name>`.</span></span> <span data-ttu-id="6ba2d-246">たとえば、を使用して、 `Get-Content` **管理** モジュールのコマンドレットにリンクします。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-246">For example, to link to the `Get-Content` cmdlet in the **Microsoft.PowerShell.Management** module.</span></span>

  `[Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)`

<span data-ttu-id="6ba2d-247">ディープリンクは、URL リンクとファイルリンクの両方で使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-247">Deep linking is allowed on both URL and file links.</span></span> <span data-ttu-id="6ba2d-248">アンカーをターゲットパスの末尾に追加します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-248">Add the anchor to the end of the target path.</span></span>
<span data-ttu-id="6ba2d-249">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-249">For example:</span></span>

- `[about_Splatting](about_Splatting.md#splatting-with-arrays)`
- `[custom key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)`

<span data-ttu-id="6ba2d-250">詳細については、 [ドキュメントの「リンクを使用する](/contribute/how-to-write-links)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-250">For more information, see [Use links in documentation](/contribute/how-to-write-links).</span></span>

## <a name="formatting-command-syntax-elements"></a><span data-ttu-id="6ba2d-251">コマンド構文要素の書式設定</span><span class="sxs-lookup"><span data-stu-id="6ba2d-251">Formatting command syntax elements</span></span>

- <span data-ttu-id="6ba2d-252">コマンドレットとパラメーターには常に完全名を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-252">Always use the full name for cmdlets and parameters.</span></span> <span data-ttu-id="6ba2d-253">別名を明示的に示す場合を除き、エイリアスの使用は避けてください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-253">Avoid using aliases unless you're specifically demonstrating the alias.</span></span>

- <span data-ttu-id="6ba2d-254">プロパティ、パラメーター、オブジェクト、型名、クラス名、クラスメソッドは **太字** にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-254">Property, parameter, object, type names, class names, class methods should be **bold**.</span></span>
  - <span data-ttu-id="6ba2d-255">プロパティとパラメーターの値は、バックティック () でラップする必要があり `` ` `` ます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-255">Property and parameter values should be wrapped in backticks (`` ` ``).</span></span>
  - <span data-ttu-id="6ba2d-256">かっこで囲まれたスタイルを使用して型を参照する場合は、backticks を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-256">When referring to types using the bracketed style, use backticks.</span></span> <span data-ttu-id="6ba2d-257">例: `[System.Io.FileInfo]`</span><span class="sxs-lookup"><span data-stu-id="6ba2d-257">For example: `[System.Io.FileInfo]`</span></span>

- <span data-ttu-id="6ba2d-258">言語キーワード、コマンドレット名、関数、変数、ネイティブ Exe、ファイルパス、およびインライン構文の例は、バックティック () 文字でラップする必要があり `` ` `` ます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-258">Language keywords, cmdlet names, functions, variables, native EXEs, file paths, and inline syntax examples should be wrapped in backtick (`` ` ``) characters.</span></span>

  <span data-ttu-id="6ba2d-259">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-259">For example:</span></span>

  ~~~markdown
  The following code uses `Get-ChildItem` to list the contents of `C:\Windows` and assigns
  the output to the `$files` variable.

  ```powershell
  $files = Get-ChildItem C:\Windows
  ```
  ~~~

  - <span data-ttu-id="6ba2d-260">名前でパラメーターを参照する場合、名前は **太字** にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-260">When referring to a parameter by name, the name should be **bold**.</span></span> <span data-ttu-id="6ba2d-261">パラメーターをハイフン プレフィックスと共に使用する場合は、パラメーターをバッククォートで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-261">When illustrating the use of a parameter with the hyphen prefix, the parameter should be wrapped in backticks.</span></span> <span data-ttu-id="6ba2d-262">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-262">For example:</span></span>

    ```markdown
    The parameter's name is **Name**, but it's typed as `-Name` when used on the command
    line as a parameter.
    ```

  - <span data-ttu-id="6ba2d-263">外部コマンドの使用例を示す場合は、例をバッククォートで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-263">When showing example usage of an external command, the example should be wrapped in backticks.</span></span>
    <span data-ttu-id="6ba2d-264">ネイティブコマンドには、常にファイル拡張子を含めます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-264">Always include the file extension in the native command.</span></span> <span data-ttu-id="6ba2d-265">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-265">For example:</span></span>

    ```markdown
    To start the spooler service on a remote computer named DC01, you type `sc.exe \\DC01 start spooler`.
    ```

    <span data-ttu-id="6ba2d-266">ファイル拡張子を含めることで、PowerShell のコマンドの優先順位に従って正しいコマンドが実行されるようになります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-266">Including the file extension ensures that the correct command is executed according to PowerShell's command precedence.</span></span>

- <span data-ttu-id="6ba2d-267">概念説明の記事 (リファレンス コンテンツではなく) を記述する場合は、コマンドレット名の最初のインスタンスをコマンドレットのドキュメントにハイパーリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-267">When writing a conceptual article (as opposed to reference content), the first instance of a cmdlet name should be hyperlinked to the cmdlet documentation.</span></span> <span data-ttu-id="6ba2d-268">ハイパーリンクの角かっこ内には、バックティック、太字、またはその他のマークアップを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-268">Don't use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>

  <span data-ttu-id="6ba2d-269">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-269">For example:</span></span>

  ```markdown
  This [Write-Host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) cmdlet
  uses the **Object** parameter to ...
  ```

  <span data-ttu-id="6ba2d-270">詳細については、この記事の「 [ハイパーリンク](#hyperlinks) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-270">For more information, see [Hyperlinks](#hyperlinks) section of this article.</span></span>

## <a name="markdown-for-code-samples"></a><span data-ttu-id="6ba2d-271">コードサンプルの Markdown</span><span class="sxs-lookup"><span data-stu-id="6ba2d-271">Markdown for code samples</span></span>

<span data-ttu-id="6ba2d-272">Markdown は、次の 2 つの異なるコード スタイルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-272">Markdown supports two different code styles:</span></span>

- <span data-ttu-id="6ba2d-273">**コードの span (inline)** -1 つのバックティック ( `` ` `` ) 文字でマークされます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-273">**Code spans (inline)** - marked by a single backtick (`` ` ``) character.</span></span> <span data-ttu-id="6ba2d-274">スタンドアロンブロックとしてではなく、段落内で使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-274">Used within a paragraph rather than as a standalone block.</span></span>
- <span data-ttu-id="6ba2d-275">**コードブロック** -トリプルバックティック () 文字列で囲まれた複数行のブロック `` ``` `` 。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-275">**Code blocks** - a multi-line block surrounded by triple-backtick (`` ``` ``) strings.</span></span> <span data-ttu-id="6ba2d-276">コードブロックには、バックティックの後に言語ラベルを付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-276">Code blocks may also have a language label following the backticks.</span></span> <span data-ttu-id="6ba2d-277">言語ラベルを使用すると、コードブロックの内容に対して構文の強調表示が有効になります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-277">The language label enables syntax highlighting for the contents of the code block.</span></span>

<span data-ttu-id="6ba2d-278">すべてのコード ブロックは、コード フェンス内に含めるようにします。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-278">All code blocks should be contained in a code fence.</span></span> <span data-ttu-id="6ba2d-279">コードブロックにはインデントを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-279">Never use indentation for code blocks.</span></span> <span data-ttu-id="6ba2d-280">Markdown ではこのパターンを使用できますが、問題になる可能性があるため、回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-280">Markdown allows this pattern but it can be problematic and should be avoided.</span></span>

<span data-ttu-id="6ba2d-281">コードブロックは、3つのバックティック () コードフェンスで囲まれた1行以上のコードです `` ``` `` 。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-281">A code block is one or more lines of code surrounded by a triple-backtick (`` ``` ``) code fence.</span></span>
<span data-ttu-id="6ba2d-282">コード フェンス マーカーは、コード サンプルの前後にある独自の行に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-282">The code fence markers must be on their own line before and after the code sample.</span></span> <span data-ttu-id="6ba2d-283">コード ブロックの先頭にあるマーカーには、省略可能な言語ラベルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-283">The marker at the start of the code block may have an optional language label.</span></span> <span data-ttu-id="6ba2d-284">Microsoft の Open Publishing System (OPS) では、言語ラベルを使用して、構文の強調表示機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-284">Microsoft's Open Publishing System (OPS) uses the language label to support the syntax highlighting feature.</span></span>

<span data-ttu-id="6ba2d-285">サポートされている言語タグの完全な一覧については、共同作成者ガイドの「 [たジオフェンス型 code block](/contribute/code-in-docs#fenced-code-blocks) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-285">For a full list of supported language tags, see [Fenced code blocks](/contribute/code-in-docs#fenced-code-blocks) in the centralized contributor guide.</span></span>

<span data-ttu-id="6ba2d-286">また、OPS では、コード ブロックの内容をクリップボードにコピーする **[コピー]** ボタンも追加されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-286">OPS also adds a **Copy** button that copies the contents of the code block to the clipboard.</span></span> <span data-ttu-id="6ba2d-287">これにより、コードを簡単にスクリプトに貼り付けて、コードサンプルをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-287">This allows you to quickly paste the code into a script to test the code sample.</span></span> <span data-ttu-id="6ba2d-288">ただし、このドキュメントに記載されているすべての例は、そのとおりに実行するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-288">However, not all examples in our documentation are intended to be run as-is.</span></span> <span data-ttu-id="6ba2d-289">一部のコードブロックは、PowerShell の概念を簡単に図解したものです。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-289">Some code blocks are simple illustrations of a PowerShell concept.</span></span>

<span data-ttu-id="6ba2d-290">ドキュメントでは、3種類のコードブロックが使用されています。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-290">There are three types code blocks used in our documentation:</span></span>

1. <span data-ttu-id="6ba2d-291">構文ブロック</span><span class="sxs-lookup"><span data-stu-id="6ba2d-291">Syntax blocks</span></span>
1. <span data-ttu-id="6ba2d-292">説明用の例</span><span class="sxs-lookup"><span data-stu-id="6ba2d-292">Illustrative examples</span></span>
1. <span data-ttu-id="6ba2d-293">実行可能ファイルの例</span><span class="sxs-lookup"><span data-stu-id="6ba2d-293">Executable examples</span></span>

### <a name="syntax-code-blocks"></a><span data-ttu-id="6ba2d-294">構文コードブロック</span><span class="sxs-lookup"><span data-stu-id="6ba2d-294">Syntax code blocks</span></span>

<span data-ttu-id="6ba2d-295">構文コードブロックは、コマンドの構文構造を記述するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-295">Syntax code blocks are used to describe the syntactic structure of a command.</span></span> <span data-ttu-id="6ba2d-296">コードフェンスに言語タグを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-296">Don't use a language tag on the code fence.</span></span> <span data-ttu-id="6ba2d-297">この例は、`Get-Command` コマンドレットのすべての使用できるパラメーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-297">This example illustrates all the possible parameters of the `Get-Command` cmdlet.</span></span>

~~~markdown
```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
  [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax]
  [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
  [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```
~~~

<span data-ttu-id="6ba2d-298">この例では、`for` ステートメントを汎用的な用語で説明します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-298">This example describes the `for` statement in generalized terms:</span></span>

~~~markdown
```
for (<init>; <condition>; <repeat>)
{<statement list>}
```
~~~

### <a name="illustrative-examples"></a><span data-ttu-id="6ba2d-299">わかりやすい例</span><span class="sxs-lookup"><span data-stu-id="6ba2d-299">Illustrative examples</span></span>

<span data-ttu-id="6ba2d-300">わかりやすい例は、PowerShell の概念を説明するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-300">Illustrative examples are used to explain a PowerShell concept.</span></span> <span data-ttu-id="6ba2d-301">これらは、実行のためにクリップボードにコピーされることを意図していません。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-301">They aren't meant to be copied to the clipboard for execution.</span></span> <span data-ttu-id="6ba2d-302">これらは、簡単に型を簡単に理解できる単純な例に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-302">These are most commonly used for simple examples that are easy to type and easy to understand.</span></span> <span data-ttu-id="6ba2d-303">コードブロックには、PowerShell プロンプトと出力例を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-303">The code block can include the PowerShell prompt and example output.</span></span>

<span data-ttu-id="6ba2d-304">次に、PowerShell の比較演算子の簡単な例を示します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-304">Here's a simple example illustrating the PowerShell comparison operators.</span></span> <span data-ttu-id="6ba2d-305">このケースでは、閲覧者がこの例をコピーして実行することは想定していません。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-305">In this case, we don't intend the reader to copy and run this example.</span></span>

~~~markdown
```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS> 1,2,3 -eq 2
2

PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```
~~~

### <a name="executable-examples"></a><span data-ttu-id="6ba2d-306">実行可能ファイルの例</span><span class="sxs-lookup"><span data-stu-id="6ba2d-306">Executable examples</span></span>

<span data-ttu-id="6ba2d-307">複雑な例、またはコピーして実行することを意図した例では、次のブロックスタイルのマークアップを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-307">Complex examples, or examples that are intended to be copied and executed, should use the following block-style markup:</span></span>

~~~markdown
```powershell
<Your PowerShell code goes here>
```
~~~

<span data-ttu-id="6ba2d-308">PowerShell コマンドで表示される出力は、構文の強調表示を防ぐために **出力** コード ブロックで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-308">The output displayed by PowerShell commands should be enclosed in an **Output** code block to prevent syntax highlighting.</span></span> <span data-ttu-id="6ba2d-309">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-309">For example:</span></span>

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

<span data-ttu-id="6ba2d-310">**出力** コードラベルは、構文の強調表示システムでサポートされている公式の "言語" ではありません。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-310">The **Output** code label isn't an official "language" supported by the syntax highlighting system.</span></span>
<span data-ttu-id="6ba2d-311">ただし、このラベルは、OPS によって web ページ上のコードボックスフレームに "出力" ラベルが追加されるため便利です。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-311">However, this label is useful because OPS adds the "Output" label to the code box frame on the web page.</span></span> <span data-ttu-id="6ba2d-312">"出力" コードボックスには構文の強調表示がありません。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-312">The "Output" code box has no syntax highlighting.</span></span>

## <a name="coding-style-rules"></a><span data-ttu-id="6ba2d-313">コーディング スタイルの規則</span><span class="sxs-lookup"><span data-stu-id="6ba2d-313">Coding style rules</span></span>

### <a name="avoid-line-continuation-in-code-samples"></a><span data-ttu-id="6ba2d-314">コード サンプルでの行の継続を避ける</span><span class="sxs-lookup"><span data-stu-id="6ba2d-314">Avoid line continuation in code samples</span></span>

<span data-ttu-id="6ba2d-315">PowerShell コード例では、行連結文字 (`` ` ``) を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-315">Avoid using line continuation characters (`` ` ``) in PowerShell code examples.</span></span> <span data-ttu-id="6ba2d-316">これらはわかりにくいため、行末に余分なスペースがあると問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-316">These are hard to see and can cause problems if there are extra spaces at the end of the line.</span></span>

- <span data-ttu-id="6ba2d-317">PowerShell スプラッティングを使用して、複数のパラメーターを持つコマンドレットの行の長さを減らします。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-317">Use PowerShell splatting to reduce line length for cmdlets that have several parameters.</span></span>
- <span data-ttu-id="6ba2d-318">パイプ ( `|` ) 文字、左中かっこ ( `{` )、かっこ () `(` 、および角かっこ () のように、PowerShell の自然な改行の機会を活用し `[` ます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-318">Take advantage of PowerShell's natural line break opportunities, like after pipe (`|`) characters, opening braces (`{`), parentheses (`(`), and brackets (`[`).</span></span>

### <a name="avoid-using-powershell-prompts-in-examples"></a><span data-ttu-id="6ba2d-319">例で PowerShell プロンプトを使用しないようにする</span><span class="sxs-lookup"><span data-stu-id="6ba2d-319">Avoid using PowerShell prompts in examples</span></span>

<span data-ttu-id="6ba2d-320">プロンプト文字列の使用は推奨されていないため、コマンドラインの使用方法を示すシナリオに限定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-320">Use of the prompt string is discouraged and should be limited to scenarios that are meant to illustrate command-line usage.</span></span> <span data-ttu-id="6ba2d-321">これらの例の大部分では、プロンプト文字列をにする必要があり `PS>` ます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-321">For most of these examples, the prompt string should be `PS>`.</span></span> <span data-ttu-id="6ba2d-322">このプロンプトは OS 固有のインジケーターに依存しません。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-322">This prompt is independent of OS-specific indicators.</span></span>

<span data-ttu-id="6ba2d-323">プロンプトを変更するコマンドや、表示されるパスがシナリオにとって重要であることを示すコマンドを示す例では、プロンプトが必要です。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-323">Prompts are required in examples to illustrate commands that alter the prompt or when the path displayed is significant to the scenario.</span></span> <span data-ttu-id="6ba2d-324">次の例は、レジストリ プロバイダーの使用時にプロンプトがどのように変化するかを示しています。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-324">The following example illustrates how the prompt changes when using the Registry provider.</span></span>

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

### <a name="dont-use-aliases-in-examples"></a><span data-ttu-id="6ba2d-325">例では別名を使用しない</span><span class="sxs-lookup"><span data-stu-id="6ba2d-325">Don't use aliases in examples</span></span>

<span data-ttu-id="6ba2d-326">エイリアスを特に記述している場合を除き、すべてのコマンドレットとパラメーターの完全な名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-326">Use the full name of all cmdlets and parameters unless you're specifically documenting the alias.</span></span>
<span data-ttu-id="6ba2d-327">コマンドレットとパラメーター名には、 [Pascal][] 形式の正しい名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-327">Cmdlet and parameter names must use the proper [Pascal-cased][] names.</span></span>

### <a name="using-parameters-in-examples"></a><span data-ttu-id="6ba2d-328">例でのパラメーターの使用</span><span class="sxs-lookup"><span data-stu-id="6ba2d-328">Using parameters in examples</span></span>

<span data-ttu-id="6ba2d-329">位置指定パラメーターは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-329">Avoid using positional parameters.</span></span> <span data-ttu-id="6ba2d-330">一般に、パラメーターが位置指定の場合でも、パラメーター名は常に例に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-330">In general, you should always include the parameter name in an example, even if the parameter is positional.</span></span> <span data-ttu-id="6ba2d-331">これにより、例で混乱を招く可能性が減ります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-331">This reduces the chance of confusion in your examples.</span></span>

## <a name="formatting-cmdlet-reference-articles"></a><span data-ttu-id="6ba2d-332">コマンドレットのリファレンス記事の書式設定</span><span class="sxs-lookup"><span data-stu-id="6ba2d-332">Formatting cmdlet reference articles</span></span>

<span data-ttu-id="6ba2d-333">コマンドレットのリファレンス記事には、特定の構造があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-333">Cmdlet reference articles have a specific structure.</span></span> <span data-ttu-id="6ba2d-334">この構造は、[PlatyPS][] によって定義されています。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-334">This structure is defined by [PlatyPS][].</span></span>
<span data-ttu-id="6ba2d-335">エラーでは、Markdown の PowerShell モジュールのコマンドレットヘルプが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-335">PlatyPS generates the cmdlet help for PowerShell modules in Markdown.</span></span> <span data-ttu-id="6ba2d-336">マークダウン ファイルを編集した後、PlatyPS を使用して、`Get-Help` コマンドレットによって使用される MAML ヘルプ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-336">After editing the Markdown files, PlatyPS is used create the MAML help files used by the `Get-Help` cmdlet.</span></span>

<span data-ttu-id="6ba2d-337">PlatyPS には、コード内に記述されるコマンドレット リファレンス用のハードコーディングされたスキーマが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-337">PlatyPS has a hard-coded schema for cmdlet reference that is written into the code.</span></span> <span data-ttu-id="6ba2d-338">[platyPS.schema.md][] ドキュメントでは、この構造が記述されています。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-338">The [platyPS.schema.md][] document attempts to describe this structure.</span></span> <span data-ttu-id="6ba2d-339">スキーマ違反があると、投稿を受け入れる前に修正する必要があるビルド エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-339">Schema violations cause build errors that must be fixed before we can accept your contribution.</span></span>

- <span data-ttu-id="6ba2d-340">ATX ヘッダー構造体は削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-340">Don't remove any of the ATX header structures.</span></span> <span data-ttu-id="6ba2d-341">PlatyPS では、特定のヘッダーのセットが想定されています。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-341">PlatyPS expects a specific set of headers.</span></span>
- <span data-ttu-id="6ba2d-342">**Input type** ヘッダーと **Output type** ヘッダーでは、型が必要です。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-342">The **Input type** and **Output type** headers must have a type.</span></span> <span data-ttu-id="6ba2d-343">コマンドレットが入力を受け取らない場合、または値を返さない場合は、値を使用し `None` ます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-343">If the cmdlet doesn't take input or return a value, then use the value `None`.</span></span>
- <span data-ttu-id="6ba2d-344">インライン コード スパンは、どのパラグラフでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-344">Inline code spans can be used in any paragraph.</span></span>
- <span data-ttu-id="6ba2d-345">たジオフェンス型コードブロックは、「 **例** 」のセクションでのみ許可されています。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-345">Fenced code blocks are only allowed in the **EXAMPLES** section.</span></span>

<span data-ttu-id="6ba2d-346">エラースキーマでは、 **例** は H2 ヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-346">In the PlatyPS schema, **EXAMPLES** is an H2 header.</span></span> <span data-ttu-id="6ba2d-347">各例は、H3 ヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-347">Each example is an H3 header.</span></span> <span data-ttu-id="6ba2d-348">例では、スキーマでコードブロックを段落で区切ることはできません。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-348">Within an example, the schema doesn't allow code blocks to be separated by paragraphs.</span></span> <span data-ttu-id="6ba2d-349">スキーマでは、次の構造を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-349">The schema allows the following structure:</span></span>

```
### Example X - Title sentence

0 or more paragraphs
1 or more code blocks
0 or more paragraphs.
```

<span data-ttu-id="6ba2d-350">各例に番号を指定し、簡単なタイトルを追加します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-350">Number each example and add a brief title.</span></span>

<span data-ttu-id="6ba2d-351">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-351">For example:</span></span>

~~~markdown
### Example 1: Get cmdlets, functions, and aliases

This command gets the PowerShell cmdlets, functions, and aliases that are installed on the
computer.

```powershell
Get-Command
```

### Example 2: Get commands in the current session

```powershell
Get-Command -ListImported
```
~~~

## <a name="formatting-about_-files"></a><span data-ttu-id="6ba2d-352">About_ ファイルの書式設定</span><span class="sxs-lookup"><span data-stu-id="6ba2d-352">Formatting About_ files</span></span>

<span data-ttu-id="6ba2d-353">`About_*` ファイルは Markdown で記述されますが、プレーンテキストファイルとして出荷されます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-353">`About_*` files are written in Markdown but are shipped as plain text files.</span></span> <span data-ttu-id="6ba2d-354">[Pandoc][]を使用して、Markdown をプレーンテキストに変換します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-354">We use [Pandoc][] to convert the Markdown to plain text.</span></span> <span data-ttu-id="6ba2d-355">`About_*` ファイルは、すべてのバージョンの PowerShell と発行ツールで最適な互換性を持つように書式設定されています。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-355">`About_*` files are formatted for the best compatibility across all versions of PowerShell and with the publishing tools.</span></span>

<span data-ttu-id="6ba2d-356">基本的な書式設定に関するガイドライン:</span><span class="sxs-lookup"><span data-stu-id="6ba2d-356">Basic formatting guidelines:</span></span>

- <span data-ttu-id="6ba2d-357">通常の行を80文字に制限する</span><span class="sxs-lookup"><span data-stu-id="6ba2d-357">Limit normal lines to 80 characters</span></span>
- <span data-ttu-id="6ba2d-358">コードブロックの文字数は76文字に制限されています</span><span class="sxs-lookup"><span data-stu-id="6ba2d-358">Code blocks are limited to 76 characters</span></span>
- <span data-ttu-id="6ba2d-359">ブロックの引用符 (およびアラート) は78文字に制限されています</span><span class="sxs-lookup"><span data-stu-id="6ba2d-359">Blockquotes (and Alerts) are limited 78 characters</span></span>
- <span data-ttu-id="6ba2d-360">これらの特殊なメタ文字 (、、および) を使用する場合は、次のように `\` `$` `<` なります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-360">When using these special meta-characters `\`,`$`, and `<`:</span></span>
  - <span data-ttu-id="6ba2d-361">ヘッダー内では、これらの文字は先頭文字を使用してエスケープする `\` か、バックティック () を使用してコード範囲で囲んでいる必要があります `` ` `` 。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-361">Within a header, these characters must be escaped using a leading `\` character or enclosed in code spans using backticks (`` ` ``)</span></span>
  - <span data-ttu-id="6ba2d-362">段落内では、これらの文字をコードの範囲内に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-362">Within a paragraph, these characters should be put into code spans.</span></span> <span data-ttu-id="6ba2d-363">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-363">For example:</span></span>

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

- <span data-ttu-id="6ba2d-364">テーブルは76文字以内に収める必要があります</span><span class="sxs-lookup"><span data-stu-id="6ba2d-364">Tables need to fit within 76 characters</span></span>
  - <span data-ttu-id="6ba2d-365">複数行にまたがるセルの内容は手動で折り返します</span><span class="sxs-lookup"><span data-stu-id="6ba2d-365">Manually wrap contents of cells across multiple lines</span></span>
  - <span data-ttu-id="6ba2d-366">各行で開始と終了の `|` 文字を使用します</span><span class="sxs-lookup"><span data-stu-id="6ba2d-366">Use opening and closing `|` characters on each line</span></span>
  - <span data-ttu-id="6ba2d-367">次の例では、セル内の複数の行に折り返される情報を含むテーブルを適切に構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-367">The following example illustrates how to properly construct a table that contains information that wraps on multiple lines within a cell.</span></span>

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
    > <span data-ttu-id="6ba2d-368">76列の制限は、トピックにのみ適用さ `About_*` れます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-368">The 76-column limitation applies only to `About_*` topics.</span></span> <span data-ttu-id="6ba2d-369">ワイド列は、概念説明またはコマンドレットのリファレンス記事で使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ba2d-369">You can use wide columns in conceptual or cmdlet reference articles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6ba2d-370">次のステップ</span><span class="sxs-lookup"><span data-stu-id="6ba2d-370">Next steps</span></span>

[<span data-ttu-id="6ba2d-371">編集のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="6ba2d-371">Editorial checklist</span></span>](editorial-checklist.md)

<!-- link references -->
[atx]: https://github.github.com/gfm/#atx-headings
[CommonMark]: https://spec.commonmark.org/
[markdig]: https://github.com/lunet-io/markdig
[Pandoc]: https://pandoc.org
[Pascal 形式の大文字と小文字の区別]: https://en.wikipedia.org/wiki/PascalCase
[Pascal-cased]: https://en.wikipedia.org/wiki/PascalCase
[platyPS.schema.md]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[PlatyPS]: https://github.com/powershell/platyps
[reflow]: https://marketplace.visualstudio.com/items?itemName=marvhen.reflow-markdown
[linkref]: https://spec.commonmark.org/0.29/#link-reference-definitions
