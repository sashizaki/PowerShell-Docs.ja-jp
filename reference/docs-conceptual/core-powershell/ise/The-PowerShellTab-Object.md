---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "PowerShellTab オブジェクト"
ms.assetid: a9b58556-951b-4f48-b3ae-b351b7564360
ms.openlocfilehash: 482984272b2f1be027cf2be49bdfa2c6e2c52070
ms.sourcegitcommit: 4102ecc35d473211f50a453f6ae3fbea31cb3428
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2017
---
# <a name="the-powershelltab-object"></a><span data-ttu-id="a04b7-103">PowerShellTab オブジェクト</span><span class="sxs-lookup"><span data-stu-id="a04b7-103">The PowerShellTab Object</span></span>
  <span data-ttu-id="a04b7-104">**PowerShellTab** オブジェクトは、Windows PowerShell ランタイム環境を表します。</span><span class="sxs-lookup"><span data-stu-id="a04b7-104">The **PowerShellTab** object represents a Windows PowerShell runtime environment.</span></span>

## <a name="methods"></a><span data-ttu-id="a04b7-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a04b7-105">Methods</span></span>

### <a name="invoke-script-"></a><span data-ttu-id="a04b7-106">Invoke\( Script \)</span><span class="sxs-lookup"><span data-stu-id="a04b7-106">Invoke\( Script \)</span></span>
  <span data-ttu-id="a04b7-107">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a04b7-107">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="a04b7-108">指定したスクリプトを [PowerShell] タブで実行します。</span><span class="sxs-lookup"><span data-stu-id="a04b7-108">Runs the given script in the PowerShell tab.</span></span>

> [!NOTE]
>  <span data-ttu-id="a04b7-109">このメソッドは、その他の [PowerShell] タブでのみ機能し、実行元となる [PowerShell] タブでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="a04b7-109">This method only works on other PowerShell tabs, not the PowerShell tab from which it is run.</span></span> <span data-ttu-id="a04b7-110">このコマンドはオブジェクトや値を返しません。</span><span class="sxs-lookup"><span data-stu-id="a04b7-110">It does not return any object or value.</span></span> <span data-ttu-id="a04b7-111">このコードによって変数が変更されると、その変更はコマンドが呼び出されたタブで保持されます。</span><span class="sxs-lookup"><span data-stu-id="a04b7-111">If the code modifies any variable, then those changes persist on the tab against which the command was invoked.</span></span>

 <span data-ttu-id="a04b7-112">**Script** - System.Management.Automation.ScriptBlock または文字列。実行するスクリプト ブロック。</span><span class="sxs-lookup"><span data-stu-id="a04b7-112">**Script** - System.Management.Automation.ScriptBlock or String The script block to run.</span></span>

```
# Manually create a second PowerShell tab before running this script.
# Return to the first PowerShell tab and type the following command
$psise.PowerShellTabs[1].Invoke({dir})
```

### <a name="invokesynchronous-script-usenewscope-millisecondstimeout-"></a><span data-ttu-id="a04b7-113">InvokeSynchronous\( Script, \[useNewScope\], millisecondsTimeout \)</span><span class="sxs-lookup"><span data-stu-id="a04b7-113">InvokeSynchronous\( Script, \[useNewScope\], millisecondsTimeout \)</span></span>
  <span data-ttu-id="a04b7-114">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="a04b7-114">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span> 

 <span data-ttu-id="a04b7-115">指定したスクリプトを [PowerShell] タブで実行します。</span><span class="sxs-lookup"><span data-stu-id="a04b7-115">Runs the given script in the PowerShell tab.</span></span>

> [!NOTE]
>  <span data-ttu-id="a04b7-116">このメソッドは、その他の [PowerShell] タブでのみ機能し、実行元となる [PowerShell] タブでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="a04b7-116">This method only works on other PowerShell tabs, not the PowerShell tab from which it is run.</span></span> <span data-ttu-id="a04b7-117">スクリプト ブロックが実行され、スクリプトから返される値はコマンドを呼び出した実行環境に返されます。</span><span class="sxs-lookup"><span data-stu-id="a04b7-117">The script block is run and any value that is returned from the script is returned to the run environment from which you invoked the command.</span></span> <span data-ttu-id="a04b7-118">コマンドが **millesecondsTimeout** の値で指定した時間内に完了しない場合、コマンドが失敗して例外 "処理がタイムアウトになりました。" が発生します。</span><span class="sxs-lookup"><span data-stu-id="a04b7-118">If the command takes longer to run than the **millesecondsTimeout** value specifies, then the command fails with an exception: "The operation has timed out."</span></span>

 <span data-ttu-id="a04b7-119">**Script** - System.Management.Automation.ScriptBlock または文字列。実行するスクリプト ブロック。</span><span class="sxs-lookup"><span data-stu-id="a04b7-119">**Script** - System.Management.Automation.ScriptBlock or String The script block to run.</span></span>

 <span data-ttu-id="a04b7-120">**\[useNewScope\]** - 省略可能なブール値で、既定は **$true** です。**$true** に設定されると、そのコマンドを実行する新しいスコープが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a04b7-120">**\[useNewScope\]** -  Optional Boolean that defaults to **$true** If set to **$true**, then a new scope is created within which to run the command.</span></span> <span data-ttu-id="a04b7-121">コマンドで指定されている [PowerShell] タブのランタイム環境は変更されません。</span><span class="sxs-lookup"><span data-stu-id="a04b7-121">It does not modify the runtime environment of the PowerShell tab that is specified by the command.</span></span>

 <span data-ttu-id="a04b7-122">**\[millisecondsTimeout\]** - **500** を既定値とする省略可能な整数。</span><span class="sxs-lookup"><span data-stu-id="a04b7-122">**\[millisecondsTimeout\]** -  Optional integer that defaults to **500**.</span></span>
<span data-ttu-id="a04b7-123">指定した時間内にコマンドが完了しない場合、コマンドによって **TimeoutException** が生成され、"処理がタイムアウトになりました。" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a04b7-123">If the command does not finish within the specified time, then the command generates a **TimeoutException** with the message "The operation has timed out."</span></span>

```
# create a new PowerShell tab and then switch back to the first
$PSise.PowerShellTabs.Add()
$psISE.PowerShellTabs.SetSelectedPowerShellTab($psISE.PowerShellTabs[0]) 

# Invoke a simple command on the other tab, in its own scope
$psISE.PowerShellTabs[1].InvokeSynchronous('$x=1',$false)
# You can switch to the other tab and type â€œ$xâ€ to see that the value is saved there.

# This example sets a value in the other tab (in a different scope) 
# and returns it through the pipeline to this tab to store in $a
$a=$psISE.PowerShellTabs[1].InvokeSynchronous('$z=3;$z') 
$a

# This example runs a command that takes longer than the allowed timeout value
# and measures how long it runs so that you can see the impact
measure-command {$psISE.PowerShellTabs[1].InvokeSynchronous("sleep 10",$false,5000)}

```

## <a name="properties"></a><span data-ttu-id="a04b7-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a04b7-124">Properties</span></span>

### <a name="addonsmenu"></a><span data-ttu-id="a04b7-125">AddOnsMenu</span><span class="sxs-lookup"><span data-stu-id="a04b7-125">AddOnsMenu</span></span>
  <span data-ttu-id="a04b7-126">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a04b7-126">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="a04b7-127">[PowerShell] タブのアドオン メニューを取得する読み取り専用のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="a04b7-127">The read-only property that gets the Add-ons menu for the PowerShell tab.</span></span>

```
# Clear the Add-ons menu if one exists.
$psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Clear()
# Create an AddOns menu with an accessor.
# Note the use of "_"  as opposed to the "&" for mapping to the fast key letter for the menu item.
$menuAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Add("_Process",{get-process},"Alt+P") 
# Add a nested menu. 
$parentAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Add("Parent",$null,$null) 
$parentAdded.SubMenus.Add("_Dir",{dir},"Alt+D")
# Show the Add-ons menu on the current PowerShell tab.
$psISE.CurrentPowerShellTab.AddOnsMenu
```

### <a name="caninvoke"></a><span data-ttu-id="a04b7-128">CanInvoke</span><span class="sxs-lookup"><span data-stu-id="a04b7-128">CanInvoke</span></span>
  <span data-ttu-id="a04b7-129">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a04b7-129">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="a04b7-130">スクリプトを [Invoke( Script )]() メソッドで呼び出すことが可能な場合は **$true** を返す、読み取り専用のブール型プロパティです。</span><span class="sxs-lookup"><span data-stu-id="a04b7-130">The read-only Boolean property that returns a **$true** value if a script can be invoked with the [Invoke( Script )]() method.</span></span>

```
# CanInvoke will be false if the PowerShell
# tab is running a script that takes a while, and you
# check its properties from another PowerShell tab. It is
# always false if checked on the current PowerShell tab. 
# Manually create a second PowerShell tab before running this script.
# Return to the first tab and type
$secondTab = $psise.PowerShellTabs[1] 
$secondTab.CanInvoke 
$secondTab.Invoke({sleep 20})
$secondTab.CanInvoke

```

### <a name="consolepane"></a><span data-ttu-id="a04b7-131">Consolepane</span><span class="sxs-lookup"><span data-stu-id="a04b7-131">Consolepane</span></span>
  <span data-ttu-id="a04b7-132">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="a04b7-132">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>  <span data-ttu-id="a04b7-133">Windows PowerShell ISE 2.0 では、このパラメータの名前は **CommandPane** でした。</span><span class="sxs-lookup"><span data-stu-id="a04b7-133">In Windows PowerShell ISE 2.0 this was named **CommandPane**.</span></span>

 <span data-ttu-id="a04b7-134">コンソール ウィンドウの [editor](../ise/The-ISEEditor-Object.md) オブジェクトを取得する読み取り専用のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="a04b7-134">The read-only property that gets the Console pane [editor](../ise/The-ISEEditor-Object.md) object.</span></span>

```
# Gets the Console Pane editor.
$psISE.CurrentPowerShellTab.ConsolePane

```

### <a name="displayname"></a><span data-ttu-id="a04b7-135">表示名</span><span class="sxs-lookup"><span data-stu-id="a04b7-135">DisplayName</span></span>
  <span data-ttu-id="a04b7-136">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a04b7-136">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="a04b7-137">[PowerShell] タブに表示されるテキストを取得または設定する読み取り/書き込みプロパティです。既定では、タブ名は "PowerShell #" となり、「#」には番号が入ります。</span><span class="sxs-lookup"><span data-stu-id="a04b7-137">The read-write property that gets or sets the text that is displayed on the PowerShell tab. By default, tabs are named "PowerShell #", where the # represents a number.</span></span>

```
$newTab = $psise.PowerShellTabs.Add()
# Change the DisplayName of the new PowerShell tab. 
$newTab.DisplayName="Brand New Tab"
```

### <a name="expandedscript"></a><span data-ttu-id="a04b7-138">ExpandedScript</span><span class="sxs-lookup"><span data-stu-id="a04b7-138">ExpandedScript</span></span>
  <span data-ttu-id="a04b7-139">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a04b7-139">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="a04b7-140">スクリプト ウィンドウが展開されているか非表示かどうかを特定する読み取り/書き込みブール型プロパティです。</span><span class="sxs-lookup"><span data-stu-id="a04b7-140">The read-write Boolean property that determines whether the Script pane is expanded or hidden.</span></span>

```
# Toggle the expanded script property to see its effect.
$PSise.CurrentPowerShellTab.ExpandedScript=!$PSise.CurrentPowerShellTab.ExpandedScript

```

### <a name="files"></a><span data-ttu-id="a04b7-141">ファイル</span><span class="sxs-lookup"><span data-stu-id="a04b7-141">Files</span></span>
  <span data-ttu-id="a04b7-142">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a04b7-142">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="a04b7-143">[PowerShell] タブで開かれている[スクリプト ファイルのコレクション](../ise/The-ISEFileCollection-Object.md)を取得する読み取り専用のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="a04b7-143">The read-only property that gets the [collection of script files](../ise/The-ISEFileCollection-Object.md) that are open in the PowerShell tab.</span></span>

```
$newFile = $psISE.CurrentPowerShellTab.Files.Add()
$newFile.Editor.Text = "a`r`nb" 
# Gets the line count
$newFile.Editor.LineCount
```

### <a name="output"></a><span data-ttu-id="a04b7-144">出力</span><span class="sxs-lookup"><span data-stu-id="a04b7-144">Output</span></span>
  <span data-ttu-id="a04b7-145">この機能は、Windows PowerShell ISE 2.0 に存在しますが、それよりも後のバージョンの ISE では削除されているか、名前が変更されています。</span><span class="sxs-lookup"><span data-stu-id="a04b7-145">This feature is present in Windows PowerShell ISE 2.0, but was removed or renamed in later versions of the ISE.</span></span>  <span data-ttu-id="a04b7-146">Windows PowerShell ISE 2.0 より後のバージョンでは、**ConsolePane** オブジェクトを同じ目的で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a04b7-146">In later versions of Windows PowerShell ISE, you can use the **ConsolePane** object for the same purposes.</span></span>

 <span data-ttu-id="a04b7-147">現在の[エディター](../ise/The-ISEEditor-Object.md)の出力ウィンドウが取得する読み取り専用のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="a04b7-147">The read-only property that gets the Output pane of the current [editor](../ise/The-ISEEditor-Object.md).</span></span>

```
# Clears the text in the Output pane.
$psise.CurrentPowerShellTab.output.clear()
```

### <a name="prompt"></a><span data-ttu-id="a04b7-148">ダイアログを表示する</span><span class="sxs-lookup"><span data-stu-id="a04b7-148">Prompt</span></span>
  <span data-ttu-id="a04b7-149">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a04b7-149">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="a04b7-150">現在のプロンプト テキストを取得する読み取り専用のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="a04b7-150">The read-only property that gets the current prompt text.</span></span> <span data-ttu-id="a04b7-151">注: **Prompt** 関数は、ユーザーのプロファイルで上書きできます。</span><span class="sxs-lookup"><span data-stu-id="a04b7-151">Note: the **Prompt** function can be overridden by the userâ€™s profile.</span></span> <span data-ttu-id="a04b7-152">結果が単純な文字列以外の場合、このプロパティは何も返しません。</span><span class="sxs-lookup"><span data-stu-id="a04b7-152">If the result is other than a simple string, then this property returns nothing.</span></span>

```
# Gets the current prompt text.
$psISE.CurrentPowerShellTab.Prompt
```

### <a name="showcommands"></a><span data-ttu-id="a04b7-153">ShowCommands</span><span class="sxs-lookup"><span data-stu-id="a04b7-153">ShowCommands</span></span>
  <span data-ttu-id="a04b7-154">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="a04b7-154">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span> 

 <span data-ttu-id="a04b7-155">コマンド ウィンドウが現在表示されているかどうかを示す読み取り/書き込みプロパティです。</span><span class="sxs-lookup"><span data-stu-id="a04b7-155">The read-write property that indicates if the Commands pane is currently displayed.</span></span>

```
# Gets the current status of the Commands pane and stores it in the $a variable
$a = $psISE.CurrentPowerShellTab.ShowCommands
# if $a is $false, then turn the Commands pane on by changing the value to $True
if (!$a) {$psISE.CurrentPowerShellTab.ShowCommands=$True}
```

### <a name="statustext"></a><span data-ttu-id="a04b7-156">StatusText</span><span class="sxs-lookup"><span data-stu-id="a04b7-156">StatusText</span></span>
  <span data-ttu-id="a04b7-157">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a04b7-157">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="a04b7-158">**PowerShellTab** ステータス テキストを取得する読み取り専用のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="a04b7-158">The read-only property that gets the **PowerShellTab** status text.</span></span>

```
# Gets the current status text,
$psISE.CurrentPowerShellTab.StatusText
```

### <a name="horizontaladdontoolspaneopened"></a><span data-ttu-id="a04b7-159">HorizontalAddOnToolsPaneOpened</span><span class="sxs-lookup"><span data-stu-id="a04b7-159">HorizontalAddOnToolsPaneOpened</span></span>
  <span data-ttu-id="a04b7-160">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="a04b7-160">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span> 

 <span data-ttu-id="a04b7-161">水平方向のアドオン ツール ウィンドウが現在開いているかどうかを示す読み取り 専用のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="a04b7-161">The read-only property that indicates whether the horizontal Add-Ons tool pane is currently open.</span></span>

```
# Gets the current state of the horizontal Add-ons tool pane. 
$psISE.CurrentPowerShellTab.HorizontalAddOnToolsPaneOpened
```

### <a name="verticaladdontoolspaneopened"></a><span data-ttu-id="a04b7-162">VerticalAddOnToolsPaneOpened</span><span class="sxs-lookup"><span data-stu-id="a04b7-162">VerticalAddOnToolsPaneOpened</span></span>
  <span data-ttu-id="a04b7-163">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="a04b7-163">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span> 

 <span data-ttu-id="a04b7-164">垂直方向のアドオン ツール ウィンドウが現在開いているかどうかを示す読み取り専用のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="a04b7-164">The read-only property that indicates whether the vertical Add-Ons tool pane is currently open.</span></span>

```
# Turns on the Commands pane
$psISE.CurrentPowerShellTab.ShowCommands=$True
# Gets the current state of the vertical Add-ons tool pane. 
$psISE.CurrentPowerShellTab.HorizontalAddOnToolsPaneOpened
```

## <a name="see-also"></a><span data-ttu-id="a04b7-165">参照</span><span class="sxs-lookup"><span data-stu-id="a04b7-165">See Also</span></span>
- [<span data-ttu-id="a04b7-166">PowerShellTabCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="a04b7-166">The PowerShellTabCollection Object</span></span>](The-PowerShellTabCollection-Object.md) 
- [<span data-ttu-id="a04b7-167">Windows PowerShell ISE スクリプト オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="a04b7-167">The Windows PowerShell ISE Scripting Object Model</span></span>](../ise/The-Windows-PowerShell-ISE-Scripting-Object-Model.md) 
- [<span data-ttu-id="a04b7-168">Windows PowerShell ISE オブジェクト モデル リファレンス</span><span class="sxs-lookup"><span data-stu-id="a04b7-168">Windows PowerShell ISE Object Model Reference</span></span>](../ise/Windows-PowerShell-ISE-Object-Model-Reference.md) 
- [<span data-ttu-id="a04b7-169">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="a04b7-169">The ISE Object Model Hierarchy</span></span>](../ise/The-ISE-Object-Model-Hierarchy.md)

  
