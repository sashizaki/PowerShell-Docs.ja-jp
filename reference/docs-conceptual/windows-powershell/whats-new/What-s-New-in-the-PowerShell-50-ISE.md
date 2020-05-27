---
ms.date: 09/06/2019
keywords: powershell,コマンドレット
title: PowerShell 5.0 ISE の新機能
ms.openlocfilehash: 1f5d32d583165ff8ead0a95b1c882386cf654326
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809138"
---
# <a name="whats-new-in-the-windows-powershell-50-ise"></a><span data-ttu-id="23a4a-103">Windows PowerShell 5.0 ISE の新機能</span><span class="sxs-lookup"><span data-stu-id="23a4a-103">What's New in the Windows PowerShell 5.0 ISE</span></span>

<span data-ttu-id="23a4a-104">このトピックでは、Windows PowerShell Integrated Scripting Environment (ISE) バージョン 5.0 に導入された新機能と更新された機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="23a4a-104">This topic explains the new and updated features that have been introduced in version 5.0 of the Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

> [!NOTE]
> <span data-ttu-id="23a4a-105">PowerShell ISE は、アクティブな機能開発の対象ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="23a4a-105">The PowerShell ISE is no longer in active feature development.</span></span> <span data-ttu-id="23a4a-106">Windows に付属するコンポーネントとして、セキュリティや優先順位の高いサービスに関する修正プログラムが引き続き公式でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-106">As a shipping component of Windows, it continues to be officially supported for security and high-priority servicing fixes.</span></span>
> <span data-ttu-id="23a4a-107">現在、Windows から ISE が削除される予定はありません。</span><span class="sxs-lookup"><span data-stu-id="23a4a-107">We currently have no plans to remove the ISE from Windows.</span></span>
>
> <span data-ttu-id="23a4a-108">PowerShell v6 以降では、ISE はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="23a4a-108">There is no support for the ISE in PowerShell v6 and beyond.</span></span> <span data-ttu-id="23a4a-109">ISE の代替をお探しのユーザーは、[PowerShell 拡張機能](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell)と共に [Visual Studio Code](https://code.visualstudio.com/) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="23a4a-109">Users looking for replacement for the ISE should use [Visual Studio Code](https://code.visualstudio.com/) with the [PowerShell Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell).</span></span>

## <a name="feature-description"></a><span data-ttu-id="23a4a-110">機能の説明</span><span class="sxs-lookup"><span data-stu-id="23a4a-110">Feature description</span></span>

<span data-ttu-id="23a4a-111">Windows PowerShell ISE は、グラフィカルで直感的な環境でスクリプトおよびモジュールを記述、実行、テストすることができるホスト アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="23a4a-111">The Windows PowerShell ISE is a host application that enables you to write, run, and test scripts and modules in a graphical and intuitive environment.</span></span> <span data-ttu-id="23a4a-112">構文の色分け、タブ補完、視覚的なデバッグ機能、Unicode 準拠、状況依存のヘルプなどの主要な機能により、多彩なスクリプトの操作性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-112">Key features such as syntax-coloring, tab completion, visual debugging, Unicode compliance, and context-sensitive Help provide a rich scripting experience.</span></span>

<span data-ttu-id="23a4a-113">詳細については、「[Windows PowerShell ISE の紹介](../ise/Introducing-the-Windows-PowerShell-ISE.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23a4a-113">For more information, see [Introducing the Windows PowerShell ISE](../ise/Introducing-the-Windows-PowerShell-ISE.md).</span></span>

<span data-ttu-id="23a4a-114">次の表に、Windows PowerShell における Windows PowerShell ISE のこのリリースの新機能と変更された機能を示します。</span><span class="sxs-lookup"><span data-stu-id="23a4a-114">The following table lists the new and changed features for this release of Windows PowerShell ISE in Windows PowerShell.</span></span>

## <a name="intellisense"></a><span data-ttu-id="23a4a-115">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="23a4a-115">IntelliSense</span></span>

> <span data-ttu-id="23a4a-116">ISE 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="23a4a-116">Added in ISE 3.0</span></span>

<span data-ttu-id="23a4a-117">IntelliSense は、Windows PowerShell ISE の一部である自動補完アシスタンス機能です。</span><span class="sxs-lookup"><span data-stu-id="23a4a-117">IntelliSense is an automatic-completion assistance feature that is part of Windows PowerShell ISE.</span></span>
<span data-ttu-id="23a4a-118">IntelliSense により、文字を入力していくと、一致する可能性のあるコマンドレット、パラメーター、パラメーター値、ファイル、またはフォルダーのクリック可能なメニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-118">IntelliSense displays clickable menus of potentially matching cmdlets, parameters, parameter values, files, or folders as you type.</span></span>

<span data-ttu-id="23a4a-119">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-119">**What value does this change add?**</span></span>

<span data-ttu-id="23a4a-120">IntelliSense の追加により、Windows PowerShell ISE を使用してスクリプトを作成する際に、コマンドレットと構文をより簡単に見つけられるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23a4a-120">With the addition of IntelliSense, it's easier to discover cmdlets and syntax when you use Windows PowerShell ISE to create scripts.</span></span> <span data-ttu-id="23a4a-121">また新しいスクリプトの作成中に Windows PowerShell ISE を使用して Windows PowerShell を理解することもできます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-121">You can also use Windows PowerShell ISE to learn Windows PowerShell while you create new scripts.</span></span>

<span data-ttu-id="23a4a-122">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-122">**What works differently?**</span></span>

<span data-ttu-id="23a4a-123">Windows PowerShell ISE でコマンドレットを入力すると、スクロールとクリックが可能なメニューが表示され、適切なコマンドを参照して選択できます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-123">When you type cmdlets in the Windows PowerShell ISE, a scrollable and clickable menu displays, allowing you to browse and select the appropriate commands.</span></span>

## <a name="snippets"></a><span data-ttu-id="23a4a-124">スニペット</span><span class="sxs-lookup"><span data-stu-id="23a4a-124">Snippets</span></span>

> <span data-ttu-id="23a4a-125">ISE 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="23a4a-125">Added in ISE 3.0</span></span>

<span data-ttu-id="23a4a-126">*スニペット* は、Windows PowerShell ISE で作成するスクリプトに挿入できる Windows PowerShell コードの短いセクションです。</span><span class="sxs-lookup"><span data-stu-id="23a4a-126">*Snippets* are short sections of Windows PowerShell code that you can insert into the scripts you create in Windows PowerShell ISE.</span></span> <span data-ttu-id="23a4a-127">Windows PowerShell ISE にはスニペットの既定のセットが付属しています。</span><span class="sxs-lookup"><span data-stu-id="23a4a-127">Windows PowerShell ISE comes with a default set of snippets.</span></span> <span data-ttu-id="23a4a-128">Windows PowerShell ISE での作業中に、`New-Snippet` コマンドレットを使用してスニペットを追加できます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-128">You can add snippets by using the `New-Snippet` cmdlet while working in Windows PowerShell ISE.</span></span>

<span data-ttu-id="23a4a-129">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-129">**What value does this change add?**</span></span>

<span data-ttu-id="23a4a-130">スニペットを使用すると、スクリプトをすばやくアセンブルして作成し、環境を自動化できます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-130">By using snippets, you can quickly assemble and create scripts to automate your environment.</span></span>

<span data-ttu-id="23a4a-131">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-131">**What works differently?**</span></span>

<span data-ttu-id="23a4a-132">Windows PowerShell 3.0 以降でスニペットを使用するには、 **[編集]** メニューで **[スニペットの開始]** をクリックするか、<kbd>Ctrl</kbd>+<kbd>J</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="23a4a-132">To use snippets in Windows PowerShell 3.0 or later, on the **Edit** menu, click **Start Snippets**, or press <kbd>Ctrl</kbd>+<kbd>J</kbd>.</span></span>

## <a name="add-on-tools"></a><span data-ttu-id="23a4a-133">アドオン ツール</span><span class="sxs-lookup"><span data-stu-id="23a4a-133">Add-on tools</span></span>

> <span data-ttu-id="23a4a-134">PowerShell 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="23a4a-134">Added in PowerShell 3.0</span></span>

<span data-ttu-id="23a4a-135">Windows PowerShell ISE で、オブジェクト モデルを使用するアドオン ツールがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23a4a-135">Windows PowerShell ISE now supports add-on tools using the object model.</span></span> <span data-ttu-id="23a4a-136">これらのアドオンは、コンソールに垂直方向または水平方向のウィンドウとして表示される Windows Presentation Foundation (WPF) コントロールです。</span><span class="sxs-lookup"><span data-stu-id="23a4a-136">These add-ons are Windows Presentation Foundation (WPF) controls that are displayed as a vertical or horizontal pane in the console.</span></span> <span data-ttu-id="23a4a-137">1 つのウィンドウ内に複数のアドオン ツールがある場合は、タブ形式のコントロールとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-137">Multiple add-on tools in a pane are displayed as a tabbed control.</span></span> <span data-ttu-id="23a4a-138">また、サード パーティ製のアドオン ツールも追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-138">You can also add or remove add-on tools that are produced by non-Microsoft parties.</span></span> <span data-ttu-id="23a4a-139">詳細については、「[Windows PowerShell ISE スクリプト オブジェクト モデルの目的](../ise/object-model/Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23a4a-139">For more information, see [The Purpose of the Windows PowerShell ISE Scripting Object Model](../ise/object-model/Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md).</span></span>

<span data-ttu-id="23a4a-140">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-140">**What value does this change add?**</span></span>

<span data-ttu-id="23a4a-141">アドオンにより、機能の追加やスクリプト作成エクスペリエンスの向上を実現するツールを使って、Windows PowerShell ISE を拡張およびカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-141">Add-ons allow you to extend and customize Windows PowerShell ISE with tools that add functionality and enhance your scripting experience.</span></span>

<span data-ttu-id="23a4a-142">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-142">**What works differently?**</span></span>

<span data-ttu-id="23a4a-143">Windows PowerShell ISE 3.0 以降には、**Commands** アドオンが付属しています。</span><span class="sxs-lookup"><span data-stu-id="23a4a-143">Windows PowerShell ISE 3.0 and later come with the **Commands** add-on.</span></span> <span data-ttu-id="23a4a-144">**Commands** アドオンを使用すると、コマンドレットを参照し、 **[スクリプト]** ウィンドウと **[コンソール]** ウィンドウで同時にコマンドレットに関するヘルプにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-144">The **Commands** add-on allows you to browse cmdlets, and access help about the cmdlets side-by-side with the **Script** and **Console** Panes.</span></span>

<span data-ttu-id="23a4a-145">追加のアドオンは、 **[アドオン]** メニューの **[アドオン ツール Web サイトを開く]** コマンドを使用して検索することができます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-145">Additional add-ons can be found by using the **Open Add-on Tools Website** command on the **Add-ons** menu.</span></span>

## <a name="restart-manager-and-auto-save"></a><span data-ttu-id="23a4a-146">再起動マネージャーと自動保存</span><span class="sxs-lookup"><span data-stu-id="23a4a-146">Restart manager and auto-save</span></span>

> <span data-ttu-id="23a4a-147">PowerShell 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="23a4a-147">Added in PowerShell 3.0</span></span>

<span data-ttu-id="23a4a-148">Windows PowerShell ISE では、開いているスクリプトを 2 分おきに別の場所に自動的に保存するようになりました。</span><span class="sxs-lookup"><span data-stu-id="23a4a-148">Windows PowerShell ISE now automatically saves your open scripts every two minutes, in a separate location.</span></span> <span data-ttu-id="23a4a-149">予期しないクラッシュまたはリブート後に Windows PowerShell ISE が再起動すると、最後のセッションで開いていたスクリプトが (そのスクリプトが保存されていなかった場合でも) 回復されます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-149">When Windows PowerShell ISE restarts after an unexpected crash or reboot, it recovers scripts that were open in the last session, even if the scripts weren't saved.</span></span>

<span data-ttu-id="23a4a-150">自動保存の間隔を変更するには、コンソール ウィンドウで `$psise.Options.AutoSaveMinuteInterval` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="23a4a-150">To change the automatic saving interval, run the following command in the Console pane: `$psise.Options.AutoSaveMinuteInterval`.</span></span>

<span data-ttu-id="23a4a-151">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-151">**What value does this change add?**</span></span>

<span data-ttu-id="23a4a-152">Windows PowerShell ISE 内での作業で、開いているスクリプトが自動的に保存されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23a4a-152">You can now work within Windows PowerShell ISE knowing that your open scripts are automatically saved.</span></span>

<span data-ttu-id="23a4a-153">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-153">**What works differently?**</span></span>

<span data-ttu-id="23a4a-154">Windows PowerShell ISE 2.0 では、スクリプトは自動的に保存されません。</span><span class="sxs-lookup"><span data-stu-id="23a4a-154">Windows PowerShell ISE 2.0 doesn't save the scripts automatically.</span></span>

## <a name="most-recently-used-list"></a><span data-ttu-id="23a4a-155">最近使用した一覧</span><span class="sxs-lookup"><span data-stu-id="23a4a-155">Most-recently used list</span></span>

> <span data-ttu-id="23a4a-156">PowerShell 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="23a4a-156">Added in PowerShell 3.0</span></span>

<span data-ttu-id="23a4a-157">Windows PowerShell ISE にファイルの最近使用した一覧が用意されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23a4a-157">Windows PowerShell ISE now has a most-recently used list for files.</span></span> <span data-ttu-id="23a4a-158">Windows PowerShell ISE でファイルを開くと、ファイルは **[ファイル]** メニューの最近使用した一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-158">When you open a file in Windows PowerShell ISE, the file is added to the most-recently used list on the **File** menu.</span></span>

<span data-ttu-id="23a4a-159">最近使用した一覧に含まれるファイル数の規定値を変更するには、[コンソール] ウィンドウで、`$psise.Options.MruCount` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="23a4a-159">To change the default number of files in the most-recently used list, run the following command in the Console Pane: `$psise.Options.MruCount`.</span></span>

<span data-ttu-id="23a4a-160">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-160">**What value does this change add?**</span></span>

<span data-ttu-id="23a4a-161">最近使用した一覧を使用して、頻繁に使用されるファイルに簡単にアクセスできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23a4a-161">You can now use the most-recently used list to easily access your frequently used files.</span></span>

<span data-ttu-id="23a4a-162">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-162">**What works differently?**</span></span>

<span data-ttu-id="23a4a-163">Windows PowerShell ISE 2.0 には、最近使用した一覧は用意されていません。</span><span class="sxs-lookup"><span data-stu-id="23a4a-163">Windows PowerShell ISE 2.0 doesn't have a most-recently used list.</span></span>

## <a name="console-pane"></a><span data-ttu-id="23a4a-164">コンソール ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="23a4a-164">Console Pane</span></span>

> <span data-ttu-id="23a4a-165">PowerShell 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="23a4a-165">Added in PowerShell 3.0</span></span>

<span data-ttu-id="23a4a-166">Windows PowerShell ISE の最初のリリースで使用できた、独立したコマンド ウィンドウと出力ウィンドウが 1 つのコンソール ウィンドウに統合されました。</span><span class="sxs-lookup"><span data-stu-id="23a4a-166">The separate Command and Output Panes that were available in the first release of Windows PowerShell ISE have been combined into a single Console Pane.</span></span> <span data-ttu-id="23a4a-167">コンソール ウィンドウの機能と外観は、標準的な Windows PowerShell コンソールと類似していますが、次のような機能強化が行われています。</span><span class="sxs-lookup"><span data-stu-id="23a4a-167">The Console Pane is similar in function and appearance to a typical Windows PowerShell console, but it includes the following enhancements:</span></span>

- <span data-ttu-id="23a4a-168">XML 構文を含む入力テキストの構文の色分け (出力テキストを除く)</span><span class="sxs-lookup"><span data-stu-id="23a4a-168">Syntax coloring for input text (not output text), including XML syntax</span></span>
- <span data-ttu-id="23a4a-169">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="23a4a-169">IntelliSense</span></span>
- <span data-ttu-id="23a4a-170">かっこの一致</span><span class="sxs-lookup"><span data-stu-id="23a4a-170">Brace matching</span></span>
- <span data-ttu-id="23a4a-171">エラー表示</span><span class="sxs-lookup"><span data-stu-id="23a4a-171">Error indication</span></span>
- <span data-ttu-id="23a4a-172">全角 Unicode のサポート</span><span class="sxs-lookup"><span data-stu-id="23a4a-172">Full Unicode support</span></span>
- <span data-ttu-id="23a4a-173"><kbd>F1</kbd> キーによる状況依存のヘルプ</span><span class="sxs-lookup"><span data-stu-id="23a4a-173"><kbd>F1</kbd> context-sensitive help</span></span>
- <span data-ttu-id="23a4a-174"><kbd>Ctrl</kbd>+<kbd>F1</kbd> キーによる状況依存の Show-Command</span><span class="sxs-lookup"><span data-stu-id="23a4a-174"><kbd>Ctrl</kbd>+<kbd>F1</kbd> context-sensitive Show-Command</span></span>
- <span data-ttu-id="23a4a-175">複雑なスクリプトおよび右から左への記述のサポート</span><span class="sxs-lookup"><span data-stu-id="23a4a-175">Complex script and right-to-left support</span></span>
- <span data-ttu-id="23a4a-176">フォントのサポート</span><span class="sxs-lookup"><span data-stu-id="23a4a-176">Font support</span></span>
- <span data-ttu-id="23a4a-177">Zoom</span><span class="sxs-lookup"><span data-stu-id="23a4a-177">Zoom</span></span>
- <span data-ttu-id="23a4a-178">行選択モードとブロック選択モード</span><span class="sxs-lookup"><span data-stu-id="23a4a-178">Line-select and block-select modes</span></span>
- <span data-ttu-id="23a4a-179"><kbd>上方向</kbd>キーを押して履歴をコンソールに表示したときにコマンド ラインに入力されたコンテンツを保存する機能</span><span class="sxs-lookup"><span data-stu-id="23a4a-179">Preservation of typed content at the command line when you press the <kbd>UpArrow</kbd> to view history in the console</span></span>

<span data-ttu-id="23a4a-180">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-180">**What value does this change add?**</span></span>

<span data-ttu-id="23a4a-181">これらのコンソール ウィンドウの変更を追加したことにより、コンソール インターフェイスとの一貫性がより向上したスクリプトの操作性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-181">The addition of these Console Pane changes provides a scripting experience that is more consistent with the console interface.</span></span>

<span data-ttu-id="23a4a-182">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-182">**What works differently?**</span></span>

<span data-ttu-id="23a4a-183">Windows PowerShell ISE 2.0 では、コマンド ウィンドウと出力ウィンドウは個別に表示されます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-183">Windows PowerShell ISE 2.0 has separate Command and Output Panes.</span></span>

## <a name="command-line-switches"></a><span data-ttu-id="23a4a-184">コマンド ライン スイッチ</span><span class="sxs-lookup"><span data-stu-id="23a4a-184">Command-line switches</span></span>

> <span data-ttu-id="23a4a-185">PowerShell 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="23a4a-185">Added in PowerShell 3.0</span></span>

<span data-ttu-id="23a4a-186">コマンド ライン (「**Powershell_ise.exe**」を入力) から Windows PowerShell ISE を起動する場合、次の新しいコマンド ライン スイッチを追加できます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-186">If you start Windows PowerShell ISE from the command line (by typing **powershell_ise.exe**), you can add the following new command-line switches.</span></span>

- <span data-ttu-id="23a4a-187">`-NoProfile`:`$profile` を実行せずに Windows PowerShell ISE を起動する</span><span class="sxs-lookup"><span data-stu-id="23a4a-187">`-NoProfile`: Starts Windows PowerShell ISE without running `$profile`</span></span>
- <span data-ttu-id="23a4a-188">`-Help`:ヘルプ ウィンドウを表示する</span><span class="sxs-lookup"><span data-stu-id="23a4a-188">`-Help`: Displays a Help window</span></span>
- <span data-ttu-id="23a4a-189">`-mta`:マルチスレッド アパートメント モードで Windows PowerShell ISE を起動する。</span><span class="sxs-lookup"><span data-stu-id="23a4a-189">`-mta`: Starts Windows PowerShell ISE in multithreaded apartment mode.</span></span> <span data-ttu-id="23a4a-190">Windows PowerShell ISE の既定の操作モードは、シングル スレッド アパートメント モード、つまり `-sta` です。</span><span class="sxs-lookup"><span data-stu-id="23a4a-190">The default operation mode for Windows PowerShell ISE is single-threaded apartment mode, or `-sta`.</span></span>

<span data-ttu-id="23a4a-191">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-191">**What value does this change add?**</span></span>

<span data-ttu-id="23a4a-192">これらのコマンド ライン スイッチを追加すると、Windows PowerShell ISE が動作する環境を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-192">The addition of these command-line switches allows you to control the environment in which the Windows PowerShell ISE runs.</span></span>

<span data-ttu-id="23a4a-193">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-193">**What works differently?**</span></span>

<span data-ttu-id="23a4a-194">Windows PowerShell ISE 2.0 では、これらのコマンド ライン スイッチは認識されません。</span><span class="sxs-lookup"><span data-stu-id="23a4a-194">Windows PowerShell ISE 2.0 doesn't recognize these command-line switches.</span></span>

## <a name="new-editor-features"></a><span data-ttu-id="23a4a-195">エディターの新機能</span><span class="sxs-lookup"><span data-stu-id="23a4a-195">New editor features</span></span>

> <span data-ttu-id="23a4a-196">PowerShell 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="23a4a-196">Added in PowerShell 3.0</span></span>

<span data-ttu-id="23a4a-197">その他の Windows PowerShell ISE 編集機能として、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="23a4a-197">Other Windows PowerShell ISE editing features include:</span></span>

- <span data-ttu-id="23a4a-198">**XML 構文の色分け** - Windows PowerShell ISE では、Windows PowerShell 構文を色分けする方法と同じ方法で XML 構文が色分けされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23a4a-198">**XML syntax coloring** - Windows PowerShell ISE now colors XML syntax in the same way as it colors Windows PowerShell syntax.</span></span>
- <span data-ttu-id="23a4a-199">**かっこの照合** - Windows PowerShell ISE にはかっこの照合と強調表示を行う機能が含まれ、次のように使用できます。たとえば、始めかっこを選択している場合、 **[一致する項目に移動]** コマンドまたは <kbd>Ctrl</kbd>+<kbd>]</kbd> キーを使用すると、終わりかっこが見つかります。</span><span class="sxs-lookup"><span data-stu-id="23a4a-199">**Brace matching** - Windows PowerShell ISE includes brace matching and highlighting, and can be used in the following ways: (for example, using the **Go to Match** command or <kbd>Ctrl</kbd>+<kbd>]</kbd> locates the closing brace, if you have an opening brace selected).</span></span>
- <span data-ttu-id="23a4a-200">**アウトライン表示**。スクリプト ウィンドウでは、アウトラインがサポートされます。これにより、左余白のプラス記号またはマイナス記号をクリックすると、コードのセクションを折りたたんだり展開したりできます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-200">**Outline view** The Script Pane supports outlining, which allows collapsing or expanding sections of code by clicking plus or minus signs in the left margin.</span></span> <span data-ttu-id="23a4a-201">かっこ、または `#region` タグと `#endregion` タグを使用して、折りたたみ可能なセクションの先頭と末尾をマークすることができます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-201">You can use braces or the `#region` and `#endregion` tags to mark the beginning or end of a collapsible section.</span></span> <span data-ttu-id="23a4a-202">すべての領域を展開する、または折りたたむには、<kbd>Ctrl</kbd>+<kbd>M</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="23a4a-202">To expand or collapse all regions, press <kbd>Ctrl</kbd>+<kbd>M</kbd>.</span></span>
- <span data-ttu-id="23a4a-203">**ドラッグ アンド ドロップ テキスト編集** - Windows PowerShell ISE で、ドラッグ アンド ドロップによるテキスト編集がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23a4a-203">**Drag and drop text editing** - Windows PowerShell ISE now supports drag and drop text editing.</span></span> <span data-ttu-id="23a4a-204">任意のテキストのブロックを選択し、そのテキストをドラッグしてエディターまたはコンソール内の別の場所に移動できます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-204">You can select any block of text and drag that text to another location in the editor or the console to move the text.</span></span> <span data-ttu-id="23a4a-205"><kbd>Ctrl</kbd> キーを押したまま選択したテキストをドラッグし、マウス ボタンを放すと、テキストが新しい場所にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-205">If you hold down the <kbd>Ctrl</kbd> key while you drag the selected text, when you release the mouse button the text is copied to the new location.</span></span> <span data-ttu-id="23a4a-206">このバージョンの Windows PowerShell ISE では、ファイルを Windows PowerShell ISE 上にドラッグ アンド ドロップすると、Windows PowerShell ISE でファイルが開かれます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-206">In this version of Windows PowerShell ISE, when you drag and drop files onto Windows PowerShell ISE, Windows PowerShell ISE opens the file.</span></span>
- <span data-ttu-id="23a4a-207">**解析エラーの表示** - 解析エラーは赤い下線で示されます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-207">**Parse error display** - Parse errors are indicated with red underlines.</span></span> <span data-ttu-id="23a4a-208">示されたエラーをポイントすると、コード内で見つかった問題がヒントのテキストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-208">When you hover over an indicated error, tooltip text displays the problem that was found in the code.</span></span>
- <span data-ttu-id="23a4a-209">**ズーム** - ズーム スライダー (Windows PowerShell ISE ウィンドウの右下隅にあります) を使用するか、コンソール ウィンドウで `$psise.options.Zoom` コマンドを入力することで、コンソールのコンテンツのズーム倍率を設定できます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-209">**Zoom** - The zoom percentage of the console's content can be set by using the zoom slider (in the lower right corner of Windows PowerShell ISE window), or by entering the command `$psise.options.Zoom` in the Console Pane.</span></span>
- <span data-ttu-id="23a4a-210">**リッチ テキストのコピーと貼り付け** - Windows PowerShell ISE でクリップボードにコピーすると、元の選択範囲のフォント、サイズ、および色の情報が保存されます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-210">**Rich text copy and paste** - Copying to the clipboard in Windows PowerShell ISE preserves the font, size, and color information of the original selection.</span></span>
- <span data-ttu-id="23a4a-211">**ブロック選択** - テキストのブロックを選択するには、<kbd>Alt</kbd> キーを押したままマウスでスクリプト ウィンドウ内のテキストを選択するか、<kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>方向</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="23a4a-211">**Block selection** - You can select a block of text by holding down the <kbd>ALT</kbd> key while selecting text in the Script Pane with your mouse, or by pressing <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>Arrow</kbd>.</span></span>

<span data-ttu-id="23a4a-212">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-212">**What value does this change add?**</span></span>

<span data-ttu-id="23a4a-213">追加の編集機能によって、より一貫性のある強力な編集環境が提供されます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-213">The additional editing features provide a more consistent and powerful editing environment.</span></span>

<span data-ttu-id="23a4a-214">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-214">**What works differently?**</span></span>

<span data-ttu-id="23a4a-215">これらの編集の拡張機能は Windows PowerShell ISE 2.0 にはなかった機能です。</span><span class="sxs-lookup"><span data-stu-id="23a4a-215">These editing enhancements weren't present in Windows PowerShell ISE 2.0.</span></span>

## <a name="new-help-viewer-window"></a><span data-ttu-id="23a4a-216">新しいヘルプ ビューアー ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="23a4a-216">New Help viewer window</span></span>

> <span data-ttu-id="23a4a-217">PowerShell 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="23a4a-217">Added in PowerShell 3.0</span></span>

<span data-ttu-id="23a4a-218">カーソルがコマンドレット内にあるかコマンドレットの一部を強調表示しているときに <kbd>F1</kbd> キーを押すと、強調表示されたコマンドレットに関する状況依存のヘルプが新しいヘルプ ビューアーで開かれます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-218">If you press <kbd>F1</kbd> when your cursor is in a cmdlet, or you have part of a cmdlet highlighted, the new Help viewer opens context-sensitive Help about the highlighted cmdlet.</span></span> <span data-ttu-id="23a4a-219">Windows PowerShell の **About** ヘルプを表示するには、コンソール ウィンドウで「`operators`」と入力し、<kbd>F1</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="23a4a-219">To display Windows PowerShell **About** help, type `operators` in the console pane, and then press <kbd>F1</kbd>.</span></span>

<span data-ttu-id="23a4a-220">この機能を使用する前に、Microsoft Web サイトから Windows PowerShell のヘルプ トピックの最新バージョンをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="23a4a-220">Before you use this feature, download the most current version of Windows PowerShell Help topics from the Microsoft website.</span></span> <span data-ttu-id="23a4a-221">ヘルプ トピックをダウンロードする最も簡単な方法は、管理者として Windows PowerShell を実行中に、コンソール ウィンドウで `Update-Help` コマンドレットを実行することです。</span><span class="sxs-lookup"><span data-stu-id="23a4a-221">The simplest method for downloading the Help topics is to run the `Update-Help` cmdlet in the Console Pane when running Windows PowerShell ISE as administrator.</span></span>

<span data-ttu-id="23a4a-222"><kbd>F1</kbd> キーを押したときにヘルプを検索する場所を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-222">You can alter where the <kbd>F1</kbd> key looks for Help.</span></span> <span data-ttu-id="23a4a-223">**[ツール]** / **[オプション]** メニューで、 **[全般設定]** タブの **[その他の設定]** の下で、 **[オンライン コンテンツの代わりにローカル ヘルプ コンテンツを使用する]** ボックスをオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-223">In the **Tools**/**Options** menu, on the **General Settings** tab, under **Other Settings**, you can set or clear the checkbox **Use local help content instead of online content**.</span></span> <span data-ttu-id="23a4a-224">オンにした場合、クライアントでは、モジュール フォルダー内にあるダウンロード済みのヘルプから、コマンドレットのヘルプが検索されます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-224">When checked, the client looks for the cmdlet Help in the downloaded Help found in the modules folder.</span></span> <span data-ttu-id="23a4a-225">チェックボックスがオフの場合、クライアントではヘルプをオンラインで検索します。</span><span class="sxs-lookup"><span data-stu-id="23a4a-225">If the checkbox is cleared, the client looks for help online.</span></span>

<span data-ttu-id="23a4a-226">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-226">**What value does this change add?**</span></span>

<span data-ttu-id="23a4a-227">現在のコマンドレットまたはスクリプトを離れることなく状況依存のヘルプを使用することで、統合された学習を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-227">Context-sensitive Help without leaving your current cmdlet or script provides an integrated learning experience.</span></span>

<span data-ttu-id="23a4a-228">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-228">**What works differently?**</span></span>

<span data-ttu-id="23a4a-229">以前のバージョンの Windows PowerShell ISE では、<kbd>F1</kbd> キーを押すと、ローカル コンピューター上のヘルプ ファイルが開きました。</span><span class="sxs-lookup"><span data-stu-id="23a4a-229">Pressing <kbd>F1</kbd> in previous versions of Windows PowerShell ISE opened the help file on the local computer.</span></span> <span data-ttu-id="23a4a-230">Windows PowerShell ISE 3.0 以降では、検索と構成が可能なコマンドレットのヘルプを含むウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-230">In Windows PowerShell ISE 3.0 and later, a window opens that contains the help for the cmdlet that is searchable and configurable.</span></span> <span data-ttu-id="23a4a-231">このヘルプ エクスペリエンスは Windows PowerShell ISE 3.0 の新機能であり、更新可能なヘルプは Windows PowerShell 3.0 の新機能です。</span><span class="sxs-lookup"><span data-stu-id="23a4a-231">This Help experience is new for Windows PowerShell ISE 3.0, and Updatable Help is new for Windows PowerShell 3.0.</span></span>

## <a name="show-command-cmdlet"></a><span data-ttu-id="23a4a-232">Show-Command コマンドレット</span><span class="sxs-lookup"><span data-stu-id="23a4a-232">Show-Command cmdlet</span></span>

> <span data-ttu-id="23a4a-233">PowerShell 3.0 に追加</span><span class="sxs-lookup"><span data-stu-id="23a4a-233">Added in PowerShell 3.0</span></span>

<span data-ttu-id="23a4a-234">`Show-Command` コマンドレットを使用すると、グラフィカルなフォームに情報を入力してコマンドレットや関数を構成または実行できます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-234">The `Show-Command` cmdlet enables you to compose or run a cmdlet or function by filling in a graphical form.</span></span> <span data-ttu-id="23a4a-235">フォームを使用すると、グラフィカルな環境でユーザーが Windows PowerShell で作業できます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-235">The form lets users work with Windows PowerShell in a graphical environment.</span></span>
<span data-ttu-id="23a4a-236">また、上級のスクリプト作成者は `Show-Command` を使用して、簡単な Windows PowerShell ベースの GUI を作成できます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-236">`Show-Command` also enables advanced scripters to create a quick Windows PowerShell-based GUI.</span></span>

<span data-ttu-id="23a4a-237">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-237">**What value does this change add?**</span></span>

<span data-ttu-id="23a4a-238">Windows PowerShell スクリプトで `Show-Command` を使用すると、ユーザーが使い慣れたグラフィカルな環境を提供できます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-238">By using `Show-Command` in your Windows PowerShell scripts, you can provide your users with the graphical environment with which they're familiar.</span></span> <span data-ttu-id="23a4a-239">また、`Show-Command` は入門ユーザーが Windows PowerShell を学習するのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="23a4a-239">`Show-Command` can also help introductory users learn Windows PowerShell.</span></span>

<span data-ttu-id="23a4a-240">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="23a4a-240">**What works differently?**</span></span>

<span data-ttu-id="23a4a-241">`Show-Command` は Windows PowerShell ISE 3.0 の新機能です。</span><span class="sxs-lookup"><span data-stu-id="23a4a-241">`Show-Command` is new Windows PowerShell ISE 3.0.</span></span>

## <a name="see-also"></a><span data-ttu-id="23a4a-242">関連項目</span><span class="sxs-lookup"><span data-stu-id="23a4a-242">See also</span></span>

<span data-ttu-id="23a4a-243">Windows PowerShell ISE の使い方の詳細については、「[Windows PowerShell Integrated Scripting Environment の探索](../ise/exploring-the-windows-powershell-ise.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23a4a-243">For more information about using Windows PowerShell ISE, see [Exploring the Windows PowerShell Integrated Scripting Environment](../ise/exploring-the-windows-powershell-ise.md).</span></span>
