---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "Windows PowerShell ISE でスクリプトをデバッグする方法"
ms.assetid: 6dc6d8f9-8978-46e9-a92f-169af37e2817
ms.openlocfilehash: 2b8313c3f2ae1a8fb670099baa8950db49722330
ms.sourcegitcommit: 4102ecc35d473211f50a453f6ae3fbea31cb3428
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2017
---
# <a name="how-to-debug-scripts-in-windows-powershell-ise"></a><span data-ttu-id="068fa-103">Windows PowerShell ISE でスクリプトをデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="068fa-103">How to Debug Scripts in Windows PowerShell ISE</span></span>
<span data-ttu-id="068fa-104">このトピックでは、Windows PowerShell® Integrated Scripting Environment (ISE) のビジュアル デバッグ機能を使ってローカル コンピューター上でスクリプトをデバッグする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="068fa-104">This topic describes how to debug scripts on a local computer by using the Windows PowerShell® Integrated Scripting Environment (ISE) visual debugging features.</span></span>

<span data-ttu-id="068fa-105">[ブレークポイントを管理する方法]()
[デバッグ セッションを管理する方法]()
[デバッグ中にステップ オーバー、ステップ イン、ステップ アウトする方法]()
[デバッグ中に変数の値を表示する方法]()</span><span class="sxs-lookup"><span data-stu-id="068fa-105">[How to manage breakpoints]()
[How to manage a debugging session]()
[How to step over, step into, and step out while debugging]()
[How to display the values of variables while debugging]()</span></span>

## <span data-ttu-id="068fa-106"><a name="bkmk_1"></a>ブレークポイントを管理する方法</span><span class="sxs-lookup"><span data-stu-id="068fa-106"><a name="bkmk_1"></a>How to manage breakpoints</span></span>
<span data-ttu-id="068fa-107">ブレークポイントは、操作を一時停止するように指定したスクリプト内の位置です。一時停止している間に、変数の現在の状態や、スクリプトが実行されている環境を確認できます。</span><span class="sxs-lookup"><span data-stu-id="068fa-107">A breakpoint is a designated spot in a script where you would like operation to pause so that you can examine the current state of the variables and the environment in which your script is running.</span></span> <span data-ttu-id="068fa-108">スクリプトがブレークポイントで一時停止したら、コンソール ウィンドウでコマンドを実行して、スクリプトの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="068fa-108">Once your script is paused by a breakpoint, you can run commands in the Console Pane to examine the state of your script.</span></span>  <span data-ttu-id="068fa-109">変数を出力したり、その他のコマンドを実行したりできます。</span><span class="sxs-lookup"><span data-stu-id="068fa-109">You can output variables or run other commands.</span></span> <span data-ttu-id="068fa-110">また、現在実行しているスクリプトのコンテキストで表示されているすべての変数の値を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="068fa-110">You can even modify the value of any variables that are visible to the context of the currently running script.</span></span> <span data-ttu-id="068fa-111">必要な事項を確認した後、スクリプトの操作を再開できます。</span><span class="sxs-lookup"><span data-stu-id="068fa-111">After you have examined what you want to see, you can resume operation of the script.</span></span>

<span data-ttu-id="068fa-112">Windows PowerShell のデバッグ環境では、次の 3 種類のブレークポイントを設定できます。</span><span class="sxs-lookup"><span data-stu-id="068fa-112">You can set three types of breakpoints in the Windows PowerShell debugging environment:</span></span>

1.  <span data-ttu-id="068fa-113">**行のブレークポイント**。</span><span class="sxs-lookup"><span data-stu-id="068fa-113">**Line breakpoint**.</span></span> <span data-ttu-id="068fa-114">スクリプトの操作中に指定した行に達すると、スクリプトは一時停止します。</span><span class="sxs-lookup"><span data-stu-id="068fa-114">The script pauses when the designated line is reached during the operation of the script</span></span>

2.  <span data-ttu-id="068fa-115">**変数のブレークポイント。**</span><span class="sxs-lookup"><span data-stu-id="068fa-115">**Variable breakpoint.**</span></span> <span data-ttu-id="068fa-116">指定した変数の値が変更されるたびに、スクリプトは一時停止します。</span><span class="sxs-lookup"><span data-stu-id="068fa-116">The script pauses whenever the designated variable’s value changes.</span></span>

3.  <span data-ttu-id="068fa-117">**コマンドのブレークポイント。**</span><span class="sxs-lookup"><span data-stu-id="068fa-117">**Command breakpoint.**</span></span> <span data-ttu-id="068fa-118">スクリプトの操作中、指定したコマンドを実行する前に、スクリプトは一時停止します。</span><span class="sxs-lookup"><span data-stu-id="068fa-118">The script pauses whenever the designated command is about to be run during the operation of the script.</span></span> <span data-ttu-id="068fa-119">ブレークポイントを必要な操作のみにフィルターで絞り込むために、パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="068fa-119">It can include parameters to further filter the breakpoint to only the operation you want.</span></span> <span data-ttu-id="068fa-120">コマンドには、作成した関数を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="068fa-120">The command can also be a function you created.</span></span>

<span data-ttu-id="068fa-121">この 3 種類のうち、行のブレークポイントだけは、Windows PowerShell ISE デバッグ環境で、メニューやキーボード ショートカットを使って設定できます。</span><span class="sxs-lookup"><span data-stu-id="068fa-121">Of these, in the Windows PowerShell ISE debugging environment, only line breakpoints can be set by using the menu or the keyboard shortcuts.</span></span> <span data-ttu-id="068fa-122">他の 2 つの種類のブレークポイントは、コンソール ウィンドウから [Set-PSBreakpoint ](https://technet.microsoft.com/library/88d2d9ad-17dc-44ae-99aa-f841125b9dc8) コマンドレットを使って設定できます。</span><span class="sxs-lookup"><span data-stu-id="068fa-122">The other two types of breakpoints can be set, but they are set from the Console Pane by using the [Set-PSBreakpoint](https://technet.microsoft.com/library/88d2d9ad-17dc-44ae-99aa-f841125b9dc8) cmdlet.</span></span> <span data-ttu-id="068fa-123">このセクションでは、Windows PowerShell ISE でメニューが使用可能な場合は使用してデバッグ作業を実行する方法と、スクリプトを使用してさまざまなコマンドをコンソール ウィンドウから実行する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="068fa-123">This section describes how you can perform debugging tasks in Windows PowerShell ISE by using the menus where available, and perform a wider range of commands from the Console Pane by using scripting.</span></span>

### <a name="to-set-a-breakpoint"></a><span data-ttu-id="068fa-124">ブレークポイントを設定するには</span><span class="sxs-lookup"><span data-stu-id="068fa-124">To set a breakpoint</span></span>
<span data-ttu-id="068fa-125">ブレークポイントをスクリプトに設定するには、まずブレークポイントを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="068fa-125">A breakpoint can be set in a script only after it has been saved.</span></span> <span data-ttu-id="068fa-126">行のブレークポイントを設定する行を右クリックしてから、**[ブレークポイントの設定/解除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="068fa-126">Right-click the line where you want to set a line breakpoint, and then click **Toggle Breakpoint**.</span></span> <span data-ttu-id="068fa-127">または、行のブレークポイントを設定する行をクリックしてから、**F9** キーを押すか、**[デバッグ]** メニューの **[ブレークポイントの設定/解除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="068fa-127">Or, click the line where you want to set a line breakpoint, and press **F9** or, on the **Debug** menu, click **Toggle Breakpoint**.</span></span>

<span data-ttu-id="068fa-128">次のスクリプトは、コンソール ウィンドウから [Set-PSBreakpoint](https://technet.microsoft.com/library/6afd5d2c-a285-4796-8607-3cbf49471420) コマンドレットを使って変数のブレークポイントを設定する方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="068fa-128">The following script is an example of how you can set a variable breakpoint from the Console Pane by using the [Set-PSBreakpoint](https://technet.microsoft.com/library/6afd5d2c-a285-4796-8607-3cbf49471420) cmdlet.</span></span>

``` PowerShell
# This command sets a breakpoint on the Server variable in the Sample.ps1 script.
Set-PSBreakpoint -Script sample.ps1 -Variable Server
```

### <a name="list-all-breakpoints"></a><span data-ttu-id="068fa-129">すべてのブレークポイントの一覧を表示</span><span class="sxs-lookup"><span data-stu-id="068fa-129">List all breakpoints</span></span>
<span data-ttu-id="068fa-130">現在の Windows PowerShell® セッションで設定されているすべてのブレークポイントを表示します。</span><span class="sxs-lookup"><span data-stu-id="068fa-130">Displays all breakpoints in the current Windows PowerShell® session.</span></span>

<span data-ttu-id="068fa-131">**[デバッグ]** メニューの **[ブレークポイントの一覧を表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="068fa-131">On the **Debug** menu, click **List Breakpoints**.</span></span> <span data-ttu-id="068fa-132">次のスクリプトは、コンソール ウィンドウから [Get-PSBreakpoint](https://technet.microsoft.com/library/0bf48936-00ab-411c-b5e0-9b10a812a3c6) コマンドレットを使ってすべてのブレークポイントの一覧を表示する方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="068fa-132">The following script is an example of how you can list all breakpoints from the Console Pane by using the [Get-PSBreakpoint](https://technet.microsoft.com/library/0bf48936-00ab-411c-b5e0-9b10a812a3c6) cmdlet.</span></span>

``` PowerShell
# This command lists all breakpoints in the current session. 
Get-PSBreakpoint
```

### <a name="remove-a-breakpoint"></a><span data-ttu-id="068fa-133">ブレークポイントの解除</span><span class="sxs-lookup"><span data-stu-id="068fa-133">Remove a breakpoint</span></span>
<span data-ttu-id="068fa-134">ブレークポイントを解除すると、そのブレークポイントは削除されます。</span><span class="sxs-lookup"><span data-stu-id="068fa-134">Removing a breakpoint deletes it.</span></span>  <span data-ttu-id="068fa-135">後で使う可能性があるブレークポイントは、解除するのではなく[無効にする]()ことができます。</span><span class="sxs-lookup"><span data-stu-id="068fa-135">If you think you might want to use it again later, consider [disabling]() it instead.</span></span>  <span data-ttu-id="068fa-136">ブレークポイントを解除する行を右クリックしてから、**[ブレークポイントの設定/解除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="068fa-136">Right-click the line where you want to remove a breakpoint, and then click **Toggle Breakpoint**.</span></span> <span data-ttu-id="068fa-137">または、ブレークポイントを解除する行をクリックして、**[デバッグ]** メニューの **[ブレークポイントの設定/解除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="068fa-137">Or, click the line where you want to remove a breakpoint, and on the **Debug** menu, click **Toggle Breakpoint**.</span></span> <span data-ttu-id="068fa-138">次のスクリプトは、コンソール ウィンドウから [Remove-PSBreakpoint](https://technet.microsoft.com/library/4c877a80-0ea0-4790-9281-88c08ef0ddd6) コマンドレットを使って、指定した ID のブレークポイントを解除する方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="068fa-138">The following script is an example of how to remove a breakpoint with a specified ID from the Console Pane by using the [Remove-PSBreakpoint](https://technet.microsoft.com/library/4c877a80-0ea0-4790-9281-88c08ef0ddd6) cmdlet.</span></span>

``` PowerShell
# This command deletes the breakpoint with breakpoint ID 2.
Remove-PSBreakpoint -Id 2
```

### <a name="remove-all-breakpoints"></a><span data-ttu-id="068fa-139">すべてのブレークポイントの削除</span><span class="sxs-lookup"><span data-stu-id="068fa-139">Remove All Breakpoints</span></span>
<span data-ttu-id="068fa-140">現在のセッション内で定義されたすべてのブレークポイントを削除するには、**[デバッグ]** メニューの **[すべてのブレークポイントを削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="068fa-140">To remove all breakpoints defined in the current session, on the **Debug** menu, click **Remove All Breakpoints**.</span></span>

<span data-ttu-id="068fa-141">次のスクリプトは、コンソール ウィンドウから [Remove-PSBreakpoint](https://technet.microsoft.com/library/4c877a80-0ea0-4790-9281-88c08ef0ddd6) コマンドレットを使ってすべてのブレークポイントを削除する方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="068fa-141">The following script is an example of how to remove all breakpoints from the Console Pane by using the [Remove-PSBreakpoint](https://technet.microsoft.com/library/4c877a80-0ea0-4790-9281-88c08ef0ddd6) cmdlet.</span></span>

``` PowerShell
# This command deletes all of the breakpoints in the current session.
Get-PSBreakpoint | Remove-PSBreakpoint
```

### <span data-ttu-id="068fa-142"><a name="bkmk_disable"></a>ブレークポイントの無効化</span><span class="sxs-lookup"><span data-stu-id="068fa-142"><a name="bkmk_disable"></a>Disable a Breakpoint</span></span>
<span data-ttu-id="068fa-143">ブレークポイントを無効にしても、そのブレークポイントは削除されず、再び有効にするまでの間オフになります。</span><span class="sxs-lookup"><span data-stu-id="068fa-143">Disabling a breakpoint does not remove it; it turns it off until it is enabled.</span></span>  <span data-ttu-id="068fa-144">特定の行のブレークポイントを無効にするには、ブレークポイントを無効にする行を右クリックし、**[ブレークポイントの無効化]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="068fa-144">To disable a specific line breakpoint, right-click the line where you want to disable a breakpoint, and then click **Disable Breakpoint**.</span></span> <span data-ttu-id="068fa-145">または、ブレークポイントを無効にする行をクリックしてから、**F9** キーを押すか、**[デバッグ]** メニューの **[ブレークポイントの無効化]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="068fa-145">Or, click the line where you want to disable a breakpoint, and press **F9** or, on the **Debug** menu, click **Disable Breakpoint**.</span></span> <span data-ttu-id="068fa-146">次のスクリプトは、コンソール ウィンドウから [Disable-PSBreakpoint](https://technet.microsoft.com/library/d4974e9b-0aaa-4e20-b87f-f599a413e4e8) コマンドレットを使って、指定した ID のブレークポイントを無効にする方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="068fa-146">The following script is an example of how you can remove a breakpoint with a specified ID from the Console Pane by using the [Disable-PSBreakpoint](https://technet.microsoft.com/library/d4974e9b-0aaa-4e20-b87f-f599a413e4e8) cmdlet.</span></span>

``` PowerShell
# This command disables the breakpoint with breakpoint ID 0.
Disable-PSBreakpoint -Id 0
```

### <a name="disable-all-breakpoints"></a><span data-ttu-id="068fa-147">すべてのブレークポイントの無効化</span><span class="sxs-lookup"><span data-stu-id="068fa-147">Disable All Breakpoints</span></span>
<span data-ttu-id="068fa-148">ブレークポイントを無効にしても、そのブレークポイントは削除されず、再び有効にするまでの間オフになります。</span><span class="sxs-lookup"><span data-stu-id="068fa-148">Disabling a breakpoint does not remove it; it turns it off until it is enabled.</span></span>  <span data-ttu-id="068fa-149">現在のセッション内のすべてのブレークポイントを無効にするには、**[デバッグ]** メニューの **[すべてのブレークポイントの無効化]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="068fa-149">To disable all breakpoints in the current session, on the **Debug** menu, click **Disable all Breakpoints**.</span></span> <span data-ttu-id="068fa-150">次のスクリプトは、コンソール ウィンドウから [Disable-PSBreakpoint](https://technet.microsoft.com/library/d4974e9b-0aaa-4e20-b87f-f599a413e4e8) コマンドレットを使ってすべてのブレークポイントを無効にする方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="068fa-150">The following script is an example of how you can disable all breakpoints from the Console Pane by using the [Disable-PSBreakpoint](https://technet.microsoft.com/library/d4974e9b-0aaa-4e20-b87f-f599a413e4e8) cmdlet.</span></span>

``` PowerShell
# This command disables all breakpoints in the current session. 
# You can abbreviate this command as: "gbp | dbp".
Get-PSBreakpoint | Disable-PSBreakpoint
```

### <a name="enable-a-breakpoint"></a><span data-ttu-id="068fa-151">ブレークポイントの有効化</span><span class="sxs-lookup"><span data-stu-id="068fa-151">Enable a Breakpoint</span></span>
<span data-ttu-id="068fa-152">特定の行のブレークポイントを有効にするには、ブレークポイントを有効にする行を右クリックし、**[ブレークポイントの有効化]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="068fa-152">To enable a specific breakpoint, right-click the line where you want to enable a breakpoint, and then click **Enable Breakpoint**.</span></span> <span data-ttu-id="068fa-153">または、ブレークポイントを有効にする行をクリックしてから、**F9** キーを押すか、**[デバッグ]** メニューの **[ブレークポイントの有効化]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="068fa-153">Or, click the line where you want to enable a breakpoint, and then press **F9** or, on the **Debug** menu, click **Enable Breakpoint**.</span></span> <span data-ttu-id="068fa-154">次のスクリプトは、コンソール ウィンドウから [Enable-PSBreakpoint](https://technet.microsoft.com/library/739e1091-3b3f-405f-a428-bec7543e5df0) コマンドレットを使って特定のブレークポイントを有効にする方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="068fa-154">The following script is an example of how you can enable specific breakpoints from the Console Pane by using the [Enable-PSBreakpoint](https://technet.microsoft.com/library/739e1091-3b3f-405f-a428-bec7543e5df0) cmdlet.</span></span>

``` PowerShell
# This command enables breakpoints with breakpoint IDs 0, 1, and 5.
Enable-PSBreakpoint -Id 0, 1, 5
```

### <a name="enable-all-breakpoints"></a><span data-ttu-id="068fa-155">すべてのブレークポイントの有効化</span><span class="sxs-lookup"><span data-stu-id="068fa-155">Enable All Breakpoints</span></span>
<span data-ttu-id="068fa-156">現在のセッション内で定義されたすべてのブレークポイントを有効にするには、**[デバッグ]** メニューの **[すべてのブレークポイントを有効化]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="068fa-156">To enable all breakpoints defined in the current session, on the **Debug** menu, click **Enable all Breakpoints**.</span></span> <span data-ttu-id="068fa-157">次のスクリプトは、コンソール ウィンドウから [Enable-PSBreakpoint](https://technet.microsoft.com/library/739e1091-3b3f-405f-a428-bec7543e5df0) コマンドレットを使ってすべてのブレークポイントを有効にする方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="068fa-157">The following script is an example of how you can enable all breakpoints from the Console Pane by using the [Enable-PSBreakpoint](https://technet.microsoft.com/library/739e1091-3b3f-405f-a428-bec7543e5df0) cmdlet.</span></span>

``` PowerShell
# This command enables all breakpoints in the current session. 
# You can abbreviate the command by using their aliases: "gbp | ebp".
Get-PSBreakpoint | Enable-PSBreakpoint
```

## <span data-ttu-id="068fa-158"><a name="bkmk_2"></a>デバッグ セッションを管理する方法</span><span class="sxs-lookup"><span data-stu-id="068fa-158"><a name="bkmk_2"></a>How to manage a debugging session</span></span>
<span data-ttu-id="068fa-159">デバッグを開始する前に、1 つ以上のブレークポイントを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="068fa-159">Before you start debugging, you must set one or more breakpoints.</span></span> <span data-ttu-id="068fa-160">ブレークポイントを設定するには、まず、デバッグするスクリプトを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="068fa-160">You cannot set a breakpoint unless the script that you want to debug is saved.</span></span> <span data-ttu-id="068fa-161">ブレークポイントを設定する手順については、「[ブレークポイントを管理する方法]()」または「[Set-PSBreakpoint](https://technet.microsoft.com/library/6afd5d2c-a285-4796-8607-3cbf49471420)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="068fa-161">For directions on of how to set a breakpoint, see [How to manage breakpoints]() or [Set-PSBreakpoint](https://technet.microsoft.com/library/6afd5d2c-a285-4796-8607-3cbf49471420).</span></span> <span data-ttu-id="068fa-162">デバッグを開始した後は、デバッグを停止するまで、スクリプトを編集できません。</span><span class="sxs-lookup"><span data-stu-id="068fa-162">After you start debugging, you cannot edit a script until you stop debugging.</span></span> <span data-ttu-id="068fa-163">1 つ以上のブレークポイントを設定したスクリプトは、実行前に自動的に保存されます。</span><span class="sxs-lookup"><span data-stu-id="068fa-163">A script that has one or more breakpoints set is automatically saved before it is run.</span></span>

### <a name="to-start-debugging"></a><span data-ttu-id="068fa-164">デバッグを開始するには</span><span class="sxs-lookup"><span data-stu-id="068fa-164">To start debugging</span></span>
<span data-ttu-id="068fa-165">**F5** キーを押すか、ツールバーの **[スクリプトを実行]** アイコンをクリックするか、**[デバッグ]** メニューの **[実行/続行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="068fa-165">Press **F5** or, on the toolbar, click the **Run Script** icon, or on the **Debug** menu click **Run/Continue**.</span></span> <span data-ttu-id="068fa-166">スクリプトは、最初のブレークポイントを検出するまで実行されます。</span><span class="sxs-lookup"><span data-stu-id="068fa-166">The script runs until it encounters the first breakpoint.</span></span> <span data-ttu-id="068fa-167">ブレークポイントを検出した位置で操作が一時停止し、一時停止した行が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="068fa-167">It pauses operation there and highlights the line on which it paused.</span></span>

### <a name="to-continue-debugging"></a><span data-ttu-id="068fa-168">デバッグを続行するには</span><span class="sxs-lookup"><span data-stu-id="068fa-168">To continue debugging</span></span>
<span data-ttu-id="068fa-169">**F5** キーを押すか、ツールバーの **[スクリプトを実行]** アイコンをクリックするか、**[デバッグ]** メニューの **[実行/続行]** をクリックするか、コンソール ウィンドウで **C** と入力してから **Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="068fa-169">Press **F5** or, on the toolbar, click the **Run Script** icon, or on the **Debug** menu, click **Run/Continue** or, in the Console Pane, type **C** and then press **ENTER**.</span></span> <span data-ttu-id="068fa-170">これにより、次のブレークポイントまで、またはこれ以上ブレークポイントが検出されない場合は、スクリプトの最後までスクリプトの実行が継続されます。</span><span class="sxs-lookup"><span data-stu-id="068fa-170">This causes the script to continue running to the next breakpoint or to the end of the script if no further breakpoints are encountered.</span></span>

### <a name="to-view-the-call-stack"></a><span data-ttu-id="068fa-171">呼び出し履歴を表示するには</span><span class="sxs-lookup"><span data-stu-id="068fa-171">To view the call stack</span></span>
<span data-ttu-id="068fa-172">呼び出し履歴には、スクリプト内で現在実行中の位置が表示されます。</span><span class="sxs-lookup"><span data-stu-id="068fa-172">The call stack displays the current run location in the script.</span></span> <span data-ttu-id="068fa-173">スクリプトが別の関数によって呼び出された関数で実行されている場合、そのことは画面の出力に行が追加されることによって示されます。</span><span class="sxs-lookup"><span data-stu-id="068fa-173">If the script is running in a function that was called by a different function, then that is represented in the display by additional rows in the output.</span></span> <span data-ttu-id="068fa-174">一番下の行には、元のスクリプトと、関数が呼び出された行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="068fa-174">The bottom-most row displays the original script and the line in it in which a function was called.</span></span> <span data-ttu-id="068fa-175">その上の行には、別の関数が呼び出された場合に、その関数と、関数が呼び出された行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="068fa-175">The next line up shows that function and the line in it in which another function might have been called.</span></span>  <span data-ttu-id="068fa-176">一番上の行には、ブレークポイントが設定されている、現在の行の現在のコンテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="068fa-176">The top-most row shows the current context of the current line on which the breakpoint is set.</span></span>

<span data-ttu-id="068fa-177">一時停止中に現在の呼び出し履歴を表示するには、**CTRL + SHIFT + D** キーを押すか、**[デバッグ]** メニューの **[呼び出し履歴の表示]** をクリックするか、コンソール ウィンドウで **K** と入力してから **ENTER** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="068fa-177">While paused, to see the current call stack, press **CTRL+SHIFT+D** or, on the **Debug** menu, click **Display Call Stack** or, in the Console Pane, type **K** and then press **ENTER**.</span></span>

### <a name="to-stop-debugging"></a><span data-ttu-id="068fa-178">デバッグを停止するには</span><span class="sxs-lookup"><span data-stu-id="068fa-178">To stop debugging</span></span>
<span data-ttu-id="068fa-179">**SHIFT-F5** キーを押すか、**[デバッグ]** メニューの **[デバッガーの停止]** をクリックするか、コンソール ウィンドウで **Q** と入力してから **ENTER** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="068fa-179">Press **SHIFT-F5** or, on the **Debug** menu, click **Stop Debugger**, or, in the Console Pane, type **Q** and then press **ENTER**.</span></span>

## <span data-ttu-id="068fa-180"><a name="bkmk_3"></a>デバッグ中にステップ オーバー、ステップ イン、ステップ アウトする方法</span><span class="sxs-lookup"><span data-stu-id="068fa-180"><a name="bkmk_3"></a>How to step over, step into, and step out while debugging</span></span>
<span data-ttu-id="068fa-181">ステッピングは、一度に 1 つのステートメントを実行するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="068fa-181">Stepping is the process of running one statement at a time.</span></span> <span data-ttu-id="068fa-182">コードの行で停止し、変数の値とシステムの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="068fa-182">You can stop on a line of code, and examine the values of variables and the state of the system.</span></span> <span data-ttu-id="068fa-183">次の表では、ステップ オーバー、ステップ イン、ステップ アウトなどの一般的なデバッグ タスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="068fa-183">The following table describes common debugging tasks such as stepping over, stepping into, and stepping out.</span></span>

| <span data-ttu-id="068fa-184">デバッグ タスク</span><span class="sxs-lookup"><span data-stu-id="068fa-184">Debugging Task</span></span> | <span data-ttu-id="068fa-185">説明</span><span class="sxs-lookup"><span data-stu-id="068fa-185">Description</span></span> | <span data-ttu-id="068fa-186">PowerShell ISE で実行する方法</span><span class="sxs-lookup"><span data-stu-id="068fa-186">How to accomplish it in PowerShell ISE</span></span> |
| --- | --- | --- |
| <span data-ttu-id="068fa-187">**ステップ イン**</span><span class="sxs-lookup"><span data-stu-id="068fa-187">**Step Into**</span></span> | <span data-ttu-id="068fa-188">現在のステートメントを実行し、次のステートメントで停止します。</span><span class="sxs-lookup"><span data-stu-id="068fa-188">Executes the current statement and then stops at the next statement.</span></span> <span data-ttu-id="068fa-189">現在のステートメントが関数やスクリプトの呼び出しの場合、デバッガーはその関数やスクリプトにステップ インします。それ以外の場合、デバッガーは次のステートメントで停止します。</span><span class="sxs-lookup"><span data-stu-id="068fa-189">If the current statement is a function or script call, then the debugger steps into that function or script, otherwise it stops at the next statement.</span></span> | <span data-ttu-id="068fa-190">**F11** キーを押すか、**[デバッグ]** メニューの **[ステップ イン]** をクリックするか、コンソール ウィンドウに **S** と入力して **Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="068fa-190">Press **F11** or, on the **Debug** menu, click **Step Into**, or in the Console Pane, type **S** and press **ENTER**.</span></span> |
| <span data-ttu-id="068fa-191">**ステップ オーバー**</span><span class="sxs-lookup"><span data-stu-id="068fa-191">**Step Over**</span></span> | <span data-ttu-id="068fa-192">現在のステートメントを実行し、次のステートメントで停止します。</span><span class="sxs-lookup"><span data-stu-id="068fa-192">Executes the current statement and then stops at the next statement.</span></span> <span data-ttu-id="068fa-193">現在のステートメントが関数やスクリプトの呼び出しの場合、デバッガーはその関数やスクリプトの全体を実行し、関数を呼び出した後の次のステートメントで停止します。</span><span class="sxs-lookup"><span data-stu-id="068fa-193">If the current statement is a function or script call then the debugger executes the whole function or script, and it stops at the next statement after the function call.</span></span> | <span data-ttu-id="068fa-194">**F10** キーを押すか、**[デバッグ]** メニューの **[ステップ オーバー]** をクリックするか、コンソール ウィンドウに **V** と入力して **Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="068fa-194">Press **F10** or, on the **Debug** menu, click **Step Over**, or in the Console Pane, type **V** and press **ENTER**.</span></span> |
| <span data-ttu-id="068fa-195">**ステップ アウト**</span><span class="sxs-lookup"><span data-stu-id="068fa-195">**Step Out**</span></span> | <span data-ttu-id="068fa-196">現在の関数からステップ アウトし、関数が入れ子になっている場合は 1 つ上のレベルに移動します。</span><span class="sxs-lookup"><span data-stu-id="068fa-196">Steps out of the current function and up one level if the function is nested.</span></span> <span data-ttu-id="068fa-197">メイン ボディの場合は、スクリプトが最後まで、または次のブレークポイントまで実行されます。</span><span class="sxs-lookup"><span data-stu-id="068fa-197">If in the main body, the script is executed to the end, or to the next breakpoint.</span></span> <span data-ttu-id="068fa-198">スキップしたステートメントは実行されますが、ステップ スルーされることはありません。</span><span class="sxs-lookup"><span data-stu-id="068fa-198">The skipped statements are executed, but not stepped through.</span></span> | <span data-ttu-id="068fa-199">**SHIFT+F11** キーを押すか、**[デバッグ]** メニューの **[ステップ アウト]** をクリックするか、コンソール ウィンドウに **O** と入力して **ENTER** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="068fa-199">Press **SHIFT+F11**, or on the **Debug** menu, click **Step Out**, or in the Console Pane, type **O** and press **ENTER**.</span></span> |
| <span data-ttu-id="068fa-200">**続行**</span><span class="sxs-lookup"><span data-stu-id="068fa-200">**Continue**</span></span> | <span data-ttu-id="068fa-201">最後まで、または次のブレークポイントまで実行を続けます。</span><span class="sxs-lookup"><span data-stu-id="068fa-201">Continues execution to the end, or to the next breakpoint.</span></span> <span data-ttu-id="068fa-202">スキップした関数と呼び出しは実行されますが、ステップ スルーされることはありません。</span><span class="sxs-lookup"><span data-stu-id="068fa-202">The skipped functions and invocations are executed, but not stepped through.</span></span> | <span data-ttu-id="068fa-203">**F5** キーを押すか、**[デバッグ]** メニューの **[実行/続行]** をクリックするか、コンソール ウィンドウに **C** と入力して **ENTER** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="068fa-203">Press **F5** or, on the **Debug** menu, click **Run/Continue**, or in the Console Pane, type **C** and press **ENTER**.</span></span> |

## <span data-ttu-id="068fa-204"><a name="bkmk_4"></a>デバッグ中に変数の値を表示する方法</span><span class="sxs-lookup"><span data-stu-id="068fa-204"><a name="bkmk_4"></a>How to display the values of variables while debugging</span></span>
<span data-ttu-id="068fa-205">コードをステップ スルーするとき、スクリプト内の変数の現在値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="068fa-205">You can display the current values of variables in the script as you step through the code.</span></span>

### <a name="to-display-the-values-of-standard-variables"></a><span data-ttu-id="068fa-206">標準変数の値を表示するには</span><span class="sxs-lookup"><span data-stu-id="068fa-206">To display the values of standard variables</span></span>
<span data-ttu-id="068fa-207">以下の方法のうちのいずれか 1 つを使用します。</span><span class="sxs-lookup"><span data-stu-id="068fa-207">Use one of the following methods:</span></span>

-   <span data-ttu-id="068fa-208">スクリプト ウィンドウで、変数にマウスのカーソルを合わせると、ツール ヒントとしてその変数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="068fa-208">In the Script Pane, hover over the variable to display its value as a tool tip.</span></span>

-   <span data-ttu-id="068fa-209">コンソール ウィンドウで、変数名を入力して **Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="068fa-209">In the Console Pane, type the variable name and press **ENTER**.</span></span>

<span data-ttu-id="068fa-210">ISE のすべてのウィンドウは、常に同じスコープ内にあります。</span><span class="sxs-lookup"><span data-stu-id="068fa-210">All panes in ISE are always in the same scope.</span></span> <span data-ttu-id="068fa-211">そのため、スクリプトをデバッグしている間は、コンソール ウィンドウに入力したコマンドはスクリプト スコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="068fa-211">Therefore, while you are debugging a script, the commands that you type in the Console Pane run in script scope.</span></span> <span data-ttu-id="068fa-212">これにより、コンソール ウィンドウを使って、スクリプト内でのみ定義されている変数の値を調べたり、スクリプト内でのみ定義されている関数を呼び出したりできます。</span><span class="sxs-lookup"><span data-stu-id="068fa-212">This allows you to use the Console Pane to find the values of variables and call functions that are defined only in the script.</span></span>

### <a name="to-display-the-values-of-automatic-variables"></a><span data-ttu-id="068fa-213">自動変数の値を表示するには</span><span class="sxs-lookup"><span data-stu-id="068fa-213">To display the values of automatic variables</span></span>
<span data-ttu-id="068fa-214">上記の方法を使えば、スクリプトのデバッグ中にほとんどすべての変数の値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="068fa-214">You can use the preceding method to display the value of almost all variables while you are debugging a script.</span></span> <span data-ttu-id="068fa-215">ただし、これらの方法は、次の自動変数に対しては機能しません。</span><span class="sxs-lookup"><span data-stu-id="068fa-215">However, these methods do not work for the following automatic variables.</span></span>

-   <span data-ttu-id="068fa-216">$_</span><span class="sxs-lookup"><span data-stu-id="068fa-216">$_</span></span>

-   <span data-ttu-id="068fa-217">$Input</span><span class="sxs-lookup"><span data-stu-id="068fa-217">$Input</span></span>

-   <span data-ttu-id="068fa-218">$MyInvocation</span><span class="sxs-lookup"><span data-stu-id="068fa-218">$MyInvocation</span></span>

-   <span data-ttu-id="068fa-219">$PSBoundParameters</span><span class="sxs-lookup"><span data-stu-id="068fa-219">$PSBoundParameters</span></span>

-   <span data-ttu-id="068fa-220">$Args</span><span class="sxs-lookup"><span data-stu-id="068fa-220">$Args</span></span>

<span data-ttu-id="068fa-221">これらの変数のいずれかの値を表示しようとする場合は、スクリプト内の変数の値ではなく、デバッガーが使う内部パイプラインでその変数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="068fa-221">If you try to display the value of any of these variables, you get the value of that variable for in an internal pipeline the debugger uses, not the value of the variable in the script.</span></span> <span data-ttu-id="068fa-222">いくつかの変数 ($_、$Input、$MyInvocation、$PSBoundParameters、$Args) についてこれを回避するには、次の方法を使います。</span><span class="sxs-lookup"><span data-stu-id="068fa-222">You can work around this for a few variables ($_, $Input, $MyInvocation, $PSBoundParameters, and $Args) by using the following method:</span></span>

1.  <span data-ttu-id="068fa-223">スクリプトで、自動変数の値を新しい変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="068fa-223">In the script, assign the value of the automatic variable to a new variable.</span></span>

2.  <span data-ttu-id="068fa-224">その新しい変数の値を表示するには、スクリプト ウィンドウ内でマウスのカーソルを新しい変数に合わせるか、コンソール ウィンドウに新しい変数を入力します。</span><span class="sxs-lookup"><span data-stu-id="068fa-224">Display the value of the new variable, either by hovering over the new variable in the Script Pane, or by typing the new variable in the Console Pane.</span></span>

<span data-ttu-id="068fa-225">たとえば、$MyInvocation 変数の値を表示するには、スクリプト内でその値を新しい変数 ($scriptname など) に割り当ててから、マウスのカーソルを合わせるか、$scriptname 変数を入力します。</span><span class="sxs-lookup"><span data-stu-id="068fa-225">For example, to display the value of the $MyInvocation variable, in the script, assign the value to a new variable, such as $scriptname, and then hover over or type the $scriptname variable to display its value.</span></span>

``` PowerShell
#In MyScript.ps1
$scriptname = $MyInvocation.MyCommand.Path

#In the Console Pane:
C:\ps-test> $scriptname
C:\ps-test\MyScript.ps1
```

## <a name="see-also"></a><span data-ttu-id="068fa-226">参照</span><span class="sxs-lookup"><span data-stu-id="068fa-226">See Also</span></span>
- [<span data-ttu-id="068fa-227">Windows PowerShell ISE の使用</span><span class="sxs-lookup"><span data-stu-id="068fa-227">Using the Windows PowerShell ISE</span></span>](Using-the-Windows-PowerShell-ISE.md)

