---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "PowerShell 50 ISE の新機能"
ms.assetid: 38648d47-7c27-4b37-a40e-ad29948519c2
ms.openlocfilehash: e772c31ae407e73a96364ffedf98057760037836
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="what39s-new-in-the-windows-powershell-ise"></a><span data-ttu-id="97e03-103">Windows PowerShell ISE の新機能</span><span class="sxs-lookup"><span data-stu-id="97e03-103">What&#39;s New in the Windows PowerShell ISE</span></span>
<span data-ttu-id="97e03-104">このトピックでは、各バージョンの Windows PowerShell® Integrated Scripting Environment (ISE) に導入された新機能と更新された機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="97e03-104">This topic explains the new and updated features that have been introduced in versions of Windows PowerShell ® Integrated Scripting Environment (ISE).</span></span>

## <span data-ttu-id="97e03-105"><a name="overview"></a>機能の説明</span><span class="sxs-lookup"><span data-stu-id="97e03-105"><a name="overview"></a>Feature description</span></span>
<span data-ttu-id="97e03-106">Windows PowerShell ISE は、グラフィカルで直感的な環境でスクリプトおよびモジュールを記述、実行、テストすることができるホスト アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="97e03-106">The Windows PowerShell ISE is a host application that enables you to write, run, and test scripts and modules in a graphical and intuitive environment.</span></span> <span data-ttu-id="97e03-107">構文の色分け、タブ補完、視覚的なデバッグ機能、Unicode 準拠、状況依存のヘルプなどの主要な機能により、多彩なスクリプトの操作性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="97e03-107">Key features such as syntax-coloring, tab completion, visual debugging, Unicode compliance, and context-sensitive Help provide a rich scripting experience.</span></span>

<span data-ttu-id="97e03-108">Windows PowerShell ISE の概要については、[Windows PowerShell Integrated Scripting Environment の概要](https://technet.microsoft.com/en-us/library/3c1892c2-bf84-4cb6-af26-1f453be9e671)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="97e03-108">For an overview of Windows PowerShell ISE, see [Windows PowerShell Integrated Scripting Environment overview](https://technet.microsoft.com/en-us/library/3c1892c2-bf84-4cb6-af26-1f453be9e671).</span></span>

## <span data-ttu-id="97e03-109"><a name="versions"></a>Windows PowerShell ISE の新機能と変更された機能</span><span class="sxs-lookup"><span data-stu-id="97e03-109"><a name="versions"></a>New and changed functionality in Windows PowerShell ISE</span></span>
<span data-ttu-id="97e03-110">次の表に、Windows PowerShell における Windows PowerShell ISE のこのリリースの新機能と変更された機能を示します。</span><span class="sxs-lookup"><span data-stu-id="97e03-110">The following table lists the new and changed features for this release of Windows PowerShell ISE in Windows PowerShell.</span></span>

|<span data-ttu-id="97e03-111">機能</span><span class="sxs-lookup"><span data-stu-id="97e03-111">Feature/functionality</span></span>|<span data-ttu-id="97e03-112">Windows PowerShell ISE 4.0</span><span class="sxs-lookup"><span data-stu-id="97e03-112">Windows PowerShell ISE 4.0</span></span>|<span data-ttu-id="97e03-113">Windows PowerShell ISE 3.0</span><span class="sxs-lookup"><span data-stu-id="97e03-113">Windows PowerShell ISE 3.0</span></span>|<span data-ttu-id="97e03-114">Windows PowerShell ISE 2.0</span><span class="sxs-lookup"><span data-stu-id="97e03-114">Windows PowerShell ISE 2.0</span></span>|
|--------------------------|-----------------------------------------------|-----------------------------------------------|-----------------------------------------------|
|<span data-ttu-id="97e03-115">**[IntelliSense](#BKMK_Intellisense)**</span><span class="sxs-lookup"><span data-stu-id="97e03-115">**[IntelliSense](#BKMK_Intellisense)**</span></span>|<span data-ttu-id="97e03-116">X</span><span class="sxs-lookup"><span data-stu-id="97e03-116">X</span></span>|<span data-ttu-id="97e03-117">X</span><span class="sxs-lookup"><span data-stu-id="97e03-117">X</span></span>||
|<span data-ttu-id="97e03-118">**[スニペット](#bkmk_snippets)**</span><span class="sxs-lookup"><span data-stu-id="97e03-118">**[Snippets](#bkmk_snippets)**</span></span>|<span data-ttu-id="97e03-119">X</span><span class="sxs-lookup"><span data-stu-id="97e03-119">X</span></span>|<span data-ttu-id="97e03-120">X</span><span class="sxs-lookup"><span data-stu-id="97e03-120">X</span></span>||
|<span data-ttu-id="97e03-121">**[アドオン ツール](#BKMK_AddOnTools)**</span><span class="sxs-lookup"><span data-stu-id="97e03-121">**[Add-on Tools](#BKMK_AddOnTools)**</span></span>|<span data-ttu-id="97e03-122">X</span><span class="sxs-lookup"><span data-stu-id="97e03-122">X</span></span>|<span data-ttu-id="97e03-123">X</span><span class="sxs-lookup"><span data-stu-id="97e03-123">X</span></span>||
|<span data-ttu-id="97e03-124">**[再起動マネージャーと自動保存](#BKMK_RestartMgr)**</span><span class="sxs-lookup"><span data-stu-id="97e03-124">**[Restart Manager and Auto-save](#BKMK_RestartMgr)**</span></span>|<span data-ttu-id="97e03-125">X</span><span class="sxs-lookup"><span data-stu-id="97e03-125">X</span></span>|<span data-ttu-id="97e03-126">X</span><span class="sxs-lookup"><span data-stu-id="97e03-126">X</span></span>||
|<span data-ttu-id="97e03-127">**[コンソール ウィンドウ](#BKMK_ConsolePane)**</span><span class="sxs-lookup"><span data-stu-id="97e03-127">**[Console Pane](#BKMK_ConsolePane)**</span></span>|<span data-ttu-id="97e03-128">X</span><span class="sxs-lookup"><span data-stu-id="97e03-128">X</span></span>|<span data-ttu-id="97e03-129">X</span><span class="sxs-lookup"><span data-stu-id="97e03-129">X</span></span>||
|<span data-ttu-id="97e03-130">**[最近使用した一覧](#BKMK_MRU)**</span><span class="sxs-lookup"><span data-stu-id="97e03-130">**[Most-recently used list](#BKMK_MRU)**</span></span>|<span data-ttu-id="97e03-131">X</span><span class="sxs-lookup"><span data-stu-id="97e03-131">X</span></span>|<span data-ttu-id="97e03-132">X</span><span class="sxs-lookup"><span data-stu-id="97e03-132">X</span></span>||
|<span data-ttu-id="97e03-133">**[コマンド ライン スイッチ](#BKMK_CommandLine)**</span><span class="sxs-lookup"><span data-stu-id="97e03-133">**[Command-line switches](#BKMK_CommandLine)**</span></span>|<span data-ttu-id="97e03-134">X</span><span class="sxs-lookup"><span data-stu-id="97e03-134">X</span></span>|<span data-ttu-id="97e03-135">X</span><span class="sxs-lookup"><span data-stu-id="97e03-135">X</span></span>||
|<span data-ttu-id="97e03-136">**[エディターの新機能](#BKMK_NewEditorFeatures)**</span><span class="sxs-lookup"><span data-stu-id="97e03-136">**[New editor features](#BKMK_NewEditorFeatures)**</span></span>|<span data-ttu-id="97e03-137">X</span><span class="sxs-lookup"><span data-stu-id="97e03-137">X</span></span>|<span data-ttu-id="97e03-138">X</span><span class="sxs-lookup"><span data-stu-id="97e03-138">X</span></span>||
|<span data-ttu-id="97e03-139">**[新しいヘルプ ビューアー ウィンドウ](#BKMK_NewHelpViewer)**</span><span class="sxs-lookup"><span data-stu-id="97e03-139">**[New Help viewer window](#BKMK_NewHelpViewer)**</span></span>|<span data-ttu-id="97e03-140">X</span><span class="sxs-lookup"><span data-stu-id="97e03-140">X</span></span>|<span data-ttu-id="97e03-141">X</span><span class="sxs-lookup"><span data-stu-id="97e03-141">X</span></span>||
|<span data-ttu-id="97e03-142">**[Show-Command コマンドレット](#BKMK_ShowCommand)**</span><span class="sxs-lookup"><span data-stu-id="97e03-142">**[Show-Command cmdlet](#BKMK_ShowCommand)**</span></span>|<span data-ttu-id="97e03-143">X</span><span class="sxs-lookup"><span data-stu-id="97e03-143">X</span></span>|<span data-ttu-id="97e03-144">X</span><span class="sxs-lookup"><span data-stu-id="97e03-144">X</span></span>||

### <span data-ttu-id="97e03-145"><a name="BKMK_Intellisense"></a>IntelliSense</span><span class="sxs-lookup"><span data-stu-id="97e03-145"><a name="BKMK_Intellisense"></a>IntelliSense</span></span>
<span data-ttu-id="97e03-146">**ISE 3.0 に追加**</span><span class="sxs-lookup"><span data-stu-id="97e03-146">**Added in ISE 3.0**</span></span>

<span data-ttu-id="97e03-147">IntelliSense は、Windows PowerShell ISE の一部である自動補完アシスタンス機能です。</span><span class="sxs-lookup"><span data-stu-id="97e03-147">IntelliSense is an automatic-completion assistance feature that is part of Windows PowerShell ISE.</span></span> <span data-ttu-id="97e03-148">IntelliSense により、文字を入力していくと、一致する可能性のあるコマンドレット、パラメーター、パラメーター値、ファイル、またはフォルダーのクリック可能なメニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97e03-148">IntelliSense displays clickable menus of potentially matching cmdlets, parameters, parameter values, files, or folders as you type.</span></span>

<span data-ttu-id="97e03-149">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="97e03-149">**What value does this change add?**</span></span>

<span data-ttu-id="97e03-150">IntelliSense の追加により、Windows PowerShell ISE を使用してスクリプトを作成する際に、コマンドレットと構文をより簡単に見つけられるようになりました。</span><span class="sxs-lookup"><span data-stu-id="97e03-150">With the addition of IntelliSense, it is easier to discover cmdlets and syntax when you use Windows PowerShell ISE to create scripts.</span></span> <span data-ttu-id="97e03-151">また新しいスクリプトの作成中に Windows PowerShell ISE を使用して Windows PowerShell を理解することもできます。</span><span class="sxs-lookup"><span data-stu-id="97e03-151">You can also use Windows PowerShell ISE to learn Windows PowerShell while you create new scripts.</span></span>

<span data-ttu-id="97e03-152">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="97e03-152">**What works differently?**</span></span>

<span data-ttu-id="97e03-153">Windows PowerShell ISE 3.0 以降でコマンドレットを入力すると、スクロールとクリックが可能なメニューが表示され、適切なコマンドを参照して選択できます。</span><span class="sxs-lookup"><span data-stu-id="97e03-153">When you type cmdlets in the Windows PowerShell ISE 3.0 or later, a scrollable and clickable menu displays, allowing you to browse and select the appropriate commands.</span></span>

### <span data-ttu-id="97e03-154"><a name="BKMK_Snippets"></a>スニペット</span><span class="sxs-lookup"><span data-stu-id="97e03-154"><a name="BKMK_Snippets"></a>Snippets</span></span>
<span data-ttu-id="97e03-155">**ISE 3.0 に追加**</span><span class="sxs-lookup"><span data-stu-id="97e03-155">**Added in ISE 3.0**</span></span>

<span data-ttu-id="97e03-156">*スニペット* は、Windows PowerShell ISE で作成するスクリプトに挿入できる Windows PowerShell コードの短いセクションです。</span><span class="sxs-lookup"><span data-stu-id="97e03-156">*Snippets* are short sections of Windows PowerShell code that you can insert into the scripts you create in Windows PowerShell ISE.</span></span> <span data-ttu-id="97e03-157">Windows PowerShell ISE にはスニペットの既定のセットが付属しています。</span><span class="sxs-lookup"><span data-stu-id="97e03-157">Windows PowerShell ISE comes with a default set of snippets.</span></span> <span data-ttu-id="97e03-158">Windows PowerShell ISE での作業中に、**New-Snippet** コマンドレットを使用してスニペットを追加できます。</span><span class="sxs-lookup"><span data-stu-id="97e03-158">You can add snippets by using the **New-Snippet** cmdlet while working in Windows PowerShell ISE.</span></span>

<span data-ttu-id="97e03-159">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="97e03-159">**What value does this change add?**</span></span>

<span data-ttu-id="97e03-160">スニペットを使用すると、スクリプトをすばやくアセンブルして作成し、環境を自動化できます。</span><span class="sxs-lookup"><span data-stu-id="97e03-160">By using snippets, you can quickly assemble and create scripts to automate your environment.</span></span>

<span data-ttu-id="97e03-161">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="97e03-161">**What works differently?**</span></span>

<span data-ttu-id="97e03-162">Windows PowerShell 3.0 以降でスニペットを使用するには、**[編集]** メニューで **[スニペットの開始]** をクリックするか、**[Ctrl-J]** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="97e03-162">To use snippets in Windows PowerShell 3.0 or later, on the **Edit** menu, click **Start Snippets**, or press **Ctrl-J**.</span></span>

### <span data-ttu-id="97e03-163"><a name="BKMK_AddOnTools"></a>アドオン ツール</span><span class="sxs-lookup"><span data-stu-id="97e03-163"><a name="BKMK_AddOnTools"></a>Add-on tools</span></span>
<span data-ttu-id="97e03-164">**PowerShell 3.0 に追加**</span><span class="sxs-lookup"><span data-stu-id="97e03-164">**Added in PowerShell 3.0**</span></span>

<span data-ttu-id="97e03-165">Windows PowerShell ISE では、アドオン ツールをサポートしています。アドオン ツールとは、オブジェクト モデルを使用して追加される Windows Presentation Foundation (WPF) コントロールです。</span><span class="sxs-lookup"><span data-stu-id="97e03-165">Windows PowerShell ISE now supports add-on tools, which are Windows Presentation Foundation (WPF) controls that are added by using the object model.</span></span> <span data-ttu-id="97e03-166">アドオン ツールは、垂直方向のウィンドウまたは水平方向のウィンドウとしてコンソール内に表示できます。</span><span class="sxs-lookup"><span data-stu-id="97e03-166">Add-on tools can be displayed as a vertical or horizontal pane in the console.</span></span> <span data-ttu-id="97e03-167">1 つのウィンドウ内に複数のアドオン ツールがある場合は、タブ形式のコントロールとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="97e03-167">Multiple add-on tools in a pane are displayed as a tabbed control.</span></span> <span data-ttu-id="97e03-168">また、サード パーティ製のアドオン ツールも追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="97e03-168">You can also add or remove add-on tools that are produced by non-Microsoft parties.</span></span> <span data-ttu-id="97e03-169">アドオン ツールのインポート方法または削除方法の詳細については、「[Windows PowerShell ISE の操作](http://technet.microsoft.com/library/cc732148.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97e03-169">For more information about how to import or remove add-on tools, see [Windows PowerShell ISE Operations](http://technet.microsoft.com/library/cc732148.aspx).</span></span>

<span data-ttu-id="97e03-170">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="97e03-170">**What value does this change add?**</span></span>

<span data-ttu-id="97e03-171">アドオンを使用すると、スクリプトの操作性を強化する、または機能を Windows PowerShell ISE に追加できるツールを使用して、Windows PowerShell ISE の拡張とカスタマイズができます。</span><span class="sxs-lookup"><span data-stu-id="97e03-171">Add-ons allow you to extend and customize Windows PowerShell ISE with tools that can enhance your scripting experience or add functionality to Windows PowerShell ISE.</span></span>

<span data-ttu-id="97e03-172">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="97e03-172">**What works differently?**</span></span>

<span data-ttu-id="97e03-173">Windows PowerShell ISE 3.0 以降には、**Commands** アドオンが付属しています。</span><span class="sxs-lookup"><span data-stu-id="97e03-173">Windows PowerShell ISE 3.0 and later come with the **Commands** add-on.</span></span> <span data-ttu-id="97e03-174">**Commands** アドオンを使用すると、コマンドレットを参照し、**[スクリプト]** ウィンドウと **[コンソール]** ウィンドウで同時にコマンドレットに関するヘルプにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="97e03-174">The **Commands** add-on allows you to browse cmdlets, and access help about the cmdlets side-by-side with the **Script** and **Console** Panes.</span></span>

<span data-ttu-id="97e03-175">追加のアドオンは、**[アドオン]** メニューの **[アドオン ツール Web サイトを開く]** コマンドを使用して検索することができます。</span><span class="sxs-lookup"><span data-stu-id="97e03-175">Additional add-ons can be found by using the **Open Add-on Tools Website** command on the **Add-ons** menu.</span></span>

### <span data-ttu-id="97e03-176"><a name="BKMK_RestartMgr"></a>再起動マネージャーと自動保存</span><span class="sxs-lookup"><span data-stu-id="97e03-176"><a name="BKMK_RestartMgr"></a>Restart manager and auto-save</span></span>
<span data-ttu-id="97e03-177">**PowerShell 3.0 に追加**</span><span class="sxs-lookup"><span data-stu-id="97e03-177">**Added in PowerShell 3.0**</span></span>

<span data-ttu-id="97e03-178">Windows PowerShell ISE では、開いているスクリプトを 2 分おきに別の場所に自動的に保存するようになりました。</span><span class="sxs-lookup"><span data-stu-id="97e03-178">Windows PowerShell ISE now automatically saves your open scripts every two minutes, in a separate location.</span></span>  <span data-ttu-id="97e03-179">Windows PowerShell ISE が動作しなくなった場合またはオペレーティング システムが再起動された場合に、Windows PowerShell ISE を再起動すると、最後のセッションで開いていたスクリプトは、保存されていなかった場合でも回復されます。</span><span class="sxs-lookup"><span data-stu-id="97e03-179">If Windows PowerShell ISE stops working, or if the operating system is restarted, after Windows PowerShell ISE restarts, it recovers scripts that were open in the last session, even if the scripts were not saved.</span></span>

<span data-ttu-id="97e03-180">自動保存の間隔を変更するには、コンソール ウィンドウでコマンド **$psise.Options.AutoSaveMinuteInterval** を実行します。</span><span class="sxs-lookup"><span data-stu-id="97e03-180">To change the automatic saving interval, run the following command in the Console pane: **$psise.Options.AutoSaveMinuteInterval**.</span></span>

<span data-ttu-id="97e03-181">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="97e03-181">**What value does this change add?**</span></span>

<span data-ttu-id="97e03-182">Windows PowerShell ISE 内での作業で、予期しない再起動が発生した場合、開いているスクリプトが自動的に保存されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="97e03-182">You can now work within Windows PowerShell ISE knowing that your open scripts are automatically saved in the event of an unexpected restart.</span></span>

<span data-ttu-id="97e03-183">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="97e03-183">**What works differently?**</span></span>

<span data-ttu-id="97e03-184">Windows PowerShell ISE 2.0 では、再起動が発生した場合、スクリプトは自動的に保存されません。</span><span class="sxs-lookup"><span data-stu-id="97e03-184">Windows PowerShell ISE 2.0 does not save the scripts automatically in the event of a restart.</span></span>

### <span data-ttu-id="97e03-185"><a name="BKMK_MRU"></a>最近使用した一覧</span><span class="sxs-lookup"><span data-stu-id="97e03-185"><a name="BKMK_MRU"></a>Most-recently used list</span></span>
<span data-ttu-id="97e03-186">**PowerShell 3.0 に追加**</span><span class="sxs-lookup"><span data-stu-id="97e03-186">**Added in PowerShell 3.0**</span></span>

<span data-ttu-id="97e03-187">Windows PowerShell ISE にファイルの最近使用した一覧が用意されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="97e03-187">Windows PowerShell ISE now has a most-recently used list for files.</span></span> <span data-ttu-id="97e03-188">Windows PowerShell ISE でファイルを開くと、ファイルは **[ファイル]** メニューの最近使用した一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="97e03-188">When you open a file in Windows PowerShell ISE, the file is added to the most-recently used list on the **File** menu.</span></span>

<span data-ttu-id="97e03-189">最近使用した一覧内の既定のファイル数を変更するには、[コンソール] ウィンドウで、**$psise.Options.MruCount** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="97e03-189">To change the default number of files in the most-recently used list, run the following command in the Console Pane: **$psise.Options.MruCount**.</span></span>

<span data-ttu-id="97e03-190">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="97e03-190">**What value does this change add?**</span></span>

<span data-ttu-id="97e03-191">最近使用した一覧を使用して、頻繁に使用されるファイルに簡単にアクセスできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="97e03-191">You can now use the most-recently used list to easily access your frequently-used files.</span></span>

<span data-ttu-id="97e03-192">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="97e03-192">**What works differently?**</span></span>

<span data-ttu-id="97e03-193">Windows PowerShell ISE 2.0 には、最近使用した一覧は用意されていません。</span><span class="sxs-lookup"><span data-stu-id="97e03-193">Windows PowerShell ISE 2.0 does not have a most-recently used list.</span></span>

### <span data-ttu-id="97e03-194"><a name="BKMK_ConsolePane"></a>コンソール ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="97e03-194"><a name="BKMK_ConsolePane"></a>Console Pane</span></span>
<span data-ttu-id="97e03-195">**PowerShell 3.0 に追加**</span><span class="sxs-lookup"><span data-stu-id="97e03-195">**Added in PowerShell 3.0**</span></span>

<span data-ttu-id="97e03-196">Windows PowerShell ISE の最初のリリースで使用できた、独立したコマンド ウィンドウと出力ウィンドウが 1 つのコンソール ウィンドウに統合されました。</span><span class="sxs-lookup"><span data-stu-id="97e03-196">The separate Command and Output Panes that were available in the first release of Windows PowerShell ISE have been combined into a single Console Pane.</span></span> <span data-ttu-id="97e03-197">コンソール ウィンドウの機能と外観は、標準的な Windows PowerShell コンソールと似ていますが、次のような機能が強化されています (このトピックで、ほとんどの機能を説明します)。</span><span class="sxs-lookup"><span data-stu-id="97e03-197">The Console Pane is similar in function and appearance to a typical Windows PowerShell console, but it includes the following enhancements (most are described in this topic).</span></span>

-   <span data-ttu-id="97e03-198">XML 構文を含む入力テキストの構文の色分け (出力テキストを除く)</span><span class="sxs-lookup"><span data-stu-id="97e03-198">Syntax coloring for input text (not output text), including XML syntax</span></span>

-   <span data-ttu-id="97e03-199">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="97e03-199">IntelliSense</span></span>

-   <span data-ttu-id="97e03-200">かっこの照合</span><span class="sxs-lookup"><span data-stu-id="97e03-200">Brace matching</span></span>

-   <span data-ttu-id="97e03-201">エラー表示</span><span class="sxs-lookup"><span data-stu-id="97e03-201">Error indication</span></span>

-   <span data-ttu-id="97e03-202">全角 Unicode のサポート</span><span class="sxs-lookup"><span data-stu-id="97e03-202">Full Unicode support</span></span>

-   <span data-ttu-id="97e03-203">**F1** キーによる状況依存のヘルプ</span><span class="sxs-lookup"><span data-stu-id="97e03-203">**F1** context-sensitive help</span></span>

-   <span data-ttu-id="97e03-204">**Ctrl + F1** キーによる状況依存の Show-Command</span><span class="sxs-lookup"><span data-stu-id="97e03-204">**Ctrl+F1** context-sensitive Show-Command</span></span>

-   <span data-ttu-id="97e03-205">複雑なスクリプトおよび右から左への記述のサポート</span><span class="sxs-lookup"><span data-stu-id="97e03-205">Complex script and right-to-left support</span></span>

-   <span data-ttu-id="97e03-206">フォントのサポート</span><span class="sxs-lookup"><span data-stu-id="97e03-206">Font support</span></span>

-   <span data-ttu-id="97e03-207">ズーム</span><span class="sxs-lookup"><span data-stu-id="97e03-207">Zoom</span></span>

-   <span data-ttu-id="97e03-208">行選択モードとブロック選択モード</span><span class="sxs-lookup"><span data-stu-id="97e03-208">Line-select and block-select modes</span></span>

-   <span data-ttu-id="97e03-209">**上**方向キーを押して履歴をコンソールに表示したときにコマンド ラインに入力されたコンテンツを保存する機能</span><span class="sxs-lookup"><span data-stu-id="97e03-209">Preservation of typed content at the command line when you press the **Up** arrow to view history in the console</span></span>

<span data-ttu-id="97e03-210">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="97e03-210">**What value does this change add?**</span></span>

<span data-ttu-id="97e03-211">これらのコンソール ウィンドウの変更を追加したことにより、コンソール インターフェイスとの一貫性がより向上したスクリプトの操作性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="97e03-211">The addition of these Console Pane changes provides a scripting experience that is more consistent with the console interface.</span></span>

<span data-ttu-id="97e03-212">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="97e03-212">**What works differently?**</span></span>

<span data-ttu-id="97e03-213">Windows PowerShell ISE 2.0 では、コマンド ウィンドウと出力ウィンドウは個別に表示されます。</span><span class="sxs-lookup"><span data-stu-id="97e03-213">Windows PowerShell ISE 2.0 has separate Command and Output Panes.</span></span>

### <span data-ttu-id="97e03-214"><a name="BKMK_CommandLine"></a>コマンド ライン スイッチ</span><span class="sxs-lookup"><span data-stu-id="97e03-214"><a name="BKMK_CommandLine"></a>Command-line switches</span></span>
<span data-ttu-id="97e03-215">**PowerShell 3.0 に追加**</span><span class="sxs-lookup"><span data-stu-id="97e03-215">**Added in PowerShell 3.0**</span></span>

<span data-ttu-id="97e03-216">コマンド ライン (「**Powershell_ise.exe**」を入力) から Windows PowerShell ISE を起動する場合、次の新しいコマンド ライン スイッチを追加できます。</span><span class="sxs-lookup"><span data-stu-id="97e03-216">If you start Windows PowerShell ISE from the command line (by typing **powershell_ise.exe**), you can add the following new command-line switches.</span></span>

-   <span data-ttu-id="97e03-217">*-NoProfile*: **$profile** を実行せずに Windows PowerShell ISE を起動する</span><span class="sxs-lookup"><span data-stu-id="97e03-217">*-NoProfile*: Starts Windows PowerShell ISE without running **$profile**</span></span>

-   <span data-ttu-id="97e03-218">*-Help*: ヘルプ ウィンドウを表示する</span><span class="sxs-lookup"><span data-stu-id="97e03-218">*-Help*: Displays a Help window</span></span>

-   <span data-ttu-id="97e03-219">*-mta*: マルチスレッド アパートメント モードで Windows PowerShell ISE を起動する。</span><span class="sxs-lookup"><span data-stu-id="97e03-219">*-mta*: Starts Windows PowerShell ISE in multithreaded apartment mode.</span></span> <span data-ttu-id="97e03-220">Windows PowerShell ISE の既定の操作モードは、1 つのシングル スレッド アパートメント モード、つまり *-sta* です。</span><span class="sxs-lookup"><span data-stu-id="97e03-220">The default operation mode for Windows PowerShell ISE is single-threaded apartment mode, or *-sta*.</span></span>

<span data-ttu-id="97e03-221">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="97e03-221">**What value does this change add?**</span></span>

<span data-ttu-id="97e03-222">これらのコマンド ライン スイッチを追加すると、Windows PowerShell ISE が動作する環境を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="97e03-222">The addition of these command-line switches allows you to control the environment in which the Windows PowerShell ISE runs.</span></span>

<span data-ttu-id="97e03-223">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="97e03-223">**What works differently?**</span></span>

<span data-ttu-id="97e03-224">Windows PowerShell ISE 2.0 では、これらのコマンド ライン スイッチは認識されません。</span><span class="sxs-lookup"><span data-stu-id="97e03-224">Windows PowerShell ISE 2.0 does not recognize these command-line switches.</span></span>

### <span data-ttu-id="97e03-225"><a name="BKMK_NewEditorFeatures"></a>エディターの新機能</span><span class="sxs-lookup"><span data-stu-id="97e03-225"><a name="BKMK_NewEditorFeatures"></a>New editor features</span></span>
<span data-ttu-id="97e03-226">**PowerShell 3.0 に追加**</span><span class="sxs-lookup"><span data-stu-id="97e03-226">**Added in PowerShell 3.0**</span></span>

<span data-ttu-id="97e03-227">その他の Windows PowerShell ISE 編集機能として、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="97e03-227">Other Windows PowerShell ISE editing features include:</span></span>

-   <span data-ttu-id="97e03-228">**XML 構文の色分け**。Windows PowerShell ISE では、Windows PowerShell 構文を色分けする方法と同じ方法で XML 構文を色分けするようになりました。</span><span class="sxs-lookup"><span data-stu-id="97e03-228">**XML syntax coloring**Windows PowerShell ISE now colors XML syntax in the same way as it colors Windows PowerShell syntax.</span></span>

-   <span data-ttu-id="97e03-229">**かっこの照合**。Windows PowerShell ISE は、かっこの照合と強調表示の機能を搭載し、次のように使用できます。たとえば、始めかっこを選択している場合、**[一致する項目に移動]** コマンドまたは **[Ctrl + ]** を使用すると、終わりかっこが見つかります。</span><span class="sxs-lookup"><span data-stu-id="97e03-229">**Brace matching** Windows PowerShell ISE includes brace matching and highlighting, and can be used in the following ways: (for example, using the **Go to Match** command or **Ctrl + ]** locates the closing brace, if you have an opening brace selected).</span></span>

-   <span data-ttu-id="97e03-230">**アウトライン表示**。スクリプト ウィンドウでは、アウトラインがサポートされます。これにより、左余白のプラス記号またはマイナス記号をクリックすると、コードのセクションを折りたたんだり展開したりできます。</span><span class="sxs-lookup"><span data-stu-id="97e03-230">**Outline view** The Script Pane supports outlining, which allows collapsing or expanding sections of code by clicking plus or minus signs in the left margin.</span></span> <span data-ttu-id="97e03-231">かっこ、または **#region** タグと **#endregion** タグを使用して、折りたたみ可能なセクションの先頭または末尾をマークすることができます。</span><span class="sxs-lookup"><span data-stu-id="97e03-231">You can use braces or the **#region** and **#endregion** tags to mark the beginning or end of a collapsible section.</span></span> <span data-ttu-id="97e03-232">すべての領域を展開する、または折りたたむには、**Ctrl + M** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="97e03-232">To expand or collapse all regions, press **Ctrl + M**.</span></span>

-   <span data-ttu-id="97e03-233">**ドラッグ アンド ドロップ テキスト編集**。Windows PowerShell ISE で、ドラッグ アンド ドロップによるテキスト編集がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="97e03-233">**Drag and drop text editing**Windows PowerShell ISE now supports drag and drop text editing.</span></span> <span data-ttu-id="97e03-234">任意のテキストのブロックを選択し、そのテキストをドラッグしてエディターまたはコンソール内の別の場所に移動できます。</span><span class="sxs-lookup"><span data-stu-id="97e03-234">You can select any block of text and drag that text to another location in the editor or the console to move the text.</span></span> <span data-ttu-id="97e03-235">Ctrl キーを押したまま選択したテキストをドラッグし、マウス ボタンを放すと、テキストが新しい場所にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="97e03-235">If you hold down the Ctrl key while you drag the selected text, when you release the mouse button the text is copied to the new location.</span></span> <span data-ttu-id="97e03-236">以前のバージョンの Windows PowerShell ISE と同様に、このバージョンの Windows PowerShell ISE では、ファイルを Windows PowerShell ISE 上にドラッグ アンド ドロップすると、Windows PowerShell ISE でファイルが開かれます。</span><span class="sxs-lookup"><span data-stu-id="97e03-236">In this version of Windows PowerShell ISE, as well as the previous version of Windows PowerShell ISE, when you drag and drop files onto Windows PowerShell ISE, Windows PowerShell ISE opens the file.</span></span>

-   <span data-ttu-id="97e03-237">**解析エラーの表示**。解析エラーは赤い下線で示されます。</span><span class="sxs-lookup"><span data-stu-id="97e03-237">**Parse error display** Parse errors are indicated with red underlines.</span></span> <span data-ttu-id="97e03-238">示されたエラーをポイントすると、コード内で見つかった問題がヒントのテキストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="97e03-238">When you hover over an indicated error, tooltip text displays the problem that was found in the code.</span></span>

-   <span data-ttu-id="97e03-239">**ズーム**。コンソールのコンテンツのズーム倍率を設定するには、ズーム スライダー (Windows PowerShell ISE ウィンドウの右下隅にあります) を使用するか、またはコンソール ウィンドウでコマンド「**$psise.options.Zoom**」を入力します。</span><span class="sxs-lookup"><span data-stu-id="97e03-239">**Zoom** The zoom percentage of the console’s content can be set by using the zoom slider (in the lower right corner of Windows PowerShell ISE window), or by entering the command **$psise.options.Zoom** in the Console Pane.</span></span>

-   <span data-ttu-id="97e03-240">**リッチ テキストのコピーと貼り付け**。Windows PowerShell ISE でクリップボードにコピーすると、元の選択範囲のフォント、サイズ、および色の情報が保存されます。</span><span class="sxs-lookup"><span data-stu-id="97e03-240">**Rich text copy and paste** Copying to the clipboard in Windows PowerShell ISE preserves the font, size, and color information of the original selection.</span></span>

-   <span data-ttu-id="97e03-241">**ブロック選択**。テキストのブロックを選択するには、Alt キーを押したままマウスでスクリプト ウィンドウ内のテキストを選択するか、または **Alt + Shift + 方向キー**を押します。</span><span class="sxs-lookup"><span data-stu-id="97e03-241">**Block selection** You can select a block of text by holding down the ALT key while selecting text in the Script Pane with your mouse, or by pressing **Alt+Shift+Arrow**.</span></span>

<span data-ttu-id="97e03-242">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="97e03-242">**What value does this change add?**</span></span>

<span data-ttu-id="97e03-243">追加の編集機能によって、より一貫性のある強力な編集環境が提供されます。</span><span class="sxs-lookup"><span data-stu-id="97e03-243">The additional editing features provide a more consistent and powerful editing environment.</span></span>

<span data-ttu-id="97e03-244">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="97e03-244">**What works differently?**</span></span>

<span data-ttu-id="97e03-245">これらの編集の拡張機能は Windows PowerShell ISE 2.0 にはなかった機能です。</span><span class="sxs-lookup"><span data-stu-id="97e03-245">These editing enhancements were not present in Windows PowerShell ISE 2.0.</span></span>

### <span data-ttu-id="97e03-246"><a name="BKMK_NewHelpViewer"></a>新しいヘルプ ビューアー ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="97e03-246"><a name="BKMK_NewHelpViewer"></a>New Help viewer window</span></span>
<span data-ttu-id="97e03-247">**PowerShell 3.0 に追加**</span><span class="sxs-lookup"><span data-stu-id="97e03-247">**Added in PowerShell 3.0**</span></span>

<span data-ttu-id="97e03-248">カーソルがコマンドレット内にあるかコマンドレットの一部を強調表示しているときに **F1** キーを押すと、強調表示されたコマンドレットに関する状況依存のヘルプが新しいヘルプ ビューアーで開かれます。</span><span class="sxs-lookup"><span data-stu-id="97e03-248">If you press **F1** when your cursor is in a cmdlet, or you have part of a cmdlet highlighted, the new Help viewer opens context-sensitive Help about the highlighted cmdlet.</span></span> <span data-ttu-id="97e03-249">Windows PowerShell の About ヘルプを表示するには、コンソール ウィンドウで「**operators**」と入力し、**F1** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="97e03-249">To display Windows PowerShell About help, type  **operators** in the console pane, and then press **F1**.</span></span>

<span data-ttu-id="97e03-250">この機能を使用する前に、Microsoft Web サイトから Windows PowerShell のヘルプ トピックの最新バージョンをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="97e03-250">Before you use this feature, download the most current version of Windows PowerShell Help topics from the Microsoft website.</span></span> <span data-ttu-id="97e03-251">ヘルプ トピックをダウンロードする最も簡単な方法は、管理者として Windows PowerShell を実行中に、コンソール ウィンドウで **Update-Help** コマンドレットを実行することです。</span><span class="sxs-lookup"><span data-stu-id="97e03-251">The simplest method for downloading the Help topics is to run the **Update-Help** cmdlet in the Console Pane when running Windows PowerShell ISE as administrator.</span></span>

<span data-ttu-id="97e03-252">**F1** キーを押したときにヘルプを検索する場所を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="97e03-252">You can alter where the **F1** key looks for Help.</span></span> <span data-ttu-id="97e03-253">**[ツール]**/**[オプション]** メニューで、**[全般設定]** タブの **[その他の設定]** の下で、**[オンライン コンテンツの代わりにローカル ヘルプ コンテンツを使用する]** ボックスをオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="97e03-253">In the **Tools**/**Options** menu, on the **General Settings** tab, under **Other Settings**, you can set or clear the checkbox **Use local help content instead of online content**.</span></span> <span data-ttu-id="97e03-254">オンにした場合、クライアントはモジュール フォルダーで検出されたダウンロード済みのヘルプ内でコマンドレット Help を検索します。</span><span class="sxs-lookup"><span data-stu-id="97e03-254">If checked, then the client looks for the cmdlet Help in the downloaded Help found in the modules folder.</span></span>  <span data-ttu-id="97e03-255">チェック ボックスをオフにした場合は、クライアントは、コマンドレット Help を TechNet ライブラリで検索します。</span><span class="sxs-lookup"><span data-stu-id="97e03-255">If the checkbox is cleared, then the client looks on the TechNet library for the cmdlet help.</span></span>

<span data-ttu-id="97e03-256">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="97e03-256">**What value does this change add?**</span></span>

<span data-ttu-id="97e03-257">現在のコマンドレットまたはスクリプトを離れることなく状況依存のヘルプを使用すると、シームレスに学習を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="97e03-257">Context-sensitive Help without leaving your current cmdlet or script provides a seamless learning experience.</span></span>

<span data-ttu-id="97e03-258">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="97e03-258">**What works differently?**</span></span>

<span data-ttu-id="97e03-259">以前のバージョンの Windows PowerShell ISE で F1 キーを押すと、ローカル コンピューター上のヘルプ ファイルが開きました。</span><span class="sxs-lookup"><span data-stu-id="97e03-259">Pressing F1 in previous versions of Windows PowerShell ISE opened the help file on the local computer.</span></span> <span data-ttu-id="97e03-260">Windows PowerShell ISE 3.0 以降では、検索と構成が可能なコマンドレットのヘルプを含むウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="97e03-260">In Windows PowerShell ISE 3.0 and later, a window opens that contains the help for the cmdlet that is searchable and configurable.</span></span> <span data-ttu-id="97e03-261">このヘルプ エクスペリエンスは Windows PowerShell ISE 3.0 の新機能であり、更新可能なヘルプは Windows PowerShell 3.0 の新機能です。</span><span class="sxs-lookup"><span data-stu-id="97e03-261">This Help experience is new for Windows PowerShell ISE 3.0, and Updatable Help is new for Windows PowerShell 3.0.</span></span>

### <span data-ttu-id="97e03-262"><a name="BKMK_ShowCommand"></a>Show-Command コマンドレット</span><span class="sxs-lookup"><span data-stu-id="97e03-262"><a name="BKMK_ShowCommand"></a>Show-Command cmdlet</span></span>
<span data-ttu-id="97e03-263">**PowerShell 3.0 に追加**</span><span class="sxs-lookup"><span data-stu-id="97e03-263">**Added in PowerShell 3.0**</span></span>

<span data-ttu-id="97e03-264">**Show-Command** コマンドレットを使用すると、グラフィカルなフォームに情報を入力してコマンドレットや関数を構成または実行できます。</span><span class="sxs-lookup"><span data-stu-id="97e03-264">The **Show-Command** cmdlet enables you to compose or run a cmdlet or function by filling in a graphical form.</span></span> <span data-ttu-id="97e03-265">フォームを使用すると、グラフィカルな環境でユーザーが Windows PowerShell で作業できます。</span><span class="sxs-lookup"><span data-stu-id="97e03-265">The form lets users work with Windows PowerShell in a graphical environment.</span></span> <span data-ttu-id="97e03-266">また、上級のスクリプト作成者は **Show-Command** を使用して、簡単な Windows PowerShell ベースの GUI を作成できます。</span><span class="sxs-lookup"><span data-stu-id="97e03-266">**Show-Command** also enables advanced scripters to create a quick Windows PowerShell-based GUI.</span></span>

<span data-ttu-id="97e03-267">**この変更の利点**</span><span class="sxs-lookup"><span data-stu-id="97e03-267">**What value does this change add?**</span></span>

<span data-ttu-id="97e03-268">Windows PowerShell スクリプトで **Show-Command** を使用すると、ユーザーが使い慣れたグラフィカルな環境を提供できます。</span><span class="sxs-lookup"><span data-stu-id="97e03-268">By using **Show-Command** in your Windows PowerShell scripts, you can provide your users with the graphical environment with which they are familiar.</span></span> <span data-ttu-id="97e03-269">また、**Show-Command** は入門ユーザーが Windows PowerShell を学習するのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="97e03-269">**Show-Command** can also help introductory users learn Windows PowerShell.</span></span>

<span data-ttu-id="97e03-270">**動作の相違点**</span><span class="sxs-lookup"><span data-stu-id="97e03-270">**What works differently?**</span></span>

<span data-ttu-id="97e03-271">Show-Command は Windows PowerShell ISE 3.0 の新機能です。</span><span class="sxs-lookup"><span data-stu-id="97e03-271">Show-Command is new Windows PowerShell ISE 3.0.</span></span>

## <span data-ttu-id="97e03-272"><a name="BKMK_LINKS"></a>関連項目</span><span class="sxs-lookup"><span data-stu-id="97e03-272"><a name="BKMK_LINKS"></a>See also</span></span>
<span data-ttu-id="97e03-273">Windows PowerShell での Windows PowerShell ISE の使用に関する詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="97e03-273">For more information about using Windows PowerShell ISE in Windows PowerShell, see the following links.</span></span>

- [<span data-ttu-id="97e03-274">Windows PowerShell Integrated Scripting Environment の使用</span><span class="sxs-lookup"><span data-stu-id="97e03-274">Using the Windows PowerShell Integrated Scripting Environment</span></span>](../core-powershell/ise/Using-the-Windows-PowerShell-ISE.md)
- [<span data-ttu-id="97e03-275">TechNet Wiki の ISE</span><span class="sxs-lookup"><span data-stu-id="97e03-275">ISE on the TechNet Wiki</span></span>](http://social.technet.microsoft.com/wiki/search/searchresults.aspx?q=ISE)
- [<span data-ttu-id="97e03-276">スクリプト センター</span><span class="sxs-lookup"><span data-stu-id="97e03-276">Script Center</span></span>](http://technet.microsoft.com/scriptcenter/default)
