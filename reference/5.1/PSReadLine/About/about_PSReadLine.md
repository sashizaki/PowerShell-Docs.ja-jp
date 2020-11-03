---
description: PSReadLine では、PowerShell コンソールでのコマンドライン編集エクスペリエンスが向上しています。
keywords: powershell
Locale: en-US
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: PSReadLine について
ms.openlocfilehash: ad6e85a30f866cb332c89a4c36f42231f511f5ae
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224920"
---
# <a name="psreadline"></a><span data-ttu-id="eb7f0-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="eb7f0-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="eb7f0-106">概要</span><span class="sxs-lookup"><span data-stu-id="eb7f0-106">SHORT DESCRIPTION</span></span>

<span data-ttu-id="eb7f0-107">PSReadLine では、PowerShell コンソールでのコマンドライン編集エクスペリエンスが向上しています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="eb7f0-108">詳細説明</span><span class="sxs-lookup"><span data-stu-id="eb7f0-108">LONG DESCRIPTION</span></span>

<span data-ttu-id="eb7f0-109">PSReadLine 2.0 では、PowerShell コンソールの強力なコマンドライン編集エクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="eb7f0-110">次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-110">It provides:</span></span>

- <span data-ttu-id="eb7f0-111">コマンドラインの構文の色分け</span><span class="sxs-lookup"><span data-stu-id="eb7f0-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="eb7f0-112">構文エラーを視覚的に示します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="eb7f0-113">より優れたマルチラインエクスペリエンス (編集と履歴の両方)</span><span class="sxs-lookup"><span data-stu-id="eb7f0-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="eb7f0-114">カスタマイズ可能なキーバインド</span><span class="sxs-lookup"><span data-stu-id="eb7f0-114">Customizable key bindings</span></span>
- <span data-ttu-id="eb7f0-115">Cmd モードと Emacs モード</span><span class="sxs-lookup"><span data-stu-id="eb7f0-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="eb7f0-116">多くの構成オプション</span><span class="sxs-lookup"><span data-stu-id="eb7f0-116">Many configuration options</span></span>
- <span data-ttu-id="eb7f0-117">Bash スタイル補完 (Cmd モードでは省略可能、Emacs モードでは既定)</span><span class="sxs-lookup"><span data-stu-id="eb7f0-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="eb7f0-118">Emacs yank/kill-リング</span><span class="sxs-lookup"><span data-stu-id="eb7f0-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="eb7f0-119">PowerShell トークンベースの "word" の移動と強制終了</span><span class="sxs-lookup"><span data-stu-id="eb7f0-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="eb7f0-120">クラス **[PSConsoleReadLine]** では、次の関数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-120">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="eb7f0-121">基本的な編集関数</span><span class="sxs-lookup"><span data-stu-id="eb7f0-121">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="eb7f0-122">中止</span><span class="sxs-lookup"><span data-stu-id="eb7f0-122">Abort</span></span>

<span data-ttu-id="eb7f0-123">現在のアクション (増分履歴検索など) を中止します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-123">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="eb7f0-124">.Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-124">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="eb7f0-125">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="eb7f0-125">AcceptAndGetNext</span></span>

<span data-ttu-id="eb7f0-126">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-126">Attempt to execute the current input.</span></span> <span data-ttu-id="eb7f0-127">(AcceptLine など) 実行できる場合は、次に ReadLine が呼び出されたときに履歴から次の項目を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-127">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="eb7f0-128">.Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-128">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="eb7f0-129">AcceptLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-129">AcceptLine</span></span>

<span data-ttu-id="eb7f0-130">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-130">Attempt to execute the current input.</span></span> <span data-ttu-id="eb7f0-131">現在の入力が不完全な場合 (たとえば、終わりかっこ、角かっこ、または引用符がない場合)、継続のプロンプトは次の行に表示され、PSReadLine は現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-131">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="eb7f0-132">コマンド: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-132">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="eb7f0-133">.Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-133">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="eb7f0-134">Vi の挿入モード: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-134">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="eb7f0-135">AddLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-135">AddLine</span></span>

<span data-ttu-id="eb7f0-136">継続プロンプトが次の行に表示され、PSReadLine が現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-136">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="eb7f0-137">これは、単一行が単独で完全に入力されている場合でも、複数行の入力を1つのコマンドとして入力する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-137">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="eb7f0-138">コマンド: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-138">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="eb7f0-139">.Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-139">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="eb7f0-140">Vi の挿入モード: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-140">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="eb7f0-141">Vi コマンドモード: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-141">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="eb7f0-142">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="eb7f0-142">BackwardDeleteChar</span></span>

<span data-ttu-id="eb7f0-143">カーソルの前の文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-143">Delete the character before the cursor.</span></span>

- <span data-ttu-id="eb7f0-144">Cmd: `<Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-144">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="eb7f0-145">Emacs: `<Backspace>` 、 `<Ctrl+Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-145">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="eb7f0-146">Vi の挿入モード: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-146">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="eb7f0-147">Vi コマンドモード: `<X>` 、 `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-147">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="eb7f0-148">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-148">BackwardDeleteLine</span></span>

<span data-ttu-id="eb7f0-149">Like BackwardKillLine-行の先頭から先頭までのテキストを削除しますが、削除されたテキストはキルリングには挿入されません。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-149">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="eb7f0-150">コマンド: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-150">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="eb7f0-151">Vi 挿入モード: `<Ctrl+u>` 、 `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-151">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="eb7f0-152">Vi コマンドモード: `<Ctrl+u>` 、 `<Ctrl+Home>` 、 `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-152">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="eb7f0-153">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-153">BackwardDeleteWord</span></span>

<span data-ttu-id="eb7f0-154">前の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-154">Deletes the previous word.</span></span>

- <span data-ttu-id="eb7f0-155">Vi コマンドモード: `<Ctrl+w>` 、 `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-155">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="eb7f0-156">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-156">BackwardKillLine</span></span>

<span data-ttu-id="eb7f0-157">入力の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-157">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="eb7f0-158">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-158">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="eb7f0-159">Emacs: `<Ctrl+u>` 、 `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-159">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="eb7f0-160">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-160">BackwardKillWord</span></span>

<span data-ttu-id="eb7f0-161">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-161">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="eb7f0-162">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-162">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="eb7f0-163">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-163">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="eb7f0-164">コマンド: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-164">Cmd: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="eb7f0-165">Emacs: `<Alt+Backspace>` 、 `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-165">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="eb7f0-166">Vi の挿入モード: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-166">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="eb7f0-167">Vi コマンドモード: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-167">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="eb7f0-168">CancelLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-168">CancelLine</span></span>

<span data-ttu-id="eb7f0-169">入力を画面に残したまま、現在の入力を取り消しますが、プロンプトが再び評価されるように、ホストに戻ります。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-169">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="eb7f0-170">Vi の挿入モード: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-170">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="eb7f0-171">Vi コマンドモード: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-171">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="eb7f0-172">コピー</span><span class="sxs-lookup"><span data-stu-id="eb7f0-172">Copy</span></span>

<span data-ttu-id="eb7f0-173">選択したリージョンをシステムクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-173">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="eb7f0-174">領域が選択されていない場合は、行全体をコピーします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-174">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="eb7f0-175">コマンド: `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-175">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="eb7f0-176">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-176">CopyOrCancelLine</span></span>

<span data-ttu-id="eb7f0-177">テキストが選択されている場合は、クリップボードにコピーします。それ以外の場合は、行をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-177">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="eb7f0-178">コマンド: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-178">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="eb7f0-179">.Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-179">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="eb7f0-180">切り取り</span><span class="sxs-lookup"><span data-stu-id="eb7f0-180">Cut</span></span>

<span data-ttu-id="eb7f0-181">削除されたテキストをシステムクリップボードに配置した、選択した領域を削除します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-181">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="eb7f0-182">コマンド: `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-182">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="eb7f0-183">Dele</span><span class="sxs-lookup"><span data-stu-id="eb7f0-183">DeleteChar</span></span>

<span data-ttu-id="eb7f0-184">カーソルの下の文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-184">Delete the character under the cursor.</span></span>

- <span data-ttu-id="eb7f0-185">コマンド: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-185">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="eb7f0-186">.Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-186">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="eb7f0-187">Vi の挿入モード: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-187">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="eb7f0-188">Vi コマンドモード: `<Delete>` 、 `<x>` 、 `<d,l>` 、 `<d,Space>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-188">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Space>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="eb7f0-189">Deleの Arorexit</span><span class="sxs-lookup"><span data-stu-id="eb7f0-189">DeleteCharOrExit</span></span>

<span data-ttu-id="eb7f0-190">カーソルの下の文字を削除するか、行が空の場合はプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-190">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="eb7f0-191">.Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-191">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="eb7f0-192">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-192">DeleteEndOfWord</span></span>

<span data-ttu-id="eb7f0-193">単語の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-193">Delete to the end of the word.</span></span>

- <span data-ttu-id="eb7f0-194">Vi コマンドモード: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-194">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="eb7f0-195">Deleteline.invoke に</span><span class="sxs-lookup"><span data-stu-id="eb7f0-195">DeleteLine</span></span>

<span data-ttu-id="eb7f0-196">現在の行を削除して、元に戻す操作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-196">Deletes the current line, enabling undo.</span></span>

- <span data-ttu-id="eb7f0-197">Vi コマンドモード: `<d,d>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-197">Vi command mode: `<d,d>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="eb7f0-198">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="eb7f0-198">DeleteLineToFirstChar</span></span>

<span data-ttu-id="eb7f0-199">カーソルから、行の最初の空白以外の文字までのテキストを削除します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-199">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="eb7f0-200">Vi コマンドモード: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-200">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="eb7f0-201">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="eb7f0-201">DeleteToEnd</span></span>

<span data-ttu-id="eb7f0-202">行の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-202">Delete to the end of the line.</span></span>

- <span data-ttu-id="eb7f0-203">Vi コマンドモード: `<D>` 、 `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-203">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="eb7f0-204">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-204">DeleteWord</span></span>

<span data-ttu-id="eb7f0-205">次の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-205">Delete the next word.</span></span>

- <span data-ttu-id="eb7f0-206">Vi コマンドモード: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-206">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="eb7f0-207">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-207">ForwardDeleteLine</span></span>

<span data-ttu-id="eb7f0-208">同じように、Forwardは、行の末尾から最後までのテキストを削除しますが、削除されたテキストはキルリングには挿入されません。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-208">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="eb7f0-209">コマンド: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-209">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="eb7f0-210">Vi の挿入モード: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-210">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="eb7f0-211">Vi コマンドモード: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-211">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="eb7f0-212">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="eb7f0-212">InsertLineAbove</span></span>

<span data-ttu-id="eb7f0-213">現在の行の上にカーソルがある場所に関係なく、現在の行の上に新しい空の行が作成されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-213">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="eb7f0-214">カーソルが新しい行の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-214">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="eb7f0-215">コマンド: `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-215">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="eb7f0-216">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="eb7f0-216">InsertLineBelow</span></span>

<span data-ttu-id="eb7f0-217">カーソルが現在の行にある場所に関係なく、現在の行の下に新しい空の行が作成されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-217">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="eb7f0-218">カーソルが新しい行の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-218">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="eb7f0-219">コマンド: `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-219">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="eb7f0-220">InvertCase</span><span class="sxs-lookup"><span data-stu-id="eb7f0-220">InvertCase</span></span>

<span data-ttu-id="eb7f0-221">現在の文字の大文字と小文字の区別を反転し、次の文字に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-221">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="eb7f0-222">Vi コマンドモード: `<~>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-222">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="eb7f0-223">行の行</span><span class="sxs-lookup"><span data-stu-id="eb7f0-223">KillLine</span></span>

<span data-ttu-id="eb7f0-224">カーソルから入力の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-224">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="eb7f0-225">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-225">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="eb7f0-226">.Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-226">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="eb7f0-227">"/" 領域</span><span class="sxs-lookup"><span data-stu-id="eb7f0-227">KillRegion</span></span>

<span data-ttu-id="eb7f0-228">カーソルとマークの間のテキストを強制終了します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-228">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="eb7f0-229">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-229">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="eb7f0-230">文字の候補</span><span class="sxs-lookup"><span data-stu-id="eb7f0-230">KillWord</span></span>

<span data-ttu-id="eb7f0-231">カーソルから現在の単語の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-231">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="eb7f0-232">カーソルが単語の間にある場合は、カーソルから次の単語の末尾まで、入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-232">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="eb7f0-233">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-233">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="eb7f0-234">コマンド: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-234">Cmd: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="eb7f0-235">Emacs: `<Alt+d>` 、 `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-235">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="eb7f0-236">Vi の挿入モード: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-236">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="eb7f0-237">Vi コマンドモード: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-237">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="eb7f0-238">貼り付け</span><span class="sxs-lookup"><span data-stu-id="eb7f0-238">Paste</span></span>

<span data-ttu-id="eb7f0-239">システムクリップボードからテキストを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-239">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="eb7f0-240">Cmd: `<Ctrl+v>` 、 `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-240">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="eb7f0-241">Vi の挿入モード: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-241">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="eb7f0-242">Vi コマンドモード: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-242">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb7f0-243">**貼り付け** 関数を使用すると、クリップボードバッファーの内容全体が psreadline の入力バッファーに貼り付けられます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-243">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="eb7f0-244">入力バッファーが PowerShell パーサーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-244">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="eb7f0-245">コンソールアプリケーションの **右クリック** による貼り付けメソッドを使用して貼り付けた入力は、一度に1文字ずつ入力バッファーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-245">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="eb7f0-246">入力バッファーは、改行文字がコピーされるときにパーサーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-246">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="eb7f0-247">そのため、入力は一度に1行ずつ解析されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-247">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="eb7f0-248">貼り付けメソッドの違いによって、実行の動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-248">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="eb7f0-249">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="eb7f0-249">PasteAfter</span></span>

<span data-ttu-id="eb7f0-250">カーソルの後にクリップボードを貼り付けて、貼り付けられたテキストの末尾にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-250">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="eb7f0-251">Vi コマンドモード: `<p>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-251">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="eb7f0-252">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="eb7f0-252">PasteBefore</span></span>

<span data-ttu-id="eb7f0-253">カーソルの前にクリップボードを貼り付けて、貼り付けられたテキストの末尾にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-253">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="eb7f0-254">Vi コマンドモード: `<P>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-254">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="eb7f0-255">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="eb7f0-255">PrependAndAccept</span></span>

<span data-ttu-id="eb7f0-256">' # ' を先頭に付加し、その行を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-256">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="eb7f0-257">Vi コマンドモード: `<#>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-257">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="eb7f0-258">やり直し</span><span class="sxs-lookup"><span data-stu-id="eb7f0-258">Redo</span></span>

<span data-ttu-id="eb7f0-259">元に戻す操作を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-259">Undo an undo.</span></span>

- <span data-ttu-id="eb7f0-260">コマンド: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-260">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="eb7f0-261">Vi の挿入モード: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-261">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="eb7f0-262">Vi コマンドモード: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-262">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="eb7f0-263">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="eb7f0-263">RepeatLastCommand</span></span>

<span data-ttu-id="eb7f0-264">最後のテキストの変更を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-264">Repeat the last text modification.</span></span>

- <span data-ttu-id="eb7f0-265">Vi コマンドモード: `<.>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-265">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="eb7f0-266">再有効化</span><span class="sxs-lookup"><span data-stu-id="eb7f0-266">RevertLine</span></span>

<span data-ttu-id="eb7f0-267">すべての入力を現在の入力に戻します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-267">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="eb7f0-268">コマンド: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-268">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="eb7f0-269">Emacs: `<Alt+r>` 、 `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-269">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="eb7f0-270">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-270">ShellBackwardKillWord</span></span>

<span data-ttu-id="eb7f0-271">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-271">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="eb7f0-272">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-272">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="eb7f0-273">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-273">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="eb7f0-274">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-274">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="eb7f0-275">Shellは Word</span><span class="sxs-lookup"><span data-stu-id="eb7f0-275">ShellKillWord</span></span>

<span data-ttu-id="eb7f0-276">カーソルから現在の単語の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-276">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="eb7f0-277">カーソルが単語の間にある場合は、カーソルから次の単語の末尾まで、入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-277">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="eb7f0-278">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-278">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="eb7f0-279">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-279">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="eb7f0-280">スワップ文字</span><span class="sxs-lookup"><span data-stu-id="eb7f0-280">SwapCharacters</span></span>

<span data-ttu-id="eb7f0-281">現在の文字とそれより前の文字を交換します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-281">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="eb7f0-282">.Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-282">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="eb7f0-283">Vi の挿入モード: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-283">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="eb7f0-284">Vi コマンドモード: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-284">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="eb7f0-285">元に戻す</span><span class="sxs-lookup"><span data-stu-id="eb7f0-285">Undo</span></span>

<span data-ttu-id="eb7f0-286">前の編集を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-286">Undo a previous edit.</span></span>

- <span data-ttu-id="eb7f0-287">コマンド: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-287">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="eb7f0-288">Emacs: `<Ctrl+_>` 、 `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-288">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="eb7f0-289">Vi の挿入モード: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-289">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="eb7f0-290">Vi コマンドモード: `<Ctrl+z>` 、 `<u>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-290">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="eb7f0-291">UndoAll</span><span class="sxs-lookup"><span data-stu-id="eb7f0-291">UndoAll</span></span>

<span data-ttu-id="eb7f0-292">行の以前の編集をすべて元に戻します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-292">Undo all previous edits for line.</span></span>

- <span data-ttu-id="eb7f0-293">Vi コマンドモード: `<U>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-293">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="eb7f0-294">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="eb7f0-294">UnixWordRubout</span></span>

<span data-ttu-id="eb7f0-295">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-295">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="eb7f0-296">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-296">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="eb7f0-297">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-297">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="eb7f0-298">.Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-298">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="eb7f0-299">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-299">ValidateAndAcceptLine</span></span>

<span data-ttu-id="eb7f0-300">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-300">Attempt to execute the current input.</span></span> <span data-ttu-id="eb7f0-301">現在の入力が不完全な場合 (たとえば、終わりかっこ、角かっこ、または引用符がない場合)、継続のプロンプトは次の行に表示され、PSReadLine は現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-301">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="eb7f0-302">.Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-302">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="eb7f0-303">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-303">ViAcceptLine</span></span>

<span data-ttu-id="eb7f0-304">行を受け入れ、挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-304">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="eb7f0-305">Vi コマンドモード: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-305">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="eb7f0-306">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="eb7f0-306">ViAcceptLineOrExit</span></span>

<span data-ttu-id="eb7f0-307">(Emacs モードでは Deleと同じですが、文字を削除するのではなく、行を受け取ります)。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-307">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="eb7f0-308">Vi の挿入モード: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-308">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="eb7f0-309">Vi コマンドモード: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-309">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="eb7f0-310">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-310">ViAppendLine</span></span>

<span data-ttu-id="eb7f0-311">現在の行の下に新しい行が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-311">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="eb7f0-312">Vi コマンドモード: `<o>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-312">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="eb7f0-313">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="eb7f0-313">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="eb7f0-314">単語区切り記号として空白文字のみを使用して、前の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-314">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="eb7f0-315">Vi コマンドモード: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-315">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="eb7f0-316">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="eb7f0-316">ViBackwardGlob</span></span>

<span data-ttu-id="eb7f0-317">区切り記号として空白文字のみを使用して、カーソルを前の単語の先頭に戻します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-317">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="eb7f0-318">Vi コマンドモード: `<B>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-318">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="eb7f0-319">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="eb7f0-319">ViDeleteBrace</span></span>

<span data-ttu-id="eb7f0-320">対応する中かっこ、かっこ、または角かっこを検索し、中かっこを含め、内のすべての内容を削除します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-320">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="eb7f0-321">Vi コマンドモード: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-321">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="eb7f0-322">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="eb7f0-322">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="eb7f0-323">単語の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-323">Delete to the end of the word.</span></span>

- <span data-ttu-id="eb7f0-324">Vi コマンドモード: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-324">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="eb7f0-325">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="eb7f0-325">ViDeleteGlob</span></span>

<span data-ttu-id="eb7f0-326">次の glob (空白で区切られた単語) を削除します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-326">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="eb7f0-327">Vi コマンドモード: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-327">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="eb7f0-328">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="eb7f0-328">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="eb7f0-329">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-329">Deletes until given character.</span></span>

- <span data-ttu-id="eb7f0-330">Vi コマンドモード: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-330">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="eb7f0-331">Videletetobeforo</span><span class="sxs-lookup"><span data-stu-id="eb7f0-331">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="eb7f0-332">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-332">Deletes until given character.</span></span>

- <span data-ttu-id="eb7f0-333">Vi コマンドモード: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-333">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="eb7f0-334">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="eb7f0-334">ViDeleteToChar</span></span>

<span data-ttu-id="eb7f0-335">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-335">Deletes until given character.</span></span>

- <span data-ttu-id="eb7f0-336">Vi コマンドモード: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-336">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="eb7f0-337">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="eb7f0-337">ViDeleteToCharBackward</span></span>

<span data-ttu-id="eb7f0-338">指定された文字まで後方を削除します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-338">Deletes backwards until given character.</span></span>

- <span data-ttu-id="eb7f0-339">Vi コマンドモード: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-339">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="eb7f0-340">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="eb7f0-340">ViInsertAtBegining</span></span>

<span data-ttu-id="eb7f0-341">挿入モードに切り替え、カーソルを行の先頭に配置します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-341">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="eb7f0-342">Vi コマンドモード: `<I>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-342">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="eb7f0-343">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="eb7f0-343">ViInsertAtEnd</span></span>

<span data-ttu-id="eb7f0-344">挿入モードに切り替え、カーソルを行の末尾に配置します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-344">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="eb7f0-345">Vi コマンドモード: `<A>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-345">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="eb7f0-346">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-346">ViInsertLine</span></span>

<span data-ttu-id="eb7f0-347">現在の行の上に新しい行が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-347">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="eb7f0-348">Vi コマンドモード: `<O>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-348">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="eb7f0-349">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="eb7f0-349">ViInsertWithAppend</span></span>

<span data-ttu-id="eb7f0-350">現在の行の位置から追加します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-350">Append from the current line position.</span></span>

- <span data-ttu-id="eb7f0-351">Vi コマンドモード: `<a>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-351">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="eb7f0-352">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="eb7f0-352">ViInsertWithDelete</span></span>

<span data-ttu-id="eb7f0-353">現在の文字を削除し、挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-353">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="eb7f0-354">Vi コマンドモード: `<s>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-354">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="eb7f0-355">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="eb7f0-355">ViJoinLines</span></span>

<span data-ttu-id="eb7f0-356">現在の行と次の行を結合します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-356">Joins the current line and the next line.</span></span>

- <span data-ttu-id="eb7f0-357">Vi コマンドモード: `<J>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-357">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="eb7f0-358">交換ライン</span><span class="sxs-lookup"><span data-stu-id="eb7f0-358">ViReplaceLine</span></span>

<span data-ttu-id="eb7f0-359">コマンドライン全体を消去します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-359">Erase the entire command line.</span></span>

- <span data-ttu-id="eb7f0-360">Vi コマンドモード: `<S>` 、 `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-360">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="eb7f0-361">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="eb7f0-361">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="eb7f0-362">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-362">Replaces until given character.</span></span>

- <span data-ttu-id="eb7f0-363">Vi コマンドモード: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-363">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="eb7f0-364">Vireplacetobeforo</span><span class="sxs-lookup"><span data-stu-id="eb7f0-364">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="eb7f0-365">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-365">Replaces until given character.</span></span>

- <span data-ttu-id="eb7f0-366">Vi コマンドモード: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-366">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="eb7f0-367">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="eb7f0-367">ViReplaceToChar</span></span>

<span data-ttu-id="eb7f0-368">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-368">Deletes until given character.</span></span>

- <span data-ttu-id="eb7f0-369">Vi コマンドモード: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-369">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="eb7f0-370">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="eb7f0-370">ViReplaceToCharBackward</span></span>

<span data-ttu-id="eb7f0-371">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-371">Replaces until given character.</span></span>

- <span data-ttu-id="eb7f0-372">Vi コマンドモード: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-372">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="eb7f0-373">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-373">ViYankBeginningOfLine</span></span>

<span data-ttu-id="eb7f0-374">バッファーの先頭からカーソルまで Yank。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-374">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="eb7f0-375">Vi コマンドモード: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-375">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="eb7f0-376">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="eb7f0-376">ViYankEndOfGlob</span></span>

<span data-ttu-id="eb7f0-377">カーソルから単語の末尾まで Yank します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-377">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="eb7f0-378">Vi コマンドモード: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-378">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="eb7f0-379">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-379">ViYankEndOfWord</span></span>

<span data-ttu-id="eb7f0-380">カーソルから単語の末尾まで Yank します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-380">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="eb7f0-381">Vi コマンドモード: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-381">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="eb7f0-382">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="eb7f0-382">ViYankLeft</span></span>

<span data-ttu-id="eb7f0-383">カーソルの左側の文字を Yank します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-383">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="eb7f0-384">Vi コマンドモード: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-384">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="eb7f0-385">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-385">ViYankLine</span></span>

<span data-ttu-id="eb7f0-386">バッファー全体を Yank します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-386">Yank the entire buffer.</span></span>

- <span data-ttu-id="eb7f0-387">Vi コマンドモード: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-387">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="eb7f0-388">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="eb7f0-388">ViYankNextGlob</span></span>

<span data-ttu-id="eb7f0-389">Yank は、次の単語の先頭にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-389">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="eb7f0-390">Vi コマンドモード: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-390">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="eb7f0-391">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-391">ViYankNextWord</span></span>

<span data-ttu-id="eb7f0-392">カーソルの後の単語を Yank します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-392">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="eb7f0-393">Vi コマンドモード: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-393">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="eb7f0-394">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="eb7f0-394">ViYankPercent</span></span>

<span data-ttu-id="eb7f0-395">一致する中かっこを Yank します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-395">Yank to/from matching brace.</span></span>

- <span data-ttu-id="eb7f0-396">Vi コマンドモード: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-396">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="eb7f0-397">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="eb7f0-397">ViYankPreviousGlob</span></span>

<span data-ttu-id="eb7f0-398">Yank は、単語の先頭からカーソルになります。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-398">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="eb7f0-399">Vi コマンドモード: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-399">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="eb7f0-400">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-400">ViYankPreviousWord</span></span>

<span data-ttu-id="eb7f0-401">カーソルの前に単語を Yank します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-401">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="eb7f0-402">Vi コマンドモード: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-402">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="eb7f0-403">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="eb7f0-403">ViYankRight</span></span>

<span data-ttu-id="eb7f0-404">カーソルの右側に Yank 文字があります。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-404">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="eb7f0-405">Vi コマンドモード: `<y,l>` 、 `<y,Space>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-405">Vi command mode: `<y,l>`, `<y,Space>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="eb7f0-406">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-406">ViYankToEndOfLine</span></span>

<span data-ttu-id="eb7f0-407">カーソルからバッファーの末尾までの Yank。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-407">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="eb7f0-408">Vi コマンドモード: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-408">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="eb7f0-409">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="eb7f0-409">ViYankToFirstChar</span></span>

<span data-ttu-id="eb7f0-410">最初の空白以外の文字からカーソルまで Yank ます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-410">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="eb7f0-411">Vi コマンドモード: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-411">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="eb7f0-412">Yank</span><span class="sxs-lookup"><span data-stu-id="eb7f0-412">Yank</span></span>

<span data-ttu-id="eb7f0-413">最後に終了したテキストを入力に追加します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-413">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="eb7f0-414">.Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-414">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="eb7f0-415">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="eb7f0-415">YankLastArg</span></span>

<span data-ttu-id="eb7f0-416">前の履歴行の最後の引数を Yank します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-416">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="eb7f0-417">引数を使用すると、最初に呼び出されたときに、YankNthArg と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-417">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="eb7f0-418">複数回呼び出された場合は、代わりに履歴を反復処理し、引数に方向を設定します (負の方向が反転します)。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-418">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="eb7f0-419">コマンド: `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-419">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="eb7f0-420">Emacs: `<Alt+.>` 、 `<Alt+_>` 、 `<Escape,.>` 、 `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-420">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="eb7f0-421">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="eb7f0-421">YankNthArg</span></span>

<span data-ttu-id="eb7f0-422">Yank は、前の履歴行から (コマンドの後に) 最初の引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-422">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="eb7f0-423">引数を使用して、n 番目の引数 (0 から始まる) を yank します。引数が負の場合は、最後の引数から開始します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-423">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="eb7f0-424">Emacs: `<Ctrl+Alt+y>` 、 `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-424">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="eb7f0-425">YankPop</span><span class="sxs-lookup"><span data-stu-id="eb7f0-425">YankPop</span></span>

<span data-ttu-id="eb7f0-426">前の操作が Yank または YankPop であった場合は、以前の引き抜かテキストをキルリングから次に強制終了されたテキストに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-426">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="eb7f0-427">Emacs: `<Alt+y>` 、 `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-427">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="eb7f0-428">カーソルの移動関数</span><span class="sxs-lookup"><span data-stu-id="eb7f0-428">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="eb7f0-429">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="eb7f0-429">BackwardChar</span></span>

<span data-ttu-id="eb7f0-430">カーソルを1文字左に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-430">Move the cursor one character to the left.</span></span> <span data-ttu-id="eb7f0-431">これにより、カーソルが複数行の入力の前の行に移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-431">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="eb7f0-432">コマンド: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-432">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="eb7f0-433">Emacs: `<LeftArrow>` 、 `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-433">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>
- <span data-ttu-id="eb7f0-434">Vi の挿入モード: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-434">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="eb7f0-435">Vi コマンドモード: `<LeftArrow>` 、 `<Backspace>` 、 `<h>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-435">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="eb7f0-436">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-436">BackwardWord</span></span>

<span data-ttu-id="eb7f0-437">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-437">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="eb7f0-438">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-438">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="eb7f0-439">コマンド: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-439">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="eb7f0-440">Emacs: `<Alt+b>` 、 `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-440">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="eb7f0-441">Vi の挿入モード: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-441">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="eb7f0-442">Vi コマンドモード: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-442">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="eb7f0-443">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-443">BeginningOfLine</span></span>

<span data-ttu-id="eb7f0-444">入力に複数の行がある場合は、現在の行の先頭に移動します。または、既に行の先頭にある場合は、入力の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-444">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="eb7f0-445">入力に1行しか含まれていない場合は、入力の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-445">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="eb7f0-446">コマンド: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-446">Cmd: `<Home>`</span></span>
- <span data-ttu-id="eb7f0-447">Emacs: `<Home>` 、 `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-447">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="eb7f0-448">Vi の挿入モード: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-448">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="eb7f0-449">Vi コマンドモード: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-449">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="eb7f0-450">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-450">EndOfLine</span></span>

<span data-ttu-id="eb7f0-451">入力に複数の行がある場合は、現在の行の末尾に移動します。または、既に行の末尾にある場合は、入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-451">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="eb7f0-452">入力に1行しか含まれていない場合は、入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-452">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="eb7f0-453">コマンド: `<End>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-453">Cmd: `<End>`</span></span>
- <span data-ttu-id="eb7f0-454">Emacs: `<End>` 、 `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-454">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="eb7f0-455">Vi の挿入モード: `<End>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-455">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="eb7f0-456">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="eb7f0-456">ForwardChar</span></span>

<span data-ttu-id="eb7f0-457">カーソルを1文字右に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-457">Move the cursor one character to the right.</span></span> <span data-ttu-id="eb7f0-458">これにより、カーソルが複数行入力の次の行に移動する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-458">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="eb7f0-459">コマンド: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-459">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="eb7f0-460">Emacs: `<RightArrow>` 、 `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-460">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>
- <span data-ttu-id="eb7f0-461">Vi の挿入モード: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-461">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="eb7f0-462">Vi コマンドモード: `<RightArrow>` 、 `<Space>` 、 `<l>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-462">Vi command mode: `<RightArrow>`, `<Space>`, `<l>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="eb7f0-463">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-463">ForwardWord</span></span>

<span data-ttu-id="eb7f0-464">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-464">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="eb7f0-465">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-465">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="eb7f0-466">Emacs: `<Alt+f>` 、 `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-466">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="eb7f0-467">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="eb7f0-467">GotoBrace</span></span>

<span data-ttu-id="eb7f0-468">対応する中かっこ、かっこ、または角かっこにジャンプします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-468">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="eb7f0-469">コマンド: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-469">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="eb7f0-470">Vi の挿入モード: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-470">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="eb7f0-471">Vi コマンドモード: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-471">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="eb7f0-472">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="eb7f0-472">GotoColumn</span></span>

<span data-ttu-id="eb7f0-473">Arg で示される列に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-473">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="eb7f0-474">Vi コマンドモード: `<|>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-474">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="eb7f0-475">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-475">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="eb7f0-476">カーソルを行の空白以外の最初の文字に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-476">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="eb7f0-477">Vi コマンドモード: `<^>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-477">Vi command mode: `<^>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="eb7f0-478">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-478">MoveToEndOfLine</span></span>

<span data-ttu-id="eb7f0-479">カーソルを入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-479">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="eb7f0-480">Vi コマンドモード: `<End>` 、 `<$>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-480">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="eb7f0-481">NextLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-481">NextLine</span></span>

<span data-ttu-id="eb7f0-482">カーソルを次の行に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-482">Move the cursor to the next line.</span></span>

- <span data-ttu-id="eb7f0-483">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-483">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="eb7f0-484">NextWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-484">NextWord</span></span>

<span data-ttu-id="eb7f0-485">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-485">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="eb7f0-486">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-486">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="eb7f0-487">コマンド: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-487">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="eb7f0-488">Vi の挿入モード: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-488">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="eb7f0-489">Vi コマンドモード: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-489">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="eb7f0-490">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="eb7f0-490">NextWordEnd</span></span>

<span data-ttu-id="eb7f0-491">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-491">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="eb7f0-492">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-492">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="eb7f0-493">Vi コマンドモード: `<e>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-493">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="eb7f0-494">前の行</span><span class="sxs-lookup"><span data-stu-id="eb7f0-494">PreviousLine</span></span>

<span data-ttu-id="eb7f0-495">カーソルを前の行に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-495">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="eb7f0-496">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-496">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="eb7f0-497">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-497">ShellBackwardWord</span></span>

<span data-ttu-id="eb7f0-498">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-498">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="eb7f0-499">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-499">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="eb7f0-500">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-500">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="eb7f0-501">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-501">ShellForwardWord</span></span>

<span data-ttu-id="eb7f0-502">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-502">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="eb7f0-503">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-503">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="eb7f0-504">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-504">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="eb7f0-505">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-505">ShellNextWord</span></span>

<span data-ttu-id="eb7f0-506">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-506">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="eb7f0-507">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-507">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="eb7f0-508">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-508">Function is unbound.</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="eb7f0-509">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-509">ViBackwardWord</span></span>

<span data-ttu-id="eb7f0-510">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-510">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="eb7f0-511">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-511">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="eb7f0-512">Vi コマンドモード: `<b>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-512">Vi command mode: `<b>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="eb7f0-513">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="eb7f0-513">ViEndOfGlob</span></span>

<span data-ttu-id="eb7f0-514">区切り記号として空白文字のみを使用して、カーソルを単語の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-514">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="eb7f0-515">Vi コマンドモード: `<E>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-515">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="eb7f0-516">Viendofの Glob</span><span class="sxs-lookup"><span data-stu-id="eb7f0-516">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="eb7f0-517">単語区切り記号として空白文字のみを使用して、前の単語の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-517">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="eb7f0-518">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-518">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="eb7f0-519">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="eb7f0-519">ViGotoBrace</span></span>

<span data-ttu-id="eb7f0-520">GotoBrace に似ていますが、トークンベースではなく文字ベースです。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-520">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="eb7f0-521">Vi コマンドモード: `<%>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-521">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="eb7f0-522">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="eb7f0-522">ViNextGlob</span></span>

<span data-ttu-id="eb7f0-523">単語区切り記号として空白文字のみを使用して、次の単語に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-523">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="eb7f0-524">Vi コマンドモード: `<W>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-524">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="eb7f0-525">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-525">ViNextWord</span></span>

<span data-ttu-id="eb7f0-526">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-526">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="eb7f0-527">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-527">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="eb7f0-528">Vi コマンドモード: `<w>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-528">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="eb7f0-529">履歴関数</span><span class="sxs-lookup"><span data-stu-id="eb7f0-529">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="eb7f0-530">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="eb7f0-530">BeginningOfHistory</span></span>

<span data-ttu-id="eb7f0-531">履歴内の最初の項目に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-531">Move to the first item in the history.</span></span>

- <span data-ttu-id="eb7f0-532">.Emacs `<Alt+`<>\`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-532">Emacs: `<Alt+`<>\`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="eb7f0-533">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="eb7f0-533">ClearHistory</span></span>

<span data-ttu-id="eb7f0-534">PSReadLine の履歴をクリアします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-534">Clears history in PSReadLine.</span></span> <span data-ttu-id="eb7f0-535">これは、PowerShell の履歴には影響しません。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-535">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="eb7f0-536">コマンド: `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-536">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="eb7f0-537">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="eb7f0-537">EndOfHistory</span></span>

<span data-ttu-id="eb7f0-538">履歴内の最後の項目 (現在の入力) に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-538">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="eb7f0-539">.Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-539">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="eb7f0-540">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="eb7f0-540">ForwardSearchHistory</span></span>

<span data-ttu-id="eb7f0-541">履歴を使用した増分転送検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-541">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="eb7f0-542">コマンド: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-542">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="eb7f0-543">.Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-543">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="eb7f0-544">履歴の Search後方</span><span class="sxs-lookup"><span data-stu-id="eb7f0-544">HistorySearchBackward</span></span>

<span data-ttu-id="eb7f0-545">現在の入力を、PSReadLine 履歴の ' previous ' 項目で置き換えます。この項目は、開始と入力の間の文字とカーソルの間の文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-545">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="eb7f0-546">コマンド: `<F8>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-546">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="eb7f0-547">履歴の Searchforward</span><span class="sxs-lookup"><span data-stu-id="eb7f0-547">HistorySearchForward</span></span>

<span data-ttu-id="eb7f0-548">現在の入力を、PSReadLine 履歴の ' next ' 項目で置き換えます。この項目は、開始と入力の間の文字とカーソルの間の文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-548">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="eb7f0-549">コマンド: `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-549">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="eb7f0-550">NextHistory</span><span class="sxs-lookup"><span data-stu-id="eb7f0-550">NextHistory</span></span>

<span data-ttu-id="eb7f0-551">現在の入力を、PSReadLine 履歴の ' next ' 項目に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-551">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="eb7f0-552">コマンド: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-552">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="eb7f0-553">Emacs: `<DownArrow>` 、 `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-553">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="eb7f0-554">Vi の挿入モード: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-554">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="eb7f0-555">Vi コマンドモード: `<DownArrow>` 、 `<j>` 、 `<+>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-555">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="eb7f0-556">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="eb7f0-556">PreviousHistory</span></span>

<span data-ttu-id="eb7f0-557">現在の入力を、PSReadLine 履歴の ' previous ' 項目に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-557">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="eb7f0-558">コマンド: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-558">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="eb7f0-559">Emacs: `<UpArrow>` 、 `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-559">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="eb7f0-560">Vi の挿入モード: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-560">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="eb7f0-561">Vi コマンドモード: `<UpArrow>` 、 `<k>` 、 `<->`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-561">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="eb7f0-562">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="eb7f0-562">ReverseSearchHistory</span></span>

<span data-ttu-id="eb7f0-563">履歴を介して後方検索を段階的に実行します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-563">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="eb7f0-564">コマンド: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-564">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="eb7f0-565">.Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-565">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="eb7f0-566">Visearchhistory 後方</span><span class="sxs-lookup"><span data-stu-id="eb7f0-566">ViSearchHistoryBackward</span></span>

<span data-ttu-id="eb7f0-567">検索文字列を入力し、AcceptLine で検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-567">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="eb7f0-568">Vi の挿入モード: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-568">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="eb7f0-569">Vi コマンドモード: `</>` 、 `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-569">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="eb7f0-570">入力候補関数</span><span class="sxs-lookup"><span data-stu-id="eb7f0-570">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="eb7f0-571">完了</span><span class="sxs-lookup"><span data-stu-id="eb7f0-571">Complete</span></span>

<span data-ttu-id="eb7f0-572">カーソルを囲むテキストに対して入力候補を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-572">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="eb7f0-573">候補が複数ある場合は、最長の明確なプレフィックスを使用して完了します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-573">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="eb7f0-574">最長の明確な完了を完了しようとすると、候補の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-574">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="eb7f0-575">.Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-575">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="eb7f0-576">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="eb7f0-576">MenuComplete</span></span>

<span data-ttu-id="eb7f0-577">カーソルを囲むテキストに対して入力候補を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-577">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="eb7f0-578">候補が複数ある場合は、最長の明確なプレフィックスを使用して完了します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-578">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="eb7f0-579">最長の明確な完了を完了しようとすると、候補の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-579">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="eb7f0-580">コマンド: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-580">Cmd: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="eb7f0-581">.Emacs `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-581">Emacs: `<Ctrl+Space>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="eb7f0-582">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="eb7f0-582">PossibleCompletions</span></span>

<span data-ttu-id="eb7f0-583">候補の候補の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-583">Display the list of possible completions.</span></span>

- <span data-ttu-id="eb7f0-584">.Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-584">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="eb7f0-585">Vi の挿入モード: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-585">Vi insert mode: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="eb7f0-586">Vi コマンドモード: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-586">Vi command mode: `<Ctrl+Space>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="eb7f0-587">タブのすべてのタブ</span><span class="sxs-lookup"><span data-stu-id="eb7f0-587">TabCompleteNext</span></span>

<span data-ttu-id="eb7f0-588">次に使用可能な完了時に、カーソルを囲むテキストを完了します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-588">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="eb7f0-589">コマンド: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-589">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="eb7f0-590">Vi コマンドモード: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-590">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="eb7f0-591">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="eb7f0-591">TabCompletePrevious</span></span>

<span data-ttu-id="eb7f0-592">以前に使用可能な入力候補を使用して、カーソルを囲むテキストを完了しようとしました。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-592">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="eb7f0-593">コマンド: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-593">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="eb7f0-594">Vi コマンドモード: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-594">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="eb7f0-595">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="eb7f0-595">ViTabCompleteNext</span></span>

<span data-ttu-id="eb7f0-596">必要に応じて現在の編集グループを終了し、Tabends を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-596">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="eb7f0-597">Vi の挿入モード: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-597">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="eb7f0-598">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="eb7f0-598">ViTabCompletePrevious</span></span>

<span data-ttu-id="eb7f0-599">必要に応じて現在の編集グループを終了し、TabCompletePrevious を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-599">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="eb7f0-600">Vi の挿入モード: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-600">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="eb7f0-601">その他の関数</span><span class="sxs-lookup"><span data-stu-id="eb7f0-601">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="eb7f0-602">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="eb7f0-602">CaptureScreen</span></span>

<span data-ttu-id="eb7f0-603">対話型画面のキャプチャを開始する/下矢印行を選択し、[選択したテキストをテキストと html としてクリップボードにコピーする] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-603">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="eb7f0-604">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-604">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="eb7f0-605">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="eb7f0-605">ClearScreen</span></span>

<span data-ttu-id="eb7f0-606">画面をクリアし、画面の上部にある現在の線を描画します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-606">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="eb7f0-607">コマンド: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-607">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="eb7f0-608">.Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-608">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="eb7f0-609">Vi の挿入モード: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-609">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="eb7f0-610">Vi コマンドモード: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-610">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="eb7f0-611">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="eb7f0-611">DigitArgument</span></span>

<span data-ttu-id="eb7f0-612">他の関数に渡す新しい桁引数を開始します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-612">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="eb7f0-613">Cmd:、、、、、、、、、 `<Alt+0>` `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-613">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="eb7f0-614">Emacs:、、、、、、、、、 `<Alt+0>` `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-614">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="eb7f0-615">Vi コマンドモード:、、、、、、、、 `<0>` `<1>` `<2>` `<3>` `<4>` `<5>` `<6>` `<7>` `<8>` 、 `<9>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-615">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="eb7f0-616">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="eb7f0-616">InvokePrompt</span></span>

<span data-ttu-id="eb7f0-617">現在のプロンプトを消去し、prompt 関数を呼び出してプロンプトを再表示します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-617">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="eb7f0-618">現在のディレクトリを変更するなど、状態を変更するカスタムキーハンドラーに便利です。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-618">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="eb7f0-619">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-619">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="eb7f0-620">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="eb7f0-620">ScrollDisplayDown</span></span>

<span data-ttu-id="eb7f0-621">画面を1画面下へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-621">Scroll the display down one screen.</span></span>

- <span data-ttu-id="eb7f0-622">コマンド: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-622">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="eb7f0-623">.Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-623">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="eb7f0-624">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-624">ScrollDisplayDownLine</span></span>

<span data-ttu-id="eb7f0-625">表示を1行下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-625">Scroll the display down one line.</span></span>

- <span data-ttu-id="eb7f0-626">コマンド: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-626">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="eb7f0-627">.Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-627">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="eb7f0-628">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="eb7f0-628">ScrollDisplayToCursor</span></span>

<span data-ttu-id="eb7f0-629">カーソルまで画面をスクロールします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-629">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="eb7f0-630">.Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-630">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="eb7f0-631">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="eb7f0-631">ScrollDisplayTop</span></span>

<span data-ttu-id="eb7f0-632">画面を上にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-632">Scroll the display to the top.</span></span>

- <span data-ttu-id="eb7f0-633">.Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-633">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="eb7f0-634">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="eb7f0-634">ScrollDisplayUp</span></span>

<span data-ttu-id="eb7f0-635">画面を1画面上へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-635">Scroll the display up one screen.</span></span>

- <span data-ttu-id="eb7f0-636">コマンド: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-636">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="eb7f0-637">.Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-637">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="eb7f0-638">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-638">ScrollDisplayUpLine</span></span>

<span data-ttu-id="eb7f0-639">表示を1行上へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-639">Scroll the display up one line.</span></span>

- <span data-ttu-id="eb7f0-640">コマンド: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-640">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="eb7f0-641">.Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-641">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="eb7f0-642">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="eb7f0-642">SelfInsert</span></span>

<span data-ttu-id="eb7f0-643">キーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-643">Insert the key.</span></span>

- <span data-ttu-id="eb7f0-644">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-644">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="eb7f0-645">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="eb7f0-645">ShowKeyBindings</span></span>

<span data-ttu-id="eb7f0-646">すべてのバインドされたキーを表示します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-646">Show all bound keys.</span></span>

- <span data-ttu-id="eb7f0-647">コマンド: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-647">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="eb7f0-648">.Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-648">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="eb7f0-649">Vi の挿入モード: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-649">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="eb7f0-650">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="eb7f0-650">ViCommandMode</span></span>

<span data-ttu-id="eb7f0-651">現在の動作モードを Vi-Insert から Vi-Command に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-651">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="eb7f0-652">Vi の挿入モード: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-652">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="eb7f0-653">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-653">ViDigitArgumentInChord</span></span>

<span data-ttu-id="eb7f0-654">Vi のいずれかの弦で、他の関数に渡す新しい桁引数を開始します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-654">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="eb7f0-655">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-655">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="eb7f0-656">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="eb7f0-656">ViEditVisually</span></span>

<span data-ttu-id="eb7f0-657">$Env: EDITOR または $env: ビジュアルによって指定されたテキストエディターでコマンドラインを編集します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-657">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="eb7f0-658">.Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-658">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="eb7f0-659">Vi コマンドモード: `<v>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-659">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="eb7f0-660">ViExit</span><span class="sxs-lookup"><span data-stu-id="eb7f0-660">ViExit</span></span>

<span data-ttu-id="eb7f0-661">シェルを終了します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-661">Exits the shell.</span></span>

- <span data-ttu-id="eb7f0-662">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-662">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="eb7f0-663">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="eb7f0-663">ViInsertMode</span></span>

<span data-ttu-id="eb7f0-664">挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-664">Switch to Insert mode.</span></span>

- <span data-ttu-id="eb7f0-665">Vi コマンドモード: `<i>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-665">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="eb7f0-666">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="eb7f0-666">WhatIsKey</span></span>

<span data-ttu-id="eb7f0-667">キーを読み取り、キーがどのようにバインドされているかを通知します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-667">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="eb7f0-668">コマンド: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-668">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="eb7f0-669">.Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-669">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="eb7f0-670">選択関数</span><span class="sxs-lookup"><span data-stu-id="eb7f0-670">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="eb7f0-671">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="eb7f0-671">ExchangePointAndMark</span></span>

<span data-ttu-id="eb7f0-672">カーソルがマークの位置に置かれ、マークがカーソルの位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-672">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="eb7f0-673">.Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-673">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="eb7f0-674">SelectAll</span><span class="sxs-lookup"><span data-stu-id="eb7f0-674">SelectAll</span></span>

<span data-ttu-id="eb7f0-675">行全体を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-675">Select the entire line.</span></span>

- <span data-ttu-id="eb7f0-676">コマンド: `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-676">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="eb7f0-677">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="eb7f0-677">SelectBackwardChar</span></span>

<span data-ttu-id="eb7f0-678">現在の選択範囲を調整して、前の文字を含めます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-678">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="eb7f0-679">コマンド: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-679">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="eb7f0-680">.Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-680">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="eb7f0-681">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-681">SelectBackwardsLine</span></span>

<span data-ttu-id="eb7f0-682">カーソルから行の先頭まで、現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-682">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="eb7f0-683">コマンド: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-683">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="eb7f0-684">.Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-684">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="eb7f0-685">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-685">SelectBackwardWord</span></span>

<span data-ttu-id="eb7f0-686">現在の選択範囲を調整して、前の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-686">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="eb7f0-687">コマンド: `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-687">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="eb7f0-688">.Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-688">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="eb7f0-689">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="eb7f0-689">SelectForwardChar</span></span>

<span data-ttu-id="eb7f0-690">現在の選択範囲を調整して、次の文字を含めます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-690">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="eb7f0-691">コマンド: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-691">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="eb7f0-692">.Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-692">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="eb7f0-693">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-693">SelectForwardWord</span></span>

<span data-ttu-id="eb7f0-694">現在の選択範囲を調整して、ForwardWord を使用して次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-694">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="eb7f0-695">.Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-695">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="eb7f0-696">SelectLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-696">SelectLine</span></span>

<span data-ttu-id="eb7f0-697">カーソルから行の末尾まで、現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-697">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="eb7f0-698">コマンド: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-698">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="eb7f0-699">.Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-699">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="eb7f0-700">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-700">SelectNextWord</span></span>

<span data-ttu-id="eb7f0-701">現在の選択範囲を調整して、次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-701">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="eb7f0-702">コマンド: `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-702">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="eb7f0-703">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-703">SelectShellBackwardWord</span></span>

<span data-ttu-id="eb7f0-704">ShellBackwardWord を使用して、前の単語が含まれるように現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-704">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="eb7f0-705">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-705">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="eb7f0-706">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-706">SelectShellForwardWord</span></span>

<span data-ttu-id="eb7f0-707">現在の選択範囲を調整して、ShellForwardWord を使用する次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-707">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="eb7f0-708">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-708">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="eb7f0-709">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="eb7f0-709">SelectShellNextWord</span></span>

<span data-ttu-id="eb7f0-710">現在の選択範囲を調整して、ShellNextWord を使用して次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-710">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="eb7f0-711">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-711">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="eb7f0-712">SetMark</span><span class="sxs-lookup"><span data-stu-id="eb7f0-712">SetMark</span></span>

<span data-ttu-id="eb7f0-713">後続の編集コマンドで使用するために、カーソルの現在の位置をマークします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-713">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="eb7f0-714">.Emacs `<Ctrl+`>\`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-714">Emacs: `<Ctrl+`>\`</span></span>

## <a name="search-functions"></a><span data-ttu-id="eb7f0-715">関数の検索</span><span class="sxs-lookup"><span data-stu-id="eb7f0-715">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="eb7f0-716">文字検索</span><span class="sxs-lookup"><span data-stu-id="eb7f0-716">CharacterSearch</span></span>

<span data-ttu-id="eb7f0-717">文字を読み取り、その文字が次に出現するまで検索します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-717">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="eb7f0-718">引数が指定されている場合は、n 番目のオカレンスに対して前方 (負の場合は後方) を検索します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-718">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="eb7f0-719">コマンド: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-719">Cmd: `<F3>`</span></span>
- <span data-ttu-id="eb7f0-720">.Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-720">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="eb7f0-721">Vi の挿入モード: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-721">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="eb7f0-722">Vi コマンドモード: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-722">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="eb7f0-723">文字 Search後方</span><span class="sxs-lookup"><span data-stu-id="eb7f0-723">CharacterSearchBackward</span></span>

<span data-ttu-id="eb7f0-724">文字を読み取り、その文字が次に出現するまで検索します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-724">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="eb7f0-725">引数が指定されている場合は、n 番目のオカレンスに対して後方 (または負の場合は forward) を検索します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-725">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="eb7f0-726">コマンド: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-726">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="eb7f0-727">.Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-727">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="eb7f0-728">Vi の挿入モード: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-728">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="eb7f0-729">Vi コマンドモード: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-729">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="eb7f0-730">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="eb7f0-730">RepeatLastCharSearch</span></span>

<span data-ttu-id="eb7f0-731">最後に記録された文字の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-731">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="eb7f0-732">Vi コマンドモード: `<;>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-732">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="eb7f0-733">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="eb7f0-733">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="eb7f0-734">最後に記録された文字検索を逆方向に繰り返します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-734">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="eb7f0-735">Vi コマンドモード: `<,>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-735">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="eb7f0-736">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="eb7f0-736">RepeatSearch</span></span>

<span data-ttu-id="eb7f0-737">前と同じ方向に最後の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-737">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="eb7f0-738">Vi コマンドモード: `<n>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-738">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="eb7f0-739">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="eb7f0-739">RepeatSearchBackward</span></span>

<span data-ttu-id="eb7f0-740">前と同じ方向に最後の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-740">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="eb7f0-741">Vi コマンドモード: `<N>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-741">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="eb7f0-742">SearchChar</span><span class="sxs-lookup"><span data-stu-id="eb7f0-742">SearchChar</span></span>

<span data-ttu-id="eb7f0-743">次の文字を読み取って検索し、次に文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-743">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="eb7f0-744">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-744">This is for 't' functionality.</span></span>

- <span data-ttu-id="eb7f0-745">Vi コマンドモード: `<f>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-745">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="eb7f0-746">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="eb7f0-746">SearchCharBackward</span></span>

<span data-ttu-id="eb7f0-747">次の文字を読み取り、それを検索して後方に移動し、次に文字を戻します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-747">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="eb7f0-748">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-748">This is for 'T' functionality.</span></span>

- <span data-ttu-id="eb7f0-749">Vi コマンドモード: `<F>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-749">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="eb7f0-750">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="eb7f0-750">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="eb7f0-751">次の文字を読み取り、それを検索して後方に移動し、次に文字を戻します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-751">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="eb7f0-752">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-752">This is for 'T' functionality.</span></span>

- <span data-ttu-id="eb7f0-753">Vi コマンドモード: `<T>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-753">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="eb7f0-754">SearchCharWithBackoff オフ</span><span class="sxs-lookup"><span data-stu-id="eb7f0-754">SearchCharWithBackoff</span></span>

<span data-ttu-id="eb7f0-755">次の文字を読み取って検索し、次に文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-755">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="eb7f0-756">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-756">This is for 't' functionality.</span></span>

- <span data-ttu-id="eb7f0-757">Vi コマンドモード: `<t>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-757">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="eb7f0-758">SearchForward</span><span class="sxs-lookup"><span data-stu-id="eb7f0-758">SearchForward</span></span>

<span data-ttu-id="eb7f0-759">検索文字列を入力し、AcceptLine で検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-759">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="eb7f0-760">Vi の挿入モード: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-760">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="eb7f0-761">Vi コマンドモード: `<?>` 、 `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="eb7f0-761">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="eb7f0-762">カスタムキーバインド</span><span class="sxs-lookup"><span data-stu-id="eb7f0-762">Custom Key Bindings</span></span>

<span data-ttu-id="eb7f0-763">PSReadLine は、コマンドレットを使用してカスタムキーバインドをサポートしてい `Set-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-763">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="eb7f0-764">ほとんどのカスタムキーバインドは、たとえば、上記の関数の1つを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-764">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="eb7f0-765">ScriptBlock をキーにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-765">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="eb7f0-766">ScriptBlock は、ほとんどすべてのことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-766">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="eb7f0-767">いくつかの便利な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-767">Some useful examples include</span></span>

- <span data-ttu-id="eb7f0-768">コマンドラインを編集する</span><span class="sxs-lookup"><span data-stu-id="eb7f0-768">edit the command line</span></span>
- <span data-ttu-id="eb7f0-769">新しいウィンドウを開く (例: ヘルプ)</span><span class="sxs-lookup"><span data-stu-id="eb7f0-769">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="eb7f0-770">コマンドラインを変更せずにディレクトリを変更する</span><span class="sxs-lookup"><span data-stu-id="eb7f0-770">change directories without changing the command line</span></span>

<span data-ttu-id="eb7f0-771">ScriptBlock は、次の2つの引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-771">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="eb7f0-772">`$key` -カスタムバインドをトリガーしたキーである **[Consolekeyinfo]** オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-772">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="eb7f0-773">同じ ScriptBlock を複数のキーにバインドし、キーに応じて異なるアクションを実行する必要がある場合は、$key を確認します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-773">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="eb7f0-774">多くのカスタムバインドでは、この引数は無視します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-774">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="eb7f0-775">`$arg` -任意の引数。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-775">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="eb7f0-776">多くの場合、これは、ユーザーがキーバインド DigitArgument から渡す整数引数になります。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-776">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="eb7f0-777">バインディングが引数を受け入れない場合は、この引数を無視するのが妥当です。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-777">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="eb7f0-778">ここでは、コマンドラインを実行せずに履歴に追加する例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-778">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="eb7f0-779">これは、何らかの操作を忘れた場合に、既に入力したコマンドラインを再入力したくない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-779">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="eb7f0-780">PSReadLine モジュールフォルダーにインストールされているファイルには、さらに多くの例が表示 `SamplePSReadLineProfile.ps1` されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-780">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="eb7f0-781">ほとんどのキーバインドでは、コマンドラインを編集するためにいくつかのヘルパー関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-781">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="eb7f0-782">これらの Api については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-782">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="eb7f0-783">カスタムキーバインディングサポート Api</span><span class="sxs-lookup"><span data-stu-id="eb7f0-783">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="eb7f0-784">次の関数は PSConsoleReadLine では公開されていますが、キーに直接バインドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-784">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="eb7f0-785">多くの場合、カスタムキーバインドに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-785">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="eb7f0-786">コマンドラインを実行せずに、履歴に追加します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-786">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="eb7f0-787">Kill リングをクリアします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-787">Clear the kill-ring.</span></span>  <span data-ttu-id="eb7f0-788">これは主にテストに使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-788">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="eb7f0-789">先頭から長さの文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-789">Delete length characters from start.</span></span>  <span data-ttu-id="eb7f0-790">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-790">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="eb7f0-791">ユーザー設定に基づいてアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-791">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="eb7f0-792">これらの2つの関数は、入力バッファーの現在の状態に関する有用な情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-792">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="eb7f0-793">1つ目は、単純なケースでよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-793">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="eb7f0-794">2つ目は、バインディングが Ast を使用してより高度な処理を実行している場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-794">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

```

<span data-ttu-id="eb7f0-795">この関数は Get-PSReadLineKeyHandler によって使用され、カスタムキーバインドでは役に立たない場合があります。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-795">This function is used by Get-PSReadLineKeyHandler and probably isn't useful in a custom key binding.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="eb7f0-796">この関数は Get-PSReadLineOption によって使用され、カスタムキーバインドではあまり役に立たない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-796">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="eb7f0-797">コマンドラインに何も選択されていない場合は、開始と長さの両方で-1 が返されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-797">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="eb7f0-798">コマンドラインに選択項目がある場合は、選択範囲の先頭と長さが返されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-798">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="eb7f0-799">カーソル位置に文字または文字列を挿入します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-799">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="eb7f0-800">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-800">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="eb7f0-801">これは、PSReadLine へのメインエントリポイントです。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-801">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="eb7f0-802">再帰はサポートされないため、カスタムキーバインドでは役に立ちません。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-802">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="eb7f0-803">この関数は Remove-PSReadLineKeyHandler によって使用され、カスタムキーバインドではあまり役に立たない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-803">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="eb7f0-804">入力の一部を置換します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-804">Replace some of the input.</span></span> <span data-ttu-id="eb7f0-805">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-805">This operation supports undo/redo.</span></span> <span data-ttu-id="eb7f0-806">これは、undo の単一のアクションとして扱われるため、Delete の後に Insert を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-806">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="eb7f0-807">カーソルを指定されたオフセットに移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-807">Move the cursor to the given offset.</span></span> <span data-ttu-id="eb7f0-808">カーソルの移動は、元に戻すために追跡されません。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-808">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="eb7f0-809">この関数は、コマンドレットの設定-PSReadLineOption によって使用されるヘルパーメソッドですが、一時的に設定を変更する必要があるカスタムキーバインドに便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-809">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="eb7f0-810">このヘルパーメソッドは、DigitArgument を優先するカスタムバインドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-810">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="eb7f0-811">一般的な呼び出しは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-811">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="eb7f0-812">注</span><span class="sxs-lookup"><span data-stu-id="eb7f0-812">NOTE</span></span>

### <a name="powershell-compatibility"></a><span data-ttu-id="eb7f0-813">POWERSHELL の互換性</span><span class="sxs-lookup"><span data-stu-id="eb7f0-813">POWERSHELL COMPATIBILITY</span></span>

<span data-ttu-id="eb7f0-814">PSReadLine には、PowerShell 3.0 以降とコンソールホストが必要です。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-814">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="eb7f0-815">PowerShell ISE では機能しません。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-815">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="eb7f0-816">これは Visual Studio Code のコンソールで機能します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-816">It does work in the console of Visual Studio Code.</span></span>

### <a name="command-history"></a><span data-ttu-id="eb7f0-817">コマンド履歴</span><span class="sxs-lookup"><span data-stu-id="eb7f0-817">COMMAND HISTORY</span></span>

<span data-ttu-id="eb7f0-818">PSReadLine は、コマンドラインから入力したすべてのコマンドとデータを含む履歴ファイルを保持します。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-818">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="eb7f0-819">これには、パスワードなどの機密データが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-819">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="eb7f0-820">たとえば、コマンドレットを使用した場合、 `ConvertTo-SecureString` パスワードはプレーンテキストとして履歴ファイルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-820">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="eb7f0-821">履歴ファイルは、という名前のファイルです `$($host.Name)_history.txt` 。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-821">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="eb7f0-822">Windows システムでは、履歴ファイルはに格納され `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` ます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-822">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="eb7f0-823">PSReadLine に貢献しているフィードバック &</span><span class="sxs-lookup"><span data-stu-id="eb7f0-823">FEEDBACK & CONTRIBUTING TO PSReadLine</span></span>

[<span data-ttu-id="eb7f0-824">GitHub の PSReadLine</span><span class="sxs-lookup"><span data-stu-id="eb7f0-824">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="eb7f0-825">プル要求を送信したり、GitHub ページでフィードバックを送信したりしてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-825">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb7f0-826">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb7f0-826">SEE ALSO</span></span>

<span data-ttu-id="eb7f0-827">PSReadLine は、GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) ライブラリの影響を強く受けます。</span><span class="sxs-lookup"><span data-stu-id="eb7f0-827">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
