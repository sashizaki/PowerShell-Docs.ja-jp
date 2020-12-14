---
description: PSReadLine では、PowerShell コンソールでのコマンドライン編集エクスペリエンスが向上しています。
keywords: powershell
Locale: en-US
ms.date: 11/16/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: PSReadLine について
ms.openlocfilehash: 6d52bb04118914a9ccca5d3442a9d1915c1c2818
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "94692277"
---
# <a name="psreadline"></a><span data-ttu-id="94614-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="94614-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="94614-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="94614-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="94614-106">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="94614-106">Short Description</span></span>

<span data-ttu-id="94614-107">PSReadLine では、PowerShell コンソールでのコマンドライン編集エクスペリエンスが向上しています。</span><span class="sxs-lookup"><span data-stu-id="94614-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="94614-108">長い説明</span><span class="sxs-lookup"><span data-stu-id="94614-108">Long Description</span></span>

<span data-ttu-id="94614-109">PSReadLine 2.1 では、PowerShell コンソールの強力なコマンドライン編集エクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="94614-109">PSReadLine 2.1 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="94614-110">次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="94614-110">It provides:</span></span>

- <span data-ttu-id="94614-111">コマンドラインの構文の色分け</span><span class="sxs-lookup"><span data-stu-id="94614-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="94614-112">構文エラーを視覚的に示します。</span><span class="sxs-lookup"><span data-stu-id="94614-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="94614-113">より優れたマルチラインエクスペリエンス (編集と履歴の両方)</span><span class="sxs-lookup"><span data-stu-id="94614-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="94614-114">カスタマイズ可能なキーバインド</span><span class="sxs-lookup"><span data-stu-id="94614-114">Customizable key bindings</span></span>
- <span data-ttu-id="94614-115">Cmd モードと Emacs モード</span><span class="sxs-lookup"><span data-stu-id="94614-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="94614-116">多くの構成オプション</span><span class="sxs-lookup"><span data-stu-id="94614-116">Many configuration options</span></span>
- <span data-ttu-id="94614-117">Bash スタイル補完 (Cmd モードでは省略可能、Emacs モードでは既定)</span><span class="sxs-lookup"><span data-stu-id="94614-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="94614-118">Emacs yank/kill-リング</span><span class="sxs-lookup"><span data-stu-id="94614-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="94614-119">PowerShell トークンベースの "word" の移動と強制終了</span><span class="sxs-lookup"><span data-stu-id="94614-119">PowerShell token based "word" movement and kill</span></span>
- <span data-ttu-id="94614-120">予測 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="94614-120">Predictive IntelliSense</span></span>

<span data-ttu-id="94614-121">PSReadLine には、PowerShell 3.0 以降とコンソールホストが必要です。</span><span class="sxs-lookup"><span data-stu-id="94614-121">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="94614-122">PowerShell ISE では機能しません。</span><span class="sxs-lookup"><span data-stu-id="94614-122">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="94614-123">これは Visual Studio Code のコンソールで機能します。</span><span class="sxs-lookup"><span data-stu-id="94614-123">It does work in the console of Visual Studio Code.</span></span>

<span data-ttu-id="94614-124">PSReadLine 2.1.0 は PowerShell 7.1 に付属しており、サポートされているすべてのバージョンの PowerShell でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="94614-124">PSReadLine 2.1.0 ships with PowerShell 7.1 and is supported in all supported versions of PowerShell.</span></span> <span data-ttu-id="94614-125">PowerShell ギャラリーからインストールできます。</span><span class="sxs-lookup"><span data-stu-id="94614-125">It is available to install from the PowerShell Gallery.</span></span>
<span data-ttu-id="94614-126">サポートされているバージョンの PowerShell に PSReadLine 2.1.0 をインストールするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="94614-126">To install PSReadLine 2.1.0 in a supported version of PowerShell run the following command.</span></span>

```powershell
Install-Module -Name PSReadLine -RequiredVersion 2.1.0
```

> [!NOTE]
> <span data-ttu-id="94614-127">PowerShell 7.0 以降では、スクリーンリーダープログラムが検出されると、PowerShell は Windows で PSReadLine の自動読み込みをスキップします。</span><span class="sxs-lookup"><span data-stu-id="94614-127">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="94614-128">現在、PSReadLine は、スクリーンリーダーではうまく機能しません。</span><span class="sxs-lookup"><span data-stu-id="94614-128">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="94614-129">Windows での PowerShell 7.0 の既定の表示と書式設定は正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="94614-129">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="94614-130">必要に応じて、モジュールを手動で読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="94614-130">You can manually load the module if necessary.</span></span>

## <a name="predictive-intellisense"></a><span data-ttu-id="94614-131">予測 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="94614-131">Predictive IntelliSense</span></span>

<span data-ttu-id="94614-132">予測 IntelliSense は、ユーザーがコマンドを正常に完了できるように、タブ補完の概念を追加したものです。</span><span class="sxs-lookup"><span data-stu-id="94614-132">Predictive IntelliSense is an addition to the concept of tab completion that assists the user in successfully completing commands.</span></span> <span data-ttu-id="94614-133">ユーザーは、ユーザーの履歴や追加のドメイン固有のプラグインからの照合予測に基づいて、完全なコマンドを検出、編集、および実行することができます。</span><span class="sxs-lookup"><span data-stu-id="94614-133">It enables users to discover, edit, and execute full commands based on matching predictions from the user's history and additional domain specific plugins.</span></span>

### <a name="enable-predictive-intellisense"></a><span data-ttu-id="94614-134">予測 IntelliSense を有効にする</span><span class="sxs-lookup"><span data-stu-id="94614-134">Enable Predictive IntelliSense</span></span>

<span data-ttu-id="94614-135">既定では、予測 IntelliSense は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="94614-135">Predictive IntelliSense is disabled by default.</span></span> <span data-ttu-id="94614-136">予測を有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="94614-136">To enable predictions, just run the following command:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource History
```

<span data-ttu-id="94614-137">**PredictionSource** パラメーターでは、ドメイン固有の要件とカスタムの要件に対してプラグインを受け入れることもできます。</span><span class="sxs-lookup"><span data-stu-id="94614-137">The **PredictionSource** parameter can also accept plugins for domain specific and custom requirements.</span></span>

<span data-ttu-id="94614-138">予測 IntelliSense を無効にするには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="94614-138">To disable Predictive IntelliSense, just run:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource None
```

<span data-ttu-id="94614-139">クラス **[PSConsoleReadLine]** では、次の関数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="94614-139">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="94614-140">基本的な編集関数</span><span class="sxs-lookup"><span data-stu-id="94614-140">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="94614-141">中止</span><span class="sxs-lookup"><span data-stu-id="94614-141">Abort</span></span>

<span data-ttu-id="94614-142">現在のアクション (増分履歴検索など) を中止します。</span><span class="sxs-lookup"><span data-stu-id="94614-142">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="94614-143">.Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="94614-143">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="94614-144">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="94614-144">AcceptAndGetNext</span></span>

<span data-ttu-id="94614-145">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="94614-145">Attempt to execute the current input.</span></span> <span data-ttu-id="94614-146">(AcceptLine など) 実行できる場合は、次に ReadLine が呼び出されたときに履歴から次の項目を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="94614-146">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="94614-147">.Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="94614-147">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="94614-148">AcceptLine</span><span class="sxs-lookup"><span data-stu-id="94614-148">AcceptLine</span></span>

<span data-ttu-id="94614-149">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="94614-149">Attempt to execute the current input.</span></span> <span data-ttu-id="94614-150">現在の入力が不完全な場合 (たとえば、終わりかっこ、角かっこ、または引用符がない場合)、継続のプロンプトは次の行に表示され、PSReadLine は現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="94614-150">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="94614-151">コマンド: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="94614-151">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="94614-152">.Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="94614-152">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="94614-153">Vi の挿入モード: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="94614-153">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="94614-154">AddLine</span><span class="sxs-lookup"><span data-stu-id="94614-154">AddLine</span></span>

<span data-ttu-id="94614-155">継続プロンプトが次の行に表示され、PSReadLine が現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="94614-155">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="94614-156">これは、単一行が単独で完全に入力されている場合でも、複数行の入力を1つのコマンドとして入力する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="94614-156">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="94614-157">コマンド: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="94614-157">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="94614-158">.Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="94614-158">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="94614-159">Vi の挿入モード: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="94614-159">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="94614-160">Vi コマンドモード: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="94614-160">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="94614-161">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="94614-161">BackwardDeleteChar</span></span>

<span data-ttu-id="94614-162">カーソルの前の文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-162">Delete the character before the cursor.</span></span>

- <span data-ttu-id="94614-163">Cmd: `<Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="94614-163">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="94614-164">Emacs: `<Backspace>` 、 `<Ctrl+Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="94614-164">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="94614-165">Vi の挿入モード: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="94614-165">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="94614-166">Vi コマンドモード: `<X>` 、 `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="94614-166">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="94614-167">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="94614-167">BackwardDeleteLine</span></span>

<span data-ttu-id="94614-168">Like BackwardKillLine-行の先頭から先頭までのテキストを削除しますが、削除されたテキストはキルリングには挿入されません。</span><span class="sxs-lookup"><span data-stu-id="94614-168">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="94614-169">コマンド: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="94614-169">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="94614-170">Vi 挿入モード: `<Ctrl+u>` 、 `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="94614-170">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="94614-171">Vi コマンドモード: `<Ctrl+u>` 、 `<Ctrl+Home>` 、 `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="94614-171">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="94614-172">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="94614-172">BackwardDeleteWord</span></span>

<span data-ttu-id="94614-173">前の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-173">Deletes the previous word.</span></span>

- <span data-ttu-id="94614-174">Vi コマンドモード: `<Ctrl+w>` 、 `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="94614-174">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="94614-175">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="94614-175">BackwardKillLine</span></span>

<span data-ttu-id="94614-176">入力の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="94614-176">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="94614-177">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="94614-177">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="94614-178">Emacs: `<Ctrl+u>` 、 `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="94614-178">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="94614-179">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="94614-179">BackwardKillWord</span></span>

<span data-ttu-id="94614-180">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="94614-180">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="94614-181">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="94614-181">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="94614-182">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="94614-182">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="94614-183">Cmd: `<Ctrl+Backspace>` 、 `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="94614-183">Cmd: `<Ctrl+Backspace>`, `<Ctrl+w>`</span></span>
- <span data-ttu-id="94614-184">Emacs: `<Alt+Backspace>` 、 `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="94614-184">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="94614-185">Vi の挿入モード: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="94614-185">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="94614-186">Vi コマンドモード: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="94614-186">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="94614-187">CancelLine</span><span class="sxs-lookup"><span data-stu-id="94614-187">CancelLine</span></span>

<span data-ttu-id="94614-188">入力を画面に残したまま、現在の入力を取り消しますが、プロンプトが再び評価されるように、ホストに戻ります。</span><span class="sxs-lookup"><span data-stu-id="94614-188">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="94614-189">Vi の挿入モード: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="94614-189">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="94614-190">Vi コマンドモード: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="94614-190">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="94614-191">コピー</span><span class="sxs-lookup"><span data-stu-id="94614-191">Copy</span></span>

<span data-ttu-id="94614-192">選択したリージョンをシステムクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="94614-192">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="94614-193">領域が選択されていない場合は、行全体をコピーします。</span><span class="sxs-lookup"><span data-stu-id="94614-193">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="94614-194">コマンド: `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="94614-194">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="94614-195">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="94614-195">CopyOrCancelLine</span></span>

<span data-ttu-id="94614-196">テキストが選択されている場合は、クリップボードにコピーします。それ以外の場合は、行をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="94614-196">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="94614-197">コマンド: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="94614-197">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="94614-198">.Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="94614-198">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="94614-199">［切り取り］</span><span class="sxs-lookup"><span data-stu-id="94614-199">Cut</span></span>

<span data-ttu-id="94614-200">削除されたテキストをシステムクリップボードに配置した、選択した領域を削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-200">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="94614-201">コマンド: `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="94614-201">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="94614-202">Dele</span><span class="sxs-lookup"><span data-stu-id="94614-202">DeleteChar</span></span>

<span data-ttu-id="94614-203">カーソルの下の文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-203">Delete the character under the cursor.</span></span>

- <span data-ttu-id="94614-204">コマンド: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="94614-204">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="94614-205">.Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="94614-205">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="94614-206">Vi の挿入モード: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="94614-206">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="94614-207">Vi コマンドモード: `<Delete>` 、 `<x>` 、 `<d,l>` 、 `<d,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="94614-207">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Spacebar>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="94614-208">Deleの Arorexit</span><span class="sxs-lookup"><span data-stu-id="94614-208">DeleteCharOrExit</span></span>

<span data-ttu-id="94614-209">カーソルの下の文字を削除するか、行が空の場合はプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="94614-209">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="94614-210">.Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="94614-210">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofbuffer"></a><span data-ttu-id="94614-211">DeleteEndOfBuffer</span><span class="sxs-lookup"><span data-stu-id="94614-211">DeleteEndOfBuffer</span></span>

<span data-ttu-id="94614-212">複数行バッファーの末尾までを削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-212">Deletes to the end of the multiline buffer.</span></span>

- <span data-ttu-id="94614-213">Vi コマンドモード: `<d,G>`</span><span class="sxs-lookup"><span data-stu-id="94614-213">Vi command mode: `<d,G>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="94614-214">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="94614-214">DeleteEndOfWord</span></span>

<span data-ttu-id="94614-215">単語の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-215">Delete to the end of the word.</span></span>

- <span data-ttu-id="94614-216">Vi コマンドモード: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="94614-216">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="94614-217">Deleteline.invoke に</span><span class="sxs-lookup"><span data-stu-id="94614-217">DeleteLine</span></span>

<span data-ttu-id="94614-218">複数行バッファーの現在の論理行を削除して、元に戻すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="94614-218">Deletes the current logical line of a multiline buffer, enabling undo.</span></span>

- <span data-ttu-id="94614-219">Vi コマンドモード: `<d,d>` 、 `<d,_>`</span><span class="sxs-lookup"><span data-stu-id="94614-219">Vi command mode: `<d,d>`, `<d,_>`</span></span>

### <a name="deletepreviouslines"></a><span data-ttu-id="94614-220">削除した行</span><span class="sxs-lookup"><span data-stu-id="94614-220">DeletePreviousLines</span></span>

<span data-ttu-id="94614-221">複数行バッファーの前に要求された論理行と現在の論理行を削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-221">Deletes the previous requested logical lines and the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="94614-222">Vi コマンドモード: `<d,k>`</span><span class="sxs-lookup"><span data-stu-id="94614-222">Vi command mode: `<d,k>`</span></span>

### <a name="deleterelativelines"></a><span data-ttu-id="94614-223">DeleteRelativeLines</span><span class="sxs-lookup"><span data-stu-id="94614-223">DeleteRelativeLines</span></span>

<span data-ttu-id="94614-224">バッファーの先頭から複数行バッファーの現在の論理行に削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-224">Deletes from the beginning of the buffer to the current logical line in a multiline buffer.</span></span>

<span data-ttu-id="94614-225">ほとんどの Vi コマンドと同様に、コマンドには、 `<d,g,g>` 絶対行番号を指定する数値引数 (現在の行番号と共に、削除する行の範囲を構成する) を付加することができます。</span><span class="sxs-lookup"><span data-stu-id="94614-225">As most Vi commands, the `<d,g,g>` command can be prepended with a numeric argument that specifies an absolute line number, which, together with the current line number, make up a range of lines to be deleted.</span></span>
<span data-ttu-id="94614-226">指定しない場合、数値引数の既定値は1です。これは、複数行バッファーの最初の論理行を参照します。</span><span class="sxs-lookup"><span data-stu-id="94614-226">If not specified, the numeric argument defaults to 1, which refers to the first logical line in a multiline buffer.</span></span>

<span data-ttu-id="94614-227">複数行から削除される実際の行数は、現在の論理行番号と指定された数値引数の差として計算されます。したがって、負の数になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="94614-227">The actual number of lines to be deleted from the multiline is computed as the difference between the current logical line number and the specified numeric argument, which can thus be negative.</span></span> <span data-ttu-id="94614-228">そのため、メソッド名の _相対_ 部分です。</span><span class="sxs-lookup"><span data-stu-id="94614-228">Hence the _relative_ part of method name.</span></span>

- <span data-ttu-id="94614-229">Vi コマンドモード: `<d,g,g>`</span><span class="sxs-lookup"><span data-stu-id="94614-229">Vi command mode: `<d,g,g>`</span></span>

### <a name="deletenextlines"></a><span data-ttu-id="94614-230">Deleの配信行</span><span class="sxs-lookup"><span data-stu-id="94614-230">DeleteNextLines</span></span>

<span data-ttu-id="94614-231">複数行バッファーで現在の論理行と次に要求された論理行を削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-231">Deletes the current logical line and the next requested logical lines in a multiline buffer.</span></span>

- <span data-ttu-id="94614-232">Vi コマンドモード: `<d,j>`</span><span class="sxs-lookup"><span data-stu-id="94614-232">Vi command mode: `<d,j>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="94614-233">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="94614-233">DeleteLineToFirstChar</span></span>

<span data-ttu-id="94614-234">カーソルから、行の最初の空白以外の文字までのテキストを削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-234">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="94614-235">Vi コマンドモード: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="94614-235">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="94614-236">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="94614-236">DeleteToEnd</span></span>

<span data-ttu-id="94614-237">行の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-237">Delete to the end of the line.</span></span>

- <span data-ttu-id="94614-238">Vi コマンドモード: `<D>` 、 `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="94614-238">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="94614-239">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="94614-239">DeleteWord</span></span>

<span data-ttu-id="94614-240">次の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-240">Delete the next word.</span></span>

- <span data-ttu-id="94614-241">Vi コマンドモード: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="94614-241">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="94614-242">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="94614-242">ForwardDeleteLine</span></span>

<span data-ttu-id="94614-243">同じように、Forwardは、行の末尾から最後までのテキストを削除しますが、削除されたテキストはキルリングには挿入されません。</span><span class="sxs-lookup"><span data-stu-id="94614-243">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="94614-244">コマンド: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="94614-244">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="94614-245">Vi の挿入モード: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="94614-245">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="94614-246">Vi コマンドモード: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="94614-246">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="94614-247">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="94614-247">InsertLineAbove</span></span>

<span data-ttu-id="94614-248">現在の行の上にカーソルがある場所に関係なく、現在の行の上に新しい空の行が作成されます。</span><span class="sxs-lookup"><span data-stu-id="94614-248">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="94614-249">カーソルが新しい行の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-249">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="94614-250">コマンド: `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="94614-250">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="94614-251">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="94614-251">InsertLineBelow</span></span>

<span data-ttu-id="94614-252">カーソルが現在の行にある場所に関係なく、現在の行の下に新しい空の行が作成されます。</span><span class="sxs-lookup"><span data-stu-id="94614-252">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="94614-253">カーソルが新しい行の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-253">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="94614-254">コマンド: `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="94614-254">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="94614-255">InvertCase</span><span class="sxs-lookup"><span data-stu-id="94614-255">InvertCase</span></span>

<span data-ttu-id="94614-256">現在の文字の大文字と小文字の区別を反転し、次の文字に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-256">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="94614-257">Vi コマンドモード: `<~>`</span><span class="sxs-lookup"><span data-stu-id="94614-257">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="94614-258">行の行</span><span class="sxs-lookup"><span data-stu-id="94614-258">KillLine</span></span>

<span data-ttu-id="94614-259">カーソルから入力の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="94614-259">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="94614-260">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="94614-260">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="94614-261">.Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="94614-261">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="94614-262">"/" 領域</span><span class="sxs-lookup"><span data-stu-id="94614-262">KillRegion</span></span>

<span data-ttu-id="94614-263">カーソルとマークの間のテキストを強制終了します。</span><span class="sxs-lookup"><span data-stu-id="94614-263">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="94614-264">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="94614-264">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="94614-265">文字の候補</span><span class="sxs-lookup"><span data-stu-id="94614-265">KillWord</span></span>

<span data-ttu-id="94614-266">カーソルから現在の単語の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="94614-266">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="94614-267">カーソルが単語の間にある場合は、カーソルから次の単語の末尾まで、入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="94614-267">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="94614-268">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="94614-268">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="94614-269">Cmd: `<Alt+d>` 、 `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="94614-269">Cmd: `<Alt+d>`, `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="94614-270">Emacs: `<Alt+d>` 、 `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="94614-270">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="94614-271">Vi の挿入モード: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="94614-271">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="94614-272">Vi コマンドモード: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="94614-272">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="94614-273">貼り付け</span><span class="sxs-lookup"><span data-stu-id="94614-273">Paste</span></span>

<span data-ttu-id="94614-274">システムクリップボードからテキストを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="94614-274">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="94614-275">Cmd: `<Ctrl+v>` 、 `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="94614-275">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="94614-276">Vi の挿入モード: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="94614-276">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="94614-277">Vi コマンドモード: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="94614-277">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94614-278">**貼り付け** 関数を使用すると、クリップボードバッファーの内容全体が psreadline の入力バッファーに貼り付けられます。</span><span class="sxs-lookup"><span data-stu-id="94614-278">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="94614-279">入力バッファーが PowerShell パーサーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="94614-279">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="94614-280">コンソールアプリケーションの **右クリック** による貼り付けメソッドを使用して貼り付けた入力は、一度に1文字ずつ入力バッファーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="94614-280">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="94614-281">入力バッファーは、改行文字がコピーされるときにパーサーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="94614-281">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="94614-282">そのため、入力は一度に1行ずつ解析されます。</span><span class="sxs-lookup"><span data-stu-id="94614-282">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="94614-283">貼り付けメソッドの違いによって、実行の動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="94614-283">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="94614-284">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="94614-284">PasteAfter</span></span>

<span data-ttu-id="94614-285">カーソルの後にクリップボードを貼り付けて、貼り付けられたテキストの末尾にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-285">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="94614-286">Vi コマンドモード: `<p>`</span><span class="sxs-lookup"><span data-stu-id="94614-286">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="94614-287">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="94614-287">PasteBefore</span></span>

<span data-ttu-id="94614-288">カーソルの前にクリップボードを貼り付けて、貼り付けられたテキストの末尾にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-288">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="94614-289">Vi コマンドモード: `<P>`</span><span class="sxs-lookup"><span data-stu-id="94614-289">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="94614-290">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="94614-290">PrependAndAccept</span></span>

<span data-ttu-id="94614-291">' # ' を先頭に付加し、その行を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="94614-291">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="94614-292">Vi コマンドモード: `<#>`</span><span class="sxs-lookup"><span data-stu-id="94614-292">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="94614-293">やり直し</span><span class="sxs-lookup"><span data-stu-id="94614-293">Redo</span></span>

<span data-ttu-id="94614-294">元に戻す操作を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="94614-294">Undo an undo.</span></span>

- <span data-ttu-id="94614-295">コマンド: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="94614-295">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="94614-296">Vi の挿入モード: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="94614-296">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="94614-297">Vi コマンドモード: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="94614-297">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="94614-298">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="94614-298">RepeatLastCommand</span></span>

<span data-ttu-id="94614-299">最後のテキストの変更を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="94614-299">Repeat the last text modification.</span></span>

- <span data-ttu-id="94614-300">Vi コマンドモード: `<.>`</span><span class="sxs-lookup"><span data-stu-id="94614-300">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="94614-301">再有効化</span><span class="sxs-lookup"><span data-stu-id="94614-301">RevertLine</span></span>

<span data-ttu-id="94614-302">すべての入力を現在の入力に戻します。</span><span class="sxs-lookup"><span data-stu-id="94614-302">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="94614-303">コマンド: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="94614-303">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="94614-304">Emacs: `<Alt+r>` 、 `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="94614-304">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="94614-305">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="94614-305">ShellBackwardKillWord</span></span>

<span data-ttu-id="94614-306">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="94614-306">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="94614-307">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="94614-307">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="94614-308">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="94614-308">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="94614-309">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="94614-309">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="94614-310">Shellは Word</span><span class="sxs-lookup"><span data-stu-id="94614-310">ShellKillWord</span></span>

<span data-ttu-id="94614-311">カーソルから現在の単語の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="94614-311">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="94614-312">カーソルが単語の間にある場合は、カーソルから次の単語の末尾まで、入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="94614-312">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="94614-313">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="94614-313">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="94614-314">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="94614-314">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="94614-315">スワップ文字</span><span class="sxs-lookup"><span data-stu-id="94614-315">SwapCharacters</span></span>

<span data-ttu-id="94614-316">現在の文字とそれより前の文字を交換します。</span><span class="sxs-lookup"><span data-stu-id="94614-316">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="94614-317">.Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="94614-317">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="94614-318">Vi の挿入モード: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="94614-318">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="94614-319">Vi コマンドモード: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="94614-319">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="94614-320">元に戻す</span><span class="sxs-lookup"><span data-stu-id="94614-320">Undo</span></span>

<span data-ttu-id="94614-321">前の編集を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="94614-321">Undo a previous edit.</span></span>

- <span data-ttu-id="94614-322">コマンド: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="94614-322">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="94614-323">Emacs: `<Ctrl+_>` 、 `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="94614-323">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="94614-324">Vi の挿入モード: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="94614-324">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="94614-325">Vi コマンドモード: `<Ctrl+z>` 、 `<u>`</span><span class="sxs-lookup"><span data-stu-id="94614-325">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="94614-326">UndoAll</span><span class="sxs-lookup"><span data-stu-id="94614-326">UndoAll</span></span>

<span data-ttu-id="94614-327">行の以前の編集をすべて元に戻します。</span><span class="sxs-lookup"><span data-stu-id="94614-327">Undo all previous edits for line.</span></span>

- <span data-ttu-id="94614-328">Vi コマンドモード: `<U>`</span><span class="sxs-lookup"><span data-stu-id="94614-328">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="94614-329">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="94614-329">UnixWordRubout</span></span>

<span data-ttu-id="94614-330">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="94614-330">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="94614-331">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="94614-331">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="94614-332">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="94614-332">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="94614-333">.Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="94614-333">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="94614-334">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="94614-334">ValidateAndAcceptLine</span></span>

<span data-ttu-id="94614-335">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="94614-335">Attempt to execute the current input.</span></span> <span data-ttu-id="94614-336">現在の入力が不完全な場合 (たとえば、終わりかっこ、角かっこ、または引用符がない場合)、継続のプロンプトは次の行に表示され、PSReadLine は現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="94614-336">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="94614-337">.Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="94614-337">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="94614-338">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="94614-338">ViAcceptLine</span></span>

<span data-ttu-id="94614-339">行を受け入れ、挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="94614-339">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="94614-340">Vi コマンドモード: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="94614-340">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="94614-341">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="94614-341">ViAcceptLineOrExit</span></span>

<span data-ttu-id="94614-342">(Emacs モードでは Deleと同じですが、文字を削除するのではなく、行を受け取ります)。</span><span class="sxs-lookup"><span data-stu-id="94614-342">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="94614-343">Vi の挿入モード: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="94614-343">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="94614-344">Vi コマンドモード: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="94614-344">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="94614-345">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="94614-345">ViAppendLine</span></span>

<span data-ttu-id="94614-346">現在の行の下に新しい行が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="94614-346">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="94614-347">Vi コマンドモード: `<o>`</span><span class="sxs-lookup"><span data-stu-id="94614-347">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="94614-348">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="94614-348">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="94614-349">単語区切り記号として空白文字のみを使用して、前の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-349">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="94614-350">Vi コマンドモード: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="94614-350">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="94614-351">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="94614-351">ViBackwardGlob</span></span>

<span data-ttu-id="94614-352">区切り記号として空白文字のみを使用して、カーソルを前の単語の先頭に戻します。</span><span class="sxs-lookup"><span data-stu-id="94614-352">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="94614-353">Vi コマンドモード: `<B>`</span><span class="sxs-lookup"><span data-stu-id="94614-353">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="94614-354">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="94614-354">ViDeleteBrace</span></span>

<span data-ttu-id="94614-355">対応する中かっこ、かっこ、または角かっこを検索し、中かっこを含め、内のすべての内容を削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-355">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="94614-356">Vi コマンドモード: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="94614-356">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="94614-357">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="94614-357">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="94614-358">単語の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-358">Delete to the end of the word.</span></span>

- <span data-ttu-id="94614-359">Vi コマンドモード: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="94614-359">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="94614-360">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="94614-360">ViDeleteGlob</span></span>

<span data-ttu-id="94614-361">次の glob (空白で区切られた単語) を削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-361">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="94614-362">Vi コマンドモード: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="94614-362">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="94614-363">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="94614-363">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="94614-364">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-364">Deletes until given character.</span></span>

- <span data-ttu-id="94614-365">Vi コマンドモード: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="94614-365">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="94614-366">Videletetobeforo</span><span class="sxs-lookup"><span data-stu-id="94614-366">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="94614-367">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-367">Deletes until given character.</span></span>

- <span data-ttu-id="94614-368">Vi コマンドモード: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="94614-368">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="94614-369">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="94614-369">ViDeleteToChar</span></span>

<span data-ttu-id="94614-370">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-370">Deletes until given character.</span></span>

- <span data-ttu-id="94614-371">Vi コマンドモード: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="94614-371">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="94614-372">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="94614-372">ViDeleteToCharBackward</span></span>

<span data-ttu-id="94614-373">指定された文字まで後方を削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-373">Deletes backwards until given character.</span></span>

- <span data-ttu-id="94614-374">Vi コマンドモード: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="94614-374">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="94614-375">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="94614-375">ViInsertAtBegining</span></span>

<span data-ttu-id="94614-376">挿入モードに切り替え、カーソルを行の先頭に配置します。</span><span class="sxs-lookup"><span data-stu-id="94614-376">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="94614-377">Vi コマンドモード: `<I>`</span><span class="sxs-lookup"><span data-stu-id="94614-377">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="94614-378">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="94614-378">ViInsertAtEnd</span></span>

<span data-ttu-id="94614-379">挿入モードに切り替え、カーソルを行の末尾に配置します。</span><span class="sxs-lookup"><span data-stu-id="94614-379">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="94614-380">Vi コマンドモード: `<A>`</span><span class="sxs-lookup"><span data-stu-id="94614-380">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="94614-381">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="94614-381">ViInsertLine</span></span>

<span data-ttu-id="94614-382">現在の行の上に新しい行が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="94614-382">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="94614-383">Vi コマンドモード: `<O>`</span><span class="sxs-lookup"><span data-stu-id="94614-383">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="94614-384">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="94614-384">ViInsertWithAppend</span></span>

<span data-ttu-id="94614-385">現在の行の位置から追加します。</span><span class="sxs-lookup"><span data-stu-id="94614-385">Append from the current line position.</span></span>

- <span data-ttu-id="94614-386">Vi コマンドモード: `<a>`</span><span class="sxs-lookup"><span data-stu-id="94614-386">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="94614-387">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="94614-387">ViInsertWithDelete</span></span>

<span data-ttu-id="94614-388">現在の文字を削除し、挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="94614-388">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="94614-389">Vi コマンドモード: `<s>`</span><span class="sxs-lookup"><span data-stu-id="94614-389">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="94614-390">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="94614-390">ViJoinLines</span></span>

<span data-ttu-id="94614-391">現在の行と次の行を結合します。</span><span class="sxs-lookup"><span data-stu-id="94614-391">Joins the current line and the next line.</span></span>

- <span data-ttu-id="94614-392">Vi コマンドモード: `<J>`</span><span class="sxs-lookup"><span data-stu-id="94614-392">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="94614-393">交換ライン</span><span class="sxs-lookup"><span data-stu-id="94614-393">ViReplaceLine</span></span>

<span data-ttu-id="94614-394">コマンドライン全体を消去します。</span><span class="sxs-lookup"><span data-stu-id="94614-394">Erase the entire command line.</span></span>

- <span data-ttu-id="94614-395">Vi コマンドモード: `<S>` 、 `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="94614-395">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="94614-396">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="94614-396">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="94614-397">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="94614-397">Replaces until given character.</span></span>

- <span data-ttu-id="94614-398">Vi コマンドモード: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="94614-398">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="94614-399">Vireplacetobeforo</span><span class="sxs-lookup"><span data-stu-id="94614-399">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="94614-400">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="94614-400">Replaces until given character.</span></span>

- <span data-ttu-id="94614-401">Vi コマンドモード: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="94614-401">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="94614-402">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="94614-402">ViReplaceToChar</span></span>

<span data-ttu-id="94614-403">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-403">Deletes until given character.</span></span>

- <span data-ttu-id="94614-404">Vi コマンドモード: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="94614-404">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="94614-405">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="94614-405">ViReplaceToCharBackward</span></span>

<span data-ttu-id="94614-406">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="94614-406">Replaces until given character.</span></span>

- <span data-ttu-id="94614-407">Vi コマンドモード: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="94614-407">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="94614-408">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="94614-408">ViYankBeginningOfLine</span></span>

<span data-ttu-id="94614-409">バッファーの先頭からカーソルまで Yank。</span><span class="sxs-lookup"><span data-stu-id="94614-409">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="94614-410">Vi コマンドモード: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="94614-410">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="94614-411">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="94614-411">ViYankEndOfGlob</span></span>

<span data-ttu-id="94614-412">カーソルから単語の末尾まで Yank します。</span><span class="sxs-lookup"><span data-stu-id="94614-412">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="94614-413">Vi コマンドモード: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="94614-413">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="94614-414">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="94614-414">ViYankEndOfWord</span></span>

<span data-ttu-id="94614-415">カーソルから単語の末尾まで Yank します。</span><span class="sxs-lookup"><span data-stu-id="94614-415">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="94614-416">Vi コマンドモード: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="94614-416">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="94614-417">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="94614-417">ViYankLeft</span></span>

<span data-ttu-id="94614-418">カーソルの左側の文字を Yank します。</span><span class="sxs-lookup"><span data-stu-id="94614-418">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="94614-419">Vi コマンドモード: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="94614-419">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="94614-420">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="94614-420">ViYankLine</span></span>

<span data-ttu-id="94614-421">バッファー全体を Yank します。</span><span class="sxs-lookup"><span data-stu-id="94614-421">Yank the entire buffer.</span></span>

- <span data-ttu-id="94614-422">Vi コマンドモード: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="94614-422">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="94614-423">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="94614-423">ViYankNextGlob</span></span>

<span data-ttu-id="94614-424">Yank は、次の単語の先頭にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="94614-424">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="94614-425">Vi コマンドモード: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="94614-425">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="94614-426">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="94614-426">ViYankNextWord</span></span>

<span data-ttu-id="94614-427">カーソルの後の単語を Yank します。</span><span class="sxs-lookup"><span data-stu-id="94614-427">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="94614-428">Vi コマンドモード: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="94614-428">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="94614-429">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="94614-429">ViYankPercent</span></span>

<span data-ttu-id="94614-430">一致する中かっこを Yank します。</span><span class="sxs-lookup"><span data-stu-id="94614-430">Yank to/from matching brace.</span></span>

- <span data-ttu-id="94614-431">Vi コマンドモード: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="94614-431">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="94614-432">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="94614-432">ViYankPreviousGlob</span></span>

<span data-ttu-id="94614-433">Yank は、単語の先頭からカーソルになります。</span><span class="sxs-lookup"><span data-stu-id="94614-433">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="94614-434">Vi コマンドモード: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="94614-434">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="94614-435">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="94614-435">ViYankPreviousWord</span></span>

<span data-ttu-id="94614-436">カーソルの前に単語を Yank します。</span><span class="sxs-lookup"><span data-stu-id="94614-436">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="94614-437">Vi コマンドモード: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="94614-437">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="94614-438">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="94614-438">ViYankRight</span></span>

<span data-ttu-id="94614-439">カーソルの右側に Yank 文字があります。</span><span class="sxs-lookup"><span data-stu-id="94614-439">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="94614-440">Vi コマンドモード: `<y,l>` 、 `<y,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="94614-440">Vi command mode: `<y,l>`, `<y,Spacebar>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="94614-441">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="94614-441">ViYankToEndOfLine</span></span>

<span data-ttu-id="94614-442">カーソルからバッファーの末尾までの Yank。</span><span class="sxs-lookup"><span data-stu-id="94614-442">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="94614-443">Vi コマンドモード: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="94614-443">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="94614-444">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="94614-444">ViYankToFirstChar</span></span>

<span data-ttu-id="94614-445">最初の空白以外の文字からカーソルまで Yank ます。</span><span class="sxs-lookup"><span data-stu-id="94614-445">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="94614-446">Vi コマンドモード: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="94614-446">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="94614-447">Yank</span><span class="sxs-lookup"><span data-stu-id="94614-447">Yank</span></span>

<span data-ttu-id="94614-448">最後に終了したテキストを入力に追加します。</span><span class="sxs-lookup"><span data-stu-id="94614-448">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="94614-449">.Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="94614-449">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="94614-450">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="94614-450">YankLastArg</span></span>

<span data-ttu-id="94614-451">前の履歴行の最後の引数を Yank します。</span><span class="sxs-lookup"><span data-stu-id="94614-451">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="94614-452">引数を使用すると、最初に呼び出されたときに、YankNthArg と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="94614-452">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="94614-453">複数回呼び出された場合は、代わりに履歴を反復処理し、引数に方向を設定します (負の方向が反転します)。</span><span class="sxs-lookup"><span data-stu-id="94614-453">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="94614-454">コマンド: `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="94614-454">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="94614-455">Emacs: `<Alt+.>` 、 `<Alt+_>` 、 `<Escape,.>` 、 `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="94614-455">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="94614-456">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="94614-456">YankNthArg</span></span>

<span data-ttu-id="94614-457">Yank は、前の履歴行から (コマンドの後に) 最初の引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="94614-457">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="94614-458">引数を使用して、n 番目の引数 (0 から始まる) を yank します。引数が負の場合は、最後の引数から開始します。</span><span class="sxs-lookup"><span data-stu-id="94614-458">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="94614-459">Emacs: `<Ctrl+Alt+y>` 、 `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="94614-459">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="94614-460">YankPop</span><span class="sxs-lookup"><span data-stu-id="94614-460">YankPop</span></span>

<span data-ttu-id="94614-461">前の操作が Yank または YankPop であった場合は、以前の引き抜かテキストをキルリングから次に強制終了されたテキストに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="94614-461">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="94614-462">Emacs: `<Alt+y>` 、 `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="94614-462">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="94614-463">カーソルの移動関数</span><span class="sxs-lookup"><span data-stu-id="94614-463">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="94614-464">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="94614-464">BackwardChar</span></span>

<span data-ttu-id="94614-465">カーソルを1文字左に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-465">Move the cursor one character to the left.</span></span> <span data-ttu-id="94614-466">これにより、カーソルが複数行の入力の前の行に移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="94614-466">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="94614-467">コマンド: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-467">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="94614-468">Emacs: `<LeftArrow>` 、 `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="94614-468">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="94614-469">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="94614-469">BackwardWord</span></span>

<span data-ttu-id="94614-470">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-470">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="94614-471">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="94614-471">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="94614-472">コマンド: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-472">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="94614-473">Emacs: `<Alt+b>` 、 `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="94614-473">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="94614-474">Vi の挿入モード: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-474">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="94614-475">Vi コマンドモード: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-475">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="94614-476">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="94614-476">BeginningOfLine</span></span>

<span data-ttu-id="94614-477">入力に複数の行がある場合は、現在の行の先頭に移動します。または、既に行の先頭にある場合は、入力の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-477">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="94614-478">入力に1行しか含まれていない場合は、入力の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-478">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="94614-479">コマンド: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="94614-479">Cmd: `<Home>`</span></span>
- <span data-ttu-id="94614-480">Emacs: `<Home>` 、 `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="94614-480">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="94614-481">Vi の挿入モード: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="94614-481">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="94614-482">Vi コマンドモード: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="94614-482">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="94614-483">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="94614-483">EndOfLine</span></span>

<span data-ttu-id="94614-484">入力に複数の行がある場合は、現在の行の末尾に移動します。または、既に行の末尾にある場合は、入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-484">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="94614-485">入力に1行しか含まれていない場合は、入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-485">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="94614-486">コマンド: `<End>`</span><span class="sxs-lookup"><span data-stu-id="94614-486">Cmd: `<End>`</span></span>
- <span data-ttu-id="94614-487">Emacs: `<End>` 、 `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="94614-487">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="94614-488">Vi の挿入モード: `<End>`</span><span class="sxs-lookup"><span data-stu-id="94614-488">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="94614-489">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="94614-489">ForwardChar</span></span>

<span data-ttu-id="94614-490">カーソルを1文字右に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-490">Move the cursor one character to the right.</span></span> <span data-ttu-id="94614-491">これにより、カーソルが複数行入力の次の行に移動する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="94614-491">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="94614-492">コマンド: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-492">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="94614-493">Emacs: `<RightArrow>` 、 `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="94614-493">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="94614-494">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="94614-494">ForwardWord</span></span>

<span data-ttu-id="94614-495">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-495">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="94614-496">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="94614-496">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="94614-497">Emacs: `<Alt+f>` 、 `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="94614-497">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="94614-498">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="94614-498">GotoBrace</span></span>

<span data-ttu-id="94614-499">対応する中かっこ、かっこ、または角かっこにジャンプします。</span><span class="sxs-lookup"><span data-stu-id="94614-499">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="94614-500">コマンド: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="94614-500">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="94614-501">Vi の挿入モード: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="94614-501">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="94614-502">Vi コマンドモード: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="94614-502">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="94614-503">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="94614-503">GotoColumn</span></span>

<span data-ttu-id="94614-504">Arg で示される列に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-504">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="94614-505">Vi コマンドモード: `<|>`</span><span class="sxs-lookup"><span data-stu-id="94614-505">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="94614-506">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="94614-506">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="94614-507">カーソルを行の空白以外の最初の文字に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-507">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="94614-508">Vi コマンドモード: `<^>` 、 `<_>`</span><span class="sxs-lookup"><span data-stu-id="94614-508">Vi command mode: `<^>`, `<_>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="94614-509">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="94614-509">MoveToEndOfLine</span></span>

<span data-ttu-id="94614-510">カーソルを入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-510">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="94614-511">Vi コマンドモード: `<End>` 、 `<$>`</span><span class="sxs-lookup"><span data-stu-id="94614-511">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="94614-512">NextLine</span><span class="sxs-lookup"><span data-stu-id="94614-512">NextLine</span></span>

<span data-ttu-id="94614-513">カーソルを次の行に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-513">Move the cursor to the next line.</span></span>

- <span data-ttu-id="94614-514">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="94614-514">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="94614-515">NextWord</span><span class="sxs-lookup"><span data-stu-id="94614-515">NextWord</span></span>

<span data-ttu-id="94614-516">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-516">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="94614-517">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="94614-517">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="94614-518">コマンド: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-518">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="94614-519">Vi の挿入モード: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-519">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="94614-520">Vi コマンドモード: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-520">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="94614-521">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="94614-521">NextWordEnd</span></span>

<span data-ttu-id="94614-522">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-522">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="94614-523">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="94614-523">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="94614-524">Vi コマンドモード: `<e>`</span><span class="sxs-lookup"><span data-stu-id="94614-524">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="94614-525">前の行</span><span class="sxs-lookup"><span data-stu-id="94614-525">PreviousLine</span></span>

<span data-ttu-id="94614-526">カーソルを前の行に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-526">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="94614-527">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="94614-527">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="94614-528">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="94614-528">ShellBackwardWord</span></span>

<span data-ttu-id="94614-529">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-529">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="94614-530">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="94614-530">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="94614-531">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="94614-531">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="94614-532">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="94614-532">ShellForwardWord</span></span>

<span data-ttu-id="94614-533">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-533">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="94614-534">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="94614-534">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="94614-535">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="94614-535">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="94614-536">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="94614-536">ShellNextWord</span></span>

<span data-ttu-id="94614-537">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-537">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="94614-538">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="94614-538">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="94614-539">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="94614-539">Function is unbound.</span></span>

### <a name="vibackwardchar"></a><span data-ttu-id="94614-540">ViBackwardChar</span><span class="sxs-lookup"><span data-stu-id="94614-540">ViBackwardChar</span></span>

<span data-ttu-id="94614-541">Vi 編集モードでカーソルを1文字左に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-541">Move the cursor one character to the left in the Vi edit mode.</span></span> <span data-ttu-id="94614-542">これにより、カーソルが複数行の入力の前の行に移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="94614-542">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="94614-543">Vi の挿入モード: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-543">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="94614-544">Vi コマンドモード: `<LeftArrow>` 、 `<Backspace>` 、 `<h>`</span><span class="sxs-lookup"><span data-stu-id="94614-544">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="94614-545">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="94614-545">ViBackwardWord</span></span>

<span data-ttu-id="94614-546">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-546">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="94614-547">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="94614-547">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="94614-548">Vi コマンドモード: `<b>`</span><span class="sxs-lookup"><span data-stu-id="94614-548">Vi command mode: `<b>`</span></span>

### <a name="viforwardchar"></a><span data-ttu-id="94614-549">ViForwardChar</span><span class="sxs-lookup"><span data-stu-id="94614-549">ViForwardChar</span></span>

<span data-ttu-id="94614-550">Vi 編集モードでカーソルを1文字右に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-550">Move the cursor one character to the right in the Vi edit mode.</span></span> <span data-ttu-id="94614-551">これにより、カーソルが複数行入力の次の行に移動する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="94614-551">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="94614-552">Vi の挿入モード: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-552">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="94614-553">Vi コマンドモード: `<RightArrow>` 、 `<Spacebar>` 、 `<l>`</span><span class="sxs-lookup"><span data-stu-id="94614-553">Vi command mode: `<RightArrow>`, `<Spacebar>`, `<l>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="94614-554">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="94614-554">ViEndOfGlob</span></span>

<span data-ttu-id="94614-555">区切り記号として空白文字のみを使用して、カーソルを単語の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-555">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="94614-556">Vi コマンドモード: `<E>`</span><span class="sxs-lookup"><span data-stu-id="94614-556">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="94614-557">Viendofの Glob</span><span class="sxs-lookup"><span data-stu-id="94614-557">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="94614-558">単語区切り記号として空白文字のみを使用して、前の単語の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-558">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="94614-559">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="94614-559">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="94614-560">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="94614-560">ViGotoBrace</span></span>

<span data-ttu-id="94614-561">GotoBrace に似ていますが、トークンベースではなく文字ベースです。</span><span class="sxs-lookup"><span data-stu-id="94614-561">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="94614-562">Vi コマンドモード: `<%>`</span><span class="sxs-lookup"><span data-stu-id="94614-562">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="94614-563">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="94614-563">ViNextGlob</span></span>

<span data-ttu-id="94614-564">単語区切り記号として空白文字のみを使用して、次の単語に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-564">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="94614-565">Vi コマンドモード: `<W>`</span><span class="sxs-lookup"><span data-stu-id="94614-565">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="94614-566">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="94614-566">ViNextWord</span></span>

<span data-ttu-id="94614-567">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-567">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="94614-568">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="94614-568">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="94614-569">Vi コマンドモード: `<w>`</span><span class="sxs-lookup"><span data-stu-id="94614-569">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="94614-570">履歴関数</span><span class="sxs-lookup"><span data-stu-id="94614-570">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="94614-571">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="94614-571">BeginningOfHistory</span></span>

<span data-ttu-id="94614-572">履歴内の最初の項目に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-572">Move to the first item in the history.</span></span>

- <span data-ttu-id="94614-573">.Emacs `<Alt+<>`</span><span class="sxs-lookup"><span data-stu-id="94614-573">Emacs: `<Alt+<>`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="94614-574">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="94614-574">ClearHistory</span></span>

<span data-ttu-id="94614-575">PSReadLine の履歴をクリアします。</span><span class="sxs-lookup"><span data-stu-id="94614-575">Clears history in PSReadLine.</span></span> <span data-ttu-id="94614-576">これは、PowerShell の履歴には影響しません。</span><span class="sxs-lookup"><span data-stu-id="94614-576">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="94614-577">コマンド: `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="94614-577">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="94614-578">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="94614-578">EndOfHistory</span></span>

<span data-ttu-id="94614-579">履歴内の最後の項目 (現在の入力) に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-579">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="94614-580">.Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="94614-580">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="94614-581">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="94614-581">ForwardSearchHistory</span></span>

<span data-ttu-id="94614-582">履歴を使用した増分転送検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="94614-582">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="94614-583">コマンド: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="94614-583">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="94614-584">.Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="94614-584">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="94614-585">履歴の Search後方</span><span class="sxs-lookup"><span data-stu-id="94614-585">HistorySearchBackward</span></span>

<span data-ttu-id="94614-586">現在の入力を、PSReadLine 履歴の ' previous ' 項目で置き換えます。この項目は、開始と入力の間の文字とカーソルの間の文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="94614-586">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="94614-587">コマンド: `<F8>`</span><span class="sxs-lookup"><span data-stu-id="94614-587">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="94614-588">履歴の Searchforward</span><span class="sxs-lookup"><span data-stu-id="94614-588">HistorySearchForward</span></span>

<span data-ttu-id="94614-589">現在の入力を、PSReadLine 履歴の ' next ' 項目で置き換えます。この項目は、開始と入力の間の文字とカーソルの間の文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="94614-589">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="94614-590">コマンド: `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="94614-590">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="94614-591">NextHistory</span><span class="sxs-lookup"><span data-stu-id="94614-591">NextHistory</span></span>

<span data-ttu-id="94614-592">現在の入力を、PSReadLine 履歴の ' next ' 項目に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="94614-592">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="94614-593">コマンド: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-593">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="94614-594">Emacs: `<DownArrow>` 、 `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="94614-594">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="94614-595">Vi の挿入モード: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-595">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="94614-596">Vi コマンドモード: `<DownArrow>` 、 `<j>` 、 `<+>`</span><span class="sxs-lookup"><span data-stu-id="94614-596">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="94614-597">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="94614-597">PreviousHistory</span></span>

<span data-ttu-id="94614-598">現在の入力を、PSReadLine 履歴の ' previous ' 項目に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="94614-598">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="94614-599">コマンド: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-599">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="94614-600">Emacs: `<UpArrow>` 、 `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="94614-600">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="94614-601">Vi の挿入モード: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-601">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="94614-602">Vi コマンドモード: `<UpArrow>` 、 `<k>` 、 `<->`</span><span class="sxs-lookup"><span data-stu-id="94614-602">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="94614-603">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="94614-603">ReverseSearchHistory</span></span>

<span data-ttu-id="94614-604">履歴を介して後方検索を段階的に実行します。</span><span class="sxs-lookup"><span data-stu-id="94614-604">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="94614-605">コマンド: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="94614-605">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="94614-606">.Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="94614-606">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="94614-607">Visearchhistory 後方</span><span class="sxs-lookup"><span data-stu-id="94614-607">ViSearchHistoryBackward</span></span>

<span data-ttu-id="94614-608">検索文字列を入力し、AcceptLine で検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="94614-608">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="94614-609">Vi の挿入モード: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="94614-609">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="94614-610">Vi コマンドモード: `</>` 、 `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="94614-610">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="94614-611">入力候補関数</span><span class="sxs-lookup"><span data-stu-id="94614-611">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="94614-612">完了</span><span class="sxs-lookup"><span data-stu-id="94614-612">Complete</span></span>

<span data-ttu-id="94614-613">カーソルを囲むテキストに対して入力候補を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="94614-613">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="94614-614">候補が複数ある場合は、最長の明確なプレフィックスを使用して完了します。</span><span class="sxs-lookup"><span data-stu-id="94614-614">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="94614-615">最長の明確な完了を完了しようとすると、候補の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="94614-615">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="94614-616">.Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="94614-616">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="94614-617">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="94614-617">MenuComplete</span></span>

<span data-ttu-id="94614-618">カーソルを囲むテキストに対して入力候補を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="94614-618">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="94614-619">候補が複数ある場合は、最長の明確なプレフィックスを使用して完了します。</span><span class="sxs-lookup"><span data-stu-id="94614-619">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="94614-620">最長の明確な完了を完了しようとすると、候補の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="94614-620">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="94614-621">Cmd: `<Ctrl+@>` 、 `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="94614-621">Cmd: `<Ctrl+@>`, `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="94614-622">.Emacs `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="94614-622">Emacs: `<Ctrl+Spacebar>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="94614-623">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="94614-623">PossibleCompletions</span></span>

<span data-ttu-id="94614-624">候補の候補の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="94614-624">Display the list of possible completions.</span></span>

- <span data-ttu-id="94614-625">.Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="94614-625">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="94614-626">Vi の挿入モード: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="94614-626">Vi insert mode: `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="94614-627">Vi コマンドモード: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="94614-627">Vi command mode: `<Ctrl+Spacebar>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="94614-628">タブのすべてのタブ</span><span class="sxs-lookup"><span data-stu-id="94614-628">TabCompleteNext</span></span>

<span data-ttu-id="94614-629">次に使用可能な完了時に、カーソルを囲むテキストを完了します。</span><span class="sxs-lookup"><span data-stu-id="94614-629">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="94614-630">コマンド: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="94614-630">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="94614-631">Vi コマンドモード: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="94614-631">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="94614-632">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="94614-632">TabCompletePrevious</span></span>

<span data-ttu-id="94614-633">以前に使用可能な入力候補を使用して、カーソルを囲むテキストを完了しようとしました。</span><span class="sxs-lookup"><span data-stu-id="94614-633">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="94614-634">コマンド: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="94614-634">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="94614-635">Vi コマンドモード: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="94614-635">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="94614-636">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="94614-636">ViTabCompleteNext</span></span>

<span data-ttu-id="94614-637">必要に応じて現在の編集グループを終了し、Tabends を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="94614-637">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="94614-638">Vi の挿入モード: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="94614-638">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="94614-639">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="94614-639">ViTabCompletePrevious</span></span>

<span data-ttu-id="94614-640">必要に応じて現在の編集グループを終了し、TabCompletePrevious を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="94614-640">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="94614-641">Vi の挿入モード: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="94614-641">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="94614-642">その他の関数</span><span class="sxs-lookup"><span data-stu-id="94614-642">Miscellaneous functions</span></span>

### <a name="acceptnextsuggestionword"></a><span data-ttu-id="94614-643">AcceptNextSuggestionWord</span><span class="sxs-lookup"><span data-stu-id="94614-643">AcceptNextSuggestionWord</span></span>

<span data-ttu-id="94614-644">インラインまたは選択した修正候補の次の単語をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="94614-644">Accept the next word of the inline or selected suggestion.</span></span>

- <span data-ttu-id="94614-645">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="94614-645">Function is unbound.</span></span>

### <a name="acceptsuggestion"></a><span data-ttu-id="94614-646">AcceptSuggestion</span><span class="sxs-lookup"><span data-stu-id="94614-646">AcceptSuggestion</span></span>

<span data-ttu-id="94614-647">現在のインラインまたは選択された提案を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="94614-647">Accept the current inline or selected suggestion.</span></span>

- <span data-ttu-id="94614-648">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="94614-648">Function is unbound.</span></span>

### <a name="capturescreen"></a><span data-ttu-id="94614-649">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="94614-649">CaptureScreen</span></span>

<span data-ttu-id="94614-650">対話型画面のキャプチャを開始する/下矢印行を選択し、[選択したテキストをテキストと html としてクリップボードにコピーする] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="94614-650">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="94614-651">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="94614-651">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="94614-652">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="94614-652">ClearScreen</span></span>

<span data-ttu-id="94614-653">画面をクリアし、画面の上部にある現在の線を描画します。</span><span class="sxs-lookup"><span data-stu-id="94614-653">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="94614-654">コマンド: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="94614-654">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="94614-655">.Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="94614-655">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="94614-656">Vi の挿入モード: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="94614-656">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="94614-657">Vi コマンドモード: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="94614-657">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="94614-658">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="94614-658">DigitArgument</span></span>

<span data-ttu-id="94614-659">他の関数に渡す新しい桁引数を開始します。</span><span class="sxs-lookup"><span data-stu-id="94614-659">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="94614-660">Cmd:、、、、、、、、、 `<Alt+0>` `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="94614-660">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="94614-661">Emacs:、、、、、、、、、 `<Alt+0>` `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="94614-661">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="94614-662">Vi コマンドモード:、、、、、、、、 `<0>` `<1>` `<2>` `<3>` `<4>` `<5>` `<6>` `<7>` `<8>` 、 `<9>`</span><span class="sxs-lookup"><span data-stu-id="94614-662">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="94614-663">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="94614-663">InvokePrompt</span></span>

<span data-ttu-id="94614-664">現在のプロンプトを消去し、prompt 関数を呼び出してプロンプトを再表示します。</span><span class="sxs-lookup"><span data-stu-id="94614-664">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="94614-665">現在のディレクトリを変更するなど、状態を変更するカスタムキーハンドラーに便利です。</span><span class="sxs-lookup"><span data-stu-id="94614-665">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="94614-666">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="94614-666">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="94614-667">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="94614-667">ScrollDisplayDown</span></span>

<span data-ttu-id="94614-668">画面を1画面下へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="94614-668">Scroll the display down one screen.</span></span>

- <span data-ttu-id="94614-669">コマンド: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="94614-669">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="94614-670">.Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="94614-670">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="94614-671">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="94614-671">ScrollDisplayDownLine</span></span>

<span data-ttu-id="94614-672">表示を1行下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="94614-672">Scroll the display down one line.</span></span>

- <span data-ttu-id="94614-673">コマンド: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="94614-673">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="94614-674">.Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="94614-674">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="94614-675">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="94614-675">ScrollDisplayToCursor</span></span>

<span data-ttu-id="94614-676">カーソルまで画面をスクロールします。</span><span class="sxs-lookup"><span data-stu-id="94614-676">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="94614-677">.Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="94614-677">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="94614-678">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="94614-678">ScrollDisplayTop</span></span>

<span data-ttu-id="94614-679">画面を上にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="94614-679">Scroll the display to the top.</span></span>

- <span data-ttu-id="94614-680">.Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="94614-680">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="94614-681">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="94614-681">ScrollDisplayUp</span></span>

<span data-ttu-id="94614-682">画面を1画面上へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="94614-682">Scroll the display up one screen.</span></span>

- <span data-ttu-id="94614-683">コマンド: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="94614-683">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="94614-684">.Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="94614-684">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="94614-685">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="94614-685">ScrollDisplayUpLine</span></span>

<span data-ttu-id="94614-686">表示を1行上へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="94614-686">Scroll the display up one line.</span></span>

- <span data-ttu-id="94614-687">コマンド: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="94614-687">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="94614-688">.Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="94614-688">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="94614-689">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="94614-689">SelfInsert</span></span>

<span data-ttu-id="94614-690">キーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="94614-690">Insert the key.</span></span>

- <span data-ttu-id="94614-691">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="94614-691">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="94614-692">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="94614-692">ShowKeyBindings</span></span>

<span data-ttu-id="94614-693">すべてのバインドされたキーを表示します。</span><span class="sxs-lookup"><span data-stu-id="94614-693">Show all bound keys.</span></span>

- <span data-ttu-id="94614-694">コマンド: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="94614-694">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="94614-695">.Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="94614-695">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="94614-696">Vi の挿入モード: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="94614-696">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="94614-697">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="94614-697">ViCommandMode</span></span>

<span data-ttu-id="94614-698">現在の動作モードを Vi-Insert から Vi-Command に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="94614-698">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="94614-699">Vi の挿入モード: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="94614-699">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="94614-700">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="94614-700">ViDigitArgumentInChord</span></span>

<span data-ttu-id="94614-701">Vi のいずれかの弦で、他の関数に渡す新しい桁引数を開始します。</span><span class="sxs-lookup"><span data-stu-id="94614-701">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="94614-702">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="94614-702">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="94614-703">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="94614-703">ViEditVisually</span></span>

<span data-ttu-id="94614-704">$Env: EDITOR または $env: ビジュアルによって指定されたテキストエディターでコマンドラインを編集します。</span><span class="sxs-lookup"><span data-stu-id="94614-704">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="94614-705">.Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="94614-705">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="94614-706">Vi コマンドモード: `<v>`</span><span class="sxs-lookup"><span data-stu-id="94614-706">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="94614-707">ViExit</span><span class="sxs-lookup"><span data-stu-id="94614-707">ViExit</span></span>

<span data-ttu-id="94614-708">シェルを終了します。</span><span class="sxs-lookup"><span data-stu-id="94614-708">Exits the shell.</span></span>

- <span data-ttu-id="94614-709">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="94614-709">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="94614-710">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="94614-710">ViInsertMode</span></span>

<span data-ttu-id="94614-711">挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="94614-711">Switch to Insert mode.</span></span>

- <span data-ttu-id="94614-712">Vi コマンドモード: `<i>`</span><span class="sxs-lookup"><span data-stu-id="94614-712">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="94614-713">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="94614-713">WhatIsKey</span></span>

<span data-ttu-id="94614-714">キーを読み取り、キーがどのようにバインドされているかを通知します。</span><span class="sxs-lookup"><span data-stu-id="94614-714">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="94614-715">コマンド: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="94614-715">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="94614-716">.Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="94614-716">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="94614-717">選択関数</span><span class="sxs-lookup"><span data-stu-id="94614-717">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="94614-718">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="94614-718">ExchangePointAndMark</span></span>

<span data-ttu-id="94614-719">カーソルがマークの位置に置かれ、マークがカーソルの位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-719">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="94614-720">.Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="94614-720">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="94614-721">SelectAll</span><span class="sxs-lookup"><span data-stu-id="94614-721">SelectAll</span></span>

<span data-ttu-id="94614-722">行全体を選択します。</span><span class="sxs-lookup"><span data-stu-id="94614-722">Select the entire line.</span></span>

- <span data-ttu-id="94614-723">コマンド: `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="94614-723">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="94614-724">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="94614-724">SelectBackwardChar</span></span>

<span data-ttu-id="94614-725">現在の選択範囲を調整して、前の文字を含めます。</span><span class="sxs-lookup"><span data-stu-id="94614-725">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="94614-726">コマンド: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-726">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="94614-727">.Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-727">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="94614-728">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="94614-728">SelectBackwardsLine</span></span>

<span data-ttu-id="94614-729">カーソルから行の先頭まで、現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="94614-729">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="94614-730">コマンド: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="94614-730">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="94614-731">.Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="94614-731">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="94614-732">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="94614-732">SelectBackwardWord</span></span>

<span data-ttu-id="94614-733">現在の選択範囲を調整して、前の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="94614-733">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="94614-734">コマンド: `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-734">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="94614-735">.Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="94614-735">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="94614-736">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="94614-736">SelectForwardChar</span></span>

<span data-ttu-id="94614-737">現在の選択範囲を調整して、次の文字を含めます。</span><span class="sxs-lookup"><span data-stu-id="94614-737">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="94614-738">コマンド: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-738">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="94614-739">.Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-739">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="94614-740">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="94614-740">SelectForwardWord</span></span>

<span data-ttu-id="94614-741">現在の選択範囲を調整して、ForwardWord を使用して次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="94614-741">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="94614-742">.Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="94614-742">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="94614-743">SelectLine</span><span class="sxs-lookup"><span data-stu-id="94614-743">SelectLine</span></span>

<span data-ttu-id="94614-744">カーソルから行の末尾まで、現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="94614-744">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="94614-745">コマンド: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="94614-745">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="94614-746">.Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="94614-746">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="94614-747">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="94614-747">SelectNextWord</span></span>

<span data-ttu-id="94614-748">現在の選択範囲を調整して、次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="94614-748">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="94614-749">コマンド: `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="94614-749">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="94614-750">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="94614-750">SelectShellBackwardWord</span></span>

<span data-ttu-id="94614-751">ShellBackwardWord を使用して、前の単語が含まれるように現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="94614-751">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="94614-752">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="94614-752">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="94614-753">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="94614-753">SelectShellForwardWord</span></span>

<span data-ttu-id="94614-754">現在の選択範囲を調整して、ShellForwardWord を使用する次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="94614-754">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="94614-755">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="94614-755">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="94614-756">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="94614-756">SelectShellNextWord</span></span>

<span data-ttu-id="94614-757">現在の選択範囲を調整して、ShellNextWord を使用して次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="94614-757">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="94614-758">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="94614-758">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="94614-759">SetMark</span><span class="sxs-lookup"><span data-stu-id="94614-759">SetMark</span></span>

<span data-ttu-id="94614-760">後続の編集コマンドで使用するために、カーソルの現在の位置をマークします。</span><span class="sxs-lookup"><span data-stu-id="94614-760">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="94614-761">.Emacs `<Ctrl+@>`</span><span class="sxs-lookup"><span data-stu-id="94614-761">Emacs: `<Ctrl+@>`</span></span>

## <a name="predictive-intellisense-functions"></a><span data-ttu-id="94614-762">予測 IntelliSense 関数</span><span class="sxs-lookup"><span data-stu-id="94614-762">Predictive IntelliSense functions</span></span>

> [!NOTE]
> <span data-ttu-id="94614-763">これらの関数を使用するには、予測 IntelliSense を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94614-763">Predictive IntelliSense needs to be enabled to use these functions.</span></span>

### <a name="acceptnextwordsuggestion"></a><span data-ttu-id="94614-764">AcceptNextWordSuggestion</span><span class="sxs-lookup"><span data-stu-id="94614-764">AcceptNextWordSuggestion</span></span>

<span data-ttu-id="94614-765">予測 IntelliSense からインライン提案の次の単語を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="94614-765">Accepts the next word of the inline suggestion from Predictive IntelliSense.</span></span>
<span data-ttu-id="94614-766">次のコマンドを実行して、この関数を<kbd>Ctrl</kbd> + <kbd>F</kbd>でバインドできます。</span><span class="sxs-lookup"><span data-stu-id="94614-766">This function can be bound with <kbd>Ctrl</kbd>+<kbd>F</kbd> by running the following command.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord "Ctrl+f" -Function ForwardWord
```

### <a name="acceptsuggestion"></a><span data-ttu-id="94614-767">AcceptSuggestion</span><span class="sxs-lookup"><span data-stu-id="94614-767">AcceptSuggestion</span></span>

<span data-ttu-id="94614-768">カーソルが現在の行の末尾にある場合に <kbd>→</kbd> を押すことで、予測 IntelliSense からの現在のインライン提案を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="94614-768">Accepts the current inline suggestion from Predictive IntelliSense by pressing <kbd>RightArrow</kbd> when the cursor is at the end of the current line.</span></span>

## <a name="search-functions"></a><span data-ttu-id="94614-769">関数の検索</span><span class="sxs-lookup"><span data-stu-id="94614-769">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="94614-770">文字検索</span><span class="sxs-lookup"><span data-stu-id="94614-770">CharacterSearch</span></span>

<span data-ttu-id="94614-771">文字を読み取り、その文字が次に出現するまで検索します。</span><span class="sxs-lookup"><span data-stu-id="94614-771">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="94614-772">引数が指定されている場合は、n 番目のオカレンスに対して前方 (負の場合は後方) を検索します。</span><span class="sxs-lookup"><span data-stu-id="94614-772">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="94614-773">コマンド: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="94614-773">Cmd: `<F3>`</span></span>
- <span data-ttu-id="94614-774">.Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="94614-774">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="94614-775">Vi の挿入モード: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="94614-775">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="94614-776">Vi コマンドモード: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="94614-776">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="94614-777">文字 Search後方</span><span class="sxs-lookup"><span data-stu-id="94614-777">CharacterSearchBackward</span></span>

<span data-ttu-id="94614-778">文字を読み取り、その文字が次に出現するまで検索します。</span><span class="sxs-lookup"><span data-stu-id="94614-778">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="94614-779">引数が指定されている場合は、n 番目のオカレンスに対して後方 (または負の場合は forward) を検索します。</span><span class="sxs-lookup"><span data-stu-id="94614-779">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="94614-780">コマンド: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="94614-780">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="94614-781">.Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="94614-781">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="94614-782">Vi の挿入モード: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="94614-782">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="94614-783">Vi コマンドモード: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="94614-783">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="94614-784">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="94614-784">RepeatLastCharSearch</span></span>

<span data-ttu-id="94614-785">最後に記録された文字の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="94614-785">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="94614-786">Vi コマンドモード: `<;>`</span><span class="sxs-lookup"><span data-stu-id="94614-786">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="94614-787">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="94614-787">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="94614-788">最後に記録された文字検索を逆方向に繰り返します。</span><span class="sxs-lookup"><span data-stu-id="94614-788">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="94614-789">Vi コマンドモード: `<,>`</span><span class="sxs-lookup"><span data-stu-id="94614-789">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="94614-790">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="94614-790">RepeatSearch</span></span>

<span data-ttu-id="94614-791">前と同じ方向に最後の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="94614-791">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="94614-792">Vi コマンドモード: `<n>`</span><span class="sxs-lookup"><span data-stu-id="94614-792">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="94614-793">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="94614-793">RepeatSearchBackward</span></span>

<span data-ttu-id="94614-794">前と同じ方向に最後の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="94614-794">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="94614-795">Vi コマンドモード: `<N>`</span><span class="sxs-lookup"><span data-stu-id="94614-795">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="94614-796">SearchChar</span><span class="sxs-lookup"><span data-stu-id="94614-796">SearchChar</span></span>

<span data-ttu-id="94614-797">次の文字を読み取って検索し、次に文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="94614-797">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="94614-798">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="94614-798">This is for 't' functionality.</span></span>

- <span data-ttu-id="94614-799">Vi コマンドモード: `<f>`</span><span class="sxs-lookup"><span data-stu-id="94614-799">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="94614-800">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="94614-800">SearchCharBackward</span></span>

<span data-ttu-id="94614-801">次の文字を読み取り、それを検索して後方に移動し、次に文字を戻します。</span><span class="sxs-lookup"><span data-stu-id="94614-801">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="94614-802">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="94614-802">This is for 'T' functionality.</span></span>

- <span data-ttu-id="94614-803">Vi コマンドモード: `<F>`</span><span class="sxs-lookup"><span data-stu-id="94614-803">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="94614-804">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="94614-804">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="94614-805">次の文字を読み取り、それを検索して後方に移動し、次に文字を戻します。</span><span class="sxs-lookup"><span data-stu-id="94614-805">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="94614-806">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="94614-806">This is for 'T' functionality.</span></span>

- <span data-ttu-id="94614-807">Vi コマンドモード: `<T>`</span><span class="sxs-lookup"><span data-stu-id="94614-807">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="94614-808">SearchCharWithBackoff オフ</span><span class="sxs-lookup"><span data-stu-id="94614-808">SearchCharWithBackoff</span></span>

<span data-ttu-id="94614-809">次の文字を読み取って検索し、次に文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="94614-809">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="94614-810">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="94614-810">This is for 't' functionality.</span></span>

- <span data-ttu-id="94614-811">Vi コマンドモード: `<t>`</span><span class="sxs-lookup"><span data-stu-id="94614-811">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="94614-812">SearchForward</span><span class="sxs-lookup"><span data-stu-id="94614-812">SearchForward</span></span>

<span data-ttu-id="94614-813">検索文字列を入力し、AcceptLine で検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="94614-813">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="94614-814">Vi の挿入モード: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="94614-814">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="94614-815">Vi コマンドモード: `<?>` 、 `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="94614-815">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="94614-816">カスタムキーバインド</span><span class="sxs-lookup"><span data-stu-id="94614-816">Custom Key Bindings</span></span>

<span data-ttu-id="94614-817">PSReadLine は、コマンドレットを使用してカスタムキーバインドをサポートしてい `Set-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="94614-817">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="94614-818">ほとんどのカスタムキーバインドは、たとえば、上記の関数の1つを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="94614-818">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="94614-819">ScriptBlock をキーにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="94614-819">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="94614-820">ScriptBlock は、ほとんどすべてのことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="94614-820">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="94614-821">いくつかの便利な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="94614-821">Some useful examples include</span></span>

- <span data-ttu-id="94614-822">コマンドラインを編集する</span><span class="sxs-lookup"><span data-stu-id="94614-822">edit the command line</span></span>
- <span data-ttu-id="94614-823">新しいウィンドウを開く (例: ヘルプ)</span><span class="sxs-lookup"><span data-stu-id="94614-823">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="94614-824">コマンドラインを変更せずにディレクトリを変更する</span><span class="sxs-lookup"><span data-stu-id="94614-824">change directories without changing the command line</span></span>

<span data-ttu-id="94614-825">ScriptBlock は、次の2つの引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="94614-825">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="94614-826">`$key` -カスタムバインドをトリガーしたキーである **[Consolekeyinfo]** オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="94614-826">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="94614-827">同じ ScriptBlock を複数のキーにバインドし、キーに応じて異なるアクションを実行する必要がある場合は、$key を確認します。</span><span class="sxs-lookup"><span data-stu-id="94614-827">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="94614-828">多くのカスタムバインドでは、この引数は無視します。</span><span class="sxs-lookup"><span data-stu-id="94614-828">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="94614-829">`$arg` -任意の引数。</span><span class="sxs-lookup"><span data-stu-id="94614-829">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="94614-830">多くの場合、これは、ユーザーがキーバインド DigitArgument から渡す整数引数になります。</span><span class="sxs-lookup"><span data-stu-id="94614-830">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="94614-831">バインディングが引数を受け入れない場合は、この引数を無視するのが妥当です。</span><span class="sxs-lookup"><span data-stu-id="94614-831">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="94614-832">ここでは、コマンドラインを実行せずに履歴に追加する例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="94614-832">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="94614-833">これは、何らかの操作を忘れた場合に、既に入力したコマンドラインを再入力したくない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="94614-833">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="94614-834">PSReadLine モジュールフォルダーにインストールされているファイルには、さらに多くの例が表示 `SamplePSReadLineProfile.ps1` されます。</span><span class="sxs-lookup"><span data-stu-id="94614-834">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="94614-835">ほとんどのキーバインドでは、コマンドラインを編集するためにいくつかのヘルパー関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="94614-835">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="94614-836">これらの Api については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="94614-836">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="94614-837">カスタムキーバインディングサポート Api</span><span class="sxs-lookup"><span data-stu-id="94614-837">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="94614-838">次の関数は PSConsoleReadLine では公開されていますが、キーに直接バインドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="94614-838">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="94614-839">多くの場合、カスタムキーバインドに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="94614-839">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="94614-840">コマンドラインを実行せずに、履歴に追加します。</span><span class="sxs-lookup"><span data-stu-id="94614-840">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="94614-841">Kill リングをクリアします。</span><span class="sxs-lookup"><span data-stu-id="94614-841">Clear the kill-ring.</span></span>  <span data-ttu-id="94614-842">これは主にテストに使用されます。</span><span class="sxs-lookup"><span data-stu-id="94614-842">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="94614-843">先頭から長さの文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="94614-843">Delete length characters from start.</span></span>  <span data-ttu-id="94614-844">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="94614-844">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="94614-845">ユーザー設定に基づいてアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="94614-845">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="94614-846">これらの2つの関数は、入力バッファーの現在の状態に関する有用な情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="94614-846">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="94614-847">1つ目は、単純なケースでよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="94614-847">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="94614-848">2つ目は、バインディングが Ast を使用してより高度な処理を実行している場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="94614-848">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(string[] Chord)
```

<span data-ttu-id="94614-849">この2つの関数は、によって使用され `Get-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="94614-849">These two functions are used by `Get-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="94614-850">最初のは、すべてのキーバインドを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="94614-850">The first is used to get all key bindings.</span></span> <span data-ttu-id="94614-851">2番目のは、特定のキーバインドを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="94614-851">The second is used to get specific key bindings.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="94614-852">この関数は Get-PSReadLineOption によって使用され、カスタムキーバインドではあまり役に立たない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="94614-852">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="94614-853">コマンドラインに何も選択されていない場合は、開始と長さの両方で-1 が返されます。</span><span class="sxs-lookup"><span data-stu-id="94614-853">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="94614-854">コマンドラインに選択項目がある場合は、選択範囲の先頭と長さが返されます。</span><span class="sxs-lookup"><span data-stu-id="94614-854">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="94614-855">カーソル位置に文字または文字列を挿入します。</span><span class="sxs-lookup"><span data-stu-id="94614-855">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="94614-856">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="94614-856">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="94614-857">これは、PSReadLine へのメインエントリポイントです。</span><span class="sxs-lookup"><span data-stu-id="94614-857">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="94614-858">再帰はサポートされないため、カスタムキーバインドでは役に立ちません。</span><span class="sxs-lookup"><span data-stu-id="94614-858">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="94614-859">この関数は Remove-PSReadLineKeyHandler によって使用され、カスタムキーバインドではあまり役に立たない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="94614-859">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="94614-860">入力の一部を置換します。</span><span class="sxs-lookup"><span data-stu-id="94614-860">Replace some of the input.</span></span> <span data-ttu-id="94614-861">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="94614-861">This operation supports undo/redo.</span></span> <span data-ttu-id="94614-862">これは、undo の単一のアクションとして扱われるため、Delete の後に Insert を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="94614-862">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="94614-863">カーソルを指定されたオフセットに移動します。</span><span class="sxs-lookup"><span data-stu-id="94614-863">Move the cursor to the given offset.</span></span> <span data-ttu-id="94614-864">カーソルの移動は、元に戻すために追跡されません。</span><span class="sxs-lookup"><span data-stu-id="94614-864">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="94614-865">この関数は、コマンドレットの設定-PSReadLineOption によって使用されるヘルパーメソッドですが、一時的に設定を変更する必要があるカスタムキーバインドに便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="94614-865">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="94614-866">このヘルパーメソッドは、DigitArgument を優先するカスタムバインドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="94614-866">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="94614-867">一般的な呼び出しは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="94614-867">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="94614-868">注意</span><span class="sxs-lookup"><span data-stu-id="94614-868">Note</span></span>

### <a name="command-history"></a><span data-ttu-id="94614-869">コマンド履歴</span><span class="sxs-lookup"><span data-stu-id="94614-869">Command History</span></span>

<span data-ttu-id="94614-870">PSReadLine は、コマンドラインから入力したすべてのコマンドとデータを含む履歴ファイルを保持します。</span><span class="sxs-lookup"><span data-stu-id="94614-870">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="94614-871">これには、パスワードなどの機密データが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="94614-871">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="94614-872">たとえば、コマンドレットを使用した場合、 `ConvertTo-SecureString` パスワードはプレーンテキストとして履歴ファイルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="94614-872">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="94614-873">履歴ファイルは、という名前のファイルです `$($host.Name)_history.txt` 。</span><span class="sxs-lookup"><span data-stu-id="94614-873">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="94614-874">Windows システムでは、履歴ファイルはに格納され `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` ます。</span><span class="sxs-lookup"><span data-stu-id="94614-874">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="94614-875">Windows 以外のシステムでは、履歴ファイルはまたはに格納され `$env:XDG_DATA_HOME/powershell/PSReadLine` `$env:HOME/.local/share/powershell/PSReadLine` ます。</span><span class="sxs-lookup"><span data-stu-id="94614-875">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="94614-876">PSReadLine に貢献しているフィードバック &</span><span class="sxs-lookup"><span data-stu-id="94614-876">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="94614-877">GitHub の PSReadLine</span><span class="sxs-lookup"><span data-stu-id="94614-877">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="94614-878">プル要求を送信したり、GitHub ページでフィードバックを送信したりしてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="94614-878">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="94614-879">参照</span><span class="sxs-lookup"><span data-stu-id="94614-879">See Also</span></span>

<span data-ttu-id="94614-880">PSReadLine は、GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) ライブラリの影響を強く受けます。</span><span class="sxs-lookup"><span data-stu-id="94614-880">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
