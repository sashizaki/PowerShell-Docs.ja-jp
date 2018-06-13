---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: Windows PowerShell ISE でスクリプトを記述および実行する方法
ms.assetid: 62f916d9-b3a1-484a-bdfb-41f57112c22b
ms.openlocfilehash: 4d7c5352ef1dac6f63a50433676068f83a920db5
ms.sourcegitcommit: 01d6985ed190a222e9da1da41596f524f607a5bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2018
ms.locfileid: "34483119"
---
# <a name="how-to-write-and-run-scripts-in-the-windows-powershell-ise"></a><span data-ttu-id="358c2-103">Windows PowerShell ISE でスクリプトを記述および実行する方法</span><span class="sxs-lookup"><span data-stu-id="358c2-103">How to Write and Run Scripts in the Windows PowerShell ISE</span></span>

<span data-ttu-id="358c2-104">このトピックでは、スクリプト ウィンドウでスクリプトを作成、編集、実行、保存する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="358c2-104">This topic describes how to create, edit, run, and save scripts in the Script Pane.</span></span>

## <a name="how-to-create-and-run-scripts"></a><span data-ttu-id="358c2-105">スクリプトを作成して実行する方法</span><span class="sxs-lookup"><span data-stu-id="358c2-105">How to create and run scripts</span></span>

<span data-ttu-id="358c2-106">Windows PowerShell ファイルは、スクリプト ウィンドウで開いたり、編集したりできます。</span><span class="sxs-lookup"><span data-stu-id="358c2-106">You can open and edit Windows PowerShell files in the Script Pane.</span></span> <span data-ttu-id="358c2-107">Windows PowerShell で対象となるファイルの種類は、スクリプト ファイル (.ps1)、スクリプト データ ファイル (.psd1)、スクリプト モジュール ファイル (.psm1) です。</span><span class="sxs-lookup"><span data-stu-id="358c2-107">Specific file types of interest in Windows PowerShell are script files (.ps1), script data files (.psd1), and script module files (.psm1).</span></span> <span data-ttu-id="358c2-108">これらのファイルの種類は、スクリプト ウィンドウのエディターで構文が色分けされます。</span><span class="sxs-lookup"><span data-stu-id="358c2-108">These file types are syntax colored in the Script Pane editor.</span></span> <span data-ttu-id="358c2-109">スクリプト ウィンドウで開くことのできる他の一般的なファイルの種類には、構成ファイル (.ps1xml)、XML ファイル、テキスト ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="358c2-109">Other common file types you may open in the Script Pane are configuration files (.ps1xml), XML files, and text files.</span></span>

> [!NOTE]
> <span data-ttu-id="358c2-110">Windows PowerShell の実行ポリシーによって、スクリプトの実行や、Windows PowerShell のプロファイルと構成ファイルの読み込みを実行できるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="358c2-110">The Windows PowerShell execution policy determines whether you can run scripts and load Windows PowerShell profiles and configuration files.</span></span> <span data-ttu-id="358c2-111">既定の実行ポリシー Restricted では、すべてのスクリプトの実行とプロファイルの読み込みが防止されます。</span><span class="sxs-lookup"><span data-stu-id="358c2-111">The default execution policy, Restricted, prevents all scripts from running, and prevents loading profiles.</span></span> <span data-ttu-id="358c2-112">プロファイルの、読み込みと使用を許可するように実行ポリシーを変更する方法については、「[Set-ExecutionPolicy[PSITPro5_Security]](https://technet.microsoft.com/library/5690a0e1-495b-4e63-8280-65ead7bf01ab)」と「[about_Signing [v4]](https://technet.microsoft.com/library/fcbdd3b9-0b9f-4734-b5c7-e0dcc304fa1d)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="358c2-112">To change the execution policy to allow profiles to load and be used, see [Set-ExecutionPolicy[PSITPro5_Security]](https://technet.microsoft.com/library/5690a0e1-495b-4e63-8280-65ead7bf01ab) and [about_Signing [v4]](https://technet.microsoft.com/library/fcbdd3b9-0b9f-4734-b5c7-e0dcc304fa1d).</span></span>

### <a name="to-create-a-new-script-file"></a><span data-ttu-id="358c2-113">新しいスクリプト ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="358c2-113">To create a new script file</span></span>

<span data-ttu-id="358c2-114">ツール バーの **[新規作成]**、または **[ファイル]** メニューの **[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-114">On the toolbar, click **New** , or on the **File** menu, click **New**.</span></span> <span data-ttu-id="358c2-115">作成されたファイルは、現在の PowerShell タブの下に新しいファイル タブとして表示されます。PowerShell のタブは、少なくとも 1 つのタブが存在する場合にのみ表示されることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="358c2-115">The created file appears in a new file tab under the current PowerShell tab. Remember that the PowerShell tabs are only visible when there are more than one.</span></span> <span data-ttu-id="358c2-116">既定では種類のスクリプトのファイル (.ps1) が作成されますが、そのファイルに新しい名前や拡張子を指定して保存できます。</span><span class="sxs-lookup"><span data-stu-id="358c2-116">By default a file of type script (.ps1) is created, but it can be saved with a new name and extension.</span></span> <span data-ttu-id="358c2-117">同じ PowerShell タブ内に複数のスクリプト ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="358c2-117">Multiple script files can be created in the same PowerShell tab.</span></span>

### <a name="to-open-an-existing-script"></a><span data-ttu-id="358c2-118">既存のスクリプトを開くには</span><span class="sxs-lookup"><span data-stu-id="358c2-118">To open an existing script</span></span>

<span data-ttu-id="358c2-119">ツール バーの **[開く]**、または **[ファイル]** メニューの **[開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-119">On the toolbar, click **Open**, or on the **File** menu, click **Open**.</span></span> <span data-ttu-id="358c2-120">**[開く]** ダイアログ ボックスで、開くファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="358c2-120">In the **Open** dialog box, select the file you want to open.</span></span> <span data-ttu-id="358c2-121">開いたファイルが新しいタブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="358c2-121">The opened file appears in a new tab.</span></span>

### <a name="to-close-a-script-tab"></a><span data-ttu-id="358c2-122">スクリプト タブを閉じるには</span><span class="sxs-lookup"><span data-stu-id="358c2-122">To close a script tab</span></span>

<span data-ttu-id="358c2-123">閉じるスクリプトのスクリプト タブをクリックし、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="358c2-123">Click the script tab of the script you want to close, then do one of the following:</span></span>

1. <span data-ttu-id="358c2-124">スクリプト タブの **[閉じる]** アイコン (X) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-124">Click the **Close** icon (X) on the script tab.</span></span>

2. <span data-ttu-id="358c2-125">**[ファイル]** メニューの **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-125">On the **File** menu, click **Close**.</span></span>

<span data-ttu-id="358c2-126">ファイルが最後に保存されてから変更された場合は、ファイルを保存するか破棄するかを選ぶメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="358c2-126">If the file has been altered since it was last saved, you are prompted to save or discard it.</span></span>

### <a name="to-display-the-file-path"></a><span data-ttu-id="358c2-127">ファイル パスを表示するには</span><span class="sxs-lookup"><span data-stu-id="358c2-127">To display the file path</span></span>

<span data-ttu-id="358c2-128">ファイル タブのファイル名をポイントします。</span><span class="sxs-lookup"><span data-stu-id="358c2-128">On the file tab, point to the file name.</span></span> <span data-ttu-id="358c2-129">スクリプト ファイルへの完全修飾パスがヒントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="358c2-129">The fully qualified path to the script file appears in a tooltip.</span></span>

### <a name="to-run-a-script"></a><span data-ttu-id="358c2-130">スクリプトを実行するには</span><span class="sxs-lookup"><span data-stu-id="358c2-130">To run a script</span></span>

<span data-ttu-id="358c2-131">ツール バーの **[スクリプトを実行]**、または **[ファイル]** メニューの **[実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-131">On the toolbar, click **Run Script**, or on the **File** menu, click **Run**.</span></span>

### <a name="to-run-a-portion-of-a-script"></a><span data-ttu-id="358c2-132">スクリプトの一部を実行するには</span><span class="sxs-lookup"><span data-stu-id="358c2-132">To run a portion of a script</span></span>

1. <span data-ttu-id="358c2-133">スクリプト ウィンドウで、スクリプトの一部を選択します。</span><span class="sxs-lookup"><span data-stu-id="358c2-133">In the Script Pane, select a portion of a script.</span></span>

2. <span data-ttu-id="358c2-134">**[ファイル]** メニューの **[選択項目を実行]**、またはツール バーの **[選択項目を実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-134">On the **File** menu, click **Run Selection**, or on the toolbar, click **Run Selection**.</span></span>

### <a name="to-stop-a-running-script"></a><span data-ttu-id="358c2-135">スクリプトの実行を停止するには</span><span class="sxs-lookup"><span data-stu-id="358c2-135">To stop a running script</span></span>

<span data-ttu-id="358c2-136">ツール バーの **[実行を中止]** をクリックするか、CTRL + BREAK キーを押すか、または、**[ファイル]** メニューの **[実行を中止]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-136">On the toolbar, click **Stop Operation**, press CTRL+BREAK, or on the **File** menu, click **Stop Operation**.</span></span> <span data-ttu-id="358c2-137">テキストが選択されていない場合は、**CTRL + C** キーを押すと、実行が停止します。テキストが選択されている場合は、**CTRL + C** キーは、選択したテキストのコピー機能にマップされます。</span><span class="sxs-lookup"><span data-stu-id="358c2-137">Pressing **CTRL+C** also works unless some text is currently selected, in which case **CTRL+C** maps to the copy function for the selected text.</span></span>

## <a name="how-to-write-and-edit-text-in-the-script-pane"></a><span data-ttu-id="358c2-138">スクリプト ウィンドウでテキストを記述して編集する方法</span><span class="sxs-lookup"><span data-stu-id="358c2-138">How to write and edit text in the Script Pane</span></span>

<span data-ttu-id="358c2-139">スクリプト ウィンドウでテキストを編集するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="358c2-139">Use the following steps to edit text in the Script Pane.</span></span> <span data-ttu-id="358c2-140">テキストのコピー、切り取り、貼り付け、検索、置換を実行できます。</span><span class="sxs-lookup"><span data-stu-id="358c2-140">You can copy, cut, paste, find, and replace text.</span></span> <span data-ttu-id="358c2-141">最後に実行した操作を元に戻したり、再実行したりできます。</span><span class="sxs-lookup"><span data-stu-id="358c2-141">You can also undo and redo the last action you just performed.</span></span> <span data-ttu-id="358c2-142">これらのアクションを実行するためのキーボード ショートカットは、すべての Windows アプリケーションで使われているものと同じです。</span><span class="sxs-lookup"><span data-stu-id="358c2-142">The keyboard shortcuts for performing these actions are the same as those used for all Windows applications.</span></span>

### <a name="to-enter-text-in-the-script-pane"></a><span data-ttu-id="358c2-143">スクリプト ウィンドウにテキストを入力するには</span><span class="sxs-lookup"><span data-stu-id="358c2-143">To enter text in the Script Pane</span></span>

1. <span data-ttu-id="358c2-144">カーソルをスクリプト ウィンドウに移すには、スクリプト ウィンドウ内の任意の場所をクリックするか、または **[表示]** メニューの **[スクリプト ウィンドウに移動]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-144">Move the cursor to the Script Pane by clicking anywhere in the Script Pane, or by clicking **Go to Script Pane** in the **View** menu.</span></span>

2. <span data-ttu-id="358c2-145">スクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="358c2-145">Create a script.</span></span> <span data-ttu-id="358c2-146">Windows PowerShell ISE では、入力しやすいように、構文の色分けやタブ補完の機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="358c2-146">Syntax coloring and tab completion make this a richer experience in Windows PowerShell ISE.</span></span>

3. <span data-ttu-id="358c2-147">入力中にタブ補完機能を使う方法について詳しくは、「[スクリプト ウィンドウとコンソール ウィンドウでタブ補完を使用する方法](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="358c2-147">See [How to Use Tab Completion in the Script Pane and Console Pane](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md) for details about using the tab completion feature to help in typing.</span></span>

### <a name="to-find-text-in-the-script-pane"></a><span data-ttu-id="358c2-148">スクリプト ウィンドウでテキストを検索するには</span><span class="sxs-lookup"><span data-stu-id="358c2-148">To find text in the Script Pane</span></span>

1. <span data-ttu-id="358c2-149">任意の場所にあるテキストを検索するには、**CTRL + F** キーを押すか、または **[編集]** メニューの **[スクリプト内を検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-149">To find text anywhere, press **CTRL+F** or, on the **Edit** menu, click **Find in Script**.</span></span>

2. <span data-ttu-id="358c2-150">カーソルより後の場所にあるテキストを検索するには、**F3** キーを押すか、または **[編集]** メニューの **[スクリプト内で次を検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-150">To find text after the cursor, press **F3** or, on the **Edit** menu, click **Find Next in Script**.</span></span>

3. <span data-ttu-id="358c2-151">カーソルより前の場所にあるテキストを検索するには、**SHIFT + F3** キーを押すか、または **[編集]** メニューの **[スクリプト内で前を検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-151">To find text before the cursor, press **SHIFT+F3** or, on the **Edit** menu, click **Find Previous in Script**.</span></span>

### <a name="to-find-and-replace-text-in-the-script-pane"></a><span data-ttu-id="358c2-152">スクリプト ウィンドウでテキストを検索して置換するには</span><span class="sxs-lookup"><span data-stu-id="358c2-152">To find and replace text in the Script Pane</span></span>

<span data-ttu-id="358c2-153">**Ctrl キーを押しながら H キー**を押すか、または **[編集]** メニューの **[スクリプト内で置換]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-153">Press **CTRL+H** or, on the **Edit** menu, click **Replace in Script**.</span></span> <span data-ttu-id="358c2-154">検索するテキストと、見つかったテキストを置換するテキストの両方を入力してから、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="358c2-154">Enter both the text you want to find and the text with which you want to replace it, and then press **ENTER**.</span></span>

### <a name="to-go-to-a-particular-line-of-text-in-the-script-pane"></a><span data-ttu-id="358c2-155">スクリプト ウィンドウ内のテキストの特定の行に移動するには</span><span class="sxs-lookup"><span data-stu-id="358c2-155">To go to a particular line of text in the Script Pane</span></span>

1. <span data-ttu-id="358c2-156">スクリプト ウィンドウで **CTRL + G** キーを押すか、または **[編集]** メニューの **[指定の行に移動]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-156">In the Script Pane, press **CTRL+G** or, on the **Edit** menu, click **Go to Line**.</span></span>

2. <span data-ttu-id="358c2-157">行番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="358c2-157">Enter a line number.</span></span>

### <a name="to-copy-text-in-the-script-pane"></a><span data-ttu-id="358c2-158">スクリプト ウィンドウでテキストをコピーするには</span><span class="sxs-lookup"><span data-stu-id="358c2-158">To copy text in the Script Pane</span></span>

1. <span data-ttu-id="358c2-159">スクリプト ウィンドウで、コピーするテキストを選択します。</span><span class="sxs-lookup"><span data-stu-id="358c2-159">In the Script Pane, select the text that you want to copy.</span></span>

2. <span data-ttu-id="358c2-160">**CTRL + C** キーを押すか、ツール バーで **[コピー]** アイコンをクリックするか、または **[編集]** メニューの **[コピー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-160">Press **CTRL+C** or, on the toolbar, click the **Copy** icon, or on the **Edit** menu, click **Copy**.</span></span>

### <a name="to-cut-text-in-the-script-pane"></a><span data-ttu-id="358c2-161">スクリプト ウィンドウでテキストを切り取るには</span><span class="sxs-lookup"><span data-stu-id="358c2-161">To cut text in the Script Pane</span></span>

1. <span data-ttu-id="358c2-162">スクリプト ウィンドウで、切り取るテキストを選択します。</span><span class="sxs-lookup"><span data-stu-id="358c2-162">In the Script Pane, select the text that you want to cut.</span></span>

2. <span data-ttu-id="358c2-163">**CTRL + X** キーを押すか、ツール バーで **[切り取り]** アイコンをクリックするか、または **[編集]** メニューの **[切り取り]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-163">Press **CTRL+X** or, on the toolbar, click the **Cut** icon, or on the **Edit** menu, click **Cut**.</span></span>

### <a name="to-paste-text-into-the-script-pane"></a><span data-ttu-id="358c2-164">スクリプト ウィンドウにテキストを貼り付けるには</span><span class="sxs-lookup"><span data-stu-id="358c2-164">To paste text into the Script Pane</span></span>

<span data-ttu-id="358c2-165">**CTRL + V** キーを押すか、ツール バーで **[貼り付け]** アイコンをクリックするか、または **[編集]** メニューの **[貼り付け]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-165">Press **CTRL+V** or, on the toolbar, click the **Paste** icon, or on the **Edit** menu, click **Paste**.</span></span>

### <a name="to-undo-an-action-in-the-script-pane"></a><span data-ttu-id="358c2-166">スクリプト ウィンドウ内のアクションを元に戻すには</span><span class="sxs-lookup"><span data-stu-id="358c2-166">To undo an action in the Script Pane</span></span>

<span data-ttu-id="358c2-167">**CTRL + Z** キーを押すか、ツール バーで **[元に戻す]** アイコンをクリックするか、または **[編集]** メニューの **[元に戻す]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-167">Press **CTRL+Z** or, on the toolbar, click the **Undo** icon, or on the **Edit** menu, click **Undo**.</span></span>

### <a name="to-redo-an-action-in-the-script-pane"></a><span data-ttu-id="358c2-168">スクリプト ウィンドウ内のアクションをやり直すには</span><span class="sxs-lookup"><span data-stu-id="358c2-168">To redo an action in the Script Pane</span></span>

<span data-ttu-id="358c2-169">**CTRL + Y** キーを押すか、ツール バーで **[やり直し]** アイコンをクリックするか、または **[編集]** メニューの **[やり直し]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-169">Press **CTRL+Y** or, on the toolbar, click the **Redo** icon, or on the **Edit** menu, click **Redo**.</span></span>

## <a name="how-to-save-a-script"></a><span data-ttu-id="358c2-170">スクリプトを保存する方法</span><span class="sxs-lookup"><span data-stu-id="358c2-170">How to save a script</span></span>

<span data-ttu-id="358c2-171">スクリプトに名前を付けて保存するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="358c2-171">Use the following steps to save and name a script.</span></span> <span data-ttu-id="358c2-172">変更されてから保存されていないファイルには、スクリプト名の横にアスタリスクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="358c2-172">An asterisk appears next to the script name to mark a file that has not been saved since it was altered.</span></span> <span data-ttu-id="358c2-173">ファイルを保存すると、アスタリスクは消えます。</span><span class="sxs-lookup"><span data-stu-id="358c2-173">The asterisk disappears when the file is saved.</span></span>

### <a name="to-save-a-script"></a><span data-ttu-id="358c2-174">スクリプトを保存するには</span><span class="sxs-lookup"><span data-stu-id="358c2-174">To save a script</span></span>

<span data-ttu-id="358c2-175">**CTRL + S** キーを押すか、ツール バーで **[保存]** アイコンをクリックするか、または **[ファイル]** メニューの **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-175">Press **CTRL+S** or, on the toolbar, click the **Save** icon, or on the **File** menu, click **Save**.</span></span>

### <a name="to-save-and-name-a-script"></a><span data-ttu-id="358c2-176">スクリプトに名前を付けて保存するには</span><span class="sxs-lookup"><span data-stu-id="358c2-176">To save and name a script</span></span>

1. <span data-ttu-id="358c2-177">**[ファイル]** メニューの **[名前を付けて保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-177">On the **File** menu, click **Save As**.</span></span> <span data-ttu-id="358c2-178">**[名前を付けて保存]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="358c2-178">The **Save As** dialog box will appear.</span></span>

2. <span data-ttu-id="358c2-179">**[ファイル名]** ボックスに、ファイルの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="358c2-179">In the **File name** box, enter a name for the file.</span></span>

3. <span data-ttu-id="358c2-180">**[ファイルの種類]** ボックスで、ファイルの種類を選びます。</span><span class="sxs-lookup"><span data-stu-id="358c2-180">In the **Save as type** box, select a file type.</span></span> <span data-ttu-id="358c2-181">たとえば、**[ファイルの種類]** ボックスで、[PowerShell スクリプト (\*.ps1)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="358c2-181">For example, in the **Save as type** box, select 'œPowerShell Scripts (\* .ps1)'.</span></span>

4. <span data-ttu-id="358c2-182">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="358c2-182">Click **Save**.</span></span>

### <a name="to-save-a-script-in-ascii-encoding"></a><span data-ttu-id="358c2-183">ASCII エンコードでスクリプトを保存するには</span><span class="sxs-lookup"><span data-stu-id="358c2-183">To save a script in ASCII encoding</span></span>

<span data-ttu-id="358c2-184">既定では、Windows PowerShell ISE は新しいスクリプト ファイル (.ps1)、スクリプト データ ファイル (.psd1)、スクリプト モジュール ファイル (.psm1) を Unicode (BigEndianUnicode) として保存します。ASCII (ANSI) など、別のエンコードでスクリプトを保存するには、[$psISE.CurrentFile](https://technet.microsoft.com/library/bc3300e4-9c17-4f00-a621-c8867126e3b3#CurrentFile) オブジェクトの **Save** または **SaveAs** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="358c2-184">By default, Windows PowerShell ISE saves new script files (.ps1), script data files (.psd1), and script module files (.psm1) as Unicode (BigEndianUnicode) by default.Â To save a script in another encoding, such as ASCII (ANSI), use the **Save** or **SaveAs** methods on the [$psISE.CurrentFile](https://technet.microsoft.com/library/bc3300e4-9c17-4f00-a621-c8867126e3b3#CurrentFile) object.</span></span>

<span data-ttu-id="358c2-185">次のコマンドでは、新しいスクリプトを MyScript.ps1 という名前の ASCII エンコードで保存します。</span><span class="sxs-lookup"><span data-stu-id="358c2-185">The following command saves a new script as MyScript.ps1 with ASCII encoding.</span></span>

```powershell
$psISE.CurrentFile.SaveAs("MyScript.ps1", [System.Text.Encoding]::ASCII)
```

<span data-ttu-id="358c2-186">次のコマンドでは、現在のスクリプト ファイルと同じ名前の ASCII エンコードのファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="358c2-186">The following command replaces the current script file with a file with the same name, but with ASCII encoding.</span></span>

```powershell
$psISE.CurrentFile.Save([System.Text.Encoding]::ASCII)
```

<span data-ttu-id="358c2-187">次のコマンドでは、現在のファイルのエンコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="358c2-187">The following command gets the encoding of the current file.</span></span>

```powershell
$psISE.CurrentFile.encoding
```

<span data-ttu-id="358c2-188">Windows PowerShell ISE では、次のエンコード オプションをサポートしています: ASCII、BigEndianUnicode、Unicode、UTF32、UTF7、UTF8、既定値。</span><span class="sxs-lookup"><span data-stu-id="358c2-188">Windows PowerShell ISE supports the following encoding options: ASCII, BigEndianUnicode, Unicode, UTF32, UTF7, UTF8 and Default.</span></span> <span data-ttu-id="358c2-189">既定値オプションの値は、システムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="358c2-189">The value of the Default option varies with the system.</span></span>

<span data-ttu-id="358c2-190">Windows PowerShell ISE では、Windows PowerShell ISE の [保存] または [名前を付けて保存] コマンドを使った場合でも、他のエディターによって作成されたスクリプトのエンコードは変更しません。</span><span class="sxs-lookup"><span data-stu-id="358c2-190">Windows PowerShell ISE does not change the encoding of scripts that were created by in other editors, even when you use the Save or Save As commands in Windows PowerShell ISE.</span></span>

## <a name="see-also"></a><span data-ttu-id="358c2-191">参照</span><span class="sxs-lookup"><span data-stu-id="358c2-191">See Also</span></span>

- [<span data-ttu-id="358c2-192">Windows PowerShell ISE の操作</span><span class="sxs-lookup"><span data-stu-id="358c2-192">Exploring the Windows PowerShell ISE</span></span>](../../getting-started/fundamental/exploring-the-windows-powershell-ise.md)