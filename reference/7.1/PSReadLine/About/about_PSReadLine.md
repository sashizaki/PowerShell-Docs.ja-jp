---
description: PSReadLine では、PowerShell コンソールでのコマンドライン編集エクスペリエンスが向上しています。
keywords: powershell
Locale: en-US
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: PSReadLine について
ms.openlocfilehash: 1188b8dc0b4099a7c1dcc472e3b02c2d4fa908bc
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220808"
---
# <a name="psreadline"></a><span data-ttu-id="6c8f4-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="6c8f4-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="6c8f4-106">概要</span><span class="sxs-lookup"><span data-stu-id="6c8f4-106">SHORT DESCRIPTION</span></span>

<span data-ttu-id="6c8f4-107">PSReadLine では、PowerShell コンソールでのコマンドライン編集エクスペリエンスが向上しています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="6c8f4-108">詳細説明</span><span class="sxs-lookup"><span data-stu-id="6c8f4-108">LONG DESCRIPTION</span></span>

<span data-ttu-id="6c8f4-109">PSReadLine 2.0 では、PowerShell コンソールの強力なコマンドライン編集エクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="6c8f4-110">次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-110">It provides:</span></span>

- <span data-ttu-id="6c8f4-111">コマンドラインの構文の色分け</span><span class="sxs-lookup"><span data-stu-id="6c8f4-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="6c8f4-112">構文エラーを視覚的に示します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="6c8f4-113">より優れたマルチラインエクスペリエンス (編集と履歴の両方)</span><span class="sxs-lookup"><span data-stu-id="6c8f4-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="6c8f4-114">カスタマイズ可能なキーバインド</span><span class="sxs-lookup"><span data-stu-id="6c8f4-114">Customizable key bindings</span></span>
- <span data-ttu-id="6c8f4-115">Cmd モードと Emacs モード</span><span class="sxs-lookup"><span data-stu-id="6c8f4-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="6c8f4-116">多くの構成オプション</span><span class="sxs-lookup"><span data-stu-id="6c8f4-116">Many configuration options</span></span>
- <span data-ttu-id="6c8f4-117">Bash スタイル補完 (Cmd モードでは省略可能、Emacs モードでは既定)</span><span class="sxs-lookup"><span data-stu-id="6c8f4-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="6c8f4-118">Emacs yank/kill-リング</span><span class="sxs-lookup"><span data-stu-id="6c8f4-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="6c8f4-119">PowerShell トークンベースの "word" の移動と強制終了</span><span class="sxs-lookup"><span data-stu-id="6c8f4-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="6c8f4-120">クラス **[PSConsoleReadLine]** では、次の関数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-120">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

> [!NOTE]
> <span data-ttu-id="6c8f4-121">PowerShell 7.0 以降では、スクリーンリーダープログラムが検出されると、PowerShell は Windows で PSReadLine の自動読み込みをスキップします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-121">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="6c8f4-122">現在、PSReadLine は、スクリーンリーダーではうまく機能しません。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-122">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="6c8f4-123">Windows での PowerShell 7.0 の既定の表示と書式設定は正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-123">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="6c8f4-124">必要に応じて、モジュールを手動で読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-124">You can manually load the module if necessary.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="6c8f4-125">基本的な編集関数</span><span class="sxs-lookup"><span data-stu-id="6c8f4-125">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="6c8f4-126">中止</span><span class="sxs-lookup"><span data-stu-id="6c8f4-126">Abort</span></span>

<span data-ttu-id="6c8f4-127">現在のアクション (増分履歴検索など) を中止します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-127">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="6c8f4-128">.Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-128">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="6c8f4-129">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="6c8f4-129">AcceptAndGetNext</span></span>

<span data-ttu-id="6c8f4-130">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-130">Attempt to execute the current input.</span></span> <span data-ttu-id="6c8f4-131">(AcceptLine など) 実行できる場合は、次に ReadLine が呼び出されたときに履歴から次の項目を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-131">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="6c8f4-132">.Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-132">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="6c8f4-133">AcceptLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-133">AcceptLine</span></span>

<span data-ttu-id="6c8f4-134">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-134">Attempt to execute the current input.</span></span> <span data-ttu-id="6c8f4-135">現在の入力が不完全な場合 (たとえば、終わりかっこ、角かっこ、または引用符がない場合)、継続のプロンプトは次の行に表示され、PSReadLine は現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-135">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="6c8f4-136">コマンド: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-136">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="6c8f4-137">.Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-137">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="6c8f4-138">Vi の挿入モード: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-138">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="6c8f4-139">AddLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-139">AddLine</span></span>

<span data-ttu-id="6c8f4-140">継続プロンプトが次の行に表示され、PSReadLine が現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-140">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="6c8f4-141">これは、単一行が単独で完全に入力されている場合でも、複数行の入力を1つのコマンドとして入力する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-141">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="6c8f4-142">コマンド: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-142">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="6c8f4-143">.Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-143">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="6c8f4-144">Vi の挿入モード: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-144">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="6c8f4-145">Vi コマンドモード: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-145">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="6c8f4-146">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="6c8f4-146">BackwardDeleteChar</span></span>

<span data-ttu-id="6c8f4-147">カーソルの前の文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-147">Delete the character before the cursor.</span></span>

- <span data-ttu-id="6c8f4-148">Cmd: `<Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-148">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="6c8f4-149">Emacs: `<Backspace>` 、 `<Ctrl+Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-149">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="6c8f4-150">Vi の挿入モード: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-150">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="6c8f4-151">Vi コマンドモード: `<X>` 、 `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-151">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="6c8f4-152">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-152">BackwardDeleteLine</span></span>

<span data-ttu-id="6c8f4-153">Like BackwardKillLine-行の先頭から先頭までのテキストを削除しますが、削除されたテキストはキルリングには挿入されません。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-153">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="6c8f4-154">コマンド: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-154">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="6c8f4-155">Vi 挿入モード: `<Ctrl+u>` 、 `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-155">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="6c8f4-156">Vi コマンドモード: `<Ctrl+u>` 、 `<Ctrl+Home>` 、 `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-156">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="6c8f4-157">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-157">BackwardDeleteWord</span></span>

<span data-ttu-id="6c8f4-158">前の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-158">Deletes the previous word.</span></span>

- <span data-ttu-id="6c8f4-159">Vi コマンドモード: `<Ctrl+w>` 、 `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-159">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="6c8f4-160">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-160">BackwardKillLine</span></span>

<span data-ttu-id="6c8f4-161">入力の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-161">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="6c8f4-162">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-162">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="6c8f4-163">Emacs: `<Ctrl+u>` 、 `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-163">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="6c8f4-164">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-164">BackwardKillWord</span></span>

<span data-ttu-id="6c8f4-165">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-165">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="6c8f4-166">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-166">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="6c8f4-167">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-167">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="6c8f4-168">Cmd: `<Ctrl+Backspace>` 、 `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-168">Cmd: `<Ctrl+Backspace>`, `<Ctrl+w>`</span></span>
- <span data-ttu-id="6c8f4-169">Emacs: `<Alt+Backspace>` 、 `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-169">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="6c8f4-170">Vi の挿入モード: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-170">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="6c8f4-171">Vi コマンドモード: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-171">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="6c8f4-172">CancelLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-172">CancelLine</span></span>

<span data-ttu-id="6c8f4-173">入力を画面に残したまま、現在の入力を取り消しますが、プロンプトが再び評価されるように、ホストに戻ります。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-173">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="6c8f4-174">Vi の挿入モード: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-174">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="6c8f4-175">Vi コマンドモード: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-175">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="6c8f4-176">コピー</span><span class="sxs-lookup"><span data-stu-id="6c8f4-176">Copy</span></span>

<span data-ttu-id="6c8f4-177">選択したリージョンをシステムクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-177">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="6c8f4-178">領域が選択されていない場合は、行全体をコピーします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-178">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="6c8f4-179">コマンド: `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-179">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="6c8f4-180">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-180">CopyOrCancelLine</span></span>

<span data-ttu-id="6c8f4-181">テキストが選択されている場合は、クリップボードにコピーします。それ以外の場合は、行をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-181">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="6c8f4-182">コマンド: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-182">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="6c8f4-183">.Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-183">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="6c8f4-184">切り取り</span><span class="sxs-lookup"><span data-stu-id="6c8f4-184">Cut</span></span>

<span data-ttu-id="6c8f4-185">削除されたテキストをシステムクリップボードに配置した、選択した領域を削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-185">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="6c8f4-186">コマンド: `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-186">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="6c8f4-187">Dele</span><span class="sxs-lookup"><span data-stu-id="6c8f4-187">DeleteChar</span></span>

<span data-ttu-id="6c8f4-188">カーソルの下の文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-188">Delete the character under the cursor.</span></span>

- <span data-ttu-id="6c8f4-189">コマンド: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-189">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="6c8f4-190">.Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-190">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="6c8f4-191">Vi の挿入モード: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-191">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="6c8f4-192">Vi コマンドモード: `<Delete>` 、 `<x>` 、 `<d,l>` 、 `<d,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-192">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Spacebar>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="6c8f4-193">Deleの Arorexit</span><span class="sxs-lookup"><span data-stu-id="6c8f4-193">DeleteCharOrExit</span></span>

<span data-ttu-id="6c8f4-194">カーソルの下の文字を削除するか、行が空の場合はプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-194">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="6c8f4-195">.Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-195">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofbuffer"></a><span data-ttu-id="6c8f4-196">DeleteEndOfBuffer</span><span class="sxs-lookup"><span data-stu-id="6c8f4-196">DeleteEndOfBuffer</span></span>

<span data-ttu-id="6c8f4-197">複数行バッファーの末尾までを削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-197">Deletes to the end of the multiline buffer.</span></span>

- <span data-ttu-id="6c8f4-198">Vi コマンドモード: `<d,G>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-198">Vi command mode: `<d,G>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="6c8f4-199">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-199">DeleteEndOfWord</span></span>

<span data-ttu-id="6c8f4-200">単語の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-200">Delete to the end of the word.</span></span>

- <span data-ttu-id="6c8f4-201">Vi コマンドモード: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-201">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="6c8f4-202">Deleteline.invoke に</span><span class="sxs-lookup"><span data-stu-id="6c8f4-202">DeleteLine</span></span>

<span data-ttu-id="6c8f4-203">複数行バッファーの現在の論理行を削除して、元に戻すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-203">Deletes the current logical line of a multiline buffer, enabling undo.</span></span>

- <span data-ttu-id="6c8f4-204">Vi コマンドモード: `<d,d>` 、 `<d,_>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-204">Vi command mode: `<d,d>`, `<d,_>`</span></span>

### <a name="deletepreviouslines"></a><span data-ttu-id="6c8f4-205">削除した行</span><span class="sxs-lookup"><span data-stu-id="6c8f4-205">DeletePreviousLines</span></span>

<span data-ttu-id="6c8f4-206">複数行バッファーの前に要求された論理行と現在の論理行を削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-206">Deletes the previous requested logical lines and the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="6c8f4-207">Vi コマンドモード: `<d,k>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-207">Vi command mode: `<d,k>`</span></span>

### <a name="deleterelativelines"></a><span data-ttu-id="6c8f4-208">DeleteRelativeLines</span><span class="sxs-lookup"><span data-stu-id="6c8f4-208">DeleteRelativeLines</span></span>

<span data-ttu-id="6c8f4-209">バッファーの先頭から複数行バッファーの現在の論理行に削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-209">Deletes from the beginning of the buffer to the current logical line in a multiline buffer.</span></span>

<span data-ttu-id="6c8f4-210">ほとんどの Vi コマンドと同様に、コマンドには、 `<d,g,g>` 絶対行番号を指定する数値引数 (現在の行番号と共に、削除する行の範囲を構成する) を付加することができます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-210">As most Vi commands, the `<d,g,g>` command can be prepended with a numeric argument that specifies an absolute line number, which, together with the current line number, make up a range of lines to be deleted.</span></span>
<span data-ttu-id="6c8f4-211">指定しない場合、数値引数の既定値は1です。これは、複数行バッファーの最初の論理行を参照します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-211">If not specified, the numeric argument defaults to 1, which refers to the first logical line in a multiline buffer.</span></span>

<span data-ttu-id="6c8f4-212">複数行から削除される実際の行数は、現在の論理行番号と指定された数値引数の差として計算されます。したがって、負の数になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-212">The actual number of lines to be deleted from the multiline is computed as the difference between the current logical line number and the specified numeric argument, which can thus be negative.</span></span> <span data-ttu-id="6c8f4-213">そのため、メソッド名の _相対_ 部分です。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-213">Hence the _relative_ part of method name.</span></span>

- <span data-ttu-id="6c8f4-214">Vi コマンドモード: `<d,g,g>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-214">Vi command mode: `<d,g,g>`</span></span>

### <a name="deletenextlines"></a><span data-ttu-id="6c8f4-215">Deleの配信行</span><span class="sxs-lookup"><span data-stu-id="6c8f4-215">DeleteNextLines</span></span>

<span data-ttu-id="6c8f4-216">複数行バッファーで現在の論理行と次に要求された論理行を削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-216">Deletes the current logical line and the next requested logical lines in a multiline buffer.</span></span>

- <span data-ttu-id="6c8f4-217">Vi コマンドモード: `<d,j>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-217">Vi command mode: `<d,j>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="6c8f4-218">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="6c8f4-218">DeleteLineToFirstChar</span></span>

<span data-ttu-id="6c8f4-219">カーソルから、行の最初の空白以外の文字までのテキストを削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-219">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="6c8f4-220">Vi コマンドモード: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-220">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="6c8f4-221">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="6c8f4-221">DeleteToEnd</span></span>

<span data-ttu-id="6c8f4-222">行の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-222">Delete to the end of the line.</span></span>

- <span data-ttu-id="6c8f4-223">Vi コマンドモード: `<D>` 、 `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-223">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="6c8f4-224">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-224">DeleteWord</span></span>

<span data-ttu-id="6c8f4-225">次の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-225">Delete the next word.</span></span>

- <span data-ttu-id="6c8f4-226">Vi コマンドモード: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-226">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="6c8f4-227">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-227">ForwardDeleteLine</span></span>

<span data-ttu-id="6c8f4-228">同じように、Forwardは、行の末尾から最後までのテキストを削除しますが、削除されたテキストはキルリングには挿入されません。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-228">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="6c8f4-229">コマンド: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-229">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="6c8f4-230">Vi の挿入モード: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-230">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="6c8f4-231">Vi コマンドモード: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-231">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="6c8f4-232">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="6c8f4-232">InsertLineAbove</span></span>

<span data-ttu-id="6c8f4-233">現在の行の上にカーソルがある場所に関係なく、現在の行の上に新しい空の行が作成されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-233">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="6c8f4-234">カーソルが新しい行の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-234">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="6c8f4-235">コマンド: `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-235">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="6c8f4-236">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="6c8f4-236">InsertLineBelow</span></span>

<span data-ttu-id="6c8f4-237">カーソルが現在の行にある場所に関係なく、現在の行の下に新しい空の行が作成されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-237">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="6c8f4-238">カーソルが新しい行の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-238">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="6c8f4-239">コマンド: `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-239">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="6c8f4-240">InvertCase</span><span class="sxs-lookup"><span data-stu-id="6c8f4-240">InvertCase</span></span>

<span data-ttu-id="6c8f4-241">現在の文字の大文字と小文字の区別を反転し、次の文字に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-241">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="6c8f4-242">Vi コマンドモード: `<~>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-242">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="6c8f4-243">行の行</span><span class="sxs-lookup"><span data-stu-id="6c8f4-243">KillLine</span></span>

<span data-ttu-id="6c8f4-244">カーソルから入力の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-244">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="6c8f4-245">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-245">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="6c8f4-246">.Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-246">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="6c8f4-247">"/" 領域</span><span class="sxs-lookup"><span data-stu-id="6c8f4-247">KillRegion</span></span>

<span data-ttu-id="6c8f4-248">カーソルとマークの間のテキストを強制終了します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-248">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="6c8f4-249">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-249">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="6c8f4-250">文字の候補</span><span class="sxs-lookup"><span data-stu-id="6c8f4-250">KillWord</span></span>

<span data-ttu-id="6c8f4-251">カーソルから現在の単語の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-251">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="6c8f4-252">カーソルが単語の間にある場合は、カーソルから次の単語の末尾まで、入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-252">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="6c8f4-253">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-253">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="6c8f4-254">Cmd: `<Alt+d>` 、 `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-254">Cmd: `<Alt+d>`, `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="6c8f4-255">Emacs: `<Alt+d>` 、 `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-255">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="6c8f4-256">Vi の挿入モード: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-256">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="6c8f4-257">Vi コマンドモード: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-257">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="6c8f4-258">貼り付け</span><span class="sxs-lookup"><span data-stu-id="6c8f4-258">Paste</span></span>

<span data-ttu-id="6c8f4-259">システムクリップボードからテキストを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-259">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="6c8f4-260">Cmd: `<Ctrl+v>` 、 `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-260">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="6c8f4-261">Vi の挿入モード: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-261">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="6c8f4-262">Vi コマンドモード: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-262">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c8f4-263">**貼り付け** 関数を使用すると、クリップボードバッファーの内容全体が psreadline の入力バッファーに貼り付けられます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-263">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="6c8f4-264">入力バッファーが PowerShell パーサーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-264">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="6c8f4-265">コンソールアプリケーションの **右クリック** による貼り付けメソッドを使用して貼り付けた入力は、一度に1文字ずつ入力バッファーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-265">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="6c8f4-266">入力バッファーは、改行文字がコピーされるときにパーサーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-266">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="6c8f4-267">そのため、入力は一度に1行ずつ解析されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-267">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="6c8f4-268">貼り付けメソッドの違いによって、実行の動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-268">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="6c8f4-269">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="6c8f4-269">PasteAfter</span></span>

<span data-ttu-id="6c8f4-270">カーソルの後にクリップボードを貼り付けて、貼り付けられたテキストの末尾にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-270">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="6c8f4-271">Vi コマンドモード: `<p>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-271">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="6c8f4-272">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="6c8f4-272">PasteBefore</span></span>

<span data-ttu-id="6c8f4-273">カーソルの前にクリップボードを貼り付けて、貼り付けられたテキストの末尾にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-273">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="6c8f4-274">Vi コマンドモード: `<P>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-274">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="6c8f4-275">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="6c8f4-275">PrependAndAccept</span></span>

<span data-ttu-id="6c8f4-276">' # ' を先頭に付加し、その行を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-276">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="6c8f4-277">Vi コマンドモード: `<#>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-277">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="6c8f4-278">やり直し</span><span class="sxs-lookup"><span data-stu-id="6c8f4-278">Redo</span></span>

<span data-ttu-id="6c8f4-279">元に戻す操作を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-279">Undo an undo.</span></span>

- <span data-ttu-id="6c8f4-280">コマンド: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-280">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="6c8f4-281">Vi の挿入モード: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-281">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="6c8f4-282">Vi コマンドモード: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-282">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="6c8f4-283">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="6c8f4-283">RepeatLastCommand</span></span>

<span data-ttu-id="6c8f4-284">最後のテキストの変更を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-284">Repeat the last text modification.</span></span>

- <span data-ttu-id="6c8f4-285">Vi コマンドモード: `<.>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-285">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="6c8f4-286">再有効化</span><span class="sxs-lookup"><span data-stu-id="6c8f4-286">RevertLine</span></span>

<span data-ttu-id="6c8f4-287">すべての入力を現在の入力に戻します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-287">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="6c8f4-288">コマンド: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-288">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="6c8f4-289">Emacs: `<Alt+r>` 、 `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-289">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="6c8f4-290">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-290">ShellBackwardKillWord</span></span>

<span data-ttu-id="6c8f4-291">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-291">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="6c8f4-292">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-292">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="6c8f4-293">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-293">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="6c8f4-294">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-294">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="6c8f4-295">Shellは Word</span><span class="sxs-lookup"><span data-stu-id="6c8f4-295">ShellKillWord</span></span>

<span data-ttu-id="6c8f4-296">カーソルから現在の単語の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-296">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="6c8f4-297">カーソルが単語の間にある場合は、カーソルから次の単語の末尾まで、入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-297">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="6c8f4-298">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-298">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="6c8f4-299">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-299">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="6c8f4-300">スワップ文字</span><span class="sxs-lookup"><span data-stu-id="6c8f4-300">SwapCharacters</span></span>

<span data-ttu-id="6c8f4-301">現在の文字とそれより前の文字を交換します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-301">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="6c8f4-302">.Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-302">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="6c8f4-303">Vi の挿入モード: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-303">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="6c8f4-304">Vi コマンドモード: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-304">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="6c8f4-305">元に戻す</span><span class="sxs-lookup"><span data-stu-id="6c8f4-305">Undo</span></span>

<span data-ttu-id="6c8f4-306">前の編集を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-306">Undo a previous edit.</span></span>

- <span data-ttu-id="6c8f4-307">コマンド: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-307">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="6c8f4-308">Emacs: `<Ctrl+_>` 、 `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-308">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="6c8f4-309">Vi の挿入モード: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-309">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="6c8f4-310">Vi コマンドモード: `<Ctrl+z>` 、 `<u>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-310">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="6c8f4-311">UndoAll</span><span class="sxs-lookup"><span data-stu-id="6c8f4-311">UndoAll</span></span>

<span data-ttu-id="6c8f4-312">行の以前の編集をすべて元に戻します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-312">Undo all previous edits for line.</span></span>

- <span data-ttu-id="6c8f4-313">Vi コマンドモード: `<U>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-313">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="6c8f4-314">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="6c8f4-314">UnixWordRubout</span></span>

<span data-ttu-id="6c8f4-315">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-315">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="6c8f4-316">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-316">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="6c8f4-317">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-317">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="6c8f4-318">.Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-318">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="6c8f4-319">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-319">ValidateAndAcceptLine</span></span>

<span data-ttu-id="6c8f4-320">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-320">Attempt to execute the current input.</span></span> <span data-ttu-id="6c8f4-321">現在の入力が不完全な場合 (たとえば、終わりかっこ、角かっこ、または引用符がない場合)、継続のプロンプトは次の行に表示され、PSReadLine は現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-321">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="6c8f4-322">.Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-322">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="6c8f4-323">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-323">ViAcceptLine</span></span>

<span data-ttu-id="6c8f4-324">行を受け入れ、挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-324">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="6c8f4-325">Vi コマンドモード: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-325">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="6c8f4-326">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="6c8f4-326">ViAcceptLineOrExit</span></span>

<span data-ttu-id="6c8f4-327">(Emacs モードでは Deleと同じですが、文字を削除するのではなく、行を受け取ります)。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-327">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="6c8f4-328">Vi の挿入モード: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-328">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="6c8f4-329">Vi コマンドモード: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-329">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="6c8f4-330">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-330">ViAppendLine</span></span>

<span data-ttu-id="6c8f4-331">現在の行の下に新しい行が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-331">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="6c8f4-332">Vi コマンドモード: `<o>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-332">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="6c8f4-333">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="6c8f4-333">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="6c8f4-334">単語区切り記号として空白文字のみを使用して、前の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-334">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="6c8f4-335">Vi コマンドモード: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-335">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="6c8f4-336">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="6c8f4-336">ViBackwardGlob</span></span>

<span data-ttu-id="6c8f4-337">区切り記号として空白文字のみを使用して、カーソルを前の単語の先頭に戻します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-337">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="6c8f4-338">Vi コマンドモード: `<B>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-338">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="6c8f4-339">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="6c8f4-339">ViDeleteBrace</span></span>

<span data-ttu-id="6c8f4-340">対応する中かっこ、かっこ、または角かっこを検索し、中かっこを含め、内のすべての内容を削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-340">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="6c8f4-341">Vi コマンドモード: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-341">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="6c8f4-342">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="6c8f4-342">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="6c8f4-343">単語の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-343">Delete to the end of the word.</span></span>

- <span data-ttu-id="6c8f4-344">Vi コマンドモード: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-344">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="6c8f4-345">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="6c8f4-345">ViDeleteGlob</span></span>

<span data-ttu-id="6c8f4-346">次の glob (空白で区切られた単語) を削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-346">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="6c8f4-347">Vi コマンドモード: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-347">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="6c8f4-348">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="6c8f4-348">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="6c8f4-349">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-349">Deletes until given character.</span></span>

- <span data-ttu-id="6c8f4-350">Vi コマンドモード: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-350">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="6c8f4-351">Videletetobeforo</span><span class="sxs-lookup"><span data-stu-id="6c8f4-351">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="6c8f4-352">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-352">Deletes until given character.</span></span>

- <span data-ttu-id="6c8f4-353">Vi コマンドモード: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-353">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="6c8f4-354">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="6c8f4-354">ViDeleteToChar</span></span>

<span data-ttu-id="6c8f4-355">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-355">Deletes until given character.</span></span>

- <span data-ttu-id="6c8f4-356">Vi コマンドモード: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-356">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="6c8f4-357">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="6c8f4-357">ViDeleteToCharBackward</span></span>

<span data-ttu-id="6c8f4-358">指定された文字まで後方を削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-358">Deletes backwards until given character.</span></span>

- <span data-ttu-id="6c8f4-359">Vi コマンドモード: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-359">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="6c8f4-360">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="6c8f4-360">ViInsertAtBegining</span></span>

<span data-ttu-id="6c8f4-361">挿入モードに切り替え、カーソルを行の先頭に配置します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-361">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="6c8f4-362">Vi コマンドモード: `<I>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-362">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="6c8f4-363">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="6c8f4-363">ViInsertAtEnd</span></span>

<span data-ttu-id="6c8f4-364">挿入モードに切り替え、カーソルを行の末尾に配置します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-364">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="6c8f4-365">Vi コマンドモード: `<A>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-365">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="6c8f4-366">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-366">ViInsertLine</span></span>

<span data-ttu-id="6c8f4-367">現在の行の上に新しい行が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-367">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="6c8f4-368">Vi コマンドモード: `<O>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-368">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="6c8f4-369">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="6c8f4-369">ViInsertWithAppend</span></span>

<span data-ttu-id="6c8f4-370">現在の行の位置から追加します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-370">Append from the current line position.</span></span>

- <span data-ttu-id="6c8f4-371">Vi コマンドモード: `<a>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-371">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="6c8f4-372">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="6c8f4-372">ViInsertWithDelete</span></span>

<span data-ttu-id="6c8f4-373">現在の文字を削除し、挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-373">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="6c8f4-374">Vi コマンドモード: `<s>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-374">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="6c8f4-375">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="6c8f4-375">ViJoinLines</span></span>

<span data-ttu-id="6c8f4-376">現在の行と次の行を結合します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-376">Joins the current line and the next line.</span></span>

- <span data-ttu-id="6c8f4-377">Vi コマンドモード: `<J>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-377">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="6c8f4-378">交換ライン</span><span class="sxs-lookup"><span data-stu-id="6c8f4-378">ViReplaceLine</span></span>

<span data-ttu-id="6c8f4-379">コマンドライン全体を消去します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-379">Erase the entire command line.</span></span>

- <span data-ttu-id="6c8f4-380">Vi コマンドモード: `<S>` 、 `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-380">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="6c8f4-381">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="6c8f4-381">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="6c8f4-382">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-382">Replaces until given character.</span></span>

- <span data-ttu-id="6c8f4-383">Vi コマンドモード: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-383">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="6c8f4-384">Vireplacetobeforo</span><span class="sxs-lookup"><span data-stu-id="6c8f4-384">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="6c8f4-385">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-385">Replaces until given character.</span></span>

- <span data-ttu-id="6c8f4-386">Vi コマンドモード: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-386">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="6c8f4-387">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="6c8f4-387">ViReplaceToChar</span></span>

<span data-ttu-id="6c8f4-388">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-388">Deletes until given character.</span></span>

- <span data-ttu-id="6c8f4-389">Vi コマンドモード: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-389">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="6c8f4-390">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="6c8f4-390">ViReplaceToCharBackward</span></span>

<span data-ttu-id="6c8f4-391">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-391">Replaces until given character.</span></span>

- <span data-ttu-id="6c8f4-392">Vi コマンドモード: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-392">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="6c8f4-393">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-393">ViYankBeginningOfLine</span></span>

<span data-ttu-id="6c8f4-394">バッファーの先頭からカーソルまで Yank。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-394">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="6c8f4-395">Vi コマンドモード: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-395">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="6c8f4-396">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="6c8f4-396">ViYankEndOfGlob</span></span>

<span data-ttu-id="6c8f4-397">カーソルから単語の末尾まで Yank します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-397">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="6c8f4-398">Vi コマンドモード: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-398">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="6c8f4-399">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-399">ViYankEndOfWord</span></span>

<span data-ttu-id="6c8f4-400">カーソルから単語の末尾まで Yank します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-400">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="6c8f4-401">Vi コマンドモード: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-401">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="6c8f4-402">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="6c8f4-402">ViYankLeft</span></span>

<span data-ttu-id="6c8f4-403">カーソルの左側の文字を Yank します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-403">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="6c8f4-404">Vi コマンドモード: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-404">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="6c8f4-405">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-405">ViYankLine</span></span>

<span data-ttu-id="6c8f4-406">バッファー全体を Yank します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-406">Yank the entire buffer.</span></span>

- <span data-ttu-id="6c8f4-407">Vi コマンドモード: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-407">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="6c8f4-408">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="6c8f4-408">ViYankNextGlob</span></span>

<span data-ttu-id="6c8f4-409">Yank は、次の単語の先頭にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-409">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="6c8f4-410">Vi コマンドモード: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-410">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="6c8f4-411">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-411">ViYankNextWord</span></span>

<span data-ttu-id="6c8f4-412">カーソルの後の単語を Yank します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-412">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="6c8f4-413">Vi コマンドモード: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-413">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="6c8f4-414">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="6c8f4-414">ViYankPercent</span></span>

<span data-ttu-id="6c8f4-415">一致する中かっこを Yank します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-415">Yank to/from matching brace.</span></span>

- <span data-ttu-id="6c8f4-416">Vi コマンドモード: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-416">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="6c8f4-417">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="6c8f4-417">ViYankPreviousGlob</span></span>

<span data-ttu-id="6c8f4-418">Yank は、単語の先頭からカーソルになります。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-418">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="6c8f4-419">Vi コマンドモード: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-419">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="6c8f4-420">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-420">ViYankPreviousWord</span></span>

<span data-ttu-id="6c8f4-421">カーソルの前に単語を Yank します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-421">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="6c8f4-422">Vi コマンドモード: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-422">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="6c8f4-423">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="6c8f4-423">ViYankRight</span></span>

<span data-ttu-id="6c8f4-424">カーソルの右側に Yank 文字があります。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-424">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="6c8f4-425">Vi コマンドモード: `<y,l>` 、 `<y,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-425">Vi command mode: `<y,l>`, `<y,Spacebar>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="6c8f4-426">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-426">ViYankToEndOfLine</span></span>

<span data-ttu-id="6c8f4-427">カーソルからバッファーの末尾までの Yank。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-427">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="6c8f4-428">Vi コマンドモード: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-428">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="6c8f4-429">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="6c8f4-429">ViYankToFirstChar</span></span>

<span data-ttu-id="6c8f4-430">最初の空白以外の文字からカーソルまで Yank ます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-430">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="6c8f4-431">Vi コマンドモード: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-431">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="6c8f4-432">Yank</span><span class="sxs-lookup"><span data-stu-id="6c8f4-432">Yank</span></span>

<span data-ttu-id="6c8f4-433">最後に終了したテキストを入力に追加します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-433">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="6c8f4-434">.Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-434">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="6c8f4-435">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="6c8f4-435">YankLastArg</span></span>

<span data-ttu-id="6c8f4-436">前の履歴行の最後の引数を Yank します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-436">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="6c8f4-437">引数を使用すると、最初に呼び出されたときに、YankNthArg と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-437">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="6c8f4-438">複数回呼び出された場合は、代わりに履歴を反復処理し、引数に方向を設定します (負の方向が反転します)。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-438">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="6c8f4-439">コマンド: `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-439">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="6c8f4-440">Emacs: `<Alt+.>` 、 `<Alt+_>` 、 `<Escape,.>` 、 `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-440">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="6c8f4-441">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="6c8f4-441">YankNthArg</span></span>

<span data-ttu-id="6c8f4-442">Yank は、前の履歴行から (コマンドの後に) 最初の引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-442">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="6c8f4-443">引数を使用して、n 番目の引数 (0 から始まる) を yank します。引数が負の場合は、最後の引数から開始します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-443">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="6c8f4-444">Emacs: `<Ctrl+Alt+y>` 、 `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-444">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="6c8f4-445">YankPop</span><span class="sxs-lookup"><span data-stu-id="6c8f4-445">YankPop</span></span>

<span data-ttu-id="6c8f4-446">前の操作が Yank または YankPop であった場合は、以前の引き抜かテキストをキルリングから次に強制終了されたテキストに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-446">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="6c8f4-447">Emacs: `<Alt+y>` 、 `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-447">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="6c8f4-448">カーソルの移動関数</span><span class="sxs-lookup"><span data-stu-id="6c8f4-448">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="6c8f4-449">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="6c8f4-449">BackwardChar</span></span>

<span data-ttu-id="6c8f4-450">カーソルを1文字左に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-450">Move the cursor one character to the left.</span></span> <span data-ttu-id="6c8f4-451">これにより、カーソルが複数行の入力の前の行に移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-451">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="6c8f4-452">コマンド: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-452">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="6c8f4-453">Emacs: `<LeftArrow>` 、 `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-453">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="6c8f4-454">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-454">BackwardWord</span></span>

<span data-ttu-id="6c8f4-455">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-455">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="6c8f4-456">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-456">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="6c8f4-457">コマンド: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-457">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="6c8f4-458">Emacs: `<Alt+b>` 、 `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-458">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="6c8f4-459">Vi の挿入モード: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-459">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="6c8f4-460">Vi コマンドモード: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-460">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="6c8f4-461">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-461">BeginningOfLine</span></span>

<span data-ttu-id="6c8f4-462">入力に複数の行がある場合は、現在の行の先頭に移動します。または、既に行の先頭にある場合は、入力の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-462">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="6c8f4-463">入力に1行しか含まれていない場合は、入力の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-463">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="6c8f4-464">コマンド: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-464">Cmd: `<Home>`</span></span>
- <span data-ttu-id="6c8f4-465">Emacs: `<Home>` 、 `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-465">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="6c8f4-466">Vi の挿入モード: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-466">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="6c8f4-467">Vi コマンドモード: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-467">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="6c8f4-468">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-468">EndOfLine</span></span>

<span data-ttu-id="6c8f4-469">入力に複数の行がある場合は、現在の行の末尾に移動します。または、既に行の末尾にある場合は、入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-469">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="6c8f4-470">入力に1行しか含まれていない場合は、入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-470">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="6c8f4-471">コマンド: `<End>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-471">Cmd: `<End>`</span></span>
- <span data-ttu-id="6c8f4-472">Emacs: `<End>` 、 `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-472">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="6c8f4-473">Vi の挿入モード: `<End>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-473">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="6c8f4-474">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="6c8f4-474">ForwardChar</span></span>

<span data-ttu-id="6c8f4-475">カーソルを1文字右に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-475">Move the cursor one character to the right.</span></span> <span data-ttu-id="6c8f4-476">これにより、カーソルが複数行入力の次の行に移動する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-476">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="6c8f4-477">コマンド: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-477">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="6c8f4-478">Emacs: `<RightArrow>` 、 `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-478">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="6c8f4-479">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-479">ForwardWord</span></span>

<span data-ttu-id="6c8f4-480">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-480">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="6c8f4-481">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-481">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="6c8f4-482">Emacs: `<Alt+f>` 、 `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-482">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="6c8f4-483">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="6c8f4-483">GotoBrace</span></span>

<span data-ttu-id="6c8f4-484">対応する中かっこ、かっこ、または角かっこにジャンプします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-484">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="6c8f4-485">コマンド: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-485">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="6c8f4-486">Vi の挿入モード: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-486">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="6c8f4-487">Vi コマンドモード: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-487">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="6c8f4-488">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="6c8f4-488">GotoColumn</span></span>

<span data-ttu-id="6c8f4-489">Arg で示される列に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-489">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="6c8f4-490">Vi コマンドモード: `<|>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-490">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="6c8f4-491">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-491">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="6c8f4-492">カーソルを行の空白以外の最初の文字に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-492">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="6c8f4-493">Vi コマンドモード: `<^>` 、 `<_>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-493">Vi command mode: `<^>`, `<_>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="6c8f4-494">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-494">MoveToEndOfLine</span></span>

<span data-ttu-id="6c8f4-495">カーソルを入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-495">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="6c8f4-496">Vi コマンドモード: `<End>` 、 `<$>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-496">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="6c8f4-497">NextLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-497">NextLine</span></span>

<span data-ttu-id="6c8f4-498">カーソルを次の行に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-498">Move the cursor to the next line.</span></span>

- <span data-ttu-id="6c8f4-499">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-499">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="6c8f4-500">NextWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-500">NextWord</span></span>

<span data-ttu-id="6c8f4-501">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-501">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="6c8f4-502">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-502">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="6c8f4-503">コマンド: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-503">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="6c8f4-504">Vi の挿入モード: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-504">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="6c8f4-505">Vi コマンドモード: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-505">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="6c8f4-506">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="6c8f4-506">NextWordEnd</span></span>

<span data-ttu-id="6c8f4-507">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-507">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="6c8f4-508">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-508">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="6c8f4-509">Vi コマンドモード: `<e>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-509">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="6c8f4-510">前の行</span><span class="sxs-lookup"><span data-stu-id="6c8f4-510">PreviousLine</span></span>

<span data-ttu-id="6c8f4-511">カーソルを前の行に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-511">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="6c8f4-512">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-512">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="6c8f4-513">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-513">ShellBackwardWord</span></span>

<span data-ttu-id="6c8f4-514">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-514">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="6c8f4-515">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-515">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="6c8f4-516">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-516">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="6c8f4-517">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-517">ShellForwardWord</span></span>

<span data-ttu-id="6c8f4-518">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-518">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="6c8f4-519">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-519">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="6c8f4-520">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-520">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="6c8f4-521">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-521">ShellNextWord</span></span>

<span data-ttu-id="6c8f4-522">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-522">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="6c8f4-523">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-523">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="6c8f4-524">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-524">Function is unbound.</span></span>

### <a name="vibackwardchar"></a><span data-ttu-id="6c8f4-525">ViBackwardChar</span><span class="sxs-lookup"><span data-stu-id="6c8f4-525">ViBackwardChar</span></span>

<span data-ttu-id="6c8f4-526">Vi 編集モードでカーソルを1文字左に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-526">Move the cursor one character to the left in the Vi edit mode.</span></span> <span data-ttu-id="6c8f4-527">これにより、カーソルが複数行の入力の前の行に移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-527">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="6c8f4-528">Vi の挿入モード: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-528">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="6c8f4-529">Vi コマンドモード: `<LeftArrow>` 、 `<Backspace>` 、 `<h>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-529">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="6c8f4-530">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-530">ViBackwardWord</span></span>

<span data-ttu-id="6c8f4-531">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-531">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="6c8f4-532">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-532">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="6c8f4-533">Vi コマンドモード: `<b>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-533">Vi command mode: `<b>`</span></span>

### <a name="viforwardchar"></a><span data-ttu-id="6c8f4-534">ViForwardChar</span><span class="sxs-lookup"><span data-stu-id="6c8f4-534">ViForwardChar</span></span>

<span data-ttu-id="6c8f4-535">Vi 編集モードでカーソルを1文字右に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-535">Move the cursor one character to the right in the Vi edit mode.</span></span> <span data-ttu-id="6c8f4-536">これにより、カーソルが複数行入力の次の行に移動する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-536">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="6c8f4-537">Vi の挿入モード: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-537">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="6c8f4-538">Vi コマンドモード: `<RightArrow>` 、 `<Spacebar>` 、 `<l>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-538">Vi command mode: `<RightArrow>`, `<Spacebar>`, `<l>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="6c8f4-539">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="6c8f4-539">ViEndOfGlob</span></span>

<span data-ttu-id="6c8f4-540">区切り記号として空白文字のみを使用して、カーソルを単語の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-540">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="6c8f4-541">Vi コマンドモード: `<E>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-541">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="6c8f4-542">Viendofの Glob</span><span class="sxs-lookup"><span data-stu-id="6c8f4-542">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="6c8f4-543">単語区切り記号として空白文字のみを使用して、前の単語の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-543">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="6c8f4-544">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-544">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="6c8f4-545">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="6c8f4-545">ViGotoBrace</span></span>

<span data-ttu-id="6c8f4-546">GotoBrace に似ていますが、トークンベースではなく文字ベースです。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-546">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="6c8f4-547">Vi コマンドモード: `<%>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-547">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="6c8f4-548">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="6c8f4-548">ViNextGlob</span></span>

<span data-ttu-id="6c8f4-549">単語区切り記号として空白文字のみを使用して、次の単語に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-549">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="6c8f4-550">Vi コマンドモード: `<W>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-550">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="6c8f4-551">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-551">ViNextWord</span></span>

<span data-ttu-id="6c8f4-552">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-552">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="6c8f4-553">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-553">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="6c8f4-554">Vi コマンドモード: `<w>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-554">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="6c8f4-555">履歴関数</span><span class="sxs-lookup"><span data-stu-id="6c8f4-555">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="6c8f4-556">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="6c8f4-556">BeginningOfHistory</span></span>

<span data-ttu-id="6c8f4-557">履歴内の最初の項目に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-557">Move to the first item in the history.</span></span>

- <span data-ttu-id="6c8f4-558">.Emacs `<Alt+<>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-558">Emacs: `<Alt+<>`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="6c8f4-559">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="6c8f4-559">ClearHistory</span></span>

<span data-ttu-id="6c8f4-560">PSReadLine の履歴をクリアします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-560">Clears history in PSReadLine.</span></span> <span data-ttu-id="6c8f4-561">これは、PowerShell の履歴には影響しません。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-561">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="6c8f4-562">コマンド: `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-562">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="6c8f4-563">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="6c8f4-563">EndOfHistory</span></span>

<span data-ttu-id="6c8f4-564">履歴内の最後の項目 (現在の入力) に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-564">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="6c8f4-565">.Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-565">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="6c8f4-566">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="6c8f4-566">ForwardSearchHistory</span></span>

<span data-ttu-id="6c8f4-567">履歴を使用した増分転送検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-567">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="6c8f4-568">コマンド: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-568">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="6c8f4-569">.Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-569">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="6c8f4-570">履歴の Search後方</span><span class="sxs-lookup"><span data-stu-id="6c8f4-570">HistorySearchBackward</span></span>

<span data-ttu-id="6c8f4-571">現在の入力を、PSReadLine 履歴の ' previous ' 項目で置き換えます。この項目は、開始と入力の間の文字とカーソルの間の文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-571">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="6c8f4-572">コマンド: `<F8>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-572">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="6c8f4-573">履歴の Searchforward</span><span class="sxs-lookup"><span data-stu-id="6c8f4-573">HistorySearchForward</span></span>

<span data-ttu-id="6c8f4-574">現在の入力を、PSReadLine 履歴の ' next ' 項目で置き換えます。この項目は、開始と入力の間の文字とカーソルの間の文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-574">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="6c8f4-575">コマンド: `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-575">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="6c8f4-576">NextHistory</span><span class="sxs-lookup"><span data-stu-id="6c8f4-576">NextHistory</span></span>

<span data-ttu-id="6c8f4-577">現在の入力を、PSReadLine 履歴の ' next ' 項目に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-577">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="6c8f4-578">コマンド: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-578">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="6c8f4-579">Emacs: `<DownArrow>` 、 `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-579">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="6c8f4-580">Vi の挿入モード: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-580">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="6c8f4-581">Vi コマンドモード: `<DownArrow>` 、 `<j>` 、 `<+>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-581">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="6c8f4-582">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="6c8f4-582">PreviousHistory</span></span>

<span data-ttu-id="6c8f4-583">現在の入力を、PSReadLine 履歴の ' previous ' 項目に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-583">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="6c8f4-584">コマンド: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-584">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="6c8f4-585">Emacs: `<UpArrow>` 、 `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-585">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="6c8f4-586">Vi の挿入モード: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-586">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="6c8f4-587">Vi コマンドモード: `<UpArrow>` 、 `<k>` 、 `<->`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-587">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="6c8f4-588">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="6c8f4-588">ReverseSearchHistory</span></span>

<span data-ttu-id="6c8f4-589">履歴を介して後方検索を段階的に実行します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-589">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="6c8f4-590">コマンド: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-590">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="6c8f4-591">.Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-591">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="6c8f4-592">Visearchhistory 後方</span><span class="sxs-lookup"><span data-stu-id="6c8f4-592">ViSearchHistoryBackward</span></span>

<span data-ttu-id="6c8f4-593">検索文字列を入力し、AcceptLine で検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-593">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="6c8f4-594">Vi の挿入モード: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-594">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="6c8f4-595">Vi コマンドモード: `</>` 、 `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-595">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="6c8f4-596">入力候補関数</span><span class="sxs-lookup"><span data-stu-id="6c8f4-596">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="6c8f4-597">完了</span><span class="sxs-lookup"><span data-stu-id="6c8f4-597">Complete</span></span>

<span data-ttu-id="6c8f4-598">カーソルを囲むテキストに対して入力候補を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-598">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="6c8f4-599">候補が複数ある場合は、最長の明確なプレフィックスを使用して完了します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-599">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="6c8f4-600">最長の明確な完了を完了しようとすると、候補の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-600">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="6c8f4-601">.Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-601">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="6c8f4-602">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="6c8f4-602">MenuComplete</span></span>

<span data-ttu-id="6c8f4-603">カーソルを囲むテキストに対して入力候補を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-603">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="6c8f4-604">候補が複数ある場合は、最長の明確なプレフィックスを使用して完了します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-604">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="6c8f4-605">最長の明確な完了を完了しようとすると、候補の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-605">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="6c8f4-606">Cmd: `<Ctrl+@>` 、 `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-606">Cmd: `<Ctrl+@>`, `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="6c8f4-607">.Emacs `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-607">Emacs: `<Ctrl+Spacebar>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="6c8f4-608">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="6c8f4-608">PossibleCompletions</span></span>

<span data-ttu-id="6c8f4-609">候補の候補の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-609">Display the list of possible completions.</span></span>

- <span data-ttu-id="6c8f4-610">.Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-610">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="6c8f4-611">Vi の挿入モード: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-611">Vi insert mode: `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="6c8f4-612">Vi コマンドモード: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-612">Vi command mode: `<Ctrl+Spacebar>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="6c8f4-613">タブのすべてのタブ</span><span class="sxs-lookup"><span data-stu-id="6c8f4-613">TabCompleteNext</span></span>

<span data-ttu-id="6c8f4-614">次に使用可能な完了時に、カーソルを囲むテキストを完了します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-614">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="6c8f4-615">コマンド: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-615">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="6c8f4-616">Vi コマンドモード: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-616">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="6c8f4-617">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="6c8f4-617">TabCompletePrevious</span></span>

<span data-ttu-id="6c8f4-618">以前に使用可能な入力候補を使用して、カーソルを囲むテキストを完了しようとしました。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-618">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="6c8f4-619">コマンド: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-619">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="6c8f4-620">Vi コマンドモード: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-620">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="6c8f4-621">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="6c8f4-621">ViTabCompleteNext</span></span>

<span data-ttu-id="6c8f4-622">必要に応じて現在の編集グループを終了し、Tabends を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-622">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="6c8f4-623">Vi の挿入モード: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-623">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="6c8f4-624">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="6c8f4-624">ViTabCompletePrevious</span></span>

<span data-ttu-id="6c8f4-625">必要に応じて現在の編集グループを終了し、TabCompletePrevious を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-625">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="6c8f4-626">Vi の挿入モード: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-626">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="6c8f4-627">その他の関数</span><span class="sxs-lookup"><span data-stu-id="6c8f4-627">Miscellaneous functions</span></span>

### <a name="acceptnextsuggestionword"></a><span data-ttu-id="6c8f4-628">AcceptNextSuggestionWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-628">AcceptNextSuggestionWord</span></span>

<span data-ttu-id="6c8f4-629">インラインまたは選択した修正候補の次の単語をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-629">Accept the next word of the inline or selected suggestion.</span></span>

- <span data-ttu-id="6c8f4-630">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-630">Function is unbound.</span></span>

### <a name="acceptsuggestion"></a><span data-ttu-id="6c8f4-631">AcceptSuggestion</span><span class="sxs-lookup"><span data-stu-id="6c8f4-631">AcceptSuggestion</span></span>

<span data-ttu-id="6c8f4-632">現在のインラインまたは選択された提案を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-632">Accept the current inline or selected suggestion.</span></span>

- <span data-ttu-id="6c8f4-633">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-633">Function is unbound.</span></span>

### <a name="capturescreen"></a><span data-ttu-id="6c8f4-634">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="6c8f4-634">CaptureScreen</span></span>

<span data-ttu-id="6c8f4-635">対話型画面のキャプチャを開始する/下矢印行を選択し、[選択したテキストをテキストと html としてクリップボードにコピーする] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-635">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="6c8f4-636">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-636">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="6c8f4-637">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="6c8f4-637">ClearScreen</span></span>

<span data-ttu-id="6c8f4-638">画面をクリアし、画面の上部にある現在の線を描画します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-638">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="6c8f4-639">コマンド: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-639">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="6c8f4-640">.Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-640">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="6c8f4-641">Vi の挿入モード: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-641">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="6c8f4-642">Vi コマンドモード: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-642">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="6c8f4-643">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="6c8f4-643">DigitArgument</span></span>

<span data-ttu-id="6c8f4-644">他の関数に渡す新しい桁引数を開始します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-644">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="6c8f4-645">Cmd:、、、、、、、、、 `<Alt+0>` `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-645">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="6c8f4-646">Emacs:、、、、、、、、、 `<Alt+0>` `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-646">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="6c8f4-647">Vi コマンドモード:、、、、、、、、 `<0>` `<1>` `<2>` `<3>` `<4>` `<5>` `<6>` `<7>` `<8>` 、 `<9>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-647">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="6c8f4-648">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="6c8f4-648">InvokePrompt</span></span>

<span data-ttu-id="6c8f4-649">現在のプロンプトを消去し、prompt 関数を呼び出してプロンプトを再表示します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-649">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="6c8f4-650">現在のディレクトリを変更するなど、状態を変更するカスタムキーハンドラーに便利です。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-650">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="6c8f4-651">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-651">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="6c8f4-652">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="6c8f4-652">ScrollDisplayDown</span></span>

<span data-ttu-id="6c8f4-653">画面を1画面下へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-653">Scroll the display down one screen.</span></span>

- <span data-ttu-id="6c8f4-654">コマンド: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-654">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="6c8f4-655">.Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-655">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="6c8f4-656">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-656">ScrollDisplayDownLine</span></span>

<span data-ttu-id="6c8f4-657">表示を1行下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-657">Scroll the display down one line.</span></span>

- <span data-ttu-id="6c8f4-658">コマンド: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-658">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="6c8f4-659">.Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-659">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="6c8f4-660">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="6c8f4-660">ScrollDisplayToCursor</span></span>

<span data-ttu-id="6c8f4-661">カーソルまで画面をスクロールします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-661">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="6c8f4-662">.Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-662">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="6c8f4-663">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="6c8f4-663">ScrollDisplayTop</span></span>

<span data-ttu-id="6c8f4-664">画面を上にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-664">Scroll the display to the top.</span></span>

- <span data-ttu-id="6c8f4-665">.Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-665">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="6c8f4-666">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="6c8f4-666">ScrollDisplayUp</span></span>

<span data-ttu-id="6c8f4-667">画面を1画面上へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-667">Scroll the display up one screen.</span></span>

- <span data-ttu-id="6c8f4-668">コマンド: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-668">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="6c8f4-669">.Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-669">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="6c8f4-670">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-670">ScrollDisplayUpLine</span></span>

<span data-ttu-id="6c8f4-671">表示を1行上へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-671">Scroll the display up one line.</span></span>

- <span data-ttu-id="6c8f4-672">コマンド: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-672">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="6c8f4-673">.Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-673">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="6c8f4-674">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="6c8f4-674">SelfInsert</span></span>

<span data-ttu-id="6c8f4-675">キーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-675">Insert the key.</span></span>

- <span data-ttu-id="6c8f4-676">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-676">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="6c8f4-677">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="6c8f4-677">ShowKeyBindings</span></span>

<span data-ttu-id="6c8f4-678">すべてのバインドされたキーを表示します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-678">Show all bound keys.</span></span>

- <span data-ttu-id="6c8f4-679">コマンド: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-679">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="6c8f4-680">.Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-680">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="6c8f4-681">Vi の挿入モード: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-681">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="6c8f4-682">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="6c8f4-682">ViCommandMode</span></span>

<span data-ttu-id="6c8f4-683">現在の動作モードを Vi-Insert から Vi-Command に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-683">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="6c8f4-684">Vi の挿入モード: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-684">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="6c8f4-685">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-685">ViDigitArgumentInChord</span></span>

<span data-ttu-id="6c8f4-686">Vi のいずれかの弦で、他の関数に渡す新しい桁引数を開始します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-686">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="6c8f4-687">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-687">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="6c8f4-688">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="6c8f4-688">ViEditVisually</span></span>

<span data-ttu-id="6c8f4-689">$Env: EDITOR または $env: ビジュアルによって指定されたテキストエディターでコマンドラインを編集します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-689">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="6c8f4-690">.Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-690">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="6c8f4-691">Vi コマンドモード: `<v>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-691">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="6c8f4-692">ViExit</span><span class="sxs-lookup"><span data-stu-id="6c8f4-692">ViExit</span></span>

<span data-ttu-id="6c8f4-693">シェルを終了します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-693">Exits the shell.</span></span>

- <span data-ttu-id="6c8f4-694">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-694">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="6c8f4-695">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="6c8f4-695">ViInsertMode</span></span>

<span data-ttu-id="6c8f4-696">挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-696">Switch to Insert mode.</span></span>

- <span data-ttu-id="6c8f4-697">Vi コマンドモード: `<i>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-697">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="6c8f4-698">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="6c8f4-698">WhatIsKey</span></span>

<span data-ttu-id="6c8f4-699">キーを読み取り、キーがどのようにバインドされているかを通知します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-699">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="6c8f4-700">コマンド: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-700">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="6c8f4-701">.Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-701">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="6c8f4-702">選択関数</span><span class="sxs-lookup"><span data-stu-id="6c8f4-702">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="6c8f4-703">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="6c8f4-703">ExchangePointAndMark</span></span>

<span data-ttu-id="6c8f4-704">カーソルがマークの位置に置かれ、マークがカーソルの位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-704">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="6c8f4-705">.Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-705">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="6c8f4-706">SelectAll</span><span class="sxs-lookup"><span data-stu-id="6c8f4-706">SelectAll</span></span>

<span data-ttu-id="6c8f4-707">行全体を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-707">Select the entire line.</span></span>

- <span data-ttu-id="6c8f4-708">コマンド: `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-708">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="6c8f4-709">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="6c8f4-709">SelectBackwardChar</span></span>

<span data-ttu-id="6c8f4-710">現在の選択範囲を調整して、前の文字を含めます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-710">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="6c8f4-711">コマンド: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-711">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="6c8f4-712">.Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-712">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="6c8f4-713">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-713">SelectBackwardsLine</span></span>

<span data-ttu-id="6c8f4-714">カーソルから行の先頭まで、現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-714">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="6c8f4-715">コマンド: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-715">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="6c8f4-716">.Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-716">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="6c8f4-717">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-717">SelectBackwardWord</span></span>

<span data-ttu-id="6c8f4-718">現在の選択範囲を調整して、前の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-718">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="6c8f4-719">コマンド: `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-719">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="6c8f4-720">.Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-720">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="6c8f4-721">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="6c8f4-721">SelectForwardChar</span></span>

<span data-ttu-id="6c8f4-722">現在の選択範囲を調整して、次の文字を含めます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-722">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="6c8f4-723">コマンド: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-723">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="6c8f4-724">.Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-724">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="6c8f4-725">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-725">SelectForwardWord</span></span>

<span data-ttu-id="6c8f4-726">現在の選択範囲を調整して、ForwardWord を使用して次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-726">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="6c8f4-727">.Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-727">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="6c8f4-728">SelectLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-728">SelectLine</span></span>

<span data-ttu-id="6c8f4-729">カーソルから行の末尾まで、現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-729">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="6c8f4-730">コマンド: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-730">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="6c8f4-731">.Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-731">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="6c8f4-732">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-732">SelectNextWord</span></span>

<span data-ttu-id="6c8f4-733">現在の選択範囲を調整して、次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-733">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="6c8f4-734">コマンド: `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-734">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="6c8f4-735">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-735">SelectShellBackwardWord</span></span>

<span data-ttu-id="6c8f4-736">ShellBackwardWord を使用して、前の単語が含まれるように現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-736">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="6c8f4-737">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-737">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="6c8f4-738">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-738">SelectShellForwardWord</span></span>

<span data-ttu-id="6c8f4-739">現在の選択範囲を調整して、ShellForwardWord を使用する次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-739">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="6c8f4-740">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-740">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="6c8f4-741">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="6c8f4-741">SelectShellNextWord</span></span>

<span data-ttu-id="6c8f4-742">現在の選択範囲を調整して、ShellNextWord を使用して次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-742">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="6c8f4-743">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-743">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="6c8f4-744">SetMark</span><span class="sxs-lookup"><span data-stu-id="6c8f4-744">SetMark</span></span>

<span data-ttu-id="6c8f4-745">後続の編集コマンドで使用するために、カーソルの現在の位置をマークします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-745">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="6c8f4-746">.Emacs `<Ctrl+@>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-746">Emacs: `<Ctrl+@>`</span></span>

## <a name="search-functions"></a><span data-ttu-id="6c8f4-747">関数の検索</span><span class="sxs-lookup"><span data-stu-id="6c8f4-747">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="6c8f4-748">文字検索</span><span class="sxs-lookup"><span data-stu-id="6c8f4-748">CharacterSearch</span></span>

<span data-ttu-id="6c8f4-749">文字を読み取り、その文字が次に出現するまで検索します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-749">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="6c8f4-750">引数が指定されている場合は、n 番目のオカレンスに対して前方 (負の場合は後方) を検索します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-750">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="6c8f4-751">コマンド: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-751">Cmd: `<F3>`</span></span>
- <span data-ttu-id="6c8f4-752">.Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-752">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="6c8f4-753">Vi の挿入モード: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-753">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="6c8f4-754">Vi コマンドモード: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-754">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="6c8f4-755">文字 Search後方</span><span class="sxs-lookup"><span data-stu-id="6c8f4-755">CharacterSearchBackward</span></span>

<span data-ttu-id="6c8f4-756">文字を読み取り、その文字が次に出現するまで検索します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-756">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="6c8f4-757">引数が指定されている場合は、n 番目のオカレンスに対して後方 (または負の場合は forward) を検索します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-757">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="6c8f4-758">コマンド: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-758">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="6c8f4-759">.Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-759">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="6c8f4-760">Vi の挿入モード: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-760">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="6c8f4-761">Vi コマンドモード: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-761">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="6c8f4-762">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="6c8f4-762">RepeatLastCharSearch</span></span>

<span data-ttu-id="6c8f4-763">最後に記録された文字の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-763">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="6c8f4-764">Vi コマンドモード: `<;>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-764">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="6c8f4-765">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="6c8f4-765">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="6c8f4-766">最後に記録された文字検索を逆方向に繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-766">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="6c8f4-767">Vi コマンドモード: `<,>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-767">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="6c8f4-768">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="6c8f4-768">RepeatSearch</span></span>

<span data-ttu-id="6c8f4-769">前と同じ方向に最後の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-769">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="6c8f4-770">Vi コマンドモード: `<n>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-770">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="6c8f4-771">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="6c8f4-771">RepeatSearchBackward</span></span>

<span data-ttu-id="6c8f4-772">前と同じ方向に最後の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-772">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="6c8f4-773">Vi コマンドモード: `<N>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-773">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="6c8f4-774">SearchChar</span><span class="sxs-lookup"><span data-stu-id="6c8f4-774">SearchChar</span></span>

<span data-ttu-id="6c8f4-775">次の文字を読み取って検索し、次に文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-775">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="6c8f4-776">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-776">This is for 't' functionality.</span></span>

- <span data-ttu-id="6c8f4-777">Vi コマンドモード: `<f>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-777">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="6c8f4-778">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="6c8f4-778">SearchCharBackward</span></span>

<span data-ttu-id="6c8f4-779">次の文字を読み取り、それを検索して後方に移動し、次に文字を戻します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-779">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="6c8f4-780">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-780">This is for 'T' functionality.</span></span>

- <span data-ttu-id="6c8f4-781">Vi コマンドモード: `<F>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-781">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="6c8f4-782">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="6c8f4-782">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="6c8f4-783">次の文字を読み取り、それを検索して後方に移動し、次に文字を戻します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-783">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="6c8f4-784">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-784">This is for 'T' functionality.</span></span>

- <span data-ttu-id="6c8f4-785">Vi コマンドモード: `<T>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-785">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="6c8f4-786">SearchCharWithBackoff オフ</span><span class="sxs-lookup"><span data-stu-id="6c8f4-786">SearchCharWithBackoff</span></span>

<span data-ttu-id="6c8f4-787">次の文字を読み取って検索し、次に文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-787">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="6c8f4-788">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-788">This is for 't' functionality.</span></span>

- <span data-ttu-id="6c8f4-789">Vi コマンドモード: `<t>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-789">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="6c8f4-790">SearchForward</span><span class="sxs-lookup"><span data-stu-id="6c8f4-790">SearchForward</span></span>

<span data-ttu-id="6c8f4-791">検索文字列を入力し、AcceptLine で検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-791">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="6c8f4-792">Vi の挿入モード: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-792">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="6c8f4-793">Vi コマンドモード: `<?>` 、 `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="6c8f4-793">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="6c8f4-794">カスタムキーバインド</span><span class="sxs-lookup"><span data-stu-id="6c8f4-794">Custom Key Bindings</span></span>

<span data-ttu-id="6c8f4-795">PSReadLine は、コマンドレットを使用してカスタムキーバインドをサポートしてい `Set-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-795">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="6c8f4-796">ほとんどのカスタムキーバインドは、たとえば、上記の関数の1つを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-796">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="6c8f4-797">ScriptBlock をキーにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-797">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="6c8f4-798">ScriptBlock は、ほとんどすべてのことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-798">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="6c8f4-799">いくつかの便利な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-799">Some useful examples include</span></span>

- <span data-ttu-id="6c8f4-800">コマンドラインを編集する</span><span class="sxs-lookup"><span data-stu-id="6c8f4-800">edit the command line</span></span>
- <span data-ttu-id="6c8f4-801">新しいウィンドウを開く (例: ヘルプ)</span><span class="sxs-lookup"><span data-stu-id="6c8f4-801">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="6c8f4-802">コマンドラインを変更せずにディレクトリを変更する</span><span class="sxs-lookup"><span data-stu-id="6c8f4-802">change directories without changing the command line</span></span>

<span data-ttu-id="6c8f4-803">ScriptBlock は、次の2つの引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-803">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="6c8f4-804">`$key` -カスタムバインドをトリガーしたキーである **[Consolekeyinfo]** オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-804">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="6c8f4-805">同じ ScriptBlock を複数のキーにバインドし、キーに応じて異なるアクションを実行する必要がある場合は、$key を確認します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-805">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="6c8f4-806">多くのカスタムバインドでは、この引数は無視します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-806">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="6c8f4-807">`$arg` -任意の引数。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-807">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="6c8f4-808">多くの場合、これは、ユーザーがキーバインド DigitArgument から渡す整数引数になります。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-808">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="6c8f4-809">バインディングが引数を受け入れない場合は、この引数を無視するのが妥当です。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-809">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="6c8f4-810">ここでは、コマンドラインを実行せずに履歴に追加する例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-810">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="6c8f4-811">これは、何らかの操作を忘れた場合に、既に入力したコマンドラインを再入力したくない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-811">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="6c8f4-812">PSReadLine モジュールフォルダーにインストールされているファイルには、さらに多くの例が表示 `SamplePSReadLineProfile.ps1` されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-812">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="6c8f4-813">ほとんどのキーバインドでは、コマンドラインを編集するためにいくつかのヘルパー関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-813">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="6c8f4-814">これらの Api については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-814">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="6c8f4-815">カスタムキーバインディングサポート Api</span><span class="sxs-lookup"><span data-stu-id="6c8f4-815">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="6c8f4-816">次の関数は PSConsoleReadLine では公開されていますが、キーに直接バインドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-816">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="6c8f4-817">多くの場合、カスタムキーバインドに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-817">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="6c8f4-818">コマンドラインを実行せずに、履歴に追加します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-818">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="6c8f4-819">Kill リングをクリアします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-819">Clear the kill-ring.</span></span>  <span data-ttu-id="6c8f4-820">これは主にテストに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-820">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="6c8f4-821">先頭から長さの文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-821">Delete length characters from start.</span></span>  <span data-ttu-id="6c8f4-822">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-822">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="6c8f4-823">ユーザー設定に基づいてアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-823">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="6c8f4-824">これらの2つの関数は、入力バッファーの現在の状態に関する有用な情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-824">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="6c8f4-825">1つ目は、単純なケースでよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-825">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="6c8f4-826">2つ目は、バインディングが Ast を使用してより高度な処理を実行している場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-826">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(string[] Chord)
```

<span data-ttu-id="6c8f4-827">この2つの関数は、によって使用され `Get-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-827">These two functions are used by `Get-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="6c8f4-828">最初のは、すべてのキーバインドを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-828">The first is used to get all key bindings.</span></span> <span data-ttu-id="6c8f4-829">2番目のは、特定のキーバインドを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-829">The second is used to get specific key bindings.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="6c8f4-830">この関数は Get-PSReadLineOption によって使用され、カスタムキーバインドではあまり役に立たない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-830">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="6c8f4-831">コマンドラインに何も選択されていない場合は、開始と長さの両方で-1 が返されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-831">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="6c8f4-832">コマンドラインに選択項目がある場合は、選択範囲の先頭と長さが返されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-832">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="6c8f4-833">カーソル位置に文字または文字列を挿入します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-833">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="6c8f4-834">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-834">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="6c8f4-835">これは、PSReadLine へのメインエントリポイントです。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-835">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="6c8f4-836">再帰はサポートされないため、カスタムキーバインドでは役に立ちません。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-836">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="6c8f4-837">この関数は Remove-PSReadLineKeyHandler によって使用され、カスタムキーバインドではあまり役に立たない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-837">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="6c8f4-838">入力の一部を置換します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-838">Replace some of the input.</span></span> <span data-ttu-id="6c8f4-839">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-839">This operation supports undo/redo.</span></span> <span data-ttu-id="6c8f4-840">これは、undo の単一のアクションとして扱われるため、Delete の後に Insert を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-840">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="6c8f4-841">カーソルを指定されたオフセットに移動します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-841">Move the cursor to the given offset.</span></span> <span data-ttu-id="6c8f4-842">カーソルの移動は、元に戻すために追跡されません。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-842">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="6c8f4-843">この関数は、コマンドレットの設定-PSReadLineOption によって使用されるヘルパーメソッドですが、一時的に設定を変更する必要があるカスタムキーバインドに便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-843">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="6c8f4-844">このヘルパーメソッドは、DigitArgument を優先するカスタムバインドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-844">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="6c8f4-845">一般的な呼び出しは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-845">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="6c8f4-846">注</span><span class="sxs-lookup"><span data-stu-id="6c8f4-846">NOTE</span></span>

### <a name="powershell-compatibility"></a><span data-ttu-id="6c8f4-847">POWERSHELL の互換性</span><span class="sxs-lookup"><span data-stu-id="6c8f4-847">POWERSHELL COMPATIBILITY</span></span>

<span data-ttu-id="6c8f4-848">PSReadLine には、PowerShell 3.0 以降とコンソールホストが必要です。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-848">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="6c8f4-849">PowerShell ISE では機能しません。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-849">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="6c8f4-850">これは Visual Studio Code のコンソールで機能します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-850">It does work in the console of Visual Studio Code.</span></span>

### <a name="command-history"></a><span data-ttu-id="6c8f4-851">コマンド履歴</span><span class="sxs-lookup"><span data-stu-id="6c8f4-851">COMMAND HISTORY</span></span>

<span data-ttu-id="6c8f4-852">PSReadLine は、コマンドラインから入力したすべてのコマンドとデータを含む履歴ファイルを保持します。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-852">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="6c8f4-853">これには、パスワードなどの機密データが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-853">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="6c8f4-854">たとえば、コマンドレットを使用した場合、 `ConvertTo-SecureString` パスワードはプレーンテキストとして履歴ファイルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-854">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="6c8f4-855">履歴ファイルは、という名前のファイルです `$($host.Name)_history.txt` 。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-855">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="6c8f4-856">Windows システムでは、履歴ファイルはに格納され `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` ます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-856">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="6c8f4-857">Windows 以外のシステムでは、履歴ファイルはまたはに格納され `$env:XDG_DATA_HOME/powershell/PSReadLine` `$env:HOME/.local/share/powershell/PSReadLine` ます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-857">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="6c8f4-858">PSReadLine に貢献しているフィードバック &</span><span class="sxs-lookup"><span data-stu-id="6c8f4-858">FEEDBACK & CONTRIBUTING TO PSReadLine</span></span>

[<span data-ttu-id="6c8f4-859">GitHub の PSReadLine</span><span class="sxs-lookup"><span data-stu-id="6c8f4-859">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="6c8f4-860">プル要求を送信したり、GitHub ページでフィードバックを送信したりしてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-860">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c8f4-861">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c8f4-861">SEE ALSO</span></span>

<span data-ttu-id="6c8f4-862">PSReadLine は、GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) ライブラリの影響を強く受けます。</span><span class="sxs-lookup"><span data-stu-id="6c8f4-862">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>

