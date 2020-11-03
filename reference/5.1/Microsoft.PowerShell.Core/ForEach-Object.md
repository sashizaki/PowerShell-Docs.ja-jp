---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ForEach-Object
ms.openlocfilehash: 327add884077083d37e1f58ab8f78b784a870362
ms.sourcegitcommit: e0f9fe6335be1e0f94bedaa0e8baec2acaeaa076
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "93219880"
---
# <span data-ttu-id="9ca8a-103">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="9ca8a-103">ForEach-Object</span></span>

## <span data-ttu-id="9ca8a-104">構文</span><span class="sxs-lookup"><span data-stu-id="9ca8a-104">Synopsis</span></span>
<span data-ttu-id="9ca8a-105">入力オブジェクトのコレクション内の各項目に対して操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-105">Performs an operation against each item in a collection of input objects.</span></span>

## <span data-ttu-id="9ca8a-106">構文</span><span class="sxs-lookup"><span data-stu-id="9ca8a-106">Syntax</span></span>

### <span data-ttu-id="9ca8a-107">ScriptBlockSet (既定)</span><span class="sxs-lookup"><span data-stu-id="9ca8a-107">ScriptBlockSet (Default)</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-Begin <ScriptBlock>] [-Process] <ScriptBlock[]>
 [-End <ScriptBlock>] [-RemainingScripts <ScriptBlock[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9ca8a-108">PropertyAndMethodSet</span><span class="sxs-lookup"><span data-stu-id="9ca8a-108">PropertyAndMethodSet</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-MemberName] <String> [-ArgumentList <Object[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9ca8a-109">説明</span><span class="sxs-lookup"><span data-stu-id="9ca8a-109">Description</span></span>

<span data-ttu-id="9ca8a-110">`ForEach-Object`コマンドレットは、入力オブジェクトのコレクション内の各項目に対して操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-110">The `ForEach-Object` cmdlet performs an operation on each item in a collection of input objects.</span></span> <span data-ttu-id="9ca8a-111">入力オブジェクトは、コマンドレットにパイプすることも、 **InputObject** パラメーターを使用して指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-111">The input objects can be piped to the cmdlet or specified by using the **InputObject** parameter.</span></span>

<span data-ttu-id="9ca8a-112">Windows PowerShell 3.0 以降では、コマンドを構築する方法は2つあり `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-112">Starting in Windows PowerShell 3.0, there are two different ways to construct a `ForEach-Object` command.</span></span>

- <span data-ttu-id="9ca8a-113">**スクリプトブロック** 。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-113">**Script block**.</span></span> <span data-ttu-id="9ca8a-114">スクリプト ブロックを使用して、操作を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-114">You can use a script block to specify the operation.</span></span> <span data-ttu-id="9ca8a-115">スクリプトブロック内で、変数を使用して `$_` 現在のオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-115">Within the script block, use the `$_` variable to represent the current object.</span></span> <span data-ttu-id="9ca8a-116">スクリプト ブロックは、 **Process** パラメーターの値です。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-116">The script block is the value of the **Process** parameter.</span></span> <span data-ttu-id="9ca8a-117">スクリプトブロックには、任意の PowerShell スクリプトを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-117">The script block can contain any PowerShell script.</span></span>

  <span data-ttu-id="9ca8a-118">たとえば、次のコマンドでは、コンピューター上の各プロセスの **ProcessName** プロパティの値を取得します</span><span class="sxs-lookup"><span data-stu-id="9ca8a-118">For example, the following command gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object {$_.ProcessName}`

  <span data-ttu-id="9ca8a-119">`ForEach-Object` 「 `begin` `process` `end` [about_functions](about/about_functions.md#piping-objects-to-functions)」で説明されているように、、、およびの各ブロックをサポートします。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-119">`ForEach-Object` supports the `begin`, `process`, and `end` blocks as described in [about_functions](about/about_functions.md#piping-objects-to-functions).</span></span>

  > [!NOTE]
  > <span data-ttu-id="9ca8a-120">スクリプトブロックは、呼び出し元のスコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-120">The script blocks run in the caller's scope.</span></span> <span data-ttu-id="9ca8a-121">したがって、ブロックはそのスコープ内の変数にアクセスでき、コマンドレットの完了後にそのスコープに保持される新しい変数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-121">Therefore the blocks have access to variables in that scope and can create new variables that persist in that scope after the cmdlet completes.</span></span>

- <span data-ttu-id="9ca8a-122">**Operation ステートメント** 。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-122">**Operation statement**.</span></span> <span data-ttu-id="9ca8a-123">また、操作ステートメントを記述することもできます。これは自然言語に似ています。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-123">You can also write an operation statement, which is much more like natural language.</span></span> <span data-ttu-id="9ca8a-124">操作のステートメントを使用してプロパティの値を指定することも、メソッドを呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-124">You can use the operation statement to specify a property value or call a method.</span></span> <span data-ttu-id="9ca8a-125">操作のステートメントは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-125">Operation statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="9ca8a-126">たとえば、次のコマンドでは、コンピューター上の各プロセスの **ProcessName** プロパティの値も取得します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-126">For example, the following command also gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object ProcessName`

## <span data-ttu-id="9ca8a-127">例</span><span class="sxs-lookup"><span data-stu-id="9ca8a-127">Examples</span></span>

### <span data-ttu-id="9ca8a-128">例 1: 配列の整数を除算する</span><span class="sxs-lookup"><span data-stu-id="9ca8a-128">Example 1: Divide integers in an array</span></span>

<span data-ttu-id="9ca8a-129">この例では、3つの整数の配列を受け取り、それぞれを1024で除算します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-129">This example takes an array of three integers and divides each one of them by 1024.</span></span>

```powershell
30000, 56798, 12432 | ForEach-Object -Process {$_/1024}
```

```Output
29.296875
55.466796875
12.140625
```

### <span data-ttu-id="9ca8a-130">例 2: ディレクトリ内のすべてのファイルの長さを取得する</span><span class="sxs-lookup"><span data-stu-id="9ca8a-130">Example 2: Get the length of all the files in a directory</span></span>

<span data-ttu-id="9ca8a-131">この例では、PowerShell インストールディレクトリ内のファイルとディレクトリを処理し `$PSHOME` ます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-131">This example processes the files and directories in the PowerShell installation directory `$PSHOME`.</span></span>

```powershell
Get-ChildItem $PSHOME |
  ForEach-Object -Process {if (!$_.PSIsContainer) {$_.Name; $_.Length / 1024; " " }}
```

<span data-ttu-id="9ca8a-132">オブジェクトがディレクトリではない場合、スクリプトブロックはファイルの名前を取得し、その **長さ** のプロパティの値を1024で割り、次のエントリと区別するためにスペース ("") を追加します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-132">If the object is not a directory, the script block gets the name of the file, divides the value of its **Length** property by 1024, and adds a space (" ") to separate it from the next entry.</span></span> <span data-ttu-id="9ca8a-133">コマンドレットでは、 **PSISContainer** プロパティを使用して、オブジェクトがディレクトリであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-133">The cmdlet uses the **PSISContainer** property to determine whether an object is a directory.</span></span>

### <span data-ttu-id="9ca8a-134">例 3: 最新のシステムイベントを操作する</span><span class="sxs-lookup"><span data-stu-id="9ca8a-134">Example 3: Operate on the most recent System events</span></span>

<span data-ttu-id="9ca8a-135">この例では、システムイベントログから1000の最新のイベントをテキストファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-135">This example write the 1000 most recent events from the System event log to a text file.</span></span> <span data-ttu-id="9ca8a-136">イベントの処理の前後に、現在の時刻が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-136">The current time is displayed before and after processing the events.</span></span>

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$events | ForEach-Object -Begin {Get-Date} -Process {Out-File -FilePath Events.txt -Append -InputObject $_.Message} -End {Get-Date}
```

<span data-ttu-id="9ca8a-137">`Get-EventLog` システムイベントログから1000の最新のイベントを取得し、変数に格納し `$Events` ます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-137">`Get-EventLog` gets the 1000 most recent events from the System event log and stores them in the `$Events` variable.</span></span> <span data-ttu-id="9ca8a-138">`$Events` 次に、をコマンドレットにパイプ処理し `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-138">`$Events` is then piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="9ca8a-139">**Begin** パラメーターは、現在の日付と時刻を示します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-139">The **Begin** parameter displays the current date and time.</span></span> <span data-ttu-id="9ca8a-140">次に、 **Process** パラメーターは、コマンドレットを使用して `Out-File` events.txt という名前のテキストファイルを作成し、そのファイル内の各イベントの message プロパティを格納します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-140">Next, the **Process** parameter uses the `Out-File` cmdlet to create a text file that is named events.txt and stores the message property of each of the events in that file.</span></span> <span data-ttu-id="9ca8a-141">最後に、 **End** パラメーターは、すべての処理が完了した後の日付と時刻を示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-141">Last, the **End** parameter is used to display the date and time after all of the processing has completed.</span></span>

### <span data-ttu-id="9ca8a-142">例 4: レジストリキーの値を変更する</span><span class="sxs-lookup"><span data-stu-id="9ca8a-142">Example 4: Change the value of a Registry key</span></span>

<span data-ttu-id="9ca8a-143">この例では、キーの下にあるすべてのサブキーの **RemotePath** レジストリエントリの値 `HKCU:\Network` を大文字に変更します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-143">This example changes the value of the **RemotePath** registry entry in all of the subkeys under the `HKCU:\Network` key to uppercase text.</span></span>

```powershell
Get-ItemProperty -Path HKCU:\Network\* |
  ForEach-Object {Set-ItemProperty -Path $_.PSPath -Name RemotePath -Value $_.RemotePath.ToUpper();}
```

<span data-ttu-id="9ca8a-144">このフォーマットを使用して、レジストリ エントリ値の形式や内容を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-144">You can use this format to change the form or content of a registry entry value.</span></span>

<span data-ttu-id="9ca8a-145">**Network** キー内の各サブキーは、ログオン時に再接続するマップ済みネットワーク ドライブを示します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-145">Each subkey in the **Network** key represents a mapped network drive that will reconnect at logon.</span></span>
<span data-ttu-id="9ca8a-146">**RemotePath** エントリには、接続されているドライブの UNC パスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-146">The **RemotePath** entry contains the UNC path of the connected drive.</span></span> <span data-ttu-id="9ca8a-147">たとえば、E: ドライブをにマップする `\\Server\Share` と、の **e** サブキーが存在し、 `HKCU:\Network` **e** サブキーの **RemotePath** レジストリエントリの値はになり `\\Server\Share` ます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-147">For example, if you map the E: drive to `\\Server\Share`, there will be an **E** subkey of `HKCU:\Network` and the value of the **RemotePath** registry entry in the **E** subkey is `\\Server\Share`.</span></span>

<span data-ttu-id="9ca8a-148">このコマンドは、コマンドレットを使用して `Get-ItemProperty` **ネットワーク** キーのすべてのサブキーを取得し、コマンドレットを使用して `Set-ItemProperty` 各キーの **RemotePath** レジストリエントリの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-148">The command uses the `Get-ItemProperty` cmdlet to get all of the subkeys of the **Network** key and the `Set-ItemProperty` cmdlet to change the value of the **RemotePath** registry entry in each key.</span></span>
<span data-ttu-id="9ca8a-149">コマンドの `Set-ItemProperty` パスは、レジストリキーの **pspath** プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-149">In the `Set-ItemProperty` command, the path is the value of the **PSPath** property of the registry key.</span></span> <span data-ttu-id="9ca8a-150">これは、レジストリエントリではなく、レジストリキーを表す Microsoft .NET Framework オブジェクトのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-150">This is a property of the Microsoft .NET Framework object that represents the registry key, not a registry entry.</span></span> <span data-ttu-id="9ca8a-151">このコマンドでは、 **RemotePath** 値の **ToUpper ()** メソッドを使用します。これは文字列 (REG_SZ) です。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-151">The command uses the **ToUpper()** method of the **RemotePath** value, which is a string (REG_SZ).</span></span>

<span data-ttu-id="9ca8a-152">`Set-ItemProperty`は各キーのプロパティを変更するため、 `ForEach-Object` プロパティにアクセスするにはコマンドレットが必要です。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-152">Because `Set-ItemProperty` is changing the property of each key, the `ForEach-Object` cmdlet is required to access the property.</span></span>

### <span data-ttu-id="9ca8a-153">例 5: $Null 自動変数を使用する</span><span class="sxs-lookup"><span data-stu-id="9ca8a-153">Example 5: Use the $Null automatic variable</span></span>

<span data-ttu-id="9ca8a-154">この例は、 `$Null` 自動変数をコマンドレットにパイプした場合の効果を示して `ForEach-Object` います。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-154">This example shows the effect of piping the `$Null` automatic variable to the `ForEach-Object` cmdlet.</span></span>

```powershell
1, 2, $null, 4 | ForEach-Object {"Hello"}
```

```Output
Hello
Hello
Hello
Hello
```

<span data-ttu-id="9ca8a-155">PowerShell では null が明示的なプレースホルダーとして扱われるため、 `ForEach-Object` このコマンドレットは `$Null` 、パイプを使用する他のオブジェクトと同様に、の値を生成します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-155">Because PowerShell treats null as an explicit placeholder, the `ForEach-Object` cmdlet generates a value for `$Null`, just as it does for other objects that you pipe to it.</span></span>

### <span data-ttu-id="9ca8a-156">例 6: プロパティ値を取得する</span><span class="sxs-lookup"><span data-stu-id="9ca8a-156">Example 6: Get property values</span></span>

<span data-ttu-id="9ca8a-157">この例では、コマンドレットの **MemberName** パラメーターを使用して、インストールされているすべての PowerShell モジュールの **Path** プロパティの値を取得し `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-157">This example gets the value of the **Path** property of all installed PowerShell modules by using the **MemberName** parameter of the `ForEach-Object` cmdlet.</span></span>

```powershell
Get-Module -ListAvailable | ForEach-Object -MemberName Path
Get-Module -ListAvailable | Foreach Path
```

<span data-ttu-id="9ca8a-158">2 番目のコマンドは、1 番目のコマンドと同等です。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-158">The second command is equivalent to the first.</span></span> <span data-ttu-id="9ca8a-159">`Foreach`コマンドレットのエイリアスを使用 `ForEach-Object` し、 **MemberName** パラメーターの名前を省略します。これは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-159">It uses the `Foreach` alias of the `ForEach-Object` cmdlet and omits the name of the **MemberName** parameter, which is optional.</span></span>

<span data-ttu-id="9ca8a-160">コマンドレットは、プロパティ値の `ForEach-Object` 型を変更する **Format** コマンドレットやコマンドレットとは異なり、型を変更せずに値を取得するため、プロパティ値を取得する場合に非常に便利です `Select-Object` 。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-160">The `ForEach-Object` cmdlet is very useful for getting property values, because it gets the value without changing the type, unlike the **Format** cmdlets or the `Select-Object` cmdlet, which change the property value type.</span></span>

### <span data-ttu-id="9ca8a-161">例 7: モジュール名をコンポーネント名に分割する</span><span class="sxs-lookup"><span data-stu-id="9ca8a-161">Example 7: Split module names into component names</span></span>

<span data-ttu-id="9ca8a-162">この例では、2つのドットで区切られたモジュール名をコンポーネント名に分割する3つの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-162">This examples shows three ways to split two dot-separated module names into their component names.</span></span>

```powershell
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object {$_.Split(".")}
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object -MemberName Split -ArgumentList "."
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | Foreach Split "."
```

```Output
Microsoft
PowerShell
Core
Microsoft
PowerShell
Host
```

<span data-ttu-id="9ca8a-163">このコマンドは、文字列の **Split** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-163">The commands call the **Split** method of strings.</span></span> <span data-ttu-id="9ca8a-164">3 つのコマンドは、別の構文を使用しますが、すべて同等であり、交換可能です。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-164">The three commands use different syntax, but they are equivalent and interchangeable.</span></span>

<span data-ttu-id="9ca8a-165">最初のコマンドは、スクリプトブロックと現在のオブジェクト演算子を含む従来の構文を使用し `$_` ます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-165">The first command uses the traditional syntax, which includes a script block and the current object operator `$_`.</span></span> <span data-ttu-id="9ca8a-166">メソッドの指定にドット構文を使用し、区切り記号の引数を囲むためにかっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-166">It uses the dot syntax to specify the method and parentheses to enclose the delimiter argument.</span></span>

<span data-ttu-id="9ca8a-167">2 番目のコマンドは、 **MemberName** パラメーターを使用して **Split** メソッドを指定し、 **ArgumentName** パラメーターを使用してドット (".") を分割の区切り記号として識別します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-167">The second command uses the **MemberName** parameter to specify the **Split** method and the **ArgumentName** parameter to identify the dot (".") as the split delimiter.</span></span>

<span data-ttu-id="9ca8a-168">3番目のコマンドは、コマンドレットの **Foreach** エイリアスを使用 `ForEach-Object` して、 **MemberName** および **ArgumentList** パラメーターの名前を省略します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-168">The third command uses the **Foreach** alias of the `ForEach-Object` cmdlet and omits the names of the **MemberName** and **ArgumentList** parameters, which are optional.</span></span>

### <span data-ttu-id="9ca8a-169">例 8: 2 つのスクリプトブロックと共に ForEach-Object を使用する</span><span class="sxs-lookup"><span data-stu-id="9ca8a-169">Example 8: Using ForEach-Object with two script blocks</span></span>

<span data-ttu-id="9ca8a-170">この例では、2つのスクリプトブロック位置を渡します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-170">In this example we pass two script blocks positionally.</span></span> <span data-ttu-id="9ca8a-171">すべてのスクリプトブロックが **Process** パラメーターにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-171">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="9ca8a-172">ただし、これらは **Begin** および **Process** パラメーターに渡されたものとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-172">However, they are treated as if they had been passed to the **Begin** and **Process** parameters.</span></span>

```powershell
1..2 | ForEach-Object { 'begin' } { 'process' }
```

```Output
begin
process
process
```

### <span data-ttu-id="9ca8a-173">例 9: 3 つ以上のスクリプトブロックと共に ForEach-Object を使用する</span><span class="sxs-lookup"><span data-stu-id="9ca8a-173">Example 9: Using ForEach-Object with more than two script blocks</span></span>

<span data-ttu-id="9ca8a-174">この例では、2つのスクリプトブロック位置を渡します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-174">In this example we pass two script blocks positionally.</span></span> <span data-ttu-id="9ca8a-175">すべてのスクリプトブロックが **Process** パラメーターにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-175">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="9ca8a-176">ただし、これらは **Begin** 、 **Process** 、および **End** パラメーターに渡されたものとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-176">However, they are treated as if they had been passed to the **Begin** , **Process** , and **End** parameters.</span></span>

```powershell
1..2 | ForEach-Object { 'begin' } { 'process A' }  { 'process B' }  { 'end' }
```

```Output
begin
process A
process B
process A
process B
end
```

> [!NOTE]
> <span data-ttu-id="9ca8a-177">最初のスクリプトブロックは常にブロックにマップされ、最後のブロックはブロックにマップされ、 `begin` `end` between 内のブロックはすべてブロックにマップされ `process` ます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-177">The first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

### <span data-ttu-id="9ca8a-178">例 10: パイプライン項目ごとに複数のスクリプトブロックを実行する</span><span class="sxs-lookup"><span data-stu-id="9ca8a-178">Example 10: Run multiple script blocks for each pipeline item</span></span>

<span data-ttu-id="9ca8a-179">前の例で示したように、 **Process** パラメーターを使用して渡された複数のスクリプトブロックは、 **Begin** および **End** パラメーターにマップされます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-179">As shown in the previous example, multiple script blocks passed using the **Process** parameter get mapped to the **Begin** and **End** parameters.</span></span> <span data-ttu-id="9ca8a-180">このマッピングを回避するには、 **Begin** および **End** パラメーターに明示的な値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-180">To avoid this mapping, you must provide explicit values for the **Begin** and **End** parameters.</span></span>

```powershell
1..2 | ForEach-Object -Begin $null -Process { 'one' }, { 'two' }, { 'three' } -End $null
```

```Output
one
two
three
one
two
three
```

## <span data-ttu-id="9ca8a-181">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9ca8a-181">Parameters</span></span>

### <span data-ttu-id="9ca8a-182">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="9ca8a-182">-ArgumentList</span></span>

<span data-ttu-id="9ca8a-183">メソッド呼び出しの引数の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-183">Specifies an array of arguments to a method call.</span></span> <span data-ttu-id="9ca8a-184">**ArgumentList** の動作の詳細については、「 [about_Splatting](about/about_Splatting.md#splatting-with-arrays)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-184">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="9ca8a-185">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-185">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: PropertyAndMethodSet
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ca8a-186">-開始</span><span class="sxs-lookup"><span data-stu-id="9ca8a-186">-Begin</span></span>

<span data-ttu-id="9ca8a-187">このコマンドレットが入力オブジェクトを処理する前に実行されるスクリプトブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-187">Specifies a script block that runs before this cmdlet processes any input objects.</span></span> <span data-ttu-id="9ca8a-188">このスクリプトブロックは、パイプライン全体に対して1回だけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-188">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="9ca8a-189">ブロックの詳細については `begin` 、「 [about_Functions](about/about_functions.md#piping-objects-to-functions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-189">For more information about the `begin` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ca8a-190">-End</span><span class="sxs-lookup"><span data-stu-id="9ca8a-190">-End</span></span>

<span data-ttu-id="9ca8a-191">このコマンドレットによってすべての入力オブジェクトが処理された後に実行されるスクリプトブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-191">Specifies a script block that runs after this cmdlet processes all input objects.</span></span> <span data-ttu-id="9ca8a-192">このスクリプトブロックは、パイプライン全体に対して1回だけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-192">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="9ca8a-193">ブロックの詳細については `end` 、「 [about_Functions](about/about_functions.md#piping-objects-to-functions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-193">For more information about the `end` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ca8a-194">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9ca8a-194">-InputObject</span></span>

<span data-ttu-id="9ca8a-195">入力オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-195">Specifies the input objects.</span></span> <span data-ttu-id="9ca8a-196">`ForEach-Object` 各入力オブジェクトに対して、スクリプトブロックまたは操作ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-196">`ForEach-Object` runs the script block or operation statement on each input object.</span></span> <span data-ttu-id="9ca8a-197">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-197">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="9ca8a-198">で **inputobject** パラメーターを使用すると、 `ForEach-Object` コマンドの結果をにパイプするのではなく、 `ForEach-Object` **inputobject** 値が1つのオブジェクトとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-198">When you use the **InputObject** parameter with `ForEach-Object`, instead of piping command results to `ForEach-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="9ca8a-199">これは、値が、などのコマンドの結果であるコレクションである場合にも当てはまり `-InputObject (Get-Process)` ます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-199">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span>
<span data-ttu-id="9ca8a-200">**InputObject** は配列またはオブジェクトのコレクションから個々のプロパティを返すことができないため、を使用し `ForEach-Object` て、定義されたプロパティに特定の値を持つオブジェクトのオブジェクトのコレクションに対して操作を実行する場合は、 `ForEach-Object` このトピックの例に示すように、パイプラインでを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-200">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that if you use `ForEach-Object` to perform operations on a collection of objects for those objects that have specific values in defined properties, you use `ForEach-Object` in the pipeline, as shown in the examples in this topic.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9ca8a-201">-MemberName</span><span class="sxs-lookup"><span data-stu-id="9ca8a-201">-MemberName</span></span>

<span data-ttu-id="9ca8a-202">取得するプロパティまたは呼び出すメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-202">Specifies the property to get or the method to call.</span></span>

<span data-ttu-id="9ca8a-203">ワイルドカード文字は使用できますが、結果の文字列が一意の値に解決される場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-203">Wildcard characters are permitted, but work only if the resulting string resolves to a unique value.</span></span>
<span data-ttu-id="9ca8a-204">たとえば、を実行したときに、 `Get-Process | ForEach -MemberName *Name` **ProcessName** プロパティや **name** プロパティなど、文字列名を含む名前を持つ複数のメンバーが存在する場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-204">If, for example, you run `Get-Process | ForEach -MemberName *Name`, and more than one member exists with a name that contains the string Name, such as the **ProcessName** and **Name** properties, the command fails.</span></span>

<span data-ttu-id="9ca8a-205">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-205">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: PropertyAndMethodSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="9ca8a-206">-Process</span><span class="sxs-lookup"><span data-stu-id="9ca8a-206">-Process</span></span>

<span data-ttu-id="9ca8a-207">各入力オブジェクトに対して実行する操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-207">Specifies the operation that is performed on each input object.</span></span> <span data-ttu-id="9ca8a-208">このスクリプトブロックは、パイプライン内のすべてのオブジェクトに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-208">This script block is run for every object in the pipeline.</span></span> <span data-ttu-id="9ca8a-209">ブロックの詳細については `process` 、「 [about_Functions](about/about_functions.md#piping-objects-to-functions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-209">For more information about the `process` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

<span data-ttu-id="9ca8a-210">**Process** パラメーターに複数のスクリプトブロックを指定した場合、最初のスクリプトブロックは常にブロックにマップされ `begin` ます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-210">When you provide multiple script blocks to the **Process** parameter, the first script block is always mapped to the `begin` block.</span></span> <span data-ttu-id="9ca8a-211">スクリプトブロックが2つしかない場合は、2番目のブロックがブロックにマップされ `process` ます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-211">If there are only two script blocks, the second block is mapped to the `process` block.</span></span> <span data-ttu-id="9ca8a-212">3つ以上のスクリプトブロックがある場合、最初のスクリプトブロックは常にブロックにマップされ、最後のブロックはブロックにマップされ、 `begin` `end` between 内のブロックはすべてブロックにマップされ `process` ます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-212">If there are three or more script blocks, first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ca8a-213">-RemainingScripts</span><span class="sxs-lookup"><span data-stu-id="9ca8a-213">-RemainingScripts</span></span>

<span data-ttu-id="9ca8a-214">**Process** パラメーターによって取得されないすべてのスクリプトブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-214">Specifies all script blocks that are not taken by the **Process** parameter.</span></span>

<span data-ttu-id="9ca8a-215">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-215">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ca8a-216">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9ca8a-216">-Confirm</span></span>

<span data-ttu-id="9ca8a-217">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-217">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ca8a-218">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9ca8a-218">-WhatIf</span></span>

<span data-ttu-id="9ca8a-219">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-219">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="9ca8a-220">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-220">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ca8a-221">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9ca8a-221">CommonParameters</span></span>

<span data-ttu-id="9ca8a-222">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-222">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9ca8a-223">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-223">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9ca8a-224">入力</span><span class="sxs-lookup"><span data-stu-id="9ca8a-224">Inputs</span></span>

### <span data-ttu-id="9ca8a-225">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="9ca8a-225">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="9ca8a-226">パイプを使用して任意のオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-226">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="9ca8a-227">出力</span><span class="sxs-lookup"><span data-stu-id="9ca8a-227">Outputs</span></span>

### <span data-ttu-id="9ca8a-228">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="9ca8a-228">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="9ca8a-229">このコマンドレットは、入力によって決定されたオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-229">This cmdlet returns objects that are determined by the input.</span></span>

## <span data-ttu-id="9ca8a-230">メモ</span><span class="sxs-lookup"><span data-stu-id="9ca8a-230">Notes</span></span>

- <span data-ttu-id="9ca8a-231">`ForEach-Object`コマンドレットは **foreach** ステートメントとよく似ていますが、入力を **foreach** ステートメントにパイプすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-231">The `ForEach-Object` cmdlet works much like the **Foreach** statement, except that you cannot pipe input to a **Foreach** statement.</span></span> <span data-ttu-id="9ca8a-232">**Foreach** ステートメントの詳細については、「 [about_Foreach](./About/about_Foreach.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-232">For more information about the **Foreach** statement, see [about_Foreach](./About/about_Foreach.md).</span></span>

- <span data-ttu-id="9ca8a-233">PowerShell 4.0 以降では `Where` 、 `ForEach` コレクションで使用するためのメソッドとメソッドが追加されました。</span><span class="sxs-lookup"><span data-stu-id="9ca8a-233">Starting in PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span> <span data-ttu-id="9ca8a-234">これらの新しいメソッドの詳細については、こちらを参照してください [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="9ca8a-234">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

## <span data-ttu-id="9ca8a-235">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9ca8a-235">Related links</span></span>

[<span data-ttu-id="9ca8a-236">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="9ca8a-236">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="9ca8a-237">Where-Object</span><span class="sxs-lookup"><span data-stu-id="9ca8a-237">Where-Object</span></span>](Where-Object.md)

[<span data-ttu-id="9ca8a-238">Group-Object</span><span class="sxs-lookup"><span data-stu-id="9ca8a-238">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="9ca8a-239">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="9ca8a-239">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="9ca8a-240">New-Object</span><span class="sxs-lookup"><span data-stu-id="9ca8a-240">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="9ca8a-241">Select-Object</span><span class="sxs-lookup"><span data-stu-id="9ca8a-241">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="9ca8a-242">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="9ca8a-242">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="9ca8a-243">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="9ca8a-243">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)
