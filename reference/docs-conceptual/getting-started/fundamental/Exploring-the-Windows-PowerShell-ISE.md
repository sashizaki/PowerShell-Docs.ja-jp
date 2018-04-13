---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: Windows PowerShell ISE の操作
ms.assetid: e0d2c6e8-5126-40e7-a1e1-d1cff29fe94a
ms.openlocfilehash: 059651f159fb2636a93167709134788e90d062b8
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="exploring-the-windows-powershell-ise"></a><span data-ttu-id="348c9-103">Windows PowerShell ISE の操作</span><span class="sxs-lookup"><span data-stu-id="348c9-103">Exploring the Windows PowerShell ISE</span></span>

<span data-ttu-id="348c9-104">Windows PowerShell® Integrated Scripting Environment (ISE) を使用すると、コマンドやスクリプトを作成、実行、デバッグできます。</span><span class="sxs-lookup"><span data-stu-id="348c9-104">You can use the Windows PowerShell® Integrated Scripting Environment (ISE) to create, run, and debug commands and scripts.</span></span> <span data-ttu-id="348c9-105">Windows PowerShell ISE は、メニュー バー、Windows PowerShell タブ、ツール バー、スクリプト タブ、スクリプト ウィンドウ、コンソール ウィンドウ、ステータス バー、文字サイズ スライダー、状況依存のヘルプで構成されています。</span><span class="sxs-lookup"><span data-stu-id="348c9-105">The Windows PowerShell ISE consists of the menu bar, Windows PowerShell tabs, the toolbar, script tabs, a Script Pane, a Console Pane, a status bar, a text-size slider and context-sensitive Help.</span></span>

> [!NOTE]
> <span data-ttu-id="348c9-106">Windows PowerShell ISE 3.0 以降、コマンド ウィンドウと出力ウィンドウは、単一のコンソール ウィンドウに統合されました。</span><span class="sxs-lookup"><span data-stu-id="348c9-106">Beginning with Windows PowerShell ISE 3.0 the Command and Output Panes were combined into a single Console Pane.</span></span>

## <a name="menu-bar"></a><span data-ttu-id="348c9-107">メニュー バー</span><span class="sxs-lookup"><span data-stu-id="348c9-107">Menu Bar</span></span>

<span data-ttu-id="348c9-108">メニュー バーには、**[ファイル]**、**[編集]**、**[表示]**、**[ツール]**、**[デバッグ]**、**[アドオン]**、**[ヘルプ]** の各メニューがあります。</span><span class="sxs-lookup"><span data-stu-id="348c9-108">The menu bar contains the **File**, **Edit**, **View**, **Tools**, **Debug**, **Add-ons**, and **Help** menus.</span></span> <span data-ttu-id="348c9-109">メニューのボタンを使用すると、スクリプトの記述と実行、および Windows PowerShell ISE でのコマンドの実行に関連したタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="348c9-109">The buttons on the menus allow you to perform tasks related to writing and running scripts and running commands in the Windows PowerShell ISE.</span></span> <span data-ttu-id="348c9-110">さらに、[ISE オブジェクト モデルの階層](../../core-powershell/ise/The-ISE-Object-Model-Hierarchy.md)を使用するスクリプトを実行して、[アドオン ツール](../../core-powershell/ise/The-ISEAddOnTool-Object.md)をメニュー バーに配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="348c9-110">Additionally, an [add-on tool](../../core-powershell/ise/The-ISEAddOnTool-Object.md) may be placed on the menu bar by running scripts that use the [The ISE Object Model Hierarchy](../../core-powershell/ise/The-ISE-Object-Model-Hierarchy.md).</span></span>

> [!NOTE]
> <span data-ttu-id="348c9-111">Windows PowerShell ISE 2.0 には、**[ツール]** と **[アドオン]** メニューはありませんでした。</span><span class="sxs-lookup"><span data-stu-id="348c9-111">In Windows PowerShell ISE 2.0, The **Tools** and **Add-ons** menus were not present.</span></span>

## <a name="windows-powershell-tabs"></a><span data-ttu-id="348c9-112">Windows PowerShell タブ</span><span class="sxs-lookup"><span data-stu-id="348c9-112">Windows PowerShell Tabs</span></span>

<span data-ttu-id="348c9-113">Windows PowerShell タブは、Windows PowerShell スクリプトが動作する環境です。</span><span class="sxs-lookup"><span data-stu-id="348c9-113">A Windows PowerShell tab is the environment in which a Windows PowerShell script runs.</span></span> <span data-ttu-id="348c9-114">Windows PowerShell ISE で新しい Windows PowerShell タブを開いて、ローカル コンピューターまたはリモート コンピューターに別個の環境を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="348c9-114">You can open new Windows PowerShell tabs in the Windows PowerShell ISE to create separate environments on your local computer or on remote computers.</span></span> <span data-ttu-id="348c9-115">最大 8 つの PowerShell タブを同時に開くことができます。</span><span class="sxs-lookup"><span data-stu-id="348c9-115">You may have a maximum of eight PowerShell tabs simultaneously open.</span></span>

## <a name="toolbar"></a><span data-ttu-id="348c9-116">ツール バー</span><span class="sxs-lookup"><span data-stu-id="348c9-116">Toolbar</span></span>

<span data-ttu-id="348c9-117">ツール バーには次のボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="348c9-117">The following buttons are located on the toolbar.</span></span>

|<span data-ttu-id="348c9-118">ボタン</span><span class="sxs-lookup"><span data-stu-id="348c9-118">Button</span></span>|<span data-ttu-id="348c9-119">機能</span><span class="sxs-lookup"><span data-stu-id="348c9-119">Function</span></span>|
|----------|------------|
|<span data-ttu-id="348c9-120">**新規**</span><span class="sxs-lookup"><span data-stu-id="348c9-120">**New**</span></span>|<span data-ttu-id="348c9-121">新しいスクリプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="348c9-121">Opens a new script.</span></span>|
|<span data-ttu-id="348c9-122">**開く**</span><span class="sxs-lookup"><span data-stu-id="348c9-122">**Open**</span></span>|<span data-ttu-id="348c9-123">既存のスクリプトまたはファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="348c9-123">Opens an existing script or file.</span></span>|
|<span data-ttu-id="348c9-124">**上書き保存**</span><span class="sxs-lookup"><span data-stu-id="348c9-124">**Save**</span></span>|<span data-ttu-id="348c9-125">スクリプトまたはファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="348c9-125">Saves a script or file.</span></span>|
|<span data-ttu-id="348c9-126">**切り取り**</span><span class="sxs-lookup"><span data-stu-id="348c9-126">**Cut**</span></span>|<span data-ttu-id="348c9-127">選んだテキストを切り取り、クリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="348c9-127">Cuts the selected text and copies it to the clipboard.</span></span>|
|<span data-ttu-id="348c9-128">**コピー**</span><span class="sxs-lookup"><span data-stu-id="348c9-128">**Copy**</span></span>|<span data-ttu-id="348c9-129">選択したテキストをクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="348c9-129">Copies the selected text to the clipboard.</span></span>|
|<span data-ttu-id="348c9-130">**貼り付け**</span><span class="sxs-lookup"><span data-stu-id="348c9-130">**Paste**</span></span>|<span data-ttu-id="348c9-131">カーソル位置にクリップボードの内容を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="348c9-131">Pastes the contents of the clipboard at the cursor location.</span></span>|
|<span data-ttu-id="348c9-132">**出力ウィンドウをクリア**</span><span class="sxs-lookup"><span data-stu-id="348c9-132">**Clear Output Pane**</span></span>|<span data-ttu-id="348c9-133">出力ウィンドウの内容をすべてクリアします。</span><span class="sxs-lookup"><span data-stu-id="348c9-133">Clears all content in the Output Pane.</span></span>|
|<span data-ttu-id="348c9-134">**元に戻す**</span><span class="sxs-lookup"><span data-stu-id="348c9-134">**Undo**</span></span>|<span data-ttu-id="348c9-135">実行した直前のアクションを元に戻します。</span><span class="sxs-lookup"><span data-stu-id="348c9-135">Reverses the action that was just performed.</span></span>|
|<span data-ttu-id="348c9-136">**やり直す**</span><span class="sxs-lookup"><span data-stu-id="348c9-136">**Redo**</span></span>|<span data-ttu-id="348c9-137">元に戻した直前のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="348c9-137">Performs the action that was just undone.</span></span>|
|<span data-ttu-id="348c9-138">**スクリプトを実行**</span><span class="sxs-lookup"><span data-stu-id="348c9-138">**Run Script**</span></span>|<span data-ttu-id="348c9-139">スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="348c9-139">Runs a script.</span></span>|
|<span data-ttu-id="348c9-140">**選択範囲の実行**</span><span class="sxs-lookup"><span data-stu-id="348c9-140">**Run Selection**</span></span>|<span data-ttu-id="348c9-141">スクリプトの選んだ部分を実行します。</span><span class="sxs-lookup"><span data-stu-id="348c9-141">Runs a selected portion of a script.</span></span>|
|<span data-ttu-id="348c9-142">**実行を中止**</span><span class="sxs-lookup"><span data-stu-id="348c9-142">**Stop Execution**</span></span>|<span data-ttu-id="348c9-143">実行中のスクリプトを中止します。</span><span class="sxs-lookup"><span data-stu-id="348c9-143">Stops a script that is running.</span></span>|
|<span data-ttu-id="348c9-144">**リモート PowerShell タブの新規作成**</span><span class="sxs-lookup"><span data-stu-id="348c9-144">**New Remote PowerShell Tab**</span></span>|<span data-ttu-id="348c9-145">リモート コンピューターにセッションを確立する PowerShell タブを新規作成します。</span><span class="sxs-lookup"><span data-stu-id="348c9-145">Creates a new PowerShell Tab that establishes a session on a remote computer.</span></span> <span data-ttu-id="348c9-146">ダイアログ ボックスが表示され、リモート接続を確立するために必要な詳細情報を入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="348c9-146">A dialog box appears and prompts you to enter details required to establish the remote connection.</span></span>|
|<span data-ttu-id="348c9-147">**PowerShell.exe を起動**</span><span class="sxs-lookup"><span data-stu-id="348c9-147">**Start PowerShell.exe**</span></span>|<span data-ttu-id="348c9-148">PowerShell コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="348c9-148">Opens a PowerShell Console.</span></span>|
|<span data-ttu-id="348c9-149">**スクリプト ウィンドウを上に表示**</span><span class="sxs-lookup"><span data-stu-id="348c9-149">**Show Script Pane Top**</span></span>|<span data-ttu-id="348c9-150">スクリプト ウィンドウを画面の上部に移動します。</span><span class="sxs-lookup"><span data-stu-id="348c9-150">Moves the Script Pane to the top in the display.</span></span>|
|<span data-ttu-id="348c9-151">**スクリプト ウィンドウを右側に表示**</span><span class="sxs-lookup"><span data-stu-id="348c9-151">**Show Script Pane Right**</span></span>|<span data-ttu-id="348c9-152">スクリプト ウィンドウを画面の右側に移動します。</span><span class="sxs-lookup"><span data-stu-id="348c9-152">Moves the Script Pane to the right in the display.</span></span>|
|<span data-ttu-id="348c9-153">**スクリプト ウィンドウを最大表示**</span><span class="sxs-lookup"><span data-stu-id="348c9-153">**Show Script Pane Maximized**</span></span>|<span data-ttu-id="348c9-154">スクリプト ウィンドウを最大表示します。</span><span class="sxs-lookup"><span data-stu-id="348c9-154">Maximizes the Script Pane.</span></span>|

## <a name="script-tab"></a><span data-ttu-id="348c9-155">スクリプト タブ</span><span class="sxs-lookup"><span data-stu-id="348c9-155">Script Tab</span></span>

<span data-ttu-id="348c9-156">編集中のスクリプトの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="348c9-156">Displays the name of the script you are editing.</span></span> <span data-ttu-id="348c9-157">スクリプト タブをクリックして、編集するスクリプトを選択できます。</span><span class="sxs-lookup"><span data-stu-id="348c9-157">You can click a script tab to select the script you want to edit.</span></span>

<span data-ttu-id="348c9-158">スクリプト タブをポイントすると、スクリプト ファイルへの完全修飾パスがヒントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="348c9-158">When you point to the script tab, the fully qualified path to the script file appears in a tooltip.</span></span>

## <a name="script-pane"></a><span data-ttu-id="348c9-159">スクリプト ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="348c9-159">Script Pane</span></span>

<span data-ttu-id="348c9-160">スクリプトを作成して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="348c9-160">Allows you to create and run scripts.</span></span> <span data-ttu-id="348c9-161">スクリプト ウィンドウでは、既存のスクリプトを開いたり、編集および実行したりできます。</span><span class="sxs-lookup"><span data-stu-id="348c9-161">You can open, edit and run existing scripts in the Script Pane.</span></span>

## <a name="output-pane"></a><span data-ttu-id="348c9-162">出力ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="348c9-162">Output Pane</span></span>

<span data-ttu-id="348c9-163">実行したコマンドおよびスクリプトの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="348c9-163">Displays the results of the commands and scripts you have run.</span></span> <span data-ttu-id="348c9-164">出力ウィンドウの内容をコピーおよびクリアすることもできます。</span><span class="sxs-lookup"><span data-stu-id="348c9-164">You can also copy and clear the contents in the Output Pane.</span></span>

## <a name="command-pane"></a><span data-ttu-id="348c9-165">コマンド ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="348c9-165">Command Pane</span></span>

<span data-ttu-id="348c9-166">コマンドを記述できます。</span><span class="sxs-lookup"><span data-stu-id="348c9-166">Allows you to write commands.</span></span> <span data-ttu-id="348c9-167">コマンド ウィンドウでは、1 行のコマンドまたは複数行のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="348c9-167">You can run a one line command or a multiline command in the Command Pane.</span></span> <span data-ttu-id="348c9-168">SHIFT キーを押しながら ENTER キーを押すことで、改行を挿入し、複数行のコマンドを入力できます。最後の行の後で Enter キーを押すと、複数行のコマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="348c9-168">Press SHIFT+ENTER to enter each line of a multiline command, and press ENTER after the last line to execute the multiline command.</span></span> <span data-ttu-id="348c9-169">コマンド ウィンドウの上部に表示されるプロンプトには、現在の作業ディレクトリへのパスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="348c9-169">The prompt displayed on top of the Command Pane shows the path to the current working directory.</span></span>

## <a name="status-bar"></a><span data-ttu-id="348c9-170">ステータス バー</span><span class="sxs-lookup"><span data-stu-id="348c9-170">Status Bar</span></span>

<span data-ttu-id="348c9-171">実行したコマンドおよびスクリプトが完了しているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="348c9-171">Allows you to see whether the commands and scripts that you run are complete.</span></span> <span data-ttu-id="348c9-172">ステータス バーは、画面の最下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="348c9-172">The status bar is at the very bottom of the display.</span></span> <span data-ttu-id="348c9-173">エラー メッセージの選んだ部分がステータス バーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="348c9-173">Selected portions of error messages are displayed on the status bar.</span></span>

## <a name="text-size-slider"></a><span data-ttu-id="348c9-174">文字サイズ スライダー</span><span class="sxs-lookup"><span data-stu-id="348c9-174">Text-Size Slider</span></span>

<span data-ttu-id="348c9-175">画面の文字のサイズを拡大または縮小することができます。</span><span class="sxs-lookup"><span data-stu-id="348c9-175">Increases or decreases the size of the text on the screen.</span></span>

## <a name="help"></a><span data-ttu-id="348c9-176">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="348c9-176">Help</span></span>

<span data-ttu-id="348c9-177">Windows PowerShell ISE のヘルプは、Web 上の TechNet ライブラリで利用できます。</span><span class="sxs-lookup"><span data-stu-id="348c9-177">Help for Windows PowerShell ISE is available on the Web in the TechNet Library.</span></span> <span data-ttu-id="348c9-178">ヘルプを開くには、**[ヘルプ]** メニューの **[Windows PowerShell ISE ヘルプ]** をクリックするか、F1 キーを押します。これは、スクリプト ウィンドウまたはコンソール ウィンドウでコマンドレット名の上にカーソルがある場合を除き、どこからでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="348c9-178">You can open the Help by clicking **Windows PowerShell ISE Help** on the **Help** menu or by pressing the F1 key anywhere except when the cursor is on a cmdlet name in either the Script Pane or the Console Pane.</span></span> <span data-ttu-id="348c9-179">**[ヘルプ]** メニューからは、Update-Help コマンドレットを実行することや、コマンド ウィンドウを表示することもできます。コマンド ウィンドウは、コマンドレットのすべてのパラメーターを示したり、使いやすいフォームにパラメーターを入力できるようにしたりして、コマンドの作成を助けます。</span><span class="sxs-lookup"><span data-stu-id="348c9-179">From the **Help** menu you can also run the Update-Help cmdlet, and display the Command Window which assists you in constructing commands by showing you all of the parameters for a cmdlet and enabling you to fill in the parameters in an easy-to-use form.</span></span>

## <a name="see-also"></a><span data-ttu-id="348c9-180">参照</span><span class="sxs-lookup"><span data-stu-id="348c9-180">See Also</span></span>

- [<span data-ttu-id="348c9-181">Windows PowerShell ISE の紹介</span><span class="sxs-lookup"><span data-stu-id="348c9-181">Introducing the Windows PowerShell ISE</span></span>](../../core-powershell/ise/Introducing-the-Windows-PowerShell-ISE.md)