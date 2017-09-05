---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "Windows PowerShell ISE でスクリプトを記述および実行する方法"
ms.assetid: 62f916d9-b3a1-484a-bdfb-41f57112c22b
ms.openlocfilehash: 577ecf96027618a0a8f98d5bcefe7ec949f337cc
ms.sourcegitcommit: 4102ecc35d473211f50a453f6ae3fbea31cb3428
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2017
---
# <a name="how-to-write-and-run-scripts-in-the-windows-powershell-ise"></a><span data-ttu-id="db69c-103">Windows PowerShell ISE でスクリプトを記述および実行する方法</span><span class="sxs-lookup"><span data-stu-id="db69c-103">How to Write and Run Scripts in the Windows PowerShell ISE</span></span>
<span data-ttu-id="db69c-104">このトピックでは、スクリプト ウィンドウでスクリプトを作成、編集、実行、保存する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="db69c-104">This topic describes how to create, edit, run, and save scripts in the Script Pane.</span></span>

-   [<span data-ttu-id="db69c-105">スクリプトを作成して実行する方法</span><span class="sxs-lookup"><span data-stu-id="db69c-105">How to create and run scripts</span></span>]()

-   [<span data-ttu-id="db69c-106">スクリプト ウィンドウでテキストを記述して編集する方法</span><span class="sxs-lookup"><span data-stu-id="db69c-106">How to write and edit text in the Script Pane</span></span>]()

-   [<span data-ttu-id="db69c-107">スクリプトを保存する方法</span><span class="sxs-lookup"><span data-stu-id="db69c-107">How to save a script</span></span>]()

## <span data-ttu-id="db69c-108"><a name="bkmk_1"></a>スクリプトを作成して実行する方法</span><span class="sxs-lookup"><span data-stu-id="db69c-108"><a name="bkmk_1"></a>How to create and run scripts</span></span>
<span data-ttu-id="db69c-109">Windows PowerShell® ファイルは、スクリプト ウィンドウで開いたり、編集したりできます。</span><span class="sxs-lookup"><span data-stu-id="db69c-109">You can open and edit Windows PowerShell® files in the Script Pane.</span></span> <span data-ttu-id="db69c-110">Windows PowerShell® で対象となるファイルの種類は、スクリプト ファイル (.ps1)、スクリプト データ ファイル (.psd1)、スクリプト モジュール ファイル (.psm1) です。</span><span class="sxs-lookup"><span data-stu-id="db69c-110">Specific file types of interest in Windows PowerShell® are script files (.ps1), script data files (.psd1), and script module files (.psm1).</span></span> <span data-ttu-id="db69c-111">これらのファイルの種類は、スクリプト ウィンドウのエディターで構文が色分けされます。</span><span class="sxs-lookup"><span data-stu-id="db69c-111">These file types are syntax colored in the Script Pane editor.</span></span> <span data-ttu-id="db69c-112">スクリプト ウィンドウで開くことのできる他の一般的なファイルの種類には、構成ファイル (.ps1xml)、XML ファイル、テキスト ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="db69c-112">Other common file types you may open in the Script Pane are configuration files (.ps1xml), XML files, and text files.</span></span>

> [!NOTE]
> <span data-ttu-id="db69c-113">Windows PowerShell の実行ポリシーによって、スクリプトの実行や、Windows PowerShell のプロファイルと構成ファイルの読み込みを実行できるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="db69c-113">The Windows PowerShell execution policy determines whether you can run scripts and load Windows PowerShell profiles and configuration files.</span></span> <span data-ttu-id="db69c-114">既定の実行ポリシー Restricted では、すべてのスクリプトの実行とプロファイルの読み込みが防止されます。</span><span class="sxs-lookup"><span data-stu-id="db69c-114">The default execution policy, Restricted, prevents all scripts from running, and prevents loading profiles.</span></span> <span data-ttu-id="db69c-115">プロファイルの、読み込みと使用を許可するように実行ポリシーを変更する方法については、「[Set-ExecutionPolicy[PSITPro5_Security]](https://technet.microsoft.com/en-us/library/5690a0e1-495b-4e63-8280-65ead7bf01ab)」と「[about_Signing [v4]](https://technet.microsoft.com/en-us/library/fcbdd3b9-0b9f-4734-b5c7-e0dcc304fa1d)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="db69c-115">To change the execution policy to allow profiles to load and be used, see [Set-ExecutionPolicy[PSITPro5_Security]](https://technet.microsoft.com/en-us/library/5690a0e1-495b-4e63-8280-65ead7bf01ab) and [about_Signing [v4]](https://technet.microsoft.com/en-us/library/fcbdd3b9-0b9f-4734-b5c7-e0dcc304fa1d).</span></span>

### <a name="to-create-a-new-script-file"></a><span data-ttu-id="db69c-116">新しいスクリプト ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="db69c-116">To create a new script file</span></span>
<span data-ttu-id="db69c-117">ツール バーの **[新規作成]**、または **[ファイル]** メニューの **[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-117">On the toolbar, click **New** , or on the **File** menu, click **New**.</span></span> <span data-ttu-id="db69c-118">作成されたファイルは、現在の PowerShell タブの下に新しいファイル タブとして表示されます。PowerShell のタブは、少なくとも 1 つのタブが存在する場合にのみ表示されることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="db69c-118">The created file appears in a new file tab under the current PowerShell tab. Remember that the PowerShell tabs are only visible when there are more than one.</span></span> <span data-ttu-id="db69c-119">既定では種類のスクリプトのファイル (.ps1) が作成されますが、そのファイルに新しい名前や拡張子を指定して保存できます。</span><span class="sxs-lookup"><span data-stu-id="db69c-119">By default a file of type script (.ps1) is created, but it can be saved with a new name and extension.</span></span> <span data-ttu-id="db69c-120">同じ PowerShell タブ内に複数のスクリプト ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="db69c-120">Multiple script files can be created in the same PowerShell tab.</span></span>

### <a name="to-open-an-existing-script"></a><span data-ttu-id="db69c-121">既存のスクリプトを開くには</span><span class="sxs-lookup"><span data-stu-id="db69c-121">To open an existing script</span></span>
<span data-ttu-id="db69c-122">ツール バーの **[開く]**、または **[ファイル]** メニューの **[開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-122">On the toolbar, click **Open…**, or on the **File** menu, click **Open**.</span></span> <span data-ttu-id="db69c-123">**[開く]** ダイアログ ボックスで、開くファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="db69c-123">In the **Open** dialog box, select the file you want to open.</span></span> <span data-ttu-id="db69c-124">開いたファイルが新しいタブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="db69c-124">The opened file appears in a new tab.</span></span>

### <a name="to-close-a-script-tab"></a><span data-ttu-id="db69c-125">スクリプト タブを閉じるには</span><span class="sxs-lookup"><span data-stu-id="db69c-125">To close a script tab</span></span>
<span data-ttu-id="db69c-126">閉じるスクリプトのスクリプト タブをクリックし、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="db69c-126">Click the script tab of the script you want to close, then do one of the following:</span></span>

1.  <span data-ttu-id="db69c-127">スクリプト タブの **[閉じる]** アイコン (X) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-127">Click the **Close** icon (X) on the script tab.</span></span>

2.  <span data-ttu-id="db69c-128">**[ファイル]** メニューの **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-128">On the **File** menu, click **Close**.</span></span>

<span data-ttu-id="db69c-129">ファイルが最後に保存されてから変更された場合は、ファイルを保存するか破棄するかを選ぶメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="db69c-129">If the file has been altered since it was last saved, you are prompted to save or discard it.</span></span>

### <a name="to-display-the-file-path"></a><span data-ttu-id="db69c-130">ファイル パスを表示するには</span><span class="sxs-lookup"><span data-stu-id="db69c-130">To display the file path</span></span>
<span data-ttu-id="db69c-131">ファイル タブのファイル名をポイントします。</span><span class="sxs-lookup"><span data-stu-id="db69c-131">On the file tab, point to the file name.</span></span> <span data-ttu-id="db69c-132">スクリプト ファイルへの完全修飾パスがヒントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="db69c-132">The fully qualified path to the script file appears in a tooltip.</span></span>

### <a name="to-run-a-script"></a><span data-ttu-id="db69c-133">スクリプトを実行するには</span><span class="sxs-lookup"><span data-stu-id="db69c-133">To run a script</span></span>
<span data-ttu-id="db69c-134">ツール バーの **[スクリプトを実行]**、または **[ファイル]** メニューの **[実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-134">On the toolbar, click **Run Script**, or on the **File** menu, click **Run**.</span></span>

### <a name="to-run-a-portion-of-a-script"></a><span data-ttu-id="db69c-135">スクリプトの一部を実行するには</span><span class="sxs-lookup"><span data-stu-id="db69c-135">To run a portion of a script</span></span>

1.  <span data-ttu-id="db69c-136">スクリプト ウィンドウで、スクリプトの一部を選択します。</span><span class="sxs-lookup"><span data-stu-id="db69c-136">In the Script Pane, select a portion of a script.</span></span>

2.  <span data-ttu-id="db69c-137">**[ファイル]** メニューの **[選択項目を実行]**、またはツール バーの **[選択項目を実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-137">On the **File** menu, click **Run Selection**, or on the toolbar, click **Run Selection**.</span></span>

### <a name="to-stop-a-running-script"></a><span data-ttu-id="db69c-138">スクリプトの実行を停止するには</span><span class="sxs-lookup"><span data-stu-id="db69c-138">To stop a running script</span></span>
<span data-ttu-id="db69c-139">ツール バーの **[実行を中止]** をクリックするか、CTRL + BREAK キーを押すか、または、**[ファイル]** メニューの **[実行を中止]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-139">On the toolbar, click **Stop Operation**, press CTRL+BREAK, or on the **File** menu, click **Stop Operation**.</span></span> <span data-ttu-id="db69c-140">テキストが選択されていない場合は、**CTRL + C** キーを押すと、実行が停止します。テキストが選択されている場合は、**CTRL + C** キーは、選択したテキストのコピー機能にマップされます。</span><span class="sxs-lookup"><span data-stu-id="db69c-140">Pressing **CTRL+C** also works unless some text is currently selected, in which case **CTRL+C** maps to the copy function for the selected text.</span></span>

## <span data-ttu-id="db69c-141"><a name="bkmk_2"></a>スクリプト ウィンドウでテキストを記述して編集する方法</span><span class="sxs-lookup"><span data-stu-id="db69c-141"><a name="bkmk_2"></a>How to write and edit text in the Script Pane</span></span>
<span data-ttu-id="db69c-142">スクリプト ウィンドウでテキストを編集するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="db69c-142">Use the following steps to edit text in the Script Pane.</span></span> <span data-ttu-id="db69c-143">テキストのコピー、切り取り、貼り付け、検索、置換を実行できます。</span><span class="sxs-lookup"><span data-stu-id="db69c-143">You can copy, cut, paste, find, and replace text.</span></span> <span data-ttu-id="db69c-144">最後に実行した操作を元に戻したり、再実行したりできます。</span><span class="sxs-lookup"><span data-stu-id="db69c-144">You can also undo and redo the last action you just performed.</span></span> <span data-ttu-id="db69c-145">これらのアクションを実行するためのキーボード ショートカットは、すべての Windows アプリケーションで使われているものと同じです。</span><span class="sxs-lookup"><span data-stu-id="db69c-145">The keyboard shortcuts for performing these actions are the same as those used for all Windows applications.</span></span>

### <a name="to-enter-text-in-the-script-pane"></a><span data-ttu-id="db69c-146">スクリプト ウィンドウにテキストを入力するには</span><span class="sxs-lookup"><span data-stu-id="db69c-146">To enter text in the Script Pane</span></span>

1.  <span data-ttu-id="db69c-147">カーソルをスクリプト ウィンドウに移すには、スクリプト ウィンドウ内の任意の場所をクリックするか、または **[表示]** メニューの **[スクリプト ウィンドウに移動]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-147">Move the cursor to the Script Pane by clicking anywhere in the Script Pane, or by clicking **Go to Script Pane** in the **View** menu.</span></span>

2.  <span data-ttu-id="db69c-148">スクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="db69c-148">Create a script.</span></span> <span data-ttu-id="db69c-149">Windows PowerShell ISE では、入力しやすいように、構文の色分けやタブ補完の機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="db69c-149">Syntax coloring and tab completion make this a richer experience in Windows PowerShell ISE.</span></span>

3.  <span data-ttu-id="db69c-150">入力中にタブ補完機能を使う方法について詳しくは、「[スクリプト ウィンドウとコンソール ウィンドウでタブ補完を使用する方法](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="db69c-150">See [How to Use Tab Completion in the Script Pane and Console Pane](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md) for details about using the tab completion feature to help in typing.</span></span>

### <a name="to-find-text-in-the-script-pane"></a><span data-ttu-id="db69c-151">スクリプト ウィンドウでテキストを検索するには</span><span class="sxs-lookup"><span data-stu-id="db69c-151">To find text in the Script Pane</span></span>

1.  <span data-ttu-id="db69c-152">任意の場所にあるテキストを検索するには、**CTRL + F** キーを押すか、または**[編集]** メニューの **[スクリプト内を検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-152">To find text anywhere, press **CTRL+F** or, on the **Edit** menu, click **Find in Script**.</span></span>

2.  <span data-ttu-id="db69c-153">カーソルより後の場所にあるテキストを検索するには、**F3** キーを押すか、または**[編集]** メニューの **[スクリプト内で次を検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-153">To find text after the cursor, press **F3** or, on the **Edit** menu, click **Find Next in Script**.</span></span>

3.  <span data-ttu-id="db69c-154">カーソルより前の場所にあるテキストを検索するには、**SHIFT + F3** キーを押すか、または**[編集]** メニューの **[スクリプト内で前を検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-154">To find text before the cursor, press **SHIFT+F3** or, on the **Edit** menu, click **Find Previous in Script**.</span></span>

### <a name="to-find-and-replace-text-in-the-script-pane"></a><span data-ttu-id="db69c-155">スクリプト ウィンドウでテキストを検索して置換するには</span><span class="sxs-lookup"><span data-stu-id="db69c-155">To find and replace text in the Script Pane</span></span>
<span data-ttu-id="db69c-156">**CTRL + H** キーを押すか、または**[編集]** メニューの **[スクリプト内で置換]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-156">Press **CRTL+H** or, on the **Edit** menu, click **Replace in Script**.</span></span> <span data-ttu-id="db69c-157">検索するテキストと、見つかったテキストを置換するテキストの両方を入力してから、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="db69c-157">Enter both the text you want to find and the text with which you want to replace it, and then press **ENTER**.</span></span>

### <a name="to-go-to-a-particular-line-of-text-in-the-script-pane"></a><span data-ttu-id="db69c-158">スクリプト ウィンドウ内のテキストの特定の行に移動するには</span><span class="sxs-lookup"><span data-stu-id="db69c-158">To go to a particular line of text in the Script Pane</span></span>

1.  <span data-ttu-id="db69c-159">スクリプト ウィンドウで **CTRL + G** キーを押すか、または **[編集]** メニューの **[指定の行に移動]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-159">In the Script Pane, press **CTRL+G** or, on the **Edit** menu, click **Go to Line**.</span></span>

2.  <span data-ttu-id="db69c-160">行番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="db69c-160">Enter a line number.</span></span>

### <a name="to-copy-text-in-the-script-pane"></a><span data-ttu-id="db69c-161">スクリプト ウィンドウでテキストをコピーするには</span><span class="sxs-lookup"><span data-stu-id="db69c-161">To copy text in the Script Pane</span></span>

1.  <span data-ttu-id="db69c-162">スクリプト ウィンドウで、コピーするテキストを選択します。</span><span class="sxs-lookup"><span data-stu-id="db69c-162">In the Script Pane, select the text that you want to copy.</span></span>

2.  <span data-ttu-id="db69c-163">**CTRL + C** キーを押すか、ツール バーで **[コピー]** アイコンをクリックするか、または **[編集]** メニューの **[コピー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-163">Press **CTRL+C** or, on the toolbar, click the **Copy** icon, or on the **Edit** menu, click **Copy**.</span></span>

### <a name="to-cut-text-in-the-script-pane"></a><span data-ttu-id="db69c-164">スクリプト ウィンドウでテキストを切り取るには</span><span class="sxs-lookup"><span data-stu-id="db69c-164">To cut text in the Script Pane</span></span>

1.  <span data-ttu-id="db69c-165">スクリプト ウィンドウで、切り取るテキストを選択します。</span><span class="sxs-lookup"><span data-stu-id="db69c-165">In the Script Pane, select the text that you want to cut.</span></span>

2.  <span data-ttu-id="db69c-166">**CTRL + X** キーを押すか、ツール バーで **[切り取り]** アイコンをクリックするか、または **[編集]** メニューの **[切り取り]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-166">Press **CTRL+X** or, on the toolbar, click the **Cut** icon, or on the **Edit** menu, click **Cut**.</span></span>

### <a name="to-paste-text-into-the-script-pane"></a><span data-ttu-id="db69c-167">スクリプト ウィンドウにテキストを貼り付けるには</span><span class="sxs-lookup"><span data-stu-id="db69c-167">To paste text into the Script Pane</span></span>
<span data-ttu-id="db69c-168">**CTRL + V** キーを押すか、ツール バーで **[貼り付け]** アイコンをクリックするか、または **[編集]** メニューの **[貼り付け]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-168">Press **CTRL+V** or, on the toolbar, click the **Paste** icon, or on the **Edit** menu, click **Paste**.</span></span>

### <a name="to-undo-an-action-in-the-script-pane"></a><span data-ttu-id="db69c-169">スクリプト ウィンドウ内のアクションを元に戻すには</span><span class="sxs-lookup"><span data-stu-id="db69c-169">To undo an action in the Script Pane</span></span>
<span data-ttu-id="db69c-170">**CTRL + Z** キーを押すか、ツール バーで **[元に戻す]** アイコンをクリックするか、または **[編集]** メニューの **[元に戻す]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-170">Press **CTRL+Z** or, on the toolbar, click the **Undo** icon, or on the **Edit** menu, click **Undo**.</span></span>

### <a name="to-redo-an-action-in-the-script-pane"></a><span data-ttu-id="db69c-171">スクリプト ウィンドウ内のアクションをやり直すには</span><span class="sxs-lookup"><span data-stu-id="db69c-171">To redo an action in the Script Pane</span></span>
<span data-ttu-id="db69c-172">**CTRL + Y** キーを押すか、ツール バーで **[やり直し]** アイコンをクリックするか、または **[編集]** メニューの **[やり直し]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-172">Press **CTRL+Y** or, on the toolbar, click the **Redo** icon, or on the **Edit** menu, click **Redo**.</span></span>

## <span data-ttu-id="db69c-173"><a name="bkmk_3"></a>スクリプトを保存する方法</span><span class="sxs-lookup"><span data-stu-id="db69c-173"><a name="bkmk_3"></a>How to save a script</span></span>
<span data-ttu-id="db69c-174">スクリプトに名前を付けて保存するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="db69c-174">Use the following steps to save and name a script.</span></span> <span data-ttu-id="db69c-175">変更されてから保存されていないファイルには、スクリプト名の横にアスタリスクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="db69c-175">An asterisk appears next to the script name to mark a file that has not been saved since it was altered.</span></span> <span data-ttu-id="db69c-176">ファイルを保存すると、アスタリスクは消えます。</span><span class="sxs-lookup"><span data-stu-id="db69c-176">The asterisk disappears when the file is saved.</span></span>

### <a name="to-save-a-script"></a><span data-ttu-id="db69c-177">スクリプトを保存するには</span><span class="sxs-lookup"><span data-stu-id="db69c-177">To save a script</span></span>
<span data-ttu-id="db69c-178">**CTRL + S** キーを押すか、ツール バーで **[保存]** アイコンをクリックするか、または **[ファイル]** メニューの **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-178">Press **CTRL+S** or, on the toolbar, click the **Save** icon, or on the **File** menu, click **Save**.</span></span>

### <a name="to-save-and-name-a-script"></a><span data-ttu-id="db69c-179">スクリプトに名前を付けて保存するには</span><span class="sxs-lookup"><span data-stu-id="db69c-179">To save and name a script</span></span>

1.  <span data-ttu-id="db69c-180">**[ファイル]** メニューの **[名前を付けて保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-180">On the **File** menu, click **Save As**.</span></span> <span data-ttu-id="db69c-181">**[名前を付けて保存]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="db69c-181">The **Save As** dialog box will appear.</span></span>

2.  <span data-ttu-id="db69c-182">**[ファイル名]** ボックスに、ファイルの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="db69c-182">In the **File name** box, enter a name for the file.</span></span>

3.  <span data-ttu-id="db69c-183">**[ファイルの種類]** ボックスで、ファイルの種類を選びます。</span><span class="sxs-lookup"><span data-stu-id="db69c-183">In the **Save as type** box, select a file type.</span></span> <span data-ttu-id="db69c-184">たとえば、**[ファイルの種類]** ボックスで、[PowerShell スクリプト (\*.ps1)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="db69c-184">For example, in the **Save as type** box, select “PowerShell Scripts (\* .ps1)”.</span></span>

4.  <span data-ttu-id="db69c-185">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db69c-185">Click **Save**.</span></span>

### <a name="to-save-a-script-in-ascii-encoding"></a><span data-ttu-id="db69c-186">ASCII エンコードでスクリプトを保存するには</span><span class="sxs-lookup"><span data-stu-id="db69c-186">To save a script in ASCII encoding</span></span>
<span data-ttu-id="db69c-187">既定では、Windows PowerShell ISE は新しいスクリプト ファイル (.ps1)、スクリプト データ ファイル (.psd1)、スクリプト モジュール ファイル (.psm1) を Unicode (BigEndianUnicode) として保存します。</span><span class="sxs-lookup"><span data-stu-id="db69c-187">By default, Windows PowerShell ISE saves new script files (.ps1), script data files (.psd1), and script module files (.psm1) as Unicode (BigEndianUnicode) by default.</span></span> <span data-ttu-id="db69c-188">ASCII (ANSI) など、別のエンコードでスクリプトを保存するには、[$psISE.CurrentFile](https://technet.microsoft.com/en-us/library/bc3300e4-9c17-4f00-a621-c8867126e3b3#CurrentFile) オブジェクトの **Save** または **SaveAs** メソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="db69c-188">To save a script in another encoding, such as ASCII (ANSI), use the **Save** or **SaveAs** methods on the [$psISE.CurrentFile](https://technet.microsoft.com/en-us/library/bc3300e4-9c17-4f00-a621-c8867126e3b3#CurrentFile) object.</span></span>

<span data-ttu-id="db69c-189">次のコマンドでは、新しいスクリプトを MyScript.ps1 という名前の ASCII エンコードで保存します。</span><span class="sxs-lookup"><span data-stu-id="db69c-189">The following command saves a new script as MyScript.ps1 with ASCII encoding.</span></span>

```
$psise.CurrentFile.SaveAs("MyScript.ps1", [System.Text.Encoding]::ASCII)
```

<span data-ttu-id="db69c-190">次のコマンドでは、現在のスクリプト ファイルと同じ名前の ASCII エンコードのファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="db69c-190">The following command replaces the current script file with a file with the same name, but with ASCII encoding.</span></span>

```
$psise.CurrentFile.Save([System.Text.Encoding]::ASCII)
```

<span data-ttu-id="db69c-191">次のコマンドでは、現在のファイルのエンコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="db69c-191">The following command gets the encoding of the current file.</span></span>

```
$psise.CurrentFile.encoding
```

<span data-ttu-id="db69c-192">Windows PowerShell ISE では、次のエンコード オプションをサポートしています: ASCII、BigEndianUnicode、Unicode、UTF32、UTF7、UTF8、既定値。</span><span class="sxs-lookup"><span data-stu-id="db69c-192">Windows PowerShell ISE supports the following encoding options: ASCII, BigEndianUnicode, Unicode, UTF32, UTF7, UTF8 and Default.</span></span> <span data-ttu-id="db69c-193">既定値オプションの値は、システムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="db69c-193">The value of the Default option varies with the system.</span></span>

<span data-ttu-id="db69c-194">Windows PowerShell ISE では、Windows PowerShell ISE の [保存] または [名前を付けて保存] コマンドを使った場合でも、他のエディターによって作成されたスクリプトのエンコードは変更しません。</span><span class="sxs-lookup"><span data-stu-id="db69c-194">Windows PowerShell ISE does not change the encoding of scripts that were created by in other editors, even when you use the Save or Save As commands in Windows PowerShell ISE.</span></span>

## <a name="see-also"></a><span data-ttu-id="db69c-195">参照</span><span class="sxs-lookup"><span data-stu-id="db69c-195">See Also</span></span>
- [<span data-ttu-id="db69c-196">Windows PowerShell ISE の使用</span><span class="sxs-lookup"><span data-stu-id="db69c-196">Using the Windows PowerShell ISE</span></span>](Using-the-Windows-PowerShell-ISE.md)

