---
description: PSReadLine では、PowerShell コンソールでのコマンドライン編集エクスペリエンスが向上しています。
keywords: powershell
Locale: en-US
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: PSReadLine について
ms.openlocfilehash: f5ae99a7c8bdae82372423a3e4d8261d95ab83d5
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "94692209"
---
# <a name="psreadline"></a><span data-ttu-id="be720-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="be720-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="be720-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="be720-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="be720-106">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="be720-106">Short Description</span></span>

<span data-ttu-id="be720-107">PSReadLine では、PowerShell コンソールでのコマンドライン編集エクスペリエンスが向上しています。</span><span class="sxs-lookup"><span data-stu-id="be720-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="be720-108">長い説明</span><span class="sxs-lookup"><span data-stu-id="be720-108">Long Description</span></span>

<span data-ttu-id="be720-109">PSReadLine 2.0 では、PowerShell コンソールの強力なコマンドライン編集エクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="be720-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="be720-110">次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="be720-110">It provides:</span></span>

- <span data-ttu-id="be720-111">コマンドラインの構文の色分け</span><span class="sxs-lookup"><span data-stu-id="be720-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="be720-112">構文エラーを視覚的に示します。</span><span class="sxs-lookup"><span data-stu-id="be720-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="be720-113">より優れたマルチラインエクスペリエンス (編集と履歴の両方)</span><span class="sxs-lookup"><span data-stu-id="be720-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="be720-114">カスタマイズ可能なキーバインド</span><span class="sxs-lookup"><span data-stu-id="be720-114">Customizable key bindings</span></span>
- <span data-ttu-id="be720-115">Cmd モードと Emacs モード</span><span class="sxs-lookup"><span data-stu-id="be720-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="be720-116">多くの構成オプション</span><span class="sxs-lookup"><span data-stu-id="be720-116">Many configuration options</span></span>
- <span data-ttu-id="be720-117">Bash スタイル補完 (Cmd モードでは省略可能、Emacs モードでは既定)</span><span class="sxs-lookup"><span data-stu-id="be720-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="be720-118">Emacs yank/kill-リング</span><span class="sxs-lookup"><span data-stu-id="be720-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="be720-119">PowerShell トークンベースの "word" の移動と強制終了</span><span class="sxs-lookup"><span data-stu-id="be720-119">PowerShell token based "word" movement and kill</span></span>

> [!NOTE]
> <span data-ttu-id="be720-120">PowerShell 7.0 以降では、スクリーンリーダープログラムが検出されると、PowerShell は Windows で PSReadLine の自動読み込みをスキップします。</span><span class="sxs-lookup"><span data-stu-id="be720-120">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="be720-121">現在、PSReadLine は、スクリーンリーダーではうまく機能しません。</span><span class="sxs-lookup"><span data-stu-id="be720-121">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="be720-122">Windows での PowerShell 7.0 の既定の表示と書式設定は正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="be720-122">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="be720-123">必要に応じて、モジュールを手動で読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="be720-123">You can manually load the module if necessary.</span></span>

<span data-ttu-id="be720-124">クラス **[PSConsoleReadLine]** では、次の関数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="be720-124">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="be720-125">基本的な編集関数</span><span class="sxs-lookup"><span data-stu-id="be720-125">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="be720-126">中止</span><span class="sxs-lookup"><span data-stu-id="be720-126">Abort</span></span>

<span data-ttu-id="be720-127">現在のアクション (増分履歴検索など) を中止します。</span><span class="sxs-lookup"><span data-stu-id="be720-127">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="be720-128">.Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="be720-128">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="be720-129">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="be720-129">AcceptAndGetNext</span></span>

<span data-ttu-id="be720-130">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="be720-130">Attempt to execute the current input.</span></span> <span data-ttu-id="be720-131">(AcceptLine など) 実行できる場合は、次に ReadLine が呼び出されたときに履歴から次の項目を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="be720-131">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="be720-132">.Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="be720-132">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="be720-133">AcceptLine</span><span class="sxs-lookup"><span data-stu-id="be720-133">AcceptLine</span></span>

<span data-ttu-id="be720-134">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="be720-134">Attempt to execute the current input.</span></span> <span data-ttu-id="be720-135">現在の入力が不完全な場合 (たとえば、終わりかっこ、角かっこ、または引用符がない場合)、継続のプロンプトは次の行に表示され、PSReadLine は現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="be720-135">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="be720-136">コマンド: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="be720-136">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="be720-137">.Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="be720-137">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="be720-138">Vi の挿入モード: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="be720-138">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="be720-139">AddLine</span><span class="sxs-lookup"><span data-stu-id="be720-139">AddLine</span></span>

<span data-ttu-id="be720-140">継続プロンプトが次の行に表示され、PSReadLine が現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="be720-140">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="be720-141">これは、単一行が単独で完全に入力されている場合でも、複数行の入力を1つのコマンドとして入力する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="be720-141">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="be720-142">コマンド: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="be720-142">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="be720-143">.Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="be720-143">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="be720-144">Vi の挿入モード: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="be720-144">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="be720-145">Vi コマンドモード: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="be720-145">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="be720-146">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="be720-146">BackwardDeleteChar</span></span>

<span data-ttu-id="be720-147">カーソルの前の文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="be720-147">Delete the character before the cursor.</span></span>

- <span data-ttu-id="be720-148">Cmd: `<Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="be720-148">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="be720-149">Emacs: `<Backspace>` 、 `<Ctrl+Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="be720-149">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="be720-150">Vi の挿入モード: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="be720-150">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="be720-151">Vi コマンドモード: `<X>` 、 `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="be720-151">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="be720-152">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="be720-152">BackwardDeleteLine</span></span>

<span data-ttu-id="be720-153">Like BackwardKillLine-行の先頭から先頭までのテキストを削除しますが、削除されたテキストはキルリングには挿入されません。</span><span class="sxs-lookup"><span data-stu-id="be720-153">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="be720-154">コマンド: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="be720-154">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="be720-155">Vi 挿入モード: `<Ctrl+u>` 、 `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="be720-155">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="be720-156">Vi コマンドモード: `<Ctrl+u>` 、 `<Ctrl+Home>` 、 `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="be720-156">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="be720-157">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="be720-157">BackwardDeleteWord</span></span>

<span data-ttu-id="be720-158">前の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="be720-158">Deletes the previous word.</span></span>

- <span data-ttu-id="be720-159">Vi コマンドモード: `<Ctrl+w>` 、 `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="be720-159">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="be720-160">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="be720-160">BackwardKillLine</span></span>

<span data-ttu-id="be720-161">入力の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="be720-161">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="be720-162">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="be720-162">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="be720-163">Emacs: `<Ctrl+u>` 、 `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="be720-163">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="be720-164">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="be720-164">BackwardKillWord</span></span>

<span data-ttu-id="be720-165">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="be720-165">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="be720-166">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="be720-166">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="be720-167">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="be720-167">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="be720-168">コマンド: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="be720-168">Cmd: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="be720-169">Emacs: `<Alt+Backspace>` 、 `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="be720-169">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="be720-170">Vi の挿入モード: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="be720-170">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="be720-171">Vi コマンドモード: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="be720-171">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="be720-172">CancelLine</span><span class="sxs-lookup"><span data-stu-id="be720-172">CancelLine</span></span>

<span data-ttu-id="be720-173">入力を画面に残したまま、現在の入力を取り消しますが、プロンプトが再び評価されるように、ホストに戻ります。</span><span class="sxs-lookup"><span data-stu-id="be720-173">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="be720-174">Vi の挿入モード: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="be720-174">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="be720-175">Vi コマンドモード: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="be720-175">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="be720-176">コピー</span><span class="sxs-lookup"><span data-stu-id="be720-176">Copy</span></span>

<span data-ttu-id="be720-177">選択したリージョンをシステムクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="be720-177">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="be720-178">領域が選択されていない場合は、行全体をコピーします。</span><span class="sxs-lookup"><span data-stu-id="be720-178">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="be720-179">コマンド: `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="be720-179">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="be720-180">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="be720-180">CopyOrCancelLine</span></span>

<span data-ttu-id="be720-181">テキストが選択されている場合は、クリップボードにコピーします。それ以外の場合は、行をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="be720-181">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="be720-182">コマンド: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="be720-182">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="be720-183">.Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="be720-183">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="be720-184">［切り取り］</span><span class="sxs-lookup"><span data-stu-id="be720-184">Cut</span></span>

<span data-ttu-id="be720-185">削除されたテキストをシステムクリップボードに配置した、選択した領域を削除します。</span><span class="sxs-lookup"><span data-stu-id="be720-185">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="be720-186">コマンド: `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="be720-186">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="be720-187">Dele</span><span class="sxs-lookup"><span data-stu-id="be720-187">DeleteChar</span></span>

<span data-ttu-id="be720-188">カーソルの下の文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="be720-188">Delete the character under the cursor.</span></span>

- <span data-ttu-id="be720-189">コマンド: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="be720-189">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="be720-190">.Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="be720-190">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="be720-191">Vi の挿入モード: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="be720-191">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="be720-192">Vi コマンドモード: `<Delete>` 、 `<x>` 、 `<d,l>` 、 `<d,Space>`</span><span class="sxs-lookup"><span data-stu-id="be720-192">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Space>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="be720-193">Deleの Arorexit</span><span class="sxs-lookup"><span data-stu-id="be720-193">DeleteCharOrExit</span></span>

<span data-ttu-id="be720-194">カーソルの下の文字を削除するか、行が空の場合はプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="be720-194">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="be720-195">.Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="be720-195">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="be720-196">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="be720-196">DeleteEndOfWord</span></span>

<span data-ttu-id="be720-197">単語の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="be720-197">Delete to the end of the word.</span></span>

- <span data-ttu-id="be720-198">Vi コマンドモード: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="be720-198">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="be720-199">Deleteline.invoke に</span><span class="sxs-lookup"><span data-stu-id="be720-199">DeleteLine</span></span>

<span data-ttu-id="be720-200">現在の行を削除して、元に戻す操作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="be720-200">Deletes the current line, enabling undo.</span></span>

- <span data-ttu-id="be720-201">Vi コマンドモード: `<d,d>`</span><span class="sxs-lookup"><span data-stu-id="be720-201">Vi command mode: `<d,d>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="be720-202">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="be720-202">DeleteLineToFirstChar</span></span>

<span data-ttu-id="be720-203">カーソルから、行の最初の空白以外の文字までのテキストを削除します。</span><span class="sxs-lookup"><span data-stu-id="be720-203">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="be720-204">Vi コマンドモード: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="be720-204">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="be720-205">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="be720-205">DeleteToEnd</span></span>

<span data-ttu-id="be720-206">行の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="be720-206">Delete to the end of the line.</span></span>

- <span data-ttu-id="be720-207">Vi コマンドモード: `<D>` 、 `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="be720-207">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="be720-208">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="be720-208">DeleteWord</span></span>

<span data-ttu-id="be720-209">次の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="be720-209">Delete the next word.</span></span>

- <span data-ttu-id="be720-210">Vi コマンドモード: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="be720-210">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="be720-211">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="be720-211">ForwardDeleteLine</span></span>

<span data-ttu-id="be720-212">同じように、Forwardは、行の末尾から最後までのテキストを削除しますが、削除されたテキストはキルリングには挿入されません。</span><span class="sxs-lookup"><span data-stu-id="be720-212">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="be720-213">コマンド: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="be720-213">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="be720-214">Vi の挿入モード: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="be720-214">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="be720-215">Vi コマンドモード: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="be720-215">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="be720-216">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="be720-216">InsertLineAbove</span></span>

<span data-ttu-id="be720-217">現在の行の上にカーソルがある場所に関係なく、現在の行の上に新しい空の行が作成されます。</span><span class="sxs-lookup"><span data-stu-id="be720-217">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="be720-218">カーソルが新しい行の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-218">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="be720-219">コマンド: `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="be720-219">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="be720-220">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="be720-220">InsertLineBelow</span></span>

<span data-ttu-id="be720-221">カーソルが現在の行にある場所に関係なく、現在の行の下に新しい空の行が作成されます。</span><span class="sxs-lookup"><span data-stu-id="be720-221">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="be720-222">カーソルが新しい行の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-222">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="be720-223">コマンド: `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="be720-223">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="be720-224">InvertCase</span><span class="sxs-lookup"><span data-stu-id="be720-224">InvertCase</span></span>

<span data-ttu-id="be720-225">現在の文字の大文字と小文字の区別を反転し、次の文字に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-225">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="be720-226">Vi コマンドモード: `<~>`</span><span class="sxs-lookup"><span data-stu-id="be720-226">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="be720-227">行の行</span><span class="sxs-lookup"><span data-stu-id="be720-227">KillLine</span></span>

<span data-ttu-id="be720-228">カーソルから入力の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="be720-228">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="be720-229">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="be720-229">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="be720-230">.Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="be720-230">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="be720-231">"/" 領域</span><span class="sxs-lookup"><span data-stu-id="be720-231">KillRegion</span></span>

<span data-ttu-id="be720-232">カーソルとマークの間のテキストを強制終了します。</span><span class="sxs-lookup"><span data-stu-id="be720-232">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="be720-233">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="be720-233">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="be720-234">文字の候補</span><span class="sxs-lookup"><span data-stu-id="be720-234">KillWord</span></span>

<span data-ttu-id="be720-235">カーソルから現在の単語の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="be720-235">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="be720-236">カーソルが単語の間にある場合は、カーソルから次の単語の末尾まで、入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="be720-236">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="be720-237">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="be720-237">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="be720-238">コマンド: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="be720-238">Cmd: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="be720-239">Emacs: `<Alt+d>` 、 `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="be720-239">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="be720-240">Vi の挿入モード: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="be720-240">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="be720-241">Vi コマンドモード: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="be720-241">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="be720-242">貼り付け</span><span class="sxs-lookup"><span data-stu-id="be720-242">Paste</span></span>

<span data-ttu-id="be720-243">システムクリップボードからテキストを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="be720-243">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="be720-244">Cmd: `<Ctrl+v>` 、 `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="be720-244">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="be720-245">Vi の挿入モード: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="be720-245">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="be720-246">Vi コマンドモード: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="be720-246">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be720-247">**貼り付け** 関数を使用すると、クリップボードバッファーの内容全体が psreadline の入力バッファーに貼り付けられます。</span><span class="sxs-lookup"><span data-stu-id="be720-247">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="be720-248">入力バッファーが PowerShell パーサーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="be720-248">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="be720-249">コンソールアプリケーションの **右クリック** による貼り付けメソッドを使用して貼り付けた入力は、一度に1文字ずつ入力バッファーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="be720-249">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="be720-250">入力バッファーは、改行文字がコピーされるときにパーサーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="be720-250">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="be720-251">そのため、入力は一度に1行ずつ解析されます。</span><span class="sxs-lookup"><span data-stu-id="be720-251">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="be720-252">貼り付けメソッドの違いによって、実行の動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="be720-252">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="be720-253">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="be720-253">PasteAfter</span></span>

<span data-ttu-id="be720-254">カーソルの後にクリップボードを貼り付けて、貼り付けられたテキストの末尾にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-254">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="be720-255">Vi コマンドモード: `<p>`</span><span class="sxs-lookup"><span data-stu-id="be720-255">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="be720-256">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="be720-256">PasteBefore</span></span>

<span data-ttu-id="be720-257">カーソルの前にクリップボードを貼り付けて、貼り付けられたテキストの末尾にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-257">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="be720-258">Vi コマンドモード: `<P>`</span><span class="sxs-lookup"><span data-stu-id="be720-258">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="be720-259">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="be720-259">PrependAndAccept</span></span>

<span data-ttu-id="be720-260">' # ' を先頭に付加し、その行を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="be720-260">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="be720-261">Vi コマンドモード: `<#>`</span><span class="sxs-lookup"><span data-stu-id="be720-261">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="be720-262">やり直し</span><span class="sxs-lookup"><span data-stu-id="be720-262">Redo</span></span>

<span data-ttu-id="be720-263">元に戻す操作を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="be720-263">Undo an undo.</span></span>

- <span data-ttu-id="be720-264">コマンド: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="be720-264">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="be720-265">Vi の挿入モード: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="be720-265">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="be720-266">Vi コマンドモード: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="be720-266">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="be720-267">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="be720-267">RepeatLastCommand</span></span>

<span data-ttu-id="be720-268">最後のテキストの変更を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="be720-268">Repeat the last text modification.</span></span>

- <span data-ttu-id="be720-269">Vi コマンドモード: `<.>`</span><span class="sxs-lookup"><span data-stu-id="be720-269">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="be720-270">再有効化</span><span class="sxs-lookup"><span data-stu-id="be720-270">RevertLine</span></span>

<span data-ttu-id="be720-271">すべての入力を現在の入力に戻します。</span><span class="sxs-lookup"><span data-stu-id="be720-271">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="be720-272">コマンド: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="be720-272">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="be720-273">Emacs: `<Alt+r>` 、 `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="be720-273">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="be720-274">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="be720-274">ShellBackwardKillWord</span></span>

<span data-ttu-id="be720-275">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="be720-275">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="be720-276">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="be720-276">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="be720-277">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="be720-277">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="be720-278">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="be720-278">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="be720-279">Shellは Word</span><span class="sxs-lookup"><span data-stu-id="be720-279">ShellKillWord</span></span>

<span data-ttu-id="be720-280">カーソルから現在の単語の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="be720-280">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="be720-281">カーソルが単語の間にある場合は、カーソルから次の単語の末尾まで、入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="be720-281">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="be720-282">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="be720-282">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="be720-283">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="be720-283">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="be720-284">スワップ文字</span><span class="sxs-lookup"><span data-stu-id="be720-284">SwapCharacters</span></span>

<span data-ttu-id="be720-285">現在の文字とそれより前の文字を交換します。</span><span class="sxs-lookup"><span data-stu-id="be720-285">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="be720-286">.Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="be720-286">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="be720-287">Vi の挿入モード: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="be720-287">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="be720-288">Vi コマンドモード: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="be720-288">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="be720-289">元に戻す</span><span class="sxs-lookup"><span data-stu-id="be720-289">Undo</span></span>

<span data-ttu-id="be720-290">前の編集を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="be720-290">Undo a previous edit.</span></span>

- <span data-ttu-id="be720-291">コマンド: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="be720-291">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="be720-292">Emacs: `<Ctrl+_>` 、 `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="be720-292">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="be720-293">Vi の挿入モード: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="be720-293">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="be720-294">Vi コマンドモード: `<Ctrl+z>` 、 `<u>`</span><span class="sxs-lookup"><span data-stu-id="be720-294">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="be720-295">UndoAll</span><span class="sxs-lookup"><span data-stu-id="be720-295">UndoAll</span></span>

<span data-ttu-id="be720-296">行の以前の編集をすべて元に戻します。</span><span class="sxs-lookup"><span data-stu-id="be720-296">Undo all previous edits for line.</span></span>

- <span data-ttu-id="be720-297">Vi コマンドモード: `<U>`</span><span class="sxs-lookup"><span data-stu-id="be720-297">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="be720-298">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="be720-298">UnixWordRubout</span></span>

<span data-ttu-id="be720-299">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="be720-299">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="be720-300">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="be720-300">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="be720-301">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="be720-301">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="be720-302">.Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="be720-302">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="be720-303">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="be720-303">ValidateAndAcceptLine</span></span>

<span data-ttu-id="be720-304">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="be720-304">Attempt to execute the current input.</span></span> <span data-ttu-id="be720-305">現在の入力が不完全な場合 (たとえば、終わりかっこ、角かっこ、または引用符がない場合)、継続のプロンプトは次の行に表示され、PSReadLine は現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="be720-305">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="be720-306">.Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="be720-306">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="be720-307">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="be720-307">ViAcceptLine</span></span>

<span data-ttu-id="be720-308">行を受け入れ、挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="be720-308">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="be720-309">Vi コマンドモード: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="be720-309">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="be720-310">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="be720-310">ViAcceptLineOrExit</span></span>

<span data-ttu-id="be720-311">(Emacs モードでは Deleと同じですが、文字を削除するのではなく、行を受け取ります)。</span><span class="sxs-lookup"><span data-stu-id="be720-311">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="be720-312">Vi の挿入モード: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="be720-312">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="be720-313">Vi コマンドモード: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="be720-313">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="be720-314">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="be720-314">ViAppendLine</span></span>

<span data-ttu-id="be720-315">現在の行の下に新しい行が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="be720-315">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="be720-316">Vi コマンドモード: `<o>`</span><span class="sxs-lookup"><span data-stu-id="be720-316">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="be720-317">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="be720-317">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="be720-318">単語区切り記号として空白文字のみを使用して、前の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="be720-318">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="be720-319">Vi コマンドモード: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="be720-319">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="be720-320">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="be720-320">ViBackwardGlob</span></span>

<span data-ttu-id="be720-321">区切り記号として空白文字のみを使用して、カーソルを前の単語の先頭に戻します。</span><span class="sxs-lookup"><span data-stu-id="be720-321">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="be720-322">Vi コマンドモード: `<B>`</span><span class="sxs-lookup"><span data-stu-id="be720-322">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="be720-323">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="be720-323">ViDeleteBrace</span></span>

<span data-ttu-id="be720-324">対応する中かっこ、かっこ、または角かっこを検索し、中かっこを含め、内のすべての内容を削除します。</span><span class="sxs-lookup"><span data-stu-id="be720-324">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="be720-325">Vi コマンドモード: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="be720-325">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="be720-326">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="be720-326">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="be720-327">単語の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="be720-327">Delete to the end of the word.</span></span>

- <span data-ttu-id="be720-328">Vi コマンドモード: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="be720-328">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="be720-329">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="be720-329">ViDeleteGlob</span></span>

<span data-ttu-id="be720-330">次の glob (空白で区切られた単語) を削除します。</span><span class="sxs-lookup"><span data-stu-id="be720-330">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="be720-331">Vi コマンドモード: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="be720-331">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="be720-332">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="be720-332">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="be720-333">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="be720-333">Deletes until given character.</span></span>

- <span data-ttu-id="be720-334">Vi コマンドモード: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="be720-334">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="be720-335">Videletetobeforo</span><span class="sxs-lookup"><span data-stu-id="be720-335">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="be720-336">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="be720-336">Deletes until given character.</span></span>

- <span data-ttu-id="be720-337">Vi コマンドモード: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="be720-337">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="be720-338">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="be720-338">ViDeleteToChar</span></span>

<span data-ttu-id="be720-339">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="be720-339">Deletes until given character.</span></span>

- <span data-ttu-id="be720-340">Vi コマンドモード: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="be720-340">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="be720-341">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="be720-341">ViDeleteToCharBackward</span></span>

<span data-ttu-id="be720-342">指定された文字まで後方を削除します。</span><span class="sxs-lookup"><span data-stu-id="be720-342">Deletes backwards until given character.</span></span>

- <span data-ttu-id="be720-343">Vi コマンドモード: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="be720-343">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="be720-344">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="be720-344">ViInsertAtBegining</span></span>

<span data-ttu-id="be720-345">挿入モードに切り替え、カーソルを行の先頭に配置します。</span><span class="sxs-lookup"><span data-stu-id="be720-345">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="be720-346">Vi コマンドモード: `<I>`</span><span class="sxs-lookup"><span data-stu-id="be720-346">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="be720-347">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="be720-347">ViInsertAtEnd</span></span>

<span data-ttu-id="be720-348">挿入モードに切り替え、カーソルを行の末尾に配置します。</span><span class="sxs-lookup"><span data-stu-id="be720-348">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="be720-349">Vi コマンドモード: `<A>`</span><span class="sxs-lookup"><span data-stu-id="be720-349">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="be720-350">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="be720-350">ViInsertLine</span></span>

<span data-ttu-id="be720-351">現在の行の上に新しい行が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="be720-351">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="be720-352">Vi コマンドモード: `<O>`</span><span class="sxs-lookup"><span data-stu-id="be720-352">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="be720-353">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="be720-353">ViInsertWithAppend</span></span>

<span data-ttu-id="be720-354">現在の行の位置から追加します。</span><span class="sxs-lookup"><span data-stu-id="be720-354">Append from the current line position.</span></span>

- <span data-ttu-id="be720-355">Vi コマンドモード: `<a>`</span><span class="sxs-lookup"><span data-stu-id="be720-355">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="be720-356">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="be720-356">ViInsertWithDelete</span></span>

<span data-ttu-id="be720-357">現在の文字を削除し、挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="be720-357">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="be720-358">Vi コマンドモード: `<s>`</span><span class="sxs-lookup"><span data-stu-id="be720-358">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="be720-359">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="be720-359">ViJoinLines</span></span>

<span data-ttu-id="be720-360">現在の行と次の行を結合します。</span><span class="sxs-lookup"><span data-stu-id="be720-360">Joins the current line and the next line.</span></span>

- <span data-ttu-id="be720-361">Vi コマンドモード: `<J>`</span><span class="sxs-lookup"><span data-stu-id="be720-361">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="be720-362">交換ライン</span><span class="sxs-lookup"><span data-stu-id="be720-362">ViReplaceLine</span></span>

<span data-ttu-id="be720-363">コマンドライン全体を消去します。</span><span class="sxs-lookup"><span data-stu-id="be720-363">Erase the entire command line.</span></span>

- <span data-ttu-id="be720-364">Vi コマンドモード: `<S>` 、 `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="be720-364">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="be720-365">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="be720-365">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="be720-366">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="be720-366">Replaces until given character.</span></span>

- <span data-ttu-id="be720-367">Vi コマンドモード: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="be720-367">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="be720-368">Vireplacetobeforo</span><span class="sxs-lookup"><span data-stu-id="be720-368">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="be720-369">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="be720-369">Replaces until given character.</span></span>

- <span data-ttu-id="be720-370">Vi コマンドモード: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="be720-370">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="be720-371">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="be720-371">ViReplaceToChar</span></span>

<span data-ttu-id="be720-372">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="be720-372">Deletes until given character.</span></span>

- <span data-ttu-id="be720-373">Vi コマンドモード: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="be720-373">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="be720-374">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="be720-374">ViReplaceToCharBackward</span></span>

<span data-ttu-id="be720-375">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="be720-375">Replaces until given character.</span></span>

- <span data-ttu-id="be720-376">Vi コマンドモード: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="be720-376">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="be720-377">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="be720-377">ViYankBeginningOfLine</span></span>

<span data-ttu-id="be720-378">バッファーの先頭からカーソルまで Yank。</span><span class="sxs-lookup"><span data-stu-id="be720-378">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="be720-379">Vi コマンドモード: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="be720-379">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="be720-380">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="be720-380">ViYankEndOfGlob</span></span>

<span data-ttu-id="be720-381">カーソルから単語の末尾まで Yank します。</span><span class="sxs-lookup"><span data-stu-id="be720-381">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="be720-382">Vi コマンドモード: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="be720-382">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="be720-383">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="be720-383">ViYankEndOfWord</span></span>

<span data-ttu-id="be720-384">カーソルから単語の末尾まで Yank します。</span><span class="sxs-lookup"><span data-stu-id="be720-384">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="be720-385">Vi コマンドモード: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="be720-385">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="be720-386">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="be720-386">ViYankLeft</span></span>

<span data-ttu-id="be720-387">カーソルの左側の文字を Yank します。</span><span class="sxs-lookup"><span data-stu-id="be720-387">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="be720-388">Vi コマンドモード: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="be720-388">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="be720-389">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="be720-389">ViYankLine</span></span>

<span data-ttu-id="be720-390">バッファー全体を Yank します。</span><span class="sxs-lookup"><span data-stu-id="be720-390">Yank the entire buffer.</span></span>

- <span data-ttu-id="be720-391">Vi コマンドモード: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="be720-391">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="be720-392">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="be720-392">ViYankNextGlob</span></span>

<span data-ttu-id="be720-393">Yank は、次の単語の先頭にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="be720-393">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="be720-394">Vi コマンドモード: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="be720-394">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="be720-395">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="be720-395">ViYankNextWord</span></span>

<span data-ttu-id="be720-396">カーソルの後の単語を Yank します。</span><span class="sxs-lookup"><span data-stu-id="be720-396">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="be720-397">Vi コマンドモード: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="be720-397">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="be720-398">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="be720-398">ViYankPercent</span></span>

<span data-ttu-id="be720-399">一致する中かっこを Yank します。</span><span class="sxs-lookup"><span data-stu-id="be720-399">Yank to/from matching brace.</span></span>

- <span data-ttu-id="be720-400">Vi コマンドモード: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="be720-400">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="be720-401">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="be720-401">ViYankPreviousGlob</span></span>

<span data-ttu-id="be720-402">Yank は、単語の先頭からカーソルになります。</span><span class="sxs-lookup"><span data-stu-id="be720-402">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="be720-403">Vi コマンドモード: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="be720-403">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="be720-404">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="be720-404">ViYankPreviousWord</span></span>

<span data-ttu-id="be720-405">カーソルの前に単語を Yank します。</span><span class="sxs-lookup"><span data-stu-id="be720-405">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="be720-406">Vi コマンドモード: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="be720-406">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="be720-407">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="be720-407">ViYankRight</span></span>

<span data-ttu-id="be720-408">カーソルの右側に Yank 文字があります。</span><span class="sxs-lookup"><span data-stu-id="be720-408">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="be720-409">Vi コマンドモード: `<y,l>` 、 `<y,Space>`</span><span class="sxs-lookup"><span data-stu-id="be720-409">Vi command mode: `<y,l>`, `<y,Space>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="be720-410">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="be720-410">ViYankToEndOfLine</span></span>

<span data-ttu-id="be720-411">カーソルからバッファーの末尾までの Yank。</span><span class="sxs-lookup"><span data-stu-id="be720-411">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="be720-412">Vi コマンドモード: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="be720-412">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="be720-413">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="be720-413">ViYankToFirstChar</span></span>

<span data-ttu-id="be720-414">最初の空白以外の文字からカーソルまで Yank ます。</span><span class="sxs-lookup"><span data-stu-id="be720-414">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="be720-415">Vi コマンドモード: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="be720-415">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="be720-416">Yank</span><span class="sxs-lookup"><span data-stu-id="be720-416">Yank</span></span>

<span data-ttu-id="be720-417">最後に終了したテキストを入力に追加します。</span><span class="sxs-lookup"><span data-stu-id="be720-417">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="be720-418">.Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="be720-418">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="be720-419">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="be720-419">YankLastArg</span></span>

<span data-ttu-id="be720-420">前の履歴行の最後の引数を Yank します。</span><span class="sxs-lookup"><span data-stu-id="be720-420">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="be720-421">引数を使用すると、最初に呼び出されたときに、YankNthArg と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="be720-421">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="be720-422">複数回呼び出された場合は、代わりに履歴を反復処理し、引数に方向を設定します (負の方向が反転します)。</span><span class="sxs-lookup"><span data-stu-id="be720-422">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="be720-423">コマンド: `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="be720-423">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="be720-424">Emacs: `<Alt+.>` 、 `<Alt+_>` 、 `<Escape,.>` 、 `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="be720-424">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="be720-425">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="be720-425">YankNthArg</span></span>

<span data-ttu-id="be720-426">Yank は、前の履歴行から (コマンドの後に) 最初の引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="be720-426">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="be720-427">引数を使用して、n 番目の引数 (0 から始まる) を yank します。引数が負の場合は、最後の引数から開始します。</span><span class="sxs-lookup"><span data-stu-id="be720-427">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="be720-428">Emacs: `<Ctrl+Alt+y>` 、 `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="be720-428">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="be720-429">YankPop</span><span class="sxs-lookup"><span data-stu-id="be720-429">YankPop</span></span>

<span data-ttu-id="be720-430">前の操作が Yank または YankPop であった場合は、以前の引き抜かテキストをキルリングから次に強制終了されたテキストに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="be720-430">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="be720-431">Emacs: `<Alt+y>` 、 `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="be720-431">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="be720-432">カーソルの移動関数</span><span class="sxs-lookup"><span data-stu-id="be720-432">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="be720-433">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="be720-433">BackwardChar</span></span>

<span data-ttu-id="be720-434">カーソルを1文字左に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-434">Move the cursor one character to the left.</span></span> <span data-ttu-id="be720-435">これにより、カーソルが複数行の入力の前の行に移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="be720-435">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="be720-436">コマンド: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-436">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="be720-437">Emacs: `<LeftArrow>` 、 `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="be720-437">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>
- <span data-ttu-id="be720-438">Vi の挿入モード: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-438">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="be720-439">Vi コマンドモード: `<LeftArrow>` 、 `<Backspace>` 、 `<h>`</span><span class="sxs-lookup"><span data-stu-id="be720-439">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="be720-440">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="be720-440">BackwardWord</span></span>

<span data-ttu-id="be720-441">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-441">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="be720-442">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="be720-442">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="be720-443">コマンド: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-443">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="be720-444">Emacs: `<Alt+b>` 、 `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="be720-444">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="be720-445">Vi の挿入モード: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-445">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="be720-446">Vi コマンドモード: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-446">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="be720-447">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="be720-447">BeginningOfLine</span></span>

<span data-ttu-id="be720-448">入力に複数の行がある場合は、現在の行の先頭に移動します。または、既に行の先頭にある場合は、入力の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-448">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="be720-449">入力に1行しか含まれていない場合は、入力の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-449">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="be720-450">コマンド: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="be720-450">Cmd: `<Home>`</span></span>
- <span data-ttu-id="be720-451">Emacs: `<Home>` 、 `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="be720-451">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="be720-452">Vi の挿入モード: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="be720-452">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="be720-453">Vi コマンドモード: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="be720-453">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="be720-454">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="be720-454">EndOfLine</span></span>

<span data-ttu-id="be720-455">入力に複数の行がある場合は、現在の行の末尾に移動します。または、既に行の末尾にある場合は、入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-455">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="be720-456">入力に1行しか含まれていない場合は、入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-456">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="be720-457">コマンド: `<End>`</span><span class="sxs-lookup"><span data-stu-id="be720-457">Cmd: `<End>`</span></span>
- <span data-ttu-id="be720-458">Emacs: `<End>` 、 `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="be720-458">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="be720-459">Vi の挿入モード: `<End>`</span><span class="sxs-lookup"><span data-stu-id="be720-459">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="be720-460">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="be720-460">ForwardChar</span></span>

<span data-ttu-id="be720-461">カーソルを1文字右に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-461">Move the cursor one character to the right.</span></span> <span data-ttu-id="be720-462">これにより、カーソルが複数行入力の次の行に移動する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="be720-462">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="be720-463">コマンド: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-463">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="be720-464">Emacs: `<RightArrow>` 、 `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="be720-464">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>
- <span data-ttu-id="be720-465">Vi の挿入モード: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-465">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="be720-466">Vi コマンドモード: `<RightArrow>` 、 `<Space>` 、 `<l>`</span><span class="sxs-lookup"><span data-stu-id="be720-466">Vi command mode: `<RightArrow>`, `<Space>`, `<l>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="be720-467">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="be720-467">ForwardWord</span></span>

<span data-ttu-id="be720-468">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-468">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="be720-469">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="be720-469">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="be720-470">Emacs: `<Alt+f>` 、 `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="be720-470">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="be720-471">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="be720-471">GotoBrace</span></span>

<span data-ttu-id="be720-472">対応する中かっこ、かっこ、または角かっこにジャンプします。</span><span class="sxs-lookup"><span data-stu-id="be720-472">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="be720-473">コマンド: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="be720-473">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="be720-474">Vi の挿入モード: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="be720-474">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="be720-475">Vi コマンドモード: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="be720-475">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="be720-476">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="be720-476">GotoColumn</span></span>

<span data-ttu-id="be720-477">Arg で示される列に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-477">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="be720-478">Vi コマンドモード: `<|>`</span><span class="sxs-lookup"><span data-stu-id="be720-478">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="be720-479">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="be720-479">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="be720-480">カーソルを行の空白以外の最初の文字に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-480">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="be720-481">Vi コマンドモード: `<^>`</span><span class="sxs-lookup"><span data-stu-id="be720-481">Vi command mode: `<^>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="be720-482">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="be720-482">MoveToEndOfLine</span></span>

<span data-ttu-id="be720-483">カーソルを入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-483">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="be720-484">Vi コマンドモード: `<End>` 、 `<$>`</span><span class="sxs-lookup"><span data-stu-id="be720-484">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="be720-485">NextLine</span><span class="sxs-lookup"><span data-stu-id="be720-485">NextLine</span></span>

<span data-ttu-id="be720-486">カーソルを次の行に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-486">Move the cursor to the next line.</span></span>

- <span data-ttu-id="be720-487">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="be720-487">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="be720-488">NextWord</span><span class="sxs-lookup"><span data-stu-id="be720-488">NextWord</span></span>

<span data-ttu-id="be720-489">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-489">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="be720-490">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="be720-490">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="be720-491">コマンド: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-491">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="be720-492">Vi の挿入モード: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-492">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="be720-493">Vi コマンドモード: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-493">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="be720-494">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="be720-494">NextWordEnd</span></span>

<span data-ttu-id="be720-495">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-495">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="be720-496">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="be720-496">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="be720-497">Vi コマンドモード: `<e>`</span><span class="sxs-lookup"><span data-stu-id="be720-497">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="be720-498">前の行</span><span class="sxs-lookup"><span data-stu-id="be720-498">PreviousLine</span></span>

<span data-ttu-id="be720-499">カーソルを前の行に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-499">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="be720-500">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="be720-500">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="be720-501">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="be720-501">ShellBackwardWord</span></span>

<span data-ttu-id="be720-502">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-502">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="be720-503">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="be720-503">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="be720-504">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="be720-504">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="be720-505">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="be720-505">ShellForwardWord</span></span>

<span data-ttu-id="be720-506">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-506">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="be720-507">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="be720-507">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="be720-508">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="be720-508">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="be720-509">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="be720-509">ShellNextWord</span></span>

<span data-ttu-id="be720-510">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-510">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="be720-511">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="be720-511">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="be720-512">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="be720-512">Function is unbound.</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="be720-513">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="be720-513">ViBackwardWord</span></span>

<span data-ttu-id="be720-514">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-514">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="be720-515">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="be720-515">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="be720-516">Vi コマンドモード: `<b>`</span><span class="sxs-lookup"><span data-stu-id="be720-516">Vi command mode: `<b>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="be720-517">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="be720-517">ViEndOfGlob</span></span>

<span data-ttu-id="be720-518">区切り記号として空白文字のみを使用して、カーソルを単語の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-518">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="be720-519">Vi コマンドモード: `<E>`</span><span class="sxs-lookup"><span data-stu-id="be720-519">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="be720-520">Viendofの Glob</span><span class="sxs-lookup"><span data-stu-id="be720-520">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="be720-521">単語区切り記号として空白文字のみを使用して、前の単語の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-521">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="be720-522">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="be720-522">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="be720-523">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="be720-523">ViGotoBrace</span></span>

<span data-ttu-id="be720-524">GotoBrace に似ていますが、トークンベースではなく文字ベースです。</span><span class="sxs-lookup"><span data-stu-id="be720-524">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="be720-525">Vi コマンドモード: `<%>`</span><span class="sxs-lookup"><span data-stu-id="be720-525">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="be720-526">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="be720-526">ViNextGlob</span></span>

<span data-ttu-id="be720-527">単語区切り記号として空白文字のみを使用して、次の単語に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-527">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="be720-528">Vi コマンドモード: `<W>`</span><span class="sxs-lookup"><span data-stu-id="be720-528">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="be720-529">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="be720-529">ViNextWord</span></span>

<span data-ttu-id="be720-530">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-530">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="be720-531">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="be720-531">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="be720-532">Vi コマンドモード: `<w>`</span><span class="sxs-lookup"><span data-stu-id="be720-532">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="be720-533">履歴関数</span><span class="sxs-lookup"><span data-stu-id="be720-533">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="be720-534">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="be720-534">BeginningOfHistory</span></span>

<span data-ttu-id="be720-535">履歴内の最初の項目に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-535">Move to the first item in the history.</span></span>

- <span data-ttu-id="be720-536">.Emacs `<Alt+`<>\`</span><span class="sxs-lookup"><span data-stu-id="be720-536">Emacs: `<Alt+`<>\`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="be720-537">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="be720-537">ClearHistory</span></span>

<span data-ttu-id="be720-538">PSReadLine の履歴をクリアします。</span><span class="sxs-lookup"><span data-stu-id="be720-538">Clears history in PSReadLine.</span></span> <span data-ttu-id="be720-539">これは、PowerShell の履歴には影響しません。</span><span class="sxs-lookup"><span data-stu-id="be720-539">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="be720-540">コマンド: `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="be720-540">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="be720-541">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="be720-541">EndOfHistory</span></span>

<span data-ttu-id="be720-542">履歴内の最後の項目 (現在の入力) に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-542">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="be720-543">.Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="be720-543">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="be720-544">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="be720-544">ForwardSearchHistory</span></span>

<span data-ttu-id="be720-545">履歴を使用した増分転送検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="be720-545">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="be720-546">コマンド: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="be720-546">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="be720-547">.Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="be720-547">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="be720-548">履歴の Search後方</span><span class="sxs-lookup"><span data-stu-id="be720-548">HistorySearchBackward</span></span>

<span data-ttu-id="be720-549">現在の入力を、PSReadLine 履歴の ' previous ' 項目で置き換えます。この項目は、開始と入力の間の文字とカーソルの間の文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="be720-549">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="be720-550">コマンド: `<F8>`</span><span class="sxs-lookup"><span data-stu-id="be720-550">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="be720-551">履歴の Searchforward</span><span class="sxs-lookup"><span data-stu-id="be720-551">HistorySearchForward</span></span>

<span data-ttu-id="be720-552">現在の入力を、PSReadLine 履歴の ' next ' 項目で置き換えます。この項目は、開始と入力の間の文字とカーソルの間の文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="be720-552">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="be720-553">コマンド: `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="be720-553">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="be720-554">NextHistory</span><span class="sxs-lookup"><span data-stu-id="be720-554">NextHistory</span></span>

<span data-ttu-id="be720-555">現在の入力を、PSReadLine 履歴の ' next ' 項目に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="be720-555">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="be720-556">コマンド: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-556">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="be720-557">Emacs: `<DownArrow>` 、 `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="be720-557">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="be720-558">Vi の挿入モード: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-558">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="be720-559">Vi コマンドモード: `<DownArrow>` 、 `<j>` 、 `<+>`</span><span class="sxs-lookup"><span data-stu-id="be720-559">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="be720-560">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="be720-560">PreviousHistory</span></span>

<span data-ttu-id="be720-561">現在の入力を、PSReadLine 履歴の ' previous ' 項目に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="be720-561">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="be720-562">コマンド: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-562">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="be720-563">Emacs: `<UpArrow>` 、 `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="be720-563">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="be720-564">Vi の挿入モード: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-564">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="be720-565">Vi コマンドモード: `<UpArrow>` 、 `<k>` 、 `<->`</span><span class="sxs-lookup"><span data-stu-id="be720-565">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="be720-566">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="be720-566">ReverseSearchHistory</span></span>

<span data-ttu-id="be720-567">履歴を介して後方検索を段階的に実行します。</span><span class="sxs-lookup"><span data-stu-id="be720-567">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="be720-568">コマンド: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="be720-568">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="be720-569">.Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="be720-569">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="be720-570">Visearchhistory 後方</span><span class="sxs-lookup"><span data-stu-id="be720-570">ViSearchHistoryBackward</span></span>

<span data-ttu-id="be720-571">検索文字列を入力し、AcceptLine で検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="be720-571">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="be720-572">Vi の挿入モード: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="be720-572">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="be720-573">Vi コマンドモード: `</>` 、 `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="be720-573">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="be720-574">入力候補関数</span><span class="sxs-lookup"><span data-stu-id="be720-574">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="be720-575">完了</span><span class="sxs-lookup"><span data-stu-id="be720-575">Complete</span></span>

<span data-ttu-id="be720-576">カーソルを囲むテキストに対して入力候補を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="be720-576">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="be720-577">候補が複数ある場合は、最長の明確なプレフィックスを使用して完了します。</span><span class="sxs-lookup"><span data-stu-id="be720-577">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="be720-578">最長の明確な完了を完了しようとすると、候補の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be720-578">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="be720-579">.Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="be720-579">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="be720-580">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="be720-580">MenuComplete</span></span>

<span data-ttu-id="be720-581">カーソルを囲むテキストに対して入力候補を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="be720-581">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="be720-582">候補が複数ある場合は、最長の明確なプレフィックスを使用して完了します。</span><span class="sxs-lookup"><span data-stu-id="be720-582">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="be720-583">最長の明確な完了を完了しようとすると、候補の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be720-583">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="be720-584">コマンド: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="be720-584">Cmd: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="be720-585">.Emacs `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="be720-585">Emacs: `<Ctrl+Space>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="be720-586">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="be720-586">PossibleCompletions</span></span>

<span data-ttu-id="be720-587">候補の候補の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="be720-587">Display the list of possible completions.</span></span>

- <span data-ttu-id="be720-588">.Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="be720-588">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="be720-589">Vi の挿入モード: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="be720-589">Vi insert mode: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="be720-590">Vi コマンドモード: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="be720-590">Vi command mode: `<Ctrl+Space>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="be720-591">タブのすべてのタブ</span><span class="sxs-lookup"><span data-stu-id="be720-591">TabCompleteNext</span></span>

<span data-ttu-id="be720-592">次に使用可能な完了時に、カーソルを囲むテキストを完了します。</span><span class="sxs-lookup"><span data-stu-id="be720-592">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="be720-593">コマンド: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="be720-593">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="be720-594">Vi コマンドモード: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="be720-594">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="be720-595">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="be720-595">TabCompletePrevious</span></span>

<span data-ttu-id="be720-596">以前に使用可能な入力候補を使用して、カーソルを囲むテキストを完了しようとしました。</span><span class="sxs-lookup"><span data-stu-id="be720-596">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="be720-597">コマンド: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="be720-597">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="be720-598">Vi コマンドモード: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="be720-598">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="be720-599">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="be720-599">ViTabCompleteNext</span></span>

<span data-ttu-id="be720-600">必要に応じて現在の編集グループを終了し、Tabends を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="be720-600">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="be720-601">Vi の挿入モード: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="be720-601">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="be720-602">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="be720-602">ViTabCompletePrevious</span></span>

<span data-ttu-id="be720-603">必要に応じて現在の編集グループを終了し、TabCompletePrevious を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="be720-603">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="be720-604">Vi の挿入モード: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="be720-604">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="be720-605">その他の関数</span><span class="sxs-lookup"><span data-stu-id="be720-605">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="be720-606">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="be720-606">CaptureScreen</span></span>

<span data-ttu-id="be720-607">対話型画面のキャプチャを開始する/下矢印行を選択し、[選択したテキストをテキストと html としてクリップボードにコピーする] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="be720-607">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="be720-608">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="be720-608">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="be720-609">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="be720-609">ClearScreen</span></span>

<span data-ttu-id="be720-610">画面をクリアし、画面の上部にある現在の線を描画します。</span><span class="sxs-lookup"><span data-stu-id="be720-610">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="be720-611">コマンド: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="be720-611">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="be720-612">.Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="be720-612">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="be720-613">Vi の挿入モード: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="be720-613">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="be720-614">Vi コマンドモード: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="be720-614">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="be720-615">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="be720-615">DigitArgument</span></span>

<span data-ttu-id="be720-616">他の関数に渡す新しい桁引数を開始します。</span><span class="sxs-lookup"><span data-stu-id="be720-616">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="be720-617">Cmd:、、、、、、、、、 `<Alt+0>` `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="be720-617">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="be720-618">Emacs:、、、、、、、、、 `<Alt+0>` `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="be720-618">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="be720-619">Vi コマンドモード:、、、、、、、、 `<0>` `<1>` `<2>` `<3>` `<4>` `<5>` `<6>` `<7>` `<8>` 、 `<9>`</span><span class="sxs-lookup"><span data-stu-id="be720-619">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="be720-620">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="be720-620">InvokePrompt</span></span>

<span data-ttu-id="be720-621">現在のプロンプトを消去し、prompt 関数を呼び出してプロンプトを再表示します。</span><span class="sxs-lookup"><span data-stu-id="be720-621">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="be720-622">現在のディレクトリを変更するなど、状態を変更するカスタムキーハンドラーに便利です。</span><span class="sxs-lookup"><span data-stu-id="be720-622">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="be720-623">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="be720-623">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="be720-624">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="be720-624">ScrollDisplayDown</span></span>

<span data-ttu-id="be720-625">画面を1画面下へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="be720-625">Scroll the display down one screen.</span></span>

- <span data-ttu-id="be720-626">コマンド: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="be720-626">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="be720-627">.Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="be720-627">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="be720-628">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="be720-628">ScrollDisplayDownLine</span></span>

<span data-ttu-id="be720-629">表示を1行下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="be720-629">Scroll the display down one line.</span></span>

- <span data-ttu-id="be720-630">コマンド: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="be720-630">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="be720-631">.Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="be720-631">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="be720-632">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="be720-632">ScrollDisplayToCursor</span></span>

<span data-ttu-id="be720-633">カーソルまで画面をスクロールします。</span><span class="sxs-lookup"><span data-stu-id="be720-633">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="be720-634">.Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="be720-634">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="be720-635">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="be720-635">ScrollDisplayTop</span></span>

<span data-ttu-id="be720-636">画面を上にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="be720-636">Scroll the display to the top.</span></span>

- <span data-ttu-id="be720-637">.Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="be720-637">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="be720-638">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="be720-638">ScrollDisplayUp</span></span>

<span data-ttu-id="be720-639">画面を1画面上へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="be720-639">Scroll the display up one screen.</span></span>

- <span data-ttu-id="be720-640">コマンド: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="be720-640">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="be720-641">.Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="be720-641">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="be720-642">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="be720-642">ScrollDisplayUpLine</span></span>

<span data-ttu-id="be720-643">表示を1行上へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="be720-643">Scroll the display up one line.</span></span>

- <span data-ttu-id="be720-644">コマンド: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="be720-644">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="be720-645">.Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="be720-645">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="be720-646">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="be720-646">SelfInsert</span></span>

<span data-ttu-id="be720-647">キーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="be720-647">Insert the key.</span></span>

- <span data-ttu-id="be720-648">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="be720-648">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="be720-649">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="be720-649">ShowKeyBindings</span></span>

<span data-ttu-id="be720-650">すべてのバインドされたキーを表示します。</span><span class="sxs-lookup"><span data-stu-id="be720-650">Show all bound keys.</span></span>

- <span data-ttu-id="be720-651">コマンド: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="be720-651">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="be720-652">.Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="be720-652">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="be720-653">Vi の挿入モード: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="be720-653">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="be720-654">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="be720-654">ViCommandMode</span></span>

<span data-ttu-id="be720-655">現在の動作モードを Vi-Insert から Vi-Command に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="be720-655">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="be720-656">Vi の挿入モード: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="be720-656">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="be720-657">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="be720-657">ViDigitArgumentInChord</span></span>

<span data-ttu-id="be720-658">Vi のいずれかの弦で、他の関数に渡す新しい桁引数を開始します。</span><span class="sxs-lookup"><span data-stu-id="be720-658">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="be720-659">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="be720-659">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="be720-660">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="be720-660">ViEditVisually</span></span>

<span data-ttu-id="be720-661">$Env: EDITOR または $env: ビジュアルによって指定されたテキストエディターでコマンドラインを編集します。</span><span class="sxs-lookup"><span data-stu-id="be720-661">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="be720-662">.Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="be720-662">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="be720-663">Vi コマンドモード: `<v>`</span><span class="sxs-lookup"><span data-stu-id="be720-663">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="be720-664">ViExit</span><span class="sxs-lookup"><span data-stu-id="be720-664">ViExit</span></span>

<span data-ttu-id="be720-665">シェルを終了します。</span><span class="sxs-lookup"><span data-stu-id="be720-665">Exits the shell.</span></span>

- <span data-ttu-id="be720-666">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="be720-666">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="be720-667">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="be720-667">ViInsertMode</span></span>

<span data-ttu-id="be720-668">挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="be720-668">Switch to Insert mode.</span></span>

- <span data-ttu-id="be720-669">Vi コマンドモード: `<i>`</span><span class="sxs-lookup"><span data-stu-id="be720-669">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="be720-670">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="be720-670">WhatIsKey</span></span>

<span data-ttu-id="be720-671">キーを読み取り、キーがどのようにバインドされているかを通知します。</span><span class="sxs-lookup"><span data-stu-id="be720-671">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="be720-672">コマンド: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="be720-672">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="be720-673">.Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="be720-673">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="be720-674">選択関数</span><span class="sxs-lookup"><span data-stu-id="be720-674">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="be720-675">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="be720-675">ExchangePointAndMark</span></span>

<span data-ttu-id="be720-676">カーソルがマークの位置に置かれ、マークがカーソルの位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-676">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="be720-677">.Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="be720-677">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="be720-678">SelectAll</span><span class="sxs-lookup"><span data-stu-id="be720-678">SelectAll</span></span>

<span data-ttu-id="be720-679">行全体を選択します。</span><span class="sxs-lookup"><span data-stu-id="be720-679">Select the entire line.</span></span>

- <span data-ttu-id="be720-680">コマンド: `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="be720-680">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="be720-681">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="be720-681">SelectBackwardChar</span></span>

<span data-ttu-id="be720-682">現在の選択範囲を調整して、前の文字を含めます。</span><span class="sxs-lookup"><span data-stu-id="be720-682">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="be720-683">コマンド: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-683">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="be720-684">.Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-684">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="be720-685">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="be720-685">SelectBackwardsLine</span></span>

<span data-ttu-id="be720-686">カーソルから行の先頭まで、現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="be720-686">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="be720-687">コマンド: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="be720-687">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="be720-688">.Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="be720-688">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="be720-689">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="be720-689">SelectBackwardWord</span></span>

<span data-ttu-id="be720-690">現在の選択範囲を調整して、前の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="be720-690">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="be720-691">コマンド: `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-691">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="be720-692">.Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="be720-692">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="be720-693">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="be720-693">SelectForwardChar</span></span>

<span data-ttu-id="be720-694">現在の選択範囲を調整して、次の文字を含めます。</span><span class="sxs-lookup"><span data-stu-id="be720-694">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="be720-695">コマンド: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-695">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="be720-696">.Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-696">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="be720-697">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="be720-697">SelectForwardWord</span></span>

<span data-ttu-id="be720-698">現在の選択範囲を調整して、ForwardWord を使用して次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="be720-698">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="be720-699">.Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="be720-699">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="be720-700">SelectLine</span><span class="sxs-lookup"><span data-stu-id="be720-700">SelectLine</span></span>

<span data-ttu-id="be720-701">カーソルから行の末尾まで、現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="be720-701">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="be720-702">コマンド: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="be720-702">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="be720-703">.Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="be720-703">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="be720-704">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="be720-704">SelectNextWord</span></span>

<span data-ttu-id="be720-705">現在の選択範囲を調整して、次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="be720-705">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="be720-706">コマンド: `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="be720-706">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="be720-707">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="be720-707">SelectShellBackwardWord</span></span>

<span data-ttu-id="be720-708">ShellBackwardWord を使用して、前の単語が含まれるように現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="be720-708">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="be720-709">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="be720-709">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="be720-710">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="be720-710">SelectShellForwardWord</span></span>

<span data-ttu-id="be720-711">現在の選択範囲を調整して、ShellForwardWord を使用する次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="be720-711">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="be720-712">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="be720-712">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="be720-713">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="be720-713">SelectShellNextWord</span></span>

<span data-ttu-id="be720-714">現在の選択範囲を調整して、ShellNextWord を使用して次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="be720-714">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="be720-715">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="be720-715">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="be720-716">SetMark</span><span class="sxs-lookup"><span data-stu-id="be720-716">SetMark</span></span>

<span data-ttu-id="be720-717">後続の編集コマンドで使用するために、カーソルの現在の位置をマークします。</span><span class="sxs-lookup"><span data-stu-id="be720-717">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="be720-718">.Emacs `<Ctrl+`>\`</span><span class="sxs-lookup"><span data-stu-id="be720-718">Emacs: `<Ctrl+`>\`</span></span>

## <a name="search-functions"></a><span data-ttu-id="be720-719">関数の検索</span><span class="sxs-lookup"><span data-stu-id="be720-719">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="be720-720">文字検索</span><span class="sxs-lookup"><span data-stu-id="be720-720">CharacterSearch</span></span>

<span data-ttu-id="be720-721">文字を読み取り、その文字が次に出現するまで検索します。</span><span class="sxs-lookup"><span data-stu-id="be720-721">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="be720-722">引数が指定されている場合は、n 番目のオカレンスに対して前方 (負の場合は後方) を検索します。</span><span class="sxs-lookup"><span data-stu-id="be720-722">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="be720-723">コマンド: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="be720-723">Cmd: `<F3>`</span></span>
- <span data-ttu-id="be720-724">.Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="be720-724">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="be720-725">Vi の挿入モード: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="be720-725">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="be720-726">Vi コマンドモード: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="be720-726">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="be720-727">文字 Search後方</span><span class="sxs-lookup"><span data-stu-id="be720-727">CharacterSearchBackward</span></span>

<span data-ttu-id="be720-728">文字を読み取り、その文字が次に出現するまで検索します。</span><span class="sxs-lookup"><span data-stu-id="be720-728">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="be720-729">引数が指定されている場合は、n 番目のオカレンスに対して後方 (または負の場合は forward) を検索します。</span><span class="sxs-lookup"><span data-stu-id="be720-729">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="be720-730">コマンド: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="be720-730">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="be720-731">.Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="be720-731">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="be720-732">Vi の挿入モード: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="be720-732">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="be720-733">Vi コマンドモード: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="be720-733">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="be720-734">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="be720-734">RepeatLastCharSearch</span></span>

<span data-ttu-id="be720-735">最後に記録された文字の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="be720-735">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="be720-736">Vi コマンドモード: `<;>`</span><span class="sxs-lookup"><span data-stu-id="be720-736">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="be720-737">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="be720-737">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="be720-738">最後に記録された文字検索を逆方向に繰り返します。</span><span class="sxs-lookup"><span data-stu-id="be720-738">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="be720-739">Vi コマンドモード: `<,>`</span><span class="sxs-lookup"><span data-stu-id="be720-739">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="be720-740">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="be720-740">RepeatSearch</span></span>

<span data-ttu-id="be720-741">前と同じ方向に最後の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="be720-741">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="be720-742">Vi コマンドモード: `<n>`</span><span class="sxs-lookup"><span data-stu-id="be720-742">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="be720-743">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="be720-743">RepeatSearchBackward</span></span>

<span data-ttu-id="be720-744">前と同じ方向に最後の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="be720-744">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="be720-745">Vi コマンドモード: `<N>`</span><span class="sxs-lookup"><span data-stu-id="be720-745">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="be720-746">SearchChar</span><span class="sxs-lookup"><span data-stu-id="be720-746">SearchChar</span></span>

<span data-ttu-id="be720-747">次の文字を読み取って検索し、次に文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="be720-747">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="be720-748">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="be720-748">This is for 't' functionality.</span></span>

- <span data-ttu-id="be720-749">Vi コマンドモード: `<f>`</span><span class="sxs-lookup"><span data-stu-id="be720-749">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="be720-750">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="be720-750">SearchCharBackward</span></span>

<span data-ttu-id="be720-751">次の文字を読み取り、それを検索して後方に移動し、次に文字を戻します。</span><span class="sxs-lookup"><span data-stu-id="be720-751">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="be720-752">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="be720-752">This is for 'T' functionality.</span></span>

- <span data-ttu-id="be720-753">Vi コマンドモード: `<F>`</span><span class="sxs-lookup"><span data-stu-id="be720-753">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="be720-754">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="be720-754">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="be720-755">次の文字を読み取り、それを検索して後方に移動し、次に文字を戻します。</span><span class="sxs-lookup"><span data-stu-id="be720-755">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="be720-756">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="be720-756">This is for 'T' functionality.</span></span>

- <span data-ttu-id="be720-757">Vi コマンドモード: `<T>`</span><span class="sxs-lookup"><span data-stu-id="be720-757">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="be720-758">SearchCharWithBackoff オフ</span><span class="sxs-lookup"><span data-stu-id="be720-758">SearchCharWithBackoff</span></span>

<span data-ttu-id="be720-759">次の文字を読み取って検索し、次に文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="be720-759">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="be720-760">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="be720-760">This is for 't' functionality.</span></span>

- <span data-ttu-id="be720-761">Vi コマンドモード: `<t>`</span><span class="sxs-lookup"><span data-stu-id="be720-761">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="be720-762">SearchForward</span><span class="sxs-lookup"><span data-stu-id="be720-762">SearchForward</span></span>

<span data-ttu-id="be720-763">検索文字列を入力し、AcceptLine で検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="be720-763">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="be720-764">Vi の挿入モード: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="be720-764">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="be720-765">Vi コマンドモード: `<?>` 、 `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="be720-765">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="be720-766">カスタムキーバインド</span><span class="sxs-lookup"><span data-stu-id="be720-766">Custom Key Bindings</span></span>

<span data-ttu-id="be720-767">PSReadLine は、コマンドレットを使用してカスタムキーバインドをサポートしてい `Set-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="be720-767">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="be720-768">ほとんどのカスタムキーバインドは、たとえば、上記の関数の1つを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="be720-768">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="be720-769">ScriptBlock をキーにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="be720-769">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="be720-770">ScriptBlock は、ほとんどすべてのことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="be720-770">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="be720-771">いくつかの便利な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="be720-771">Some useful examples include</span></span>

- <span data-ttu-id="be720-772">コマンドラインを編集する</span><span class="sxs-lookup"><span data-stu-id="be720-772">edit the command line</span></span>
- <span data-ttu-id="be720-773">新しいウィンドウを開く (例: ヘルプ)</span><span class="sxs-lookup"><span data-stu-id="be720-773">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="be720-774">コマンドラインを変更せずにディレクトリを変更する</span><span class="sxs-lookup"><span data-stu-id="be720-774">change directories without changing the command line</span></span>

<span data-ttu-id="be720-775">ScriptBlock は、次の2つの引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="be720-775">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="be720-776">`$key` -カスタムバインドをトリガーしたキーである **[Consolekeyinfo]** オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="be720-776">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="be720-777">同じ ScriptBlock を複数のキーにバインドし、キーに応じて異なるアクションを実行する必要がある場合は、$key を確認します。</span><span class="sxs-lookup"><span data-stu-id="be720-777">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="be720-778">多くのカスタムバインドでは、この引数は無視します。</span><span class="sxs-lookup"><span data-stu-id="be720-778">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="be720-779">`$arg` -任意の引数。</span><span class="sxs-lookup"><span data-stu-id="be720-779">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="be720-780">多くの場合、これは、ユーザーがキーバインド DigitArgument から渡す整数引数になります。</span><span class="sxs-lookup"><span data-stu-id="be720-780">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="be720-781">バインディングが引数を受け入れない場合は、この引数を無視するのが妥当です。</span><span class="sxs-lookup"><span data-stu-id="be720-781">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="be720-782">ここでは、コマンドラインを実行せずに履歴に追加する例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="be720-782">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="be720-783">これは、何らかの操作を忘れた場合に、既に入力したコマンドラインを再入力したくない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="be720-783">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

```powershell
$parameters = @{
    Key = 'Alt+w'
    BriefDescription = 'SaveInHistory'
    LongDescription = 'Save current line in history but do not execute'
    ScriptBlock = {
      param($key, $arg)   # The arguments are ignored in this example

      # GetBufferState gives us the command line (with the cursor position)
      $line = $null
      $cursor = $null
      [Microsoft.PowerShell.PSConsoleReadLine]::GetBufferState([ref]$line,
        [ref]$cursor)

      # AddToHistory saves the line in history, but does not execute it.
      [Microsoft.PowerShell.PSConsoleReadLine]::AddToHistory($line)

      # RevertLine is like pressing Escape.
      [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
  }
}
Set-PSReadLineKeyHandler @parameters
```

<span data-ttu-id="be720-784">PSReadLine モジュールフォルダーにインストールされているファイルには、さらに多くの例が表示 `SamplePSReadLineProfile.ps1` されます。</span><span class="sxs-lookup"><span data-stu-id="be720-784">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="be720-785">ほとんどのキーバインドでは、コマンドラインを編集するためにいくつかのヘルパー関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="be720-785">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="be720-786">これらの Api については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="be720-786">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="be720-787">カスタムキーバインディングサポート Api</span><span class="sxs-lookup"><span data-stu-id="be720-787">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="be720-788">次の関数は PSConsoleReadLine では公開されていますが、キーに直接バインドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="be720-788">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="be720-789">多くの場合、カスタムキーバインドに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="be720-789">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="be720-790">コマンドラインを実行せずに、履歴に追加します。</span><span class="sxs-lookup"><span data-stu-id="be720-790">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="be720-791">Kill リングをクリアします。</span><span class="sxs-lookup"><span data-stu-id="be720-791">Clear the kill-ring.</span></span>  <span data-ttu-id="be720-792">これは主にテストに使用されます。</span><span class="sxs-lookup"><span data-stu-id="be720-792">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="be720-793">先頭から長さの文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="be720-793">Delete length characters from start.</span></span>  <span data-ttu-id="be720-794">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="be720-794">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="be720-795">ユーザー設定に基づいてアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="be720-795">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="be720-796">これらの2つの関数は、入力バッファーの現在の状態に関する有用な情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="be720-796">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="be720-797">1つ目は、単純なケースでよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="be720-797">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="be720-798">2つ目は、バインディングが Ast を使用してより高度な処理を実行している場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="be720-798">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

```

<span data-ttu-id="be720-799">この関数は Get-PSReadLineKeyHandler によって使用され、カスタムキーバインドでは役に立たない場合があります。</span><span class="sxs-lookup"><span data-stu-id="be720-799">This function is used by Get-PSReadLineKeyHandler and probably isn't useful in a custom key binding.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="be720-800">この関数は Get-PSReadLineOption によって使用され、カスタムキーバインドではあまり役に立たない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="be720-800">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="be720-801">コマンドラインに何も選択されていない場合は、開始と長さの両方で-1 が返されます。</span><span class="sxs-lookup"><span data-stu-id="be720-801">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="be720-802">コマンドラインに選択項目がある場合は、選択範囲の先頭と長さが返されます。</span><span class="sxs-lookup"><span data-stu-id="be720-802">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="be720-803">カーソル位置に文字または文字列を挿入します。</span><span class="sxs-lookup"><span data-stu-id="be720-803">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="be720-804">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="be720-804">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="be720-805">これは、PSReadLine へのメインエントリポイントです。</span><span class="sxs-lookup"><span data-stu-id="be720-805">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="be720-806">再帰はサポートされないため、カスタムキーバインドでは役に立ちません。</span><span class="sxs-lookup"><span data-stu-id="be720-806">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="be720-807">この関数は Remove-PSReadLineKeyHandler によって使用され、カスタムキーバインドではあまり役に立たない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="be720-807">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="be720-808">入力の一部を置換します。</span><span class="sxs-lookup"><span data-stu-id="be720-808">Replace some of the input.</span></span> <span data-ttu-id="be720-809">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="be720-809">This operation supports undo/redo.</span></span> <span data-ttu-id="be720-810">これは、undo の単一のアクションとして扱われるため、Delete の後に Insert を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="be720-810">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="be720-811">カーソルを指定されたオフセットに移動します。</span><span class="sxs-lookup"><span data-stu-id="be720-811">Move the cursor to the given offset.</span></span> <span data-ttu-id="be720-812">カーソルの移動は、元に戻すために追跡されません。</span><span class="sxs-lookup"><span data-stu-id="be720-812">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="be720-813">この関数は、コマンドレットの設定-PSReadLineOption によって使用されるヘルパーメソッドですが、一時的に設定を変更する必要があるカスタムキーバインドに便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="be720-813">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="be720-814">このヘルパーメソッドは、DigitArgument を優先するカスタムバインドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="be720-814">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="be720-815">一般的な呼び出しは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="be720-815">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="be720-816">注意</span><span class="sxs-lookup"><span data-stu-id="be720-816">Note</span></span>

### <a name="command-history"></a><span data-ttu-id="be720-817">コマンド履歴</span><span class="sxs-lookup"><span data-stu-id="be720-817">Command History</span></span>

<span data-ttu-id="be720-818">PSReadLine は、コマンドラインから入力したすべてのコマンドとデータを含む履歴ファイルを保持します。</span><span class="sxs-lookup"><span data-stu-id="be720-818">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="be720-819">これには、パスワードなどの機密データが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="be720-819">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="be720-820">たとえば、コマンドレットを使用した場合、 `ConvertTo-SecureString` パスワードはプレーンテキストとして履歴ファイルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="be720-820">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="be720-821">履歴ファイルは、という名前のファイルです `$($host.Name)_history.txt` 。</span><span class="sxs-lookup"><span data-stu-id="be720-821">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="be720-822">Windows システムでは、履歴ファイルはに格納され `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` ます。</span><span class="sxs-lookup"><span data-stu-id="be720-822">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="be720-823">Windows 以外のシステムでは、履歴ファイルはまたはに格納され `$env:XDG_DATA_HOME/powershell/PSReadLine` `$env:HOME/.local/share/powershell/PSReadLine` ます。</span><span class="sxs-lookup"><span data-stu-id="be720-823">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="be720-824">PSReadLine に貢献しているフィードバック &</span><span class="sxs-lookup"><span data-stu-id="be720-824">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="be720-825">GitHub の PSReadLine</span><span class="sxs-lookup"><span data-stu-id="be720-825">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="be720-826">プル要求を送信したり、GitHub ページでフィードバックを送信したりしてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="be720-826">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="be720-827">参照</span><span class="sxs-lookup"><span data-stu-id="be720-827">See Also</span></span>

<span data-ttu-id="be720-828">PSReadLine は、GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) ライブラリの影響を強く受けます。</span><span class="sxs-lookup"><span data-stu-id="be720-828">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
