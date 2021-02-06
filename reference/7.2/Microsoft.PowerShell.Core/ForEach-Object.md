---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ForEach-Object
ms.openlocfilehash: 8a79dcf9c2af7aed0c52c361467cab23f880a893
ms.sourcegitcommit: fb9bafd041e3615b9dc9fb77c9245581b705cd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2020
ms.locfileid: "99603221"
---
# <span data-ttu-id="4cee8-102">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="4cee8-102">ForEach-Object</span></span>

## <span data-ttu-id="4cee8-103">構文</span><span class="sxs-lookup"><span data-stu-id="4cee8-103">Synopsis</span></span>
<span data-ttu-id="4cee8-104">入力オブジェクトのコレクション内の各項目に対して操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-104">Performs an operation against each item in a collection of input objects.</span></span>

## <span data-ttu-id="4cee8-105">構文</span><span class="sxs-lookup"><span data-stu-id="4cee8-105">Syntax</span></span>

### <span data-ttu-id="4cee8-106">ScriptBlockSet (既定)</span><span class="sxs-lookup"><span data-stu-id="4cee8-106">ScriptBlockSet (Default)</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-Begin <ScriptBlock>] [-Process] <ScriptBlock[]>
 [-End <ScriptBlock>] [-RemainingScripts <ScriptBlock[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4cee8-107">PropertyAndMethodSet</span><span class="sxs-lookup"><span data-stu-id="4cee8-107">PropertyAndMethodSet</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-MemberName] <String> [-ArgumentList <Object[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4cee8-108">ParallelParameterSet</span><span class="sxs-lookup"><span data-stu-id="4cee8-108">ParallelParameterSet</span></span>

```
ForEach-Object -Parallel <scriptblock> [-InputObject <PSObject>] [-ThrottleLimit <int>]
[-UseNewRunspace] [-TimeoutSeconds <int>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4cee8-109">説明</span><span class="sxs-lookup"><span data-stu-id="4cee8-109">Description</span></span>

<span data-ttu-id="4cee8-110">`ForEach-Object`コマンドレットは、入力オブジェクトのコレクション内の各項目に対して操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-110">The `ForEach-Object` cmdlet performs an operation on each item in a collection of input objects.</span></span> <span data-ttu-id="4cee8-111">入力オブジェクトは、コマンドレットにパイプすることも、 **InputObject** パラメーターを使用して指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-111">The input objects can be piped to the cmdlet or specified by using the **InputObject** parameter.</span></span>

<span data-ttu-id="4cee8-112">Windows PowerShell 3.0 以降では、コマンドを構築する方法は2つあり `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-112">Starting in Windows PowerShell 3.0, there are two different ways to construct a `ForEach-Object` command.</span></span>

- <span data-ttu-id="4cee8-113">**スクリプトブロック**。</span><span class="sxs-lookup"><span data-stu-id="4cee8-113">**Script block**.</span></span> <span data-ttu-id="4cee8-114">スクリプト ブロックを使用して、操作を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-114">You can use a script block to specify the operation.</span></span> <span data-ttu-id="4cee8-115">スクリプトブロック内で、変数を使用して `$_` 現在のオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-115">Within the script block, use the `$_` variable to represent the current object.</span></span> <span data-ttu-id="4cee8-116">スクリプト ブロックは、**Process** パラメーターの値です。</span><span class="sxs-lookup"><span data-stu-id="4cee8-116">The script block is the value of the **Process** parameter.</span></span> <span data-ttu-id="4cee8-117">スクリプトブロックには、任意の PowerShell スクリプトを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-117">The script block can contain any PowerShell script.</span></span>

  <span data-ttu-id="4cee8-118">たとえば、次のコマンドでは、コンピューター上の各プロセスの **ProcessName** プロパティの値を取得します</span><span class="sxs-lookup"><span data-stu-id="4cee8-118">For example, the following command gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object {$_.ProcessName}`

  <span data-ttu-id="4cee8-119">`ForEach-Object` 「 `begin` `process` `end` [about_functions](about/about_functions.md#piping-objects-to-functions)」で説明されているように、、、およびの各ブロックをサポートします。</span><span class="sxs-lookup"><span data-stu-id="4cee8-119">`ForEach-Object` supports the `begin`, `process`, and `end` blocks as described in [about_functions](about/about_functions.md#piping-objects-to-functions).</span></span>

  > [!NOTE]
  > <span data-ttu-id="4cee8-120">スクリプトブロックは、呼び出し元のスコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-120">The script blocks run in the caller's scope.</span></span> <span data-ttu-id="4cee8-121">したがって、ブロックはそのスコープ内の変数にアクセスでき、コマンドレットの完了後にそのスコープに保持される新しい変数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-121">Therefore the blocks have access to variables in that scope and can create new variables that persist in that scope after the cmdlet completes.</span></span>

- <span data-ttu-id="4cee8-122">**Operation ステートメント**。</span><span class="sxs-lookup"><span data-stu-id="4cee8-122">**Operation statement**.</span></span> <span data-ttu-id="4cee8-123">また、操作ステートメントを記述することもできます。これは自然言語に似ています。</span><span class="sxs-lookup"><span data-stu-id="4cee8-123">You can also write an operation statement, which is much more like natural language.</span></span> <span data-ttu-id="4cee8-124">操作のステートメントを使用してプロパティの値を指定することも、メソッドを呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-124">You can use the operation statement to specify a property value or call a method.</span></span> <span data-ttu-id="4cee8-125">操作のステートメントは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4cee8-125">Operation statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="4cee8-126">たとえば、次のコマンドでは、コンピューター上の各プロセスの **ProcessName** プロパティの値も取得します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-126">For example, the following command also gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object ProcessName`

- <span data-ttu-id="4cee8-127">**並列実行スクリプトブロック** です。</span><span class="sxs-lookup"><span data-stu-id="4cee8-127">**Parallel running script block**.</span></span> <span data-ttu-id="4cee8-128">PowerShell 7.0 以降では、3番目のパラメーターセットを使用して、各スクリプトブロックを並列に実行できます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-128">Beginning with PowerShell 7.0, a third parameter set is available that runs each script block in parallel.</span></span> <span data-ttu-id="4cee8-129">**ThrottleLimit** パラメーターは、一度に実行される並列スクリプトの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-129">The **ThrottleLimit** parameter limits the number of parallel scripts running at a time.</span></span> <span data-ttu-id="4cee8-130">前と同様に、変数を使用して、 `$_` スクリプトブロック内の現在の入力オブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-130">As before, use the `$_` variable to represent the current input object in the script block.</span></span> <span data-ttu-id="4cee8-131">`$using:`実行中のスクリプトに変数参照を渡すには、キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-131">Use the `$using:` keyword to pass variable references to the running script.</span></span>

  <span data-ttu-id="4cee8-132">PowerShell 7 では、ループの反復ごとに新しい実行空間が作成され、最大の分離が実現されます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-132">In PowerShell 7, a new runspace is created for each loop iteration to ensure maximum isolation.</span></span>
  <span data-ttu-id="4cee8-133">これは、新しい実行空間の作成と比較した場合や、大量の作業を実行するイテレーションが多数ある場合に、パフォーマンスとリソースに大きな影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4cee8-133">This can be a large performance and resource hit if the work you are doing is small compared to creating new runspaces or if there are a lot of iterations performing significant work.</span></span> <span data-ttu-id="4cee8-134">PowerShell 7.1 では、実行空間プールからの実行空間が既定で再利用されます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-134">As of PowerShell 7.1, runspaces from a runspace pool are reused by default.</span></span> <span data-ttu-id="4cee8-135">実行空間プールのサイズは、 **ThrottleLimit** パラメーターによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-135">The runspace pool size is specified by the **ThrottleLimit** parameter.</span></span> <span data-ttu-id="4cee8-136">既定の実行空間プールサイズは5です。</span><span class="sxs-lookup"><span data-stu-id="4cee8-136">The default runspace pool size is 5.</span></span> <span data-ttu-id="4cee8-137">**UseNewRunspace** スイッチを使用して、反復ごとに新しい実行空間を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-137">You can still create a new runspace for each iteration using the **UseNewRunspace** switch.</span></span>

  <span data-ttu-id="4cee8-138">既定では、parallel scriptblocks は、並列タスクを開始した呼び出し元の現在の作業ディレクトリを使用します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-138">By default, the parallel scriptblocks use the current working directory of the caller that started the parallel tasks.</span></span>

  <span data-ttu-id="4cee8-139">終了しないエラーは、並列実行される scriptblocks で発生するようにコマンドレットエラーストリームに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-139">Non-terminating errors are written to the cmdlet error stream as they occur in parallel running scriptblocks.</span></span> <span data-ttu-id="4cee8-140">並列 scriptblock の実行順序を決定できないため、エラーストリームにエラーが表示される順序はランダムになります。</span><span class="sxs-lookup"><span data-stu-id="4cee8-140">Because parallel scriptblock execution order cannot be determined, the order in which errors appear in the error stream is random.</span></span> <span data-ttu-id="4cee8-141">同様に、警告、詳細、情報など、他のデータストリームに書き込まれたメッセージは、不定の順序でこれらのデータストリームに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-141">Likewise, messages written to other data streams, like warning, verbose, or information are written to those data streams in an indeterminate order.</span></span>

  <span data-ttu-id="4cee8-142">例外などの終了エラーは、発生した scriptblocks の個々の並列インスタンスを終了します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-142">Terminating errors, such as exceptions, terminate the individual parallel instance of the scriptblocks in which they occur.</span></span> <span data-ttu-id="4cee8-143">1つの scriptblocks で終了エラーが発生しても、コマンドレットが終了しないことがあり `Foreach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-143">A terminating error in one scriptblocks may not cause the termination of the `Foreach-Object` cmdlet.</span></span> <span data-ttu-id="4cee8-144">並列で実行されている他の scriptblocks は、終了エラーも発生しない限り実行を継続します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-144">The other scriptblocks, running in parallel, continue to run unless they also encounter a terminating error.</span></span> <span data-ttu-id="4cee8-145">終了エラーは、の **FullyQualifiedErrorId** を持つ **errorrecord** としてエラーデータストリームに書き込まれ `PSTaskException` ます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-145">The terminating error is written to the error data stream as an **ErrorRecord** with a **FullyQualifiedErrorId** of `PSTaskException`.</span></span>
  <span data-ttu-id="4cee8-146">終了エラーは、PowerShell の try/catch ブロックまたはトラップブロックを使用して、終了しないエラーに変換できます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-146">Terminating errors can be converted to non-terminating errors using PowerShell try/catch or trap blocks.</span></span>

## <span data-ttu-id="4cee8-147">例</span><span class="sxs-lookup"><span data-stu-id="4cee8-147">Examples</span></span>

### <span data-ttu-id="4cee8-148">例 1: 配列の整数を除算する</span><span class="sxs-lookup"><span data-stu-id="4cee8-148">Example 1: Divide integers in an array</span></span>

<span data-ttu-id="4cee8-149">この例では、3つの整数の配列を受け取り、それぞれを1024で除算します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-149">This example takes an array of three integers and divides each one of them by 1024.</span></span>

```powershell
30000, 56798, 12432 | ForEach-Object -Process {$_/1024}
```

```Output
29.296875
55.466796875
12.140625
```

### <span data-ttu-id="4cee8-150">例 2: ディレクトリ内のすべてのファイルの長さを取得する</span><span class="sxs-lookup"><span data-stu-id="4cee8-150">Example 2: Get the length of all the files in a directory</span></span>

<span data-ttu-id="4cee8-151">この例では、PowerShell インストールディレクトリ内のファイルとディレクトリを処理し `$PSHOME` ます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-151">This example processes the files and directories in the PowerShell installation directory `$PSHOME`.</span></span>

```powershell
Get-ChildItem $PSHOME |
  ForEach-Object -Process {if (!$_.PSIsContainer) {$_.Name; $_.Length / 1024; " " }}
```

<span data-ttu-id="4cee8-152">オブジェクトがディレクトリではない場合、スクリプトブロックはファイルの名前を取得し、その **長さ** のプロパティの値を1024で割り、次のエントリと区別するためにスペース ("") を追加します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-152">If the object is not a directory, the script block gets the name of the file, divides the value of its **Length** property by 1024, and adds a space (" ") to separate it from the next entry.</span></span> <span data-ttu-id="4cee8-153">コマンドレットでは、 **PSISContainer** プロパティを使用して、オブジェクトがディレクトリであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-153">The cmdlet uses the **PSISContainer** property to determine whether an object is a directory.</span></span>

### <span data-ttu-id="4cee8-154">例 3: 最新のシステムイベントを操作する</span><span class="sxs-lookup"><span data-stu-id="4cee8-154">Example 3: Operate on the most recent System events</span></span>

<span data-ttu-id="4cee8-155">この例では、システムイベントログから1000の最新のイベントをテキストファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-155">This example writes the 1000 most recent events from the System event log to a text file.</span></span> <span data-ttu-id="4cee8-156">イベントの処理の前後に、現在の時刻が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-156">The current time is displayed before and after processing the events.</span></span>

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$events | ForEach-Object -Begin {Get-Date} -Process {Out-File -FilePath Events.txt -Append -InputObject $_.Message} -End {Get-Date}
```

<span data-ttu-id="4cee8-157">`Get-EventLog` システムイベントログから1000の最新のイベントを取得し、変数に格納し `$Events` ます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-157">`Get-EventLog` gets the 1000 most recent events from the System event log and stores them in the `$Events` variable.</span></span> <span data-ttu-id="4cee8-158">`$Events` 次に、をコマンドレットにパイプ処理し `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-158">`$Events` is then piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="4cee8-159">**Begin** パラメーターは、現在の日付と時刻を示します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-159">The **Begin** parameter displays the current date and time.</span></span> <span data-ttu-id="4cee8-160">次に、 **Process** パラメーターは、コマンドレットを使用して `Out-File` events.txt という名前のテキストファイルを作成し、そのファイル内の各イベントの message プロパティを格納します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-160">Next, the **Process** parameter uses the `Out-File` cmdlet to create a text file that is named events.txt and stores the message property of each of the events in that file.</span></span> <span data-ttu-id="4cee8-161">最後に、**End** パラメーターは、すべての処理が完了した後の日付と時刻を示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-161">Last, the **End** parameter is used to display the date and time after all of the processing has completed.</span></span>

### <span data-ttu-id="4cee8-162">例 4: レジストリキーの値を変更する</span><span class="sxs-lookup"><span data-stu-id="4cee8-162">Example 4: Change the value of a Registry key</span></span>

<span data-ttu-id="4cee8-163">この例では、キーの下にあるすべてのサブキーの **RemotePath** レジストリエントリの値 `HKCU:\Network` を大文字に変更します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-163">This example changes the value of the **RemotePath** registry entry in all of the subkeys under the `HKCU:\Network` key to uppercase text.</span></span>

```powershell
Get-ItemProperty -Path HKCU:\Network\* |
  ForEach-Object {Set-ItemProperty -Path $_.PSPath -Name RemotePath -Value $_.RemotePath.ToUpper();}
```

<span data-ttu-id="4cee8-164">このフォーマットを使用して、レジストリ エントリ値の形式や内容を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-164">You can use this format to change the form or content of a registry entry value.</span></span>

<span data-ttu-id="4cee8-165">**ネットワーク** キーの各サブキーは、サインオン時に再接続する、マップされたネットワークドライブを表します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-165">Each subkey in the **Network** key represents a mapped network drive that reconnects at sign on.</span></span> <span data-ttu-id="4cee8-166">**RemotePath** エントリには、接続されているドライブの UNC パスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-166">The **RemotePath** entry contains the UNC path of the connected drive.</span></span> <span data-ttu-id="4cee8-167">たとえば、E: ドライブをにマップすると、 `\\Server\Share` で RemotePath レジストリ値がに設定された **e** サブキーが作成され `HKCU:\Network`  `\\Server\Share` ます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-167">For example, if you map the E: drive to `\\Server\Share`, an **E** subkey is created in `HKCU:\Network` with the **RemotePath** registry value set to `\\Server\Share`.</span></span>

<span data-ttu-id="4cee8-168">このコマンドは、コマンドレットを使用して `Get-ItemProperty` **ネットワーク** キーのすべてのサブキーを取得し、コマンドレットを使用して `Set-ItemProperty` 各キーの **RemotePath** レジストリエントリの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-168">The command uses the `Get-ItemProperty` cmdlet to get all of the subkeys of the **Network** key and the `Set-ItemProperty` cmdlet to change the value of the **RemotePath** registry entry in each key.</span></span>
<span data-ttu-id="4cee8-169">コマンドの `Set-ItemProperty` パスは、レジストリキーの **pspath** プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="4cee8-169">In the `Set-ItemProperty` command, the path is the value of the **PSPath** property of the registry key.</span></span> <span data-ttu-id="4cee8-170">これは、レジストリエントリではなく、レジストリキーを表す Microsoft .NET Framework オブジェクトのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="4cee8-170">This is a property of the Microsoft .NET Framework object that represents the registry key, not a registry entry.</span></span> <span data-ttu-id="4cee8-171">このコマンドでは、 **RemotePath** 値の **ToUpper ()** メソッドを使用します。これは文字列 (REG_SZ) です。</span><span class="sxs-lookup"><span data-stu-id="4cee8-171">The command uses the **ToUpper()** method of the **RemotePath** value, which is a string (REG_SZ).</span></span>

<span data-ttu-id="4cee8-172">`Set-ItemProperty`は各キーのプロパティを変更するため、 `ForEach-Object` プロパティにアクセスするにはコマンドレットが必要です。</span><span class="sxs-lookup"><span data-stu-id="4cee8-172">Because `Set-ItemProperty` is changing the property of each key, the `ForEach-Object` cmdlet is required to access the property.</span></span>

### <span data-ttu-id="4cee8-173">例 5: $Null 自動変数を使用する</span><span class="sxs-lookup"><span data-stu-id="4cee8-173">Example 5: Use the $Null automatic variable</span></span>

<span data-ttu-id="4cee8-174">この例は、 `$Null` 自動変数をコマンドレットにパイプした場合の効果を示して `ForEach-Object` います。</span><span class="sxs-lookup"><span data-stu-id="4cee8-174">This example shows the effect of piping the `$Null` automatic variable to the `ForEach-Object` cmdlet.</span></span>

```powershell
1, 2, $null, 4 | ForEach-Object {"Hello"}
```

```Output
Hello
Hello
Hello
Hello
```

<span data-ttu-id="4cee8-175">PowerShell では null が明示的なプレースホルダーとして扱われるため、 `ForEach-Object` このコマンドレットは `$Null` 、パイプを使用する他のオブジェクトと同様に、の値を生成します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-175">Because PowerShell treats null as an explicit placeholder, the `ForEach-Object` cmdlet generates a value for `$Null`, just as it does for other objects that you pipe to it.</span></span>

### <span data-ttu-id="4cee8-176">例 6: プロパティ値を取得する</span><span class="sxs-lookup"><span data-stu-id="4cee8-176">Example 6: Get property values</span></span>

<span data-ttu-id="4cee8-177">この例では、コマンドレットの **MemberName** パラメーターを使用して、インストールされているすべての PowerShell モジュールの **Path** プロパティの値を取得し `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-177">This example gets the value of the **Path** property of all installed PowerShell modules by using the **MemberName** parameter of the `ForEach-Object` cmdlet.</span></span>

```powershell
Get-Module -ListAvailable | ForEach-Object -MemberName Path
Get-Module -ListAvailable | Foreach Path
```

<span data-ttu-id="4cee8-178">2 番目のコマンドは、1 番目のコマンドと同等です。</span><span class="sxs-lookup"><span data-stu-id="4cee8-178">The second command is equivalent to the first.</span></span> <span data-ttu-id="4cee8-179">`Foreach`コマンドレットのエイリアスを使用 `ForEach-Object` し、 **MemberName** パラメーターの名前を省略します。これは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="4cee8-179">It uses the `Foreach` alias of the `ForEach-Object` cmdlet and omits the name of the **MemberName** parameter, which is optional.</span></span>

<span data-ttu-id="4cee8-180">コマンドレットは、プロパティ値の `ForEach-Object` 型を変更する **Format** コマンドレットやコマンドレットとは異なり、型を変更せずに値を取得するため、プロパティ値を取得する場合に便利です `Select-Object` 。</span><span class="sxs-lookup"><span data-stu-id="4cee8-180">The `ForEach-Object` cmdlet is useful for getting property values, because it gets the value without changing the type, unlike the **Format** cmdlets or the `Select-Object` cmdlet, which change the property value type.</span></span>

### <span data-ttu-id="4cee8-181">例 7: モジュール名をコンポーネント名に分割する</span><span class="sxs-lookup"><span data-stu-id="4cee8-181">Example 7: Split module names into component names</span></span>

<span data-ttu-id="4cee8-182">この例では、2つのドットで区切られたモジュール名をコンポーネント名に分割する3つの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-182">This example shows three ways to split two dot-separated module names into their component names.</span></span>

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

<span data-ttu-id="4cee8-183">このコマンドは、文字列の **Split** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-183">The commands call the **Split** method of strings.</span></span> <span data-ttu-id="4cee8-184">3 つのコマンドは、別の構文を使用しますが、すべて同等であり、交換可能です。</span><span class="sxs-lookup"><span data-stu-id="4cee8-184">The three commands use different syntax, but they are equivalent and interchangeable.</span></span>

<span data-ttu-id="4cee8-185">最初のコマンドは、スクリプトブロックと現在のオブジェクト演算子を含む従来の構文を使用し `$_` ます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-185">The first command uses the traditional syntax, which includes a script block and the current object operator `$_`.</span></span> <span data-ttu-id="4cee8-186">メソッドの指定にドット構文を使用し、区切り記号の引数を囲むためにかっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-186">It uses the dot syntax to specify the method and parentheses to enclose the delimiter argument.</span></span>

<span data-ttu-id="4cee8-187">2 番目のコマンドは、**MemberName** パラメーターを使用して **Split** メソッドを指定し、**ArgumentName** パラメーターを使用してドット (".") を分割の区切り記号として識別します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-187">The second command uses the **MemberName** parameter to specify the **Split** method and the **ArgumentName** parameter to identify the dot (".") as the split delimiter.</span></span>

<span data-ttu-id="4cee8-188">3番目のコマンドは、コマンドレットの **Foreach** エイリアスを使用 `ForEach-Object` して、 **MemberName** および **ArgumentList** パラメーターの名前を省略します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="4cee8-188">The third command uses the **Foreach** alias of the `ForEach-Object` cmdlet and omits the names of the **MemberName** and **ArgumentList** parameters, which are optional.</span></span>

### <span data-ttu-id="4cee8-189">例 8: 2 つのスクリプトブロックと共に ForEach-Object を使用する</span><span class="sxs-lookup"><span data-stu-id="4cee8-189">Example 8: Using ForEach-Object with two script blocks</span></span>

<span data-ttu-id="4cee8-190">この例では、2つのスクリプトブロック位置を渡します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-190">In this example, we pass two script blocks positionally.</span></span> <span data-ttu-id="4cee8-191">すべてのスクリプトブロックが **Process** パラメーターにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-191">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="4cee8-192">ただし、これらは **Begin** および **Process** パラメーターに渡されたものとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-192">However, they are treated as if they had been passed to the **Begin** and **Process** parameters.</span></span>

```powershell
1..2 | ForEach-Object { 'begin' } { 'process' }
```

```Output
begin
process
process
```

### <span data-ttu-id="4cee8-193">例 9: 3 つ以上のスクリプトブロックと共に ForEach-Object を使用する</span><span class="sxs-lookup"><span data-stu-id="4cee8-193">Example 9: Using ForEach-Object with more than two script blocks</span></span>

<span data-ttu-id="4cee8-194">この例では、2つのスクリプトブロック位置を渡します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-194">In this example, we pass two script blocks positionally.</span></span> <span data-ttu-id="4cee8-195">すべてのスクリプトブロックが **Process** パラメーターにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-195">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="4cee8-196">ただし、これらは **Begin**、 **Process**、および **End** パラメーターに渡されたものとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-196">However, they are treated as if they had been passed to the **Begin**, **Process**, and **End** parameters.</span></span>

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
> <span data-ttu-id="4cee8-197">最初のスクリプトブロックは常にブロックにマップされ、最後のブロックはブロックにマップされ、 `begin` `end` between 内のブロックはすべてブロックにマップされ `process` ます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-197">The first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

### <span data-ttu-id="4cee8-198">例 10: パイプライン項目ごとに複数のスクリプトブロックを実行する</span><span class="sxs-lookup"><span data-stu-id="4cee8-198">Example 10: Run multiple script blocks for each pipeline item</span></span>

<span data-ttu-id="4cee8-199">前の例で示したように、 **Process** パラメーターを使用して渡された複数のスクリプトブロックは、 **Begin** および **End** パラメーターにマップされます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-199">As shown in the previous example, multiple script blocks passed using the **Process** parameter get mapped to the **Begin** and **End** parameters.</span></span> <span data-ttu-id="4cee8-200">このマッピングを回避するには、 **Begin** および **End** パラメーターに明示的な値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cee8-200">To avoid this mapping, you must provide explicit values for the **Begin** and **End** parameters.</span></span>

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

### <span data-ttu-id="4cee8-201">例 11: 並列バッチで低速スクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="4cee8-201">Example 11: Run slow script in parallel batches</span></span>

<span data-ttu-id="4cee8-202">この例では、文字列を評価し、1秒間スリープする単純なスクリプトブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-202">This example runs a simple script block that evaluates a string and sleeps for one second.</span></span>

```powershell
$Message = "Output:"

1..8 | ForEach-Object -Parallel {
    "$using:Message $_"
    Start-Sleep 1
} -ThrottleLimit 4
```

```Output
Output: 1
Output: 2
Output: 3
Output: 4
Output: 5
Output: 6
Output: 7
Output: 8
```

<span data-ttu-id="4cee8-203">入力が4つのバッチで処理されるように、 **ThrottleLimit** パラメーターの値は4に設定されています。</span><span class="sxs-lookup"><span data-stu-id="4cee8-203">The **ThrottleLimit** parameter value is set to 4 so that the input is processed in batches of four.</span></span>
<span data-ttu-id="4cee8-204">キーワードは、 `$using:` `$Message` 各並列スクリプトブロックに変数を渡すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-204">The `$using:` keyword is used to pass the `$Message` variable into each parallel script block.</span></span>

### <span data-ttu-id="4cee8-205">例 12: ログエントリを並列で取得する</span><span class="sxs-lookup"><span data-stu-id="4cee8-205">Example 12: Retrieve log entries in parallel</span></span>

<span data-ttu-id="4cee8-206">この例では、ローカル Windows コンピューター上の5つのシステムログから5万のログエントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-206">This example retrieves 50,000 log entries from 5 system logs on a local Windows machine.</span></span>

```powershell
$logNames = 'Security','Application','System','Windows PowerShell','Microsoft-Windows-Store/Operational'

$logEntries = $logNames | ForEach-Object -Parallel {
    Get-WinEvent -LogName $_ -MaxEvents 10000
} -ThrottleLimit 5

$logEntries.Count
```

```Output
50000
```

<span data-ttu-id="4cee8-207">**Parallel** パラメーターは、入力ログ名ごとに並列実行されるスクリプト ブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-207">The **Parallel** parameter specifies the script block that is run in parallel for each input log name.</span></span> <span data-ttu-id="4cee8-208">**ThrottleLimit** パラメーターを指定すると、5つのすべてのスクリプトブロックが同時に実行されるようになります。</span><span class="sxs-lookup"><span data-stu-id="4cee8-208">The **ThrottleLimit** parameter ensures that all five script blocks run at the same time.</span></span>

### <span data-ttu-id="4cee8-209">例 13: ジョブとして並列に実行する</span><span class="sxs-lookup"><span data-stu-id="4cee8-209">Example 13: Run in parallel as a job</span></span>

<span data-ttu-id="4cee8-210">この例では、単純なスクリプトブロックを並列に実行し、同時に2つのバックグラウンドジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-210">This example runs a simple script block in parallel, creating two background jobs at a time.</span></span>

```powershell
$job = 1..10 | ForEach-Object -Parallel {
    "Output: $_"
    Start-Sleep 1
} -ThrottleLimit 2 -AsJob

$job | Receive-Job -Wait
```

```Output
Output: 1
Output: 2
Output: 3
Output: 4
Output: 5
Output: 6
Output: 7
Output: 8
Output: 9
Output: 10
```

<span data-ttu-id="4cee8-211">変数は、 `$job` 出力データを収集し、実行状態を監視するジョブオブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4cee8-211">the `$job` variable receives the job object that collects output data and monitors running state.</span></span>
<span data-ttu-id="4cee8-212">ジョブオブジェクトは、待機スイッチパラメーターを使用してにパイプ処理され `Receive-Job` ます。 </span><span class="sxs-lookup"><span data-stu-id="4cee8-212">The job object is piped to `Receive-Job` with the **Wait** switch parameter.</span></span> <span data-ttu-id="4cee8-213">このストリームは、が AsJob なしで実行された場合と同様に、コンソールに出力 `ForEach-Object -Parallel` されます。 </span><span class="sxs-lookup"><span data-stu-id="4cee8-213">And this streams output to the console, just as if `ForEach-Object -Parallel` was run without **AsJob**.</span></span>

### <span data-ttu-id="4cee8-214">例 14: スレッドセーフな変数参照を使用する</span><span class="sxs-lookup"><span data-stu-id="4cee8-214">Example 14: Using thread safe variable references</span></span>

<span data-ttu-id="4cee8-215">この例では、スクリプトブロックを並行して呼び出して、一意の名前を付けたプロセスオブジェクトを収集します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-215">This example invokes script blocks in parallel to collect uniquely named Process objects.</span></span>

```powershell
$threadSafeDictionary = [System.Collections.Concurrent.ConcurrentDictionary[string,object]]::new()
Get-Process | ForEach-Object -Parallel {
    $dict = $using:threadSafeDictionary
    $dict.TryAdd($_.ProcessName, $_)
}

$threadSafeDictionary["pwsh"]
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     82    82.87     130.85      15.55    2808   2 pwsh
```

<span data-ttu-id="4cee8-216">オブジェクトを収集するために、 **ConcurrentDictionary** オブジェクトの1つのインスタンスが各スクリプトブロックに渡されます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-216">A single instance of a **ConcurrentDictionary** object is passed to each script block to collect the objects.</span></span> <span data-ttu-id="4cee8-217">**ConcurrentDictionary** はスレッドセーフであるため、各並列スクリプトによって安全に変更できます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-217">Since the **ConcurrentDictionary** is thread safe, it is safe to be modified by each parallel script.</span></span> <span data-ttu-id="4cee8-218">スレッドセーフでないオブジェクト ( **system.string など)** は、ここでは安全に使用できません。</span><span class="sxs-lookup"><span data-stu-id="4cee8-218">A non-thread-safe object, such as **System.Collections.Generic.Dictionary**, would not be safe to use here.</span></span>

> [!NOTE]
> <span data-ttu-id="4cee8-219">この例は、 **並列** パラメーターの非常に非効率的な使用方法です。</span><span class="sxs-lookup"><span data-stu-id="4cee8-219">This example is a very inefficient use of **Parallel** parameter.</span></span> <span data-ttu-id="4cee8-220">このスクリプトは、単純に入力オブジェクトを同時辞書オブジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-220">The script simply adds the input object to a concurrent dictionary object.</span></span> <span data-ttu-id="4cee8-221">これは簡単で、各スクリプトを個別のスレッドで呼び出すオーバーヘッドにはなりません。</span><span class="sxs-lookup"><span data-stu-id="4cee8-221">It is trivial and not worth the overhead of invoking each script in a separate thread.</span></span> <span data-ttu-id="4cee8-222">`ForEach-Object`**並列** スイッチを使用せずに通常どおりに実行すると、より効率的で高速になります。</span><span class="sxs-lookup"><span data-stu-id="4cee8-222">Running `ForEach-Object` normally without the **Parallel** switch is much more efficient and faster.</span></span> <span data-ttu-id="4cee8-223">この例は、スレッドセーフな変数の使用方法を示すことのみを目的としています。</span><span class="sxs-lookup"><span data-stu-id="4cee8-223">This example is only intended to demonstrate how to use thread safe variables.</span></span>

### <span data-ttu-id="4cee8-224">例 15: 並列実行によるエラーの書き込み</span><span class="sxs-lookup"><span data-stu-id="4cee8-224">Example 15: Writing errors with parallel execution</span></span>

<span data-ttu-id="4cee8-225">この例では、エラーストリームへの書き込みを並行して行います。書き込まれたエラーの順序はランダムになります。</span><span class="sxs-lookup"><span data-stu-id="4cee8-225">This example writes to the error stream in parallel, where the order of written errors is random.</span></span>

```powershell
1..3 | ForEach-Object -Parallel {
    Write-Error "Error: $_"
}
```

```Output
Write-Error: Error: 1
Write-Error: Error: 3
Write-Error: Error: 2
```

### <span data-ttu-id="4cee8-226">例 16: 並列実行のエラーを終了する</span><span class="sxs-lookup"><span data-stu-id="4cee8-226">Example 16: Terminating errors in parallel execution</span></span>

<span data-ttu-id="4cee8-227">この例では、1つの並列実行 scriptblock での終了エラーを示します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-227">This example demonstrates a terminating error in one parallel running scriptblock.</span></span>

```powershell
1..5 | ForEach-Object -Parallel {
    if ($_ -eq 3)
    {
        throw "Terminating Error: $_"
    }

    Write-Output "Output: $_"
}
```

```Output
Exception: Terminating Error: 3
Output: 1
Output: 4
Output: 2
Output: 5
```

<span data-ttu-id="4cee8-228">`Output: 3` は、その反復処理の並列 scriptblock が終了したため、書き込まれませんでした。</span><span class="sxs-lookup"><span data-stu-id="4cee8-228">`Output: 3` is never written because the parallel scriptblock for that iteration was terminated.</span></span>

## <span data-ttu-id="4cee8-229">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4cee8-229">Parameters</span></span>

### <span data-ttu-id="4cee8-230">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="4cee8-230">-ArgumentList</span></span>

<span data-ttu-id="4cee8-231">メソッド呼び出しの引数の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-231">Specifies an array of arguments to a method call.</span></span> <span data-ttu-id="4cee8-232">**ArgumentList** の動作の詳細については、「 [about_Splatting](about/about_Splatting.md#splatting-with-arrays)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cee8-232">For more information about the behavior of **ArgumentList**, see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="4cee8-233">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4cee8-233">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="4cee8-234">-開始</span><span class="sxs-lookup"><span data-stu-id="4cee8-234">-Begin</span></span>

<span data-ttu-id="4cee8-235">このコマンドレットが入力オブジェクトを処理する前に実行されるスクリプトブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-235">Specifies a script block that runs before this cmdlet processes any input objects.</span></span> <span data-ttu-id="4cee8-236">このスクリプトブロックは、パイプライン全体に対して1回だけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-236">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="4cee8-237">ブロックの詳細については `begin` 、「 [about_Functions](about/about_functions.md#piping-objects-to-functions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cee8-237">For more information about the `begin` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

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

### <span data-ttu-id="4cee8-238">-End</span><span class="sxs-lookup"><span data-stu-id="4cee8-238">-End</span></span>

<span data-ttu-id="4cee8-239">このコマンドレットによってすべての入力オブジェクトが処理された後に実行されるスクリプトブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-239">Specifies a script block that runs after this cmdlet processes all input objects.</span></span> <span data-ttu-id="4cee8-240">このスクリプトブロックは、パイプライン全体に対して1回だけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-240">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="4cee8-241">ブロックの詳細については `end` 、「 [about_Functions](about/about_functions.md#piping-objects-to-functions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cee8-241">For more information about the `end` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

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

### <span data-ttu-id="4cee8-242">-InputObject</span><span class="sxs-lookup"><span data-stu-id="4cee8-242">-InputObject</span></span>

<span data-ttu-id="4cee8-243">入力オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-243">Specifies the input objects.</span></span> <span data-ttu-id="4cee8-244">`ForEach-Object` 各入力オブジェクトに対して、スクリプトブロックまたは操作ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-244">`ForEach-Object` runs the script block or operation statement on each input object.</span></span> <span data-ttu-id="4cee8-245">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-245">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="4cee8-246">で **inputobject** パラメーターを使用すると、 `ForEach-Object` コマンドの結果をにパイプするのではなく、 `ForEach-Object` **inputobject** 値が1つのオブジェクトとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-246">When you use the **InputObject** parameter with `ForEach-Object`, instead of piping command results to `ForEach-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="4cee8-247">これは、値が、などのコマンドの結果であるコレクションである場合にも当てはまり `-InputObject (Get-Process)` ます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-247">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span>
<span data-ttu-id="4cee8-248">**InputObject** は配列またはオブジェクトのコレクションから個々のプロパティを返すことができないため、を使用し `ForEach-Object` て、定義されたプロパティに特定の値を持つオブジェクトのオブジェクトのコレクションに対して操作を実行する場合は、 `ForEach-Object` このトピックの例に示すように、パイプラインでを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4cee8-248">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that if you use `ForEach-Object` to perform operations on a collection of objects for those objects that have specific values in defined properties, you use `ForEach-Object` in the pipeline, as shown in the examples in this topic.</span></span>

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

### <span data-ttu-id="4cee8-249">-MemberName</span><span class="sxs-lookup"><span data-stu-id="4cee8-249">-MemberName</span></span>

<span data-ttu-id="4cee8-250">取得するプロパティまたは呼び出すメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-250">Specifies the property to get or the method to call.</span></span>

<span data-ttu-id="4cee8-251">ワイルドカード文字は使用できますが、結果の文字列が一意の値に解決される場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-251">Wildcard characters are permitted, but work only if the resulting string resolves to a unique value.</span></span>
<span data-ttu-id="4cee8-252">たとえば、を実行すると、 `Get-Process | ForEach -MemberName *Name` ワイルドカードパターンは、コマンドが失敗する原因となる複数のメンバーと一致します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-252">For example, if you run `Get-Process | ForEach -MemberName *Name`, the wildcard pattern matches more than one member causing the command to fail.</span></span>

<span data-ttu-id="4cee8-253">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4cee8-253">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="4cee8-254">-Process</span><span class="sxs-lookup"><span data-stu-id="4cee8-254">-Process</span></span>

<span data-ttu-id="4cee8-255">各入力オブジェクトに対して実行する操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-255">Specifies the operation that is performed on each input object.</span></span> <span data-ttu-id="4cee8-256">このスクリプトブロックは、パイプライン内のすべてのオブジェクトに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-256">This script block is run for every object in the pipeline.</span></span> <span data-ttu-id="4cee8-257">ブロックの詳細については `process` 、「 [about_Functions](about/about_functions.md#piping-objects-to-functions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cee8-257">For more information about the `process` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

<span data-ttu-id="4cee8-258">**Process** パラメーターに複数のスクリプトブロックを指定した場合、最初のスクリプトブロックは常にブロックにマップされ `begin` ます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-258">When you provide multiple script blocks to the **Process** parameter, the first script block is always mapped to the `begin` block.</span></span> <span data-ttu-id="4cee8-259">スクリプトブロックが2つしかない場合は、2番目のブロックがブロックにマップされ `process` ます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-259">If there are only two script blocks, the second block is mapped to the `process` block.</span></span> <span data-ttu-id="4cee8-260">3つ以上のスクリプトブロックがある場合、最初のスクリプトブロックは常にブロックにマップされ、最後のブロックはブロックにマップされ、 `begin` `end` between 内のブロックはすべてブロックにマップされ `process` ます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-260">If there are three or more script blocks, first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

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

### <span data-ttu-id="4cee8-261">-RemainingScripts</span><span class="sxs-lookup"><span data-stu-id="4cee8-261">-RemainingScripts</span></span>

<span data-ttu-id="4cee8-262">**Process** パラメーターによって取得されないすべてのスクリプトブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-262">Specifies all script blocks that are not taken by the **Process** parameter.</span></span>

<span data-ttu-id="4cee8-263">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4cee8-263">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="4cee8-264">-Parallel</span><span class="sxs-lookup"><span data-stu-id="4cee8-264">-Parallel</span></span>

<span data-ttu-id="4cee8-265">入力オブジェクトの並列処理に使用するスクリプトブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-265">Specifies the script block to be used for parallel processing of input objects.</span></span> <span data-ttu-id="4cee8-266">操作を記述するスクリプト ブロックを入力します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-266">Enter a script block that describes the operation.</span></span>

<span data-ttu-id="4cee8-267">このパラメーターは、PowerShell 7.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4cee8-267">This parameter was introduced in PowerShell 7.0.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ParallelParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cee8-268">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="4cee8-268">-ThrottleLimit</span></span>

<span data-ttu-id="4cee8-269">並列でスクリプトブロックの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-269">Specifies the number of script blocks that in parallel.</span></span> <span data-ttu-id="4cee8-270">入力オブジェクトは、実行中のスクリプトブロックカウントが **ThrottleLimit** を下回るまでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-270">Input objects are blocked until the running script block count falls below the **ThrottleLimit**.</span></span> <span data-ttu-id="4cee8-271">既定値は `5` です。</span><span class="sxs-lookup"><span data-stu-id="4cee8-271">The default value is `5`.</span></span>

<span data-ttu-id="4cee8-272">このパラメーターは、PowerShell 7.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4cee8-272">This parameter was introduced in PowerShell 7.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cee8-273">-TimeoutSeconds</span><span class="sxs-lookup"><span data-stu-id="4cee8-273">-TimeoutSeconds</span></span>

<span data-ttu-id="4cee8-274">すべての入力が並行して処理されるまで待機する秒数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-274">Specifies the number of seconds to wait for all input to be processed in parallel.</span></span> <span data-ttu-id="4cee8-275">指定されたタイムアウト時間が経過すると、実行中のすべてのスクリプトが停止します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-275">After the specified timeout time, all running scripts are stopped.</span></span> <span data-ttu-id="4cee8-276">また、処理するその他の入力オブジェクトは無視されます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-276">And any remaining input objects to be processed are ignored.</span></span> <span data-ttu-id="4cee8-277">の既定値 `0` はタイムアウトを無効にし、 `ForEach-Object -Parallel` 無期限に実行できます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-277">Default value of `0` disables the timeout, and `ForEach-Object -Parallel` can run indefinitely.</span></span> <span data-ttu-id="4cee8-278"><kbd></kbd> + コマンドラインで Ctrl<kbd>C</kbd>キーを押すと、実行中のコマンドが停止 `ForEach-Object -Parallel` します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-278">Typing <kbd>Ctrl</kbd>+<kbd>C</kbd> at the command line stops a running `ForEach-Object -Parallel` command.</span></span> <span data-ttu-id="4cee8-279">このパラメーターは、 **AsJob** パラメーターと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4cee8-279">This parameter cannot be used along with the **AsJob** parameter.</span></span>

<span data-ttu-id="4cee8-280">このパラメーターは、PowerShell 7.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4cee8-280">This parameter was introduced in PowerShell 7.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cee8-281">-UseNewRunspace</span><span class="sxs-lookup"><span data-stu-id="4cee8-281">-UseNewRunspace</span></span>

<span data-ttu-id="4cee8-282">実行空間プールから実行空間を再利用するのではなく、並列呼び出しによって、ループの反復ごとに新しい実行空間が作成されます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-282">Causes the parallel invocation to create a new runspace for every loop iteration instead of reusing runspaces from the runspace pool.</span></span>

<span data-ttu-id="4cee8-283">このパラメーターは、PowerShell 7.1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4cee8-283">This parameter was introduced in PowerShell 7.1</span></span>

```yml
Type: SwitchParameter
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cee8-284">-AsJob</span><span class="sxs-lookup"><span data-stu-id="4cee8-284">-AsJob</span></span>

<span data-ttu-id="4cee8-285">並列呼び出しを PowerShell ジョブとして実行します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-285">Causes the parallel invocation to run as a PowerShell job.</span></span> <span data-ttu-id="4cee8-286">実行中のスクリプトブロックからの出力ではなく、1つのジョブオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-286">A single job object is returned instead of output from the running script blocks.</span></span> <span data-ttu-id="4cee8-287">ジョブオブジェクトには、実行される各並列スクリプトブロックの子ジョブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4cee8-287">The job object contains child jobs for each parallel script block that runs.</span></span> <span data-ttu-id="4cee8-288">ジョブオブジェクトは、実行状態を監視してデータを取得するために、すべての PowerShell ジョブコマンドレットで使用できます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-288">The job object can be used by all PowerShell job cmdlets, to monitor running state and retrieve data.</span></span>

<span data-ttu-id="4cee8-289">このパラメーターは、PowerShell 7.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4cee8-289">This parameter was introduced in PowerShell 7.0.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cee8-290">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4cee8-290">-Confirm</span></span>

<span data-ttu-id="4cee8-291">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-291">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cee8-292">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4cee8-292">-WhatIf</span></span>

<span data-ttu-id="4cee8-293">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-293">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="4cee8-294">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="4cee8-294">The cmdlet is not run.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cee8-295">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4cee8-295">CommonParameters</span></span>

<span data-ttu-id="4cee8-296">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="4cee8-296">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4cee8-297">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cee8-297">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4cee8-298">入力</span><span class="sxs-lookup"><span data-stu-id="4cee8-298">Inputs</span></span>

### <span data-ttu-id="4cee8-299">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="4cee8-299">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="4cee8-300">パイプを使用して任意のオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-300">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="4cee8-301">出力</span><span class="sxs-lookup"><span data-stu-id="4cee8-301">Outputs</span></span>

### <span data-ttu-id="4cee8-302">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="4cee8-302">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="4cee8-303">このコマンドレットは、入力によって決定されたオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-303">This cmdlet returns objects that are determined by the input.</span></span>

## <span data-ttu-id="4cee8-304">メモ</span><span class="sxs-lookup"><span data-stu-id="4cee8-304">Notes</span></span>

- <span data-ttu-id="4cee8-305">`ForEach-Object`コマンドレットは **foreach** ステートメントとよく似ていますが、入力を **foreach** ステートメントにパイプすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4cee8-305">The `ForEach-Object` cmdlet works much like the **Foreach** statement, except that you cannot pipe input to a **Foreach** statement.</span></span> <span data-ttu-id="4cee8-306">**Foreach** ステートメントの詳細については、「 [about_Foreach](./About/about_Foreach.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cee8-306">For more information about the **Foreach** statement, see [about_Foreach](./About/about_Foreach.md).</span></span>

- <span data-ttu-id="4cee8-307">PowerShell 4.0 以降では `Where` 、 `ForEach` コレクションで使用するためのメソッドとメソッドが追加されました。</span><span class="sxs-lookup"><span data-stu-id="4cee8-307">Starting in PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span> <span data-ttu-id="4cee8-308">これらの新しいメソッドの詳細については、こちらを参照してください [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="4cee8-308">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

- <span data-ttu-id="4cee8-309">`ForEach-Object -Parallel`パラメーターセットは、PowerShell の内部 API を使用して各スクリプトブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-309">The `ForEach-Object -Parallel` parameter set uses PowerShell's internal API to run each script block.</span></span> <span data-ttu-id="4cee8-310">これは `ForEach-Object` 、通常のシーケンシャル処理で実行する場合よりも、オーバーヘッドが大幅に増加します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-310">This is significantly more overhead than running `ForEach-Object` normally with sequential processing.</span></span> <span data-ttu-id="4cee8-311">**並列実行** のオーバーヘッドは、スクリプトブロックで実行される作業と比較して小さくすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="4cee8-311">It is important to use **Parallel** where the overhead of running in parallel is small compared to work the script block performs.</span></span> <span data-ttu-id="4cee8-312">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-312">For example:</span></span>

  - <span data-ttu-id="4cee8-313">マルチコアマシンでの多くのコンピューティング処理を要するスクリプト</span><span class="sxs-lookup"><span data-stu-id="4cee8-313">Compute intensive scripts on multi-core machines</span></span>
  - <span data-ttu-id="4cee8-314">結果の待機時間またはファイル操作の実行に時間を費やすスクリプト</span><span class="sxs-lookup"><span data-stu-id="4cee8-314">Scripts that spend time waiting for results or doing file operations</span></span>

  <span data-ttu-id="4cee8-315">**Parallel** パラメーターを使用すると、スクリプトの実行速度が通常より遅くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4cee8-315">Using the **Parallel** parameter can cause scripts to run much slower than normal.</span></span> <span data-ttu-id="4cee8-316">並列スクリプトが単純な場合は特にそうです。</span><span class="sxs-lookup"><span data-stu-id="4cee8-316">Especially if the parallel scripts are trivial.</span></span> <span data-ttu-id="4cee8-317">**並列** で実験して、利点がある場所を見つけます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-317">Experiment with **Parallel** to discover where it can be beneficial.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="4cee8-318">`ForEach-Object -Parallel`パラメーターセットは、個別のプロセススレッドでスクリプトブロックを並列に実行します。</span><span class="sxs-lookup"><span data-stu-id="4cee8-318">The `ForEach-Object -Parallel` parameter set runs script blocks in parallel on separate process threads.</span></span> <span data-ttu-id="4cee8-319">`$using:`キーワードを使用すると、実行中の各スクリプトブロックスレッドに、コマンドレット呼び出しスレッドから変数参照を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-319">The `$using:` keyword allows passing variable references from the cmdlet invocation thread to each running script block thread.</span></span> <span data-ttu-id="4cee8-320">スクリプトブロックは異なるスレッドで実行されるため、参照渡しで渡されるオブジェクト変数は安全に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cee8-320">Since the script blocks run in different threads, the object variables passed by reference must be used safely.</span></span> <span data-ttu-id="4cee8-321">一般に、変更されていない参照先オブジェクトからは安全に読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="4cee8-321">Generally it is safe to read from referenced objects that don't change.</span></span> <span data-ttu-id="4cee8-322">ただし、オブジェクトの状態が変更されている場合は、.Net system.string などのスレッドセーフなオブジェクトを使用する必要が **あります (** 例11を参照)。</span><span class="sxs-lookup"><span data-stu-id="4cee8-322">But if the object state is being modified then you must used thread safe objects, such as .Net **System.Collection.Concurrent** types (See Example 11).</span></span>

## <span data-ttu-id="4cee8-323">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4cee8-323">Related links</span></span>

[<span data-ttu-id="4cee8-324">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="4cee8-324">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="4cee8-325">Where-Object</span><span class="sxs-lookup"><span data-stu-id="4cee8-325">Where-Object</span></span>](Where-Object.md)

[<span data-ttu-id="4cee8-326">Group-Object</span><span class="sxs-lookup"><span data-stu-id="4cee8-326">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="4cee8-327">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="4cee8-327">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="4cee8-328">New-Object</span><span class="sxs-lookup"><span data-stu-id="4cee8-328">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="4cee8-329">Select-Object</span><span class="sxs-lookup"><span data-stu-id="4cee8-329">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="4cee8-330">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="4cee8-330">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="4cee8-331">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="4cee8-331">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)
