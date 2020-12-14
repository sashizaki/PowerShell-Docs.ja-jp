---
description: PSReadLine では、PowerShell コンソールでのコマンドライン編集エクスペリエンスが向上しています。
keywords: powershell
Locale: en-US
ms.date: 11/16/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: PSReadLine について
ms.openlocfilehash: 25fc3a9a814728057b1ebc7e721d3fba84ae72c2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "94692311"
---
# <a name="psreadline"></a><span data-ttu-id="31a43-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="31a43-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="31a43-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="31a43-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="31a43-106">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="31a43-106">Short Description</span></span>

<span data-ttu-id="31a43-107">PSReadLine では、PowerShell コンソールでのコマンドライン編集エクスペリエンスが向上しています。</span><span class="sxs-lookup"><span data-stu-id="31a43-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="31a43-108">長い説明</span><span class="sxs-lookup"><span data-stu-id="31a43-108">Long Description</span></span>

<span data-ttu-id="31a43-109">PSReadLine 2.0 では、PowerShell コンソールの強力なコマンドライン編集エクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="31a43-110">次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="31a43-110">It provides:</span></span>

- <span data-ttu-id="31a43-111">コマンドラインの構文の色分け</span><span class="sxs-lookup"><span data-stu-id="31a43-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="31a43-112">構文エラーを視覚的に示します。</span><span class="sxs-lookup"><span data-stu-id="31a43-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="31a43-113">より優れたマルチラインエクスペリエンス (編集と履歴の両方)</span><span class="sxs-lookup"><span data-stu-id="31a43-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="31a43-114">カスタマイズ可能なキーバインド</span><span class="sxs-lookup"><span data-stu-id="31a43-114">Customizable key bindings</span></span>
- <span data-ttu-id="31a43-115">Cmd モードと Emacs モード</span><span class="sxs-lookup"><span data-stu-id="31a43-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="31a43-116">多くの構成オプション</span><span class="sxs-lookup"><span data-stu-id="31a43-116">Many configuration options</span></span>
- <span data-ttu-id="31a43-117">Bash スタイル補完 (Cmd モードでは省略可能、Emacs モードでは既定)</span><span class="sxs-lookup"><span data-stu-id="31a43-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="31a43-118">Emacs yank/kill-リング</span><span class="sxs-lookup"><span data-stu-id="31a43-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="31a43-119">PowerShell トークンベースの "word" の移動と強制終了</span><span class="sxs-lookup"><span data-stu-id="31a43-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="31a43-120">PSReadLine には、PowerShell 3.0 以降とコンソールホストが必要です。</span><span class="sxs-lookup"><span data-stu-id="31a43-120">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="31a43-121">PowerShell ISE では機能しません。</span><span class="sxs-lookup"><span data-stu-id="31a43-121">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="31a43-122">これは Visual Studio Code のコンソールで機能します。</span><span class="sxs-lookup"><span data-stu-id="31a43-122">It does work in the console of Visual Studio Code.</span></span>

<span data-ttu-id="31a43-123">クラス **[PSConsoleReadLine]** では、次の関数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="31a43-123">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="31a43-124">基本的な編集関数</span><span class="sxs-lookup"><span data-stu-id="31a43-124">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="31a43-125">中止</span><span class="sxs-lookup"><span data-stu-id="31a43-125">Abort</span></span>

<span data-ttu-id="31a43-126">現在のアクション (増分履歴検索など) を中止します。</span><span class="sxs-lookup"><span data-stu-id="31a43-126">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="31a43-127">.Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="31a43-127">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="31a43-128">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="31a43-128">AcceptAndGetNext</span></span>

<span data-ttu-id="31a43-129">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="31a43-129">Attempt to execute the current input.</span></span> <span data-ttu-id="31a43-130">(AcceptLine など) 実行できる場合は、次に ReadLine が呼び出されたときに履歴から次の項目を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="31a43-130">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="31a43-131">.Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="31a43-131">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="31a43-132">AcceptLine</span><span class="sxs-lookup"><span data-stu-id="31a43-132">AcceptLine</span></span>

<span data-ttu-id="31a43-133">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="31a43-133">Attempt to execute the current input.</span></span> <span data-ttu-id="31a43-134">現在の入力が不完全な場合 (たとえば、終わりかっこ、角かっこ、または引用符がない場合)、継続のプロンプトは次の行に表示され、PSReadLine は現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="31a43-134">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="31a43-135">コマンド: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="31a43-135">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="31a43-136">.Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="31a43-136">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="31a43-137">Vi の挿入モード: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="31a43-137">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="31a43-138">AddLine</span><span class="sxs-lookup"><span data-stu-id="31a43-138">AddLine</span></span>

<span data-ttu-id="31a43-139">継続プロンプトが次の行に表示され、PSReadLine が現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="31a43-139">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="31a43-140">これは、単一行が単独で完全に入力されている場合でも、複数行の入力を1つのコマンドとして入力する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="31a43-140">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="31a43-141">コマンド: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="31a43-141">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="31a43-142">.Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="31a43-142">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="31a43-143">Vi の挿入モード: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="31a43-143">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="31a43-144">Vi コマンドモード: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="31a43-144">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="31a43-145">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="31a43-145">BackwardDeleteChar</span></span>

<span data-ttu-id="31a43-146">カーソルの前の文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="31a43-146">Delete the character before the cursor.</span></span>

- <span data-ttu-id="31a43-147">Cmd: `<Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="31a43-147">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="31a43-148">Emacs: `<Backspace>` 、 `<Ctrl+Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="31a43-148">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="31a43-149">Vi の挿入モード: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="31a43-149">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="31a43-150">Vi コマンドモード: `<X>` 、 `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="31a43-150">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="31a43-151">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="31a43-151">BackwardDeleteLine</span></span>

<span data-ttu-id="31a43-152">Like BackwardKillLine-行の先頭から先頭までのテキストを削除しますが、削除されたテキストはキルリングには挿入されません。</span><span class="sxs-lookup"><span data-stu-id="31a43-152">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="31a43-153">コマンド: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="31a43-153">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="31a43-154">Vi 挿入モード: `<Ctrl+u>` 、 `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="31a43-154">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="31a43-155">Vi コマンドモード: `<Ctrl+u>` 、 `<Ctrl+Home>` 、 `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="31a43-155">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="31a43-156">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="31a43-156">BackwardDeleteWord</span></span>

<span data-ttu-id="31a43-157">前の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="31a43-157">Deletes the previous word.</span></span>

- <span data-ttu-id="31a43-158">Vi コマンドモード: `<Ctrl+w>` 、 `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="31a43-158">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="31a43-159">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="31a43-159">BackwardKillLine</span></span>

<span data-ttu-id="31a43-160">入力の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="31a43-160">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="31a43-161">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-161">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="31a43-162">Emacs: `<Ctrl+u>` 、 `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="31a43-162">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="31a43-163">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="31a43-163">BackwardKillWord</span></span>

<span data-ttu-id="31a43-164">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="31a43-164">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="31a43-165">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="31a43-165">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="31a43-166">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-166">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="31a43-167">コマンド: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="31a43-167">Cmd: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="31a43-168">Emacs: `<Alt+Backspace>` 、 `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="31a43-168">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="31a43-169">Vi の挿入モード: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="31a43-169">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="31a43-170">Vi コマンドモード: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="31a43-170">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="31a43-171">CancelLine</span><span class="sxs-lookup"><span data-stu-id="31a43-171">CancelLine</span></span>

<span data-ttu-id="31a43-172">入力を画面に残したまま、現在の入力を取り消しますが、プロンプトが再び評価されるように、ホストに戻ります。</span><span class="sxs-lookup"><span data-stu-id="31a43-172">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="31a43-173">Vi の挿入モード: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="31a43-173">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="31a43-174">Vi コマンドモード: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="31a43-174">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="31a43-175">コピー</span><span class="sxs-lookup"><span data-stu-id="31a43-175">Copy</span></span>

<span data-ttu-id="31a43-176">選択したリージョンをシステムクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="31a43-176">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="31a43-177">領域が選択されていない場合は、行全体をコピーします。</span><span class="sxs-lookup"><span data-stu-id="31a43-177">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="31a43-178">コマンド: `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="31a43-178">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="31a43-179">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="31a43-179">CopyOrCancelLine</span></span>

<span data-ttu-id="31a43-180">テキストが選択されている場合は、クリップボードにコピーします。それ以外の場合は、行をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="31a43-180">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="31a43-181">コマンド: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="31a43-181">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="31a43-182">.Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="31a43-182">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="31a43-183">［切り取り］</span><span class="sxs-lookup"><span data-stu-id="31a43-183">Cut</span></span>

<span data-ttu-id="31a43-184">削除されたテキストをシステムクリップボードに配置した、選択した領域を削除します。</span><span class="sxs-lookup"><span data-stu-id="31a43-184">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="31a43-185">コマンド: `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="31a43-185">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="31a43-186">Dele</span><span class="sxs-lookup"><span data-stu-id="31a43-186">DeleteChar</span></span>

<span data-ttu-id="31a43-187">カーソルの下の文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="31a43-187">Delete the character under the cursor.</span></span>

- <span data-ttu-id="31a43-188">コマンド: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="31a43-188">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="31a43-189">.Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="31a43-189">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="31a43-190">Vi の挿入モード: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="31a43-190">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="31a43-191">Vi コマンドモード: `<Delete>` 、 `<x>` 、 `<d,l>` 、 `<d,Space>`</span><span class="sxs-lookup"><span data-stu-id="31a43-191">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Space>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="31a43-192">Deleの Arorexit</span><span class="sxs-lookup"><span data-stu-id="31a43-192">DeleteCharOrExit</span></span>

<span data-ttu-id="31a43-193">カーソルの下の文字を削除するか、行が空の場合はプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="31a43-193">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="31a43-194">.Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="31a43-194">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="31a43-195">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="31a43-195">DeleteEndOfWord</span></span>

<span data-ttu-id="31a43-196">単語の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="31a43-196">Delete to the end of the word.</span></span>

- <span data-ttu-id="31a43-197">Vi コマンドモード: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="31a43-197">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="31a43-198">Deleteline.invoke に</span><span class="sxs-lookup"><span data-stu-id="31a43-198">DeleteLine</span></span>

<span data-ttu-id="31a43-199">現在の行を削除して、元に戻す操作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="31a43-199">Deletes the current line, enabling undo.</span></span>

- <span data-ttu-id="31a43-200">Vi コマンドモード: `<d,d>`</span><span class="sxs-lookup"><span data-stu-id="31a43-200">Vi command mode: `<d,d>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="31a43-201">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="31a43-201">DeleteLineToFirstChar</span></span>

<span data-ttu-id="31a43-202">カーソルから、行の最初の空白以外の文字までのテキストを削除します。</span><span class="sxs-lookup"><span data-stu-id="31a43-202">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="31a43-203">Vi コマンドモード: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="31a43-203">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="31a43-204">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="31a43-204">DeleteToEnd</span></span>

<span data-ttu-id="31a43-205">行の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="31a43-205">Delete to the end of the line.</span></span>

- <span data-ttu-id="31a43-206">Vi コマンドモード: `<D>` 、 `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="31a43-206">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="31a43-207">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="31a43-207">DeleteWord</span></span>

<span data-ttu-id="31a43-208">次の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="31a43-208">Delete the next word.</span></span>

- <span data-ttu-id="31a43-209">Vi コマンドモード: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="31a43-209">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="31a43-210">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="31a43-210">ForwardDeleteLine</span></span>

<span data-ttu-id="31a43-211">同じように、Forwardは、行の末尾から最後までのテキストを削除しますが、削除されたテキストはキルリングには挿入されません。</span><span class="sxs-lookup"><span data-stu-id="31a43-211">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="31a43-212">コマンド: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="31a43-212">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="31a43-213">Vi の挿入モード: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="31a43-213">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="31a43-214">Vi コマンドモード: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="31a43-214">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="31a43-215">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="31a43-215">InsertLineAbove</span></span>

<span data-ttu-id="31a43-216">現在の行の上にカーソルがある場所に関係なく、現在の行の上に新しい空の行が作成されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-216">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="31a43-217">カーソルが新しい行の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-217">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="31a43-218">コマンド: `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="31a43-218">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="31a43-219">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="31a43-219">InsertLineBelow</span></span>

<span data-ttu-id="31a43-220">カーソルが現在の行にある場所に関係なく、現在の行の下に新しい空の行が作成されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-220">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="31a43-221">カーソルが新しい行の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-221">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="31a43-222">コマンド: `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="31a43-222">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="31a43-223">InvertCase</span><span class="sxs-lookup"><span data-stu-id="31a43-223">InvertCase</span></span>

<span data-ttu-id="31a43-224">現在の文字の大文字と小文字の区別を反転し、次の文字に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-224">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="31a43-225">Vi コマンドモード: `<~>`</span><span class="sxs-lookup"><span data-stu-id="31a43-225">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="31a43-226">行の行</span><span class="sxs-lookup"><span data-stu-id="31a43-226">KillLine</span></span>

<span data-ttu-id="31a43-227">カーソルから入力の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="31a43-227">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="31a43-228">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-228">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="31a43-229">.Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="31a43-229">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="31a43-230">"/" 領域</span><span class="sxs-lookup"><span data-stu-id="31a43-230">KillRegion</span></span>

<span data-ttu-id="31a43-231">カーソルとマークの間のテキストを強制終了します。</span><span class="sxs-lookup"><span data-stu-id="31a43-231">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="31a43-232">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="31a43-232">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="31a43-233">文字の候補</span><span class="sxs-lookup"><span data-stu-id="31a43-233">KillWord</span></span>

<span data-ttu-id="31a43-234">カーソルから現在の単語の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="31a43-234">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="31a43-235">カーソルが単語の間にある場合は、カーソルから次の単語の末尾まで、入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="31a43-235">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="31a43-236">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-236">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="31a43-237">コマンド: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="31a43-237">Cmd: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="31a43-238">Emacs: `<Alt+d>` 、 `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="31a43-238">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="31a43-239">Vi の挿入モード: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="31a43-239">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="31a43-240">Vi コマンドモード: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="31a43-240">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="31a43-241">貼り付け</span><span class="sxs-lookup"><span data-stu-id="31a43-241">Paste</span></span>

<span data-ttu-id="31a43-242">システムクリップボードからテキストを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="31a43-242">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="31a43-243">Cmd: `<Ctrl+v>` 、 `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="31a43-243">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="31a43-244">Vi の挿入モード: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="31a43-244">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="31a43-245">Vi コマンドモード: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="31a43-245">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31a43-246">**貼り付け** 関数を使用すると、クリップボードバッファーの内容全体が psreadline の入力バッファーに貼り付けられます。</span><span class="sxs-lookup"><span data-stu-id="31a43-246">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="31a43-247">入力バッファーが PowerShell パーサーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-247">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="31a43-248">コンソールアプリケーションの **右クリック** による貼り付けメソッドを使用して貼り付けた入力は、一度に1文字ずつ入力バッファーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="31a43-248">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="31a43-249">入力バッファーは、改行文字がコピーされるときにパーサーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-249">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="31a43-250">そのため、入力は一度に1行ずつ解析されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-250">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="31a43-251">貼り付けメソッドの違いによって、実行の動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="31a43-251">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="31a43-252">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="31a43-252">PasteAfter</span></span>

<span data-ttu-id="31a43-253">カーソルの後にクリップボードを貼り付けて、貼り付けられたテキストの末尾にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-253">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="31a43-254">Vi コマンドモード: `<p>`</span><span class="sxs-lookup"><span data-stu-id="31a43-254">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="31a43-255">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="31a43-255">PasteBefore</span></span>

<span data-ttu-id="31a43-256">カーソルの前にクリップボードを貼り付けて、貼り付けられたテキストの末尾にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-256">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="31a43-257">Vi コマンドモード: `<P>`</span><span class="sxs-lookup"><span data-stu-id="31a43-257">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="31a43-258">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="31a43-258">PrependAndAccept</span></span>

<span data-ttu-id="31a43-259">' # ' を先頭に付加し、その行を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="31a43-259">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="31a43-260">Vi コマンドモード: `<#>`</span><span class="sxs-lookup"><span data-stu-id="31a43-260">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="31a43-261">やり直し</span><span class="sxs-lookup"><span data-stu-id="31a43-261">Redo</span></span>

<span data-ttu-id="31a43-262">元に戻す操作を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="31a43-262">Undo an undo.</span></span>

- <span data-ttu-id="31a43-263">コマンド: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="31a43-263">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="31a43-264">Vi の挿入モード: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="31a43-264">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="31a43-265">Vi コマンドモード: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="31a43-265">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="31a43-266">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="31a43-266">RepeatLastCommand</span></span>

<span data-ttu-id="31a43-267">最後のテキストの変更を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="31a43-267">Repeat the last text modification.</span></span>

- <span data-ttu-id="31a43-268">Vi コマンドモード: `<.>`</span><span class="sxs-lookup"><span data-stu-id="31a43-268">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="31a43-269">再有効化</span><span class="sxs-lookup"><span data-stu-id="31a43-269">RevertLine</span></span>

<span data-ttu-id="31a43-270">すべての入力を現在の入力に戻します。</span><span class="sxs-lookup"><span data-stu-id="31a43-270">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="31a43-271">コマンド: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="31a43-271">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="31a43-272">Emacs: `<Alt+r>` 、 `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="31a43-272">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="31a43-273">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="31a43-273">ShellBackwardKillWord</span></span>

<span data-ttu-id="31a43-274">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="31a43-274">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="31a43-275">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="31a43-275">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="31a43-276">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-276">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="31a43-277">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="31a43-277">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="31a43-278">Shellは Word</span><span class="sxs-lookup"><span data-stu-id="31a43-278">ShellKillWord</span></span>

<span data-ttu-id="31a43-279">カーソルから現在の単語の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="31a43-279">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="31a43-280">カーソルが単語の間にある場合は、カーソルから次の単語の末尾まで、入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="31a43-280">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="31a43-281">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-281">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="31a43-282">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="31a43-282">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="31a43-283">スワップ文字</span><span class="sxs-lookup"><span data-stu-id="31a43-283">SwapCharacters</span></span>

<span data-ttu-id="31a43-284">現在の文字とそれより前の文字を交換します。</span><span class="sxs-lookup"><span data-stu-id="31a43-284">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="31a43-285">.Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="31a43-285">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="31a43-286">Vi の挿入モード: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="31a43-286">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="31a43-287">Vi コマンドモード: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="31a43-287">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="31a43-288">元に戻す</span><span class="sxs-lookup"><span data-stu-id="31a43-288">Undo</span></span>

<span data-ttu-id="31a43-289">前の編集を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="31a43-289">Undo a previous edit.</span></span>

- <span data-ttu-id="31a43-290">コマンド: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="31a43-290">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="31a43-291">Emacs: `<Ctrl+_>` 、 `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="31a43-291">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="31a43-292">Vi の挿入モード: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="31a43-292">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="31a43-293">Vi コマンドモード: `<Ctrl+z>` 、 `<u>`</span><span class="sxs-lookup"><span data-stu-id="31a43-293">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="31a43-294">UndoAll</span><span class="sxs-lookup"><span data-stu-id="31a43-294">UndoAll</span></span>

<span data-ttu-id="31a43-295">行の以前の編集をすべて元に戻します。</span><span class="sxs-lookup"><span data-stu-id="31a43-295">Undo all previous edits for line.</span></span>

- <span data-ttu-id="31a43-296">Vi コマンドモード: `<U>`</span><span class="sxs-lookup"><span data-stu-id="31a43-296">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="31a43-297">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="31a43-297">UnixWordRubout</span></span>

<span data-ttu-id="31a43-298">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="31a43-298">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="31a43-299">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="31a43-299">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="31a43-300">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-300">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="31a43-301">.Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="31a43-301">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="31a43-302">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="31a43-302">ValidateAndAcceptLine</span></span>

<span data-ttu-id="31a43-303">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="31a43-303">Attempt to execute the current input.</span></span> <span data-ttu-id="31a43-304">現在の入力が不完全な場合 (たとえば、終わりかっこ、角かっこ、または引用符がない場合)、継続のプロンプトは次の行に表示され、PSReadLine は現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="31a43-304">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="31a43-305">.Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="31a43-305">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="31a43-306">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="31a43-306">ViAcceptLine</span></span>

<span data-ttu-id="31a43-307">行を受け入れ、挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="31a43-307">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="31a43-308">Vi コマンドモード: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="31a43-308">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="31a43-309">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="31a43-309">ViAcceptLineOrExit</span></span>

<span data-ttu-id="31a43-310">(Emacs モードでは Deleと同じですが、文字を削除するのではなく、行を受け取ります)。</span><span class="sxs-lookup"><span data-stu-id="31a43-310">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="31a43-311">Vi の挿入モード: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="31a43-311">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="31a43-312">Vi コマンドモード: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="31a43-312">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="31a43-313">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="31a43-313">ViAppendLine</span></span>

<span data-ttu-id="31a43-314">現在の行の下に新しい行が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-314">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="31a43-315">Vi コマンドモード: `<o>`</span><span class="sxs-lookup"><span data-stu-id="31a43-315">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="31a43-316">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="31a43-316">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="31a43-317">単語区切り記号として空白文字のみを使用して、前の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="31a43-317">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="31a43-318">Vi コマンドモード: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="31a43-318">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="31a43-319">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="31a43-319">ViBackwardGlob</span></span>

<span data-ttu-id="31a43-320">区切り記号として空白文字のみを使用して、カーソルを前の単語の先頭に戻します。</span><span class="sxs-lookup"><span data-stu-id="31a43-320">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="31a43-321">Vi コマンドモード: `<B>`</span><span class="sxs-lookup"><span data-stu-id="31a43-321">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="31a43-322">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="31a43-322">ViDeleteBrace</span></span>

<span data-ttu-id="31a43-323">対応する中かっこ、かっこ、または角かっこを検索し、中かっこを含め、内のすべての内容を削除します。</span><span class="sxs-lookup"><span data-stu-id="31a43-323">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="31a43-324">Vi コマンドモード: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="31a43-324">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="31a43-325">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="31a43-325">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="31a43-326">単語の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="31a43-326">Delete to the end of the word.</span></span>

- <span data-ttu-id="31a43-327">Vi コマンドモード: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="31a43-327">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="31a43-328">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="31a43-328">ViDeleteGlob</span></span>

<span data-ttu-id="31a43-329">次の glob (空白で区切られた単語) を削除します。</span><span class="sxs-lookup"><span data-stu-id="31a43-329">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="31a43-330">Vi コマンドモード: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="31a43-330">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="31a43-331">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="31a43-331">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="31a43-332">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="31a43-332">Deletes until given character.</span></span>

- <span data-ttu-id="31a43-333">Vi コマンドモード: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="31a43-333">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="31a43-334">Videletetobeforo</span><span class="sxs-lookup"><span data-stu-id="31a43-334">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="31a43-335">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="31a43-335">Deletes until given character.</span></span>

- <span data-ttu-id="31a43-336">Vi コマンドモード: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="31a43-336">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="31a43-337">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="31a43-337">ViDeleteToChar</span></span>

<span data-ttu-id="31a43-338">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="31a43-338">Deletes until given character.</span></span>

- <span data-ttu-id="31a43-339">Vi コマンドモード: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="31a43-339">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="31a43-340">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="31a43-340">ViDeleteToCharBackward</span></span>

<span data-ttu-id="31a43-341">指定された文字まで後方を削除します。</span><span class="sxs-lookup"><span data-stu-id="31a43-341">Deletes backwards until given character.</span></span>

- <span data-ttu-id="31a43-342">Vi コマンドモード: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="31a43-342">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="31a43-343">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="31a43-343">ViInsertAtBegining</span></span>

<span data-ttu-id="31a43-344">挿入モードに切り替え、カーソルを行の先頭に配置します。</span><span class="sxs-lookup"><span data-stu-id="31a43-344">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="31a43-345">Vi コマンドモード: `<I>`</span><span class="sxs-lookup"><span data-stu-id="31a43-345">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="31a43-346">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="31a43-346">ViInsertAtEnd</span></span>

<span data-ttu-id="31a43-347">挿入モードに切り替え、カーソルを行の末尾に配置します。</span><span class="sxs-lookup"><span data-stu-id="31a43-347">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="31a43-348">Vi コマンドモード: `<A>`</span><span class="sxs-lookup"><span data-stu-id="31a43-348">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="31a43-349">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="31a43-349">ViInsertLine</span></span>

<span data-ttu-id="31a43-350">現在の行の上に新しい行が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-350">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="31a43-351">Vi コマンドモード: `<O>`</span><span class="sxs-lookup"><span data-stu-id="31a43-351">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="31a43-352">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="31a43-352">ViInsertWithAppend</span></span>

<span data-ttu-id="31a43-353">現在の行の位置から追加します。</span><span class="sxs-lookup"><span data-stu-id="31a43-353">Append from the current line position.</span></span>

- <span data-ttu-id="31a43-354">Vi コマンドモード: `<a>`</span><span class="sxs-lookup"><span data-stu-id="31a43-354">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="31a43-355">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="31a43-355">ViInsertWithDelete</span></span>

<span data-ttu-id="31a43-356">現在の文字を削除し、挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="31a43-356">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="31a43-357">Vi コマンドモード: `<s>`</span><span class="sxs-lookup"><span data-stu-id="31a43-357">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="31a43-358">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="31a43-358">ViJoinLines</span></span>

<span data-ttu-id="31a43-359">現在の行と次の行を結合します。</span><span class="sxs-lookup"><span data-stu-id="31a43-359">Joins the current line and the next line.</span></span>

- <span data-ttu-id="31a43-360">Vi コマンドモード: `<J>`</span><span class="sxs-lookup"><span data-stu-id="31a43-360">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="31a43-361">交換ライン</span><span class="sxs-lookup"><span data-stu-id="31a43-361">ViReplaceLine</span></span>

<span data-ttu-id="31a43-362">コマンドライン全体を消去します。</span><span class="sxs-lookup"><span data-stu-id="31a43-362">Erase the entire command line.</span></span>

- <span data-ttu-id="31a43-363">Vi コマンドモード: `<S>` 、 `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="31a43-363">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="31a43-364">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="31a43-364">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="31a43-365">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="31a43-365">Replaces until given character.</span></span>

- <span data-ttu-id="31a43-366">Vi コマンドモード: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="31a43-366">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="31a43-367">Vireplacetobeforo</span><span class="sxs-lookup"><span data-stu-id="31a43-367">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="31a43-368">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="31a43-368">Replaces until given character.</span></span>

- <span data-ttu-id="31a43-369">Vi コマンドモード: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="31a43-369">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="31a43-370">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="31a43-370">ViReplaceToChar</span></span>

<span data-ttu-id="31a43-371">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="31a43-371">Deletes until given character.</span></span>

- <span data-ttu-id="31a43-372">Vi コマンドモード: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="31a43-372">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="31a43-373">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="31a43-373">ViReplaceToCharBackward</span></span>

<span data-ttu-id="31a43-374">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="31a43-374">Replaces until given character.</span></span>

- <span data-ttu-id="31a43-375">Vi コマンドモード: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="31a43-375">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="31a43-376">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="31a43-376">ViYankBeginningOfLine</span></span>

<span data-ttu-id="31a43-377">バッファーの先頭からカーソルまで Yank。</span><span class="sxs-lookup"><span data-stu-id="31a43-377">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="31a43-378">Vi コマンドモード: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="31a43-378">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="31a43-379">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="31a43-379">ViYankEndOfGlob</span></span>

<span data-ttu-id="31a43-380">カーソルから単語の末尾まで Yank します。</span><span class="sxs-lookup"><span data-stu-id="31a43-380">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="31a43-381">Vi コマンドモード: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="31a43-381">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="31a43-382">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="31a43-382">ViYankEndOfWord</span></span>

<span data-ttu-id="31a43-383">カーソルから単語の末尾まで Yank します。</span><span class="sxs-lookup"><span data-stu-id="31a43-383">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="31a43-384">Vi コマンドモード: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="31a43-384">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="31a43-385">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="31a43-385">ViYankLeft</span></span>

<span data-ttu-id="31a43-386">カーソルの左側の文字を Yank します。</span><span class="sxs-lookup"><span data-stu-id="31a43-386">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="31a43-387">Vi コマンドモード: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="31a43-387">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="31a43-388">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="31a43-388">ViYankLine</span></span>

<span data-ttu-id="31a43-389">バッファー全体を Yank します。</span><span class="sxs-lookup"><span data-stu-id="31a43-389">Yank the entire buffer.</span></span>

- <span data-ttu-id="31a43-390">Vi コマンドモード: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="31a43-390">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="31a43-391">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="31a43-391">ViYankNextGlob</span></span>

<span data-ttu-id="31a43-392">Yank は、次の単語の先頭にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="31a43-392">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="31a43-393">Vi コマンドモード: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="31a43-393">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="31a43-394">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="31a43-394">ViYankNextWord</span></span>

<span data-ttu-id="31a43-395">カーソルの後の単語を Yank します。</span><span class="sxs-lookup"><span data-stu-id="31a43-395">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="31a43-396">Vi コマンドモード: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="31a43-396">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="31a43-397">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="31a43-397">ViYankPercent</span></span>

<span data-ttu-id="31a43-398">一致する中かっこを Yank します。</span><span class="sxs-lookup"><span data-stu-id="31a43-398">Yank to/from matching brace.</span></span>

- <span data-ttu-id="31a43-399">Vi コマンドモード: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="31a43-399">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="31a43-400">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="31a43-400">ViYankPreviousGlob</span></span>

<span data-ttu-id="31a43-401">Yank は、単語の先頭からカーソルになります。</span><span class="sxs-lookup"><span data-stu-id="31a43-401">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="31a43-402">Vi コマンドモード: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="31a43-402">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="31a43-403">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="31a43-403">ViYankPreviousWord</span></span>

<span data-ttu-id="31a43-404">カーソルの前に単語を Yank します。</span><span class="sxs-lookup"><span data-stu-id="31a43-404">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="31a43-405">Vi コマンドモード: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="31a43-405">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="31a43-406">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="31a43-406">ViYankRight</span></span>

<span data-ttu-id="31a43-407">カーソルの右側に Yank 文字があります。</span><span class="sxs-lookup"><span data-stu-id="31a43-407">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="31a43-408">Vi コマンドモード: `<y,l>` 、 `<y,Space>`</span><span class="sxs-lookup"><span data-stu-id="31a43-408">Vi command mode: `<y,l>`, `<y,Space>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="31a43-409">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="31a43-409">ViYankToEndOfLine</span></span>

<span data-ttu-id="31a43-410">カーソルからバッファーの末尾までの Yank。</span><span class="sxs-lookup"><span data-stu-id="31a43-410">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="31a43-411">Vi コマンドモード: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="31a43-411">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="31a43-412">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="31a43-412">ViYankToFirstChar</span></span>

<span data-ttu-id="31a43-413">最初の空白以外の文字からカーソルまで Yank ます。</span><span class="sxs-lookup"><span data-stu-id="31a43-413">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="31a43-414">Vi コマンドモード: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="31a43-414">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="31a43-415">Yank</span><span class="sxs-lookup"><span data-stu-id="31a43-415">Yank</span></span>

<span data-ttu-id="31a43-416">最後に終了したテキストを入力に追加します。</span><span class="sxs-lookup"><span data-stu-id="31a43-416">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="31a43-417">.Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="31a43-417">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="31a43-418">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="31a43-418">YankLastArg</span></span>

<span data-ttu-id="31a43-419">前の履歴行の最後の引数を Yank します。</span><span class="sxs-lookup"><span data-stu-id="31a43-419">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="31a43-420">引数を使用すると、最初に呼び出されたときに、YankNthArg と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="31a43-420">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="31a43-421">複数回呼び出された場合は、代わりに履歴を反復処理し、引数に方向を設定します (負の方向が反転します)。</span><span class="sxs-lookup"><span data-stu-id="31a43-421">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="31a43-422">コマンド: `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="31a43-422">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="31a43-423">Emacs: `<Alt+.>` 、 `<Alt+_>` 、 `<Escape,.>` 、 `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="31a43-423">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="31a43-424">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="31a43-424">YankNthArg</span></span>

<span data-ttu-id="31a43-425">Yank は、前の履歴行から (コマンドの後に) 最初の引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="31a43-425">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="31a43-426">引数を使用して、n 番目の引数 (0 から始まる) を yank します。引数が負の場合は、最後の引数から開始します。</span><span class="sxs-lookup"><span data-stu-id="31a43-426">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="31a43-427">Emacs: `<Ctrl+Alt+y>` 、 `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="31a43-427">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="31a43-428">YankPop</span><span class="sxs-lookup"><span data-stu-id="31a43-428">YankPop</span></span>

<span data-ttu-id="31a43-429">前の操作が Yank または YankPop であった場合は、以前の引き抜かテキストをキルリングから次に強制終了されたテキストに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="31a43-429">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="31a43-430">Emacs: `<Alt+y>` 、 `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="31a43-430">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="31a43-431">カーソルの移動関数</span><span class="sxs-lookup"><span data-stu-id="31a43-431">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="31a43-432">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="31a43-432">BackwardChar</span></span>

<span data-ttu-id="31a43-433">カーソルを1文字左に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-433">Move the cursor one character to the left.</span></span> <span data-ttu-id="31a43-434">これにより、カーソルが複数行の入力の前の行に移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="31a43-434">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="31a43-435">コマンド: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-435">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="31a43-436">Emacs: `<LeftArrow>` 、 `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="31a43-436">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>
- <span data-ttu-id="31a43-437">Vi の挿入モード: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-437">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="31a43-438">Vi コマンドモード: `<LeftArrow>` 、 `<Backspace>` 、 `<h>`</span><span class="sxs-lookup"><span data-stu-id="31a43-438">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="31a43-439">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="31a43-439">BackwardWord</span></span>

<span data-ttu-id="31a43-440">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-440">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="31a43-441">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-441">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="31a43-442">コマンド: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-442">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="31a43-443">Emacs: `<Alt+b>` 、 `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="31a43-443">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="31a43-444">Vi の挿入モード: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-444">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="31a43-445">Vi コマンドモード: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-445">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="31a43-446">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="31a43-446">BeginningOfLine</span></span>

<span data-ttu-id="31a43-447">入力に複数の行がある場合は、現在の行の先頭に移動します。または、既に行の先頭にある場合は、入力の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-447">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="31a43-448">入力に1行しか含まれていない場合は、入力の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-448">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="31a43-449">コマンド: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="31a43-449">Cmd: `<Home>`</span></span>
- <span data-ttu-id="31a43-450">Emacs: `<Home>` 、 `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="31a43-450">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="31a43-451">Vi の挿入モード: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="31a43-451">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="31a43-452">Vi コマンドモード: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="31a43-452">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="31a43-453">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="31a43-453">EndOfLine</span></span>

<span data-ttu-id="31a43-454">入力に複数の行がある場合は、現在の行の末尾に移動します。または、既に行の末尾にある場合は、入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-454">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="31a43-455">入力に1行しか含まれていない場合は、入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-455">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="31a43-456">コマンド: `<End>`</span><span class="sxs-lookup"><span data-stu-id="31a43-456">Cmd: `<End>`</span></span>
- <span data-ttu-id="31a43-457">Emacs: `<End>` 、 `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="31a43-457">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="31a43-458">Vi の挿入モード: `<End>`</span><span class="sxs-lookup"><span data-stu-id="31a43-458">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="31a43-459">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="31a43-459">ForwardChar</span></span>

<span data-ttu-id="31a43-460">カーソルを1文字右に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-460">Move the cursor one character to the right.</span></span> <span data-ttu-id="31a43-461">これにより、カーソルが複数行入力の次の行に移動する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31a43-461">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="31a43-462">コマンド: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-462">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="31a43-463">Emacs: `<RightArrow>` 、 `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="31a43-463">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>
- <span data-ttu-id="31a43-464">Vi の挿入モード: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-464">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="31a43-465">Vi コマンドモード: `<RightArrow>` 、 `<Space>` 、 `<l>`</span><span class="sxs-lookup"><span data-stu-id="31a43-465">Vi command mode: `<RightArrow>`, `<Space>`, `<l>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="31a43-466">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="31a43-466">ForwardWord</span></span>

<span data-ttu-id="31a43-467">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-467">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="31a43-468">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-468">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="31a43-469">Emacs: `<Alt+f>` 、 `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="31a43-469">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="31a43-470">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="31a43-470">GotoBrace</span></span>

<span data-ttu-id="31a43-471">対応する中かっこ、かっこ、または角かっこにジャンプします。</span><span class="sxs-lookup"><span data-stu-id="31a43-471">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="31a43-472">コマンド: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="31a43-472">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="31a43-473">Vi の挿入モード: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="31a43-473">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="31a43-474">Vi コマンドモード: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="31a43-474">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="31a43-475">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="31a43-475">GotoColumn</span></span>

<span data-ttu-id="31a43-476">Arg で示される列に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-476">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="31a43-477">Vi コマンドモード: `<|>`</span><span class="sxs-lookup"><span data-stu-id="31a43-477">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="31a43-478">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="31a43-478">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="31a43-479">カーソルを行の空白以外の最初の文字に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-479">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="31a43-480">Vi コマンドモード: `<^>`</span><span class="sxs-lookup"><span data-stu-id="31a43-480">Vi command mode: `<^>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="31a43-481">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="31a43-481">MoveToEndOfLine</span></span>

<span data-ttu-id="31a43-482">カーソルを入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-482">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="31a43-483">Vi コマンドモード: `<End>` 、 `<$>`</span><span class="sxs-lookup"><span data-stu-id="31a43-483">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="31a43-484">NextLine</span><span class="sxs-lookup"><span data-stu-id="31a43-484">NextLine</span></span>

<span data-ttu-id="31a43-485">カーソルを次の行に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-485">Move the cursor to the next line.</span></span>

- <span data-ttu-id="31a43-486">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="31a43-486">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="31a43-487">NextWord</span><span class="sxs-lookup"><span data-stu-id="31a43-487">NextWord</span></span>

<span data-ttu-id="31a43-488">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-488">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="31a43-489">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-489">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="31a43-490">コマンド: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-490">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="31a43-491">Vi の挿入モード: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-491">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="31a43-492">Vi コマンドモード: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-492">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="31a43-493">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="31a43-493">NextWordEnd</span></span>

<span data-ttu-id="31a43-494">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-494">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="31a43-495">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-495">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="31a43-496">Vi コマンドモード: `<e>`</span><span class="sxs-lookup"><span data-stu-id="31a43-496">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="31a43-497">前の行</span><span class="sxs-lookup"><span data-stu-id="31a43-497">PreviousLine</span></span>

<span data-ttu-id="31a43-498">カーソルを前の行に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-498">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="31a43-499">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="31a43-499">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="31a43-500">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="31a43-500">ShellBackwardWord</span></span>

<span data-ttu-id="31a43-501">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-501">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="31a43-502">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-502">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="31a43-503">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="31a43-503">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="31a43-504">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="31a43-504">ShellForwardWord</span></span>

<span data-ttu-id="31a43-505">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-505">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="31a43-506">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-506">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="31a43-507">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="31a43-507">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="31a43-508">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="31a43-508">ShellNextWord</span></span>

<span data-ttu-id="31a43-509">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-509">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="31a43-510">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-510">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="31a43-511">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="31a43-511">Function is unbound.</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="31a43-512">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="31a43-512">ViBackwardWord</span></span>

<span data-ttu-id="31a43-513">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-513">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="31a43-514">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-514">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="31a43-515">Vi コマンドモード: `<b>`</span><span class="sxs-lookup"><span data-stu-id="31a43-515">Vi command mode: `<b>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="31a43-516">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="31a43-516">ViEndOfGlob</span></span>

<span data-ttu-id="31a43-517">区切り記号として空白文字のみを使用して、カーソルを単語の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-517">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="31a43-518">Vi コマンドモード: `<E>`</span><span class="sxs-lookup"><span data-stu-id="31a43-518">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="31a43-519">Viendofの Glob</span><span class="sxs-lookup"><span data-stu-id="31a43-519">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="31a43-520">単語区切り記号として空白文字のみを使用して、前の単語の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-520">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="31a43-521">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="31a43-521">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="31a43-522">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="31a43-522">ViGotoBrace</span></span>

<span data-ttu-id="31a43-523">GotoBrace に似ていますが、トークンベースではなく文字ベースです。</span><span class="sxs-lookup"><span data-stu-id="31a43-523">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="31a43-524">Vi コマンドモード: `<%>`</span><span class="sxs-lookup"><span data-stu-id="31a43-524">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="31a43-525">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="31a43-525">ViNextGlob</span></span>

<span data-ttu-id="31a43-526">単語区切り記号として空白文字のみを使用して、次の単語に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-526">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="31a43-527">Vi コマンドモード: `<W>`</span><span class="sxs-lookup"><span data-stu-id="31a43-527">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="31a43-528">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="31a43-528">ViNextWord</span></span>

<span data-ttu-id="31a43-529">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-529">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="31a43-530">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-530">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="31a43-531">Vi コマンドモード: `<w>`</span><span class="sxs-lookup"><span data-stu-id="31a43-531">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="31a43-532">履歴関数</span><span class="sxs-lookup"><span data-stu-id="31a43-532">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="31a43-533">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="31a43-533">BeginningOfHistory</span></span>

<span data-ttu-id="31a43-534">履歴内の最初の項目に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-534">Move to the first item in the history.</span></span>

- <span data-ttu-id="31a43-535">.Emacs `<Alt+`<>\`</span><span class="sxs-lookup"><span data-stu-id="31a43-535">Emacs: `<Alt+`<>\`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="31a43-536">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="31a43-536">ClearHistory</span></span>

<span data-ttu-id="31a43-537">PSReadLine の履歴をクリアします。</span><span class="sxs-lookup"><span data-stu-id="31a43-537">Clears history in PSReadLine.</span></span> <span data-ttu-id="31a43-538">これは、PowerShell の履歴には影響しません。</span><span class="sxs-lookup"><span data-stu-id="31a43-538">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="31a43-539">コマンド: `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="31a43-539">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="31a43-540">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="31a43-540">EndOfHistory</span></span>

<span data-ttu-id="31a43-541">履歴内の最後の項目 (現在の入力) に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-541">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="31a43-542">.Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="31a43-542">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="31a43-543">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="31a43-543">ForwardSearchHistory</span></span>

<span data-ttu-id="31a43-544">履歴を使用した増分転送検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="31a43-544">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="31a43-545">コマンド: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="31a43-545">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="31a43-546">.Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="31a43-546">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="31a43-547">履歴の Search後方</span><span class="sxs-lookup"><span data-stu-id="31a43-547">HistorySearchBackward</span></span>

<span data-ttu-id="31a43-548">現在の入力を、PSReadLine 履歴の ' previous ' 項目で置き換えます。この項目は、開始と入力の間の文字とカーソルの間の文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="31a43-548">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="31a43-549">コマンド: `<F8>`</span><span class="sxs-lookup"><span data-stu-id="31a43-549">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="31a43-550">履歴の Searchforward</span><span class="sxs-lookup"><span data-stu-id="31a43-550">HistorySearchForward</span></span>

<span data-ttu-id="31a43-551">現在の入力を、PSReadLine 履歴の ' next ' 項目で置き換えます。この項目は、開始と入力の間の文字とカーソルの間の文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="31a43-551">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="31a43-552">コマンド: `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="31a43-552">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="31a43-553">NextHistory</span><span class="sxs-lookup"><span data-stu-id="31a43-553">NextHistory</span></span>

<span data-ttu-id="31a43-554">現在の入力を、PSReadLine 履歴の ' next ' 項目に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="31a43-554">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="31a43-555">コマンド: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-555">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="31a43-556">Emacs: `<DownArrow>` 、 `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="31a43-556">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="31a43-557">Vi の挿入モード: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-557">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="31a43-558">Vi コマンドモード: `<DownArrow>` 、 `<j>` 、 `<+>`</span><span class="sxs-lookup"><span data-stu-id="31a43-558">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="31a43-559">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="31a43-559">PreviousHistory</span></span>

<span data-ttu-id="31a43-560">現在の入力を、PSReadLine 履歴の ' previous ' 項目に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="31a43-560">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="31a43-561">コマンド: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-561">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="31a43-562">Emacs: `<UpArrow>` 、 `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="31a43-562">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="31a43-563">Vi の挿入モード: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-563">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="31a43-564">Vi コマンドモード: `<UpArrow>` 、 `<k>` 、 `<->`</span><span class="sxs-lookup"><span data-stu-id="31a43-564">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="31a43-565">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="31a43-565">ReverseSearchHistory</span></span>

<span data-ttu-id="31a43-566">履歴を介して後方検索を段階的に実行します。</span><span class="sxs-lookup"><span data-stu-id="31a43-566">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="31a43-567">コマンド: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="31a43-567">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="31a43-568">.Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="31a43-568">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="31a43-569">Visearchhistory 後方</span><span class="sxs-lookup"><span data-stu-id="31a43-569">ViSearchHistoryBackward</span></span>

<span data-ttu-id="31a43-570">検索文字列を入力し、AcceptLine で検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="31a43-570">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="31a43-571">Vi の挿入モード: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="31a43-571">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="31a43-572">Vi コマンドモード: `</>` 、 `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="31a43-572">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="31a43-573">入力候補関数</span><span class="sxs-lookup"><span data-stu-id="31a43-573">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="31a43-574">完了</span><span class="sxs-lookup"><span data-stu-id="31a43-574">Complete</span></span>

<span data-ttu-id="31a43-575">カーソルを囲むテキストに対して入力候補を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="31a43-575">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="31a43-576">候補が複数ある場合は、最長の明確なプレフィックスを使用して完了します。</span><span class="sxs-lookup"><span data-stu-id="31a43-576">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="31a43-577">最長の明確な完了を完了しようとすると、候補の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-577">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="31a43-578">.Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="31a43-578">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="31a43-579">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="31a43-579">MenuComplete</span></span>

<span data-ttu-id="31a43-580">カーソルを囲むテキストに対して入力候補を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="31a43-580">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="31a43-581">候補が複数ある場合は、最長の明確なプレフィックスを使用して完了します。</span><span class="sxs-lookup"><span data-stu-id="31a43-581">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="31a43-582">最長の明確な完了を完了しようとすると、候補の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-582">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="31a43-583">コマンド: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="31a43-583">Cmd: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="31a43-584">.Emacs `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="31a43-584">Emacs: `<Ctrl+Space>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="31a43-585">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="31a43-585">PossibleCompletions</span></span>

<span data-ttu-id="31a43-586">候補の候補の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="31a43-586">Display the list of possible completions.</span></span>

- <span data-ttu-id="31a43-587">.Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="31a43-587">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="31a43-588">Vi の挿入モード: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="31a43-588">Vi insert mode: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="31a43-589">Vi コマンドモード: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="31a43-589">Vi command mode: `<Ctrl+Space>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="31a43-590">タブのすべてのタブ</span><span class="sxs-lookup"><span data-stu-id="31a43-590">TabCompleteNext</span></span>

<span data-ttu-id="31a43-591">次に使用可能な完了時に、カーソルを囲むテキストを完了します。</span><span class="sxs-lookup"><span data-stu-id="31a43-591">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="31a43-592">コマンド: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="31a43-592">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="31a43-593">Vi コマンドモード: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="31a43-593">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="31a43-594">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="31a43-594">TabCompletePrevious</span></span>

<span data-ttu-id="31a43-595">以前に使用可能な入力候補を使用して、カーソルを囲むテキストを完了しようとしました。</span><span class="sxs-lookup"><span data-stu-id="31a43-595">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="31a43-596">コマンド: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="31a43-596">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="31a43-597">Vi コマンドモード: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="31a43-597">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="31a43-598">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="31a43-598">ViTabCompleteNext</span></span>

<span data-ttu-id="31a43-599">必要に応じて現在の編集グループを終了し、Tabends を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="31a43-599">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="31a43-600">Vi の挿入モード: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="31a43-600">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="31a43-601">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="31a43-601">ViTabCompletePrevious</span></span>

<span data-ttu-id="31a43-602">必要に応じて現在の編集グループを終了し、TabCompletePrevious を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="31a43-602">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="31a43-603">Vi の挿入モード: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="31a43-603">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="31a43-604">その他の関数</span><span class="sxs-lookup"><span data-stu-id="31a43-604">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="31a43-605">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="31a43-605">CaptureScreen</span></span>

<span data-ttu-id="31a43-606">対話型画面のキャプチャを開始する/下矢印行を選択し、[選択したテキストをテキストと html としてクリップボードにコピーする] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="31a43-606">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="31a43-607">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="31a43-607">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="31a43-608">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="31a43-608">ClearScreen</span></span>

<span data-ttu-id="31a43-609">画面をクリアし、画面の上部にある現在の線を描画します。</span><span class="sxs-lookup"><span data-stu-id="31a43-609">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="31a43-610">コマンド: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="31a43-610">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="31a43-611">.Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="31a43-611">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="31a43-612">Vi の挿入モード: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="31a43-612">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="31a43-613">Vi コマンドモード: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="31a43-613">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="31a43-614">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="31a43-614">DigitArgument</span></span>

<span data-ttu-id="31a43-615">他の関数に渡す新しい桁引数を開始します。</span><span class="sxs-lookup"><span data-stu-id="31a43-615">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="31a43-616">Cmd:、、、、、、、、、 `<Alt+0>` `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="31a43-616">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="31a43-617">Emacs:、、、、、、、、、 `<Alt+0>` `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="31a43-617">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="31a43-618">Vi コマンドモード:、、、、、、、、 `<0>` `<1>` `<2>` `<3>` `<4>` `<5>` `<6>` `<7>` `<8>` 、 `<9>`</span><span class="sxs-lookup"><span data-stu-id="31a43-618">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="31a43-619">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="31a43-619">InvokePrompt</span></span>

<span data-ttu-id="31a43-620">現在のプロンプトを消去し、prompt 関数を呼び出してプロンプトを再表示します。</span><span class="sxs-lookup"><span data-stu-id="31a43-620">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="31a43-621">現在のディレクトリを変更するなど、状態を変更するカスタムキーハンドラーに便利です。</span><span class="sxs-lookup"><span data-stu-id="31a43-621">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="31a43-622">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="31a43-622">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="31a43-623">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="31a43-623">ScrollDisplayDown</span></span>

<span data-ttu-id="31a43-624">画面を1画面下へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="31a43-624">Scroll the display down one screen.</span></span>

- <span data-ttu-id="31a43-625">コマンド: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="31a43-625">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="31a43-626">.Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="31a43-626">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="31a43-627">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="31a43-627">ScrollDisplayDownLine</span></span>

<span data-ttu-id="31a43-628">表示を1行下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="31a43-628">Scroll the display down one line.</span></span>

- <span data-ttu-id="31a43-629">コマンド: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="31a43-629">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="31a43-630">.Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="31a43-630">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="31a43-631">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="31a43-631">ScrollDisplayToCursor</span></span>

<span data-ttu-id="31a43-632">カーソルまで画面をスクロールします。</span><span class="sxs-lookup"><span data-stu-id="31a43-632">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="31a43-633">.Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="31a43-633">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="31a43-634">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="31a43-634">ScrollDisplayTop</span></span>

<span data-ttu-id="31a43-635">画面を上にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="31a43-635">Scroll the display to the top.</span></span>

- <span data-ttu-id="31a43-636">.Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="31a43-636">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="31a43-637">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="31a43-637">ScrollDisplayUp</span></span>

<span data-ttu-id="31a43-638">画面を1画面上へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="31a43-638">Scroll the display up one screen.</span></span>

- <span data-ttu-id="31a43-639">コマンド: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="31a43-639">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="31a43-640">.Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="31a43-640">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="31a43-641">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="31a43-641">ScrollDisplayUpLine</span></span>

<span data-ttu-id="31a43-642">表示を1行上へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="31a43-642">Scroll the display up one line.</span></span>

- <span data-ttu-id="31a43-643">コマンド: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="31a43-643">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="31a43-644">.Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="31a43-644">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="31a43-645">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="31a43-645">SelfInsert</span></span>

<span data-ttu-id="31a43-646">キーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="31a43-646">Insert the key.</span></span>

- <span data-ttu-id="31a43-647">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="31a43-647">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="31a43-648">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="31a43-648">ShowKeyBindings</span></span>

<span data-ttu-id="31a43-649">すべてのバインドされたキーを表示します。</span><span class="sxs-lookup"><span data-stu-id="31a43-649">Show all bound keys.</span></span>

- <span data-ttu-id="31a43-650">コマンド: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="31a43-650">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="31a43-651">.Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="31a43-651">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="31a43-652">Vi の挿入モード: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="31a43-652">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="31a43-653">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="31a43-653">ViCommandMode</span></span>

<span data-ttu-id="31a43-654">現在の動作モードを Vi-Insert から Vi-Command に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="31a43-654">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="31a43-655">Vi の挿入モード: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="31a43-655">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="31a43-656">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="31a43-656">ViDigitArgumentInChord</span></span>

<span data-ttu-id="31a43-657">Vi のいずれかの弦で、他の関数に渡す新しい桁引数を開始します。</span><span class="sxs-lookup"><span data-stu-id="31a43-657">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="31a43-658">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="31a43-658">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="31a43-659">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="31a43-659">ViEditVisually</span></span>

<span data-ttu-id="31a43-660">$Env: EDITOR または $env: ビジュアルによって指定されたテキストエディターでコマンドラインを編集します。</span><span class="sxs-lookup"><span data-stu-id="31a43-660">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="31a43-661">.Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="31a43-661">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="31a43-662">Vi コマンドモード: `<v>`</span><span class="sxs-lookup"><span data-stu-id="31a43-662">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="31a43-663">ViExit</span><span class="sxs-lookup"><span data-stu-id="31a43-663">ViExit</span></span>

<span data-ttu-id="31a43-664">シェルを終了します。</span><span class="sxs-lookup"><span data-stu-id="31a43-664">Exits the shell.</span></span>

- <span data-ttu-id="31a43-665">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="31a43-665">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="31a43-666">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="31a43-666">ViInsertMode</span></span>

<span data-ttu-id="31a43-667">挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="31a43-667">Switch to Insert mode.</span></span>

- <span data-ttu-id="31a43-668">Vi コマンドモード: `<i>`</span><span class="sxs-lookup"><span data-stu-id="31a43-668">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="31a43-669">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="31a43-669">WhatIsKey</span></span>

<span data-ttu-id="31a43-670">キーを読み取り、キーがどのようにバインドされているかを通知します。</span><span class="sxs-lookup"><span data-stu-id="31a43-670">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="31a43-671">コマンド: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="31a43-671">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="31a43-672">.Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="31a43-672">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="31a43-673">選択関数</span><span class="sxs-lookup"><span data-stu-id="31a43-673">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="31a43-674">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="31a43-674">ExchangePointAndMark</span></span>

<span data-ttu-id="31a43-675">カーソルがマークの位置に置かれ、マークがカーソルの位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-675">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="31a43-676">.Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="31a43-676">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="31a43-677">SelectAll</span><span class="sxs-lookup"><span data-stu-id="31a43-677">SelectAll</span></span>

<span data-ttu-id="31a43-678">行全体を選択します。</span><span class="sxs-lookup"><span data-stu-id="31a43-678">Select the entire line.</span></span>

- <span data-ttu-id="31a43-679">コマンド: `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="31a43-679">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="31a43-680">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="31a43-680">SelectBackwardChar</span></span>

<span data-ttu-id="31a43-681">現在の選択範囲を調整して、前の文字を含めます。</span><span class="sxs-lookup"><span data-stu-id="31a43-681">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="31a43-682">コマンド: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-682">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="31a43-683">.Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-683">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="31a43-684">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="31a43-684">SelectBackwardsLine</span></span>

<span data-ttu-id="31a43-685">カーソルから行の先頭まで、現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="31a43-685">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="31a43-686">コマンド: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="31a43-686">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="31a43-687">.Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="31a43-687">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="31a43-688">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="31a43-688">SelectBackwardWord</span></span>

<span data-ttu-id="31a43-689">現在の選択範囲を調整して、前の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="31a43-689">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="31a43-690">コマンド: `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-690">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="31a43-691">.Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="31a43-691">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="31a43-692">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="31a43-692">SelectForwardChar</span></span>

<span data-ttu-id="31a43-693">現在の選択範囲を調整して、次の文字を含めます。</span><span class="sxs-lookup"><span data-stu-id="31a43-693">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="31a43-694">コマンド: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-694">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="31a43-695">.Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-695">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="31a43-696">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="31a43-696">SelectForwardWord</span></span>

<span data-ttu-id="31a43-697">現在の選択範囲を調整して、ForwardWord を使用して次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="31a43-697">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="31a43-698">.Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="31a43-698">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="31a43-699">SelectLine</span><span class="sxs-lookup"><span data-stu-id="31a43-699">SelectLine</span></span>

<span data-ttu-id="31a43-700">カーソルから行の末尾まで、現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="31a43-700">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="31a43-701">コマンド: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="31a43-701">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="31a43-702">.Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="31a43-702">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="31a43-703">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="31a43-703">SelectNextWord</span></span>

<span data-ttu-id="31a43-704">現在の選択範囲を調整して、次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="31a43-704">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="31a43-705">コマンド: `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="31a43-705">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="31a43-706">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="31a43-706">SelectShellBackwardWord</span></span>

<span data-ttu-id="31a43-707">ShellBackwardWord を使用して、前の単語が含まれるように現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="31a43-707">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="31a43-708">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="31a43-708">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="31a43-709">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="31a43-709">SelectShellForwardWord</span></span>

<span data-ttu-id="31a43-710">現在の選択範囲を調整して、ShellForwardWord を使用する次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="31a43-710">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="31a43-711">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="31a43-711">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="31a43-712">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="31a43-712">SelectShellNextWord</span></span>

<span data-ttu-id="31a43-713">現在の選択範囲を調整して、ShellNextWord を使用して次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="31a43-713">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="31a43-714">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="31a43-714">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="31a43-715">SetMark</span><span class="sxs-lookup"><span data-stu-id="31a43-715">SetMark</span></span>

<span data-ttu-id="31a43-716">後続の編集コマンドで使用するために、カーソルの現在の位置をマークします。</span><span class="sxs-lookup"><span data-stu-id="31a43-716">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="31a43-717">.Emacs `<Ctrl+`>\`</span><span class="sxs-lookup"><span data-stu-id="31a43-717">Emacs: `<Ctrl+`>\`</span></span>

## <a name="search-functions"></a><span data-ttu-id="31a43-718">関数の検索</span><span class="sxs-lookup"><span data-stu-id="31a43-718">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="31a43-719">文字検索</span><span class="sxs-lookup"><span data-stu-id="31a43-719">CharacterSearch</span></span>

<span data-ttu-id="31a43-720">文字を読み取り、その文字が次に出現するまで検索します。</span><span class="sxs-lookup"><span data-stu-id="31a43-720">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="31a43-721">引数が指定されている場合は、n 番目のオカレンスに対して前方 (負の場合は後方) を検索します。</span><span class="sxs-lookup"><span data-stu-id="31a43-721">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="31a43-722">コマンド: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="31a43-722">Cmd: `<F3>`</span></span>
- <span data-ttu-id="31a43-723">.Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="31a43-723">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="31a43-724">Vi の挿入モード: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="31a43-724">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="31a43-725">Vi コマンドモード: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="31a43-725">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="31a43-726">文字 Search後方</span><span class="sxs-lookup"><span data-stu-id="31a43-726">CharacterSearchBackward</span></span>

<span data-ttu-id="31a43-727">文字を読み取り、その文字が次に出現するまで検索します。</span><span class="sxs-lookup"><span data-stu-id="31a43-727">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="31a43-728">引数が指定されている場合は、n 番目のオカレンスに対して後方 (または負の場合は forward) を検索します。</span><span class="sxs-lookup"><span data-stu-id="31a43-728">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="31a43-729">コマンド: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="31a43-729">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="31a43-730">.Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="31a43-730">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="31a43-731">Vi の挿入モード: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="31a43-731">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="31a43-732">Vi コマンドモード: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="31a43-732">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="31a43-733">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="31a43-733">RepeatLastCharSearch</span></span>

<span data-ttu-id="31a43-734">最後に記録された文字の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="31a43-734">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="31a43-735">Vi コマンドモード: `<;>`</span><span class="sxs-lookup"><span data-stu-id="31a43-735">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="31a43-736">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="31a43-736">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="31a43-737">最後に記録された文字検索を逆方向に繰り返します。</span><span class="sxs-lookup"><span data-stu-id="31a43-737">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="31a43-738">Vi コマンドモード: `<,>`</span><span class="sxs-lookup"><span data-stu-id="31a43-738">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="31a43-739">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="31a43-739">RepeatSearch</span></span>

<span data-ttu-id="31a43-740">前と同じ方向に最後の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="31a43-740">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="31a43-741">Vi コマンドモード: `<n>`</span><span class="sxs-lookup"><span data-stu-id="31a43-741">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="31a43-742">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="31a43-742">RepeatSearchBackward</span></span>

<span data-ttu-id="31a43-743">前と同じ方向に最後の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="31a43-743">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="31a43-744">Vi コマンドモード: `<N>`</span><span class="sxs-lookup"><span data-stu-id="31a43-744">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="31a43-745">SearchChar</span><span class="sxs-lookup"><span data-stu-id="31a43-745">SearchChar</span></span>

<span data-ttu-id="31a43-746">次の文字を読み取って検索し、次に文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="31a43-746">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="31a43-747">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="31a43-747">This is for 't' functionality.</span></span>

- <span data-ttu-id="31a43-748">Vi コマンドモード: `<f>`</span><span class="sxs-lookup"><span data-stu-id="31a43-748">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="31a43-749">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="31a43-749">SearchCharBackward</span></span>

<span data-ttu-id="31a43-750">次の文字を読み取り、それを検索して後方に移動し、次に文字を戻します。</span><span class="sxs-lookup"><span data-stu-id="31a43-750">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="31a43-751">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="31a43-751">This is for 'T' functionality.</span></span>

- <span data-ttu-id="31a43-752">Vi コマンドモード: `<F>`</span><span class="sxs-lookup"><span data-stu-id="31a43-752">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="31a43-753">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="31a43-753">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="31a43-754">次の文字を読み取り、それを検索して後方に移動し、次に文字を戻します。</span><span class="sxs-lookup"><span data-stu-id="31a43-754">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="31a43-755">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="31a43-755">This is for 'T' functionality.</span></span>

- <span data-ttu-id="31a43-756">Vi コマンドモード: `<T>`</span><span class="sxs-lookup"><span data-stu-id="31a43-756">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="31a43-757">SearchCharWithBackoff オフ</span><span class="sxs-lookup"><span data-stu-id="31a43-757">SearchCharWithBackoff</span></span>

<span data-ttu-id="31a43-758">次の文字を読み取って検索し、次に文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="31a43-758">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="31a43-759">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="31a43-759">This is for 't' functionality.</span></span>

- <span data-ttu-id="31a43-760">Vi コマンドモード: `<t>`</span><span class="sxs-lookup"><span data-stu-id="31a43-760">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="31a43-761">SearchForward</span><span class="sxs-lookup"><span data-stu-id="31a43-761">SearchForward</span></span>

<span data-ttu-id="31a43-762">検索文字列を入力し、AcceptLine で検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="31a43-762">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="31a43-763">Vi の挿入モード: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="31a43-763">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="31a43-764">Vi コマンドモード: `<?>` 、 `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="31a43-764">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="31a43-765">カスタムキーバインド</span><span class="sxs-lookup"><span data-stu-id="31a43-765">Custom Key Bindings</span></span>

<span data-ttu-id="31a43-766">PSReadLine は、コマンドレットを使用してカスタムキーバインドをサポートしてい `Set-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="31a43-766">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="31a43-767">ほとんどのカスタムキーバインドは、たとえば、上記の関数の1つを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="31a43-767">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="31a43-768">ScriptBlock をキーにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="31a43-768">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="31a43-769">ScriptBlock は、ほとんどすべてのことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="31a43-769">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="31a43-770">いくつかの便利な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31a43-770">Some useful examples include</span></span>

- <span data-ttu-id="31a43-771">コマンドラインを編集する</span><span class="sxs-lookup"><span data-stu-id="31a43-771">edit the command line</span></span>
- <span data-ttu-id="31a43-772">新しいウィンドウを開く (例: ヘルプ)</span><span class="sxs-lookup"><span data-stu-id="31a43-772">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="31a43-773">コマンドラインを変更せずにディレクトリを変更する</span><span class="sxs-lookup"><span data-stu-id="31a43-773">change directories without changing the command line</span></span>

<span data-ttu-id="31a43-774">ScriptBlock は、次の2つの引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="31a43-774">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="31a43-775">`$key` -カスタムバインドをトリガーしたキーである **[Consolekeyinfo]** オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="31a43-775">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="31a43-776">同じ ScriptBlock を複数のキーにバインドし、キーに応じて異なるアクションを実行する必要がある場合は、$key を確認します。</span><span class="sxs-lookup"><span data-stu-id="31a43-776">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="31a43-777">多くのカスタムバインドでは、この引数は無視します。</span><span class="sxs-lookup"><span data-stu-id="31a43-777">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="31a43-778">`$arg` -任意の引数。</span><span class="sxs-lookup"><span data-stu-id="31a43-778">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="31a43-779">多くの場合、これは、ユーザーがキーバインド DigitArgument から渡す整数引数になります。</span><span class="sxs-lookup"><span data-stu-id="31a43-779">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="31a43-780">バインディングが引数を受け入れない場合は、この引数を無視するのが妥当です。</span><span class="sxs-lookup"><span data-stu-id="31a43-780">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="31a43-781">ここでは、コマンドラインを実行せずに履歴に追加する例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="31a43-781">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="31a43-782">これは、何らかの操作を忘れた場合に、既に入力したコマンドラインを再入力したくない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="31a43-782">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="31a43-783">PSReadLine モジュールフォルダーにインストールされているファイルには、さらに多くの例が表示 `SamplePSReadLineProfile.ps1` されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-783">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="31a43-784">ほとんどのキーバインドでは、コマンドラインを編集するためにいくつかのヘルパー関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="31a43-784">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="31a43-785">これらの Api については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="31a43-785">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="31a43-786">カスタムキーバインディングサポート Api</span><span class="sxs-lookup"><span data-stu-id="31a43-786">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="31a43-787">次の関数は PSConsoleReadLine では公開されていますが、キーに直接バインドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="31a43-787">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="31a43-788">多くの場合、カスタムキーバインドに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="31a43-788">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="31a43-789">コマンドラインを実行せずに、履歴に追加します。</span><span class="sxs-lookup"><span data-stu-id="31a43-789">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="31a43-790">Kill リングをクリアします。</span><span class="sxs-lookup"><span data-stu-id="31a43-790">Clear the kill-ring.</span></span>  <span data-ttu-id="31a43-791">これは主にテストに使用されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-791">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="31a43-792">先頭から長さの文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="31a43-792">Delete length characters from start.</span></span>  <span data-ttu-id="31a43-793">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="31a43-793">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="31a43-794">ユーザー設定に基づいてアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="31a43-794">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="31a43-795">これらの2つの関数は、入力バッファーの現在の状態に関する有用な情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="31a43-795">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="31a43-796">1つ目は、単純なケースでよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-796">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="31a43-797">2つ目は、バインディングが Ast を使用してより高度な処理を実行している場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-797">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

```

<span data-ttu-id="31a43-798">この関数は Get-PSReadLineKeyHandler によって使用され、カスタムキーバインドでは役に立たない場合があります。</span><span class="sxs-lookup"><span data-stu-id="31a43-798">This function is used by Get-PSReadLineKeyHandler and probably isn't useful in a custom key binding.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="31a43-799">この関数は Get-PSReadLineOption によって使用され、カスタムキーバインドではあまり役に立たない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31a43-799">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="31a43-800">コマンドラインに何も選択されていない場合は、開始と長さの両方で-1 が返されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-800">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="31a43-801">コマンドラインに選択項目がある場合は、選択範囲の先頭と長さが返されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-801">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="31a43-802">カーソル位置に文字または文字列を挿入します。</span><span class="sxs-lookup"><span data-stu-id="31a43-802">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="31a43-803">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="31a43-803">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="31a43-804">これは、PSReadLine へのメインエントリポイントです。</span><span class="sxs-lookup"><span data-stu-id="31a43-804">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="31a43-805">再帰はサポートされないため、カスタムキーバインドでは役に立ちません。</span><span class="sxs-lookup"><span data-stu-id="31a43-805">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="31a43-806">この関数は Remove-PSReadLineKeyHandler によって使用され、カスタムキーバインドではあまり役に立たない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31a43-806">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="31a43-807">入力の一部を置換します。</span><span class="sxs-lookup"><span data-stu-id="31a43-807">Replace some of the input.</span></span> <span data-ttu-id="31a43-808">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="31a43-808">This operation supports undo/redo.</span></span> <span data-ttu-id="31a43-809">これは、undo の単一のアクションとして扱われるため、Delete の後に Insert を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="31a43-809">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="31a43-810">カーソルを指定されたオフセットに移動します。</span><span class="sxs-lookup"><span data-stu-id="31a43-810">Move the cursor to the given offset.</span></span> <span data-ttu-id="31a43-811">カーソルの移動は、元に戻すために追跡されません。</span><span class="sxs-lookup"><span data-stu-id="31a43-811">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="31a43-812">この関数は、コマンドレットの設定-PSReadLineOption によって使用されるヘルパーメソッドですが、一時的に設定を変更する必要があるカスタムキーバインドに便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="31a43-812">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="31a43-813">このヘルパーメソッドは、DigitArgument を優先するカスタムバインドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-813">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="31a43-814">一般的な呼び出しは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="31a43-814">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="31a43-815">注意</span><span class="sxs-lookup"><span data-stu-id="31a43-815">Note</span></span>

### <a name="command-history"></a><span data-ttu-id="31a43-816">コマンド履歴</span><span class="sxs-lookup"><span data-stu-id="31a43-816">Command History</span></span>

<span data-ttu-id="31a43-817">PSReadLine は、コマンドラインから入力したすべてのコマンドとデータを含む履歴ファイルを保持します。</span><span class="sxs-lookup"><span data-stu-id="31a43-817">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="31a43-818">これには、パスワードなどの機密データが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="31a43-818">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="31a43-819">たとえば、コマンドレットを使用した場合、 `ConvertTo-SecureString` パスワードはプレーンテキストとして履歴ファイルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="31a43-819">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="31a43-820">履歴ファイルは、という名前のファイルです `$($host.Name)_history.txt` 。</span><span class="sxs-lookup"><span data-stu-id="31a43-820">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="31a43-821">Windows システムでは、履歴ファイルはに格納され `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` ます。</span><span class="sxs-lookup"><span data-stu-id="31a43-821">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="31a43-822">PSReadLine に貢献しているフィードバック &</span><span class="sxs-lookup"><span data-stu-id="31a43-822">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="31a43-823">GitHub の PSReadLine</span><span class="sxs-lookup"><span data-stu-id="31a43-823">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="31a43-824">プル要求を送信したり、GitHub ページでフィードバックを送信したりしてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="31a43-824">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="31a43-825">参照</span><span class="sxs-lookup"><span data-stu-id="31a43-825">See Also</span></span>

<span data-ttu-id="31a43-826">PSReadLine は、GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) ライブラリの影響を強く受けます。</span><span class="sxs-lookup"><span data-stu-id="31a43-826">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
