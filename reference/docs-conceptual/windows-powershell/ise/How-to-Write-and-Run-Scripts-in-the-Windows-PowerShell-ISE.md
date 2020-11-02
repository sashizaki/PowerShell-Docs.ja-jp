---
ms.date: 01/02/2020
title: Windows PowerShell ISE でスクリプトを記述および実行する方法
description: この記事では、スクリプト ウィンドウでスクリプトを作成、編集、実行、保存する方法について説明します。
ms.openlocfilehash: 8e85da1d4eecbb975f2dd799c91512e0081309d2
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663645"
---
# <a name="how-to-write-and-run-scripts-in-the-windows-powershell-ise"></a><span data-ttu-id="c846b-103">Windows PowerShell ISE でスクリプトを記述および実行する方法</span><span class="sxs-lookup"><span data-stu-id="c846b-103">How to Write and Run Scripts in the Windows PowerShell ISE</span></span>

<span data-ttu-id="c846b-104">この記事では、スクリプト ウィンドウでスクリプトを作成、編集、実行、保存する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c846b-104">This article describes how to create, edit, run, and save scripts in the Script Pane.</span></span>

## <a name="how-to-create-and-run-scripts"></a><span data-ttu-id="c846b-105">スクリプトを作成して実行する方法</span><span class="sxs-lookup"><span data-stu-id="c846b-105">How to create and run scripts</span></span>

<span data-ttu-id="c846b-106">Windows PowerShell ファイルは、スクリプト ウィンドウで開いたり、編集したりできます。</span><span class="sxs-lookup"><span data-stu-id="c846b-106">You can open and edit Windows PowerShell files in the Script Pane.</span></span> <span data-ttu-id="c846b-107">Windows PowerShell で対象となるファイルの種類は、スクリプト ファイル (`.ps1`)、スクリプト データ ファイル (`.psd1`)、スクリプト モジュール ファイル (`.psm1`) です。</span><span class="sxs-lookup"><span data-stu-id="c846b-107">Specific file types of interest in Windows PowerShell are script files (`.ps1`), script data files (`.psd1`), and script module files (`.psm1`).</span></span> <span data-ttu-id="c846b-108">これらのファイルの種類は、スクリプト ウィンドウのエディターで構文が色分けされます。</span><span class="sxs-lookup"><span data-stu-id="c846b-108">These file types are syntax colored in the Script Pane editor.</span></span> <span data-ttu-id="c846b-109">スクリプト ウィンドウで開くことのできる他の一般的なファイルの種類には、構成ファイル (`.ps1xml`)、XML ファイル、テキスト ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="c846b-109">Other common file types you may open in the Script Pane are configuration files (`.ps1xml`), XML files, and text files.</span></span>

> [!NOTE]
> <span data-ttu-id="c846b-110">Windows PowerShell の実行ポリシーによって、スクリプトの実行や、Windows PowerShell のプロファイルと構成ファイルの読み込みを実行できるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="c846b-110">The Windows PowerShell execution policy determines whether you can run scripts and load Windows PowerShell profiles and configuration files.</span></span> <span data-ttu-id="c846b-111">既定の実行ポリシー Restricted では、すべてのスクリプトの実行とプロファイルの読み込みが防止されます。</span><span class="sxs-lookup"><span data-stu-id="c846b-111">The default execution policy, Restricted, prevents all scripts from running, and prevents loading profiles.</span></span> <span data-ttu-id="c846b-112">プロファイルの、読み込みと使用を許可するように実行ポリシーを変更する方法については、「[Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy)」と「[about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c846b-112">To change the execution policy to allow profiles to load and be used, see [Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy) and [about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing).</span></span>

### <a name="to-create-a-new-script-file"></a><span data-ttu-id="c846b-113">新しいスクリプト ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="c846b-113">To create a new script file</span></span>

<span data-ttu-id="c846b-114">ツール バーの **[新規作成]** 、または **[ファイル]** メニューの **[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c846b-114">On the toolbar, click **New** , or on the **File** menu, click **New** .</span></span> <span data-ttu-id="c846b-115">作成されたファイルは、現在の PowerShell タブの下に新しいファイル タブとして表示されます。PowerShell のタブは、少なくとも 1 つのタブが存在する場合にのみ表示されることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="c846b-115">The created file appears in a new file tab under the current PowerShell tab. Remember that the PowerShell tabs are only visible when there are more than one.</span></span> <span data-ttu-id="c846b-116">既定では種類のスクリプトのファイル (`.ps1`) が作成されますが、そのファイルに新しい名前や拡張子を指定して保存できます。</span><span class="sxs-lookup"><span data-stu-id="c846b-116">By default a file of type script (`.ps1`) is created, but it can be saved with a new name and extension.</span></span> <span data-ttu-id="c846b-117">同じ PowerShell タブ内に複数のスクリプト ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c846b-117">Multiple script files can be created in the same PowerShell tab.</span></span>

### <a name="to-open-an-existing-script"></a><span data-ttu-id="c846b-118">既存のスクリプトを開くには</span><span class="sxs-lookup"><span data-stu-id="c846b-118">To open an existing script</span></span>

<span data-ttu-id="c846b-119">ツール バーの **[開く]** 、または **[ファイル]** メニューの **[開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c846b-119">On the toolbar, click **Open** , or on the **File** menu, click **Open** .</span></span> <span data-ttu-id="c846b-120">**[開く]** ダイアログ ボックスで、開くファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="c846b-120">In the **Open** dialog box, select the file you want to open.</span></span> <span data-ttu-id="c846b-121">開いたファイルが新しいタブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c846b-121">The opened file appears in a new tab.</span></span>

### <a name="to-close-a-script-tab"></a><span data-ttu-id="c846b-122">スクリプト タブを閉じるには</span><span class="sxs-lookup"><span data-stu-id="c846b-122">To close a script tab</span></span>

<span data-ttu-id="c846b-123">閉じたいファイル タブの **[閉じる]** アイコン ( **[X]** ) をクリックするか、または **[ファイル]** メニューを選択して **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c846b-123">Click the **Close** icon ( **X** ) of the file tab you want to close or select the **File** menu and click **Close** .</span></span>

<span data-ttu-id="c846b-124">ファイルが最後に保存されてから変更された場合は、ファイルを保存するか破棄するかを選ぶメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c846b-124">If the file has been altered since it was last saved, you're prompted to save or discard it.</span></span>

### <a name="to-display-the-file-path"></a><span data-ttu-id="c846b-125">ファイル パスを表示するには</span><span class="sxs-lookup"><span data-stu-id="c846b-125">To display the file path</span></span>

<span data-ttu-id="c846b-126">ファイル タブのファイル名をポイントします。</span><span class="sxs-lookup"><span data-stu-id="c846b-126">On the file tab, point to the file name.</span></span> <span data-ttu-id="c846b-127">スクリプト ファイルへの完全修飾パスがヒントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c846b-127">The fully qualified path to the script file appears in a tooltip.</span></span>

### <a name="to-run-a-script"></a><span data-ttu-id="c846b-128">スクリプトを実行するには</span><span class="sxs-lookup"><span data-stu-id="c846b-128">To run a script</span></span>

<span data-ttu-id="c846b-129">ツール バーの **[スクリプトを実行]** 、または **[ファイル]** メニューの **[実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c846b-129">On the toolbar, click **Run Script** , or on the **File** menu, click **Run** .</span></span>

### <a name="to-run-a-portion-of-a-script"></a><span data-ttu-id="c846b-130">スクリプトの一部を実行するには</span><span class="sxs-lookup"><span data-stu-id="c846b-130">To run a portion of a script</span></span>

1. <span data-ttu-id="c846b-131">スクリプト ウィンドウで、スクリプトの一部を選択します。</span><span class="sxs-lookup"><span data-stu-id="c846b-131">In the Script Pane, select a portion of a script.</span></span>
2. <span data-ttu-id="c846b-132">**[ファイル]** メニューの **[選択項目を実行]** 、またはツール バーの **[選択項目を実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c846b-132">On the **File** menu, click **Run Selection** , or on the toolbar, click **Run Selection** .</span></span>

### <a name="to-stop-a-running-script"></a><span data-ttu-id="c846b-133">スクリプトの実行を停止するには</span><span class="sxs-lookup"><span data-stu-id="c846b-133">To stop a running script</span></span>

<span data-ttu-id="c846b-134">実行中のスクリプトを停止するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="c846b-134">There are several ways to stop a running script.</span></span>

- <span data-ttu-id="c846b-135">ツールバーの **[操作の停止]** をクリックする</span><span class="sxs-lookup"><span data-stu-id="c846b-135">Click **Stop Operation** on the toolbar</span></span>
- <span data-ttu-id="c846b-136"><kbd>Ctrl</kbd> + <kbd>Break</kbd> キーを押す</span><span class="sxs-lookup"><span data-stu-id="c846b-136">Press <kbd>CTRL</kbd>+<kbd>BREAK</kbd></span></span>
- <span data-ttu-id="c846b-137">**[ファイル]** メニューを選択して、 **[操作の停止]** をクリックする</span><span class="sxs-lookup"><span data-stu-id="c846b-137">Select the **File** menu and click **Stop Operation** .</span></span>

<span data-ttu-id="c846b-138">テキストが選択されていない場合は、<kbd>Ctrl</kbd> + <kbd>C</kbd> キーを押すと、実行が停止します。テキストが選択されている場合は、<kbd>Ctrl</kbd> + <kbd>C</kbd> キーは、選択したテキストのコピー機能にマップされます。</span><span class="sxs-lookup"><span data-stu-id="c846b-138">Pressing <kbd>CTRL</kbd>+<kbd>C</kbd> also works unless some text is currently selected, in which case <kbd>CTRL</kbd>+<kbd>C</kbd> maps to the copy function for the selected text.</span></span>

## <a name="how-to-write-and-edit-text-in-the-script-pane"></a><span data-ttu-id="c846b-139">スクリプト ウィンドウでテキストを記述して編集する方法</span><span class="sxs-lookup"><span data-stu-id="c846b-139">How to write and edit text in the Script Pane</span></span>

<span data-ttu-id="c846b-140">スクリプト ペインで、テキストのコピー、切り取り、貼り付け、検索、および置換を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c846b-140">You can copy, cut, paste, find, and replace text in the Script Pane.</span></span> <span data-ttu-id="c846b-141">最後に実行した操作を元に戻したり、再実行したりできます。</span><span class="sxs-lookup"><span data-stu-id="c846b-141">You can also undo and redo the last action you just performed.</span></span> <span data-ttu-id="c846b-142">これらのアクションのキーボード ショートカットは、すべての Windows アプリケーションで使われているショートカットと同じです。</span><span class="sxs-lookup"><span data-stu-id="c846b-142">The keyboard shortcuts for these actions are the same shortcuts used for all Windows applications.</span></span>

### <a name="to-enter-text-in-the-script-pane"></a><span data-ttu-id="c846b-143">スクリプト ウィンドウにテキストを入力するには</span><span class="sxs-lookup"><span data-stu-id="c846b-143">To enter text in the Script Pane</span></span>

1. <span data-ttu-id="c846b-144">カーソルをスクリプト ウィンドウに移すには、スクリプト ウィンドウ内の任意の場所をクリックするか、または **[表示]** メニューの **[スクリプト ウィンドウに移動]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c846b-144">Move the cursor to the Script Pane by clicking anywhere in the Script Pane, or by clicking **Go to Script Pane** in the **View** menu.</span></span>
2. <span data-ttu-id="c846b-145">スクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c846b-145">Create a script.</span></span> <span data-ttu-id="c846b-146">Windows PowerShell ISE では、編集しやすいように、構文の色分けやタブ補完の機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="c846b-146">Syntax coloring and tab completion provide a richer editing experience in Windows PowerShell ISE.</span></span>
3. <span data-ttu-id="c846b-147">入力中にタブ補完機能を使う方法について詳しくは、「[スクリプト ウィンドウとコンソール ウィンドウでタブ補完を使用する方法](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c846b-147">See [How to Use Tab Completion in the Script Pane and Console Pane](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md) for details about using the tab completion feature to help in typing.</span></span>

### <a name="to-find-text-in-the-script-pane"></a><span data-ttu-id="c846b-148">スクリプト ウィンドウでテキストを検索するには</span><span class="sxs-lookup"><span data-stu-id="c846b-148">To find text in the Script Pane</span></span>

1. <span data-ttu-id="c846b-149">任意の場所にあるテキストを検索するには、 <kbd>Ctrl</kbd> + <kbd>F</kbd> キーを押すか、または **[編集]** メニューの **[スクリプト内を検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c846b-149">To find text anywhere, press <kbd>CTRL</kbd>+<kbd>F</kbd> or, on the **Edit** menu, click **Find in Script** .</span></span>
2. <span data-ttu-id="c846b-150">カーソルより後の場所にあるテキストを検索するには、 <kbd>F3</kbd> キーを押すか、または **[編集]** メニューの **[スクリプト内で次を検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c846b-150">To find text after the cursor, press <kbd>F3</kbd> or, on the **Edit** menu, click **Find Next in Script** .</span></span>
3. <span data-ttu-id="c846b-151">カーソルより前の場所にあるテキストを検索するには、 <kbd>Shift</kbd> + <kbd>F3</kbd> キーを押すか、または **[編集]** メニューの **[スクリプト内で前を検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c846b-151">To find text before the cursor, press <kbd>SHIFT</kbd>+<kbd>F3</kbd> or, on the **Edit** menu, click **Find Previous in Script** .</span></span>

### <a name="to-find-and-replace-text-in-the-script-pane"></a><span data-ttu-id="c846b-152">スクリプト ウィンドウでテキストを検索して置換するには</span><span class="sxs-lookup"><span data-stu-id="c846b-152">To find and replace text in the Script Pane</span></span>

<span data-ttu-id="c846b-153"><kbd>Ctrl</kbd> + <kbd>H</kbd> キーを押すか、または **[編集]** メニューの **[スクリプト内で置換]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c846b-153">Press <kbd>CTRL</kbd>+<kbd>H</kbd> or, on the **Edit** menu, click **Replace in Script** .</span></span> <span data-ttu-id="c846b-154">検索するテキストと置換後のテキストを入力して、<kbd>ENTER</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c846b-154">Enter the text you want to find and the replacement text, then press <kbd>ENTER</kbd>.</span></span>

### <a name="to-go-to-a-particular-line-of-text-in-the-script-pane"></a><span data-ttu-id="c846b-155">スクリプト ウィンドウ内のテキストの特定の行に移動するには</span><span class="sxs-lookup"><span data-stu-id="c846b-155">To go to a particular line of text in the Script Pane</span></span>

1. <span data-ttu-id="c846b-156">スクリプト ウィンドウで <kbd>Ctrl</kbd> + <kbd>G</kbd> キーを押すか、または **[編集]** メニューの **[指定の行に移動]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c846b-156">In the Script Pane, press <kbd>CTRL</kbd>+<kbd>G</kbd> or, on the **Edit** menu, click **Go to Line** .</span></span>

2. <span data-ttu-id="c846b-157">行番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="c846b-157">Enter a line number.</span></span>

### <a name="to-copy-text-in-the-script-pane"></a><span data-ttu-id="c846b-158">スクリプト ウィンドウでテキストをコピーするには</span><span class="sxs-lookup"><span data-stu-id="c846b-158">To copy text in the Script Pane</span></span>

1. <span data-ttu-id="c846b-159">スクリプト ウィンドウで、コピーするテキストを選択します。</span><span class="sxs-lookup"><span data-stu-id="c846b-159">In the Script Pane, select the text that you want to copy.</span></span>

2. <span data-ttu-id="c846b-160"><kbd>Ctrl</kbd> + <kbd>C</kbd> キーを押すか、ツール バーで **[コピー]** アイコンをクリックするか、または **[編集]** メニューの **[コピー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c846b-160">Press <kbd>CTRL</kbd>+<kbd>C</kbd> or, on the toolbar, click the **Copy** icon, or on the **Edit** menu, click **Copy** .</span></span>

### <a name="to-cut-text-in-the-script-pane"></a><span data-ttu-id="c846b-161">スクリプト ウィンドウでテキストを切り取るには</span><span class="sxs-lookup"><span data-stu-id="c846b-161">To cut text in the Script Pane</span></span>

1. <span data-ttu-id="c846b-162">スクリプト ウィンドウで、切り取るテキストを選択します。</span><span class="sxs-lookup"><span data-stu-id="c846b-162">In the Script Pane, select the text that you want to cut.</span></span>
2. <span data-ttu-id="c846b-163"><kbd>Ctrl</kbd> + <kbd></kbd>X **キーを押すか、ツール バーで** [切り取り] **アイコンをクリックするか、または** [編集] **メニューの** [切り取り] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c846b-163">Press <kbd>CTRL</kbd>+<kbd>X</kbd> or, on the toolbar, click the **Cut** icon, or on the **Edit** menu, click **Cut** .</span></span>

### <a name="to-paste-text-into-the-script-pane"></a><span data-ttu-id="c846b-164">スクリプト ウィンドウにテキストを貼り付けるには</span><span class="sxs-lookup"><span data-stu-id="c846b-164">To paste text into the Script Pane</span></span>

<span data-ttu-id="c846b-165"><kbd>Ctrl</kbd> + <kbd>V</kbd> キーを押すか、ツール バーで **[貼り付け]** アイコンをクリックするか、または **[編集]** メニューの **[貼り付け]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c846b-165">Press <kbd>CTRL</kbd>+<kbd>V</kbd> or, on the toolbar, click the **Paste** icon, or on the **Edit** menu, click **Paste** .</span></span>

### <a name="to-undo-an-action-in-the-script-pane"></a><span data-ttu-id="c846b-166">スクリプト ウィンドウ内のアクションを元に戻すには</span><span class="sxs-lookup"><span data-stu-id="c846b-166">To undo an action in the Script Pane</span></span>

<span data-ttu-id="c846b-167"><kbd>Ctrl</kbd> + <kbd>Z</kbd> キーを押すか、ツール バーで **[元に戻す]** アイコンをクリックするか、または **[編集]** メニューの **[元に戻す]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c846b-167">Press <kbd>CTRL</kbd>+<kbd>Z</kbd> or, on the toolbar, click the **Undo** icon, or on the **Edit** menu, click **Undo** .</span></span>

### <a name="to-redo-an-action-in-the-script-pane"></a><span data-ttu-id="c846b-168">スクリプト ウィンドウ内のアクションをやり直すには</span><span class="sxs-lookup"><span data-stu-id="c846b-168">To redo an action in the Script Pane</span></span>

<span data-ttu-id="c846b-169"><kbd>Ctrl</kbd> + <kbd>Y</kbd> キーを押すか、ツール バーで **[やり直し]** アイコンをクリックするか、または **[編集]** メニューの **[やり直し]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c846b-169">Press <kbd>CTRL</kbd>+<kbd>Y</kbd> or, on the toolbar, click the **Redo** icon, or on the **Edit** menu, click **Redo** .</span></span>

## <a name="how-to-save-a-script"></a><span data-ttu-id="c846b-170">スクリプトを保存する方法</span><span class="sxs-lookup"><span data-stu-id="c846b-170">How to save a script</span></span>

<span data-ttu-id="c846b-171">変更されてから保存されていないファイルには、スクリプト名の横にアスタリスクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c846b-171">An asterisk appears next to the script name to mark a file that hasn't been saved since it was changed.</span></span> <span data-ttu-id="c846b-172">ファイルを保存すると、アスタリスクは消えます。</span><span class="sxs-lookup"><span data-stu-id="c846b-172">The asterisk disappears when the file is saved.</span></span>

### <a name="to-save-a-script"></a><span data-ttu-id="c846b-173">スクリプトを保存するには</span><span class="sxs-lookup"><span data-stu-id="c846b-173">To save a script</span></span>

<span data-ttu-id="c846b-174"><kbd>Ctrl</kbd> + <kbd>S</kbd> キーを押すか、ツール バーで **[保存]** アイコンをクリックするか、または **[ファイル]** メニューの **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c846b-174">Press <kbd>CTRL</kbd>+<kbd>S</kbd> or, on the toolbar, click the **Save** icon, or on the **File** menu, click **Save** .</span></span>

### <a name="to-save-and-name-a-script"></a><span data-ttu-id="c846b-175">スクリプトに名前を付けて保存するには</span><span class="sxs-lookup"><span data-stu-id="c846b-175">To save and name a script</span></span>

1. <span data-ttu-id="c846b-176">**[ファイル]** メニューの **[名前を付けて保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c846b-176">On the **File** menu, click **Save As** .</span></span> <span data-ttu-id="c846b-177">**[名前を付けて保存]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c846b-177">The **Save As** dialog box will appear.</span></span>
2. <span data-ttu-id="c846b-178">**[ファイル名]** ボックスに、ファイルの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c846b-178">In the **File name** box, enter a name for the file.</span></span>
3. <span data-ttu-id="c846b-179">**[ファイルの種類]** ボックスで、ファイルの種類を選びます。</span><span class="sxs-lookup"><span data-stu-id="c846b-179">In the **Save as type** box, select a file type.</span></span> <span data-ttu-id="c846b-180">たとえば、 **[ファイルの種類]** ボックスで、[PowerShell スクリプト (`*.ps1`1)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c846b-180">For example, in the **Save as type** box, select 'PowerShell Scripts (`*.ps1`)'.</span></span>
4. <span data-ttu-id="c846b-181">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c846b-181">Click **Save** .</span></span>

### <a name="to-save-a-script-in-ascii-encoding"></a><span data-ttu-id="c846b-182">ASCII エンコードでスクリプトを保存するには</span><span class="sxs-lookup"><span data-stu-id="c846b-182">To save a script in ASCII encoding</span></span>

<span data-ttu-id="c846b-183">既定では、Windows PowerShell ISE は新しいスクリプト ファイル (`.ps1`)、スクリプト データ ファイル (`.psd1`)、スクリプト モジュール ファイル (`.psm1`) を Unicode (BigEndianUnicode) として保存します。</span><span class="sxs-lookup"><span data-stu-id="c846b-183">By default, Windows PowerShell ISE saves new script files (`.ps1`), script data files (`.psd1`), and script module files (`.psm1`) as Unicode (BigEndianUnicode) by default.</span></span> <span data-ttu-id="c846b-184">ASCII (ANSI) など、別のエンコードでスクリプトを保存するには、 [$psISE.CurrentFile](object-model/the-ise-object-model-hierarchy.md) オブジェクトの **Save** または **SaveAs** メソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="c846b-184">To save a script in another encoding, such as ASCII (ANSI), use the **Save** or **SaveAs** methods on the [$psISE.CurrentFile](object-model/the-ise-object-model-hierarchy.md) object.</span></span>

<span data-ttu-id="c846b-185">次のコマンドでは、新しいスクリプトを MyScript.ps1 という名前の ASCII エンコードで保存します。</span><span class="sxs-lookup"><span data-stu-id="c846b-185">The following command saves a new script as MyScript.ps1 with ASCII encoding.</span></span>

```powershell
$psISE.CurrentFile.SaveAs("MyScript.ps1", [System.Text.Encoding]::ASCII)
```

<span data-ttu-id="c846b-186">次のコマンドでは、現在のスクリプト ファイルと同じ名前の ASCII エンコードのファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c846b-186">The following command replaces the current script file with a file with the same name, but with ASCII encoding.</span></span>

```powershell
$psISE.CurrentFile.Save([System.Text.Encoding]::ASCII)
```

<span data-ttu-id="c846b-187">次のコマンドでは、現在のファイルのエンコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="c846b-187">The following command gets the encoding of the current file.</span></span>

```powershell
$psISE.CurrentFile.encoding
```

<span data-ttu-id="c846b-188">Windows PowerShell ISE では、次のエンコード オプションがサポートされています: ASCII、BigEndianUnicode、Unicode、UTF32、UTF7、UTF8、Default。</span><span class="sxs-lookup"><span data-stu-id="c846b-188">Windows PowerShell ISE supports the following encoding options: ASCII, BigEndianUnicode, Unicode, UTF32, UTF7, UTF8, and Default.</span></span> <span data-ttu-id="c846b-189">既定値オプションの値は、システムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c846b-189">The value of the Default option varies with the system.</span></span>

<span data-ttu-id="c846b-190">Save または Save As コマンドを使用した場合、Windows PowerShell ISE ではスクリプト ファイルのエンコードを変更しません。</span><span class="sxs-lookup"><span data-stu-id="c846b-190">Windows PowerShell ISE doesn't change the encoding of script files when you use the Save or Save As commands.</span></span>

## <a name="see-also"></a><span data-ttu-id="c846b-191">参照</span><span class="sxs-lookup"><span data-stu-id="c846b-191">See Also</span></span>

- [<span data-ttu-id="c846b-192">Windows PowerShell ISE の操作</span><span class="sxs-lookup"><span data-stu-id="c846b-192">Exploring the Windows PowerShell ISE</span></span>](exploring-the-windows-powershell-ise.md)
