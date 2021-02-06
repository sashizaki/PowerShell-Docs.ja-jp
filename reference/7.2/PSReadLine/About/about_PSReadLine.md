---
description: PSReadLine では、PowerShell コンソールでのコマンドライン編集エクスペリエンスが向上しています。
Locale: en-US
ms.date: 11/23/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: PSReadLine について
ms.openlocfilehash: 4836abfec465ba7cdfb6800c1e60104fba19ce08
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "99600977"
---
# <a name="psreadline"></a><span data-ttu-id="0ce7d-103">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-103">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="0ce7d-104">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-104">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="0ce7d-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="0ce7d-105">Short Description</span></span>

<span data-ttu-id="0ce7d-106">PSReadLine では、PowerShell コンソールでのコマンドライン編集エクスペリエンスが向上しています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-106">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="0ce7d-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="0ce7d-107">Long Description</span></span>

<span data-ttu-id="0ce7d-108">PSReadLine 2.2 では、PowerShell コンソールの強力なコマンドライン編集エクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-108">PSReadLine 2.2 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="0ce7d-109">次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-109">It provides:</span></span>

- <span data-ttu-id="0ce7d-110">コマンドラインの構文の色分け</span><span class="sxs-lookup"><span data-stu-id="0ce7d-110">Syntax coloring of the command line</span></span>
- <span data-ttu-id="0ce7d-111">構文エラーを視覚的に示します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-111">A visual indication of syntax errors</span></span>
- <span data-ttu-id="0ce7d-112">より優れたマルチラインエクスペリエンス (編集と履歴の両方)</span><span class="sxs-lookup"><span data-stu-id="0ce7d-112">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="0ce7d-113">カスタマイズ可能なキーバインド</span><span class="sxs-lookup"><span data-stu-id="0ce7d-113">Customizable key bindings</span></span>
- <span data-ttu-id="0ce7d-114">Cmd モードと Emacs モード</span><span class="sxs-lookup"><span data-stu-id="0ce7d-114">Cmd and Emacs modes</span></span>
- <span data-ttu-id="0ce7d-115">多くの構成オプション</span><span class="sxs-lookup"><span data-stu-id="0ce7d-115">Many configuration options</span></span>
- <span data-ttu-id="0ce7d-116">Bash スタイル補完 (Cmd モードでは省略可能、Emacs モードでは既定)</span><span class="sxs-lookup"><span data-stu-id="0ce7d-116">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="0ce7d-117">Emacs yank/kill-リング</span><span class="sxs-lookup"><span data-stu-id="0ce7d-117">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="0ce7d-118">PowerShell トークンベースの "word" の移動と強制終了</span><span class="sxs-lookup"><span data-stu-id="0ce7d-118">PowerShell token based "word" movement and kill</span></span>
- <span data-ttu-id="0ce7d-119">予測 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="0ce7d-119">Predictive IntelliSense</span></span>

<span data-ttu-id="0ce7d-120">PSReadLine 2.2.0 には、次の2つの新しい予測 IntelliSense 機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-120">PSReadLine 2.2.0 added two new predictive IntelliSense features:</span></span>

- <span data-ttu-id="0ce7d-121">**PredictionViewStyle** パラメーターを追加して、新しいを選択できるようにしました `ListView` 。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-121">Added the **PredictionViewStyle** parameter to allow for the selection of the new `ListView`.</span></span>
- <span data-ttu-id="0ce7d-122">PSReadLine を PS 7.1 で導入された api に接続して、 `CommandPrediction` ユーザーがカスタムソースから提案を表示できる予測モジュールをインポートできるようにしました。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-122">Connected PSReadLine to the `CommandPrediction` APIs introduced in PS 7.1 to allow a user can import a predictor module that can render the suggestions from a custom source.</span></span>

<span data-ttu-id="0ce7d-123">PSReadLine には PowerShell 3.0 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-123">PSReadLine requires PowerShell 3.0, or newer.</span></span> <span data-ttu-id="0ce7d-124">PSReadLine は、既定のコンソールホスト、Visual Studio Code、ウィンドウターミナルで動作します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-124">PSReadLine works with default console host, Visual Studio Code, and Window Terminal.</span></span> <span data-ttu-id="0ce7d-125">PowerShell ISE では機能しません。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-125">It does not work in PowerShell ISE.</span></span>

<span data-ttu-id="0ce7d-126">PSReadLine 2.2.0 は PowerShell 7.2 に付属しており、サポートされているすべてのバージョンの PowerShell でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-126">PSReadLine 2.2.0 ships with PowerShell 7.2 and is supported in all supported versions of PowerShell.</span></span> <span data-ttu-id="0ce7d-127">PowerShell ギャラリーからインストールできます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-127">It is available to install from the PowerShell Gallery.</span></span>
<span data-ttu-id="0ce7d-128">サポートされているバージョンの PowerShell に PSReadLine 2.2.0 をインストールするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-128">To install PSReadLine 2.2.0 in a supported version of PowerShell run the following command.</span></span>

```powershell
Install-Module -Name PSReadLine -AllowPrerelease
```

> [!NOTE]
> <span data-ttu-id="0ce7d-129">PowerShell 7.0 以降では、スクリーンリーダープログラムが検出されると、PowerShell は Windows で PSReadLine の自動読み込みをスキップします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-129">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="0ce7d-130">現在、PSReadLine は、スクリーンリーダーではうまく機能しません。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-130">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="0ce7d-131">Windows での PowerShell 7.0 の既定の表示と書式設定は正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-131">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="0ce7d-132">必要に応じて、モジュールを手動で読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-132">You can manually load the module if necessary.</span></span>

## <a name="predictive-intellisense"></a><span data-ttu-id="0ce7d-133">予測 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="0ce7d-133">Predictive IntelliSense</span></span>

<span data-ttu-id="0ce7d-134">予測 IntelliSense は、ユーザーがコマンドを正常に完了できるように、タブ補完の概念を追加したものです。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-134">Predictive IntelliSense is an addition to the concept of tab completion that assists the user in successfully completing commands.</span></span> <span data-ttu-id="0ce7d-135">ユーザーは、ユーザーの履歴や追加のドメイン固有のプラグインからの照合予測に基づいて、完全なコマンドを検出、編集、および実行することができます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-135">It enables users to discover, edit, and execute full commands based on matching predictions from the user's history and additional domain specific plugins.</span></span>

### <a name="enable-predictive-intellisense"></a><span data-ttu-id="0ce7d-136">予測 IntelliSense を有効にする</span><span class="sxs-lookup"><span data-stu-id="0ce7d-136">Enable Predictive IntelliSense</span></span>

<span data-ttu-id="0ce7d-137">既定では、予測 IntelliSense は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-137">Predictive IntelliSense is disabled by default.</span></span> <span data-ttu-id="0ce7d-138">予測を有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-138">To enable predictions, just run the following command:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource History
```

<span data-ttu-id="0ce7d-139">**PredictionSource** パラメーターでは、ドメイン固有の要件とカスタムの要件に対してプラグインを受け入れることもできます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-139">The **PredictionSource** parameter can also accept plugins for domain specific and custom requirements.</span></span>

<span data-ttu-id="0ce7d-140">予測 IntelliSense を無効にするには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-140">To disable Predictive IntelliSense, just run:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource None
```

<span data-ttu-id="0ce7d-141">クラス **[PSConsoleReadLine]** では、次の関数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-141">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="0ce7d-142">基本的な編集関数</span><span class="sxs-lookup"><span data-stu-id="0ce7d-142">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="0ce7d-143">中止</span><span class="sxs-lookup"><span data-stu-id="0ce7d-143">Abort</span></span>

<span data-ttu-id="0ce7d-144">現在のアクション (増分履歴検索など) を中止します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-144">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="0ce7d-145">.Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-145">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="0ce7d-146">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="0ce7d-146">AcceptAndGetNext</span></span>

<span data-ttu-id="0ce7d-147">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-147">Attempt to execute the current input.</span></span> <span data-ttu-id="0ce7d-148">(AcceptLine など) 実行できる場合は、次に ReadLine が呼び出されたときに履歴から次の項目を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-148">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="0ce7d-149">.Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-149">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="0ce7d-150">AcceptLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-150">AcceptLine</span></span>

<span data-ttu-id="0ce7d-151">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-151">Attempt to execute the current input.</span></span> <span data-ttu-id="0ce7d-152">現在の入力が不完全な場合 (たとえば、終わりかっこ、角かっこ、または引用符がない場合)、継続のプロンプトは次の行に表示され、PSReadLine は現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-152">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="0ce7d-153">コマンド: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-153">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="0ce7d-154">.Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-154">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="0ce7d-155">Vi の挿入モード: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-155">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="0ce7d-156">AddLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-156">AddLine</span></span>

<span data-ttu-id="0ce7d-157">継続プロンプトが次の行に表示され、PSReadLine が現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-157">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="0ce7d-158">これは、単一行が単独で完全に入力されている場合でも、複数行の入力を1つのコマンドとして入力する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-158">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="0ce7d-159">コマンド: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-159">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="0ce7d-160">.Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-160">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="0ce7d-161">Vi の挿入モード: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-161">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="0ce7d-162">Vi コマンドモード: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-162">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="0ce7d-163">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="0ce7d-163">BackwardDeleteChar</span></span>

<span data-ttu-id="0ce7d-164">カーソルの前の文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-164">Delete the character before the cursor.</span></span>

- <span data-ttu-id="0ce7d-165">Cmd: `<Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-165">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="0ce7d-166">Emacs: `<Backspace>` 、 `<Ctrl+Backspace>` 、 `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-166">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="0ce7d-167">Vi の挿入モード: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-167">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="0ce7d-168">Vi コマンドモード: `<X>` 、 `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-168">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="0ce7d-169">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-169">BackwardDeleteLine</span></span>

<span data-ttu-id="0ce7d-170">Like BackwardKillLine-行の先頭から先頭までのテキストを削除しますが、削除されたテキストはキルリングには挿入されません。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-170">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="0ce7d-171">コマンド: `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-171">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="0ce7d-172">Vi 挿入モード: `<Ctrl+u>` 、 `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-172">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="0ce7d-173">Vi コマンドモード: `<Ctrl+u>` 、 `<Ctrl+Home>` 、 `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-173">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="0ce7d-174">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-174">BackwardDeleteWord</span></span>

<span data-ttu-id="0ce7d-175">前の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-175">Deletes the previous word.</span></span>

- <span data-ttu-id="0ce7d-176">Vi コマンドモード: `<Ctrl+w>` 、 `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-176">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="0ce7d-177">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-177">BackwardKillLine</span></span>

<span data-ttu-id="0ce7d-178">入力の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-178">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="0ce7d-179">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-179">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="0ce7d-180">Emacs: `<Ctrl+u>` 、 `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-180">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="0ce7d-181">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-181">BackwardKillWord</span></span>

<span data-ttu-id="0ce7d-182">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-182">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="0ce7d-183">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-183">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="0ce7d-184">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-184">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="0ce7d-185">Cmd: `<Ctrl+Backspace>` 、 `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-185">Cmd: `<Ctrl+Backspace>`, `<Ctrl+w>`</span></span>
- <span data-ttu-id="0ce7d-186">Emacs: `<Alt+Backspace>` 、 `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-186">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="0ce7d-187">Vi の挿入モード: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-187">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="0ce7d-188">Vi コマンドモード: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-188">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="0ce7d-189">CancelLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-189">CancelLine</span></span>

<span data-ttu-id="0ce7d-190">入力を画面に残したまま、現在の入力を取り消しますが、プロンプトが再び評価されるように、ホストに戻ります。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-190">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="0ce7d-191">Vi の挿入モード: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-191">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="0ce7d-192">Vi コマンドモード: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-192">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="0ce7d-193">コピー</span><span class="sxs-lookup"><span data-stu-id="0ce7d-193">Copy</span></span>

<span data-ttu-id="0ce7d-194">選択したリージョンをシステムクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-194">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="0ce7d-195">領域が選択されていない場合は、行全体をコピーします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-195">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="0ce7d-196">コマンド: `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-196">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="0ce7d-197">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-197">CopyOrCancelLine</span></span>

<span data-ttu-id="0ce7d-198">テキストが選択されている場合は、クリップボードにコピーします。それ以外の場合は、行をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-198">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="0ce7d-199">コマンド: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-199">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="0ce7d-200">.Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-200">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="0ce7d-201">［切り取り］</span><span class="sxs-lookup"><span data-stu-id="0ce7d-201">Cut</span></span>

<span data-ttu-id="0ce7d-202">削除されたテキストをシステムクリップボードに配置した、選択した領域を削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-202">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="0ce7d-203">コマンド: `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-203">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="0ce7d-204">Dele</span><span class="sxs-lookup"><span data-stu-id="0ce7d-204">DeleteChar</span></span>

<span data-ttu-id="0ce7d-205">カーソルの下の文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-205">Delete the character under the cursor.</span></span>

- <span data-ttu-id="0ce7d-206">コマンド: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-206">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="0ce7d-207">.Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-207">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="0ce7d-208">Vi の挿入モード: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-208">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="0ce7d-209">Vi コマンドモード: `<Delete>` 、 `<x>` 、 `<d,l>` 、 `<d,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-209">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Spacebar>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="0ce7d-210">Deleの Arorexit</span><span class="sxs-lookup"><span data-stu-id="0ce7d-210">DeleteCharOrExit</span></span>

<span data-ttu-id="0ce7d-211">カーソルの下の文字を削除するか、行が空の場合はプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-211">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="0ce7d-212">.Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-212">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofbuffer"></a><span data-ttu-id="0ce7d-213">DeleteEndOfBuffer</span><span class="sxs-lookup"><span data-stu-id="0ce7d-213">DeleteEndOfBuffer</span></span>

<span data-ttu-id="0ce7d-214">複数行バッファーの末尾までを削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-214">Deletes to the end of the multiline buffer.</span></span>

- <span data-ttu-id="0ce7d-215">Vi コマンドモード: `<d,G>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-215">Vi command mode: `<d,G>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="0ce7d-216">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-216">DeleteEndOfWord</span></span>

<span data-ttu-id="0ce7d-217">単語の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-217">Delete to the end of the word.</span></span>

- <span data-ttu-id="0ce7d-218">Vi コマンドモード: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-218">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="0ce7d-219">Deleteline.invoke に</span><span class="sxs-lookup"><span data-stu-id="0ce7d-219">DeleteLine</span></span>

<span data-ttu-id="0ce7d-220">複数行バッファーの現在の論理行を削除して、元に戻すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-220">Deletes the current logical line of a multiline buffer, enabling undo.</span></span>

- <span data-ttu-id="0ce7d-221">Vi コマンドモード: `<d,d>` 、 `<d,_>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-221">Vi command mode: `<d,d>`, `<d,_>`</span></span>

### <a name="deletepreviouslines"></a><span data-ttu-id="0ce7d-222">削除した行</span><span class="sxs-lookup"><span data-stu-id="0ce7d-222">DeletePreviousLines</span></span>

<span data-ttu-id="0ce7d-223">複数行バッファーの前に要求された論理行と現在の論理行を削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-223">Deletes the previous requested logical lines and the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="0ce7d-224">Vi コマンドモード: `<d,k>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-224">Vi command mode: `<d,k>`</span></span>

### <a name="deleterelativelines"></a><span data-ttu-id="0ce7d-225">DeleteRelativeLines</span><span class="sxs-lookup"><span data-stu-id="0ce7d-225">DeleteRelativeLines</span></span>

<span data-ttu-id="0ce7d-226">バッファーの先頭から複数行バッファーの現在の論理行に削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-226">Deletes from the beginning of the buffer to the current logical line in a multiline buffer.</span></span>

<span data-ttu-id="0ce7d-227">ほとんどの Vi コマンドと同様に、コマンドには、 `<d,g,g>` 絶対行番号を指定する数値引数 (現在の行番号と共に、削除する行の範囲を構成する) を付加することができます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-227">As most Vi commands, the `<d,g,g>` command can be prepended with a numeric argument that specifies an absolute line number, which, together with the current line number, make up a range of lines to be deleted.</span></span>
<span data-ttu-id="0ce7d-228">指定しない場合、数値引数の既定値は1です。これは、複数行バッファーの最初の論理行を参照します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-228">If not specified, the numeric argument defaults to 1, which refers to the first logical line in a multiline buffer.</span></span>

<span data-ttu-id="0ce7d-229">複数行から削除される実際の行数は、現在の論理行番号と指定された数値引数の差として計算されます。したがって、負の数になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-229">The actual number of lines to be deleted from the multiline is computed as the difference between the current logical line number and the specified numeric argument, which can thus be negative.</span></span> <span data-ttu-id="0ce7d-230">そのため、メソッド名の _相対_ 部分です。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-230">Hence the _relative_ part of method name.</span></span>

- <span data-ttu-id="0ce7d-231">Vi コマンドモード: `<d,g,g>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-231">Vi command mode: `<d,g,g>`</span></span>

### <a name="deletenextlines"></a><span data-ttu-id="0ce7d-232">Deleの配信行</span><span class="sxs-lookup"><span data-stu-id="0ce7d-232">DeleteNextLines</span></span>

<span data-ttu-id="0ce7d-233">複数行バッファーで現在の論理行と次に要求された論理行を削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-233">Deletes the current logical line and the next requested logical lines in a multiline buffer.</span></span>

- <span data-ttu-id="0ce7d-234">Vi コマンドモード: `<d,j>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-234">Vi command mode: `<d,j>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="0ce7d-235">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="0ce7d-235">DeleteLineToFirstChar</span></span>

<span data-ttu-id="0ce7d-236">複数行バッファーの現在の論理行の最初の空白以外の文字からを削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-236">Deletes from the first non-blank character of the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="0ce7d-237">Vi コマンドモード: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-237">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="0ce7d-238">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="0ce7d-238">DeleteToEnd</span></span>

<span data-ttu-id="0ce7d-239">行の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-239">Delete to the end of the line.</span></span>

- <span data-ttu-id="0ce7d-240">Vi コマンドモード: `<D>` 、 `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-240">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="0ce7d-241">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-241">DeleteWord</span></span>

<span data-ttu-id="0ce7d-242">次の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-242">Delete the next word.</span></span>

- <span data-ttu-id="0ce7d-243">Vi コマンドモード: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-243">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="0ce7d-244">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-244">ForwardDeleteLine</span></span>

<span data-ttu-id="0ce7d-245">同じように、Forwardは、行の末尾から最後までのテキストを削除しますが、削除されたテキストはキルリングには挿入されません。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-245">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="0ce7d-246">コマンド: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-246">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="0ce7d-247">Vi の挿入モード: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-247">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="0ce7d-248">Vi コマンドモード: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-248">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="0ce7d-249">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="0ce7d-249">InsertLineAbove</span></span>

<span data-ttu-id="0ce7d-250">現在の行の上にカーソルがある場所に関係なく、現在の行の上に新しい空の行が作成されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-250">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="0ce7d-251">カーソルが新しい行の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-251">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="0ce7d-252">コマンド: `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-252">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="0ce7d-253">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="0ce7d-253">InsertLineBelow</span></span>

<span data-ttu-id="0ce7d-254">カーソルが現在の行にある場所に関係なく、現在の行の下に新しい空の行が作成されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-254">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="0ce7d-255">カーソルが新しい行の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-255">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="0ce7d-256">コマンド: `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-256">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="0ce7d-257">InvertCase</span><span class="sxs-lookup"><span data-stu-id="0ce7d-257">InvertCase</span></span>

<span data-ttu-id="0ce7d-258">現在の文字の大文字と小文字の区別を反転し、次の文字に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-258">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="0ce7d-259">Vi コマンドモード: `<~>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-259">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="0ce7d-260">行の行</span><span class="sxs-lookup"><span data-stu-id="0ce7d-260">KillLine</span></span>

<span data-ttu-id="0ce7d-261">カーソルから入力の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-261">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="0ce7d-262">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-262">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="0ce7d-263">.Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-263">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="0ce7d-264">"/" 領域</span><span class="sxs-lookup"><span data-stu-id="0ce7d-264">KillRegion</span></span>

<span data-ttu-id="0ce7d-265">カーソルとマークの間のテキストを強制終了します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-265">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="0ce7d-266">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-266">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="0ce7d-267">文字の候補</span><span class="sxs-lookup"><span data-stu-id="0ce7d-267">KillWord</span></span>

<span data-ttu-id="0ce7d-268">カーソルから現在の単語の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-268">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="0ce7d-269">カーソルが単語の間にある場合は、カーソルから次の単語の末尾まで、入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-269">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="0ce7d-270">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-270">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="0ce7d-271">Cmd: `<Alt+d>` 、 `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-271">Cmd: `<Alt+d>`, `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="0ce7d-272">Emacs: `<Alt+d>` 、 `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-272">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="0ce7d-273">Vi の挿入モード: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-273">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="0ce7d-274">Vi コマンドモード: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-274">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="0ce7d-275">貼り付け</span><span class="sxs-lookup"><span data-stu-id="0ce7d-275">Paste</span></span>

<span data-ttu-id="0ce7d-276">システムクリップボードからテキストを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-276">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="0ce7d-277">Cmd: `<Ctrl+v>` 、 `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-277">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="0ce7d-278">Vi の挿入モード: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-278">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="0ce7d-279">Vi コマンドモード: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-279">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ce7d-280">**貼り付け** 関数を使用すると、クリップボードバッファーの内容全体が psreadline の入力バッファーに貼り付けられます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-280">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="0ce7d-281">入力バッファーが PowerShell パーサーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-281">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="0ce7d-282">コンソールアプリケーションの **右クリック** による貼り付けメソッドを使用して貼り付けた入力は、一度に1文字ずつ入力バッファーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-282">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="0ce7d-283">入力バッファーは、改行文字がコピーされるときにパーサーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-283">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="0ce7d-284">そのため、入力は一度に1行ずつ解析されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-284">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="0ce7d-285">貼り付けメソッドの違いによって、実行の動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-285">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="0ce7d-286">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="0ce7d-286">PasteAfter</span></span>

<span data-ttu-id="0ce7d-287">カーソルの後にクリップボードを貼り付けて、貼り付けられたテキストの末尾にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-287">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="0ce7d-288">Vi コマンドモード: `<p>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-288">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="0ce7d-289">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="0ce7d-289">PasteBefore</span></span>

<span data-ttu-id="0ce7d-290">カーソルの前にクリップボードを貼り付けて、貼り付けられたテキストの末尾にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-290">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="0ce7d-291">Vi コマンドモード: `<P>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-291">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="0ce7d-292">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="0ce7d-292">PrependAndAccept</span></span>

<span data-ttu-id="0ce7d-293">' # ' を先頭に付加し、その行を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-293">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="0ce7d-294">Vi コマンドモード: `<#>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-294">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="0ce7d-295">やり直す</span><span class="sxs-lookup"><span data-stu-id="0ce7d-295">Redo</span></span>

<span data-ttu-id="0ce7d-296">元に戻す操作を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-296">Undo an undo.</span></span>

- <span data-ttu-id="0ce7d-297">コマンド: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-297">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="0ce7d-298">Vi の挿入モード: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-298">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="0ce7d-299">Vi コマンドモード: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-299">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="0ce7d-300">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="0ce7d-300">RepeatLastCommand</span></span>

<span data-ttu-id="0ce7d-301">最後のテキストの変更を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-301">Repeat the last text modification.</span></span>

- <span data-ttu-id="0ce7d-302">Vi コマンドモード: `<.>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-302">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="0ce7d-303">再有効化</span><span class="sxs-lookup"><span data-stu-id="0ce7d-303">RevertLine</span></span>

<span data-ttu-id="0ce7d-304">すべての入力を現在の入力に戻します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-304">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="0ce7d-305">コマンド: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-305">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="0ce7d-306">Emacs: `<Alt+r>` 、 `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-306">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="0ce7d-307">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-307">ShellBackwardKillWord</span></span>

<span data-ttu-id="0ce7d-308">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-308">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="0ce7d-309">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-309">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="0ce7d-310">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-310">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="0ce7d-311">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-311">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="0ce7d-312">Shellは Word</span><span class="sxs-lookup"><span data-stu-id="0ce7d-312">ShellKillWord</span></span>

<span data-ttu-id="0ce7d-313">カーソルから現在の単語の末尾までの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-313">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="0ce7d-314">カーソルが単語の間にある場合は、カーソルから次の単語の末尾まで、入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-314">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="0ce7d-315">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-315">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="0ce7d-316">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-316">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="0ce7d-317">スワップ文字</span><span class="sxs-lookup"><span data-stu-id="0ce7d-317">SwapCharacters</span></span>

<span data-ttu-id="0ce7d-318">現在の文字とそれより前の文字を交換します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-318">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="0ce7d-319">.Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-319">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="0ce7d-320">Vi の挿入モード: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-320">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="0ce7d-321">Vi コマンドモード: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-321">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="0ce7d-322">元に戻す</span><span class="sxs-lookup"><span data-stu-id="0ce7d-322">Undo</span></span>

<span data-ttu-id="0ce7d-323">前の編集を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-323">Undo a previous edit.</span></span>

- <span data-ttu-id="0ce7d-324">コマンド: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-324">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="0ce7d-325">Emacs: `<Ctrl+_>` 、 `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-325">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="0ce7d-326">Vi の挿入モード: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-326">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="0ce7d-327">Vi コマンドモード: `<Ctrl+z>` 、 `<u>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-327">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="0ce7d-328">UndoAll</span><span class="sxs-lookup"><span data-stu-id="0ce7d-328">UndoAll</span></span>

<span data-ttu-id="0ce7d-329">行の以前の編集をすべて元に戻します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-329">Undo all previous edits for line.</span></span>

- <span data-ttu-id="0ce7d-330">Vi コマンドモード: `<U>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-330">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="0ce7d-331">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="0ce7d-331">UnixWordRubout</span></span>

<span data-ttu-id="0ce7d-332">現在の単語の先頭からカーソルまでの入力をクリアします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-332">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="0ce7d-333">カーソルが単語の間にある場合は、前の単語の先頭からカーソルまでの入力がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-333">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="0ce7d-334">クリアテキストはキルリングに配置されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-334">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="0ce7d-335">.Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-335">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="0ce7d-336">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-336">ValidateAndAcceptLine</span></span>

<span data-ttu-id="0ce7d-337">現在の入力を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-337">Attempt to execute the current input.</span></span> <span data-ttu-id="0ce7d-338">現在の入力が不完全な場合 (たとえば、終わりかっこ、角かっこ、または引用符がない場合)、継続のプロンプトは次の行に表示され、PSReadLine は現在の入力を編集するためのキーを待機します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-338">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="0ce7d-339">.Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-339">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="0ce7d-340">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-340">ViAcceptLine</span></span>

<span data-ttu-id="0ce7d-341">行を受け入れ、挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-341">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="0ce7d-342">Vi コマンドモード: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-342">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="0ce7d-343">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="0ce7d-343">ViAcceptLineOrExit</span></span>

<span data-ttu-id="0ce7d-344">(Emacs モードでは Deleと同じですが、文字を削除するのではなく、行を受け取ります)。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-344">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="0ce7d-345">Vi の挿入モード: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-345">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="0ce7d-346">Vi コマンドモード: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-346">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="0ce7d-347">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-347">ViAppendLine</span></span>

<span data-ttu-id="0ce7d-348">現在の行の下に新しい行が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-348">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="0ce7d-349">Vi コマンドモード: `<o>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-349">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="0ce7d-350">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="0ce7d-350">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="0ce7d-351">単語区切り記号として空白文字のみを使用して、前の単語を削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-351">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="0ce7d-352">Vi コマンドモード: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-352">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="0ce7d-353">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="0ce7d-353">ViBackwardGlob</span></span>

<span data-ttu-id="0ce7d-354">区切り記号として空白文字のみを使用して、カーソルを前の単語の先頭に戻します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-354">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="0ce7d-355">Vi コマンドモード: `<B>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-355">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="0ce7d-356">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="0ce7d-356">ViDeleteBrace</span></span>

<span data-ttu-id="0ce7d-357">対応する中かっこ、かっこ、または角かっこを検索し、中かっこを含め、内のすべての内容を削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-357">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="0ce7d-358">Vi コマンドモード: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-358">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="0ce7d-359">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="0ce7d-359">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="0ce7d-360">単語の末尾まで削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-360">Delete to the end of the word.</span></span>

- <span data-ttu-id="0ce7d-361">Vi コマンドモード: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-361">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="0ce7d-362">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="0ce7d-362">ViDeleteGlob</span></span>

<span data-ttu-id="0ce7d-363">次の glob (空白で区切られた単語) を削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-363">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="0ce7d-364">Vi コマンドモード: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-364">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="0ce7d-365">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="0ce7d-365">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="0ce7d-366">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-366">Deletes until given character.</span></span>

- <span data-ttu-id="0ce7d-367">Vi コマンドモード: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-367">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="0ce7d-368">Videletetobeforo</span><span class="sxs-lookup"><span data-stu-id="0ce7d-368">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="0ce7d-369">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-369">Deletes until given character.</span></span>

- <span data-ttu-id="0ce7d-370">Vi コマンドモード: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-370">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="0ce7d-371">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="0ce7d-371">ViDeleteToChar</span></span>

<span data-ttu-id="0ce7d-372">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-372">Deletes until given character.</span></span>

- <span data-ttu-id="0ce7d-373">Vi コマンドモード: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-373">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="0ce7d-374">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="0ce7d-374">ViDeleteToCharBackward</span></span>

<span data-ttu-id="0ce7d-375">指定された文字まで後方を削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-375">Deletes backwards until given character.</span></span>

- <span data-ttu-id="0ce7d-376">Vi コマンドモード: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-376">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="0ce7d-377">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="0ce7d-377">ViInsertAtBegining</span></span>

<span data-ttu-id="0ce7d-378">挿入モードに切り替え、カーソルを行の先頭に配置します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-378">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="0ce7d-379">Vi コマンドモード: `<I>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-379">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="0ce7d-380">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="0ce7d-380">ViInsertAtEnd</span></span>

<span data-ttu-id="0ce7d-381">挿入モードに切り替え、カーソルを行の末尾に配置します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-381">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="0ce7d-382">Vi コマンドモード: `<A>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-382">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="0ce7d-383">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-383">ViInsertLine</span></span>

<span data-ttu-id="0ce7d-384">現在の行の上に新しい行が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-384">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="0ce7d-385">Vi コマンドモード: `<O>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-385">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="0ce7d-386">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="0ce7d-386">ViInsertWithAppend</span></span>

<span data-ttu-id="0ce7d-387">現在の行の位置から追加します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-387">Append from the current line position.</span></span>

- <span data-ttu-id="0ce7d-388">Vi コマンドモード: `<a>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-388">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="0ce7d-389">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="0ce7d-389">ViInsertWithDelete</span></span>

<span data-ttu-id="0ce7d-390">現在の文字を削除し、挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-390">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="0ce7d-391">Vi コマンドモード: `<s>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-391">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="0ce7d-392">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="0ce7d-392">ViJoinLines</span></span>

<span data-ttu-id="0ce7d-393">現在の行と次の行を結合します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-393">Joins the current line and the next line.</span></span>

- <span data-ttu-id="0ce7d-394">Vi コマンドモード: `<J>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-394">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="0ce7d-395">交換ライン</span><span class="sxs-lookup"><span data-stu-id="0ce7d-395">ViReplaceLine</span></span>

<span data-ttu-id="0ce7d-396">コマンドライン全体を消去します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-396">Erase the entire command line.</span></span>

- <span data-ttu-id="0ce7d-397">Vi コマンドモード: `<S>` 、 `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-397">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="0ce7d-398">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="0ce7d-398">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="0ce7d-399">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-399">Replaces until given character.</span></span>

- <span data-ttu-id="0ce7d-400">Vi コマンドモード: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-400">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="0ce7d-401">Vireplacetobeforo</span><span class="sxs-lookup"><span data-stu-id="0ce7d-401">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="0ce7d-402">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-402">Replaces until given character.</span></span>

- <span data-ttu-id="0ce7d-403">Vi コマンドモード: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-403">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="0ce7d-404">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="0ce7d-404">ViReplaceToChar</span></span>

<span data-ttu-id="0ce7d-405">指定された文字まで削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-405">Deletes until given character.</span></span>

- <span data-ttu-id="0ce7d-406">Vi コマンドモード: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-406">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="0ce7d-407">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="0ce7d-407">ViReplaceToCharBackward</span></span>

<span data-ttu-id="0ce7d-408">指定された文字になるまで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-408">Replaces until given character.</span></span>

- <span data-ttu-id="0ce7d-409">Vi コマンドモード: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-409">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="0ce7d-410">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-410">ViYankBeginningOfLine</span></span>

<span data-ttu-id="0ce7d-411">バッファーの先頭からカーソルまで Yank。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-411">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="0ce7d-412">Vi コマンドモード: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-412">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="0ce7d-413">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="0ce7d-413">ViYankEndOfGlob</span></span>

<span data-ttu-id="0ce7d-414">カーソルから単語の末尾まで Yank します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-414">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="0ce7d-415">Vi コマンドモード: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-415">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="0ce7d-416">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-416">ViYankEndOfWord</span></span>

<span data-ttu-id="0ce7d-417">カーソルから単語の末尾まで Yank します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-417">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="0ce7d-418">Vi コマンドモード: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-418">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="0ce7d-419">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="0ce7d-419">ViYankLeft</span></span>

<span data-ttu-id="0ce7d-420">カーソルの左側の文字を Yank します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-420">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="0ce7d-421">Vi コマンドモード: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-421">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="0ce7d-422">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-422">ViYankLine</span></span>

<span data-ttu-id="0ce7d-423">バッファー全体を Yank します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-423">Yank the entire buffer.</span></span>

- <span data-ttu-id="0ce7d-424">Vi コマンドモード: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-424">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="0ce7d-425">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="0ce7d-425">ViYankNextGlob</span></span>

<span data-ttu-id="0ce7d-426">Yank は、次の単語の先頭にカーソルを置きます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-426">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="0ce7d-427">Vi コマンドモード: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-427">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="0ce7d-428">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-428">ViYankNextWord</span></span>

<span data-ttu-id="0ce7d-429">カーソルの後の単語を Yank します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-429">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="0ce7d-430">Vi コマンドモード: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-430">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="0ce7d-431">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="0ce7d-431">ViYankPercent</span></span>

<span data-ttu-id="0ce7d-432">一致する中かっこを Yank します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-432">Yank to/from matching brace.</span></span>

- <span data-ttu-id="0ce7d-433">Vi コマンドモード: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-433">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="0ce7d-434">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="0ce7d-434">ViYankPreviousGlob</span></span>

<span data-ttu-id="0ce7d-435">Yank は、単語の先頭からカーソルになります。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-435">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="0ce7d-436">Vi コマンドモード: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-436">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="0ce7d-437">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-437">ViYankPreviousWord</span></span>

<span data-ttu-id="0ce7d-438">カーソルの前に単語を Yank します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-438">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="0ce7d-439">Vi コマンドモード: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-439">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="0ce7d-440">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="0ce7d-440">ViYankRight</span></span>

<span data-ttu-id="0ce7d-441">カーソルの右側に Yank 文字があります。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-441">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="0ce7d-442">Vi コマンドモード: `<y,l>` 、 `<y,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-442">Vi command mode: `<y,l>`, `<y,Spacebar>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="0ce7d-443">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-443">ViYankToEndOfLine</span></span>

<span data-ttu-id="0ce7d-444">カーソルからバッファーの末尾までの Yank。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-444">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="0ce7d-445">Vi コマンドモード: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-445">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="0ce7d-446">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="0ce7d-446">ViYankToFirstChar</span></span>

<span data-ttu-id="0ce7d-447">最初の空白以外の文字からカーソルまで Yank ます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-447">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="0ce7d-448">Vi コマンドモード: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-448">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="0ce7d-449">Yank</span><span class="sxs-lookup"><span data-stu-id="0ce7d-449">Yank</span></span>

<span data-ttu-id="0ce7d-450">最後に終了したテキストを入力に追加します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-450">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="0ce7d-451">.Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-451">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="0ce7d-452">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="0ce7d-452">YankLastArg</span></span>

<span data-ttu-id="0ce7d-453">前の履歴行の最後の引数を Yank します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-453">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="0ce7d-454">引数を使用すると、最初に呼び出されたときに、YankNthArg と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-454">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="0ce7d-455">複数回呼び出された場合は、代わりに履歴を反復処理し、引数に方向を設定します (負の方向が反転します)。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-455">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="0ce7d-456">コマンド: `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-456">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="0ce7d-457">Emacs: `<Alt+.>` 、 `<Alt+_>` 、 `<Escape,.>` 、 `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-457">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="0ce7d-458">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="0ce7d-458">YankNthArg</span></span>

<span data-ttu-id="0ce7d-459">Yank は、前の履歴行から (コマンドの後に) 最初の引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-459">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="0ce7d-460">引数を使用して、n 番目の引数 (0 から始まる) を yank します。引数が負の場合は、最後の引数から開始します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-460">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="0ce7d-461">Emacs: `<Ctrl+Alt+y>` 、 `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-461">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="0ce7d-462">YankPop</span><span class="sxs-lookup"><span data-stu-id="0ce7d-462">YankPop</span></span>

<span data-ttu-id="0ce7d-463">前の操作が Yank または YankPop であった場合は、以前の引き抜かテキストをキルリングから次に強制終了されたテキストに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-463">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="0ce7d-464">Emacs: `<Alt+y>` 、 `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-464">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="0ce7d-465">カーソルの移動関数</span><span class="sxs-lookup"><span data-stu-id="0ce7d-465">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="0ce7d-466">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="0ce7d-466">BackwardChar</span></span>

<span data-ttu-id="0ce7d-467">カーソルを1文字左に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-467">Move the cursor one character to the left.</span></span> <span data-ttu-id="0ce7d-468">これにより、カーソルが複数行の入力の前の行に移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-468">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="0ce7d-469">コマンド: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-469">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="0ce7d-470">Emacs: `<LeftArrow>` 、 `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-470">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="0ce7d-471">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-471">BackwardWord</span></span>

<span data-ttu-id="0ce7d-472">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-472">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="0ce7d-473">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-473">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="0ce7d-474">コマンド: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-474">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="0ce7d-475">Emacs: `<Alt+b>` 、 `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-475">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="0ce7d-476">Vi の挿入モード: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-476">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="0ce7d-477">Vi コマンドモード: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-477">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="0ce7d-478">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-478">BeginningOfLine</span></span>

<span data-ttu-id="0ce7d-479">入力に複数の行がある場合は、現在の行の先頭に移動します。または、既に行の先頭にある場合は、入力の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-479">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="0ce7d-480">入力に1行しか含まれていない場合は、入力の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-480">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="0ce7d-481">コマンド: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-481">Cmd: `<Home>`</span></span>
- <span data-ttu-id="0ce7d-482">Emacs: `<Home>` 、 `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-482">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="0ce7d-483">Vi の挿入モード: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-483">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="0ce7d-484">Vi コマンドモード: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-484">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="0ce7d-485">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-485">EndOfLine</span></span>

<span data-ttu-id="0ce7d-486">入力に複数の行がある場合は、現在の行の末尾に移動します。または、既に行の末尾にある場合は、入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-486">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="0ce7d-487">入力に1行しか含まれていない場合は、入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-487">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="0ce7d-488">コマンド: `<End>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-488">Cmd: `<End>`</span></span>
- <span data-ttu-id="0ce7d-489">Emacs: `<End>` 、 `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-489">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="0ce7d-490">Vi の挿入モード: `<End>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-490">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="0ce7d-491">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="0ce7d-491">ForwardChar</span></span>

<span data-ttu-id="0ce7d-492">カーソルを1文字右に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-492">Move the cursor one character to the right.</span></span> <span data-ttu-id="0ce7d-493">これにより、カーソルが複数行入力の次の行に移動する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-493">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="0ce7d-494">コマンド: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-494">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="0ce7d-495">Emacs: `<RightArrow>` 、 `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-495">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="0ce7d-496">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-496">ForwardWord</span></span>

<span data-ttu-id="0ce7d-497">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-497">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="0ce7d-498">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-498">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="0ce7d-499">Emacs: `<Alt+f>` 、 `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-499">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="0ce7d-500">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="0ce7d-500">GotoBrace</span></span>

<span data-ttu-id="0ce7d-501">対応する中かっこ、かっこ、または角かっこにジャンプします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-501">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="0ce7d-502">コマンド: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-502">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="0ce7d-503">Vi の挿入モード: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-503">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="0ce7d-504">Vi コマンドモード: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-504">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="0ce7d-505">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="0ce7d-505">GotoColumn</span></span>

<span data-ttu-id="0ce7d-506">Arg で示される列に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-506">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="0ce7d-507">Vi コマンドモード: `<|>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-507">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="0ce7d-508">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-508">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="0ce7d-509">カーソルを行の空白以外の最初の文字に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-509">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="0ce7d-510">Vi コマンドモード: `<^>` 、 `<_>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-510">Vi command mode: `<^>`, `<_>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="0ce7d-511">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-511">MoveToEndOfLine</span></span>

<span data-ttu-id="0ce7d-512">カーソルを入力の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-512">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="0ce7d-513">Vi コマンドモード: `<End>` 、 `<$>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-513">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="0ce7d-514">NextLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-514">NextLine</span></span>

<span data-ttu-id="0ce7d-515">カーソルを次の行に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-515">Move the cursor to the next line.</span></span>

- <span data-ttu-id="0ce7d-516">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-516">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="0ce7d-517">NextWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-517">NextWord</span></span>

<span data-ttu-id="0ce7d-518">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-518">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="0ce7d-519">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-519">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="0ce7d-520">コマンド: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-520">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="0ce7d-521">Vi の挿入モード: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-521">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="0ce7d-522">Vi コマンドモード: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-522">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="0ce7d-523">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="0ce7d-523">NextWordEnd</span></span>

<span data-ttu-id="0ce7d-524">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-524">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="0ce7d-525">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-525">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="0ce7d-526">Vi コマンドモード: `<e>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-526">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="0ce7d-527">前の行</span><span class="sxs-lookup"><span data-stu-id="0ce7d-527">PreviousLine</span></span>

<span data-ttu-id="0ce7d-528">カーソルを前の行に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-528">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="0ce7d-529">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-529">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="0ce7d-530">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-530">ShellBackwardWord</span></span>

<span data-ttu-id="0ce7d-531">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-531">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="0ce7d-532">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-532">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="0ce7d-533">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-533">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="0ce7d-534">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-534">ShellForwardWord</span></span>

<span data-ttu-id="0ce7d-535">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-535">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="0ce7d-536">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-536">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="0ce7d-537">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-537">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="0ce7d-538">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-538">ShellNextWord</span></span>

<span data-ttu-id="0ce7d-539">カーソルを現在の単語の末尾、または単語の間で次の単語の末尾まで移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-539">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="0ce7d-540">単語の境界は、PowerShell トークンによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-540">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="0ce7d-541">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-541">Function is unbound.</span></span>

### <a name="vibackwardchar"></a><span data-ttu-id="0ce7d-542">ViBackwardChar</span><span class="sxs-lookup"><span data-stu-id="0ce7d-542">ViBackwardChar</span></span>

<span data-ttu-id="0ce7d-543">Vi 編集モードでカーソルを1文字左に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-543">Move the cursor one character to the left in the Vi edit mode.</span></span> <span data-ttu-id="0ce7d-544">これにより、カーソルが複数行の入力の前の行に移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-544">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="0ce7d-545">Vi の挿入モード: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-545">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="0ce7d-546">Vi コマンドモード: `<LeftArrow>` 、 `<Backspace>` 、 `<h>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-546">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="0ce7d-547">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-547">ViBackwardWord</span></span>

<span data-ttu-id="0ce7d-548">カーソルを現在の単語の先頭に戻すか、前の単語の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-548">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="0ce7d-549">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-549">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="0ce7d-550">Vi コマンドモード: `<b>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-550">Vi command mode: `<b>`</span></span>

### <a name="viforwardchar"></a><span data-ttu-id="0ce7d-551">ViForwardChar</span><span class="sxs-lookup"><span data-stu-id="0ce7d-551">ViForwardChar</span></span>

<span data-ttu-id="0ce7d-552">Vi 編集モードでカーソルを1文字右に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-552">Move the cursor one character to the right in the Vi edit mode.</span></span> <span data-ttu-id="0ce7d-553">これにより、カーソルが複数行入力の次の行に移動する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-553">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="0ce7d-554">Vi の挿入モード: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-554">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="0ce7d-555">Vi コマンドモード: `<RightArrow>` 、 `<Spacebar>` 、 `<l>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-555">Vi command mode: `<RightArrow>`, `<Spacebar>`, `<l>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="0ce7d-556">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="0ce7d-556">ViEndOfGlob</span></span>

<span data-ttu-id="0ce7d-557">区切り記号として空白文字のみを使用して、カーソルを単語の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-557">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="0ce7d-558">Vi コマンドモード: `<E>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-558">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="0ce7d-559">Viendofの Glob</span><span class="sxs-lookup"><span data-stu-id="0ce7d-559">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="0ce7d-560">単語区切り記号として空白文字のみを使用して、前の単語の末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-560">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="0ce7d-561">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-561">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="0ce7d-562">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="0ce7d-562">ViGotoBrace</span></span>

<span data-ttu-id="0ce7d-563">GotoBrace に似ていますが、トークンベースではなく文字ベースです。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-563">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="0ce7d-564">Vi コマンドモード: `<%>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-564">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="0ce7d-565">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="0ce7d-565">ViNextGlob</span></span>

<span data-ttu-id="0ce7d-566">単語区切り記号として空白文字のみを使用して、次の単語に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-566">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="0ce7d-567">Vi コマンドモード: `<W>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-567">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="0ce7d-568">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-568">ViNextWord</span></span>

<span data-ttu-id="0ce7d-569">次の単語の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-569">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="0ce7d-570">単語の境界は、構成可能な文字のセットによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-570">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="0ce7d-571">Vi コマンドモード: `<w>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-571">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="0ce7d-572">履歴関数</span><span class="sxs-lookup"><span data-stu-id="0ce7d-572">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="0ce7d-573">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="0ce7d-573">BeginningOfHistory</span></span>

<span data-ttu-id="0ce7d-574">履歴内の最初の項目に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-574">Move to the first item in the history.</span></span>

- <span data-ttu-id="0ce7d-575">.Emacs `<Alt+<>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-575">Emacs: `<Alt+<>`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="0ce7d-576">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="0ce7d-576">ClearHistory</span></span>

<span data-ttu-id="0ce7d-577">PSReadLine の履歴をクリアします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-577">Clears history in PSReadLine.</span></span> <span data-ttu-id="0ce7d-578">これは、PowerShell の履歴には影響しません。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-578">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="0ce7d-579">コマンド: `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-579">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="0ce7d-580">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="0ce7d-580">EndOfHistory</span></span>

<span data-ttu-id="0ce7d-581">履歴内の最後の項目 (現在の入力) に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-581">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="0ce7d-582">.Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-582">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="0ce7d-583">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="0ce7d-583">ForwardSearchHistory</span></span>

<span data-ttu-id="0ce7d-584">履歴を使用した増分転送検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-584">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="0ce7d-585">コマンド: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-585">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="0ce7d-586">.Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-586">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="0ce7d-587">履歴の Search後方</span><span class="sxs-lookup"><span data-stu-id="0ce7d-587">HistorySearchBackward</span></span>

<span data-ttu-id="0ce7d-588">現在の入力を、PSReadLine 履歴の ' previous ' 項目で置き換えます。この項目は、開始と入力の間の文字とカーソルの間の文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-588">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="0ce7d-589">コマンド: `<F8>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-589">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="0ce7d-590">履歴の Searchforward</span><span class="sxs-lookup"><span data-stu-id="0ce7d-590">HistorySearchForward</span></span>

<span data-ttu-id="0ce7d-591">現在の入力を、PSReadLine 履歴の ' next ' 項目で置き換えます。この項目は、開始と入力の間の文字とカーソルの間の文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-591">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="0ce7d-592">コマンド: `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-592">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="0ce7d-593">NextHistory</span><span class="sxs-lookup"><span data-stu-id="0ce7d-593">NextHistory</span></span>

<span data-ttu-id="0ce7d-594">現在の入力を、PSReadLine 履歴の ' next ' 項目に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-594">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="0ce7d-595">コマンド: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-595">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="0ce7d-596">Emacs: `<DownArrow>` 、 `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-596">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="0ce7d-597">Vi の挿入モード: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-597">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="0ce7d-598">Vi コマンドモード: `<DownArrow>` 、 `<j>` 、 `<+>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-598">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="0ce7d-599">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="0ce7d-599">PreviousHistory</span></span>

<span data-ttu-id="0ce7d-600">現在の入力を、PSReadLine 履歴の ' previous ' 項目に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-600">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="0ce7d-601">コマンド: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-601">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="0ce7d-602">Emacs: `<UpArrow>` 、 `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-602">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="0ce7d-603">Vi の挿入モード: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-603">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="0ce7d-604">Vi コマンドモード: `<UpArrow>` 、 `<k>` 、 `<->`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-604">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="0ce7d-605">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="0ce7d-605">ReverseSearchHistory</span></span>

<span data-ttu-id="0ce7d-606">履歴を介して後方検索を段階的に実行します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-606">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="0ce7d-607">コマンド: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-607">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="0ce7d-608">.Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-608">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="0ce7d-609">Visearchhistory 後方</span><span class="sxs-lookup"><span data-stu-id="0ce7d-609">ViSearchHistoryBackward</span></span>

<span data-ttu-id="0ce7d-610">検索文字列を入力し、AcceptLine で検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-610">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="0ce7d-611">Vi の挿入モード: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-611">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="0ce7d-612">Vi コマンドモード: `</>` 、 `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-612">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="0ce7d-613">入力候補関数</span><span class="sxs-lookup"><span data-stu-id="0ce7d-613">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="0ce7d-614">完了</span><span class="sxs-lookup"><span data-stu-id="0ce7d-614">Complete</span></span>

<span data-ttu-id="0ce7d-615">カーソルを囲むテキストに対して入力候補を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-615">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="0ce7d-616">候補が複数ある場合は、最長の明確なプレフィックスを使用して完了します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-616">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="0ce7d-617">最長の明確な完了を完了しようとすると、候補の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-617">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="0ce7d-618">.Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-618">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="0ce7d-619">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="0ce7d-619">MenuComplete</span></span>

<span data-ttu-id="0ce7d-620">カーソルを囲むテキストに対して入力候補を実行しようとしました。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-620">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="0ce7d-621">候補が複数ある場合は、最長の明確なプレフィックスを使用して完了します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-621">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="0ce7d-622">最長の明確な完了を完了しようとすると、候補の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-622">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="0ce7d-623">Cmd: `<Ctrl+@>` 、 `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-623">Cmd: `<Ctrl+@>`, `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="0ce7d-624">.Emacs `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-624">Emacs: `<Ctrl+Spacebar>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="0ce7d-625">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="0ce7d-625">PossibleCompletions</span></span>

<span data-ttu-id="0ce7d-626">候補の候補の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-626">Display the list of possible completions.</span></span>

- <span data-ttu-id="0ce7d-627">.Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-627">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="0ce7d-628">Vi の挿入モード: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-628">Vi insert mode: `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="0ce7d-629">Vi コマンドモード: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-629">Vi command mode: `<Ctrl+Spacebar>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="0ce7d-630">タブのすべてのタブ</span><span class="sxs-lookup"><span data-stu-id="0ce7d-630">TabCompleteNext</span></span>

<span data-ttu-id="0ce7d-631">次に使用可能な完了時に、カーソルを囲むテキストを完了します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-631">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="0ce7d-632">コマンド: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-632">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="0ce7d-633">Vi コマンドモード: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-633">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="0ce7d-634">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="0ce7d-634">TabCompletePrevious</span></span>

<span data-ttu-id="0ce7d-635">以前に使用可能な入力候補を使用して、カーソルを囲むテキストを完了しようとしました。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-635">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="0ce7d-636">コマンド: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-636">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="0ce7d-637">Vi コマンドモード: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-637">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="0ce7d-638">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="0ce7d-638">ViTabCompleteNext</span></span>

<span data-ttu-id="0ce7d-639">必要に応じて現在の編集グループを終了し、Tabends を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-639">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="0ce7d-640">Vi の挿入モード: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-640">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="0ce7d-641">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="0ce7d-641">ViTabCompletePrevious</span></span>

<span data-ttu-id="0ce7d-642">必要に応じて現在の編集グループを終了し、TabCompletePrevious を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-642">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="0ce7d-643">Vi の挿入モード: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-643">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="0ce7d-644">その他の関数</span><span class="sxs-lookup"><span data-stu-id="0ce7d-644">Miscellaneous functions</span></span>

### <a name="acceptnextsuggestionword"></a><span data-ttu-id="0ce7d-645">AcceptNextSuggestionWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-645">AcceptNextSuggestionWord</span></span>

<span data-ttu-id="0ce7d-646">インラインまたは選択した修正候補の次の単語をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-646">Accept the next word of the inline or selected suggestion.</span></span>

- <span data-ttu-id="0ce7d-647">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-647">Function is unbound.</span></span>

### <a name="acceptsuggestion"></a><span data-ttu-id="0ce7d-648">AcceptSuggestion</span><span class="sxs-lookup"><span data-stu-id="0ce7d-648">AcceptSuggestion</span></span>

<span data-ttu-id="0ce7d-649">現在のインラインまたは選択された提案を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-649">Accept the current inline or selected suggestion.</span></span>

- <span data-ttu-id="0ce7d-650">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-650">Function is unbound.</span></span>

### <a name="capturescreen"></a><span data-ttu-id="0ce7d-651">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="0ce7d-651">CaptureScreen</span></span>

<span data-ttu-id="0ce7d-652">対話型画面のキャプチャを開始する/下矢印行を選択し、[選択したテキストをテキストと html としてクリップボードにコピーする] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-652">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="0ce7d-653">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-653">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="0ce7d-654">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="0ce7d-654">ClearScreen</span></span>

<span data-ttu-id="0ce7d-655">画面をクリアし、画面の上部にある現在の線を描画します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-655">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="0ce7d-656">コマンド: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-656">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="0ce7d-657">.Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-657">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="0ce7d-658">Vi の挿入モード: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-658">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="0ce7d-659">Vi コマンドモード: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-659">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="0ce7d-660">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="0ce7d-660">DigitArgument</span></span>

<span data-ttu-id="0ce7d-661">他の関数に渡す新しい桁引数を開始します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-661">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="0ce7d-662">Cmd:、、、、、、、、、 `<Alt+0>` `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-662">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="0ce7d-663">Emacs:、、、、、、、、、 `<Alt+0>` `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` `<Alt+6>` `<Alt+7>` `<Alt+8>` `<Alt+9>` 、 `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-663">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="0ce7d-664">Vi コマンドモード:、、、、、、、、 `<0>` `<1>` `<2>` `<3>` `<4>` `<5>` `<6>` `<7>` `<8>` 、 `<9>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-664">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="0ce7d-665">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="0ce7d-665">InvokePrompt</span></span>

<span data-ttu-id="0ce7d-666">現在のプロンプトを消去し、prompt 関数を呼び出してプロンプトを再表示します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-666">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="0ce7d-667">現在のディレクトリを変更するなど、状態を変更するカスタムキーハンドラーに便利です。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-667">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="0ce7d-668">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-668">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="0ce7d-669">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="0ce7d-669">ScrollDisplayDown</span></span>

<span data-ttu-id="0ce7d-670">画面を1画面下へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-670">Scroll the display down one screen.</span></span>

- <span data-ttu-id="0ce7d-671">コマンド: `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-671">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="0ce7d-672">.Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-672">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="0ce7d-673">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-673">ScrollDisplayDownLine</span></span>

<span data-ttu-id="0ce7d-674">表示を1行下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-674">Scroll the display down one line.</span></span>

- <span data-ttu-id="0ce7d-675">コマンド: `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-675">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="0ce7d-676">.Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-676">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="0ce7d-677">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="0ce7d-677">ScrollDisplayToCursor</span></span>

<span data-ttu-id="0ce7d-678">カーソルまで画面をスクロールします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-678">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="0ce7d-679">.Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-679">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="0ce7d-680">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="0ce7d-680">ScrollDisplayTop</span></span>

<span data-ttu-id="0ce7d-681">画面を上にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-681">Scroll the display to the top.</span></span>

- <span data-ttu-id="0ce7d-682">.Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-682">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="0ce7d-683">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="0ce7d-683">ScrollDisplayUp</span></span>

<span data-ttu-id="0ce7d-684">画面を1画面上へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-684">Scroll the display up one screen.</span></span>

- <span data-ttu-id="0ce7d-685">コマンド: `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-685">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="0ce7d-686">.Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-686">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="0ce7d-687">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-687">ScrollDisplayUpLine</span></span>

<span data-ttu-id="0ce7d-688">表示を1行上へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-688">Scroll the display up one line.</span></span>

- <span data-ttu-id="0ce7d-689">コマンド: `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-689">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="0ce7d-690">.Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-690">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="0ce7d-691">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="0ce7d-691">SelfInsert</span></span>

<span data-ttu-id="0ce7d-692">キーを挿入します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-692">Insert the key.</span></span>

- <span data-ttu-id="0ce7d-693">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-693">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="0ce7d-694">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="0ce7d-694">ShowKeyBindings</span></span>

<span data-ttu-id="0ce7d-695">すべてのバインドされたキーを表示します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-695">Show all bound keys.</span></span>

- <span data-ttu-id="0ce7d-696">コマンド: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-696">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="0ce7d-697">.Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-697">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="0ce7d-698">Vi の挿入モード: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-698">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="0ce7d-699">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="0ce7d-699">ViCommandMode</span></span>

<span data-ttu-id="0ce7d-700">現在の動作モードを Vi-Insert から Vi-Command に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-700">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="0ce7d-701">Vi の挿入モード: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-701">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="0ce7d-702">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-702">ViDigitArgumentInChord</span></span>

<span data-ttu-id="0ce7d-703">Vi のいずれかの弦で、他の関数に渡す新しい桁引数を開始します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-703">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="0ce7d-704">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-704">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="0ce7d-705">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="0ce7d-705">ViEditVisually</span></span>

<span data-ttu-id="0ce7d-706">$Env: EDITOR または $env: ビジュアルによって指定されたテキストエディターでコマンドラインを編集します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-706">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="0ce7d-707">.Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-707">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="0ce7d-708">Vi コマンドモード: `<v>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-708">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="0ce7d-709">ViExit</span><span class="sxs-lookup"><span data-stu-id="0ce7d-709">ViExit</span></span>

<span data-ttu-id="0ce7d-710">シェルを終了します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-710">Exits the shell.</span></span>

- <span data-ttu-id="0ce7d-711">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-711">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="0ce7d-712">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="0ce7d-712">ViInsertMode</span></span>

<span data-ttu-id="0ce7d-713">挿入モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-713">Switch to Insert mode.</span></span>

- <span data-ttu-id="0ce7d-714">Vi コマンドモード: `<i>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-714">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="0ce7d-715">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="0ce7d-715">WhatIsKey</span></span>

<span data-ttu-id="0ce7d-716">キーを読み取り、キーがどのようにバインドされているかを通知します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-716">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="0ce7d-717">コマンド: `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-717">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="0ce7d-718">.Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-718">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="0ce7d-719">選択関数</span><span class="sxs-lookup"><span data-stu-id="0ce7d-719">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="0ce7d-720">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="0ce7d-720">ExchangePointAndMark</span></span>

<span data-ttu-id="0ce7d-721">カーソルがマークの位置に置かれ、マークがカーソルの位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-721">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="0ce7d-722">.Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-722">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="0ce7d-723">SelectAll</span><span class="sxs-lookup"><span data-stu-id="0ce7d-723">SelectAll</span></span>

<span data-ttu-id="0ce7d-724">行全体を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-724">Select the entire line.</span></span>

- <span data-ttu-id="0ce7d-725">コマンド: `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-725">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="0ce7d-726">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="0ce7d-726">SelectBackwardChar</span></span>

<span data-ttu-id="0ce7d-727">現在の選択範囲を調整して、前の文字を含めます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-727">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="0ce7d-728">コマンド: `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-728">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="0ce7d-729">.Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-729">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="0ce7d-730">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-730">SelectBackwardsLine</span></span>

<span data-ttu-id="0ce7d-731">カーソルから行の先頭まで、現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-731">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="0ce7d-732">コマンド: `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-732">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="0ce7d-733">.Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-733">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="0ce7d-734">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-734">SelectBackwardWord</span></span>

<span data-ttu-id="0ce7d-735">現在の選択範囲を調整して、前の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-735">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="0ce7d-736">コマンド: `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-736">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="0ce7d-737">.Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-737">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="0ce7d-738">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="0ce7d-738">SelectForwardChar</span></span>

<span data-ttu-id="0ce7d-739">現在の選択範囲を調整して、次の文字を含めます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-739">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="0ce7d-740">コマンド: `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-740">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="0ce7d-741">.Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-741">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="0ce7d-742">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-742">SelectForwardWord</span></span>

<span data-ttu-id="0ce7d-743">現在の選択範囲を調整して、ForwardWord を使用して次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-743">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="0ce7d-744">.Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-744">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="0ce7d-745">SelectLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-745">SelectLine</span></span>

<span data-ttu-id="0ce7d-746">カーソルから行の末尾まで、現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-746">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="0ce7d-747">コマンド: `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-747">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="0ce7d-748">.Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-748">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="0ce7d-749">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-749">SelectNextWord</span></span>

<span data-ttu-id="0ce7d-750">現在の選択範囲を調整して、次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-750">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="0ce7d-751">コマンド: `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-751">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="0ce7d-752">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-752">SelectShellBackwardWord</span></span>

<span data-ttu-id="0ce7d-753">ShellBackwardWord を使用して、前の単語が含まれるように現在の選択範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-753">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="0ce7d-754">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-754">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="0ce7d-755">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-755">SelectShellForwardWord</span></span>

<span data-ttu-id="0ce7d-756">現在の選択範囲を調整して、ShellForwardWord を使用する次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-756">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="0ce7d-757">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-757">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="0ce7d-758">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="0ce7d-758">SelectShellNextWord</span></span>

<span data-ttu-id="0ce7d-759">現在の選択範囲を調整して、ShellNextWord を使用して次の単語を含めます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-759">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="0ce7d-760">関数はバインド解除されています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-760">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="0ce7d-761">SetMark</span><span class="sxs-lookup"><span data-stu-id="0ce7d-761">SetMark</span></span>

<span data-ttu-id="0ce7d-762">後続の編集コマンドで使用するために、カーソルの現在の位置をマークします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-762">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="0ce7d-763">.Emacs `<Ctrl+@>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-763">Emacs: `<Ctrl+@>`</span></span>

## <a name="predictive-intellisense-functions"></a><span data-ttu-id="0ce7d-764">予測 IntelliSense 関数</span><span class="sxs-lookup"><span data-stu-id="0ce7d-764">Predictive IntelliSense functions</span></span>

> [!NOTE]
> <span data-ttu-id="0ce7d-765">これらの関数を使用するには、予測 IntelliSense を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-765">Predictive IntelliSense needs to be enabled to use these functions.</span></span>

### <a name="acceptnextwordsuggestion"></a><span data-ttu-id="0ce7d-766">AcceptNextWordSuggestion</span><span class="sxs-lookup"><span data-stu-id="0ce7d-766">AcceptNextWordSuggestion</span></span>

<span data-ttu-id="0ce7d-767">予測 IntelliSense からインライン提案の次の単語を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-767">Accepts the next word of the inline suggestion from Predictive IntelliSense.</span></span>
<span data-ttu-id="0ce7d-768">次のコマンドを実行して、この関数を<kbd>Ctrl</kbd> + <kbd>F</kbd>でバインドできます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-768">This function can be bound with <kbd>Ctrl</kbd>+<kbd>F</kbd> by running the following command.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord "Ctrl+f" -Function ForwardWord
```

### <a name="acceptsuggestion"></a><span data-ttu-id="0ce7d-769">AcceptSuggestion</span><span class="sxs-lookup"><span data-stu-id="0ce7d-769">AcceptSuggestion</span></span>

<span data-ttu-id="0ce7d-770">カーソルが現在の行の末尾にある場合に <kbd>→</kbd> を押すことで、予測 IntelliSense からの現在のインライン提案を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-770">Accepts the current inline suggestion from Predictive IntelliSense by pressing <kbd>RightArrow</kbd> when the cursor is at the end of the current line.</span></span>

## <a name="search-functions"></a><span data-ttu-id="0ce7d-771">関数の検索</span><span class="sxs-lookup"><span data-stu-id="0ce7d-771">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="0ce7d-772">文字検索</span><span class="sxs-lookup"><span data-stu-id="0ce7d-772">CharacterSearch</span></span>

<span data-ttu-id="0ce7d-773">文字を読み取り、その文字が次に出現するまで検索します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-773">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="0ce7d-774">引数が指定されている場合は、n 番目のオカレンスに対して前方 (負の場合は後方) を検索します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-774">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="0ce7d-775">コマンド: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-775">Cmd: `<F3>`</span></span>
- <span data-ttu-id="0ce7d-776">.Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-776">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="0ce7d-777">Vi の挿入モード: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-777">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="0ce7d-778">Vi コマンドモード: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-778">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="0ce7d-779">文字 Search後方</span><span class="sxs-lookup"><span data-stu-id="0ce7d-779">CharacterSearchBackward</span></span>

<span data-ttu-id="0ce7d-780">文字を読み取り、その文字が次に出現するまで検索します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-780">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="0ce7d-781">引数が指定されている場合は、n 番目のオカレンスに対して後方 (または負の場合は forward) を検索します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-781">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="0ce7d-782">コマンド: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-782">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="0ce7d-783">.Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-783">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="0ce7d-784">Vi の挿入モード: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-784">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="0ce7d-785">Vi コマンドモード: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-785">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="0ce7d-786">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="0ce7d-786">RepeatLastCharSearch</span></span>

<span data-ttu-id="0ce7d-787">最後に記録された文字の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-787">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="0ce7d-788">Vi コマンドモード: `<;>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-788">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="0ce7d-789">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="0ce7d-789">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="0ce7d-790">最後に記録された文字検索を逆方向に繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-790">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="0ce7d-791">Vi コマンドモード: `<,>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-791">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="0ce7d-792">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="0ce7d-792">RepeatSearch</span></span>

<span data-ttu-id="0ce7d-793">前と同じ方向に最後の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-793">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="0ce7d-794">Vi コマンドモード: `<n>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-794">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="0ce7d-795">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="0ce7d-795">RepeatSearchBackward</span></span>

<span data-ttu-id="0ce7d-796">前と同じ方向に最後の検索を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-796">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="0ce7d-797">Vi コマンドモード: `<N>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-797">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="0ce7d-798">SearchChar</span><span class="sxs-lookup"><span data-stu-id="0ce7d-798">SearchChar</span></span>

<span data-ttu-id="0ce7d-799">次の文字を読み取って検索し、次に文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-799">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="0ce7d-800">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-800">This is for 't' functionality.</span></span>

- <span data-ttu-id="0ce7d-801">Vi コマンドモード: `<f>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-801">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="0ce7d-802">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="0ce7d-802">SearchCharBackward</span></span>

<span data-ttu-id="0ce7d-803">次の文字を読み取り、それを検索して後方に移動し、次に文字を戻します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-803">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="0ce7d-804">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-804">This is for 'T' functionality.</span></span>

- <span data-ttu-id="0ce7d-805">Vi コマンドモード: `<F>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-805">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="0ce7d-806">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="0ce7d-806">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="0ce7d-807">次の文字を読み取り、それを検索して後方に移動し、次に文字を戻します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-807">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="0ce7d-808">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-808">This is for 'T' functionality.</span></span>

- <span data-ttu-id="0ce7d-809">Vi コマンドモード: `<T>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-809">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="0ce7d-810">SearchCharWithBackoff オフ</span><span class="sxs-lookup"><span data-stu-id="0ce7d-810">SearchCharWithBackoff</span></span>

<span data-ttu-id="0ce7d-811">次の文字を読み取って検索し、次に文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-811">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="0ce7d-812">これは、' ' の機能のためのものです。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-812">This is for 't' functionality.</span></span>

- <span data-ttu-id="0ce7d-813">Vi コマンドモード: `<t>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-813">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="0ce7d-814">SearchForward</span><span class="sxs-lookup"><span data-stu-id="0ce7d-814">SearchForward</span></span>

<span data-ttu-id="0ce7d-815">検索文字列を入力し、AcceptLine で検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-815">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="0ce7d-816">Vi の挿入モード: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-816">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="0ce7d-817">Vi コマンドモード: `<?>` 、 `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="0ce7d-817">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="0ce7d-818">カスタムキーバインド</span><span class="sxs-lookup"><span data-stu-id="0ce7d-818">Custom Key Bindings</span></span>

<span data-ttu-id="0ce7d-819">PSReadLine は、コマンドレットを使用してカスタムキーバインドをサポートしてい `Set-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-819">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="0ce7d-820">ほとんどのカスタムキーバインドは、たとえば、上記の関数の1つを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-820">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="0ce7d-821">ScriptBlock をキーにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-821">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="0ce7d-822">ScriptBlock は、ほとんどすべてのことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-822">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="0ce7d-823">いくつかの便利な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-823">Some useful examples include</span></span>

- <span data-ttu-id="0ce7d-824">コマンドラインを編集する</span><span class="sxs-lookup"><span data-stu-id="0ce7d-824">edit the command line</span></span>
- <span data-ttu-id="0ce7d-825">新しいウィンドウを開く (例: ヘルプ)</span><span class="sxs-lookup"><span data-stu-id="0ce7d-825">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="0ce7d-826">コマンドラインを変更せずにディレクトリを変更する</span><span class="sxs-lookup"><span data-stu-id="0ce7d-826">change directories without changing the command line</span></span>

<span data-ttu-id="0ce7d-827">ScriptBlock は、次の2つの引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-827">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="0ce7d-828">`$key` -カスタムバインドをトリガーしたキーである **[Consolekeyinfo]** オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-828">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="0ce7d-829">同じ ScriptBlock を複数のキーにバインドし、キーに応じて異なるアクションを実行する必要がある場合は、$key を確認します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-829">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="0ce7d-830">多くのカスタムバインドでは、この引数は無視します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-830">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="0ce7d-831">`$arg` -任意の引数。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-831">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="0ce7d-832">多くの場合、これは、ユーザーがキーバインド DigitArgument から渡す整数引数になります。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-832">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="0ce7d-833">バインディングが引数を受け入れない場合は、この引数を無視するのが妥当です。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-833">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="0ce7d-834">ここでは、コマンドラインを実行せずに履歴に追加する例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-834">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="0ce7d-835">これは、何らかの操作を忘れた場合に、既に入力したコマンドラインを再入力したくない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-835">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="0ce7d-836">PSReadLine モジュールフォルダーにインストールされているファイルには、さらに多くの例が表示 `SamplePSReadLineProfile.ps1` されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-836">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="0ce7d-837">ほとんどのキーバインドでは、コマンドラインを編集するためにいくつかのヘルパー関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-837">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="0ce7d-838">これらの Api については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-838">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="0ce7d-839">カスタムキーバインディングサポート Api</span><span class="sxs-lookup"><span data-stu-id="0ce7d-839">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="0ce7d-840">次の関数は PSConsoleReadLine では公開されていますが、キーに直接バインドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-840">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="0ce7d-841">多くの場合、カスタムキーバインドに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-841">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="0ce7d-842">コマンドラインを実行せずに、履歴に追加します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-842">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="0ce7d-843">Kill リングをクリアします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-843">Clear the kill-ring.</span></span>  <span data-ttu-id="0ce7d-844">これは主にテストに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-844">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="0ce7d-845">先頭から長さの文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-845">Delete length characters from start.</span></span>  <span data-ttu-id="0ce7d-846">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-846">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="0ce7d-847">ユーザー設定に基づいてアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-847">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="0ce7d-848">これらの2つの関数は、入力バッファーの現在の状態に関する有用な情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-848">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="0ce7d-849">1つ目は、単純なケースでよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-849">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="0ce7d-850">2つ目は、バインディングが Ast を使用してより高度な処理を実行している場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-850">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(string[] Chord)
```

<span data-ttu-id="0ce7d-851">この2つの関数は、によって使用され `Get-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-851">These two functions are used by `Get-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="0ce7d-852">最初のは、すべてのキーバインドを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-852">The first is used to get all key bindings.</span></span> <span data-ttu-id="0ce7d-853">2番目のは、特定のキーバインドを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-853">The second is used to get specific key bindings.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="0ce7d-854">この関数は Get-PSReadLineOption によって使用され、カスタムキーバインドではあまり役に立たない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-854">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="0ce7d-855">コマンドラインに何も選択されていない場合は、開始と長さの両方で-1 が返されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-855">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="0ce7d-856">コマンドラインに選択項目がある場合は、選択範囲の先頭と長さが返されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-856">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="0ce7d-857">カーソル位置に文字または文字列を挿入します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-857">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="0ce7d-858">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-858">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="0ce7d-859">これは、PSReadLine へのメインエントリポイントです。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-859">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="0ce7d-860">再帰はサポートされないため、カスタムキーバインドでは役に立ちません。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-860">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="0ce7d-861">この関数は Remove-PSReadLineKeyHandler によって使用され、カスタムキーバインドではあまり役に立たない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-861">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="0ce7d-862">入力の一部を置換します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-862">Replace some of the input.</span></span> <span data-ttu-id="0ce7d-863">この操作では、元に戻す/やり直しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-863">This operation supports undo/redo.</span></span> <span data-ttu-id="0ce7d-864">これは、undo の単一のアクションとして扱われるため、Delete の後に Insert を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-864">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="0ce7d-865">カーソルを指定されたオフセットに移動します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-865">Move the cursor to the given offset.</span></span> <span data-ttu-id="0ce7d-866">カーソルの移動は、元に戻すために追跡されません。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-866">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="0ce7d-867">この関数は、コマンドレットの設定-PSReadLineOption によって使用されるヘルパーメソッドですが、一時的に設定を変更する必要があるカスタムキーバインドに便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-867">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="0ce7d-868">このヘルパーメソッドは、DigitArgument を優先するカスタムバインドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-868">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="0ce7d-869">一般的な呼び出しは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-869">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="notes"></a><span data-ttu-id="0ce7d-870">メモ</span><span class="sxs-lookup"><span data-stu-id="0ce7d-870">Notes</span></span>

### <a name="command-history"></a><span data-ttu-id="0ce7d-871">コマンド履歴</span><span class="sxs-lookup"><span data-stu-id="0ce7d-871">Command History</span></span>

<span data-ttu-id="0ce7d-872">PSReadLine は、コマンドラインから入力したすべてのコマンドとデータを含む履歴ファイルを保持します。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-872">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="0ce7d-873">これには、パスワードなどの機密データが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-873">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="0ce7d-874">たとえば、コマンドレットを使用した場合、 `ConvertTo-SecureString` パスワードはプレーンテキストとして履歴ファイルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-874">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="0ce7d-875">履歴ファイルは、という名前のファイルです `$($host.Name)_history.txt` 。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-875">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="0ce7d-876">Windows システムでは、履歴ファイルはに格納され `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` ます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-876">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="0ce7d-877">Windows 以外のシステムでは、履歴ファイルはまたはに格納され `$env:XDG_DATA_HOME/powershell/PSReadLine` `$env:HOME/.local/share/powershell/PSReadLine` ます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-877">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="0ce7d-878">PSReadLine に貢献しているフィードバック &</span><span class="sxs-lookup"><span data-stu-id="0ce7d-878">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="0ce7d-879">GitHub の PSReadLine</span><span class="sxs-lookup"><span data-stu-id="0ce7d-879">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="0ce7d-880">プル要求を送信したり、GitHub ページでフィードバックを送信したりしてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-880">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ce7d-881">参照</span><span class="sxs-lookup"><span data-stu-id="0ce7d-881">See Also</span></span>

<span data-ttu-id="0ce7d-882">PSReadLine は、GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) ライブラリの影響を強く受けます。</span><span class="sxs-lookup"><span data-stu-id="0ce7d-882">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
