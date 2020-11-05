---
ms.date: 09/06/2019
keywords: powershell,コマンドレット
title: PowerShell 5.0 ISE の新機能
description: この記事では、Windows PowerShell Integrated Scripting Environment (ISE) バージョン 5.0 に導入された新機能と更新された機能について説明します。
ms.openlocfilehash: 75d37d0dafe381c84898ac48343336cd525d2dd1
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92660832"
---
# <a name="whats-new-in-the-windows-powershell-50-ise"></a><span data-ttu-id="2dc1a-104">Windows PowerShell 5.0 ISE の新機能</span><span class="sxs-lookup"><span data-stu-id="2dc1a-104">What's New in the Windows PowerShell 5.0 ISE</span></span>

<span data-ttu-id="2dc1a-105">この記事では、Windows PowerShell Integrated Scripting Environment (ISE) バージョン 5.0 に導入された新機能と更新された機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-105">This article explains the new and updated features that have been introduced in version 5.0 of the Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

> [!NOTE]
> <span data-ttu-id="2dc1a-106">PowerShell ISE は、アクティブな機能開発の対象ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-106">The PowerShell ISE is no longer in active feature development.</span></span> <span data-ttu-id="2dc1a-107">Windows に付属するコンポーネントとして、セキュリティや優先順位の高いサービスに関する修正プログラムが引き続き公式でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-107">As a shipping component of Windows, it continues to be officially supported for security and high-priority servicing fixes.</span></span>
> <span data-ttu-id="2dc1a-108">現在、Windows から ISE が削除される予定はありません。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-108">We currently have no plans to remove the ISE from Windows.</span></span>
>
> <span data-ttu-id="2dc1a-109">PowerShell v6 以降では、ISE はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-109">There is no support for the ISE in PowerShell v6 and beyond.</span></span> <span data-ttu-id="2dc1a-110">ISE の代替をお探しのユーザーは、[PowerShell 拡張機能](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell)と共に [Visual Studio Code](https://code.visualstudio.com/) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-110">Users looking for replacement for the ISE should use [Visual Studio Code](https://code.visualstudio.com/) with the [PowerShell Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell).</span></span>

## <a name="feature-description"></a><span data-ttu-id="2dc1a-111">機能の説明</span><span class="sxs-lookup"><span data-stu-id="2dc1a-111">Feature description</span></span>

<span data-ttu-id="2dc1a-112">Windows PowerShell ISE は、グラフィカルで直感的な環境でスクリプトおよびモジュールを記述、実行、テストすることができるホスト アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-112">The Windows PowerShell ISE is a host application that enables you to write, run, and test scripts and modules in a graphical and intuitive environment.</span></span> <span data-ttu-id="2dc1a-113">構文の色分け、タブ補完、視覚的なデバッグ機能、Unicode 準拠、状況依存のヘルプなどの主要な機能により、多彩なスクリプトの操作性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-113">Key features such as syntax-coloring, tab completion, visual debugging, Unicode compliance, and context-sensitive Help provide a rich scripting experience.</span></span>

<span data-ttu-id="2dc1a-114">詳細については、「[Windows PowerShell ISE の紹介](../ise/Introducing-the-Windows-PowerShell-ISE.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-114">For more information, see [Introducing the Windows PowerShell ISE](../ise/Introducing-the-Windows-PowerShell-ISE.md).</span></span>

<span data-ttu-id="2dc1a-115">次の表に、Windows PowerShell における Windows PowerShell ISE のこのリリースの新機能と変更された機能を示します。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-115">The following table lists the new and changed features for this release of Windows PowerShell ISE in Windows PowerShell.</span></span>

## <a name="intellisense"></a><span data-ttu-id="2dc1a-116">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="2dc1a-116">IntelliSense</span></span>

> <span data-ttu-id="2dc1a-117">ISE 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="2dc1a-117">Added in ISE 3.0</span></span>

<span data-ttu-id="2dc1a-118">IntelliSense は、Windows PowerShell ISE の一部である自動補完アシスタンス機能です。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-118">IntelliSense is an automatic-completion assistance feature that is part of Windows PowerShell ISE.</span></span>
<span data-ttu-id="2dc1a-119">IntelliSense により、文字を入力していくと、一致する可能性のあるコマンドレット、パラメーター、パラメーター値、ファイル、またはフォルダーのクリック可能なメニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-119">IntelliSense displays clickable menus of potentially matching cmdlets, parameters, parameter values, files, or folders as you type.</span></span>

<span data-ttu-id="2dc1a-120">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-120">**What value does this change add?**</span></span>

<span data-ttu-id="2dc1a-121">IntelliSense の追加により、Windows PowerShell ISE を使用してスクリプトを作成する際に、コマンドレットと構文をより簡単に見つけられるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-121">With the addition of IntelliSense, it's easier to discover cmdlets and syntax when you use Windows PowerShell ISE to create scripts.</span></span> <span data-ttu-id="2dc1a-122">また新しいスクリプトの作成中に Windows PowerShell ISE を使用して Windows PowerShell を理解することもできます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-122">You can also use Windows PowerShell ISE to learn Windows PowerShell while you create new scripts.</span></span>

<span data-ttu-id="2dc1a-123">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-123">**What works differently?**</span></span>

<span data-ttu-id="2dc1a-124">Windows PowerShell ISE でコマンドレットを入力すると、スクロールとクリックが可能なメニューが表示され、適切なコマンドを参照して選択できます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-124">When you type cmdlets in the Windows PowerShell ISE, a scrollable and clickable menu displays, allowing you to browse and select the appropriate commands.</span></span>

## <a name="snippets"></a><span data-ttu-id="2dc1a-125">スニペット</span><span class="sxs-lookup"><span data-stu-id="2dc1a-125">Snippets</span></span>

> <span data-ttu-id="2dc1a-126">ISE 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="2dc1a-126">Added in ISE 3.0</span></span>

<span data-ttu-id="2dc1a-127">*スニペット* は、Windows PowerShell ISE で作成するスクリプトに挿入できる Windows PowerShell コードの短いセクションです。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-127">*Snippets* are short sections of Windows PowerShell code that you can insert into the scripts you create in Windows PowerShell ISE.</span></span> <span data-ttu-id="2dc1a-128">Windows PowerShell ISE にはスニペットの既定のセットが付属しています。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-128">Windows PowerShell ISE comes with a default set of snippets.</span></span> <span data-ttu-id="2dc1a-129">Windows PowerShell ISE での作業中に、`New-Snippet` コマンドレットを使用してスニペットを追加できます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-129">You can add snippets by using the `New-Snippet` cmdlet while working in Windows PowerShell ISE.</span></span>

<span data-ttu-id="2dc1a-130">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-130">**What value does this change add?**</span></span>

<span data-ttu-id="2dc1a-131">スニペットを使用すると、スクリプトをすばやくアセンブルして作成し、環境を自動化できます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-131">By using snippets, you can quickly assemble and create scripts to automate your environment.</span></span>

<span data-ttu-id="2dc1a-132">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-132">**What works differently?**</span></span>

<span data-ttu-id="2dc1a-133">Windows PowerShell 3.0 以降でスニペットを使用するには、 **[編集]** メニューで **[スニペットの開始]** をクリックするか、<kbd>Ctrl</kbd>+<kbd>J</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-133">To use snippets in Windows PowerShell 3.0 or later, on the **Edit** menu, click **Start Snippets** , or press <kbd>Ctrl</kbd>+<kbd>J</kbd>.</span></span>

## <a name="add-on-tools"></a><span data-ttu-id="2dc1a-134">アドオン ツール</span><span class="sxs-lookup"><span data-stu-id="2dc1a-134">Add-on tools</span></span>

> <span data-ttu-id="2dc1a-135">PowerShell 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="2dc1a-135">Added in PowerShell 3.0</span></span>

<span data-ttu-id="2dc1a-136">Windows PowerShell ISE で、オブジェクト モデルを使用するアドオン ツールがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-136">Windows PowerShell ISE now supports add-on tools using the object model.</span></span> <span data-ttu-id="2dc1a-137">これらのアドオンは、コンソールに垂直方向または水平方向のウィンドウとして表示される Windows Presentation Foundation (WPF) コントロールです。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-137">These add-ons are Windows Presentation Foundation (WPF) controls that are displayed as a vertical or horizontal pane in the console.</span></span> <span data-ttu-id="2dc1a-138">1 つのウィンドウ内に複数のアドオン ツールがある場合は、タブ形式のコントロールとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-138">Multiple add-on tools in a pane are displayed as a tabbed control.</span></span> <span data-ttu-id="2dc1a-139">また、サード パーティ製のアドオン ツールも追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-139">You can also add or remove add-on tools that are produced by non-Microsoft parties.</span></span> <span data-ttu-id="2dc1a-140">詳細については、「[Windows PowerShell ISE スクリプト オブジェクト モデルの目的](../ise/object-model/Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-140">For more information, see [The Purpose of the Windows PowerShell ISE Scripting Object Model](../ise/object-model/Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md).</span></span>

<span data-ttu-id="2dc1a-141">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-141">**What value does this change add?**</span></span>

<span data-ttu-id="2dc1a-142">アドオンにより、機能の追加やスクリプト作成エクスペリエンスの向上を実現するツールを使って、Windows PowerShell ISE を拡張およびカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-142">Add-ons allow you to extend and customize Windows PowerShell ISE with tools that add functionality and enhance your scripting experience.</span></span>

<span data-ttu-id="2dc1a-143">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-143">**What works differently?**</span></span>

<span data-ttu-id="2dc1a-144">Windows PowerShell ISE 3.0 以降には、 **Commands** アドオンが付属しています。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-144">Windows PowerShell ISE 3.0 and later come with the **Commands** add-on.</span></span> <span data-ttu-id="2dc1a-145">**Commands** アドオンを使用すると、コマンドレットを参照し、 **[スクリプト]** ウィンドウと **[コンソール]** ウィンドウで同時にコマンドレットに関するヘルプにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-145">The **Commands** add-on allows you to browse cmdlets, and access help about the cmdlets side-by-side with the **Script** and **Console** Panes.</span></span>

<span data-ttu-id="2dc1a-146">追加のアドオンは、 **[アドオン]** メニューの **[アドオン ツール Web サイトを開く]** コマンドを使用して検索することができます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-146">Additional add-ons can be found by using the **Open Add-on Tools Website** command on the **Add-ons** menu.</span></span>

## <a name="restart-manager-and-auto-save"></a><span data-ttu-id="2dc1a-147">再起動マネージャーと自動保存</span><span class="sxs-lookup"><span data-stu-id="2dc1a-147">Restart manager and auto-save</span></span>

> <span data-ttu-id="2dc1a-148">PowerShell 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="2dc1a-148">Added in PowerShell 3.0</span></span>

<span data-ttu-id="2dc1a-149">Windows PowerShell ISE では、開いているスクリプトを 2 分おきに別の場所に自動的に保存するようになりました。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-149">Windows PowerShell ISE now automatically saves your open scripts every two minutes, in a separate location.</span></span> <span data-ttu-id="2dc1a-150">予期しないクラッシュまたはリブート後に Windows PowerShell ISE が再起動すると、最後のセッションで開いていたスクリプトが (そのスクリプトが保存されていなかった場合でも) 回復されます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-150">When Windows PowerShell ISE restarts after an unexpected crash or reboot, it recovers scripts that were open in the last session, even if the scripts weren't saved.</span></span>

<span data-ttu-id="2dc1a-151">自動保存の間隔を変更するには、コンソール ウィンドウで `$psise.Options.AutoSaveMinuteInterval` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-151">To change the automatic saving interval, run the following command in the Console pane: `$psise.Options.AutoSaveMinuteInterval`.</span></span>

<span data-ttu-id="2dc1a-152">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-152">**What value does this change add?**</span></span>

<span data-ttu-id="2dc1a-153">Windows PowerShell ISE 内での作業で、開いているスクリプトが自動的に保存されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-153">You can now work within Windows PowerShell ISE knowing that your open scripts are automatically saved.</span></span>

<span data-ttu-id="2dc1a-154">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-154">**What works differently?**</span></span>

<span data-ttu-id="2dc1a-155">Windows PowerShell ISE 2.0 では、スクリプトは自動的に保存されません。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-155">Windows PowerShell ISE 2.0 doesn't save the scripts automatically.</span></span>

## <a name="most-recently-used-list"></a><span data-ttu-id="2dc1a-156">最近使用した一覧</span><span class="sxs-lookup"><span data-stu-id="2dc1a-156">Most-recently used list</span></span>

> <span data-ttu-id="2dc1a-157">PowerShell 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="2dc1a-157">Added in PowerShell 3.0</span></span>

<span data-ttu-id="2dc1a-158">Windows PowerShell ISE にファイルの最近使用した一覧が用意されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-158">Windows PowerShell ISE now has a most-recently used list for files.</span></span> <span data-ttu-id="2dc1a-159">Windows PowerShell ISE でファイルを開くと、ファイルは **[ファイル]** メニューの最近使用した一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-159">When you open a file in Windows PowerShell ISE, the file is added to the most-recently used list on the **File** menu.</span></span>

<span data-ttu-id="2dc1a-160">最近使用した一覧に含まれるファイル数の規定値を変更するには、[コンソール] ウィンドウで、`$psise.Options.MruCount` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-160">To change the default number of files in the most-recently used list, run the following command in the Console Pane: `$psise.Options.MruCount`.</span></span>

<span data-ttu-id="2dc1a-161">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-161">**What value does this change add?**</span></span>

<span data-ttu-id="2dc1a-162">最近使用した一覧を使用して、頻繁に使用されるファイルに簡単にアクセスできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-162">You can now use the most-recently used list to easily access your frequently used files.</span></span>

<span data-ttu-id="2dc1a-163">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-163">**What works differently?**</span></span>

<span data-ttu-id="2dc1a-164">Windows PowerShell ISE 2.0 には、最近使用した一覧は用意されていません。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-164">Windows PowerShell ISE 2.0 doesn't have a most-recently used list.</span></span>

## <a name="console-pane"></a><span data-ttu-id="2dc1a-165">コンソール ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="2dc1a-165">Console Pane</span></span>

> <span data-ttu-id="2dc1a-166">PowerShell 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="2dc1a-166">Added in PowerShell 3.0</span></span>

<span data-ttu-id="2dc1a-167">Windows PowerShell ISE の最初のリリースで使用できた、独立したコマンド ウィンドウと出力ウィンドウが 1 つのコンソール ウィンドウに統合されました。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-167">The separate Command and Output Panes that were available in the first release of Windows PowerShell ISE have been combined into a single Console Pane.</span></span> <span data-ttu-id="2dc1a-168">コンソール ウィンドウの機能と外観は、標準的な Windows PowerShell コンソールと類似していますが、次のような機能強化が行われています。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-168">The Console Pane is similar in function and appearance to a typical Windows PowerShell console, but it includes the following enhancements:</span></span>

- <span data-ttu-id="2dc1a-169">XML 構文を含む入力テキストの構文の色分け (出力テキストを除く)</span><span class="sxs-lookup"><span data-stu-id="2dc1a-169">Syntax coloring for input text (not output text), including XML syntax</span></span>
- <span data-ttu-id="2dc1a-170">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="2dc1a-170">IntelliSense</span></span>
- <span data-ttu-id="2dc1a-171">かっこの一致</span><span class="sxs-lookup"><span data-stu-id="2dc1a-171">Brace matching</span></span>
- <span data-ttu-id="2dc1a-172">エラー表示</span><span class="sxs-lookup"><span data-stu-id="2dc1a-172">Error indication</span></span>
- <span data-ttu-id="2dc1a-173">全角 Unicode のサポート</span><span class="sxs-lookup"><span data-stu-id="2dc1a-173">Full Unicode support</span></span>
- <span data-ttu-id="2dc1a-174"><kbd>F1</kbd> キーによる状況依存のヘルプ</span><span class="sxs-lookup"><span data-stu-id="2dc1a-174"><kbd>F1</kbd> context-sensitive help</span></span>
- <span data-ttu-id="2dc1a-175"><kbd>Ctrl</kbd>+<kbd>F1</kbd> キーによる状況依存の Show-Command</span><span class="sxs-lookup"><span data-stu-id="2dc1a-175"><kbd>Ctrl</kbd>+<kbd>F1</kbd> context-sensitive Show-Command</span></span>
- <span data-ttu-id="2dc1a-176">複雑なスクリプトおよび右から左への記述のサポート</span><span class="sxs-lookup"><span data-stu-id="2dc1a-176">Complex script and right-to-left support</span></span>
- <span data-ttu-id="2dc1a-177">フォントのサポート</span><span class="sxs-lookup"><span data-stu-id="2dc1a-177">Font support</span></span>
- <span data-ttu-id="2dc1a-178">Zoom</span><span class="sxs-lookup"><span data-stu-id="2dc1a-178">Zoom</span></span>
- <span data-ttu-id="2dc1a-179">行選択モードとブロック選択モード</span><span class="sxs-lookup"><span data-stu-id="2dc1a-179">Line-select and block-select modes</span></span>
- <span data-ttu-id="2dc1a-180"><kbd>上方向</kbd>キーを押して履歴をコンソールに表示したときにコマンド ラインに入力されたコンテンツを保存する機能</span><span class="sxs-lookup"><span data-stu-id="2dc1a-180">Preservation of typed content at the command line when you press the <kbd>UpArrow</kbd> to view history in the console</span></span>

<span data-ttu-id="2dc1a-181">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-181">**What value does this change add?**</span></span>

<span data-ttu-id="2dc1a-182">これらのコンソール ウィンドウの変更を追加したことにより、コンソール インターフェイスとの一貫性がより向上したスクリプトの操作性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-182">The addition of these Console Pane changes provides a scripting experience that is more consistent with the console interface.</span></span>

<span data-ttu-id="2dc1a-183">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-183">**What works differently?**</span></span>

<span data-ttu-id="2dc1a-184">Windows PowerShell ISE 2.0 では、コマンド ウィンドウと出力ウィンドウは個別に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-184">Windows PowerShell ISE 2.0 has separate Command and Output Panes.</span></span>

## <a name="command-line-switches"></a><span data-ttu-id="2dc1a-185">コマンド ライン スイッチ</span><span class="sxs-lookup"><span data-stu-id="2dc1a-185">Command-line switches</span></span>

> <span data-ttu-id="2dc1a-186">PowerShell 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="2dc1a-186">Added in PowerShell 3.0</span></span>

<span data-ttu-id="2dc1a-187">コマンド ライン (「 **Powershell_ise.exe** 」を入力) から Windows PowerShell ISE を起動する場合、次の新しいコマンド ライン スイッチを追加できます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-187">If you start Windows PowerShell ISE from the command line (by typing **powershell_ise.exe** ), you can add the following new command-line switches.</span></span>

- <span data-ttu-id="2dc1a-188">`-NoProfile`:`$profile` を実行せずに Windows PowerShell ISE を起動する</span><span class="sxs-lookup"><span data-stu-id="2dc1a-188">`-NoProfile`: Starts Windows PowerShell ISE without running `$profile`</span></span>
- <span data-ttu-id="2dc1a-189">`-Help`:ヘルプ ウィンドウを表示する</span><span class="sxs-lookup"><span data-stu-id="2dc1a-189">`-Help`: Displays a Help window</span></span>
- <span data-ttu-id="2dc1a-190">`-mta`:マルチスレッド アパートメント モードで Windows PowerShell ISE を起動する。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-190">`-mta`: Starts Windows PowerShell ISE in multithreaded apartment mode.</span></span> <span data-ttu-id="2dc1a-191">Windows PowerShell ISE の既定の操作モードは、シングル スレッド アパートメント モード、つまり `-sta` です。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-191">The default operation mode for Windows PowerShell ISE is single-threaded apartment mode, or `-sta`.</span></span>

<span data-ttu-id="2dc1a-192">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-192">**What value does this change add?**</span></span>

<span data-ttu-id="2dc1a-193">これらのコマンド ライン スイッチを追加すると、Windows PowerShell ISE が動作する環境を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-193">The addition of these command-line switches allows you to control the environment in which the Windows PowerShell ISE runs.</span></span>

<span data-ttu-id="2dc1a-194">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-194">**What works differently?**</span></span>

<span data-ttu-id="2dc1a-195">Windows PowerShell ISE 2.0 では、これらのコマンド ライン スイッチは認識されません。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-195">Windows PowerShell ISE 2.0 doesn't recognize these command-line switches.</span></span>

## <a name="new-editor-features"></a><span data-ttu-id="2dc1a-196">エディターの新機能</span><span class="sxs-lookup"><span data-stu-id="2dc1a-196">New editor features</span></span>

> <span data-ttu-id="2dc1a-197">PowerShell 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="2dc1a-197">Added in PowerShell 3.0</span></span>

<span data-ttu-id="2dc1a-198">その他の Windows PowerShell ISE 編集機能として、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-198">Other Windows PowerShell ISE editing features include:</span></span>

- <span data-ttu-id="2dc1a-199">**XML 構文の色分け** - Windows PowerShell ISE では、Windows PowerShell 構文を色分けする方法と同じ方法で XML 構文が色分けされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-199">**XML syntax coloring** - Windows PowerShell ISE now colors XML syntax in the same way as it colors Windows PowerShell syntax.</span></span>
- <span data-ttu-id="2dc1a-200">**かっこの照合** - Windows PowerShell ISE にはかっこの照合と強調表示を行う機能が含まれ、次のように使用できます。たとえば、始めかっこを選択している場合、 **[一致する項目に移動]** コマンドまたは <kbd>Ctrl</kbd>+<kbd>]</kbd> キーを使用すると、終わりかっこが見つかります。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-200">**Brace matching** - Windows PowerShell ISE includes brace matching and highlighting, and can be used in the following ways: (for example, using the **Go to Match** command or <kbd>Ctrl</kbd>+<kbd>]</kbd> locates the closing brace, if you have an opening brace selected).</span></span>
- <span data-ttu-id="2dc1a-201">**アウトライン表示** 。スクリプト ウィンドウでは、アウトラインがサポートされます。これにより、左余白のプラス記号またはマイナス記号をクリックすると、コードのセクションを折りたたんだり展開したりできます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-201">**Outline view** The Script Pane supports outlining, which allows collapsing or expanding sections of code by clicking plus or minus signs in the left margin.</span></span> <span data-ttu-id="2dc1a-202">かっこ、または `#region` タグと `#endregion` タグを使用して、折りたたみ可能なセクションの先頭と末尾をマークすることができます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-202">You can use braces or the `#region` and `#endregion` tags to mark the beginning or end of a collapsible section.</span></span> <span data-ttu-id="2dc1a-203">すべての領域を展開する、または折りたたむには、<kbd>Ctrl</kbd>+<kbd>M</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-203">To expand or collapse all regions, press <kbd>Ctrl</kbd>+<kbd>M</kbd>.</span></span>
- <span data-ttu-id="2dc1a-204">**ドラッグ アンド ドロップ テキスト編集** - Windows PowerShell ISE で、ドラッグ アンド ドロップによるテキスト編集がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-204">**Drag and drop text editing** - Windows PowerShell ISE now supports drag and drop text editing.</span></span> <span data-ttu-id="2dc1a-205">任意のテキストのブロックを選択し、そのテキストをドラッグしてエディターまたはコンソール内の別の場所に移動できます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-205">You can select any block of text and drag that text to another location in the editor or the console to move the text.</span></span> <span data-ttu-id="2dc1a-206"><kbd>Ctrl</kbd> キーを押したまま選択したテキストをドラッグし、マウス ボタンを放すと、テキストが新しい場所にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-206">If you hold down the <kbd>Ctrl</kbd> key while you drag the selected text, when you release the mouse button the text is copied to the new location.</span></span> <span data-ttu-id="2dc1a-207">このバージョンの Windows PowerShell ISE では、ファイルを Windows PowerShell ISE 上にドラッグ アンド ドロップすると、Windows PowerShell ISE でファイルが開かれます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-207">In this version of Windows PowerShell ISE, when you drag and drop files onto Windows PowerShell ISE, Windows PowerShell ISE opens the file.</span></span>
- <span data-ttu-id="2dc1a-208">**解析エラーの表示** - 解析エラーは赤い下線で示されます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-208">**Parse error display** - Parse errors are indicated with red underlines.</span></span> <span data-ttu-id="2dc1a-209">示されたエラーをポイントすると、コード内で見つかった問題がヒントのテキストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-209">When you hover over an indicated error, tooltip text displays the problem that was found in the code.</span></span>
- <span data-ttu-id="2dc1a-210">**ズーム** - ズーム スライダー (Windows PowerShell ISE ウィンドウの右下隅にあります) を使用するか、コンソール ウィンドウで `$psise.options.Zoom` コマンドを入力することで、コンソールのコンテンツのズーム倍率を設定できます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-210">**Zoom** - The zoom percentage of the console's content can be set by using the zoom slider (in the lower right corner of Windows PowerShell ISE window), or by entering the command `$psise.options.Zoom` in the Console Pane.</span></span>
- <span data-ttu-id="2dc1a-211">**リッチ テキストのコピーと貼り付け** - Windows PowerShell ISE でクリップボードにコピーすると、元の選択範囲のフォント、サイズ、および色の情報が保存されます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-211">**Rich text copy and paste** - Copying to the clipboard in Windows PowerShell ISE preserves the font, size, and color information of the original selection.</span></span>
- <span data-ttu-id="2dc1a-212">**ブロック選択** - テキストのブロックを選択するには、 <kbd>Alt</kbd> キーを押したままマウスでスクリプト ウィンドウ内のテキストを選択するか、 <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>方向</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-212">**Block selection** - You can select a block of text by holding down the <kbd>ALT</kbd> key while selecting text in the Script Pane with your mouse, or by pressing <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>Arrow</kbd>.</span></span>

<span data-ttu-id="2dc1a-213">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-213">**What value does this change add?**</span></span>

<span data-ttu-id="2dc1a-214">追加の編集機能によって、より一貫性のある強力な編集環境が提供されます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-214">The additional editing features provide a more consistent and powerful editing environment.</span></span>

<span data-ttu-id="2dc1a-215">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-215">**What works differently?**</span></span>

<span data-ttu-id="2dc1a-216">これらの編集の拡張機能は Windows PowerShell ISE 2.0 にはなかった機能です。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-216">These editing enhancements weren't present in Windows PowerShell ISE 2.0.</span></span>

## <a name="new-help-viewer-window"></a><span data-ttu-id="2dc1a-217">新しいヘルプ ビューアー ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="2dc1a-217">New Help viewer window</span></span>

> <span data-ttu-id="2dc1a-218">PowerShell 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="2dc1a-218">Added in PowerShell 3.0</span></span>

<span data-ttu-id="2dc1a-219">カーソルがコマンドレット内にあるかコマンドレットの一部を強調表示しているときに <kbd>F1</kbd> キーを押すと、強調表示されたコマンドレットに関する状況依存のヘルプが新しいヘルプ ビューアーで開かれます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-219">If you press <kbd>F1</kbd> when your cursor is in a cmdlet, or you have part of a cmdlet highlighted, the new Help viewer opens context-sensitive Help about the highlighted cmdlet.</span></span> <span data-ttu-id="2dc1a-220">Windows PowerShell の **About** ヘルプを表示するには、コンソール ウィンドウで「`operators`」と入力し、 <kbd>F1</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-220">To display Windows PowerShell **About** help, type `operators` in the console pane, and then press <kbd>F1</kbd>.</span></span>

<span data-ttu-id="2dc1a-221">この機能を使用する前に、Microsoft Web サイトから Windows PowerShell のヘルプ トピックの最新バージョンをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-221">Before you use this feature, download the most current version of Windows PowerShell Help topics from the Microsoft website.</span></span> <span data-ttu-id="2dc1a-222">ヘルプ トピックをダウンロードする最も簡単な方法は、管理者として Windows PowerShell を実行中に、コンソール ウィンドウで `Update-Help` コマンドレットを実行することです。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-222">The simplest method for downloading the Help topics is to run the `Update-Help` cmdlet in the Console Pane when running Windows PowerShell ISE as administrator.</span></span>

<span data-ttu-id="2dc1a-223"><kbd>F1</kbd> キーを押したときにヘルプを検索する場所を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-223">You can alter where the <kbd>F1</kbd> key looks for Help.</span></span> <span data-ttu-id="2dc1a-224">**[ツール]** / **[オプション]** メニューで、 **[全般設定]** タブの **[その他の設定]** の下で、 **[オンライン コンテンツの代わりにローカル ヘルプ コンテンツを使用する]** ボックスをオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-224">In the **Tools**/**Options** menu, on the **General Settings** tab, under **Other Settings** , you can set or clear the checkbox **Use local help content instead of online content**.</span></span> <span data-ttu-id="2dc1a-225">オンにした場合、クライアントでは、モジュール フォルダー内にあるダウンロード済みのヘルプから、コマンドレットのヘルプが検索されます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-225">When checked, the client looks for the cmdlet Help in the downloaded Help found in the modules folder.</span></span> <span data-ttu-id="2dc1a-226">チェックボックスがオフの場合、クライアントではヘルプをオンラインで検索します。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-226">If the checkbox is cleared, the client looks for help online.</span></span>

<span data-ttu-id="2dc1a-227">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-227">**What value does this change add?**</span></span>

<span data-ttu-id="2dc1a-228">現在のコマンドレットまたはスクリプトを離れることなく状況依存のヘルプを使用することで、統合された学習を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-228">Context-sensitive Help without leaving your current cmdlet or script provides an integrated learning experience.</span></span>

<span data-ttu-id="2dc1a-229">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-229">**What works differently?**</span></span>

<span data-ttu-id="2dc1a-230">以前のバージョンの Windows PowerShell ISE では、<kbd>F1</kbd> キーを押すと、ローカル コンピューター上のヘルプ ファイルが開きました。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-230">Pressing <kbd>F1</kbd> in previous versions of Windows PowerShell ISE opened the help file on the local computer.</span></span> <span data-ttu-id="2dc1a-231">Windows PowerShell ISE 3.0 以降では、検索と構成が可能なコマンドレットのヘルプを含むウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-231">In Windows PowerShell ISE 3.0 and later, a window opens that contains the help for the cmdlet that is searchable and configurable.</span></span> <span data-ttu-id="2dc1a-232">このヘルプ エクスペリエンスは Windows PowerShell ISE 3.0 の新機能であり、更新可能なヘルプは Windows PowerShell 3.0 の新機能です。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-232">This Help experience is new for Windows PowerShell ISE 3.0, and Updatable Help is new for Windows PowerShell 3.0.</span></span>

## <a name="show-command-cmdlet"></a><span data-ttu-id="2dc1a-233">Show-Command コマンドレット</span><span class="sxs-lookup"><span data-stu-id="2dc1a-233">Show-Command cmdlet</span></span>

> <span data-ttu-id="2dc1a-234">PowerShell 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="2dc1a-234">Added in PowerShell 3.0</span></span>

<span data-ttu-id="2dc1a-235">`Show-Command` コマンドレットを使用すると、グラフィカルなフォームに情報を入力してコマンドレットや関数を構成または実行できます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-235">The `Show-Command` cmdlet enables you to compose or run a cmdlet or function by filling in a graphical form.</span></span> <span data-ttu-id="2dc1a-236">フォームを使用すると、グラフィカルな環境でユーザーが Windows PowerShell で作業できます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-236">The form lets users work with Windows PowerShell in a graphical environment.</span></span>
<span data-ttu-id="2dc1a-237">また、上級のスクリプト作成者は `Show-Command` を使用して、簡単な Windows PowerShell ベースの GUI を作成できます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-237">`Show-Command` also enables advanced scripters to create a quick Windows PowerShell-based GUI.</span></span>

<span data-ttu-id="2dc1a-238">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-238">**What value does this change add?**</span></span>

<span data-ttu-id="2dc1a-239">Windows PowerShell スクリプトで `Show-Command` を使用すると、ユーザーが使い慣れたグラフィカルな環境を提供できます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-239">By using `Show-Command` in your Windows PowerShell scripts, you can provide your users with the graphical environment with which they're familiar.</span></span> <span data-ttu-id="2dc1a-240">また、`Show-Command` は入門ユーザーが Windows PowerShell を学習するのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-240">`Show-Command` can also help introductory users learn Windows PowerShell.</span></span>

<span data-ttu-id="2dc1a-241">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="2dc1a-241">**What works differently?**</span></span>

<span data-ttu-id="2dc1a-242">`Show-Command` は Windows PowerShell ISE 3.0 の新機能です。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-242">`Show-Command` is new Windows PowerShell ISE 3.0.</span></span>

## <a name="see-also"></a><span data-ttu-id="2dc1a-243">関連項目</span><span class="sxs-lookup"><span data-stu-id="2dc1a-243">See also</span></span>

<span data-ttu-id="2dc1a-244">Windows PowerShell ISE の使い方の詳細については、「[Windows PowerShell Integrated Scripting Environment の探索](../ise/exploring-the-windows-powershell-ise.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dc1a-244">For more information about using Windows PowerShell ISE, see [Exploring the Windows PowerShell Integrated Scripting Environment](../ise/exploring-the-windows-powershell-ise.md).</span></span>
