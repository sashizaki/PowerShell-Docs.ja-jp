---
title: 編集チェックリスト
description: PowerShell ドキュメントを編集する際のルールの概要を示します。
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 511e0c323e1a3256039e819d06f32f6e1ac42767
ms.sourcegitcommit: 18d832858a7b8ea094763afa753e0f48f01372e7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2020
ms.locfileid: "79060337"
---
# <a name="editors-checklist"></a><span data-ttu-id="47020-103">編集者のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="47020-103">Editor's checklist</span></span>

<span data-ttu-id="47020-104">ここでは、新しい記事を書くときや既存の記事を更新するときに適用されるルールの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="47020-104">This is a summary of rules to apply when writing new or updating existing articles.</span></span> <span data-ttu-id="47020-105">これらのルールの詳しい説明と例については、共同作成者ガイドの他の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="47020-105">See other articles in the Contributor's Guide for detailed explanations and examples of these rules.</span></span>

## <a name="metadata"></a><span data-ttu-id="47020-106">Metadata</span><span class="sxs-lookup"><span data-stu-id="47020-106">Metadata</span></span>

- <span data-ttu-id="47020-107">`ms.date`: **MM/DD/YYYY** 形式</span><span class="sxs-lookup"><span data-stu-id="47020-107">`ms.date`: must be in the format **MM/DD/YYYY**</span></span>
  - <span data-ttu-id="47020-108">重要な更新または事実に基づく更新がある場合は日付を変更する</span><span class="sxs-lookup"><span data-stu-id="47020-108">Change the date when there is a significant or factual update</span></span>
    - <span data-ttu-id="47020-109">記事の再構成</span><span class="sxs-lookup"><span data-stu-id="47020-109">Reorganizing the article</span></span>
    - <span data-ttu-id="47020-110">事実誤認の修正</span><span class="sxs-lookup"><span data-stu-id="47020-110">Fixing factual errors</span></span>
    - <span data-ttu-id="47020-111">新しい情報の追加</span><span class="sxs-lookup"><span data-stu-id="47020-111">Adding new information</span></span>
  - <span data-ttu-id="47020-112">更新が重要でない場合は日付を変更しない</span><span class="sxs-lookup"><span data-stu-id="47020-112">Do not change the date if the update is insignificant</span></span>
    - <span data-ttu-id="47020-113">誤字や書式設定の修正</span><span class="sxs-lookup"><span data-stu-id="47020-113">Fixing typos and formatting</span></span>
- <span data-ttu-id="47020-114">`title`: スペースを含め、43 から 59 文字の一意の文字列</span><span class="sxs-lookup"><span data-stu-id="47020-114">`title`: unique string of 43-59 chars including spaces</span></span>
  - <span data-ttu-id="47020-115">サイト識別子を含めない - 自動生成されます</span><span class="sxs-lookup"><span data-stu-id="47020-115">Do not include site identifier (it is auto-generated)</span></span>
  - <span data-ttu-id="47020-116">文の先頭文字を大文字にする - 先頭文字と固有名詞のみを大文字にします</span><span class="sxs-lookup"><span data-stu-id="47020-116">Use sentence case - capitalize only the first word and any proper nouns</span></span>
- <span data-ttu-id="47020-117">`description`:スペースを含め、115 から 145 文字 - この要約は検索結果に表示されます</span><span class="sxs-lookup"><span data-stu-id="47020-117">`description`: 115-145 characters including spaces - this abstract displays in the search result</span></span>

## <a name="formatting"></a><span data-ttu-id="47020-118">書式設定</span><span class="sxs-lookup"><span data-stu-id="47020-118">Formatting</span></span>

- <span data-ttu-id="47020-119">段落内にインラインで表示されるバッククォート構文要素</span><span class="sxs-lookup"><span data-stu-id="47020-119">Backtick syntax elements that appear, inline, within a paragraph</span></span>
  - <span data-ttu-id="47020-120">コマンドレット名: `Verb-Noun`</span><span class="sxs-lookup"><span data-stu-id="47020-120">Cmdlet names `Verb-Noun`</span></span>
  - <span data-ttu-id="47020-121">変数: `$counter`</span><span class="sxs-lookup"><span data-stu-id="47020-121">Variable `$counter`</span></span>
  - <span data-ttu-id="47020-122">構文例: `Verb-Noun -Parameter`</span><span class="sxs-lookup"><span data-stu-id="47020-122">Syntactic examples `Verb-Noun -Parameter`</span></span>
  - <span data-ttu-id="47020-123">ファイル パス: `C:\Program Files\PowerShell`、`/usr/bin/pwsh`</span><span class="sxs-lookup"><span data-stu-id="47020-123">File paths `C:\Program Files\PowerShell`, `/usr/bin/pwsh`</span></span>
  - <span data-ttu-id="47020-124">ドキュメント内でクリック可能であることを意図していない URL</span><span class="sxs-lookup"><span data-stu-id="47020-124">URLs that are not meant to be clickable in the document</span></span>
- <span data-ttu-id="47020-125">プロパティ名、パラメーター値、パラメーター名、クラス名、モジュール名、エンティティ名、オブジェクト名、型名には太字を使用する</span><span class="sxs-lookup"><span data-stu-id="47020-125">Use bold for property names, parameter values, parameter names, class names, module names, entity names, object or type names</span></span>
  - <span data-ttu-id="47020-126">太字は、強調ではなく、セマンティック マークアップに使用</span><span class="sxs-lookup"><span data-stu-id="47020-126">Bold is used for semantic markup, not emphasis</span></span>
  - <span data-ttu-id="47020-127">太字 - アスタリスク (`**`) を使用</span><span class="sxs-lookup"><span data-stu-id="47020-127">Bold - use asterisks `**`</span></span>
- <span data-ttu-id="47020-128">斜体 - アンダースコア (`_`) を使用</span><span class="sxs-lookup"><span data-stu-id="47020-128">Italic - use underscore `_`</span></span>
  - <span data-ttu-id="47020-129">セマンティック マークアップではなく、強調にのみ使用</span><span class="sxs-lookup"><span data-stu-id="47020-129">Only used for emphasis, not for semantic markup</span></span>
- <span data-ttu-id="47020-130">100 列 (**about_Topics** の場合は 80 列) で改行する</span><span class="sxs-lookup"><span data-stu-id="47020-130">Line breaks at 100 columns (or at 80 for **about_Topics**)</span></span>
- <span data-ttu-id="47020-131">ハード タブを使用しない - スペースのみを使用します</span><span class="sxs-lookup"><span data-stu-id="47020-131">No hard tabs - use spaces only</span></span>
- <span data-ttu-id="47020-132">行の末尾にスペースを含めない</span><span class="sxs-lookup"><span data-stu-id="47020-132">No trailing spaces on lines</span></span>

### <a name="headers"></a><span data-ttu-id="47020-133">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="47020-133">Headers</span></span>

- <span data-ttu-id="47020-134">H1 が最初 - H1 は記事ごとに 1 つだけ使用します</span><span class="sxs-lookup"><span data-stu-id="47020-134">H1 is first - only one H1 per article</span></span>
- <span data-ttu-id="47020-135">[ATX ヘッダー](https://github.github.com/gfm/#atx-headings)だけを使用する</span><span class="sxs-lookup"><span data-stu-id="47020-135">Use [ATX Headers](https://github.github.com/gfm/#atx-headings) only</span></span>
- <span data-ttu-id="47020-136">すべてのヘッダーの先頭文字を大文字にする</span><span class="sxs-lookup"><span data-stu-id="47020-136">Use sentence case for all headers</span></span>
- <span data-ttu-id="47020-137">レベルをスキップしない - H2 をスキップして H3 を使用することはできません</span><span class="sxs-lookup"><span data-stu-id="47020-137">Do not skip levels - no H3 without an H2</span></span>
- <span data-ttu-id="47020-138">最大の深さを H3 または H4 にする</span><span class="sxs-lookup"><span data-stu-id="47020-138">Max depth of H3 or H4</span></span>
- <span data-ttu-id="47020-139">前後に空白行を挿入する</span><span class="sxs-lookup"><span data-stu-id="47020-139">Blank line before and after</span></span>
- <span data-ttu-id="47020-140">PlatyPS では、そのスキーマの特定のヘッダーが適用される - ヘッダーを追加または削除しないでください</span><span class="sxs-lookup"><span data-stu-id="47020-140">PlatyPS enforces specific headers in its schema - do not add or remove headers</span></span>

### <a name="code-blocks"></a><span data-ttu-id="47020-141">コード ブロック</span><span class="sxs-lookup"><span data-stu-id="47020-141">Code blocks</span></span>

- <span data-ttu-id="47020-142">前後に空白行を挿入する</span><span class="sxs-lookup"><span data-stu-id="47020-142">Blank line before and after</span></span>
- <span data-ttu-id="47020-143">タグ付きのコード フェンスを使用する - **powershell**、**Output**、または他の適切な言語 ID</span><span class="sxs-lookup"><span data-stu-id="47020-143">Use tagged code fences - **powershell**, **Output**, or other appropriate language ID</span></span>
- <span data-ttu-id="47020-144">タグなしのフェンス - 構文ブロックまたはその他のシェル</span><span class="sxs-lookup"><span data-stu-id="47020-144">Untagged fence - syntax blocks or other shells</span></span>
- <span data-ttu-id="47020-145">読者が **[コピー]** ボタンを使用することを意図していない簡単な例を除き、**Output** は別のコード ブロックに配置する</span><span class="sxs-lookup"><span data-stu-id="47020-145">Put **Output** in separate code block except for simple examples where you don't intend the for the reader to use the **Copy** button</span></span>
- <span data-ttu-id="47020-146">[サポートされている言語](/contribute/code-in-docs#supported-languages)の一覧を参照する</span><span class="sxs-lookup"><span data-stu-id="47020-146">See list of [supported languages](/contribute/code-in-docs#supported-languages)</span></span>

### <a name="lists"></a><span data-ttu-id="47020-147">リスト</span><span class="sxs-lookup"><span data-stu-id="47020-147">Lists</span></span>

- <span data-ttu-id="47020-148">適切にインデントする</span><span class="sxs-lookup"><span data-stu-id="47020-148">Indented properly</span></span>
- <span data-ttu-id="47020-149">最初の項目の前と最後の項目の後に空白行を挿入する</span><span class="sxs-lookup"><span data-stu-id="47020-149">Blank line before first item and after last item</span></span>
- <span data-ttu-id="47020-150">箇条書き - 強調と混同しやすいアスタリスク (`*`) ではなく、ハイフン (`-`) を使用する</span><span class="sxs-lookup"><span data-stu-id="47020-150">Bullet - use hyphen (`-`) not asterisk (`*`) - too easy to confuse with emphasis</span></span>
- <span data-ttu-id="47020-151">番号付きリストの場合、すべての番号に "1." を使用する</span><span class="sxs-lookup"><span data-stu-id="47020-151">For numbered lists, all numbers are "1."</span></span>

## <a name="terminology"></a><span data-ttu-id="47020-152">用語</span><span class="sxs-lookup"><span data-stu-id="47020-152">Terminology</span></span>

- <span data-ttu-id="47020-153">PowerShell、Windows PowerShell、PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="47020-153">PowerShell vs. Windows PowerShell vs. PowerShell Core</span></span>
- <span data-ttu-id="47020-154">「[Product Terminology (製品用語)](powershell-style-guide.md#product-terminology)」を参照する</span><span class="sxs-lookup"><span data-stu-id="47020-154">See [Product Terminology](powershell-style-guide.md#product-terminology)</span></span>

## <a name="cmdlet-reference-examples"></a><span data-ttu-id="47020-155">コマンドレット リファレンスの例</span><span class="sxs-lookup"><span data-stu-id="47020-155">Cmdlet reference examples</span></span>

- <span data-ttu-id="47020-156">コマンドレット リファレンスには、例を少なくとも 1 つ含める必要がある</span><span class="sxs-lookup"><span data-stu-id="47020-156">Must have at least one example in cmdlet reference</span></span>
- <span data-ttu-id="47020-157">例には、使用方法を示すのにちょうどよいコードを使用する</span><span class="sxs-lookup"><span data-stu-id="47020-157">Examples should be just enough code to demonstrate the usage</span></span>
- <span data-ttu-id="47020-158">PowerShell 構文</span><span class="sxs-lookup"><span data-stu-id="47020-158">PowerShell syntax</span></span>
  - <span data-ttu-id="47020-159">コマンドレットとパラメーターのフル ネームを使用する - エイリアスは使用しないでください</span><span class="sxs-lookup"><span data-stu-id="47020-159">Use full names of cmdlets and parameters - no aliases</span></span>
  - <span data-ttu-id="47020-160">コマンド ラインが長すぎる場合は、パラメーターにスプラッティングを使用する</span><span class="sxs-lookup"><span data-stu-id="47020-160">Use splatting for parameters when the command line gets too long</span></span>
  - <span data-ttu-id="47020-161">行継続のバッククォートの使用は避ける - 必要な場合にのみ使用してください</span><span class="sxs-lookup"><span data-stu-id="47020-161">Avoid using line continuation backticks - only use when necessary</span></span>
- <span data-ttu-id="47020-162">例に必要な場合を除き、PowerShell プロンプト (`PS>`) を削除または簡略化する</span><span class="sxs-lookup"><span data-stu-id="47020-162">Remove or simplify the PowerShell prompt (`PS>`) except where required for the example</span></span>
- <span data-ttu-id="47020-163">コマンドレット リファレンスの例は、次の PlatyPS スキーマに従う必要がある</span><span class="sxs-lookup"><span data-stu-id="47020-163">Cmdlet reference example must follow the following PlatyPS schema</span></span>

  ~~~Markdown
  ### Example 1 - Descriptive title

  Zero or more short descriptive paragraphs explaining the context of the example followed by one or
  more code blocks. Recommend at least one and no more than two.

  ```powershell
  ... one or more PowerShell code statements ...
  ```

  ```Output
  Example output of the code above.
  ```

  Zero or more optional follow up paragraphs that explain the details of the code and output.
  ~~~

- <span data-ttu-id="47020-164">コード ブロックの間に段落を入れない -</span><span class="sxs-lookup"><span data-stu-id="47020-164">Do not put paragraphs between the code blocks.</span></span> <span data-ttu-id="47020-165">説明的な内容はすべてコード ブロックの前後に配置する必要があります</span><span class="sxs-lookup"><span data-stu-id="47020-165">All descriptive content must come before or after the code blocks.</span></span>

## <a name="linking-to-other-documents"></a><span data-ttu-id="47020-166">他のドキュメントへのリンク</span><span class="sxs-lookup"><span data-stu-id="47020-166">Linking to other documents</span></span>

- <span data-ttu-id="47020-167">ドキュメント セットの外部またはコマンドレット リファレンスと概念の間にリンクを設定する</span><span class="sxs-lookup"><span data-stu-id="47020-167">Linking outside the docset or between cmdlet reference and conceptual</span></span>
  - <span data-ttu-id="47020-168">docs.microsoft.com にリンクする場合は、相対 URL を使用する (`https://docs.microsoft.com/en-us` を削除する)</span><span class="sxs-lookup"><span data-stu-id="47020-168">Use relative URLs when linking to docs.microsoft.com (remove `https://docs.microsoft.com/en-us`)</span></span>
  - <span data-ttu-id="47020-169">Microsoft プロパティの URL にロケールを含めない (例:</span><span class="sxs-lookup"><span data-stu-id="47020-169">Do not include locales in URLs on Microsoft properties (eg.</span></span> <span data-ttu-id="47020-170">URL から `/en-us` を削除する)</span><span class="sxs-lookup"><span data-stu-id="47020-170">remove `/en-us` from URL)</span></span>
  - <span data-ttu-id="47020-171">ターゲット サイトで無効である場合を除き、外部 Web サイトへのすべての URL で HTTPS を使用する</span><span class="sxs-lookup"><span data-stu-id="47020-171">All URLs to external websites should use HTTPS unless that is not valid for the target site</span></span>
- <span data-ttu-id="47020-172">ドキュメント セット内</span><span class="sxs-lookup"><span data-stu-id="47020-172">Within docset</span></span>
  - <span data-ttu-id="47020-173">ファイル パスへのリンク (例: `../folder/file.md`)</span><span class="sxs-lookup"><span data-stu-id="47020-173">Link to file path (e.g. `../folder/file.md`)</span></span>
  - <span data-ttu-id="47020-174">すべてのファイル パスでスラッシュ (`/`) 文字を使用する</span><span class="sxs-lookup"><span data-stu-id="47020-174">All file paths use forward-slash (`/`) characters</span></span>
- <span data-ttu-id="47020-175">画像リンクには一意の代替テキストが必要</span><span class="sxs-lookup"><span data-stu-id="47020-175">Image links should have unique alt text</span></span>
