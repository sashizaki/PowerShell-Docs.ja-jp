---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/29/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/show-command?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-Command
ms.openlocfilehash: b5758fdb9fc3e8f604b24fb9c64cad3f95047ec3
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347773"
---
# <span data-ttu-id="21d4a-103">Show-Command</span><span class="sxs-lookup"><span data-stu-id="21d4a-103">Show-Command</span></span>

## <span data-ttu-id="21d4a-104">概要</span><span class="sxs-lookup"><span data-stu-id="21d4a-104">SYNOPSIS</span></span>
<span data-ttu-id="21d4a-105">グラフィカルウィンドウに PowerShell コマンド情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-105">Displays PowerShell command information in a graphical window.</span></span>

## <span data-ttu-id="21d4a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="21d4a-106">SYNTAX</span></span>

```
Show-Command [[-Name] <String>] [-Height <Double>] [-Width <Double>] [-NoCommonParameter]
 [-ErrorPopup] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="21d4a-107">Description</span><span class="sxs-lookup"><span data-stu-id="21d4a-107">DESCRIPTION</span></span>

<span data-ttu-id="21d4a-108">`Show-Command`コマンドレットを使用すると、コマンドウィンドウで PowerShell コマンドを作成できます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-108">The `Show-Command` cmdlet lets you create a PowerShell command in a command window.</span></span> <span data-ttu-id="21d4a-109">コマンド ウィンドウの機能を使用して、コマンドを実行することやコマンドを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-109">You can use the features of the command window to run the command or have it return the command to you.</span></span>

<span data-ttu-id="21d4a-110">`Show-Command` は、非常に便利な教育および学習ツールです。</span><span class="sxs-lookup"><span data-stu-id="21d4a-110">`Show-Command` is a very useful teaching and learning tool.</span></span> <span data-ttu-id="21d4a-111">`Show-Command` コマンドレット、関数、ワークフロー、CIM コマンドなど、すべてのコマンドの種類に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-111">`Show-Command` works on all command types, including cmdlets, functions, workflows and CIM commands.</span></span>

<span data-ttu-id="21d4a-112">パラメーターを指定しない場合、 `Show-Command` インストールされているすべてのモジュールで使用可能なすべてのコマンドを一覧表示するコマンドウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-112">Without parameters, `Show-Command` displays a command window that lists all available commands in all installed modules.</span></span> <span data-ttu-id="21d4a-113">モジュール内のコマンドを検索するには、[モジュール] ボックスの一覧からモジュールを選択します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-113">To find the commands in a module, select the module from the Modules drop-down list.</span></span> <span data-ttu-id="21d4a-114">コマンドを選択するには、コマンド名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21d4a-114">To select a command, click the command name.</span></span>

<span data-ttu-id="21d4a-115">コマンドウィンドウを使用するには、名前を使用する **か、コマンド一覧の** コマンド名をクリックして、コマンドを選択します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-115">To use the command window, select a command, either by using the Name or by clicking the command name in the **Commands** list.</span></span> <span data-ttu-id="21d4a-116">各パラメーターセットは、別のタブに表示されます。アスタリスクは、必須のパラメーターを示します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-116">Each parameter set is displayed on a separate tab. Asterisks indicate the mandatory parameters.</span></span> <span data-ttu-id="21d4a-117">パラメーターに値を入力するには、テキスト ボックスに値を入力するか、ドロップダウン ボックスから値を選択します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-117">To enter values for a parameter, type the value in the text box or select the value from the drop-down box.</span></span> <span data-ttu-id="21d4a-118">スイッチ パラメーターを追加するには、パラメーター チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="21d4a-118">To add a switch parameter, click to select the parameter check box.</span></span>

<span data-ttu-id="21d4a-119">準備ができたら、[ **Copy** ] をクリックして、作成したコマンドをクリップボードにコピーするか、[ **Run** ] をクリックしてコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-119">When you're ready, you can click **Copy** to copy the command that you've created to the clipboard or click **Run** to run the command.</span></span> <span data-ttu-id="21d4a-120">また、 **PassThru** パラメーターを使用して、PowerShell コンソールなどのホストプログラムにコマンドを返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-120">You can also use the **PassThru** parameter to return the command to the host program, such as the PowerShell console.</span></span> <span data-ttu-id="21d4a-121">コマンドの選択をキャンセルし、すべてのコマンドを表示するビューに戻るには、Ctrl キーを押しながら、選択したコマンドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="21d4a-121">To cancel the command selection and return to the view that displays all commands, press Ctrl and click the selected command.</span></span>

<span data-ttu-id="21d4a-122">PowerShell Integrated Scripting Environment (ISE) では、ウィンドウのバリエーション `Show-Command` が既定で表示されます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-122">In the PowerShell Integrated Scripting Environment (ISE), a variation of the `Show-Command` window is displayed by default.</span></span> <span data-ttu-id="21d4a-123">このコマンドウィンドウの使用方法の詳細については、PowerShell ISE のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="21d4a-123">For information about using this command window, see the PowerShell ISE Help topics.</span></span>

<span data-ttu-id="21d4a-124">このコマンドレットは、PowerShell 7 で再導入されました。</span><span class="sxs-lookup"><span data-stu-id="21d4a-124">This cmdlet was reintroduced in PowerShell 7.</span></span>

<span data-ttu-id="21d4a-125">このコマンドレットはユーザーインターフェイスを必要とするため、Windows Server Core または Windows Nano Server では機能しません。</span><span class="sxs-lookup"><span data-stu-id="21d4a-125">Because this cmdlet requires a user interface, it does not work on Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="21d4a-126">このコマンドレットは、Windows デスクトップをサポートする Windows システムでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-126">This cmdlet is only available on Windows systems that support the Windows Desktop.</span></span>

## <span data-ttu-id="21d4a-127">例</span><span class="sxs-lookup"><span data-stu-id="21d4a-127">EXAMPLES</span></span>

### <span data-ttu-id="21d4a-128">例 1: [コマンド] ウィンドウを開く</span><span class="sxs-lookup"><span data-stu-id="21d4a-128">Example 1: Open the Commands window</span></span>

<span data-ttu-id="21d4a-129">この例では、ウィンドウの既定のビューを表示し `Show-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-129">This example displays the default view of the `Show-Command` window.</span></span> <span data-ttu-id="21d4a-130">[ **コマンド** ] ウィンドウには、コンピューターにインストールされているすべてのモジュールのすべてのコマンドの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-130">The **Commands** window displays a list of all commands in all modules that are installed on the computer.</span></span>

```powershell
Show-Command
```

### <span data-ttu-id="21d4a-131">例 2: [コマンド] ウィンドウでコマンドレットを開く</span><span class="sxs-lookup"><span data-stu-id="21d4a-131">Example 2: Open a cmdlet in the Commands window</span></span>

<span data-ttu-id="21d4a-132">この例では `Invoke-Command` 、コマンドレットを **コマンド** ウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-132">This example display the `Invoke-Command` cmdlet in the **Command** window.</span></span> <span data-ttu-id="21d4a-133">この表示を使用して、コマンドを実行でき `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-133">You can use this display to run `Invoke-Command` commands.</span></span>

```powershell
Show-Command -Name "Invoke-Command"
```

### <span data-ttu-id="21d4a-134">例 3: 指定されたパラメーターを使用してコマンドレットを開く</span><span class="sxs-lookup"><span data-stu-id="21d4a-134">Example 3: Open a cmdlet with specified parameters</span></span>

<span data-ttu-id="21d4a-135">このコマンドを実行すると `Show-Command` 、コマンドレットのウィンドウが開き `Connect-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-135">This command opens a `Show-Command` window for the`Connect-PSSession`cmdlet.</span></span>

```powershell
Show-Command -Name "Connect-PSSession" -Height 700 -Width 1000 -ErrorPopup
```

<span data-ttu-id="21d4a-136">**高さ** と **幅** のパラメーターでは、コマンドウィンドウの次元を指定します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-136">The **Height** and **Width** parameters specify the dimension of the command window.</span></span> <span data-ttu-id="21d4a-137">**Errorpopup** パラメーターを指定すると、エラーコマンドウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-137">The **ErrorPopup** parameter displays the error command window.</span></span>

<span data-ttu-id="21d4a-138">[ **実行** ] をクリックすると、コマンドラインでコマンドを入力した `Connect-PSSession` 場合と同様に、コマンドが実行され `Connect-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-138">When you click **Run** , the `Connect-PSSession` command runs, just as would if you typed the `Connect-PSSession` command at the command line.</span></span>

### <span data-ttu-id="21d4a-139">例 4: コマンドレットの新しい既定のパラメーター値を指定する</span><span class="sxs-lookup"><span data-stu-id="21d4a-139">Example 4: Specify new default parameter values for a cmdlet</span></span>

<span data-ttu-id="21d4a-140">この例では、自動変数を使用して、 `$PSDefaultParameterValues` コマンドレットの **Height** 、 **Width** 、および **errorpopup** パラメーターに新しい既定値を設定し `Show-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-140">This example uses the `$PSDefaultParameterValues` automatic variable to set new default values for the **Height** , **Width** , and **ErrorPopup** parameters of the `Show-Command` cmdlet.</span></span>

```powershell
$PSDefaultParameterValues = @{
    "Show-Command:Height" = 700
    "Show-Command:Width" = 1000
    "Show-Command:ErrorPopup" = $True
}
```

<span data-ttu-id="21d4a-141">コマンドを実行すると `Show-Command` 、新しい既定値が自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-141">Now when you run a `Show-Command` command, the new defaults are applied automatically.</span></span> <span data-ttu-id="21d4a-142">すべての PowerShell セッションでこれらの既定値を使用するには、 `$PSDefaultParameterValues` powershell プロファイルに変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-142">To use these default values in every PowerShell session, add the `$PSDefaultParameterValues` variable to your PowerShell profile.</span></span> <span data-ttu-id="21d4a-143">詳細については、「 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md) 」および「 [about_Parameters_Default_Values](../Microsoft.PowerShell.Core/About/about_Parameters_Default_Values.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21d4a-143">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md) and [about_Parameters_Default_Values](../Microsoft.PowerShell.Core/About/about_Parameters_Default_Values.md).</span></span>

### <span data-ttu-id="21d4a-144">例 5: 出力をグリッドビューに送信する</span><span class="sxs-lookup"><span data-stu-id="21d4a-144">Example 5: Send output to a grid view</span></span>

<span data-ttu-id="21d4a-145">このコマンドは、コマンドレットとコマンドレットを一緒に使用する方法を示し `Show-Command` て `Out-GridView` います。</span><span class="sxs-lookup"><span data-stu-id="21d4a-145">This command shows how to use the `Show-Command` and `Out-GridView` cmdlets together.</span></span>

```powershell
Show-Command Get-ChildItem | Out-GridView
```

<span data-ttu-id="21d4a-146">コマンドレットを使用してコマンド `Show-Command` レットのコマンドウィンドウを開き `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-146">The command uses the `Show-Command` cmdlet to open a command window for the`Get-ChildItem`cmdlet.</span></span>
<span data-ttu-id="21d4a-147">[ **実行** ] ボタンをクリックすると、コマンドが実行され、 `Get-ChildItem` 出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-147">When you click the **Run** button, the `Get-ChildItem` command runs and generates output.</span></span> <span data-ttu-id="21d4a-148">パイプライン演算子 (|) は、コマンドの出力を `Get-ChildItem` コマンドレットに送信します。これにより、 `Out-GridView` `Get-ChildItem` 対話型ウィンドウに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-148">The pipeline operator ( | ) sends the output of the `Get-ChildItem` command to the `Out-GridView` cmdlet, which displays the `Get-ChildItem` output in an interactive window.</span></span>

### <span data-ttu-id="21d4a-149">例 6: [コマンド] ウィンドウで作成したコマンドを表示する</span><span class="sxs-lookup"><span data-stu-id="21d4a-149">Example 6: Display a command that you create in the Commands window</span></span>

<span data-ttu-id="21d4a-150">この例は、ウィンドウで作成したコマンドを示して `Show-Command` います。</span><span class="sxs-lookup"><span data-stu-id="21d4a-150">This example shows the command that you created in the `Show-Command` window.</span></span> <span data-ttu-id="21d4a-151">このコマンドは、 **PassThru** パラメーターを使用します。これにより、結果が文字列として返され `Show-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-151">The command uses the **PassThru** parameter, which returns the `Show-Command` results in a string.</span></span>

```powershell
Show-Command -PassThru
```

```Output
Get-EventLog -LogName "Windows PowerShell" -Newest 5
```

<span data-ttu-id="21d4a-152">たとえば、 `Show-Command` `Get-EventLog` Windows PowerShell イベントログ内の最新の5つのイベントを取得するコマンドをウィンドウで作成し、[ **OK** ] をクリックすると、上記の出力が返されます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-152">For example, if you use the `Show-Command` window to create a `Get-EventLog` command that gets the five newest events in the Windows PowerShell event log, and then click **OK** , the command returns the output shown above.</span></span> <span data-ttu-id="21d4a-153">コマンド文字列を表示すると、PowerShell の学習に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-153">Viewing the command string helps you learn PowerShell.</span></span>

### <span data-ttu-id="21d4a-154">例 7: コマンドを変数に保存する</span><span class="sxs-lookup"><span data-stu-id="21d4a-154">Example 7: Save a command to a variable</span></span>

<span data-ttu-id="21d4a-155">この例では、コマンドレットの **PassThru** パラメーターを使用したときに取得したコマンド文字列を実行する方法を示し `Show-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-155">This example shows how to run the command string that you get when you use the **PassThru** parameter of the `Show-Command` cmdlet.</span></span> <span data-ttu-id="21d4a-156">この方法により、コマンドを表示して使用することができます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-156">This strategy lets you see the command and use it.</span></span>

```powershell
$C = Show-Command -PassThru
$C
Invoke-Expression $C
```

```Output
Get-EventLog -LogName "PowerShell" -Newest 5

Index Time          EntryType   Source                 InstanceID Message
----- ----          ---------   ------                 ---------- -------
11520 Dec 16 16:37  Information Windows PowerShell            400 Engine state is changed from None to Available...
11519 Dec 16 16:37  Information Windows PowerShell            600 Provider "Variable" is Started. ...
11518 Dec 16 16:37  Information Windows PowerShell            600 Provider "Registry" is Started. ...
11517 Dec 16 16:37  Information Windows PowerShell            600 Provider "Function" is Started. ...
11516 Dec 16 16:37  Information Windows PowerShell            600 Provider "FileSystem" is Started. ...
```

<span data-ttu-id="21d4a-157">最初のコマンドは、コマンドレットの **PassThru** パラメーター `Show-Command` を使用して、コマンドの結果を変数に保存し `$C` ます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-157">The first command uses the **PassThru** parameter of the `Show-Command` cmdlet and saves the results of the command in the `$C` variable.</span></span> <span data-ttu-id="21d4a-158">この場合は、ウィンドウを使用して、 `Show-Command` `Get-EventLog` Windows PowerShell イベントログ内の最新の5つのイベントを取得するコマンドを作成します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-158">In this case, we use the `Show-Command` window to create a `Get-EventLog` command that gets the five newest events in the Windows PowerShell event log.</span></span> <span data-ttu-id="21d4a-159">[ **OK** ] をクリックすると、 `Show-Command` コマンド文字列が返されます。この文字列は変数に保存されてい `$C` ます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-159">When you click **OK** , `Show-Command` returns the command string, which is saved in the `$C` variable.</span></span>

### <span data-ttu-id="21d4a-160">例 8: コマンドの出力を変数に保存する</span><span class="sxs-lookup"><span data-stu-id="21d4a-160">Example 8: Save the output of a command to a variable</span></span>

<span data-ttu-id="21d4a-161">この例では、 **Errorpopup** パラメーターを使用して、コマンドの出力を変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-161">This example uses the **ErrorPopup** parameter to save the output of a command in a variable.</span></span>

```powershell
$P = Show-Command Get-Process -ErrorPopup
$P
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    473      33    94096     112532   709     2.06   4492 powershell
```

<span data-ttu-id="21d4a-162">**ErrorPopup** は、ウィンドウにエラーを表示するだけでなく、新しいコマンドを作成する代わりにコマンドの出力を現在のコマンドに返します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-162">In addition to displaying errors in a window, **ErrorPopup** returns command output to the current command, instead of creating a new command.</span></span> <span data-ttu-id="21d4a-163">このコマンドを実行すると、 `Show-Command` ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-163">When you run this command, the `Show-Command` window opens.</span></span> <span data-ttu-id="21d4a-164">ウィンドウの機能を使用して、パラメーターの値を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-164">You can use the window features to set parameter values.</span></span> <span data-ttu-id="21d4a-165">コマンドを実行するには、ウィンドウの [ **実行** ] ボタンをクリックし `Show-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-165">To run the command, click the **Run** button in the `Show-Command` window.</span></span>

## <span data-ttu-id="21d4a-166">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="21d4a-166">PARAMETERS</span></span>

### <span data-ttu-id="21d4a-167">-ErrorPopup</span><span class="sxs-lookup"><span data-stu-id="21d4a-167">-ErrorPopup</span></span>

<span data-ttu-id="21d4a-168">コマンドレットによってエラーがコマンドラインに表示されるだけでなく、ポップアップウィンドウに表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-168">Indicates that the cmdlet displays errors in a pop-up window, in addition to displaying them at the command line.</span></span> <span data-ttu-id="21d4a-169">既定では、ウィンドウで実行されるコマンドが `Show-Command` エラーを生成すると、そのエラーはコマンドラインでのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-169">By default, when a command that is run in a `Show-Command` window generates an error, the error is displayed only at the command line.</span></span>

<span data-ttu-id="21d4a-170">また、(ウィンドウの [ **実行** ] ボタンを使用して) コマンドを実行すると、コマンドを `Show-Command` 実行して出力を新しいコマンドに返すのではなく、 **errorpopup** パラメーターによってコマンドの結果が現在のコマンドに返されます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-170">Also, when you run the command (by using the **Run** button in the `Show-Command` window), the **ErrorPopup** parameter returns the command results to the current command, instead of running the command and returning its output to a new command.</span></span> <span data-ttu-id="21d4a-171">この機能を使用すると、コマンドの結果を変数に保存できます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-171">You can use this feature to save the command results in a variable.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21d4a-172">-高さ</span><span class="sxs-lookup"><span data-stu-id="21d4a-172">-Height</span></span>

<span data-ttu-id="21d4a-173">ウィンドウの高さをピクセル単位で指定し `Show-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-173">Specifies the height of the `Show-Command` window in pixels.</span></span> <span data-ttu-id="21d4a-174">300 以上で画面の解像度以下の値を入力します (ピクセル単位)。</span><span class="sxs-lookup"><span data-stu-id="21d4a-174">Enter a value between 300 and the number of pixels in the screen resolution.</span></span> <span data-ttu-id="21d4a-175">値が大きすぎて画面にコマンドウィンドウを表示できない場合は、に `Show-Command` よってエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-175">If the value is too large to display the command window on the screen, `Show-Command` generates an error.</span></span> <span data-ttu-id="21d4a-176">既定の高さは 600 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="21d4a-176">The default height is 600 pixels.</span></span> <span data-ttu-id="21d4a-177">`Show-Command` **Name** パラメーターを含むコマンドの場合、既定の高さは300ピクセルになります。</span><span class="sxs-lookup"><span data-stu-id="21d4a-177">For a `Show-Command` command that includes the **Name** parameter, the default height is 300 pixels.</span></span>

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21d4a-178">-Name</span><span class="sxs-lookup"><span data-stu-id="21d4a-178">-Name</span></span>

<span data-ttu-id="21d4a-179">指定されたコマンドについて、コマンド ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-179">Displays a command window for the specified command.</span></span> <span data-ttu-id="21d4a-180">コマンドレット、関数、または CIM コマンドの名前など、1つのコマンドの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-180">Enter the name of one command, such as the name of a cmdlet, function, or CIM command.</span></span> <span data-ttu-id="21d4a-181">このパラメーターを省略した場合、には、 `Show-Command` コンピューターにインストールされているすべてのモジュールのすべての PowerShell コマンドを一覧表示するコマンドウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-181">If you omit this parameter, `Show-Command` displays a command window that lists all of the PowerShell commands in all modules installed on the computer.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CommandName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21d4a-182">-NoCommonParameter</span><span class="sxs-lookup"><span data-stu-id="21d4a-182">-NoCommonParameter</span></span>

<span data-ttu-id="21d4a-183">このコマンドレットがコマンド表示の共通パラメーターセクションを省略することを示します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-183">Indicates that this cmdlet omits the Common Parameters section of the command display.</span></span> <span data-ttu-id="21d4a-184">既定では、共通パラメーターはコマンド ウィンドウの下部の展開可能なセクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-184">By default, the Common Parameters appear in an expandable section at the bottom of the command window.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21d4a-185">-PassThru</span><span class="sxs-lookup"><span data-stu-id="21d4a-185">-PassThru</span></span>

<span data-ttu-id="21d4a-186">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-186">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="21d4a-187">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="21d4a-187">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="21d4a-188">コマンド文字列を実行するには、コマンドプロンプトでコピーして貼り付けます。または、変数に保存し、コマンドレットを使用して `Invoke-Expression` 変数内の文字列を実行します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-188">To run the command string, copy and paste it at the command prompt or save it in a variable and use the `Invoke-Expression` cmdlet to run the string in the variable.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21d4a-189">-Width</span><span class="sxs-lookup"><span data-stu-id="21d4a-189">-Width</span></span>

<span data-ttu-id="21d4a-190">ウィンドウの幅をピクセル単位で指定し `Show-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-190">Specifies the width of the `Show-Command` window in pixels.</span></span> <span data-ttu-id="21d4a-191">300 以上で画面の解像度以下の値を入力します (ピクセル単位)。</span><span class="sxs-lookup"><span data-stu-id="21d4a-191">Enter a value between 300 and the number of pixels in the screen resolution.</span></span> <span data-ttu-id="21d4a-192">値が大きすぎて画面にコマンドウィンドウを表示できない場合は、に `Show-Command` よってエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-192">If the value is too large to display the command window on the screen, `Show-Command` generates an error.</span></span> <span data-ttu-id="21d4a-193">既定の幅は 300 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="21d4a-193">The default width is 300 pixels.</span></span>

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21d4a-194">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="21d4a-194">CommonParameters</span></span>

<span data-ttu-id="21d4a-195">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="21d4a-195">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="21d4a-196">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21d4a-196">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="21d4a-197">入力</span><span class="sxs-lookup"><span data-stu-id="21d4a-197">INPUTS</span></span>

### <span data-ttu-id="21d4a-198">なし</span><span class="sxs-lookup"><span data-stu-id="21d4a-198">None</span></span>

<span data-ttu-id="21d4a-199">入力をにパイプすることはできません `Show-Command` 。</span><span class="sxs-lookup"><span data-stu-id="21d4a-199">You cannot pipe input to `Show-Command`.</span></span>

## <span data-ttu-id="21d4a-200">出力</span><span class="sxs-lookup"><span data-stu-id="21d4a-200">OUTPUTS</span></span>

### <span data-ttu-id="21d4a-201">None、System.string、System.object</span><span class="sxs-lookup"><span data-stu-id="21d4a-201">None, System.String, System.Object</span></span>

<span data-ttu-id="21d4a-202">**PassThru** パラメーターを使用すると、は `Show-Command` コマンド文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-202">When you use the **PassThru** parameter, `Show-Command` returns a command string.</span></span> <span data-ttu-id="21d4a-203">**Errorpopup** パラメーターを使用すると、は `Show-Command` コマンド出力 (すべてのオブジェクト) を返します。</span><span class="sxs-lookup"><span data-stu-id="21d4a-203">When you use the **ErrorPopup** parameter, `Show-Command` returns the command output (any object).</span></span> <span data-ttu-id="21d4a-204">それ以外の場合、 `Show-Command` は出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="21d4a-204">Otherwise, `Show-Command` does not generate any output.</span></span>

## <span data-ttu-id="21d4a-205">注</span><span class="sxs-lookup"><span data-stu-id="21d4a-205">NOTES</span></span>

<span data-ttu-id="21d4a-206">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="21d4a-206">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="21d4a-207">`Show-Command` リモートセッションでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="21d4a-207">`Show-Command` does not work in remote sessions.</span></span>

## <span data-ttu-id="21d4a-208">関連リンク</span><span class="sxs-lookup"><span data-stu-id="21d4a-208">RELATED LINKS</span></span>
