---
description: PSReadLine では、PowerShell コンソールでのコマンドライン編集エクスペリエンスが向上しています。
Locale: en-US
ms.date: 11/23/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: PSReadLine について
ms.openlocfilehash: b0c5950b2af6a866d0ffcfdd6ce7ad92a1763778
ms.sourcegitcommit: 77f6225ab0c8ea9faa1fe46b2ea15c178ec170e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2021
ms.locfileid: "100500214"
---
# <a name="psreadline"></a><span data-ttu-id="73d30-103">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="73d30-103">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="73d30-104">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="73d30-104">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="73d30-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="73d30-105">Short Description</span></span>

<span data-ttu-id="73d30-106">PSReadLine では、PowerShell コンソールでのコマンドライン編集エクスペリエンスが向上しています。</span><span class="sxs-lookup"><span data-stu-id="73d30-106">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="73d30-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="73d30-107">Long Description</span></span>

<span data-ttu-id="73d30-108">PSReadLine 2.2 では、PowerShell コンソールの強力なコマンドライン編集エクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-108">PSReadLine 2.2 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="73d30-109">次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="73d30-109">It provides:</span></span>

- <span data-ttu-id="73d30-110">コマンドラインの構文の色分け</span><span class="sxs-lookup"><span data-stu-id="73d30-110">Syntax coloring of the command line</span></span>
- <span data-ttu-id="73d30-111">構文エラーを視覚的に示します。</span><span class="sxs-lookup"><span data-stu-id="73d30-111">A visual indication of syntax errors</span></span>
- <span data-ttu-id="73d30-112">より優れたマルチラインエクスペリエンス (編集と履歴の両方)</span><span class="sxs-lookup"><span data-stu-id="73d30-112">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="73d30-113">カスタマイズ可能なキーバインド</span><span class="sxs-lookup"><span data-stu-id="73d30-113">Customizable key bindings</span></span>
- <span data-ttu-id="73d30-114">Cmd モードと Emacs モード</span><span class="sxs-lookup"><span data-stu-id="73d30-114">Cmd and Emacs modes</span></span>
- <span data-ttu-id="73d30-115">多くの構成オプション</span><span class="sxs-lookup"><span data-stu-id="73d30-115">Many configuration options</span></span>
- <span data-ttu-id="73d30-116">Bash スタイル補完 (Cmd モードでは省略可能、Emacs モードでは既定)</span><span class="sxs-lookup"><span data-stu-id="73d30-116">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="73d30-117">Emacs yank/kill-リング</span><span class="sxs-lookup"><span data-stu-id="73d30-117">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="73d30-118">PowerShell トークンベースの "word" の移動と強制終了</span><span class="sxs-lookup"><span data-stu-id="73d30-118">PowerShell token based "word" movement and kill</span></span>
- <span data-ttu-id="73d30-119">予測 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="73d30-119">Predictive IntelliSense</span></span>

<span data-ttu-id="73d30-120">PSReadLine 2.2.0 には、次の2つの新しい予測 IntelliSense 機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="73d30-120">PSReadLine 2.2.0 added two new predictive IntelliSense features:</span></span>

- <span data-ttu-id="73d30-121">**PredictionViewStyle** パラメーターを追加して、新しいを選択できるようにしました `ListView` 。</span><span class="sxs-lookup"><span data-stu-id="73d30-121">Added the **PredictionViewStyle** parameter to allow for the selection of the new `ListView`.</span></span>
- <span data-ttu-id="73d30-122">PSReadLine を PS 7.1 で導入された api に接続して、 `CommandPrediction` ユーザーがカスタムソースから提案を表示できる予測モジュールをインポートできるようにしました。</span><span class="sxs-lookup"><span data-stu-id="73d30-122">Connected PSReadLine to the `CommandPrediction` APIs introduced in PS 7.1 to allow a user can import a predictor module that can render the suggestions from a custom source.</span></span>

<span data-ttu-id="73d30-123">PSReadLine には PowerShell 3.0 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="73d30-123">PSReadLine requires PowerShell 3.0, or newer.</span></span> <span data-ttu-id="73d30-124">PSReadLine は、既定のコンソールホスト、Visual Studio Code、ウィンドウターミナルで動作します。</span><span class="sxs-lookup"><span data-stu-id="73d30-124">PSReadLine works with default console host, Visual Studio Code, and Window Terminal.</span></span> <span data-ttu-id="73d30-125">PowerShell ISE では機能しません。</span><span class="sxs-lookup"><span data-stu-id="73d30-125">It does not work in PowerShell ISE.</span></span>

<span data-ttu-id="73d30-126">PSReadLine 2.2.0 は PowerShell 7.2 に付属しており、サポートされているすべてのバージョンの PowerShell でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="73d30-126">PSReadLine 2.2.0 ships with PowerShell 7.2 and is supported in all supported versions of PowerShell.</span></span> <span data-ttu-id="73d30-127">PowerShell ギャラリーからインストールできます。</span><span class="sxs-lookup"><span data-stu-id="73d30-127">It is available to install from the PowerShell Gallery.</span></span>
<span data-ttu-id="73d30-128">サポートされているバージョンの PowerShell に PSReadLine 2.2.0 をインストールするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="73d30-128">To install PSReadLine 2.2.0 in a supported version of PowerShell run the following command.</span></span>

```powershell
Install-Module -Name PSReadLine -AllowPrerelease
```

> [!NOTE]
> <span data-ttu-id="73d30-129">PowerShell 7.0 以降では、スクリーンリーダープログラムが検出されると、PowerShell は Windows で PSReadLine の自動読み込みをスキップします。</span><span class="sxs-lookup"><span data-stu-id="73d30-129">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="73d30-130">現在、PSReadLine は、スクリーンリーダーではうまく機能しません。</span><span class="sxs-lookup"><span data-stu-id="73d30-130">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="73d30-131">Windows での PowerShell 7.0 の既定の表示と書式設定は正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="73d30-131">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="73d30-132">必要に応じて、モジュールを手動で読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="73d30-132">You can manually load the module if necessary.</span></span>

## <a name="predictive-intellisense"></a><span data-ttu-id="73d30-133">予測 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="73d30-133">Predictive IntelliSense</span></span>

<span data-ttu-id="73d30-134">予測 IntelliSense は、ユーザーがコマンドを正常に完了できるように、タブ補完の概念を追加したものです。</span><span class="sxs-lookup"><span data-stu-id="73d30-134">Predictive IntelliSense is an addition to the concept of tab completion that assists the user in successfully completing commands.</span></span> <span data-ttu-id="73d30-135">ユーザーは、ユーザーの履歴や追加のドメイン固有のプラグインからの照合予測に基づいて、完全なコマンドを検出、編集、および実行することができます。</span><span class="sxs-lookup"><span data-stu-id="73d30-135">It enables users to discover, edit, and execute full commands based on matching predictions from the user's history and additional domain specific plugins.</span></span>

### <a name="enable-predictive-intellisense"></a><span data-ttu-id="73d30-136">予測 IntelliSense を有効にする</span><span class="sxs-lookup"><span data-stu-id="73d30-136">Enable Predictive IntelliSense</span></span>

<span data-ttu-id="73d30-137">既定では、予測 IntelliSense は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="73d30-137">Predictive IntelliSense is disabled by default.</span></span> <span data-ttu-id="73d30-138">予測を有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="73d30-138">To enable predictions, just run the following command:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource History
```

<span data-ttu-id="73d30-139">**PredictionSource** パラメーターでは、ドメイン固有の要件とカスタムの要件に対してプラグインを受け入れることもできます。</span><span class="sxs-lookup"><span data-stu-id="73d30-139">The **PredictionSource** parameter can also accept plugins for domain specific and custom requirements.</span></span>

<span data-ttu-id="73d30-140">予測 IntelliSense を無効にするには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="73d30-140">To disable Predictive IntelliSense, just run:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource None
```

<span data-ttu-id="73d30-141">クラス **[PSConsoleReadLine]** では、次の関数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="73d30-141">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="73d30-142">基本的な編集関数</span><span class="sxs-lookup"><span data-stu-id="73d30-142">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="73d30-143">中止</span><span class="sxs-lookup"><span data-stu-id="73d30-143">Abort</span></span>

<span data-ttu-id="73d30-144">現在のアクション (増分履歴検索など) を中止します。</span><span class="sxs-lookup"><span data-stu-id="73d30-144">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="73d30-145">.Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="73d30-145">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="73d30-146">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="73d30-146">AcceptAndGetNext</span></span>

<span data-ttu-id="73d30-147">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="73d30-147">Attempt to execute the current input.</span></span> <span data-ttu-id="73d30-148">(AcceptLine など) 実行できる場合は、次に ReadLine が呼び出されたときに履歴から次の項目を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="73d30-148">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="73d30-149">.Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="73d30-149">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="73d30-150">AcceptLine</span><span class="sxs-lookup"><span data-stu-id="73d30-150">AcceptLine</span></span>

<span data-ttu-id="73d30-151">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="73d30-151">Attempt to execute the current input.</span></span> <span data-ttu-id="73d30-152">現在の入力が不完全な場合 (たとえば、終わりかっこ、角かっこ、または引用符がない場合)、継続のプロンプトは次の行に表示され、PSReadLine は現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="73d30-152">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="73d30-153">コマンド: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="73d30-153">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="73d30-154">.Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="73d30-154">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="73d30-155">Vi の挿入モード: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="73d30-155">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="73d30-156">AddLine</span><span class="sxs-lookup"><span data-stu-id="73d30-156">AddLine</span></span>

<span data-ttu-id="73d30-157">継続プロンプトが次の行に表示され、PSReadLine が現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="73d30-157">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="73d30-158">これは、単一行が単独で完全に入力されている場合でも、複数行の入力を1つのコマンドとして入力する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="73d30-158">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="73d30-159">コマンド: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="73d30-159">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="73d30-160">.Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="73d30-160">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="73d30-161">Vi の挿入モード: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="73d30-161">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="73d30-162">Vi コマンドモード: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="73d30-162">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="73d30-163">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="73d30-163">BackwardDeleteChar</span></span>

<span data-ttu-id="73d30-164">カーソルの前の文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-164">Delete the character before the cursor.</span></span>

- <span data-ttu-id="73d30-165">Cmd: `<Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="73d30-165">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="73d30-166">Emacs: `<Backspace>` 、 `<Ctrl+Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="73d30-166">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="73d30-167">Vi の挿入モード: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="73d30-167">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="73d30-168">Vi コマンドモード: `<X>` 、 `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="73d30-168">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="73d30-169">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="73d30-169">BackwardDeleteLine</span></span>

<span data-ttu-id="73d30-170">Like BackwardKillLine-行の先頭から先頭までのテキストを削除しますが、削除されたテキストはキルリングには挿入されません。</span><span class="sxs-lookup"><span data-stu-id="73d30-170">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="73d30-171">コマンド: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="73d30-171">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="73d30-172">Vi 挿入モード: `<Ctrl+u>` 、 `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="73d30-172">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="73d30-173">Vi コマンドモード: `<Ctrl+u>` 、 `<Ctrl+Home>` 、 `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="73d30-173">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="73d30-174">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="73d30-174">BackwardDeleteWord</span></span>

<span data-ttu-id="73d30-175">前の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-175">Deletes the previous word.</span></span>

- <span data-ttu-id="73d30-176">Vi コマンドモード: `<Ctrl+w>` 、 `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="73d30-176">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="73d30-177">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="73d30-177">BackwardKillLine</span></span>

<span data-ttu-id="73d30-178">入力の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="73d30-178">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="73d30-179">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-179">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="73d30-180">Emacs: `<Ctrl+u>` 、 `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="73d30-180">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="73d30-181">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="73d30-181">BackwardKillWord</span></span>

<span data-ttu-id="73d30-182">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="73d30-182">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="73d30-183">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="73d30-183">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="73d30-184">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-184">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="73d30-185">Cmd: `<Ctrl+Backspace>` 、 `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="73d30-185">Cmd: `<Ctrl+Backspace>`, `<Ctrl+w>`</span></span>
- <span data-ttu-id="73d30-186">Emacs: `<Alt+Backspace>` 、 `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="73d30-186">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="73d30-187">Vi の挿入モード: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="73d30-187">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="73d30-188">Vi コマンドモード: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="73d30-188">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="73d30-189">CancelLine</span><span class="sxs-lookup"><span data-stu-id="73d30-189">CancelLine</span></span>

<span data-ttu-id="73d30-190">入力を画面に残したまま、現在の入力を取り消しますが、プロンプトが再び評価されるように、ホストに戻ります。</span><span class="sxs-lookup"><span data-stu-id="73d30-190">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="73d30-191">Vi の挿入モード: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="73d30-191">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="73d30-192">Vi コマンドモード: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="73d30-192">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="73d30-193">コピー</span><span class="sxs-lookup"><span data-stu-id="73d30-193">Copy</span></span>

<span data-ttu-id="73d30-194">選択したリージョンをシステムクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="73d30-194">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="73d30-195">領域が選択されていない場合は、行全体をコピーします。</span><span class="sxs-lookup"><span data-stu-id="73d30-195">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="73d30-196">コマンド: `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="73d30-196">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="73d30-197">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="73d30-197">CopyOrCancelLine</span></span>

<span data-ttu-id="73d30-198">テキストが選択されている場合は、クリップボードにコピーします。それ以外の場合は、行をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="73d30-198">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="73d30-199">コマンド: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="73d30-199">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="73d30-200">.Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="73d30-200">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="73d30-201">［切り取り］</span><span class="sxs-lookup"><span data-stu-id="73d30-201">Cut</span></span>

<span data-ttu-id="73d30-202">削除されたテキストをシステムクリップボードに配置した、選択した領域を削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-202">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="73d30-203">コマンド: `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="73d30-203">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="73d30-204">Dele</span><span class="sxs-lookup"><span data-stu-id="73d30-204">DeleteChar</span></span>

<span data-ttu-id="73d30-205">カーソルの下の文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-205">Delete the character under the cursor.</span></span>

- <span data-ttu-id="73d30-206">コマンド: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="73d30-206">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="73d30-207">.Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="73d30-207">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="73d30-208">Vi の挿入モード: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="73d30-208">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="73d30-209">Vi コマンドモード: `<Delete>` 、 `<x>` 、 `<d,l>` 、 `<d,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="73d30-209">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Spacebar>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="73d30-210">Deleの Arorexit</span><span class="sxs-lookup"><span data-stu-id="73d30-210">DeleteCharOrExit</span></span>

<span data-ttu-id="73d30-211">カーソルの下の文字を削除するか、行が空の場合はプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="73d30-211">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="73d30-212">.Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="73d30-212">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofbuffer"></a><span data-ttu-id="73d30-213">DeleteEndOfBuffer</span><span class="sxs-lookup"><span data-stu-id="73d30-213">DeleteEndOfBuffer</span></span>

<span data-ttu-id="73d30-214">複数行バッファーの末尾までを削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-214">Deletes to the end of the multiline buffer.</span></span>

- <span data-ttu-id="73d30-215">Vi コマンドモード: `<d,G>`</span><span class="sxs-lookup"><span data-stu-id="73d30-215">Vi command mode: `<d,G>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="73d30-216">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="73d30-216">DeleteEndOfWord</span></span>

<span data-ttu-id="73d30-217">単語の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-217">Delete to the end of the word.</span></span>

- <span data-ttu-id="73d30-218">Vi コマンドモード: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="73d30-218">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="73d30-219">Deleteline.invoke に</span><span class="sxs-lookup"><span data-stu-id="73d30-219">DeleteLine</span></span>

<span data-ttu-id="73d30-220">複数行バッファーの現在の論理行を削除して、元に戻すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="73d30-220">Deletes the current logical line of a multiline buffer, enabling undo.</span></span>

- <span data-ttu-id="73d30-221">Vi コマンドモード: `<d,d>` 、 `<d,_>`</span><span class="sxs-lookup"><span data-stu-id="73d30-221">Vi command mode: `<d,d>`, `<d,_>`</span></span>

### <a name="deletepreviouslines"></a><span data-ttu-id="73d30-222">削除した行</span><span class="sxs-lookup"><span data-stu-id="73d30-222">DeletePreviousLines</span></span>

<span data-ttu-id="73d30-223">複数行バッファーの前に要求された論理行と現在の論理行を削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-223">Deletes the previous requested logical lines and the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="73d30-224">Vi コマンドモード: `<d,k>`</span><span class="sxs-lookup"><span data-stu-id="73d30-224">Vi command mode: `<d,k>`</span></span>

### <a name="deleterelativelines"></a><span data-ttu-id="73d30-225">DeleteRelativeLines</span><span class="sxs-lookup"><span data-stu-id="73d30-225">DeleteRelativeLines</span></span>

<span data-ttu-id="73d30-226">バッファーの先頭から複数行バッファーの現在の論理行に削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-226">Deletes from the beginning of the buffer to the current logical line in a multiline buffer.</span></span>

<span data-ttu-id="73d30-227">ほとんどの Vi コマンドと同様に、コマンドには、 `<d,g,g>` 絶対行番号を指定する数値引数 (現在の行番号と共に、削除する行の範囲を構成する) を付加することができます。</span><span class="sxs-lookup"><span data-stu-id="73d30-227">As most Vi commands, the `<d,g,g>` command can be prepended with a numeric argument that specifies an absolute line number, which, together with the current line number, make up a range of lines to be deleted.</span></span>
<span data-ttu-id="73d30-228">指定しない場合、数値引数の既定値は1です。これは、複数行バッファーの最初の論理行を参照します。</span><span class="sxs-lookup"><span data-stu-id="73d30-228">If not specified, the numeric argument defaults to 1, which refers to the first logical line in a multiline buffer.</span></span>

<span data-ttu-id="73d30-229">複数行から削除される実際の行数は、現在の論理行番号と指定された数値引数の差として計算されます。したがって、負の数になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73d30-229">The actual number of lines to be deleted from the multiline is computed as the difference between the current logical line number and the specified numeric argument, which can thus be negative.</span></span> <span data-ttu-id="73d30-230">そのため、メソッド名の _相対_ 部分です。</span><span class="sxs-lookup"><span data-stu-id="73d30-230">Hence the _relative_ part of method name.</span></span>

- <span data-ttu-id="73d30-231">Vi コマンドモード: `<d,g,g>`</span><span class="sxs-lookup"><span data-stu-id="73d30-231">Vi command mode: `<d,g,g>`</span></span>

### <a name="deletenextlines"></a><span data-ttu-id="73d30-232">Deleの配信行</span><span class="sxs-lookup"><span data-stu-id="73d30-232">DeleteNextLines</span></span>

<span data-ttu-id="73d30-233">複数行バッファーで現在の論理行と次に要求された論理行を削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-233">Deletes the current logical line and the next requested logical lines in a multiline buffer.</span></span>

- <span data-ttu-id="73d30-234">Vi コマンドモード: `<d,j>`</span><span class="sxs-lookup"><span data-stu-id="73d30-234">Vi command mode: `<d,j>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="73d30-235">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="73d30-235">DeleteLineToFirstChar</span></span>

<span data-ttu-id="73d30-236">複数行バッファーの現在の論理行の最初の空白以外の文字からを削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-236">Deletes from the first non-blank character of the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="73d30-237">Vi コマンドモード: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="73d30-237">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="73d30-238">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="73d30-238">DeleteToEnd</span></span>

<span data-ttu-id="73d30-239">行の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-239">Delete to the end of the line.</span></span>

- <span data-ttu-id="73d30-240">Vi コマンドモード: `<D>` 、 `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="73d30-240">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="73d30-241">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="73d30-241">DeleteWord</span></span>

<span data-ttu-id="73d30-242">次の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-242">Delete the next word.</span></span>

- <span data-ttu-id="73d30-243">Vi コマンドモード: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="73d30-243">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="73d30-244">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="73d30-244">ForwardDeleteLine</span></span>

<span data-ttu-id="73d30-245">同じように、Forwardは、行の末尾から最後までのテキストを削除しますが、削除されたテキストはキルリングには挿入されません。</span><span class="sxs-lookup"><span data-stu-id="73d30-245">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="73d30-246">コマンド: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="73d30-246">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="73d30-247">Vi の挿入モード: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="73d30-247">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="73d30-248">Vi コマンドモード: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="73d30-248">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="73d30-249">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="73d30-249">InsertLineAbove</span></span>

<span data-ttu-id="73d30-250">現在の行の上にカーソルがある場所に関係なく、現在の行の上に新しい空の行が作成されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-250">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="73d30-251">カーソルが新しい行の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-251">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="73d30-252">コマンド: `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="73d30-252">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="73d30-253">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="73d30-253">InsertLineBelow</span></span>

<span data-ttu-id="73d30-254">カーソルが現在の行にある場所に関係なく、現在の行の下に新しい空の行が作成されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-254">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="73d30-255">カーソルが新しい行の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-255">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="73d30-256">コマンド: `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="73d30-256">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="73d30-257">InvertCase</span><span class="sxs-lookup"><span data-stu-id="73d30-257">InvertCase</span></span>

<span data-ttu-id="73d30-258">現在の文字の大文字と小文字の区別を反転し、次の文字に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-258">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="73d30-259">Vi コマンドモード: `<~>`</span><span class="sxs-lookup"><span data-stu-id="73d30-259">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="73d30-260">行の行</span><span class="sxs-lookup"><span data-stu-id="73d30-260">KillLine</span></span>

<span data-ttu-id="73d30-261">カーソルから入力の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="73d30-261">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="73d30-262">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-262">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="73d30-263">.Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="73d30-263">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="73d30-264">"/" 領域</span><span class="sxs-lookup"><span data-stu-id="73d30-264">KillRegion</span></span>

<span data-ttu-id="73d30-265">カーソルとマークの間のテキストを強制終了します。</span><span class="sxs-lookup"><span data-stu-id="73d30-265">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="73d30-266">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-266">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="73d30-267">文字の候補</span><span class="sxs-lookup"><span data-stu-id="73d30-267">KillWord</span></span>

<span data-ttu-id="73d30-268">カーソルから現在の単語の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="73d30-268">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="73d30-269">カーソルが単語の間にある場合は、カーソルから次の単語の末尾まで、入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="73d30-269">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="73d30-270">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-270">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="73d30-271">Cmd: `<Alt+d>` 、 `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="73d30-271">Cmd: `<Alt+d>`, `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="73d30-272">Emacs: `<Alt+d>` 、 `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="73d30-272">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="73d30-273">Vi の挿入モード: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="73d30-273">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="73d30-274">Vi コマンドモード: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="73d30-274">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="73d30-275">貼り付け</span><span class="sxs-lookup"><span data-stu-id="73d30-275">Paste</span></span>

<span data-ttu-id="73d30-276">システムクリップボードからテキストを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="73d30-276">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="73d30-277">Cmd: `<Ctrl+v>` 、 `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="73d30-277">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="73d30-278">Vi の挿入モード: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="73d30-278">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="73d30-279">Vi コマンドモード: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="73d30-279">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73d30-280">**貼り付け** 関数を使用すると、クリップボードバッファーの内容全体が psreadline の入力バッファーに貼り付けられます。</span><span class="sxs-lookup"><span data-stu-id="73d30-280">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="73d30-281">入力バッファーが PowerShell パーサーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-281">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="73d30-282">コンソールアプリケーションの **右クリック** による貼り付けメソッドを使用して貼り付けた入力は、一度に1文字ずつ入力バッファーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="73d30-282">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="73d30-283">入力バッファーは、改行文字がコピーされるときにパーサーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-283">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="73d30-284">そのため、入力は一度に1行ずつ解析されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-284">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="73d30-285">貼り付けメソッドの違いによって、実行の動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="73d30-285">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="73d30-286">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="73d30-286">PasteAfter</span></span>

<span data-ttu-id="73d30-287">カーソルの後にクリップボードを貼り付けて、貼り付けられたテキストの末尾にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-287">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="73d30-288">Vi コマンドモード: `<p>`</span><span class="sxs-lookup"><span data-stu-id="73d30-288">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="73d30-289">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="73d30-289">PasteBefore</span></span>

<span data-ttu-id="73d30-290">カーソルの前にクリップボードを貼り付けて、貼り付けられたテキストの末尾にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-290">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="73d30-291">Vi コマンドモード: `<P>`</span><span class="sxs-lookup"><span data-stu-id="73d30-291">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="73d30-292">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="73d30-292">PrependAndAccept</span></span>

<span data-ttu-id="73d30-293">' # ' を先頭に付加し、その行を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="73d30-293">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="73d30-294">Vi コマンドモード: `<#>`</span><span class="sxs-lookup"><span data-stu-id="73d30-294">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="73d30-295">やり直す</span><span class="sxs-lookup"><span data-stu-id="73d30-295">Redo</span></span>

<span data-ttu-id="73d30-296">元に戻す操作を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="73d30-296">Undo an undo.</span></span>

- <span data-ttu-id="73d30-297">コマンド: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="73d30-297">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="73d30-298">Vi の挿入モード: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="73d30-298">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="73d30-299">Vi コマンドモード: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="73d30-299">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="73d30-300">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="73d30-300">RepeatLastCommand</span></span>

<span data-ttu-id="73d30-301">最後のテキストの変更を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="73d30-301">Repeat the last text modification.</span></span>

- <span data-ttu-id="73d30-302">Vi コマンドモード: `<.>`</span><span class="sxs-lookup"><span data-stu-id="73d30-302">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="73d30-303">再有効化</span><span class="sxs-lookup"><span data-stu-id="73d30-303">RevertLine</span></span>

<span data-ttu-id="73d30-304">すべての入力を現在の入力に戻します。</span><span class="sxs-lookup"><span data-stu-id="73d30-304">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="73d30-305">コマンド: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="73d30-305">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="73d30-306">Emacs: `<Alt+r>` 、 `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="73d30-306">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="73d30-307">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="73d30-307">ShellBackwardKillWord</span></span>

<span data-ttu-id="73d30-308">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="73d30-308">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="73d30-309">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="73d30-309">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="73d30-310">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-310">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="73d30-311">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-311">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="73d30-312">Shellは Word</span><span class="sxs-lookup"><span data-stu-id="73d30-312">ShellKillWord</span></span>

<span data-ttu-id="73d30-313">カーソルから現在の単語の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="73d30-313">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="73d30-314">カーソルが単語の間にある場合は、カーソルから次の単語の末尾まで、入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="73d30-314">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="73d30-315">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-315">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="73d30-316">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-316">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="73d30-317">スワップ文字</span><span class="sxs-lookup"><span data-stu-id="73d30-317">SwapCharacters</span></span>

<span data-ttu-id="73d30-318">現在の文字とそれより前の文字を交換します。</span><span class="sxs-lookup"><span data-stu-id="73d30-318">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="73d30-319">.Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="73d30-319">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="73d30-320">Vi の挿入モード: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="73d30-320">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="73d30-321">Vi コマンドモード: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="73d30-321">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="73d30-322">元に戻す</span><span class="sxs-lookup"><span data-stu-id="73d30-322">Undo</span></span>

<span data-ttu-id="73d30-323">前の編集を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="73d30-323">Undo a previous edit.</span></span>

- <span data-ttu-id="73d30-324">コマンド: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="73d30-324">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="73d30-325">Emacs: `<Ctrl+_>` 、 `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="73d30-325">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="73d30-326">Vi の挿入モード: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="73d30-326">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="73d30-327">Vi コマンドモード: `<Ctrl+z>` 、 `<u>`</span><span class="sxs-lookup"><span data-stu-id="73d30-327">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="73d30-328">UndoAll</span><span class="sxs-lookup"><span data-stu-id="73d30-328">UndoAll</span></span>

<span data-ttu-id="73d30-329">行の以前の編集をすべて元に戻します。</span><span class="sxs-lookup"><span data-stu-id="73d30-329">Undo all previous edits for line.</span></span>

- <span data-ttu-id="73d30-330">Vi コマンドモード: `<U>`</span><span class="sxs-lookup"><span data-stu-id="73d30-330">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="73d30-331">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="73d30-331">UnixWordRubout</span></span>

<span data-ttu-id="73d30-332">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="73d30-332">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="73d30-333">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="73d30-333">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="73d30-334">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-334">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="73d30-335">.Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="73d30-335">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="73d30-336">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="73d30-336">ValidateAndAcceptLine</span></span>

<span data-ttu-id="73d30-337">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="73d30-337">Attempt to execute the current input.</span></span> <span data-ttu-id="73d30-338">現在の入力が不完全な場合 (たとえば、終わりかっこ、角かっこ、または引用符がない場合)、継続のプロンプトは次の行に表示され、PSReadLine は現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="73d30-338">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="73d30-339">.Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="73d30-339">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="73d30-340">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="73d30-340">ViAcceptLine</span></span>

<span data-ttu-id="73d30-341">行を受け入れ、挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="73d30-341">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="73d30-342">Vi コマンドモード: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="73d30-342">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="73d30-343">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="73d30-343">ViAcceptLineOrExit</span></span>

<span data-ttu-id="73d30-344">(Emacs モードでは Deleと同じですが、文字を削除するのではなく、行を受け取ります)。</span><span class="sxs-lookup"><span data-stu-id="73d30-344">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="73d30-345">Vi の挿入モード: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="73d30-345">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="73d30-346">Vi コマンドモード: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="73d30-346">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="73d30-347">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="73d30-347">ViAppendLine</span></span>

<span data-ttu-id="73d30-348">現在の行の下に新しい行が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-348">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="73d30-349">Vi コマンドモード: `<o>`</span><span class="sxs-lookup"><span data-stu-id="73d30-349">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="73d30-350">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="73d30-350">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="73d30-351">単語区切り記号として空白文字のみを使用して、前の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-351">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="73d30-352">Vi コマンドモード: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="73d30-352">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="73d30-353">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="73d30-353">ViBackwardGlob</span></span>

<span data-ttu-id="73d30-354">区切り記号として空白文字のみを使用して、カーソルを前の単語の先頭に戻します。</span><span class="sxs-lookup"><span data-stu-id="73d30-354">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="73d30-355">Vi コマンドモード: `<B>`</span><span class="sxs-lookup"><span data-stu-id="73d30-355">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="73d30-356">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="73d30-356">ViDeleteBrace</span></span>

<span data-ttu-id="73d30-357">対応する中かっこ、かっこ、または角かっこを検索し、中かっこを含め、内のすべての内容を削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-357">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="73d30-358">Vi コマンドモード: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="73d30-358">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="73d30-359">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="73d30-359">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="73d30-360">単語の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-360">Delete to the end of the word.</span></span>

- <span data-ttu-id="73d30-361">Vi コマンドモード: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="73d30-361">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="73d30-362">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="73d30-362">ViDeleteGlob</span></span>

<span data-ttu-id="73d30-363">次の glob (空白で区切られた単語) を削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-363">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="73d30-364">Vi コマンドモード: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="73d30-364">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="73d30-365">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="73d30-365">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="73d30-366">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-366">Deletes until given character.</span></span>

- <span data-ttu-id="73d30-367">Vi コマンドモード: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="73d30-367">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="73d30-368">Videletetobeforo</span><span class="sxs-lookup"><span data-stu-id="73d30-368">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="73d30-369">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-369">Deletes until given character.</span></span>

- <span data-ttu-id="73d30-370">Vi コマンドモード: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="73d30-370">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="73d30-371">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="73d30-371">ViDeleteToChar</span></span>

<span data-ttu-id="73d30-372">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-372">Deletes until given character.</span></span>

- <span data-ttu-id="73d30-373">Vi コマンドモード: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="73d30-373">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="73d30-374">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="73d30-374">ViDeleteToCharBackward</span></span>

<span data-ttu-id="73d30-375">指定された文字まで後方を削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-375">Deletes backwards until given character.</span></span>

- <span data-ttu-id="73d30-376">Vi コマンドモード: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="73d30-376">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="73d30-377">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="73d30-377">ViInsertAtBegining</span></span>

<span data-ttu-id="73d30-378">挿入モードに切り替え、カーソルを行の先頭に配置します。</span><span class="sxs-lookup"><span data-stu-id="73d30-378">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="73d30-379">Vi コマンドモード: `<I>`</span><span class="sxs-lookup"><span data-stu-id="73d30-379">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="73d30-380">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="73d30-380">ViInsertAtEnd</span></span>

<span data-ttu-id="73d30-381">挿入モードに切り替え、カーソルを行の末尾に配置します。</span><span class="sxs-lookup"><span data-stu-id="73d30-381">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="73d30-382">Vi コマンドモード: `<A>`</span><span class="sxs-lookup"><span data-stu-id="73d30-382">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="73d30-383">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="73d30-383">ViInsertLine</span></span>

<span data-ttu-id="73d30-384">現在の行の上に新しい行が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-384">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="73d30-385">Vi コマンドモード: `<O>`</span><span class="sxs-lookup"><span data-stu-id="73d30-385">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="73d30-386">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="73d30-386">ViInsertWithAppend</span></span>

<span data-ttu-id="73d30-387">現在の行の位置から追加します。</span><span class="sxs-lookup"><span data-stu-id="73d30-387">Append from the current line position.</span></span>

- <span data-ttu-id="73d30-388">Vi コマンドモード: `<a>`</span><span class="sxs-lookup"><span data-stu-id="73d30-388">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="73d30-389">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="73d30-389">ViInsertWithDelete</span></span>

<span data-ttu-id="73d30-390">現在の文字を削除し、挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="73d30-390">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="73d30-391">Vi コマンドモード: `<s>`</span><span class="sxs-lookup"><span data-stu-id="73d30-391">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="73d30-392">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="73d30-392">ViJoinLines</span></span>

<span data-ttu-id="73d30-393">現在の行と次の行を結合します。</span><span class="sxs-lookup"><span data-stu-id="73d30-393">Joins the current line and the next line.</span></span>

- <span data-ttu-id="73d30-394">Vi コマンドモード: `<J>`</span><span class="sxs-lookup"><span data-stu-id="73d30-394">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="73d30-395">交換ライン</span><span class="sxs-lookup"><span data-stu-id="73d30-395">ViReplaceLine</span></span>

<span data-ttu-id="73d30-396">コマンドライン全体を消去します。</span><span class="sxs-lookup"><span data-stu-id="73d30-396">Erase the entire command line.</span></span>

- <span data-ttu-id="73d30-397">Vi コマンドモード: `<S>` 、 `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="73d30-397">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="73d30-398">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="73d30-398">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="73d30-399">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="73d30-399">Replaces until given character.</span></span>

- <span data-ttu-id="73d30-400">Vi コマンドモード: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="73d30-400">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="73d30-401">Vireplacetobeforo</span><span class="sxs-lookup"><span data-stu-id="73d30-401">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="73d30-402">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="73d30-402">Replaces until given character.</span></span>

- <span data-ttu-id="73d30-403">Vi コマンドモード: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="73d30-403">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="73d30-404">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="73d30-404">ViReplaceToChar</span></span>

<span data-ttu-id="73d30-405">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-405">Deletes until given character.</span></span>

- <span data-ttu-id="73d30-406">Vi コマンドモード: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="73d30-406">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="73d30-407">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="73d30-407">ViReplaceToCharBackward</span></span>

<span data-ttu-id="73d30-408">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="73d30-408">Replaces until given character.</span></span>

- <span data-ttu-id="73d30-409">Vi コマンドモード: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="73d30-409">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="73d30-410">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="73d30-410">ViYankBeginningOfLine</span></span>

<span data-ttu-id="73d30-411">バッファーの先頭からカーソルまで Yank。</span><span class="sxs-lookup"><span data-stu-id="73d30-411">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="73d30-412">Vi コマンドモード: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="73d30-412">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="73d30-413">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="73d30-413">ViYankEndOfGlob</span></span>

<span data-ttu-id="73d30-414">カーソルから単語の末尾まで Yank します。</span><span class="sxs-lookup"><span data-stu-id="73d30-414">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="73d30-415">Vi コマンドモード: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="73d30-415">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="73d30-416">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="73d30-416">ViYankEndOfWord</span></span>

<span data-ttu-id="73d30-417">カーソルから単語の末尾まで Yank します。</span><span class="sxs-lookup"><span data-stu-id="73d30-417">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="73d30-418">Vi コマンドモード: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="73d30-418">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="73d30-419">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="73d30-419">ViYankLeft</span></span>

<span data-ttu-id="73d30-420">カーソルの左側の文字を Yank します。</span><span class="sxs-lookup"><span data-stu-id="73d30-420">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="73d30-421">Vi コマンドモード: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="73d30-421">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="73d30-422">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="73d30-422">ViYankLine</span></span>

<span data-ttu-id="73d30-423">バッファー全体を Yank します。</span><span class="sxs-lookup"><span data-stu-id="73d30-423">Yank the entire buffer.</span></span>

- <span data-ttu-id="73d30-424">Vi コマンドモード: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="73d30-424">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="73d30-425">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="73d30-425">ViYankNextGlob</span></span>

<span data-ttu-id="73d30-426">Yank は、次の単語の先頭にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="73d30-426">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="73d30-427">Vi コマンドモード: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="73d30-427">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="73d30-428">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="73d30-428">ViYankNextWord</span></span>

<span data-ttu-id="73d30-429">カーソルの後の単語を Yank します。</span><span class="sxs-lookup"><span data-stu-id="73d30-429">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="73d30-430">Vi コマンドモード: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="73d30-430">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="73d30-431">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="73d30-431">ViYankPercent</span></span>

<span data-ttu-id="73d30-432">一致する中かっこを Yank します。</span><span class="sxs-lookup"><span data-stu-id="73d30-432">Yank to/from matching brace.</span></span>

- <span data-ttu-id="73d30-433">Vi コマンドモード: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="73d30-433">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="73d30-434">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="73d30-434">ViYankPreviousGlob</span></span>

<span data-ttu-id="73d30-435">Yank は、単語の先頭からカーソルになります。</span><span class="sxs-lookup"><span data-stu-id="73d30-435">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="73d30-436">Vi コマンドモード: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="73d30-436">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="73d30-437">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="73d30-437">ViYankPreviousWord</span></span>

<span data-ttu-id="73d30-438">カーソルの前に単語を Yank します。</span><span class="sxs-lookup"><span data-stu-id="73d30-438">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="73d30-439">Vi コマンドモード: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="73d30-439">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="73d30-440">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="73d30-440">ViYankRight</span></span>

<span data-ttu-id="73d30-441">カーソルの右側に Yank 文字があります。</span><span class="sxs-lookup"><span data-stu-id="73d30-441">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="73d30-442">Vi コマンドモード: `<y,l>` 、 `<y,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="73d30-442">Vi command mode: `<y,l>`, `<y,Spacebar>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="73d30-443">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="73d30-443">ViYankToEndOfLine</span></span>

<span data-ttu-id="73d30-444">カーソルからバッファーの末尾までの Yank。</span><span class="sxs-lookup"><span data-stu-id="73d30-444">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="73d30-445">Vi コマンドモード: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="73d30-445">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="73d30-446">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="73d30-446">ViYankToFirstChar</span></span>

<span data-ttu-id="73d30-447">最初の空白以外の文字からカーソルまで Yank ます。</span><span class="sxs-lookup"><span data-stu-id="73d30-447">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="73d30-448">Vi コマンドモード: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="73d30-448">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="73d30-449">Yank</span><span class="sxs-lookup"><span data-stu-id="73d30-449">Yank</span></span>

<span data-ttu-id="73d30-450">最後に終了したテキストを入力に追加します。</span><span class="sxs-lookup"><span data-stu-id="73d30-450">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="73d30-451">.Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="73d30-451">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="73d30-452">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="73d30-452">YankLastArg</span></span>

<span data-ttu-id="73d30-453">前の履歴行の最後の引数を Yank します。</span><span class="sxs-lookup"><span data-stu-id="73d30-453">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="73d30-454">引数を使用すると、最初に呼び出されたときに、YankNthArg と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="73d30-454">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="73d30-455">複数回呼び出された場合は、代わりに履歴を反復処理し、引数に方向を設定します (負の方向が反転します)。</span><span class="sxs-lookup"><span data-stu-id="73d30-455">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="73d30-456">コマンド: `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="73d30-456">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="73d30-457">Emacs: `<Alt+.>` 、 `<Alt+_>` 、 `<Escape,.>` 、 `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="73d30-457">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="73d30-458">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="73d30-458">YankNthArg</span></span>

<span data-ttu-id="73d30-459">Yank は、前の履歴行から (コマンドの後に) 最初の引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="73d30-459">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="73d30-460">引数を使用して、n 番目の引数 (0 から始まる) を yank します。引数が負の場合は、最後の引数から開始します。</span><span class="sxs-lookup"><span data-stu-id="73d30-460">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="73d30-461">Emacs: `<Ctrl+Alt+y>` 、 `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="73d30-461">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="73d30-462">YankPop</span><span class="sxs-lookup"><span data-stu-id="73d30-462">YankPop</span></span>

<span data-ttu-id="73d30-463">前の操作が Yank または YankPop であった場合は、以前の引き抜かテキストをキルリングから次に強制終了されたテキストに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="73d30-463">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="73d30-464">Emacs: `<Alt+y>` 、 `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="73d30-464">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="73d30-465">カーソルの移動関数</span><span class="sxs-lookup"><span data-stu-id="73d30-465">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="73d30-466">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="73d30-466">BackwardChar</span></span>

<span data-ttu-id="73d30-467">カーソルを1文字左に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-467">Move the cursor one character to the left.</span></span> <span data-ttu-id="73d30-468">これにより、カーソルが複数行の入力の前の行に移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="73d30-468">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="73d30-469">コマンド: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-469">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="73d30-470">Emacs: `<LeftArrow>` 、 `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="73d30-470">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="73d30-471">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="73d30-471">BackwardWord</span></span>

<span data-ttu-id="73d30-472">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-472">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="73d30-473">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-473">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="73d30-474">コマンド: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-474">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="73d30-475">Emacs: `<Alt+b>` 、 `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="73d30-475">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="73d30-476">Vi の挿入モード: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-476">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="73d30-477">Vi コマンドモード: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-477">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="73d30-478">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="73d30-478">BeginningOfLine</span></span>

<span data-ttu-id="73d30-479">入力に複数の行がある場合は、現在の行の先頭に移動します。または、既に行の先頭にある場合は、入力の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-479">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="73d30-480">入力に1行しか含まれていない場合は、入力の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-480">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="73d30-481">コマンド: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="73d30-481">Cmd: `<Home>`</span></span>
- <span data-ttu-id="73d30-482">Emacs: `<Home>` 、 `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="73d30-482">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="73d30-483">Vi の挿入モード: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="73d30-483">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="73d30-484">Vi コマンドモード: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="73d30-484">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="73d30-485">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="73d30-485">EndOfLine</span></span>

<span data-ttu-id="73d30-486">入力に複数の行がある場合は、現在の行の末尾に移動します。または、既に行の末尾にある場合は、入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-486">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="73d30-487">入力に1行しか含まれていない場合は、入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-487">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="73d30-488">コマンド: `<End>`</span><span class="sxs-lookup"><span data-stu-id="73d30-488">Cmd: `<End>`</span></span>
- <span data-ttu-id="73d30-489">Emacs: `<End>` 、 `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="73d30-489">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="73d30-490">Vi の挿入モード: `<End>`</span><span class="sxs-lookup"><span data-stu-id="73d30-490">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="73d30-491">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="73d30-491">ForwardChar</span></span>

<span data-ttu-id="73d30-492">カーソルを1文字右に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-492">Move the cursor one character to the right.</span></span> <span data-ttu-id="73d30-493">これにより、カーソルが複数行入力の次の行に移動する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73d30-493">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="73d30-494">コマンド: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-494">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="73d30-495">Emacs: `<RightArrow>` 、 `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="73d30-495">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="73d30-496">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="73d30-496">ForwardWord</span></span>

<span data-ttu-id="73d30-497">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-497">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="73d30-498">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-498">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="73d30-499">Emacs: `<Alt+f>` 、 `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="73d30-499">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="73d30-500">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="73d30-500">GotoBrace</span></span>

<span data-ttu-id="73d30-501">対応する中かっこ、かっこ、または角かっこにジャンプします。</span><span class="sxs-lookup"><span data-stu-id="73d30-501">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="73d30-502">コマンド: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="73d30-502">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="73d30-503">Vi の挿入モード: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="73d30-503">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="73d30-504">Vi コマンドモード: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="73d30-504">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="73d30-505">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="73d30-505">GotoColumn</span></span>

<span data-ttu-id="73d30-506">Arg で示される列に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-506">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="73d30-507">Vi コマンドモード: `<|>`</span><span class="sxs-lookup"><span data-stu-id="73d30-507">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="73d30-508">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="73d30-508">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="73d30-509">カーソルを行の空白以外の最初の文字に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-509">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="73d30-510">Vi コマンドモード: `<^>` 、 `<_>`</span><span class="sxs-lookup"><span data-stu-id="73d30-510">Vi command mode: `<^>`, `<_>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="73d30-511">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="73d30-511">MoveToEndOfLine</span></span>

<span data-ttu-id="73d30-512">カーソルを入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-512">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="73d30-513">Vi コマンドモード: `<End>` 、 `<$>`</span><span class="sxs-lookup"><span data-stu-id="73d30-513">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="73d30-514">NextLine</span><span class="sxs-lookup"><span data-stu-id="73d30-514">NextLine</span></span>

<span data-ttu-id="73d30-515">カーソルを次の行に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-515">Move the cursor to the next line.</span></span>

- <span data-ttu-id="73d30-516">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-516">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="73d30-517">NextWord</span><span class="sxs-lookup"><span data-stu-id="73d30-517">NextWord</span></span>

<span data-ttu-id="73d30-518">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-518">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="73d30-519">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-519">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="73d30-520">コマンド: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-520">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="73d30-521">Vi の挿入モード: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-521">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="73d30-522">Vi コマンドモード: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-522">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="73d30-523">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="73d30-523">NextWordEnd</span></span>

<span data-ttu-id="73d30-524">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-524">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="73d30-525">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-525">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="73d30-526">Vi コマンドモード: `<e>`</span><span class="sxs-lookup"><span data-stu-id="73d30-526">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="73d30-527">前の行</span><span class="sxs-lookup"><span data-stu-id="73d30-527">PreviousLine</span></span>

<span data-ttu-id="73d30-528">カーソルを前の行に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-528">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="73d30-529">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-529">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="73d30-530">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="73d30-530">ShellBackwardWord</span></span>

<span data-ttu-id="73d30-531">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-531">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="73d30-532">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-532">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="73d30-533">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-533">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="73d30-534">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="73d30-534">ShellForwardWord</span></span>

<span data-ttu-id="73d30-535">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-535">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="73d30-536">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-536">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="73d30-537">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-537">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="73d30-538">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="73d30-538">ShellNextWord</span></span>

<span data-ttu-id="73d30-539">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-539">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="73d30-540">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-540">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="73d30-541">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-541">Function is unbound.</span></span>

### <a name="vibackwardchar"></a><span data-ttu-id="73d30-542">ViBackwardChar</span><span class="sxs-lookup"><span data-stu-id="73d30-542">ViBackwardChar</span></span>

<span data-ttu-id="73d30-543">Vi 編集モードでカーソルを1文字左に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-543">Move the cursor one character to the left in the Vi edit mode.</span></span> <span data-ttu-id="73d30-544">これにより、カーソルが複数行の入力の前の行に移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="73d30-544">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="73d30-545">Vi の挿入モード: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-545">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="73d30-546">Vi コマンドモード: `<LeftArrow>` 、 `<Backspace>` 、 `<h>`</span><span class="sxs-lookup"><span data-stu-id="73d30-546">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="73d30-547">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="73d30-547">ViBackwardWord</span></span>

<span data-ttu-id="73d30-548">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-548">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="73d30-549">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-549">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="73d30-550">Vi コマンドモード: `<b>`</span><span class="sxs-lookup"><span data-stu-id="73d30-550">Vi command mode: `<b>`</span></span>

### <a name="viforwardchar"></a><span data-ttu-id="73d30-551">ViForwardChar</span><span class="sxs-lookup"><span data-stu-id="73d30-551">ViForwardChar</span></span>

<span data-ttu-id="73d30-552">Vi 編集モードでカーソルを1文字右に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-552">Move the cursor one character to the right in the Vi edit mode.</span></span> <span data-ttu-id="73d30-553">これにより、カーソルが複数行入力の次の行に移動する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73d30-553">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="73d30-554">Vi の挿入モード: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-554">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="73d30-555">Vi コマンドモード: `<RightArrow>` 、 `<Spacebar>` 、 `<l>`</span><span class="sxs-lookup"><span data-stu-id="73d30-555">Vi command mode: `<RightArrow>`, `<Spacebar>`, `<l>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="73d30-556">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="73d30-556">ViEndOfGlob</span></span>

<span data-ttu-id="73d30-557">区切り記号として空白文字のみを使用して、カーソルを単語の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-557">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="73d30-558">Vi コマンドモード: `<E>`</span><span class="sxs-lookup"><span data-stu-id="73d30-558">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="73d30-559">Viendofの Glob</span><span class="sxs-lookup"><span data-stu-id="73d30-559">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="73d30-560">単語区切り記号として空白文字のみを使用して、前の単語の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-560">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="73d30-561">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-561">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="73d30-562">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="73d30-562">ViGotoBrace</span></span>

<span data-ttu-id="73d30-563">GotoBrace に似ていますが、トークンベースではなく文字ベースです。</span><span class="sxs-lookup"><span data-stu-id="73d30-563">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="73d30-564">Vi コマンドモード: `<%>`</span><span class="sxs-lookup"><span data-stu-id="73d30-564">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="73d30-565">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="73d30-565">ViNextGlob</span></span>

<span data-ttu-id="73d30-566">単語区切り記号として空白文字のみを使用して、次の単語に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-566">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="73d30-567">Vi コマンドモード: `<W>`</span><span class="sxs-lookup"><span data-stu-id="73d30-567">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="73d30-568">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="73d30-568">ViNextWord</span></span>

<span data-ttu-id="73d30-569">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-569">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="73d30-570">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-570">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="73d30-571">Vi コマンドモード: `<w>`</span><span class="sxs-lookup"><span data-stu-id="73d30-571">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="73d30-572">履歴関数</span><span class="sxs-lookup"><span data-stu-id="73d30-572">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="73d30-573">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="73d30-573">BeginningOfHistory</span></span>

<span data-ttu-id="73d30-574">履歴内の最初の項目に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-574">Move to the first item in the history.</span></span>

- <span data-ttu-id="73d30-575">.Emacs `<Alt+<>`</span><span class="sxs-lookup"><span data-stu-id="73d30-575">Emacs: `<Alt+<>`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="73d30-576">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="73d30-576">ClearHistory</span></span>

<span data-ttu-id="73d30-577">PSReadLine の履歴をクリアします。</span><span class="sxs-lookup"><span data-stu-id="73d30-577">Clears history in PSReadLine.</span></span> <span data-ttu-id="73d30-578">これは、PowerShell の履歴には影響しません。</span><span class="sxs-lookup"><span data-stu-id="73d30-578">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="73d30-579">コマンド: `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="73d30-579">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="73d30-580">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="73d30-580">EndOfHistory</span></span>

<span data-ttu-id="73d30-581">履歴内の最後の項目 (現在の入力) に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-581">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="73d30-582">.Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="73d30-582">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="73d30-583">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="73d30-583">ForwardSearchHistory</span></span>

<span data-ttu-id="73d30-584">履歴を使用した増分転送検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="73d30-584">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="73d30-585">コマンド: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="73d30-585">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="73d30-586">.Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="73d30-586">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="73d30-587">履歴の Search後方</span><span class="sxs-lookup"><span data-stu-id="73d30-587">HistorySearchBackward</span></span>

<span data-ttu-id="73d30-588">現在の入力を、PSReadLine 履歴の ' previous ' 項目で置き換えます。この項目は、開始と入力の間の文字とカーソルの間の文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="73d30-588">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="73d30-589">コマンド: `<F8>`</span><span class="sxs-lookup"><span data-stu-id="73d30-589">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="73d30-590">履歴の Searchforward</span><span class="sxs-lookup"><span data-stu-id="73d30-590">HistorySearchForward</span></span>

<span data-ttu-id="73d30-591">現在の入力を、PSReadLine 履歴の ' next ' 項目で置き換えます。この項目は、開始と入力の間の文字とカーソルの間の文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="73d30-591">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="73d30-592">コマンド: `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="73d30-592">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="73d30-593">NextHistory</span><span class="sxs-lookup"><span data-stu-id="73d30-593">NextHistory</span></span>

<span data-ttu-id="73d30-594">現在の入力を、PSReadLine 履歴の ' next ' 項目に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="73d30-594">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="73d30-595">コマンド: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-595">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="73d30-596">Emacs: `<DownArrow>` 、 `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="73d30-596">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="73d30-597">Vi の挿入モード: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-597">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="73d30-598">Vi コマンドモード: `<DownArrow>` 、 `<j>` 、 `<+>`</span><span class="sxs-lookup"><span data-stu-id="73d30-598">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="73d30-599">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="73d30-599">PreviousHistory</span></span>

<span data-ttu-id="73d30-600">現在の入力を、PSReadLine 履歴の ' previous ' 項目に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="73d30-600">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="73d30-601">コマンド: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-601">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="73d30-602">Emacs: `<UpArrow>` 、 `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="73d30-602">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="73d30-603">Vi の挿入モード: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-603">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="73d30-604">Vi コマンドモード: `<UpArrow>` 、 `<k>` 、 `<->`</span><span class="sxs-lookup"><span data-stu-id="73d30-604">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="73d30-605">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="73d30-605">ReverseSearchHistory</span></span>

<span data-ttu-id="73d30-606">履歴を介して後方検索を段階的に実行します。</span><span class="sxs-lookup"><span data-stu-id="73d30-606">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="73d30-607">コマンド: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="73d30-607">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="73d30-608">.Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="73d30-608">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="73d30-609">Visearchhistory 後方</span><span class="sxs-lookup"><span data-stu-id="73d30-609">ViSearchHistoryBackward</span></span>

<span data-ttu-id="73d30-610">検索文字列を入力し、AcceptLine で検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="73d30-610">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="73d30-611">Vi の挿入モード: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="73d30-611">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="73d30-612">Vi コマンドモード: `</>` 、 `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="73d30-612">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="73d30-613">入力候補関数</span><span class="sxs-lookup"><span data-stu-id="73d30-613">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="73d30-614">完了</span><span class="sxs-lookup"><span data-stu-id="73d30-614">Complete</span></span>

<span data-ttu-id="73d30-615">カーソルを囲むテキストに対して入力候補を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="73d30-615">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="73d30-616">候補が複数ある場合は、最長の明確なプレフィックスを使用して完了します。</span><span class="sxs-lookup"><span data-stu-id="73d30-616">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="73d30-617">最長の明確な完了を完了しようとすると、候補の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-617">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="73d30-618">.Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="73d30-618">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="73d30-619">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="73d30-619">MenuComplete</span></span>

<span data-ttu-id="73d30-620">カーソルを囲むテキストに対して入力候補を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="73d30-620">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="73d30-621">候補が複数ある場合は、最長の明確なプレフィックスを使用して完了します。</span><span class="sxs-lookup"><span data-stu-id="73d30-621">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="73d30-622">最長の明確な完了を完了しようとすると、候補の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-622">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="73d30-623">Cmd: `<Ctrl+@>` 、 `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="73d30-623">Cmd: `<Ctrl+@>`, `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="73d30-624">.Emacs `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="73d30-624">Emacs: `<Ctrl+Spacebar>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="73d30-625">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="73d30-625">PossibleCompletions</span></span>

<span data-ttu-id="73d30-626">候補の候補の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="73d30-626">Display the list of possible completions.</span></span>

- <span data-ttu-id="73d30-627">.Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="73d30-627">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="73d30-628">Vi の挿入モード: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="73d30-628">Vi insert mode: `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="73d30-629">Vi コマンドモード: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="73d30-629">Vi command mode: `<Ctrl+Spacebar>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="73d30-630">タブのすべてのタブ</span><span class="sxs-lookup"><span data-stu-id="73d30-630">TabCompleteNext</span></span>

<span data-ttu-id="73d30-631">次に使用可能な完了時に、カーソルを囲むテキストを完了します。</span><span class="sxs-lookup"><span data-stu-id="73d30-631">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="73d30-632">コマンド: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="73d30-632">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="73d30-633">Vi コマンドモード: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="73d30-633">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="73d30-634">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="73d30-634">TabCompletePrevious</span></span>

<span data-ttu-id="73d30-635">以前に使用可能な入力候補を使用して、カーソルを囲むテキストを完了しようとしました。</span><span class="sxs-lookup"><span data-stu-id="73d30-635">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="73d30-636">コマンド: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="73d30-636">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="73d30-637">Vi コマンドモード: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="73d30-637">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="73d30-638">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="73d30-638">ViTabCompleteNext</span></span>

<span data-ttu-id="73d30-639">必要に応じて現在の編集グループを終了し、Tabends を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="73d30-639">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="73d30-640">Vi の挿入モード: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="73d30-640">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="73d30-641">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="73d30-641">ViTabCompletePrevious</span></span>

<span data-ttu-id="73d30-642">必要に応じて現在の編集グループを終了し、TabCompletePrevious を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="73d30-642">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="73d30-643">Vi の挿入モード: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="73d30-643">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="prediction-functions"></a><span data-ttu-id="73d30-644">予測関数</span><span class="sxs-lookup"><span data-stu-id="73d30-644">Prediction functions</span></span>

### <a name="acceptnextsuggestionword"></a><span data-ttu-id="73d30-645">AcceptNextSuggestionWord</span><span class="sxs-lookup"><span data-stu-id="73d30-645">AcceptNextSuggestionWord</span></span>

<span data-ttu-id="73d30-646">予測のビュースタイルとしてを使用する場合は `InlineView` 、インライン修正候補の次の単語を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="73d30-646">When using `InlineView` as the view style for prediction, accept the next word of the inline suggestion.</span></span>

- <span data-ttu-id="73d30-647">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-647">Function is unbound.</span></span>

### <a name="acceptsuggestion"></a><span data-ttu-id="73d30-648">AcceptSuggestion</span><span class="sxs-lookup"><span data-stu-id="73d30-648">AcceptSuggestion</span></span>

<span data-ttu-id="73d30-649">予測のビュースタイルとしてを使用する場合は `InlineView` 、現在のインライン提案を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="73d30-649">When using `InlineView` as the view style for prediction, accept the current inline suggestion.</span></span>

- <span data-ttu-id="73d30-650">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-650">Function is unbound.</span></span>

### <a name="nextsuggestion"></a><span data-ttu-id="73d30-651">NextSuggestion</span><span class="sxs-lookup"><span data-stu-id="73d30-651">NextSuggestion</span></span>

<span data-ttu-id="73d30-652">予測のビュースタイルとしてを使用する場合は、 `ListView` 一覧の次の提案に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-652">When using `ListView` as the view style for prediction, navigate to the next suggestion in the list.</span></span>

- <span data-ttu-id="73d30-653">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-653">Function is unbound.</span></span>

### <a name="previoussuggestion"></a><span data-ttu-id="73d30-654">前の提案</span><span class="sxs-lookup"><span data-stu-id="73d30-654">PreviousSuggestion</span></span>

<span data-ttu-id="73d30-655">予測のビュースタイルとしてを使用する場合は、 `ListView` 一覧の前の候補に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-655">When using `ListView` as the view style for prediction, navigate to the previous suggestion in the list.</span></span>

- <span data-ttu-id="73d30-656">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-656">Function is unbound.</span></span>

### <a name="switchpredictionview"></a><span data-ttu-id="73d30-657">SwitchPredictionView</span><span class="sxs-lookup"><span data-stu-id="73d30-657">SwitchPredictionView</span></span>

<span data-ttu-id="73d30-658">との間の予測のビュースタイルを切り替え `InlineView` `ListView` ます。</span><span class="sxs-lookup"><span data-stu-id="73d30-658">Switch the view style for prediction between `InlineView` and `ListView`.</span></span>

- <span data-ttu-id="73d30-659">コマンド: `<F2>`</span><span class="sxs-lookup"><span data-stu-id="73d30-659">Cmd: `<F2>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="73d30-660">その他の関数</span><span class="sxs-lookup"><span data-stu-id="73d30-660">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="73d30-661">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="73d30-661">CaptureScreen</span></span>

<span data-ttu-id="73d30-662">対話型画面のキャプチャを開始する/下矢印行を選択し、[選択したテキストをテキストと html としてクリップボードにコピーする] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="73d30-662">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="73d30-663">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-663">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="73d30-664">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="73d30-664">ClearScreen</span></span>

<span data-ttu-id="73d30-665">画面をクリアし、画面の上部にある現在の線を描画します。</span><span class="sxs-lookup"><span data-stu-id="73d30-665">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="73d30-666">コマンド: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="73d30-666">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="73d30-667">.Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="73d30-667">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="73d30-668">Vi の挿入モード: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="73d30-668">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="73d30-669">Vi コマンドモード: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="73d30-669">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="73d30-670">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="73d30-670">DigitArgument</span></span>

<span data-ttu-id="73d30-671">他の関数に渡す新しい桁引数を開始します。</span><span class="sxs-lookup"><span data-stu-id="73d30-671">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="73d30-672">Cmd:、、、、、、、、、 `<Alt+0>` `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="73d30-672">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="73d30-673">Emacs:、、、、、、、、、 `<Alt+0>` `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="73d30-673">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="73d30-674">Vi コマンドモード:、、、、、、、、 `<0>` `<1>` `<2>` `<3>` `<4>` `<5>` `<6>` `<7>` `<8>` 、 `<9>`</span><span class="sxs-lookup"><span data-stu-id="73d30-674">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="73d30-675">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="73d30-675">InvokePrompt</span></span>

<span data-ttu-id="73d30-676">現在のプロンプトを消去し、prompt 関数を呼び出してプロンプトを再表示します。</span><span class="sxs-lookup"><span data-stu-id="73d30-676">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="73d30-677">現在のディレクトリを変更するなど、状態を変更するカスタムキーハンドラーに便利です。</span><span class="sxs-lookup"><span data-stu-id="73d30-677">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="73d30-678">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-678">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="73d30-679">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="73d30-679">ScrollDisplayDown</span></span>

<span data-ttu-id="73d30-680">画面を1画面下へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="73d30-680">Scroll the display down one screen.</span></span>

- <span data-ttu-id="73d30-681">コマンド: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="73d30-681">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="73d30-682">.Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="73d30-682">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="73d30-683">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="73d30-683">ScrollDisplayDownLine</span></span>

<span data-ttu-id="73d30-684">表示を1行下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="73d30-684">Scroll the display down one line.</span></span>

- <span data-ttu-id="73d30-685">コマンド: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="73d30-685">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="73d30-686">.Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="73d30-686">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="73d30-687">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="73d30-687">ScrollDisplayToCursor</span></span>

<span data-ttu-id="73d30-688">カーソルまで画面をスクロールします。</span><span class="sxs-lookup"><span data-stu-id="73d30-688">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="73d30-689">.Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="73d30-689">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="73d30-690">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="73d30-690">ScrollDisplayTop</span></span>

<span data-ttu-id="73d30-691">画面を上にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="73d30-691">Scroll the display to the top.</span></span>

- <span data-ttu-id="73d30-692">.Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="73d30-692">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="73d30-693">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="73d30-693">ScrollDisplayUp</span></span>

<span data-ttu-id="73d30-694">画面を1画面上へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="73d30-694">Scroll the display up one screen.</span></span>

- <span data-ttu-id="73d30-695">コマンド: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="73d30-695">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="73d30-696">.Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="73d30-696">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="73d30-697">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="73d30-697">ScrollDisplayUpLine</span></span>

<span data-ttu-id="73d30-698">表示を1行上へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="73d30-698">Scroll the display up one line.</span></span>

- <span data-ttu-id="73d30-699">コマンド: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="73d30-699">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="73d30-700">.Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="73d30-700">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="73d30-701">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="73d30-701">SelfInsert</span></span>

<span data-ttu-id="73d30-702">キーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="73d30-702">Insert the key.</span></span>

- <span data-ttu-id="73d30-703">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-703">Function is unbound.</span></span>

### <a name="showcommandhelp"></a><span data-ttu-id="73d30-704">ShowCommandHelp</span><span class="sxs-lookup"><span data-stu-id="73d30-704">ShowCommandHelp</span></span>

<span data-ttu-id="73d30-705">**Microsoft PowerShell** のポケットベルを使用して、代替画面バッファーの完全なコマンドレットヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="73d30-705">Provides a view of full cmdlet help on alternate screen buffer using a Pager from **Microsoft.PowerShell.Pager**.</span></span>

- <span data-ttu-id="73d30-706">コマンド: `<F1>`</span><span class="sxs-lookup"><span data-stu-id="73d30-706">Cmd: `<F1>`</span></span>
- <span data-ttu-id="73d30-707">.Emacs `<F1>`</span><span class="sxs-lookup"><span data-stu-id="73d30-707">Emacs: `<F1>`</span></span>
- <span data-ttu-id="73d30-708">Vi の挿入モード: `<F1>`</span><span class="sxs-lookup"><span data-stu-id="73d30-708">Vi insert mode: `<F1>`</span></span>
- <span data-ttu-id="73d30-709">Vi コマンドモード: `<F1>`</span><span class="sxs-lookup"><span data-stu-id="73d30-709">Vi command mode: `<F1>`</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="73d30-710">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="73d30-710">ShowKeyBindings</span></span>

<span data-ttu-id="73d30-711">すべてのバインドされたキーを表示します。</span><span class="sxs-lookup"><span data-stu-id="73d30-711">Show all bound keys.</span></span>

- <span data-ttu-id="73d30-712">コマンド: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="73d30-712">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="73d30-713">.Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="73d30-713">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="73d30-714">Vi の挿入モード: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="73d30-714">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="showparameterhelp"></a><span data-ttu-id="73d30-715">ShowParameterHelp</span><span class="sxs-lookup"><span data-stu-id="73d30-715">ShowParameterHelp</span></span>

<span data-ttu-id="73d30-716">のような現在のコマンドラインの下に表示することにより、パラメーターの動的なヘルプを提供 `MenuComplete` します。</span><span class="sxs-lookup"><span data-stu-id="73d30-716">Provides dynamic help for parameters by showing it below the current command line like `MenuComplete`.</span></span>

- <span data-ttu-id="73d30-717">コマンド: `<Alt+h>`</span><span class="sxs-lookup"><span data-stu-id="73d30-717">Cmd: `<Alt+h>`</span></span>
- <span data-ttu-id="73d30-718">.Emacs `<Alt+h>`</span><span class="sxs-lookup"><span data-stu-id="73d30-718">Emacs: `<Alt+h>`</span></span>
- <span data-ttu-id="73d30-719">Vi の挿入モード: `<Alt+h>`</span><span class="sxs-lookup"><span data-stu-id="73d30-719">Vi insert mode: `<Alt+h>`</span></span>
- <span data-ttu-id="73d30-720">Vi コマンドモード: `<Alt+h>`</span><span class="sxs-lookup"><span data-stu-id="73d30-720">Vi command mode: `<Alt+h>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="73d30-721">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="73d30-721">ViCommandMode</span></span>

<span data-ttu-id="73d30-722">現在の動作モードを Vi-Insert から Vi-Command に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="73d30-722">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="73d30-723">Vi の挿入モード: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="73d30-723">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="73d30-724">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="73d30-724">ViDigitArgumentInChord</span></span>

<span data-ttu-id="73d30-725">Vi のいずれかの弦で、他の関数に渡す新しい桁引数を開始します。</span><span class="sxs-lookup"><span data-stu-id="73d30-725">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="73d30-726">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-726">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="73d30-727">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="73d30-727">ViEditVisually</span></span>

<span data-ttu-id="73d30-728">$Env: EDITOR または $env: ビジュアルによって指定されたテキストエディターでコマンドラインを編集します。</span><span class="sxs-lookup"><span data-stu-id="73d30-728">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="73d30-729">.Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="73d30-729">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="73d30-730">Vi コマンドモード: `<v>`</span><span class="sxs-lookup"><span data-stu-id="73d30-730">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="73d30-731">ViExit</span><span class="sxs-lookup"><span data-stu-id="73d30-731">ViExit</span></span>

<span data-ttu-id="73d30-732">シェルを終了します。</span><span class="sxs-lookup"><span data-stu-id="73d30-732">Exits the shell.</span></span>

- <span data-ttu-id="73d30-733">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-733">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="73d30-734">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="73d30-734">ViInsertMode</span></span>

<span data-ttu-id="73d30-735">挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="73d30-735">Switch to Insert mode.</span></span>

- <span data-ttu-id="73d30-736">Vi コマンドモード: `<i>`</span><span class="sxs-lookup"><span data-stu-id="73d30-736">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="73d30-737">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="73d30-737">WhatIsKey</span></span>

<span data-ttu-id="73d30-738">キーを読み取り、キーがどのようにバインドされているかを通知します。</span><span class="sxs-lookup"><span data-stu-id="73d30-738">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="73d30-739">コマンド: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="73d30-739">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="73d30-740">.Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="73d30-740">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="73d30-741">選択関数</span><span class="sxs-lookup"><span data-stu-id="73d30-741">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="73d30-742">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="73d30-742">ExchangePointAndMark</span></span>

<span data-ttu-id="73d30-743">カーソルがマークの位置に置かれ、マークがカーソルの位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-743">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="73d30-744">.Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="73d30-744">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="73d30-745">SelectAll</span><span class="sxs-lookup"><span data-stu-id="73d30-745">SelectAll</span></span>

<span data-ttu-id="73d30-746">行全体を選択します。</span><span class="sxs-lookup"><span data-stu-id="73d30-746">Select the entire line.</span></span>

- <span data-ttu-id="73d30-747">コマンド: `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="73d30-747">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="73d30-748">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="73d30-748">SelectBackwardChar</span></span>

<span data-ttu-id="73d30-749">現在の選択範囲を調整して、前の文字を含めます。</span><span class="sxs-lookup"><span data-stu-id="73d30-749">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="73d30-750">コマンド: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-750">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="73d30-751">.Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-751">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="73d30-752">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="73d30-752">SelectBackwardsLine</span></span>

<span data-ttu-id="73d30-753">カーソルから行の先頭まで、現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="73d30-753">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="73d30-754">コマンド: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="73d30-754">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="73d30-755">.Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="73d30-755">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="73d30-756">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="73d30-756">SelectBackwardWord</span></span>

<span data-ttu-id="73d30-757">現在の選択範囲を調整して、前の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="73d30-757">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="73d30-758">コマンド: `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-758">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="73d30-759">.Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="73d30-759">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="73d30-760">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="73d30-760">SelectForwardChar</span></span>

<span data-ttu-id="73d30-761">現在の選択範囲を調整して、次の文字を含めます。</span><span class="sxs-lookup"><span data-stu-id="73d30-761">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="73d30-762">コマンド: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-762">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="73d30-763">.Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-763">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="73d30-764">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="73d30-764">SelectForwardWord</span></span>

<span data-ttu-id="73d30-765">現在の選択範囲を調整して、ForwardWord を使用して次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="73d30-765">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="73d30-766">.Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="73d30-766">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="73d30-767">SelectLine</span><span class="sxs-lookup"><span data-stu-id="73d30-767">SelectLine</span></span>

<span data-ttu-id="73d30-768">カーソルから行の末尾まで、現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="73d30-768">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="73d30-769">コマンド: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="73d30-769">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="73d30-770">.Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="73d30-770">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="73d30-771">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="73d30-771">SelectNextWord</span></span>

<span data-ttu-id="73d30-772">現在の選択範囲を調整して、次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="73d30-772">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="73d30-773">コマンド: `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="73d30-773">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="73d30-774">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="73d30-774">SelectShellBackwardWord</span></span>

<span data-ttu-id="73d30-775">ShellBackwardWord を使用して、前の単語が含まれるように現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="73d30-775">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="73d30-776">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-776">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="73d30-777">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="73d30-777">SelectShellForwardWord</span></span>

<span data-ttu-id="73d30-778">現在の選択範囲を調整して、ShellForwardWord を使用する次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="73d30-778">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="73d30-779">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-779">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="73d30-780">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="73d30-780">SelectShellNextWord</span></span>

<span data-ttu-id="73d30-781">現在の選択範囲を調整して、ShellNextWord を使用して次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="73d30-781">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="73d30-782">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="73d30-782">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="73d30-783">SetMark</span><span class="sxs-lookup"><span data-stu-id="73d30-783">SetMark</span></span>

<span data-ttu-id="73d30-784">後続の編集コマンドで使用するために、カーソルの現在の位置をマークします。</span><span class="sxs-lookup"><span data-stu-id="73d30-784">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="73d30-785">.Emacs `<Ctrl+@>`</span><span class="sxs-lookup"><span data-stu-id="73d30-785">Emacs: `<Ctrl+@>`</span></span>

## <a name="predictive-intellisense-functions"></a><span data-ttu-id="73d30-786">予測 IntelliSense 関数</span><span class="sxs-lookup"><span data-stu-id="73d30-786">Predictive IntelliSense functions</span></span>

> [!NOTE]
> <span data-ttu-id="73d30-787">これらの関数を使用するには、予測 IntelliSense を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="73d30-787">Predictive IntelliSense needs to be enabled to use these functions.</span></span>

### <a name="acceptnextwordsuggestion"></a><span data-ttu-id="73d30-788">AcceptNextWordSuggestion</span><span class="sxs-lookup"><span data-stu-id="73d30-788">AcceptNextWordSuggestion</span></span>

<span data-ttu-id="73d30-789">予測 IntelliSense からインライン提案の次の単語を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="73d30-789">Accepts the next word of the inline suggestion from Predictive IntelliSense.</span></span>
<span data-ttu-id="73d30-790">次のコマンドを実行して、この関数を<kbd>Ctrl</kbd> + <kbd>F</kbd>でバインドできます。</span><span class="sxs-lookup"><span data-stu-id="73d30-790">This function can be bound with <kbd>Ctrl</kbd>+<kbd>F</kbd> by running the following command.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord "Ctrl+f" -Function ForwardWord
```

### <a name="acceptsuggestion"></a><span data-ttu-id="73d30-791">AcceptSuggestion</span><span class="sxs-lookup"><span data-stu-id="73d30-791">AcceptSuggestion</span></span>

<span data-ttu-id="73d30-792">カーソルが現在の行の末尾にある場合に <kbd>→</kbd> を押すことで、予測 IntelliSense からの現在のインライン提案を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="73d30-792">Accepts the current inline suggestion from Predictive IntelliSense by pressing <kbd>RightArrow</kbd> when the cursor is at the end of the current line.</span></span>

## <a name="search-functions"></a><span data-ttu-id="73d30-793">関数の検索</span><span class="sxs-lookup"><span data-stu-id="73d30-793">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="73d30-794">文字検索</span><span class="sxs-lookup"><span data-stu-id="73d30-794">CharacterSearch</span></span>

<span data-ttu-id="73d30-795">文字を読み取り、その文字が次に出現するまで検索します。</span><span class="sxs-lookup"><span data-stu-id="73d30-795">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="73d30-796">引数が指定されている場合は、n 番目のオカレンスに対して前方 (負の場合は後方) を検索します。</span><span class="sxs-lookup"><span data-stu-id="73d30-796">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="73d30-797">コマンド: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="73d30-797">Cmd: `<F3>`</span></span>
- <span data-ttu-id="73d30-798">.Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="73d30-798">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="73d30-799">Vi の挿入モード: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="73d30-799">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="73d30-800">Vi コマンドモード: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="73d30-800">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="73d30-801">文字 Search後方</span><span class="sxs-lookup"><span data-stu-id="73d30-801">CharacterSearchBackward</span></span>

<span data-ttu-id="73d30-802">文字を読み取り、その文字が次に出現するまで検索します。</span><span class="sxs-lookup"><span data-stu-id="73d30-802">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="73d30-803">引数が指定されている場合は、n 番目のオカレンスに対して後方 (または負の場合は forward) を検索します。</span><span class="sxs-lookup"><span data-stu-id="73d30-803">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="73d30-804">コマンド: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="73d30-804">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="73d30-805">.Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="73d30-805">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="73d30-806">Vi の挿入モード: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="73d30-806">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="73d30-807">Vi コマンドモード: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="73d30-807">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="73d30-808">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="73d30-808">RepeatLastCharSearch</span></span>

<span data-ttu-id="73d30-809">最後に記録された文字の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="73d30-809">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="73d30-810">Vi コマンドモード: `<;>`</span><span class="sxs-lookup"><span data-stu-id="73d30-810">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="73d30-811">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="73d30-811">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="73d30-812">最後に記録された文字検索を逆方向に繰り返します。</span><span class="sxs-lookup"><span data-stu-id="73d30-812">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="73d30-813">Vi コマンドモード: `<,>`</span><span class="sxs-lookup"><span data-stu-id="73d30-813">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="73d30-814">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="73d30-814">RepeatSearch</span></span>

<span data-ttu-id="73d30-815">前と同じ方向に最後の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="73d30-815">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="73d30-816">Vi コマンドモード: `<n>`</span><span class="sxs-lookup"><span data-stu-id="73d30-816">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="73d30-817">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="73d30-817">RepeatSearchBackward</span></span>

<span data-ttu-id="73d30-818">前と同じ方向に最後の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="73d30-818">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="73d30-819">Vi コマンドモード: `<N>`</span><span class="sxs-lookup"><span data-stu-id="73d30-819">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="73d30-820">SearchChar</span><span class="sxs-lookup"><span data-stu-id="73d30-820">SearchChar</span></span>

<span data-ttu-id="73d30-821">次の文字を読み取って検索し、次に文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="73d30-821">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="73d30-822">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="73d30-822">This is for 't' functionality.</span></span>

- <span data-ttu-id="73d30-823">Vi コマンドモード: `<f>`</span><span class="sxs-lookup"><span data-stu-id="73d30-823">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="73d30-824">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="73d30-824">SearchCharBackward</span></span>

<span data-ttu-id="73d30-825">次の文字を読み取り、それを検索して後方に移動し、次に文字を戻します。</span><span class="sxs-lookup"><span data-stu-id="73d30-825">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="73d30-826">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="73d30-826">This is for 'T' functionality.</span></span>

- <span data-ttu-id="73d30-827">Vi コマンドモード: `<F>`</span><span class="sxs-lookup"><span data-stu-id="73d30-827">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="73d30-828">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="73d30-828">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="73d30-829">次の文字を読み取り、それを検索して後方に移動し、次に文字を戻します。</span><span class="sxs-lookup"><span data-stu-id="73d30-829">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="73d30-830">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="73d30-830">This is for 'T' functionality.</span></span>

- <span data-ttu-id="73d30-831">Vi コマンドモード: `<T>`</span><span class="sxs-lookup"><span data-stu-id="73d30-831">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="73d30-832">SearchCharWithBackoff オフ</span><span class="sxs-lookup"><span data-stu-id="73d30-832">SearchCharWithBackoff</span></span>

<span data-ttu-id="73d30-833">次の文字を読み取って検索し、次に文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="73d30-833">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="73d30-834">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="73d30-834">This is for 't' functionality.</span></span>

- <span data-ttu-id="73d30-835">Vi コマンドモード: `<t>`</span><span class="sxs-lookup"><span data-stu-id="73d30-835">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="73d30-836">SearchForward</span><span class="sxs-lookup"><span data-stu-id="73d30-836">SearchForward</span></span>

<span data-ttu-id="73d30-837">検索文字列を入力し、AcceptLine で検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="73d30-837">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="73d30-838">Vi の挿入モード: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="73d30-838">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="73d30-839">Vi コマンドモード: `<?>` 、 `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="73d30-839">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="73d30-840">カスタムキーバインド</span><span class="sxs-lookup"><span data-stu-id="73d30-840">Custom Key Bindings</span></span>

<span data-ttu-id="73d30-841">PSReadLine は、コマンドレットを使用してカスタムキーバインドをサポートしてい `Set-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="73d30-841">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="73d30-842">ほとんどのカスタムキーバインドは、たとえば、上記の関数の1つを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="73d30-842">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="73d30-843">ScriptBlock をキーにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="73d30-843">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="73d30-844">ScriptBlock は、ほとんどすべてのことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="73d30-844">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="73d30-845">いくつかの便利な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="73d30-845">Some useful examples include</span></span>

- <span data-ttu-id="73d30-846">コマンドラインを編集する</span><span class="sxs-lookup"><span data-stu-id="73d30-846">edit the command line</span></span>
- <span data-ttu-id="73d30-847">新しいウィンドウを開く (例: ヘルプ)</span><span class="sxs-lookup"><span data-stu-id="73d30-847">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="73d30-848">コマンドラインを変更せずにディレクトリを変更する</span><span class="sxs-lookup"><span data-stu-id="73d30-848">change directories without changing the command line</span></span>

<span data-ttu-id="73d30-849">ScriptBlock は、次の2つの引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="73d30-849">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="73d30-850">`$key` -カスタムバインドをトリガーしたキーである **[Consolekeyinfo]** オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="73d30-850">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="73d30-851">同じ ScriptBlock を複数のキーにバインドし、キーに応じて異なるアクションを実行する必要がある場合は、$key を確認します。</span><span class="sxs-lookup"><span data-stu-id="73d30-851">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="73d30-852">多くのカスタムバインドでは、この引数は無視します。</span><span class="sxs-lookup"><span data-stu-id="73d30-852">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="73d30-853">`$arg` -任意の引数。</span><span class="sxs-lookup"><span data-stu-id="73d30-853">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="73d30-854">多くの場合、これは、ユーザーがキーバインド DigitArgument から渡す整数引数になります。</span><span class="sxs-lookup"><span data-stu-id="73d30-854">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="73d30-855">バインディングが引数を受け入れない場合は、この引数を無視するのが妥当です。</span><span class="sxs-lookup"><span data-stu-id="73d30-855">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="73d30-856">ここでは、コマンドラインを実行せずに履歴に追加する例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="73d30-856">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="73d30-857">これは、何らかの操作を忘れた場合に、既に入力したコマンドラインを再入力したくない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="73d30-857">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="73d30-858">PSReadLine モジュールフォルダーにインストールされているファイルには、さらに多くの例が表示 `SamplePSReadLineProfile.ps1` されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-858">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="73d30-859">ほとんどのキーバインドでは、コマンドラインを編集するためにいくつかのヘルパー関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="73d30-859">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="73d30-860">これらの Api については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="73d30-860">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="73d30-861">カスタムキーバインディングサポート Api</span><span class="sxs-lookup"><span data-stu-id="73d30-861">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="73d30-862">次の関数は PSConsoleReadLine では公開されていますが、キーに直接バインドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="73d30-862">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="73d30-863">多くの場合、カスタムキーバインドに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="73d30-863">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="73d30-864">コマンドラインを実行せずに、履歴に追加します。</span><span class="sxs-lookup"><span data-stu-id="73d30-864">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="73d30-865">Kill リングをクリアします。</span><span class="sxs-lookup"><span data-stu-id="73d30-865">Clear the kill-ring.</span></span>  <span data-ttu-id="73d30-866">これは主にテストに使用されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-866">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="73d30-867">先頭から長さの文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="73d30-867">Delete length characters from start.</span></span>  <span data-ttu-id="73d30-868">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="73d30-868">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="73d30-869">ユーザー設定に基づいてアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="73d30-869">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="73d30-870">これらの2つの関数は、入力バッファーの現在の状態に関する有用な情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="73d30-870">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="73d30-871">1つ目は、単純なケースでよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-871">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="73d30-872">2つ目は、バインディングが Ast を使用してより高度な処理を実行している場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-872">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(string[] Chord)
```

<span data-ttu-id="73d30-873">この2つの関数は、によって使用され `Get-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="73d30-873">These two functions are used by `Get-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="73d30-874">最初のは、すべてのキーバインドを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-874">The first is used to get all key bindings.</span></span> <span data-ttu-id="73d30-875">2番目のは、特定のキーバインドを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-875">The second is used to get specific key bindings.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="73d30-876">この関数は Get-PSReadLineOption によって使用され、カスタムキーバインドではあまり役に立たない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73d30-876">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="73d30-877">コマンドラインに何も選択されていない場合は、開始と長さの両方で-1 が返されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-877">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="73d30-878">コマンドラインに選択項目がある場合は、選択範囲の先頭と長さが返されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-878">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="73d30-879">カーソル位置に文字または文字列を挿入します。</span><span class="sxs-lookup"><span data-stu-id="73d30-879">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="73d30-880">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="73d30-880">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="73d30-881">これは、PSReadLine へのメインエントリポイントです。</span><span class="sxs-lookup"><span data-stu-id="73d30-881">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="73d30-882">再帰はサポートされないため、カスタムキーバインドでは役に立ちません。</span><span class="sxs-lookup"><span data-stu-id="73d30-882">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="73d30-883">この関数は Remove-PSReadLineKeyHandler によって使用され、カスタムキーバインドではあまり役に立たない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73d30-883">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="73d30-884">入力の一部を置換します。</span><span class="sxs-lookup"><span data-stu-id="73d30-884">Replace some of the input.</span></span> <span data-ttu-id="73d30-885">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="73d30-885">This operation supports undo/redo.</span></span> <span data-ttu-id="73d30-886">これは、undo の単一のアクションとして扱われるため、Delete の後に Insert を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="73d30-886">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="73d30-887">カーソルを指定されたオフセットに移動します。</span><span class="sxs-lookup"><span data-stu-id="73d30-887">Move the cursor to the given offset.</span></span> <span data-ttu-id="73d30-888">カーソルの移動は、元に戻すために追跡されません。</span><span class="sxs-lookup"><span data-stu-id="73d30-888">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="73d30-889">この関数は、コマンドレットの設定-PSReadLineOption によって使用されるヘルパーメソッドですが、一時的に設定を変更する必要があるカスタムキーバインドに便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="73d30-889">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="73d30-890">このヘルパーメソッドは、DigitArgument を優先するカスタムバインドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-890">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="73d30-891">一般的な呼び出しは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="73d30-891">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="notes"></a><span data-ttu-id="73d30-892">ノート</span><span class="sxs-lookup"><span data-stu-id="73d30-892">Notes</span></span>

### <a name="command-history"></a><span data-ttu-id="73d30-893">コマンド履歴</span><span class="sxs-lookup"><span data-stu-id="73d30-893">Command History</span></span>

<span data-ttu-id="73d30-894">PSReadLine は、コマンドラインから入力したすべてのコマンドとデータを含む履歴ファイルを保持します。</span><span class="sxs-lookup"><span data-stu-id="73d30-894">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="73d30-895">これには、パスワードなどの機密データが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="73d30-895">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="73d30-896">たとえば、コマンドレットを使用した場合、 `ConvertTo-SecureString` パスワードはプレーンテキストとして履歴ファイルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="73d30-896">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="73d30-897">履歴ファイルは、という名前のファイルです `$($host.Name)_history.txt` 。</span><span class="sxs-lookup"><span data-stu-id="73d30-897">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="73d30-898">Windows システムでは、履歴ファイルはに格納され `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` ます。</span><span class="sxs-lookup"><span data-stu-id="73d30-898">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="73d30-899">Windows 以外のシステムでは、履歴ファイルはまたはに格納され `$env:XDG_DATA_HOME/powershell/PSReadLine` `$env:HOME/.local/share/powershell/PSReadLine` ます。</span><span class="sxs-lookup"><span data-stu-id="73d30-899">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="73d30-900">PSReadLine に貢献しているフィードバック &</span><span class="sxs-lookup"><span data-stu-id="73d30-900">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="73d30-901">GitHub の PSReadLine</span><span class="sxs-lookup"><span data-stu-id="73d30-901">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="73d30-902">プル要求を送信したり、GitHub ページでフィードバックを送信したりしてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="73d30-902">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="73d30-903">参照</span><span class="sxs-lookup"><span data-stu-id="73d30-903">See Also</span></span>

<span data-ttu-id="73d30-904">PSReadLine は、GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) ライブラリの影響を強く受けます。</span><span class="sxs-lookup"><span data-stu-id="73d30-904">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
