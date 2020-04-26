---
title: 編集チェックリスト
description: PowerShell ドキュメントを編集する際のルールの概要を示します。
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: b5baf7366239084779d34e23f218e5e6222ed1a3
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81624739"
---
# <a name="editors-checklist"></a><span data-ttu-id="11513-103">編集者のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="11513-103">Editor's checklist</span></span>

<span data-ttu-id="11513-104">ここでは、新しい記事を書くときや既存の記事を更新するときに適用されるルールの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="11513-104">This is a summary of rules to apply when writing new or updating existing articles.</span></span> <span data-ttu-id="11513-105">これらのルールの詳しい説明と例については、共同作成者ガイドの他の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="11513-105">See other articles in the Contributor's Guide for detailed explanations and examples of these rules.</span></span>

## <a name="metadata"></a><span data-ttu-id="11513-106">Metadata</span><span class="sxs-lookup"><span data-stu-id="11513-106">Metadata</span></span>

- <span data-ttu-id="11513-107">`ms.date`: **MM/DD/YYYY** 形式</span><span class="sxs-lookup"><span data-stu-id="11513-107">`ms.date`: must be in the format **MM/DD/YYYY**</span></span>
  - <span data-ttu-id="11513-108">重要な更新または事実に基づく更新がある場合は日付を変更する</span><span class="sxs-lookup"><span data-stu-id="11513-108">Change the date when there is a significant or factual update</span></span>
    - <span data-ttu-id="11513-109">記事の再構成</span><span class="sxs-lookup"><span data-stu-id="11513-109">Reorganizing the article</span></span>
    - <span data-ttu-id="11513-110">事実誤認の修正</span><span class="sxs-lookup"><span data-stu-id="11513-110">Fixing factual errors</span></span>
    - <span data-ttu-id="11513-111">新しい情報の追加</span><span class="sxs-lookup"><span data-stu-id="11513-111">Adding new information</span></span>
  - <span data-ttu-id="11513-112">更新が重要でない場合は日付を変更しない</span><span class="sxs-lookup"><span data-stu-id="11513-112">Do not change the date if the update is insignificant</span></span>
    - <span data-ttu-id="11513-113">誤字や書式設定の修正</span><span class="sxs-lookup"><span data-stu-id="11513-113">Fixing typos and formatting</span></span>
- <span data-ttu-id="11513-114">`title`: スペースを含め、43 から 59 文字の一意の文字列</span><span class="sxs-lookup"><span data-stu-id="11513-114">`title`: unique string of 43-59 chars including spaces</span></span>
  - <span data-ttu-id="11513-115">サイト識別子を含めない - 自動生成されます</span><span class="sxs-lookup"><span data-stu-id="11513-115">Do not include site identifier (it is auto-generated)</span></span>
  - <span data-ttu-id="11513-116">文の先頭文字を大文字にする - 先頭文字と固有名詞のみを大文字にします</span><span class="sxs-lookup"><span data-stu-id="11513-116">Use sentence case - capitalize only the first word and any proper nouns</span></span>
- <span data-ttu-id="11513-117">`description`:スペースを含め、115 から 145 文字 - この要約は検索結果に表示されます</span><span class="sxs-lookup"><span data-stu-id="11513-117">`description`: 115-145 characters including spaces - this abstract displays in the search result</span></span>

## <a name="formatting"></a><span data-ttu-id="11513-118">書式設定</span><span class="sxs-lookup"><span data-stu-id="11513-118">Formatting</span></span>

- <span data-ttu-id="11513-119">段落内にインラインで表示されるバッククォート構文要素</span><span class="sxs-lookup"><span data-stu-id="11513-119">Backtick syntax elements that appear, inline, within a paragraph</span></span>
  - <span data-ttu-id="11513-120">コマンドレット名: `Verb-Noun`</span><span class="sxs-lookup"><span data-stu-id="11513-120">Cmdlet names `Verb-Noun`</span></span>
  - <span data-ttu-id="11513-121">変数: `$counter`</span><span class="sxs-lookup"><span data-stu-id="11513-121">Variable `$counter`</span></span>
  - <span data-ttu-id="11513-122">構文例: `Verb-Noun -Parameter`</span><span class="sxs-lookup"><span data-stu-id="11513-122">Syntactic examples `Verb-Noun -Parameter`</span></span>
  - <span data-ttu-id="11513-123">ファイル パス: `C:\Program Files\PowerShell`、`/usr/bin/pwsh`</span><span class="sxs-lookup"><span data-stu-id="11513-123">File paths `C:\Program Files\PowerShell`, `/usr/bin/pwsh`</span></span>
  - <span data-ttu-id="11513-124">ドキュメント内でクリック可能であることを意図していない URL</span><span class="sxs-lookup"><span data-stu-id="11513-124">URLs that are not meant to be clickable in the document</span></span>
  - <span data-ttu-id="11513-125">プロパティまたはパラメーターの値</span><span class="sxs-lookup"><span data-stu-id="11513-125">Property or parameter values</span></span>
- <span data-ttu-id="11513-126">プロパティ名、パラメーター、名前、クラス名、モジュール名、エンティティ名、オブジェクト名、型名には太字を使用する</span><span class="sxs-lookup"><span data-stu-id="11513-126">Use bold for property names, parameter names, class names, module names, entity names, object or type names</span></span>
  - <span data-ttu-id="11513-127">太字は、強調ではなく、セマンティック マークアップに使用</span><span class="sxs-lookup"><span data-stu-id="11513-127">Bold is used for semantic markup, not emphasis</span></span>
  - <span data-ttu-id="11513-128">太字 - アスタリスク (`**`) を使用</span><span class="sxs-lookup"><span data-stu-id="11513-128">Bold - use asterisks `**`</span></span>
- <span data-ttu-id="11513-129">斜体 - アンダースコア (`_`) を使用</span><span class="sxs-lookup"><span data-stu-id="11513-129">Italic - use underscore `_`</span></span>
  - <span data-ttu-id="11513-130">セマンティック マークアップではなく、強調にのみ使用</span><span class="sxs-lookup"><span data-stu-id="11513-130">Only used for emphasis, not for semantic markup</span></span>
- <span data-ttu-id="11513-131">100 列 (**about_Topics** の場合は 80 列) で改行する</span><span class="sxs-lookup"><span data-stu-id="11513-131">Line breaks at 100 columns (or at 80 for **about_Topics**)</span></span>
- <span data-ttu-id="11513-132">ハード タブを使用しない - スペースのみを使用します</span><span class="sxs-lookup"><span data-stu-id="11513-132">No hard tabs - use spaces only</span></span>
- <span data-ttu-id="11513-133">行の末尾にスペースを含めない</span><span class="sxs-lookup"><span data-stu-id="11513-133">No trailing spaces on lines</span></span>

### <a name="headers"></a><span data-ttu-id="11513-134">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="11513-134">Headers</span></span>

- <span data-ttu-id="11513-135">H1 が最初 - H1 は記事ごとに 1 つだけ使用します</span><span class="sxs-lookup"><span data-stu-id="11513-135">H1 is first - only one H1 per article</span></span>
- <span data-ttu-id="11513-136">[ATX ヘッダー](https://github.github.com/gfm/#atx-headings)だけを使用する</span><span class="sxs-lookup"><span data-stu-id="11513-136">Use [ATX Headers](https://github.github.com/gfm/#atx-headings) only</span></span>
- <span data-ttu-id="11513-137">すべてのヘッダーの先頭文字を大文字にする</span><span class="sxs-lookup"><span data-stu-id="11513-137">Use sentence case for all headers</span></span>
- <span data-ttu-id="11513-138">レベルをスキップしない - H2 をスキップして H3 を使用することはできません</span><span class="sxs-lookup"><span data-stu-id="11513-138">Do not skip levels - no H3 without an H2</span></span>
- <span data-ttu-id="11513-139">最大の深さを H3 または H4 にする</span><span class="sxs-lookup"><span data-stu-id="11513-139">Max depth of H3 or H4</span></span>
- <span data-ttu-id="11513-140">前後に空白行を挿入する</span><span class="sxs-lookup"><span data-stu-id="11513-140">Blank line before and after</span></span>
- <span data-ttu-id="11513-141">PlatyPS では、そのスキーマの特定のヘッダーが適用される - ヘッダーを追加または削除しないでください</span><span class="sxs-lookup"><span data-stu-id="11513-141">PlatyPS enforces specific headers in its schema - do not add or remove headers</span></span>

### <a name="code-blocks"></a><span data-ttu-id="11513-142">コード ブロック</span><span class="sxs-lookup"><span data-stu-id="11513-142">Code blocks</span></span>

- <span data-ttu-id="11513-143">前後に空白行を挿入する</span><span class="sxs-lookup"><span data-stu-id="11513-143">Blank line before and after</span></span>
- <span data-ttu-id="11513-144">タグ付きのコード フェンスを使用する - **powershell**、**Output**、または他の適切な言語 ID</span><span class="sxs-lookup"><span data-stu-id="11513-144">Use tagged code fences - **powershell**, **Output**, or other appropriate language ID</span></span>
- <span data-ttu-id="11513-145">タグなしのフェンス - 構文ブロックまたはその他のシェル</span><span class="sxs-lookup"><span data-stu-id="11513-145">Untagged fence - syntax blocks or other shells</span></span>
- <span data-ttu-id="11513-146">読者が **[コピー]** ボタンを使用することを意図していないシンプルな例を除き、Output は別のコード ブロックに配置する</span><span class="sxs-lookup"><span data-stu-id="11513-146">Put output in separate code block except for simple examples where you don't intend the for the reader to use the **Copy** button</span></span>
- <span data-ttu-id="11513-147">[サポートされている言語](/contribute/code-in-docs#supported-languages)の一覧を参照する</span><span class="sxs-lookup"><span data-stu-id="11513-147">See list of [supported languages](/contribute/code-in-docs#supported-languages)</span></span>

### <a name="lists"></a><span data-ttu-id="11513-148">リスト</span><span class="sxs-lookup"><span data-stu-id="11513-148">Lists</span></span>

- <span data-ttu-id="11513-149">適切にインデントする</span><span class="sxs-lookup"><span data-stu-id="11513-149">Indented properly</span></span>
- <span data-ttu-id="11513-150">最初の項目の前と最後の項目の後に空白行を挿入する</span><span class="sxs-lookup"><span data-stu-id="11513-150">Blank line before first item and after last item</span></span>
- <span data-ttu-id="11513-151">箇条書き - 強調と混同しやすいアスタリスク (`*`) ではなく、ハイフン (`-`) を使用する</span><span class="sxs-lookup"><span data-stu-id="11513-151">Bullet - use hyphen (`-`) not asterisk (`*`) - too easy to confuse with emphasis</span></span>
- <span data-ttu-id="11513-152">番号付きリストの場合、すべての番号に "1." を使用する</span><span class="sxs-lookup"><span data-stu-id="11513-152">For numbered lists, all numbers are "1."</span></span>

## <a name="terminology"></a><span data-ttu-id="11513-153">用語</span><span class="sxs-lookup"><span data-stu-id="11513-153">Terminology</span></span>

- <span data-ttu-id="11513-154">PowerShell、Windows PowerShell、PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="11513-154">PowerShell vs. Windows PowerShell vs. PowerShell Core</span></span>
- <span data-ttu-id="11513-155">「[Product Terminology (製品用語)](powershell-style-guide.md#product-terminology)」を参照する</span><span class="sxs-lookup"><span data-stu-id="11513-155">See [Product Terminology](powershell-style-guide.md#product-terminology)</span></span>

## <a name="cmdlet-reference-examples"></a><span data-ttu-id="11513-156">コマンドレット リファレンスの例</span><span class="sxs-lookup"><span data-stu-id="11513-156">Cmdlet reference examples</span></span>

- <span data-ttu-id="11513-157">コマンドレット リファレンスには、例を少なくとも 1 つ含める必要がある</span><span class="sxs-lookup"><span data-stu-id="11513-157">Must have at least one example in cmdlet reference</span></span>
- <span data-ttu-id="11513-158">例には、使用方法を示すのにちょうどよいコードを使用する</span><span class="sxs-lookup"><span data-stu-id="11513-158">Examples should be just enough code to demonstrate the usage</span></span>
- <span data-ttu-id="11513-159">PowerShell 構文</span><span class="sxs-lookup"><span data-stu-id="11513-159">PowerShell syntax</span></span>
  - <span data-ttu-id="11513-160">コマンドレットとパラメーターのフル ネームを使用する - エイリアスは使用しないでください</span><span class="sxs-lookup"><span data-stu-id="11513-160">Use full names of cmdlets and parameters - no aliases</span></span>
  - <span data-ttu-id="11513-161">コマンド ラインが長すぎる場合は、パラメーターにスプラッティングを使用する</span><span class="sxs-lookup"><span data-stu-id="11513-161">Use splatting for parameters when the command line gets too long</span></span>
  - <span data-ttu-id="11513-162">行継続のバッククォートの使用は避ける - 必要な場合にのみ使用してください</span><span class="sxs-lookup"><span data-stu-id="11513-162">Avoid using line continuation backticks - only use when necessary</span></span>
- <span data-ttu-id="11513-163">例に必要な場合を除き、PowerShell プロンプト (`PS>`) を削除または簡略化する</span><span class="sxs-lookup"><span data-stu-id="11513-163">Remove or simplify the PowerShell prompt (`PS>`) except where required for the example</span></span>
- <span data-ttu-id="11513-164">コマンドレット リファレンスの例は、次の PlatyPS スキーマに従う必要がある</span><span class="sxs-lookup"><span data-stu-id="11513-164">Cmdlet reference example must follow the following PlatyPS schema</span></span>

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

- <span data-ttu-id="11513-165">コード ブロックの間に段落を入れない -</span><span class="sxs-lookup"><span data-stu-id="11513-165">Do not put paragraphs between the code blocks.</span></span> <span data-ttu-id="11513-166">説明的な内容はすべてコード ブロックの前後に配置する必要があります</span><span class="sxs-lookup"><span data-stu-id="11513-166">All descriptive content must come before or after the code blocks.</span></span>

## <a name="linking-to-other-documents"></a><span data-ttu-id="11513-167">他のドキュメントへのリンク</span><span class="sxs-lookup"><span data-stu-id="11513-167">Linking to other documents</span></span>

- <span data-ttu-id="11513-168">ドキュメント セットの外部またはコマンドレット リファレンスと概念の間にリンクを設定する</span><span class="sxs-lookup"><span data-stu-id="11513-168">Linking outside the docset or between cmdlet reference and conceptual</span></span>
  - <span data-ttu-id="11513-169">docs.microsoft.com にリンクする場合は、相対 URL を使用する (`https://docs.microsoft.com/en-us` を削除する)</span><span class="sxs-lookup"><span data-stu-id="11513-169">Use relative URLs when linking to docs.microsoft.com (remove `https://docs.microsoft.com/en-us`)</span></span>
  - <span data-ttu-id="11513-170">Microsoft プロパティの URL にロケールを含めない (例:</span><span class="sxs-lookup"><span data-stu-id="11513-170">Do not include locales in URLs on Microsoft properties (eg.</span></span> <span data-ttu-id="11513-171">URL から `/en-us` を削除する)</span><span class="sxs-lookup"><span data-stu-id="11513-171">remove `/en-us` from URL)</span></span>
  - <span data-ttu-id="11513-172">ターゲット サイトで無効である場合を除き、外部 Web サイトへのすべての URL で HTTPS を使用する</span><span class="sxs-lookup"><span data-stu-id="11513-172">All URLs to external websites should use HTTPS unless that is not valid for the target site</span></span>
- <span data-ttu-id="11513-173">ドキュメント セット内</span><span class="sxs-lookup"><span data-stu-id="11513-173">Within docset</span></span>
  - <span data-ttu-id="11513-174">ファイル パスへのリンク (例: `../folder/file.md`)</span><span class="sxs-lookup"><span data-stu-id="11513-174">Link to file path (e.g. `../folder/file.md`)</span></span>
  - <span data-ttu-id="11513-175">すべてのファイル パスでスラッシュ (`/`) 文字を使用する</span><span class="sxs-lookup"><span data-stu-id="11513-175">All file paths use forward-slash (`/`) characters</span></span>
- <span data-ttu-id="11513-176">画像リンクには一意の代替テキストが必要</span><span class="sxs-lookup"><span data-stu-id="11513-176">Image links should have unique alt text</span></span>
