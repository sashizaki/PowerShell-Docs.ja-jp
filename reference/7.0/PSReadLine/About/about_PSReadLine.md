---
description: PSReadLine では、PowerShell コンソールでのコマンドライン編集エクスペリエンスが向上しています。
keywords: powershell
Locale: en-US
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: PSReadLine について
ms.openlocfilehash: 890f8e92172f2d492b6b817b558d4f25c70e8949
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220547"
---
# <a name="psreadline"></a><span data-ttu-id="5149a-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="5149a-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="5149a-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="5149a-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="5149a-106">概要</span><span class="sxs-lookup"><span data-stu-id="5149a-106">SHORT DESCRIPTION</span></span>

<span data-ttu-id="5149a-107">PSReadLine では、PowerShell コンソールでのコマンドライン編集エクスペリエンスが向上しています。</span><span class="sxs-lookup"><span data-stu-id="5149a-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="5149a-108">詳細説明</span><span class="sxs-lookup"><span data-stu-id="5149a-108">LONG DESCRIPTION</span></span>

<span data-ttu-id="5149a-109">PSReadLine 2.0 では、PowerShell コンソールの強力なコマンドライン編集エクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="5149a-110">次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="5149a-110">It provides:</span></span>

- <span data-ttu-id="5149a-111">コマンドラインの構文の色分け</span><span class="sxs-lookup"><span data-stu-id="5149a-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="5149a-112">構文エラーを視覚的に示します。</span><span class="sxs-lookup"><span data-stu-id="5149a-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="5149a-113">より優れたマルチラインエクスペリエンス (編集と履歴の両方)</span><span class="sxs-lookup"><span data-stu-id="5149a-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="5149a-114">カスタマイズ可能なキーバインド</span><span class="sxs-lookup"><span data-stu-id="5149a-114">Customizable key bindings</span></span>
- <span data-ttu-id="5149a-115">Cmd モードと Emacs モード</span><span class="sxs-lookup"><span data-stu-id="5149a-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="5149a-116">多くの構成オプション</span><span class="sxs-lookup"><span data-stu-id="5149a-116">Many configuration options</span></span>
- <span data-ttu-id="5149a-117">Bash スタイル補完 (Cmd モードでは省略可能、Emacs モードでは既定)</span><span class="sxs-lookup"><span data-stu-id="5149a-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="5149a-118">Emacs yank/kill-リング</span><span class="sxs-lookup"><span data-stu-id="5149a-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="5149a-119">PowerShell トークンベースの "word" の移動と強制終了</span><span class="sxs-lookup"><span data-stu-id="5149a-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="5149a-120">クラス **[PSConsoleReadLine]** では、次の関数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5149a-120">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

> [!NOTE]
> <span data-ttu-id="5149a-121">PowerShell 7.0 以降では、スクリーンリーダープログラムが検出されると、PowerShell は Windows で PSReadLine の自動読み込みをスキップします。</span><span class="sxs-lookup"><span data-stu-id="5149a-121">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="5149a-122">現在、PSReadLine は、スクリーンリーダーではうまく機能しません。</span><span class="sxs-lookup"><span data-stu-id="5149a-122">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="5149a-123">Windows での PowerShell 7.0 の既定の表示と書式設定は正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="5149a-123">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="5149a-124">必要に応じて、モジュールを手動で読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="5149a-124">You can manually load the module if necessary.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="5149a-125">基本的な編集関数</span><span class="sxs-lookup"><span data-stu-id="5149a-125">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="5149a-126">中止</span><span class="sxs-lookup"><span data-stu-id="5149a-126">Abort</span></span>

<span data-ttu-id="5149a-127">現在のアクション (増分履歴検索など) を中止します。</span><span class="sxs-lookup"><span data-stu-id="5149a-127">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="5149a-128">.Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="5149a-128">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="5149a-129">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="5149a-129">AcceptAndGetNext</span></span>

<span data-ttu-id="5149a-130">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="5149a-130">Attempt to execute the current input.</span></span> <span data-ttu-id="5149a-131">(AcceptLine など) 実行できる場合は、次に ReadLine が呼び出されたときに履歴から次の項目を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5149a-131">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="5149a-132">.Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="5149a-132">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="5149a-133">AcceptLine</span><span class="sxs-lookup"><span data-stu-id="5149a-133">AcceptLine</span></span>

<span data-ttu-id="5149a-134">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="5149a-134">Attempt to execute the current input.</span></span> <span data-ttu-id="5149a-135">現在の入力が不完全な場合 (たとえば、終わりかっこ、角かっこ、または引用符がない場合)、継続のプロンプトは次の行に表示され、PSReadLine は現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="5149a-135">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="5149a-136">コマンド: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="5149a-136">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="5149a-137">.Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="5149a-137">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="5149a-138">Vi の挿入モード: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="5149a-138">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="5149a-139">AddLine</span><span class="sxs-lookup"><span data-stu-id="5149a-139">AddLine</span></span>

<span data-ttu-id="5149a-140">継続プロンプトが次の行に表示され、PSReadLine が現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="5149a-140">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="5149a-141">これは、単一行が単独で完全に入力されている場合でも、複数行の入力を1つのコマンドとして入力する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="5149a-141">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="5149a-142">コマンド: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="5149a-142">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="5149a-143">.Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="5149a-143">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="5149a-144">Vi の挿入モード: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="5149a-144">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="5149a-145">Vi コマンドモード: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="5149a-145">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="5149a-146">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="5149a-146">BackwardDeleteChar</span></span>

<span data-ttu-id="5149a-147">カーソルの前の文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="5149a-147">Delete the character before the cursor.</span></span>

- <span data-ttu-id="5149a-148">Cmd: `<Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="5149a-148">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="5149a-149">Emacs: `<Backspace>` 、 `<Ctrl+Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="5149a-149">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="5149a-150">Vi の挿入モード: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="5149a-150">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="5149a-151">Vi コマンドモード: `<X>` 、 `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="5149a-151">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="5149a-152">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="5149a-152">BackwardDeleteLine</span></span>

<span data-ttu-id="5149a-153">Like BackwardKillLine-行の先頭から先頭までのテキストを削除しますが、削除されたテキストはキルリングには挿入されません。</span><span class="sxs-lookup"><span data-stu-id="5149a-153">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="5149a-154">コマンド: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="5149a-154">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="5149a-155">Vi 挿入モード: `<Ctrl+u>` 、 `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="5149a-155">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="5149a-156">Vi コマンドモード: `<Ctrl+u>` 、 `<Ctrl+Home>` 、 `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="5149a-156">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="5149a-157">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="5149a-157">BackwardDeleteWord</span></span>

<span data-ttu-id="5149a-158">前の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="5149a-158">Deletes the previous word.</span></span>

- <span data-ttu-id="5149a-159">Vi コマンドモード: `<Ctrl+w>` 、 `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="5149a-159">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="5149a-160">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="5149a-160">BackwardKillLine</span></span>

<span data-ttu-id="5149a-161">入力の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="5149a-161">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="5149a-162">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-162">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="5149a-163">Emacs: `<Ctrl+u>` 、 `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="5149a-163">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="5149a-164">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="5149a-164">BackwardKillWord</span></span>

<span data-ttu-id="5149a-165">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="5149a-165">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="5149a-166">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="5149a-166">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="5149a-167">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-167">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="5149a-168">コマンド: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="5149a-168">Cmd: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="5149a-169">Emacs: `<Alt+Backspace>` 、 `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="5149a-169">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="5149a-170">Vi の挿入モード: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="5149a-170">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="5149a-171">Vi コマンドモード: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="5149a-171">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="5149a-172">CancelLine</span><span class="sxs-lookup"><span data-stu-id="5149a-172">CancelLine</span></span>

<span data-ttu-id="5149a-173">入力を画面に残したまま、現在の入力を取り消しますが、プロンプトが再び評価されるように、ホストに戻ります。</span><span class="sxs-lookup"><span data-stu-id="5149a-173">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="5149a-174">Vi の挿入モード: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="5149a-174">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="5149a-175">Vi コマンドモード: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="5149a-175">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="5149a-176">コピー</span><span class="sxs-lookup"><span data-stu-id="5149a-176">Copy</span></span>

<span data-ttu-id="5149a-177">選択したリージョンをシステムクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="5149a-177">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="5149a-178">領域が選択されていない場合は、行全体をコピーします。</span><span class="sxs-lookup"><span data-stu-id="5149a-178">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="5149a-179">コマンド: `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="5149a-179">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="5149a-180">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="5149a-180">CopyOrCancelLine</span></span>

<span data-ttu-id="5149a-181">テキストが選択されている場合は、クリップボードにコピーします。それ以外の場合は、行をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="5149a-181">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="5149a-182">コマンド: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="5149a-182">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="5149a-183">.Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="5149a-183">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="5149a-184">切り取り</span><span class="sxs-lookup"><span data-stu-id="5149a-184">Cut</span></span>

<span data-ttu-id="5149a-185">削除されたテキストをシステムクリップボードに配置した、選択した領域を削除します。</span><span class="sxs-lookup"><span data-stu-id="5149a-185">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="5149a-186">コマンド: `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="5149a-186">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="5149a-187">Dele</span><span class="sxs-lookup"><span data-stu-id="5149a-187">DeleteChar</span></span>

<span data-ttu-id="5149a-188">カーソルの下の文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="5149a-188">Delete the character under the cursor.</span></span>

- <span data-ttu-id="5149a-189">コマンド: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="5149a-189">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="5149a-190">.Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="5149a-190">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="5149a-191">Vi の挿入モード: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="5149a-191">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="5149a-192">Vi コマンドモード: `<Delete>` 、 `<x>` 、 `<d,l>` 、 `<d,Space>`</span><span class="sxs-lookup"><span data-stu-id="5149a-192">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Space>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="5149a-193">Deleの Arorexit</span><span class="sxs-lookup"><span data-stu-id="5149a-193">DeleteCharOrExit</span></span>

<span data-ttu-id="5149a-194">カーソルの下の文字を削除するか、行が空の場合はプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="5149a-194">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="5149a-195">.Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="5149a-195">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="5149a-196">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="5149a-196">DeleteEndOfWord</span></span>

<span data-ttu-id="5149a-197">単語の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="5149a-197">Delete to the end of the word.</span></span>

- <span data-ttu-id="5149a-198">Vi コマンドモード: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="5149a-198">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="5149a-199">Deleteline.invoke に</span><span class="sxs-lookup"><span data-stu-id="5149a-199">DeleteLine</span></span>

<span data-ttu-id="5149a-200">現在の行を削除して、元に戻す操作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5149a-200">Deletes the current line, enabling undo.</span></span>

- <span data-ttu-id="5149a-201">Vi コマンドモード: `<d,d>`</span><span class="sxs-lookup"><span data-stu-id="5149a-201">Vi command mode: `<d,d>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="5149a-202">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="5149a-202">DeleteLineToFirstChar</span></span>

<span data-ttu-id="5149a-203">カーソルから、行の最初の空白以外の文字までのテキストを削除します。</span><span class="sxs-lookup"><span data-stu-id="5149a-203">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="5149a-204">Vi コマンドモード: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="5149a-204">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="5149a-205">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="5149a-205">DeleteToEnd</span></span>

<span data-ttu-id="5149a-206">行の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="5149a-206">Delete to the end of the line.</span></span>

- <span data-ttu-id="5149a-207">Vi コマンドモード: `<D>` 、 `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="5149a-207">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="5149a-208">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="5149a-208">DeleteWord</span></span>

<span data-ttu-id="5149a-209">次の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="5149a-209">Delete the next word.</span></span>

- <span data-ttu-id="5149a-210">Vi コマンドモード: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="5149a-210">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="5149a-211">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="5149a-211">ForwardDeleteLine</span></span>

<span data-ttu-id="5149a-212">同じように、Forwardは、行の末尾から最後までのテキストを削除しますが、削除されたテキストはキルリングには挿入されません。</span><span class="sxs-lookup"><span data-stu-id="5149a-212">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="5149a-213">コマンド: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="5149a-213">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="5149a-214">Vi の挿入モード: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="5149a-214">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="5149a-215">Vi コマンドモード: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="5149a-215">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="5149a-216">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="5149a-216">InsertLineAbove</span></span>

<span data-ttu-id="5149a-217">現在の行の上にカーソルがある場所に関係なく、現在の行の上に新しい空の行が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-217">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="5149a-218">カーソルが新しい行の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-218">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="5149a-219">コマンド: `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="5149a-219">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="5149a-220">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="5149a-220">InsertLineBelow</span></span>

<span data-ttu-id="5149a-221">カーソルが現在の行にある場所に関係なく、現在の行の下に新しい空の行が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-221">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="5149a-222">カーソルが新しい行の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-222">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="5149a-223">コマンド: `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="5149a-223">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="5149a-224">InvertCase</span><span class="sxs-lookup"><span data-stu-id="5149a-224">InvertCase</span></span>

<span data-ttu-id="5149a-225">現在の文字の大文字と小文字の区別を反転し、次の文字に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-225">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="5149a-226">Vi コマンドモード: `<~>`</span><span class="sxs-lookup"><span data-stu-id="5149a-226">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="5149a-227">行の行</span><span class="sxs-lookup"><span data-stu-id="5149a-227">KillLine</span></span>

<span data-ttu-id="5149a-228">カーソルから入力の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="5149a-228">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="5149a-229">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-229">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="5149a-230">.Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="5149a-230">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="5149a-231">"/" 領域</span><span class="sxs-lookup"><span data-stu-id="5149a-231">KillRegion</span></span>

<span data-ttu-id="5149a-232">カーソルとマークの間のテキストを強制終了します。</span><span class="sxs-lookup"><span data-stu-id="5149a-232">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="5149a-233">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="5149a-233">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="5149a-234">文字の候補</span><span class="sxs-lookup"><span data-stu-id="5149a-234">KillWord</span></span>

<span data-ttu-id="5149a-235">カーソルから現在の単語の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="5149a-235">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="5149a-236">カーソルが単語の間にある場合は、カーソルから次の単語の末尾まで、入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="5149a-236">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="5149a-237">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-237">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="5149a-238">コマンド: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="5149a-238">Cmd: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="5149a-239">Emacs: `<Alt+d>` 、 `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="5149a-239">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="5149a-240">Vi の挿入モード: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="5149a-240">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="5149a-241">Vi コマンドモード: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="5149a-241">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="5149a-242">貼り付け</span><span class="sxs-lookup"><span data-stu-id="5149a-242">Paste</span></span>

<span data-ttu-id="5149a-243">システムクリップボードからテキストを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5149a-243">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="5149a-244">Cmd: `<Ctrl+v>` 、 `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="5149a-244">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="5149a-245">Vi の挿入モード: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="5149a-245">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="5149a-246">Vi コマンドモード: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="5149a-246">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5149a-247">**貼り付け** 関数を使用すると、クリップボードバッファーの内容全体が psreadline の入力バッファーに貼り付けられます。</span><span class="sxs-lookup"><span data-stu-id="5149a-247">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="5149a-248">入力バッファーが PowerShell パーサーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-248">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="5149a-249">コンソールアプリケーションの **右クリック** による貼り付けメソッドを使用して貼り付けた入力は、一度に1文字ずつ入力バッファーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="5149a-249">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="5149a-250">入力バッファーは、改行文字がコピーされるときにパーサーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-250">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="5149a-251">そのため、入力は一度に1行ずつ解析されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-251">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="5149a-252">貼り付けメソッドの違いによって、実行の動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="5149a-252">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="5149a-253">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="5149a-253">PasteAfter</span></span>

<span data-ttu-id="5149a-254">カーソルの後にクリップボードを貼り付けて、貼り付けられたテキストの末尾にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-254">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="5149a-255">Vi コマンドモード: `<p>`</span><span class="sxs-lookup"><span data-stu-id="5149a-255">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="5149a-256">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="5149a-256">PasteBefore</span></span>

<span data-ttu-id="5149a-257">カーソルの前にクリップボードを貼り付けて、貼り付けられたテキストの末尾にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-257">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="5149a-258">Vi コマンドモード: `<P>`</span><span class="sxs-lookup"><span data-stu-id="5149a-258">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="5149a-259">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="5149a-259">PrependAndAccept</span></span>

<span data-ttu-id="5149a-260">' # ' を先頭に付加し、その行を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="5149a-260">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="5149a-261">Vi コマンドモード: `<#>`</span><span class="sxs-lookup"><span data-stu-id="5149a-261">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="5149a-262">やり直し</span><span class="sxs-lookup"><span data-stu-id="5149a-262">Redo</span></span>

<span data-ttu-id="5149a-263">元に戻す操作を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="5149a-263">Undo an undo.</span></span>

- <span data-ttu-id="5149a-264">コマンド: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="5149a-264">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="5149a-265">Vi の挿入モード: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="5149a-265">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="5149a-266">Vi コマンドモード: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="5149a-266">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="5149a-267">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="5149a-267">RepeatLastCommand</span></span>

<span data-ttu-id="5149a-268">最後のテキストの変更を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5149a-268">Repeat the last text modification.</span></span>

- <span data-ttu-id="5149a-269">Vi コマンドモード: `<.>`</span><span class="sxs-lookup"><span data-stu-id="5149a-269">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="5149a-270">再有効化</span><span class="sxs-lookup"><span data-stu-id="5149a-270">RevertLine</span></span>

<span data-ttu-id="5149a-271">すべての入力を現在の入力に戻します。</span><span class="sxs-lookup"><span data-stu-id="5149a-271">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="5149a-272">コマンド: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="5149a-272">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="5149a-273">Emacs: `<Alt+r>` 、 `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="5149a-273">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="5149a-274">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="5149a-274">ShellBackwardKillWord</span></span>

<span data-ttu-id="5149a-275">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="5149a-275">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="5149a-276">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="5149a-276">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="5149a-277">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-277">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="5149a-278">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="5149a-278">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="5149a-279">Shellは Word</span><span class="sxs-lookup"><span data-stu-id="5149a-279">ShellKillWord</span></span>

<span data-ttu-id="5149a-280">カーソルから現在の単語の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="5149a-280">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="5149a-281">カーソルが単語の間にある場合は、カーソルから次の単語の末尾まで、入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="5149a-281">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="5149a-282">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-282">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="5149a-283">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="5149a-283">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="5149a-284">スワップ文字</span><span class="sxs-lookup"><span data-stu-id="5149a-284">SwapCharacters</span></span>

<span data-ttu-id="5149a-285">現在の文字とそれより前の文字を交換します。</span><span class="sxs-lookup"><span data-stu-id="5149a-285">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="5149a-286">.Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="5149a-286">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="5149a-287">Vi の挿入モード: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="5149a-287">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="5149a-288">Vi コマンドモード: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="5149a-288">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="5149a-289">元に戻す</span><span class="sxs-lookup"><span data-stu-id="5149a-289">Undo</span></span>

<span data-ttu-id="5149a-290">前の編集を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="5149a-290">Undo a previous edit.</span></span>

- <span data-ttu-id="5149a-291">コマンド: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="5149a-291">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="5149a-292">Emacs: `<Ctrl+_>` 、 `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="5149a-292">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="5149a-293">Vi の挿入モード: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="5149a-293">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="5149a-294">Vi コマンドモード: `<Ctrl+z>` 、 `<u>`</span><span class="sxs-lookup"><span data-stu-id="5149a-294">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="5149a-295">UndoAll</span><span class="sxs-lookup"><span data-stu-id="5149a-295">UndoAll</span></span>

<span data-ttu-id="5149a-296">行の以前の編集をすべて元に戻します。</span><span class="sxs-lookup"><span data-stu-id="5149a-296">Undo all previous edits for line.</span></span>

- <span data-ttu-id="5149a-297">Vi コマンドモード: `<U>`</span><span class="sxs-lookup"><span data-stu-id="5149a-297">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="5149a-298">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="5149a-298">UnixWordRubout</span></span>

<span data-ttu-id="5149a-299">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="5149a-299">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="5149a-300">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="5149a-300">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="5149a-301">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-301">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="5149a-302">.Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="5149a-302">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="5149a-303">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="5149a-303">ValidateAndAcceptLine</span></span>

<span data-ttu-id="5149a-304">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="5149a-304">Attempt to execute the current input.</span></span> <span data-ttu-id="5149a-305">現在の入力が不完全な場合 (たとえば、終わりかっこ、角かっこ、または引用符がない場合)、継続のプロンプトは次の行に表示され、PSReadLine は現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="5149a-305">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="5149a-306">.Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="5149a-306">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="5149a-307">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="5149a-307">ViAcceptLine</span></span>

<span data-ttu-id="5149a-308">行を受け入れ、挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="5149a-308">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="5149a-309">Vi コマンドモード: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="5149a-309">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="5149a-310">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="5149a-310">ViAcceptLineOrExit</span></span>

<span data-ttu-id="5149a-311">(Emacs モードでは Deleと同じですが、文字を削除するのではなく、行を受け取ります)。</span><span class="sxs-lookup"><span data-stu-id="5149a-311">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="5149a-312">Vi の挿入モード: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="5149a-312">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="5149a-313">Vi コマンドモード: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="5149a-313">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="5149a-314">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="5149a-314">ViAppendLine</span></span>

<span data-ttu-id="5149a-315">現在の行の下に新しい行が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-315">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="5149a-316">Vi コマンドモード: `<o>`</span><span class="sxs-lookup"><span data-stu-id="5149a-316">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="5149a-317">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="5149a-317">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="5149a-318">単語区切り記号として空白文字のみを使用して、前の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="5149a-318">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="5149a-319">Vi コマンドモード: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="5149a-319">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="5149a-320">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="5149a-320">ViBackwardGlob</span></span>

<span data-ttu-id="5149a-321">区切り記号として空白文字のみを使用して、カーソルを前の単語の先頭に戻します。</span><span class="sxs-lookup"><span data-stu-id="5149a-321">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="5149a-322">Vi コマンドモード: `<B>`</span><span class="sxs-lookup"><span data-stu-id="5149a-322">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="5149a-323">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="5149a-323">ViDeleteBrace</span></span>

<span data-ttu-id="5149a-324">対応する中かっこ、かっこ、または角かっこを検索し、中かっこを含め、内のすべての内容を削除します。</span><span class="sxs-lookup"><span data-stu-id="5149a-324">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="5149a-325">Vi コマンドモード: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="5149a-325">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="5149a-326">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="5149a-326">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="5149a-327">単語の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="5149a-327">Delete to the end of the word.</span></span>

- <span data-ttu-id="5149a-328">Vi コマンドモード: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="5149a-328">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="5149a-329">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="5149a-329">ViDeleteGlob</span></span>

<span data-ttu-id="5149a-330">次の glob (空白で区切られた単語) を削除します。</span><span class="sxs-lookup"><span data-stu-id="5149a-330">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="5149a-331">Vi コマンドモード: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="5149a-331">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="5149a-332">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="5149a-332">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="5149a-333">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="5149a-333">Deletes until given character.</span></span>

- <span data-ttu-id="5149a-334">Vi コマンドモード: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="5149a-334">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="5149a-335">Videletetobeforo</span><span class="sxs-lookup"><span data-stu-id="5149a-335">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="5149a-336">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="5149a-336">Deletes until given character.</span></span>

- <span data-ttu-id="5149a-337">Vi コマンドモード: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="5149a-337">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="5149a-338">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="5149a-338">ViDeleteToChar</span></span>

<span data-ttu-id="5149a-339">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="5149a-339">Deletes until given character.</span></span>

- <span data-ttu-id="5149a-340">Vi コマンドモード: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="5149a-340">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="5149a-341">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="5149a-341">ViDeleteToCharBackward</span></span>

<span data-ttu-id="5149a-342">指定された文字まで後方を削除します。</span><span class="sxs-lookup"><span data-stu-id="5149a-342">Deletes backwards until given character.</span></span>

- <span data-ttu-id="5149a-343">Vi コマンドモード: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="5149a-343">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="5149a-344">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="5149a-344">ViInsertAtBegining</span></span>

<span data-ttu-id="5149a-345">挿入モードに切り替え、カーソルを行の先頭に配置します。</span><span class="sxs-lookup"><span data-stu-id="5149a-345">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="5149a-346">Vi コマンドモード: `<I>`</span><span class="sxs-lookup"><span data-stu-id="5149a-346">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="5149a-347">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="5149a-347">ViInsertAtEnd</span></span>

<span data-ttu-id="5149a-348">挿入モードに切り替え、カーソルを行の末尾に配置します。</span><span class="sxs-lookup"><span data-stu-id="5149a-348">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="5149a-349">Vi コマンドモード: `<A>`</span><span class="sxs-lookup"><span data-stu-id="5149a-349">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="5149a-350">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="5149a-350">ViInsertLine</span></span>

<span data-ttu-id="5149a-351">現在の行の上に新しい行が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-351">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="5149a-352">Vi コマンドモード: `<O>`</span><span class="sxs-lookup"><span data-stu-id="5149a-352">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="5149a-353">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="5149a-353">ViInsertWithAppend</span></span>

<span data-ttu-id="5149a-354">現在の行の位置から追加します。</span><span class="sxs-lookup"><span data-stu-id="5149a-354">Append from the current line position.</span></span>

- <span data-ttu-id="5149a-355">Vi コマンドモード: `<a>`</span><span class="sxs-lookup"><span data-stu-id="5149a-355">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="5149a-356">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="5149a-356">ViInsertWithDelete</span></span>

<span data-ttu-id="5149a-357">現在の文字を削除し、挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="5149a-357">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="5149a-358">Vi コマンドモード: `<s>`</span><span class="sxs-lookup"><span data-stu-id="5149a-358">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="5149a-359">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="5149a-359">ViJoinLines</span></span>

<span data-ttu-id="5149a-360">現在の行と次の行を結合します。</span><span class="sxs-lookup"><span data-stu-id="5149a-360">Joins the current line and the next line.</span></span>

- <span data-ttu-id="5149a-361">Vi コマンドモード: `<J>`</span><span class="sxs-lookup"><span data-stu-id="5149a-361">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="5149a-362">交換ライン</span><span class="sxs-lookup"><span data-stu-id="5149a-362">ViReplaceLine</span></span>

<span data-ttu-id="5149a-363">コマンドライン全体を消去します。</span><span class="sxs-lookup"><span data-stu-id="5149a-363">Erase the entire command line.</span></span>

- <span data-ttu-id="5149a-364">Vi コマンドモード: `<S>` 、 `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="5149a-364">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="5149a-365">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="5149a-365">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="5149a-366">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="5149a-366">Replaces until given character.</span></span>

- <span data-ttu-id="5149a-367">Vi コマンドモード: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="5149a-367">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="5149a-368">Vireplacetobeforo</span><span class="sxs-lookup"><span data-stu-id="5149a-368">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="5149a-369">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="5149a-369">Replaces until given character.</span></span>

- <span data-ttu-id="5149a-370">Vi コマンドモード: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="5149a-370">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="5149a-371">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="5149a-371">ViReplaceToChar</span></span>

<span data-ttu-id="5149a-372">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="5149a-372">Deletes until given character.</span></span>

- <span data-ttu-id="5149a-373">Vi コマンドモード: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="5149a-373">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="5149a-374">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="5149a-374">ViReplaceToCharBackward</span></span>

<span data-ttu-id="5149a-375">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="5149a-375">Replaces until given character.</span></span>

- <span data-ttu-id="5149a-376">Vi コマンドモード: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="5149a-376">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="5149a-377">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="5149a-377">ViYankBeginningOfLine</span></span>

<span data-ttu-id="5149a-378">バッファーの先頭からカーソルまで Yank。</span><span class="sxs-lookup"><span data-stu-id="5149a-378">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="5149a-379">Vi コマンドモード: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="5149a-379">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="5149a-380">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="5149a-380">ViYankEndOfGlob</span></span>

<span data-ttu-id="5149a-381">カーソルから単語の末尾まで Yank します。</span><span class="sxs-lookup"><span data-stu-id="5149a-381">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="5149a-382">Vi コマンドモード: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="5149a-382">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="5149a-383">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="5149a-383">ViYankEndOfWord</span></span>

<span data-ttu-id="5149a-384">カーソルから単語の末尾まで Yank します。</span><span class="sxs-lookup"><span data-stu-id="5149a-384">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="5149a-385">Vi コマンドモード: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="5149a-385">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="5149a-386">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="5149a-386">ViYankLeft</span></span>

<span data-ttu-id="5149a-387">カーソルの左側の文字を Yank します。</span><span class="sxs-lookup"><span data-stu-id="5149a-387">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="5149a-388">Vi コマンドモード: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="5149a-388">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="5149a-389">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="5149a-389">ViYankLine</span></span>

<span data-ttu-id="5149a-390">バッファー全体を Yank します。</span><span class="sxs-lookup"><span data-stu-id="5149a-390">Yank the entire buffer.</span></span>

- <span data-ttu-id="5149a-391">Vi コマンドモード: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="5149a-391">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="5149a-392">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="5149a-392">ViYankNextGlob</span></span>

<span data-ttu-id="5149a-393">Yank は、次の単語の先頭にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="5149a-393">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="5149a-394">Vi コマンドモード: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="5149a-394">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="5149a-395">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="5149a-395">ViYankNextWord</span></span>

<span data-ttu-id="5149a-396">カーソルの後の単語を Yank します。</span><span class="sxs-lookup"><span data-stu-id="5149a-396">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="5149a-397">Vi コマンドモード: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="5149a-397">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="5149a-398">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="5149a-398">ViYankPercent</span></span>

<span data-ttu-id="5149a-399">一致する中かっこを Yank します。</span><span class="sxs-lookup"><span data-stu-id="5149a-399">Yank to/from matching brace.</span></span>

- <span data-ttu-id="5149a-400">Vi コマンドモード: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="5149a-400">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="5149a-401">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="5149a-401">ViYankPreviousGlob</span></span>

<span data-ttu-id="5149a-402">Yank は、単語の先頭からカーソルになります。</span><span class="sxs-lookup"><span data-stu-id="5149a-402">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="5149a-403">Vi コマンドモード: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="5149a-403">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="5149a-404">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="5149a-404">ViYankPreviousWord</span></span>

<span data-ttu-id="5149a-405">カーソルの前に単語を Yank します。</span><span class="sxs-lookup"><span data-stu-id="5149a-405">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="5149a-406">Vi コマンドモード: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="5149a-406">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="5149a-407">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="5149a-407">ViYankRight</span></span>

<span data-ttu-id="5149a-408">カーソルの右側に Yank 文字があります。</span><span class="sxs-lookup"><span data-stu-id="5149a-408">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="5149a-409">Vi コマンドモード: `<y,l>` 、 `<y,Space>`</span><span class="sxs-lookup"><span data-stu-id="5149a-409">Vi command mode: `<y,l>`, `<y,Space>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="5149a-410">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="5149a-410">ViYankToEndOfLine</span></span>

<span data-ttu-id="5149a-411">カーソルからバッファーの末尾までの Yank。</span><span class="sxs-lookup"><span data-stu-id="5149a-411">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="5149a-412">Vi コマンドモード: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="5149a-412">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="5149a-413">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="5149a-413">ViYankToFirstChar</span></span>

<span data-ttu-id="5149a-414">最初の空白以外の文字からカーソルまで Yank ます。</span><span class="sxs-lookup"><span data-stu-id="5149a-414">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="5149a-415">Vi コマンドモード: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="5149a-415">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="5149a-416">Yank</span><span class="sxs-lookup"><span data-stu-id="5149a-416">Yank</span></span>

<span data-ttu-id="5149a-417">最後に終了したテキストを入力に追加します。</span><span class="sxs-lookup"><span data-stu-id="5149a-417">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="5149a-418">.Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="5149a-418">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="5149a-419">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="5149a-419">YankLastArg</span></span>

<span data-ttu-id="5149a-420">前の履歴行の最後の引数を Yank します。</span><span class="sxs-lookup"><span data-stu-id="5149a-420">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="5149a-421">引数を使用すると、最初に呼び出されたときに、YankNthArg と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="5149a-421">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="5149a-422">複数回呼び出された場合は、代わりに履歴を反復処理し、引数に方向を設定します (負の方向が反転します)。</span><span class="sxs-lookup"><span data-stu-id="5149a-422">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="5149a-423">コマンド: `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="5149a-423">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="5149a-424">Emacs: `<Alt+.>` 、 `<Alt+_>` 、 `<Escape,.>` 、 `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="5149a-424">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="5149a-425">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="5149a-425">YankNthArg</span></span>

<span data-ttu-id="5149a-426">Yank は、前の履歴行から (コマンドの後に) 最初の引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="5149a-426">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="5149a-427">引数を使用して、n 番目の引数 (0 から始まる) を yank します。引数が負の場合は、最後の引数から開始します。</span><span class="sxs-lookup"><span data-stu-id="5149a-427">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="5149a-428">Emacs: `<Ctrl+Alt+y>` 、 `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="5149a-428">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="5149a-429">YankPop</span><span class="sxs-lookup"><span data-stu-id="5149a-429">YankPop</span></span>

<span data-ttu-id="5149a-430">前の操作が Yank または YankPop であった場合は、以前の引き抜かテキストをキルリングから次に強制終了されたテキストに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="5149a-430">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="5149a-431">Emacs: `<Alt+y>` 、 `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="5149a-431">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="5149a-432">カーソルの移動関数</span><span class="sxs-lookup"><span data-stu-id="5149a-432">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="5149a-433">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="5149a-433">BackwardChar</span></span>

<span data-ttu-id="5149a-434">カーソルを1文字左に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-434">Move the cursor one character to the left.</span></span> <span data-ttu-id="5149a-435">これにより、カーソルが複数行の入力の前の行に移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="5149a-435">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="5149a-436">コマンド: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-436">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="5149a-437">Emacs: `<LeftArrow>` 、 `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="5149a-437">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>
- <span data-ttu-id="5149a-438">Vi の挿入モード: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-438">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="5149a-439">Vi コマンドモード: `<LeftArrow>` 、 `<Backspace>` 、 `<h>`</span><span class="sxs-lookup"><span data-stu-id="5149a-439">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="5149a-440">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="5149a-440">BackwardWord</span></span>

<span data-ttu-id="5149a-441">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-441">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="5149a-442">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-442">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="5149a-443">コマンド: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-443">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="5149a-444">Emacs: `<Alt+b>` 、 `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="5149a-444">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="5149a-445">Vi の挿入モード: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-445">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="5149a-446">Vi コマンドモード: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-446">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="5149a-447">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="5149a-447">BeginningOfLine</span></span>

<span data-ttu-id="5149a-448">入力に複数の行がある場合は、現在の行の先頭に移動します。または、既に行の先頭にある場合は、入力の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-448">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="5149a-449">入力に1行しか含まれていない場合は、入力の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-449">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="5149a-450">コマンド: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="5149a-450">Cmd: `<Home>`</span></span>
- <span data-ttu-id="5149a-451">Emacs: `<Home>` 、 `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="5149a-451">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="5149a-452">Vi の挿入モード: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="5149a-452">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="5149a-453">Vi コマンドモード: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="5149a-453">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="5149a-454">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="5149a-454">EndOfLine</span></span>

<span data-ttu-id="5149a-455">入力に複数の行がある場合は、現在の行の末尾に移動します。または、既に行の末尾にある場合は、入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-455">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="5149a-456">入力に1行しか含まれていない場合は、入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-456">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="5149a-457">コマンド: `<End>`</span><span class="sxs-lookup"><span data-stu-id="5149a-457">Cmd: `<End>`</span></span>
- <span data-ttu-id="5149a-458">Emacs: `<End>` 、 `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="5149a-458">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="5149a-459">Vi の挿入モード: `<End>`</span><span class="sxs-lookup"><span data-stu-id="5149a-459">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="5149a-460">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="5149a-460">ForwardChar</span></span>

<span data-ttu-id="5149a-461">カーソルを1文字右に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-461">Move the cursor one character to the right.</span></span> <span data-ttu-id="5149a-462">これにより、カーソルが複数行入力の次の行に移動する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5149a-462">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="5149a-463">コマンド: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-463">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="5149a-464">Emacs: `<RightArrow>` 、 `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="5149a-464">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>
- <span data-ttu-id="5149a-465">Vi の挿入モード: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-465">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="5149a-466">Vi コマンドモード: `<RightArrow>` 、 `<Space>` 、 `<l>`</span><span class="sxs-lookup"><span data-stu-id="5149a-466">Vi command mode: `<RightArrow>`, `<Space>`, `<l>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="5149a-467">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="5149a-467">ForwardWord</span></span>

<span data-ttu-id="5149a-468">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-468">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="5149a-469">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-469">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="5149a-470">Emacs: `<Alt+f>` 、 `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="5149a-470">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="5149a-471">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="5149a-471">GotoBrace</span></span>

<span data-ttu-id="5149a-472">対応する中かっこ、かっこ、または角かっこにジャンプします。</span><span class="sxs-lookup"><span data-stu-id="5149a-472">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="5149a-473">コマンド: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="5149a-473">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="5149a-474">Vi の挿入モード: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="5149a-474">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="5149a-475">Vi コマンドモード: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="5149a-475">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="5149a-476">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="5149a-476">GotoColumn</span></span>

<span data-ttu-id="5149a-477">Arg で示される列に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-477">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="5149a-478">Vi コマンドモード: `<|>`</span><span class="sxs-lookup"><span data-stu-id="5149a-478">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="5149a-479">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="5149a-479">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="5149a-480">カーソルを行の空白以外の最初の文字に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-480">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="5149a-481">Vi コマンドモード: `<^>`</span><span class="sxs-lookup"><span data-stu-id="5149a-481">Vi command mode: `<^>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="5149a-482">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="5149a-482">MoveToEndOfLine</span></span>

<span data-ttu-id="5149a-483">カーソルを入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-483">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="5149a-484">Vi コマンドモード: `<End>` 、 `<$>`</span><span class="sxs-lookup"><span data-stu-id="5149a-484">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="5149a-485">NextLine</span><span class="sxs-lookup"><span data-stu-id="5149a-485">NextLine</span></span>

<span data-ttu-id="5149a-486">カーソルを次の行に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-486">Move the cursor to the next line.</span></span>

- <span data-ttu-id="5149a-487">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="5149a-487">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="5149a-488">NextWord</span><span class="sxs-lookup"><span data-stu-id="5149a-488">NextWord</span></span>

<span data-ttu-id="5149a-489">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-489">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="5149a-490">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-490">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="5149a-491">コマンド: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-491">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="5149a-492">Vi の挿入モード: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-492">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="5149a-493">Vi コマンドモード: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-493">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="5149a-494">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="5149a-494">NextWordEnd</span></span>

<span data-ttu-id="5149a-495">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-495">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="5149a-496">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-496">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="5149a-497">Vi コマンドモード: `<e>`</span><span class="sxs-lookup"><span data-stu-id="5149a-497">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="5149a-498">前の行</span><span class="sxs-lookup"><span data-stu-id="5149a-498">PreviousLine</span></span>

<span data-ttu-id="5149a-499">カーソルを前の行に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-499">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="5149a-500">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="5149a-500">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="5149a-501">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="5149a-501">ShellBackwardWord</span></span>

<span data-ttu-id="5149a-502">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-502">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="5149a-503">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-503">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="5149a-504">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="5149a-504">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="5149a-505">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="5149a-505">ShellForwardWord</span></span>

<span data-ttu-id="5149a-506">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-506">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="5149a-507">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-507">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="5149a-508">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="5149a-508">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="5149a-509">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="5149a-509">ShellNextWord</span></span>

<span data-ttu-id="5149a-510">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-510">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="5149a-511">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-511">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="5149a-512">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="5149a-512">Function is unbound.</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="5149a-513">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="5149a-513">ViBackwardWord</span></span>

<span data-ttu-id="5149a-514">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-514">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="5149a-515">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-515">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="5149a-516">Vi コマンドモード: `<b>`</span><span class="sxs-lookup"><span data-stu-id="5149a-516">Vi command mode: `<b>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="5149a-517">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="5149a-517">ViEndOfGlob</span></span>

<span data-ttu-id="5149a-518">区切り記号として空白文字のみを使用して、カーソルを単語の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-518">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="5149a-519">Vi コマンドモード: `<E>`</span><span class="sxs-lookup"><span data-stu-id="5149a-519">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="5149a-520">Viendofの Glob</span><span class="sxs-lookup"><span data-stu-id="5149a-520">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="5149a-521">単語区切り記号として空白文字のみを使用して、前の単語の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-521">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="5149a-522">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="5149a-522">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="5149a-523">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="5149a-523">ViGotoBrace</span></span>

<span data-ttu-id="5149a-524">GotoBrace に似ていますが、トークンベースではなく文字ベースです。</span><span class="sxs-lookup"><span data-stu-id="5149a-524">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="5149a-525">Vi コマンドモード: `<%>`</span><span class="sxs-lookup"><span data-stu-id="5149a-525">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="5149a-526">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="5149a-526">ViNextGlob</span></span>

<span data-ttu-id="5149a-527">単語区切り記号として空白文字のみを使用して、次の単語に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-527">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="5149a-528">Vi コマンドモード: `<W>`</span><span class="sxs-lookup"><span data-stu-id="5149a-528">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="5149a-529">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="5149a-529">ViNextWord</span></span>

<span data-ttu-id="5149a-530">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-530">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="5149a-531">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-531">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="5149a-532">Vi コマンドモード: `<w>`</span><span class="sxs-lookup"><span data-stu-id="5149a-532">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="5149a-533">履歴関数</span><span class="sxs-lookup"><span data-stu-id="5149a-533">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="5149a-534">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="5149a-534">BeginningOfHistory</span></span>

<span data-ttu-id="5149a-535">履歴内の最初の項目に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-535">Move to the first item in the history.</span></span>

- <span data-ttu-id="5149a-536">.Emacs `<Alt+`<>\`</span><span class="sxs-lookup"><span data-stu-id="5149a-536">Emacs: `<Alt+`<>\`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="5149a-537">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="5149a-537">ClearHistory</span></span>

<span data-ttu-id="5149a-538">PSReadLine の履歴をクリアします。</span><span class="sxs-lookup"><span data-stu-id="5149a-538">Clears history in PSReadLine.</span></span> <span data-ttu-id="5149a-539">これは、PowerShell の履歴には影響しません。</span><span class="sxs-lookup"><span data-stu-id="5149a-539">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="5149a-540">コマンド: `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="5149a-540">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="5149a-541">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="5149a-541">EndOfHistory</span></span>

<span data-ttu-id="5149a-542">履歴内の最後の項目 (現在の入力) に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-542">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="5149a-543">.Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="5149a-543">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="5149a-544">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="5149a-544">ForwardSearchHistory</span></span>

<span data-ttu-id="5149a-545">履歴を使用した増分転送検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="5149a-545">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="5149a-546">コマンド: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="5149a-546">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="5149a-547">.Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="5149a-547">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="5149a-548">履歴の Search後方</span><span class="sxs-lookup"><span data-stu-id="5149a-548">HistorySearchBackward</span></span>

<span data-ttu-id="5149a-549">現在の入力を、PSReadLine 履歴の ' previous ' 項目で置き換えます。この項目は、開始と入力の間の文字とカーソルの間の文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="5149a-549">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="5149a-550">コマンド: `<F8>`</span><span class="sxs-lookup"><span data-stu-id="5149a-550">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="5149a-551">履歴の Searchforward</span><span class="sxs-lookup"><span data-stu-id="5149a-551">HistorySearchForward</span></span>

<span data-ttu-id="5149a-552">現在の入力を、PSReadLine 履歴の ' next ' 項目で置き換えます。この項目は、開始と入力の間の文字とカーソルの間の文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="5149a-552">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="5149a-553">コマンド: `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="5149a-553">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="5149a-554">NextHistory</span><span class="sxs-lookup"><span data-stu-id="5149a-554">NextHistory</span></span>

<span data-ttu-id="5149a-555">現在の入力を、PSReadLine 履歴の ' next ' 項目に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="5149a-555">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="5149a-556">コマンド: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-556">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="5149a-557">Emacs: `<DownArrow>` 、 `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="5149a-557">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="5149a-558">Vi の挿入モード: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-558">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="5149a-559">Vi コマンドモード: `<DownArrow>` 、 `<j>` 、 `<+>`</span><span class="sxs-lookup"><span data-stu-id="5149a-559">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="5149a-560">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="5149a-560">PreviousHistory</span></span>

<span data-ttu-id="5149a-561">現在の入力を、PSReadLine 履歴の ' previous ' 項目に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="5149a-561">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="5149a-562">コマンド: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-562">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="5149a-563">Emacs: `<UpArrow>` 、 `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="5149a-563">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="5149a-564">Vi の挿入モード: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-564">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="5149a-565">Vi コマンドモード: `<UpArrow>` 、 `<k>` 、 `<->`</span><span class="sxs-lookup"><span data-stu-id="5149a-565">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="5149a-566">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="5149a-566">ReverseSearchHistory</span></span>

<span data-ttu-id="5149a-567">履歴を介して後方検索を段階的に実行します。</span><span class="sxs-lookup"><span data-stu-id="5149a-567">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="5149a-568">コマンド: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="5149a-568">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="5149a-569">.Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="5149a-569">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="5149a-570">Visearchhistory 後方</span><span class="sxs-lookup"><span data-stu-id="5149a-570">ViSearchHistoryBackward</span></span>

<span data-ttu-id="5149a-571">検索文字列を入力し、AcceptLine で検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="5149a-571">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="5149a-572">Vi の挿入モード: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="5149a-572">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="5149a-573">Vi コマンドモード: `</>` 、 `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="5149a-573">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="5149a-574">入力候補関数</span><span class="sxs-lookup"><span data-stu-id="5149a-574">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="5149a-575">完了</span><span class="sxs-lookup"><span data-stu-id="5149a-575">Complete</span></span>

<span data-ttu-id="5149a-576">カーソルを囲むテキストに対して入力候補を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="5149a-576">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="5149a-577">候補が複数ある場合は、最長の明確なプレフィックスを使用して完了します。</span><span class="sxs-lookup"><span data-stu-id="5149a-577">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="5149a-578">最長の明確な完了を完了しようとすると、候補の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-578">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="5149a-579">.Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="5149a-579">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="5149a-580">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="5149a-580">MenuComplete</span></span>

<span data-ttu-id="5149a-581">カーソルを囲むテキストに対して入力候補を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="5149a-581">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="5149a-582">候補が複数ある場合は、最長の明確なプレフィックスを使用して完了します。</span><span class="sxs-lookup"><span data-stu-id="5149a-582">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="5149a-583">最長の明確な完了を完了しようとすると、候補の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-583">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="5149a-584">コマンド: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="5149a-584">Cmd: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="5149a-585">.Emacs `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="5149a-585">Emacs: `<Ctrl+Space>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="5149a-586">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="5149a-586">PossibleCompletions</span></span>

<span data-ttu-id="5149a-587">候補の候補の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="5149a-587">Display the list of possible completions.</span></span>

- <span data-ttu-id="5149a-588">.Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="5149a-588">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="5149a-589">Vi の挿入モード: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="5149a-589">Vi insert mode: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="5149a-590">Vi コマンドモード: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="5149a-590">Vi command mode: `<Ctrl+Space>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="5149a-591">タブのすべてのタブ</span><span class="sxs-lookup"><span data-stu-id="5149a-591">TabCompleteNext</span></span>

<span data-ttu-id="5149a-592">次に使用可能な完了時に、カーソルを囲むテキストを完了します。</span><span class="sxs-lookup"><span data-stu-id="5149a-592">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="5149a-593">コマンド: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="5149a-593">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="5149a-594">Vi コマンドモード: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="5149a-594">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="5149a-595">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="5149a-595">TabCompletePrevious</span></span>

<span data-ttu-id="5149a-596">以前に使用可能な入力候補を使用して、カーソルを囲むテキストを完了しようとしました。</span><span class="sxs-lookup"><span data-stu-id="5149a-596">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="5149a-597">コマンド: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="5149a-597">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="5149a-598">Vi コマンドモード: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="5149a-598">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="5149a-599">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="5149a-599">ViTabCompleteNext</span></span>

<span data-ttu-id="5149a-600">必要に応じて現在の編集グループを終了し、Tabends を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5149a-600">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="5149a-601">Vi の挿入モード: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="5149a-601">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="5149a-602">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="5149a-602">ViTabCompletePrevious</span></span>

<span data-ttu-id="5149a-603">必要に応じて現在の編集グループを終了し、TabCompletePrevious を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5149a-603">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="5149a-604">Vi の挿入モード: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="5149a-604">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="5149a-605">その他の関数</span><span class="sxs-lookup"><span data-stu-id="5149a-605">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="5149a-606">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="5149a-606">CaptureScreen</span></span>

<span data-ttu-id="5149a-607">対話型画面のキャプチャを開始する/下矢印行を選択し、[選択したテキストをテキストと html としてクリップボードにコピーする] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="5149a-607">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="5149a-608">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="5149a-608">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="5149a-609">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="5149a-609">ClearScreen</span></span>

<span data-ttu-id="5149a-610">画面をクリアし、画面の上部にある現在の線を描画します。</span><span class="sxs-lookup"><span data-stu-id="5149a-610">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="5149a-611">コマンド: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="5149a-611">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="5149a-612">.Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="5149a-612">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="5149a-613">Vi の挿入モード: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="5149a-613">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="5149a-614">Vi コマンドモード: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="5149a-614">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="5149a-615">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="5149a-615">DigitArgument</span></span>

<span data-ttu-id="5149a-616">他の関数に渡す新しい桁引数を開始します。</span><span class="sxs-lookup"><span data-stu-id="5149a-616">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="5149a-617">Cmd:、、、、、、、、、 `<Alt+0>` `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="5149a-617">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="5149a-618">Emacs:、、、、、、、、、 `<Alt+0>` `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="5149a-618">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="5149a-619">Vi コマンドモード:、、、、、、、、 `<0>` `<1>` `<2>` `<3>` `<4>` `<5>` `<6>` `<7>` `<8>` 、 `<9>`</span><span class="sxs-lookup"><span data-stu-id="5149a-619">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="5149a-620">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="5149a-620">InvokePrompt</span></span>

<span data-ttu-id="5149a-621">現在のプロンプトを消去し、prompt 関数を呼び出してプロンプトを再表示します。</span><span class="sxs-lookup"><span data-stu-id="5149a-621">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="5149a-622">現在のディレクトリを変更するなど、状態を変更するカスタムキーハンドラーに便利です。</span><span class="sxs-lookup"><span data-stu-id="5149a-622">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="5149a-623">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="5149a-623">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="5149a-624">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="5149a-624">ScrollDisplayDown</span></span>

<span data-ttu-id="5149a-625">画面を1画面下へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="5149a-625">Scroll the display down one screen.</span></span>

- <span data-ttu-id="5149a-626">コマンド: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="5149a-626">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="5149a-627">.Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="5149a-627">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="5149a-628">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="5149a-628">ScrollDisplayDownLine</span></span>

<span data-ttu-id="5149a-629">表示を1行下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="5149a-629">Scroll the display down one line.</span></span>

- <span data-ttu-id="5149a-630">コマンド: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="5149a-630">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="5149a-631">.Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="5149a-631">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="5149a-632">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="5149a-632">ScrollDisplayToCursor</span></span>

<span data-ttu-id="5149a-633">カーソルまで画面をスクロールします。</span><span class="sxs-lookup"><span data-stu-id="5149a-633">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="5149a-634">.Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="5149a-634">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="5149a-635">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="5149a-635">ScrollDisplayTop</span></span>

<span data-ttu-id="5149a-636">画面を上にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="5149a-636">Scroll the display to the top.</span></span>

- <span data-ttu-id="5149a-637">.Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="5149a-637">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="5149a-638">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="5149a-638">ScrollDisplayUp</span></span>

<span data-ttu-id="5149a-639">画面を1画面上へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="5149a-639">Scroll the display up one screen.</span></span>

- <span data-ttu-id="5149a-640">コマンド: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="5149a-640">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="5149a-641">.Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="5149a-641">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="5149a-642">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="5149a-642">ScrollDisplayUpLine</span></span>

<span data-ttu-id="5149a-643">表示を1行上へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="5149a-643">Scroll the display up one line.</span></span>

- <span data-ttu-id="5149a-644">コマンド: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="5149a-644">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="5149a-645">.Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="5149a-645">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="5149a-646">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="5149a-646">SelfInsert</span></span>

<span data-ttu-id="5149a-647">キーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="5149a-647">Insert the key.</span></span>

- <span data-ttu-id="5149a-648">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="5149a-648">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="5149a-649">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="5149a-649">ShowKeyBindings</span></span>

<span data-ttu-id="5149a-650">すべてのバインドされたキーを表示します。</span><span class="sxs-lookup"><span data-stu-id="5149a-650">Show all bound keys.</span></span>

- <span data-ttu-id="5149a-651">コマンド: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="5149a-651">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="5149a-652">.Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="5149a-652">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="5149a-653">Vi の挿入モード: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="5149a-653">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="5149a-654">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="5149a-654">ViCommandMode</span></span>

<span data-ttu-id="5149a-655">現在の動作モードを Vi-Insert から Vi-Command に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="5149a-655">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="5149a-656">Vi の挿入モード: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="5149a-656">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="5149a-657">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="5149a-657">ViDigitArgumentInChord</span></span>

<span data-ttu-id="5149a-658">Vi のいずれかの弦で、他の関数に渡す新しい桁引数を開始します。</span><span class="sxs-lookup"><span data-stu-id="5149a-658">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="5149a-659">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="5149a-659">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="5149a-660">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="5149a-660">ViEditVisually</span></span>

<span data-ttu-id="5149a-661">$Env: EDITOR または $env: ビジュアルによって指定されたテキストエディターでコマンドラインを編集します。</span><span class="sxs-lookup"><span data-stu-id="5149a-661">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="5149a-662">.Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="5149a-662">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="5149a-663">Vi コマンドモード: `<v>`</span><span class="sxs-lookup"><span data-stu-id="5149a-663">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="5149a-664">ViExit</span><span class="sxs-lookup"><span data-stu-id="5149a-664">ViExit</span></span>

<span data-ttu-id="5149a-665">シェルを終了します。</span><span class="sxs-lookup"><span data-stu-id="5149a-665">Exits the shell.</span></span>

- <span data-ttu-id="5149a-666">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="5149a-666">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="5149a-667">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="5149a-667">ViInsertMode</span></span>

<span data-ttu-id="5149a-668">挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="5149a-668">Switch to Insert mode.</span></span>

- <span data-ttu-id="5149a-669">Vi コマンドモード: `<i>`</span><span class="sxs-lookup"><span data-stu-id="5149a-669">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="5149a-670">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="5149a-670">WhatIsKey</span></span>

<span data-ttu-id="5149a-671">キーを読み取り、キーがどのようにバインドされているかを通知します。</span><span class="sxs-lookup"><span data-stu-id="5149a-671">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="5149a-672">コマンド: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="5149a-672">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="5149a-673">.Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="5149a-673">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="5149a-674">選択関数</span><span class="sxs-lookup"><span data-stu-id="5149a-674">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="5149a-675">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="5149a-675">ExchangePointAndMark</span></span>

<span data-ttu-id="5149a-676">カーソルがマークの位置に置かれ、マークがカーソルの位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-676">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="5149a-677">.Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="5149a-677">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="5149a-678">SelectAll</span><span class="sxs-lookup"><span data-stu-id="5149a-678">SelectAll</span></span>

<span data-ttu-id="5149a-679">行全体を選択します。</span><span class="sxs-lookup"><span data-stu-id="5149a-679">Select the entire line.</span></span>

- <span data-ttu-id="5149a-680">コマンド: `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="5149a-680">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="5149a-681">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="5149a-681">SelectBackwardChar</span></span>

<span data-ttu-id="5149a-682">現在の選択範囲を調整して、前の文字を含めます。</span><span class="sxs-lookup"><span data-stu-id="5149a-682">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="5149a-683">コマンド: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-683">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="5149a-684">.Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-684">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="5149a-685">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="5149a-685">SelectBackwardsLine</span></span>

<span data-ttu-id="5149a-686">カーソルから行の先頭まで、現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="5149a-686">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="5149a-687">コマンド: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="5149a-687">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="5149a-688">.Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="5149a-688">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="5149a-689">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="5149a-689">SelectBackwardWord</span></span>

<span data-ttu-id="5149a-690">現在の選択範囲を調整して、前の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="5149a-690">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="5149a-691">コマンド: `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-691">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="5149a-692">.Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="5149a-692">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="5149a-693">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="5149a-693">SelectForwardChar</span></span>

<span data-ttu-id="5149a-694">現在の選択範囲を調整して、次の文字を含めます。</span><span class="sxs-lookup"><span data-stu-id="5149a-694">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="5149a-695">コマンド: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-695">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="5149a-696">.Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-696">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="5149a-697">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="5149a-697">SelectForwardWord</span></span>

<span data-ttu-id="5149a-698">現在の選択範囲を調整して、ForwardWord を使用して次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="5149a-698">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="5149a-699">.Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="5149a-699">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="5149a-700">SelectLine</span><span class="sxs-lookup"><span data-stu-id="5149a-700">SelectLine</span></span>

<span data-ttu-id="5149a-701">カーソルから行の末尾まで、現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="5149a-701">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="5149a-702">コマンド: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="5149a-702">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="5149a-703">.Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="5149a-703">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="5149a-704">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="5149a-704">SelectNextWord</span></span>

<span data-ttu-id="5149a-705">現在の選択範囲を調整して、次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="5149a-705">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="5149a-706">コマンド: `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="5149a-706">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="5149a-707">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="5149a-707">SelectShellBackwardWord</span></span>

<span data-ttu-id="5149a-708">ShellBackwardWord を使用して、前の単語が含まれるように現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="5149a-708">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="5149a-709">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="5149a-709">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="5149a-710">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="5149a-710">SelectShellForwardWord</span></span>

<span data-ttu-id="5149a-711">現在の選択範囲を調整して、ShellForwardWord を使用する次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="5149a-711">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="5149a-712">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="5149a-712">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="5149a-713">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="5149a-713">SelectShellNextWord</span></span>

<span data-ttu-id="5149a-714">現在の選択範囲を調整して、ShellNextWord を使用して次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="5149a-714">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="5149a-715">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="5149a-715">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="5149a-716">SetMark</span><span class="sxs-lookup"><span data-stu-id="5149a-716">SetMark</span></span>

<span data-ttu-id="5149a-717">後続の編集コマンドで使用するために、カーソルの現在の位置をマークします。</span><span class="sxs-lookup"><span data-stu-id="5149a-717">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="5149a-718">.Emacs `<Ctrl+`>\`</span><span class="sxs-lookup"><span data-stu-id="5149a-718">Emacs: `<Ctrl+`>\`</span></span>

## <a name="search-functions"></a><span data-ttu-id="5149a-719">関数の検索</span><span class="sxs-lookup"><span data-stu-id="5149a-719">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="5149a-720">文字検索</span><span class="sxs-lookup"><span data-stu-id="5149a-720">CharacterSearch</span></span>

<span data-ttu-id="5149a-721">文字を読み取り、その文字が次に出現するまで検索します。</span><span class="sxs-lookup"><span data-stu-id="5149a-721">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="5149a-722">引数が指定されている場合は、n 番目のオカレンスに対して前方 (負の場合は後方) を検索します。</span><span class="sxs-lookup"><span data-stu-id="5149a-722">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="5149a-723">コマンド: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="5149a-723">Cmd: `<F3>`</span></span>
- <span data-ttu-id="5149a-724">.Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="5149a-724">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="5149a-725">Vi の挿入モード: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="5149a-725">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="5149a-726">Vi コマンドモード: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="5149a-726">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="5149a-727">文字 Search後方</span><span class="sxs-lookup"><span data-stu-id="5149a-727">CharacterSearchBackward</span></span>

<span data-ttu-id="5149a-728">文字を読み取り、その文字が次に出現するまで検索します。</span><span class="sxs-lookup"><span data-stu-id="5149a-728">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="5149a-729">引数が指定されている場合は、n 番目のオカレンスに対して後方 (または負の場合は forward) を検索します。</span><span class="sxs-lookup"><span data-stu-id="5149a-729">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="5149a-730">コマンド: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="5149a-730">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="5149a-731">.Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="5149a-731">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="5149a-732">Vi の挿入モード: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="5149a-732">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="5149a-733">Vi コマンドモード: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="5149a-733">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="5149a-734">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="5149a-734">RepeatLastCharSearch</span></span>

<span data-ttu-id="5149a-735">最後に記録された文字の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5149a-735">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="5149a-736">Vi コマンドモード: `<;>`</span><span class="sxs-lookup"><span data-stu-id="5149a-736">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="5149a-737">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="5149a-737">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="5149a-738">最後に記録された文字検索を逆方向に繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5149a-738">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="5149a-739">Vi コマンドモード: `<,>`</span><span class="sxs-lookup"><span data-stu-id="5149a-739">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="5149a-740">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="5149a-740">RepeatSearch</span></span>

<span data-ttu-id="5149a-741">前と同じ方向に最後の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5149a-741">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="5149a-742">Vi コマンドモード: `<n>`</span><span class="sxs-lookup"><span data-stu-id="5149a-742">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="5149a-743">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="5149a-743">RepeatSearchBackward</span></span>

<span data-ttu-id="5149a-744">前と同じ方向に最後の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5149a-744">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="5149a-745">Vi コマンドモード: `<N>`</span><span class="sxs-lookup"><span data-stu-id="5149a-745">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="5149a-746">SearchChar</span><span class="sxs-lookup"><span data-stu-id="5149a-746">SearchChar</span></span>

<span data-ttu-id="5149a-747">次の文字を読み取って検索し、次に文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="5149a-747">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="5149a-748">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="5149a-748">This is for 't' functionality.</span></span>

- <span data-ttu-id="5149a-749">Vi コマンドモード: `<f>`</span><span class="sxs-lookup"><span data-stu-id="5149a-749">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="5149a-750">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="5149a-750">SearchCharBackward</span></span>

<span data-ttu-id="5149a-751">次の文字を読み取り、それを検索して後方に移動し、次に文字を戻します。</span><span class="sxs-lookup"><span data-stu-id="5149a-751">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="5149a-752">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="5149a-752">This is for 'T' functionality.</span></span>

- <span data-ttu-id="5149a-753">Vi コマンドモード: `<F>`</span><span class="sxs-lookup"><span data-stu-id="5149a-753">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="5149a-754">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="5149a-754">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="5149a-755">次の文字を読み取り、それを検索して後方に移動し、次に文字を戻します。</span><span class="sxs-lookup"><span data-stu-id="5149a-755">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="5149a-756">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="5149a-756">This is for 'T' functionality.</span></span>

- <span data-ttu-id="5149a-757">Vi コマンドモード: `<T>`</span><span class="sxs-lookup"><span data-stu-id="5149a-757">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="5149a-758">SearchCharWithBackoff オフ</span><span class="sxs-lookup"><span data-stu-id="5149a-758">SearchCharWithBackoff</span></span>

<span data-ttu-id="5149a-759">次の文字を読み取って検索し、次に文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="5149a-759">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="5149a-760">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="5149a-760">This is for 't' functionality.</span></span>

- <span data-ttu-id="5149a-761">Vi コマンドモード: `<t>`</span><span class="sxs-lookup"><span data-stu-id="5149a-761">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="5149a-762">SearchForward</span><span class="sxs-lookup"><span data-stu-id="5149a-762">SearchForward</span></span>

<span data-ttu-id="5149a-763">検索文字列を入力し、AcceptLine で検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="5149a-763">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="5149a-764">Vi の挿入モード: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="5149a-764">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="5149a-765">Vi コマンドモード: `<?>` 、 `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="5149a-765">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="5149a-766">カスタムキーバインド</span><span class="sxs-lookup"><span data-stu-id="5149a-766">Custom Key Bindings</span></span>

<span data-ttu-id="5149a-767">PSReadLine は、コマンドレットを使用してカスタムキーバインドをサポートしてい `Set-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="5149a-767">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="5149a-768">ほとんどのカスタムキーバインドは、たとえば、上記の関数の1つを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5149a-768">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="5149a-769">ScriptBlock をキーにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="5149a-769">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="5149a-770">ScriptBlock は、ほとんどすべてのことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5149a-770">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="5149a-771">いくつかの便利な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5149a-771">Some useful examples include</span></span>

- <span data-ttu-id="5149a-772">コマンドラインを編集する</span><span class="sxs-lookup"><span data-stu-id="5149a-772">edit the command line</span></span>
- <span data-ttu-id="5149a-773">新しいウィンドウを開く (例: ヘルプ)</span><span class="sxs-lookup"><span data-stu-id="5149a-773">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="5149a-774">コマンドラインを変更せずにディレクトリを変更する</span><span class="sxs-lookup"><span data-stu-id="5149a-774">change directories without changing the command line</span></span>

<span data-ttu-id="5149a-775">ScriptBlock は、次の2つの引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5149a-775">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="5149a-776">`$key` -カスタムバインドをトリガーしたキーである **[Consolekeyinfo]** オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5149a-776">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="5149a-777">同じ ScriptBlock を複数のキーにバインドし、キーに応じて異なるアクションを実行する必要がある場合は、$key を確認します。</span><span class="sxs-lookup"><span data-stu-id="5149a-777">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="5149a-778">多くのカスタムバインドでは、この引数は無視します。</span><span class="sxs-lookup"><span data-stu-id="5149a-778">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="5149a-779">`$arg` -任意の引数。</span><span class="sxs-lookup"><span data-stu-id="5149a-779">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="5149a-780">多くの場合、これは、ユーザーがキーバインド DigitArgument から渡す整数引数になります。</span><span class="sxs-lookup"><span data-stu-id="5149a-780">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="5149a-781">バインディングが引数を受け入れない場合は、この引数を無視するのが妥当です。</span><span class="sxs-lookup"><span data-stu-id="5149a-781">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="5149a-782">ここでは、コマンドラインを実行せずに履歴に追加する例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="5149a-782">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="5149a-783">これは、何らかの操作を忘れた場合に、既に入力したコマンドラインを再入力したくない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="5149a-783">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="5149a-784">PSReadLine モジュールフォルダーにインストールされているファイルには、さらに多くの例が表示 `SamplePSReadLineProfile.ps1` されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-784">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="5149a-785">ほとんどのキーバインドでは、コマンドラインを編集するためにいくつかのヘルパー関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="5149a-785">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="5149a-786">これらの Api については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="5149a-786">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="5149a-787">カスタムキーバインディングサポート Api</span><span class="sxs-lookup"><span data-stu-id="5149a-787">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="5149a-788">次の関数は PSConsoleReadLine では公開されていますが、キーに直接バインドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5149a-788">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="5149a-789">多くの場合、カスタムキーバインドに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5149a-789">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="5149a-790">コマンドラインを実行せずに、履歴に追加します。</span><span class="sxs-lookup"><span data-stu-id="5149a-790">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="5149a-791">Kill リングをクリアします。</span><span class="sxs-lookup"><span data-stu-id="5149a-791">Clear the kill-ring.</span></span>  <span data-ttu-id="5149a-792">これは主にテストに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-792">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="5149a-793">先頭から長さの文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="5149a-793">Delete length characters from start.</span></span>  <span data-ttu-id="5149a-794">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5149a-794">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="5149a-795">ユーザー設定に基づいてアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="5149a-795">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="5149a-796">これらの2つの関数は、入力バッファーの現在の状態に関する有用な情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="5149a-796">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="5149a-797">1つ目は、単純なケースでよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-797">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="5149a-798">2つ目は、バインディングが Ast を使用してより高度な処理を実行している場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-798">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

```

<span data-ttu-id="5149a-799">この関数は Get-PSReadLineKeyHandler によって使用され、カスタムキーバインドでは役に立たない場合があります。</span><span class="sxs-lookup"><span data-stu-id="5149a-799">This function is used by Get-PSReadLineKeyHandler and probably isn't useful in a custom key binding.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="5149a-800">この関数は Get-PSReadLineOption によって使用され、カスタムキーバインドではあまり役に立たない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5149a-800">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="5149a-801">コマンドラインに何も選択されていない場合は、開始と長さの両方で-1 が返されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-801">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="5149a-802">コマンドラインに選択項目がある場合は、選択範囲の先頭と長さが返されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-802">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="5149a-803">カーソル位置に文字または文字列を挿入します。</span><span class="sxs-lookup"><span data-stu-id="5149a-803">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="5149a-804">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5149a-804">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="5149a-805">これは、PSReadLine へのメインエントリポイントです。</span><span class="sxs-lookup"><span data-stu-id="5149a-805">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="5149a-806">再帰はサポートされないため、カスタムキーバインドでは役に立ちません。</span><span class="sxs-lookup"><span data-stu-id="5149a-806">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="5149a-807">この関数は Remove-PSReadLineKeyHandler によって使用され、カスタムキーバインドではあまり役に立たない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5149a-807">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="5149a-808">入力の一部を置換します。</span><span class="sxs-lookup"><span data-stu-id="5149a-808">Replace some of the input.</span></span> <span data-ttu-id="5149a-809">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5149a-809">This operation supports undo/redo.</span></span> <span data-ttu-id="5149a-810">これは、undo の単一のアクションとして扱われるため、Delete の後に Insert を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5149a-810">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="5149a-811">カーソルを指定されたオフセットに移動します。</span><span class="sxs-lookup"><span data-stu-id="5149a-811">Move the cursor to the given offset.</span></span> <span data-ttu-id="5149a-812">カーソルの移動は、元に戻すために追跡されません。</span><span class="sxs-lookup"><span data-stu-id="5149a-812">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="5149a-813">この関数は、コマンドレットの設定-PSReadLineOption によって使用されるヘルパーメソッドですが、一時的に設定を変更する必要があるカスタムキーバインドに便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="5149a-813">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="5149a-814">このヘルパーメソッドは、DigitArgument を優先するカスタムバインドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-814">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="5149a-815">一般的な呼び出しは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5149a-815">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="5149a-816">注</span><span class="sxs-lookup"><span data-stu-id="5149a-816">NOTE</span></span>

### <a name="powershell-compatibility"></a><span data-ttu-id="5149a-817">POWERSHELL の互換性</span><span class="sxs-lookup"><span data-stu-id="5149a-817">POWERSHELL COMPATIBILITY</span></span>

<span data-ttu-id="5149a-818">PSReadLine には、PowerShell 3.0 以降とコンソールホストが必要です。</span><span class="sxs-lookup"><span data-stu-id="5149a-818">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="5149a-819">PowerShell ISE では機能しません。</span><span class="sxs-lookup"><span data-stu-id="5149a-819">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="5149a-820">これは Visual Studio Code のコンソールで機能します。</span><span class="sxs-lookup"><span data-stu-id="5149a-820">It does work in the console of Visual Studio Code.</span></span>

### <a name="command-history"></a><span data-ttu-id="5149a-821">コマンド履歴</span><span class="sxs-lookup"><span data-stu-id="5149a-821">COMMAND HISTORY</span></span>

<span data-ttu-id="5149a-822">PSReadLine は、コマンドラインから入力したすべてのコマンドとデータを含む履歴ファイルを保持します。</span><span class="sxs-lookup"><span data-stu-id="5149a-822">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="5149a-823">これには、パスワードなどの機密データが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5149a-823">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="5149a-824">たとえば、コマンドレットを使用した場合、 `ConvertTo-SecureString` パスワードはプレーンテキストとして履歴ファイルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="5149a-824">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="5149a-825">履歴ファイルは、という名前のファイルです `$($host.Name)_history.txt` 。</span><span class="sxs-lookup"><span data-stu-id="5149a-825">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="5149a-826">Windows システムでは、履歴ファイルはに格納され `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` ます。</span><span class="sxs-lookup"><span data-stu-id="5149a-826">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="5149a-827">Windows 以外のシステムでは、履歴ファイルはまたはに格納され `$env:XDG_DATA_HOME/powershell/PSReadLine` `$env:HOME/.local/share/powershell/PSReadLine` ます。</span><span class="sxs-lookup"><span data-stu-id="5149a-827">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="5149a-828">PSReadLine に貢献しているフィードバック &</span><span class="sxs-lookup"><span data-stu-id="5149a-828">FEEDBACK & CONTRIBUTING TO PSReadLine</span></span>

[<span data-ttu-id="5149a-829">GitHub の PSReadLine</span><span class="sxs-lookup"><span data-stu-id="5149a-829">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="5149a-830">プル要求を送信したり、GitHub ページでフィードバックを送信したりしてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="5149a-830">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="5149a-831">関連項目</span><span class="sxs-lookup"><span data-stu-id="5149a-831">SEE ALSO</span></span>

<span data-ttu-id="5149a-832">PSReadLine は、GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) ライブラリの影響を強く受けます。</span><span class="sxs-lookup"><span data-stu-id="5149a-832">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
