---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-object?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-Object
ms.openlocfilehash: 4b1d1fc9961f453c43981c7c81c7de5f059a790e
ms.sourcegitcommit: f9ae48d026d65833b9c8ca881058dda0bbd067b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "93220096"
---
# <span data-ttu-id="a92c2-103">Select-Object</span><span class="sxs-lookup"><span data-stu-id="a92c2-103">Select-Object</span></span>

## <span data-ttu-id="a92c2-104">概要</span><span class="sxs-lookup"><span data-stu-id="a92c2-104">SYNOPSIS</span></span>
<span data-ttu-id="a92c2-105">オブジェクトまたはオブジェクトのプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-105">Selects objects or object properties.</span></span>

## <span data-ttu-id="a92c2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a92c2-106">SYNTAX</span></span>

### <span data-ttu-id="a92c2-107">DefaultParameter (既定値)</span><span class="sxs-lookup"><span data-stu-id="a92c2-107">DefaultParameter (Default)</span></span>

```
Select-Object [-InputObject <PSObject>] [[-Property] <Object[]>] [-ExcludeProperty <String[]>]
 [-ExpandProperty <String>] [-Unique] [-Last <Int32>] [-First <Int32>] [-Skip <Int32>] [-Wait]
 [<CommonParameters>]
```

### <span data-ttu-id="a92c2-108">SkipLastParameter</span><span class="sxs-lookup"><span data-stu-id="a92c2-108">SkipLastParameter</span></span>

```
Select-Object [-InputObject <PSObject>] [[-Property] <Object[]>] [-ExcludeProperty <String[]>]
 [-ExpandProperty <String>] [-Unique] [-SkipLast <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="a92c2-109">IndexParameter</span><span class="sxs-lookup"><span data-stu-id="a92c2-109">IndexParameter</span></span>

```
Select-Object [-InputObject <PSObject>] [-Unique] [-Wait] [-Index <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="a92c2-110">SkipIndexParameter</span><span class="sxs-lookup"><span data-stu-id="a92c2-110">SkipIndexParameter</span></span>

```
Select-Object [-InputObject <PSObject>] [-Unique] [-SkipIndex <Int32[]>] [<CommonParameters>]
```

## <span data-ttu-id="a92c2-111">Description</span><span class="sxs-lookup"><span data-stu-id="a92c2-111">DESCRIPTION</span></span>

<span data-ttu-id="a92c2-112">`Select-Object`コマンドレットでは、オブジェクトまたはオブジェクトのセットの指定されたプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-112">The `Select-Object` cmdlet selects specified properties of an object or set of objects.</span></span> <span data-ttu-id="a92c2-113">加えて、配列内の一意のオブジェクト、指定された数のオブジェクト、または指定された位置にあるオブジェクトを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-113">It can also select unique objects, a specified number of objects, or objects in a specified position in an array.</span></span>

<span data-ttu-id="a92c2-114">コレクションからオブジェクトを選択するには、 **First** 、 **Last** 、 **Unique** 、 **Skip** 、および **Index** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-114">To select objects from a collection, use the **First** , **Last** , **Unique** , **Skip** , and **Index** parameters.</span></span> <span data-ttu-id="a92c2-115">オブジェクトのプロパティを選択するには、 **Property** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-115">To select object properties, use the **Property** parameter.</span></span> <span data-ttu-id="a92c2-116">[プロパティ] を選択すると、は `Select-Object` 指定されたプロパティのみを持つ新しいオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-116">When you select properties, `Select-Object` returns new objects that have only the specified properties.</span></span>

<span data-ttu-id="a92c2-117">Windows PowerShell 3.0 以降では、には、使用されて `Select-Object` いないオブジェクトの作成および処理を防止する最適化機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a92c2-117">Beginning in Windows PowerShell 3.0, `Select-Object` includes an optimization feature that prevents commands from creating and processing objects that are not used.</span></span>

<span data-ttu-id="a92c2-118">コマンド `Select-Object` パイプラインに **最初** のパラメーターまたは **インデックス** のパラメーターを含むコマンドを含めると、オブジェクトを生成するコマンドがパイプラインのコマンドの前に表示されていても、選択したオブジェクトの数が生成されるとすぐに、PowerShell はオブジェクトを生成するコマンドを停止し `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-118">When you include a `Select-Object` command with the **First** or **Index** parameters in a command pipeline, PowerShell stops the command that generates the objects as soon as the selected number of objects is generated, even when the command that generates the objects appears before the `Select-Object` command in the pipeline.</span></span> <span data-ttu-id="a92c2-119">この最適化動作を無効にするには、 **Wait** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-119">To turn off this optimizing behavior, use the **Wait** parameter.</span></span>

## <span data-ttu-id="a92c2-120">例</span><span class="sxs-lookup"><span data-stu-id="a92c2-120">EXAMPLES</span></span>

### <span data-ttu-id="a92c2-121">例 1: プロパティによってオブジェクトを選択する</span><span class="sxs-lookup"><span data-stu-id="a92c2-121">Example 1: Select objects by property</span></span>

<span data-ttu-id="a92c2-122">この例では、プロセスオブジェクトの **名前** 、 **ID** 、およびワーキングセット ( **WS** ) プロパティを持つオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-122">This example creates objects that have the **Name** , **ID** , and working set ( **WS** ) properties of process objects.</span></span>

```powershell
Get-Process | Select-Object -Property ProcessName, Id, WS
```

### <span data-ttu-id="a92c2-123">例 2: プロパティによってオブジェクトを選択し、結果を書式設定する</span><span class="sxs-lookup"><span data-stu-id="a92c2-123">Example 2: Select objects by property and format the results</span></span>

<span data-ttu-id="a92c2-124">この例では、コンピューター上のプロセスによって使用されているモジュールに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-124">This example gets information about the modules used by the processes on the computer.</span></span> <span data-ttu-id="a92c2-125">コマンドレットを使用して、 `Get-Process` コンピューター上のプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-125">It uses `Get-Process` cmdlet to get the process on the computer.</span></span>

<span data-ttu-id="a92c2-126">コマンドレットを使用して、 `Select-Object` `[System.Diagnostics.ProcessModule]` によって出力された各インスタンスの **Modules** プロパティに含まれるインスタンスの配列を出力し `System.Diagnostics.Process` `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-126">It uses the `Select-Object` cmdlet to output an array of `[System.Diagnostics.ProcessModule]` instances as contained in the **Modules** property of each `System.Diagnostics.Process` instance output by `Get-Process`.</span></span>

<span data-ttu-id="a92c2-127">コマンドレットの **Property** パラメーターは、 `Select-Object` プロセス名を選択します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-127">The **Property** parameter of the `Select-Object` cmdlet selects the process names.</span></span> <span data-ttu-id="a92c2-128">これ `ProcessName` により、すべてのインスタンスに **"メモ" プロパティ** が追加さ `[System.Diagnostics.ProcessModule]` れ、現在のプロセスの **ProcessName** プロパティの値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-128">This adds a `ProcessName` **NoteProperty** to every `[System.Diagnostics.ProcessModule]` instance and populates it with the value of current process's **ProcessName** property.</span></span>

<span data-ttu-id="a92c2-129">最後に、コマンドレットを使用して、 `Format-List` 各プロセスの名前とモジュールを一覧に表示します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-129">Finally, `Format-List` cmdlet is used to display the name and modules of each process in a list.</span></span>

```powershell
Get-Process Explorer | Select-Object -Property ProcessName -ExpandProperty Modules | Format-List
```

```Output
ProcessName       : explorer
ModuleName        : explorer.exe
FileName          : C:\WINDOWS\explorer.exe
BaseAddress       : 140697278152704
ModuleMemorySize  : 3919872
EntryPointAddress : 140697278841168
FileVersionInfo   : File:             C:\WINDOWS\explorer.exe
                    InternalName:     explorer
                    OriginalFilename: EXPLORER.EXE.MUI
                    FileVersion:      10.0.17134.1 (WinBuild.160101.0800)
                    FileDescription:  Windows Explorer
                    Product:          Microsoft Windows Operating System
                    ProductVersion:   10.0.17134.1
...
```

### <span data-ttu-id="a92c2-130">例 3: 最も多くのメモリを使用するプロセスを選択する</span><span class="sxs-lookup"><span data-stu-id="a92c2-130">Example 3: Select processes using the most memory</span></span>

<span data-ttu-id="a92c2-131">この例では、最も多くのメモリを使用している5つのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-131">This example gets the five processes that are using the most memory.</span></span> <span data-ttu-id="a92c2-132">`Get-Process`コマンドレットは、コンピューター上のプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-132">The `Get-Process` cmdlet gets the processes on the computer.</span></span> <span data-ttu-id="a92c2-133">`Sort-Object`コマンドレットは、メモリ (ワーキングセット) の使用状況に応じてプロセスを並べ替えます。このコマンドレットは、結果として `Select-Object` 得られるオブジェクトの配列の最後の5つのメンバーのみを選択します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-133">The `Sort-Object` cmdlet sorts the processes according to memory (working set) usage, and the `Select-Object` cmdlet selects only the last five members of the resulting array of objects.</span></span>

<span data-ttu-id="a92c2-134">コマンドレットを含むコマンドでは、 **Wait** パラメーターは必要ありません。これは、が `Sort-Object` `Sort-Object` すべてのオブジェクトを処理してから、コレクションを返すためです。</span><span class="sxs-lookup"><span data-stu-id="a92c2-134">The **Wait** parameter is not required in commands that include the `Sort-Object` cmdlet because `Sort-Object` processes all objects and then returns a collection.</span></span> <span data-ttu-id="a92c2-135">`Select-Object`最適化は、オブジェクトが処理されたときにオブジェクトを個別に返すコマンドに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-135">The `Select-Object` optimization is available only for commands that return objects individually as they are processed.</span></span>

```powershell
Get-Process | Sort-Object -Property WS | Select-Object -Last 5
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VS(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
2866     320       33432      45764   203   222.41   1292 svchost
577      17        23676      50516   265    50.58   4388 WINWORD
826      11        75448      76712   188    19.77   3780 Ps
1367     14        73152      88736   216    61.69    676 Ps
1612     44        66080      92780   380   900.59   6132 INFOPATH
```

### <span data-ttu-id="a92c2-136">例 4: 配列から一意の文字を選択する</span><span class="sxs-lookup"><span data-stu-id="a92c2-136">Example 4: Select unique characters from an array</span></span>

<span data-ttu-id="a92c2-137">この例では、の **unique** パラメーターを使用して、 `Select-Object` 文字の配列から一意の文字を取得します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-137">This example uses the **Unique** parameter of `Select-Object` to get unique characters from an array of characters.</span></span>

```powershell
"a","b","c","a","a","a" | Select-Object -Unique
```

```Output
a
b
c
```

### <span data-ttu-id="a92c2-138">例 5: イベントログで最新および最も古いイベントを選択する</span><span class="sxs-lookup"><span data-stu-id="a92c2-138">Example 5: Select newest and oldest events in the event log</span></span>

<span data-ttu-id="a92c2-139">この例では、Windows PowerShell イベントログの最初の (最新の) イベントと最後の (最も古い) イベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-139">This example gets the first (newest) and last (oldest) events in the Windows PowerShell event log.</span></span>

<span data-ttu-id="a92c2-140">`Get-EventLog` Windows PowerShell ログ内のすべてのイベントを取得し、変数に保存し `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-140">`Get-EventLog` gets all events in the Windows PowerShell log and saves them in the `$a` variable.</span></span>
<span data-ttu-id="a92c2-141">次 `$a` に、はコマンドレットにパイプ処理され `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-141">Then, `$a` is piped to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="a92c2-142">この `Select-Object` コマンドは、 **Index** パラメーターを使用して、変数内のイベントの配列からイベントを選択し `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-142">The `Select-Object` command uses the **Index** parameter to select events from the array of events in the `$a` variable.</span></span> <span data-ttu-id="a92c2-143">最初のイベントのインデックスは 0 です。</span><span class="sxs-lookup"><span data-stu-id="a92c2-143">The index of the first event is 0.</span></span> <span data-ttu-id="a92c2-144">最後のイベントのインデックスは、の項目数から1を引いた値です `$a` 。</span><span class="sxs-lookup"><span data-stu-id="a92c2-144">The index of the last event is the number of items in `$a` minus 1.</span></span>

```powershell
$a = Get-EventLog -LogName "Windows PowerShell"
$a | Select-Object -Index 0, ($A.count - 1)
```

### <span data-ttu-id="a92c2-145">例 6: 最初のオブジェクト以外のすべてを選択する</span><span class="sxs-lookup"><span data-stu-id="a92c2-145">Example 6: Select all but the first object</span></span>

<span data-ttu-id="a92c2-146">この例では、最初のファイルを除き、Servers.txt ファイルに一覧表示されている各コンピューターに新しい PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-146">This example creates a new PSSession on each of the computers listed in the Servers.txt files, except for the first one.</span></span>

<span data-ttu-id="a92c2-147">`Select-Object` コンピューター名の一覧で、最初のコンピューター以外のすべてを選択します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-147">`Select-Object` selects all but the first computer in a list of computer names.</span></span> <span data-ttu-id="a92c2-148">結果として得られるコンピューターの一覧は、コマンドレットの **ComputerName** パラメーターの値として設定され `New-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-148">The resulting list of computers is set as the value of the **ComputerName** parameter of the `New-PSSession` cmdlet.</span></span>

```powershell
New-PSSession -ComputerName (Get-Content Servers.txt | Select-Object -Skip 1)
```

### <span data-ttu-id="a92c2-149">例 7: ファイル名を変更し、いくつかを選択して確認する</span><span class="sxs-lookup"><span data-stu-id="a92c2-149">Example 7: Rename files and select several to review</span></span>

<span data-ttu-id="a92c2-150">この例では、読み取り専用属性を持つテキストファイルのベース名に "-ro" サフィックスを追加し、最初の5つのファイルを表示して、ユーザーが効果のサンプルを確認できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a92c2-150">This example adds a "-ro" suffix to the base names of text files that have the read-only attribute and then displays the first five files so the user can see a sample of the effect.</span></span>

<span data-ttu-id="a92c2-151">`Get-ChildItem`**ReadOnly** 動的パラメーターを使用して、読み取り専用のファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-151">`Get-ChildItem` uses the **ReadOnly** dynamic parameter to get read-only files.</span></span> <span data-ttu-id="a92c2-152">結果として得られるファイルはコマンドレットにパイプ処理され、ファイル名が変更され `Rename-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-152">The resulting files are piped to the `Rename-Item` cmdlet, which renames the file.</span></span> <span data-ttu-id="a92c2-153">の **Passthru** パラメーターを使用して、 `Rename-Item` 名前が変更されたファイルをコマンドレットに送信し `Select-Object` ます。このコマンドレットは、表示する最初の5を選択します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-153">It uses the **Passthru** parameter of `Rename-Item` to send the renamed files to the `Select-Object` cmdlet, which selects the first 5 for display.</span></span>

<span data-ttu-id="a92c2-154">の **Wait** パラメーターを指定すると、 `Select-Object` `Get-ChildItem` 最初の5つの読み取り専用テキストファイルを取得した後、PowerShell がコマンドレットを停止できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a92c2-154">The **Wait** parameter of `Select-Object` prevents PowerShell from stopping the `Get-ChildItem` cmdlet after it gets the first five read-only text files.</span></span> <span data-ttu-id="a92c2-155">このパラメーターを指定しない場合、最初の 5 つの読み取り専用ファイルだけ名前が変更されます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-155">Without this parameter, only the first five read-only files would be renamed.</span></span>

```powershell
Get-ChildItem *.txt -ReadOnly |
    Rename-Item -NewName {$_.BaseName + "-ro.txt"} -PassThru |
    Select-Object -First 5 -Wait
```

### <span data-ttu-id="a92c2-156">例 8:-ExpandProperty パラメーターの複雑さを示す</span><span class="sxs-lookup"><span data-stu-id="a92c2-156">Example 8: Demonstrate the intricacies of the -ExpandProperty parameter</span></span>

<span data-ttu-id="a92c2-157">この例は、 **Expandproperty** パラメーターの複雑な例を示しています。</span><span class="sxs-lookup"><span data-stu-id="a92c2-157">This example demonstrates the intricacies of the **ExpandProperty** parameter.</span></span>

<span data-ttu-id="a92c2-158">生成された出力はインスタンスの配列であることに注意して `[System.Int32]` ください。</span><span class="sxs-lookup"><span data-stu-id="a92c2-158">Note that the output generated was an array of `[System.Int32]` instances.</span></span> <span data-ttu-id="a92c2-159">インスタンスは、 **出力ビュー** の標準の書式設定規則に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="a92c2-159">The instances conform to standard formatting rules of the **Output View**.</span></span> <span data-ttu-id="a92c2-160">これは、 *展開* されたプロパティに対しても当てはまります。</span><span class="sxs-lookup"><span data-stu-id="a92c2-160">This is true for any *Expanded* properties.</span></span> <span data-ttu-id="a92c2-161">出力されたオブジェクトに特定の標準形式がある場合、展開されたプロパティは表示されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a92c2-161">If the outputted objects have a specific standard format, the expanded property might not be visible.</span></span>

```powershell
# Create a custom object to use for the Select-Object example.
$object = [pscustomobject]@{Name="CustomObject";Expand=@(1,2,3,4,5)}
# Use the ExpandProperty parameter to Expand the property.
$object | Select-Object -ExpandProperty Expand -Property Name
```

```Output
1
2
3
4
5
```

```powershell
# The output did not contain the Name property, but it was added successfully.
# Use Get-Member to confirm the Name property was added and populated.
$object | Select-Object -ExpandProperty Expand -Property Name | Get-Member
```

```Output
   TypeName: System.Int32

Name        MemberType   Definition
----        ----------   ----------
CompareTo   Method       int CompareTo(System.Object value), int CompareTo(int value), int IComparable.CompareTo(System.Object obj)...
Equals      Method       bool Equals(System.Object obj), bool Equals(int obj), bool IEquatable[int].Equals(int other)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
GetTypeCode Method       System.TypeCode GetTypeCode(), System.TypeCode IConvertible.GetTypeCode()
ToBoolean   Method       bool IConvertible.ToBoolean(System.IFormatProvider provider)
ToByte      Method       byte IConvertible.ToByte(System.IFormatProvider provider)
ToChar      Method       char IConvertible.ToChar(System.IFormatProvider provider)
ToDateTime  Method       datetime IConvertible.ToDateTime(System.IFormatProvider provider)
ToDecimal   Method       decimal IConvertible.ToDecimal(System.IFormatProvider provider)
ToDouble    Method       double IConvertible.ToDouble(System.IFormatProvider provider)
ToInt16     Method       int16 IConvertible.ToInt16(System.IFormatProvider provider)
ToInt32     Method       int IConvertible.ToInt32(System.IFormatProvider provider)
ToInt64     Method       long IConvertible.ToInt64(System.IFormatProvider provider)
ToSByte     Method       sbyte IConvertible.ToSByte(System.IFormatProvider provider)
ToSingle    Method       float IConvertible.ToSingle(System.IFormatProvider provider)
ToString    Method       string ToString(), string ToString(string format), string ToString(System.IFormatProvider provider)...
ToType      Method       System.Object IConvertible.ToType(type conversionType, System.IFormatProvider provider)
ToUInt16    Method       uint16 IConvertible.ToUInt16(System.IFormatProvider provider)
ToUInt32    Method       uint32 IConvertible.ToUInt32(System.IFormatProvider provider)
ToUInt64    Method       uint64 IConvertible.ToUInt64(System.IFormatProvider provider)
Name        NoteProperty string Name=CustomObject
```

### <span data-ttu-id="a92c2-162">例 9: オブジェクトのカスタムプロパティを作成する</span><span class="sxs-lookup"><span data-stu-id="a92c2-162">Example 9: Create custom properties on objects</span></span>

<span data-ttu-id="a92c2-163">次の例は、を使用して `Select-Object` 、任意のオブジェクトにカスタムプロパティを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a92c2-163">The following example demonstrates using `Select-Object` to add a custom property to any object.</span></span>
<span data-ttu-id="a92c2-164">存在しないプロパティ名を指定すると、は `Select-Object` 渡された各オブジェクトに対して、そのプロパティを " **メモ" プロパティ** として作成します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-164">When you specify a property name that does not exist, `Select-Object` creates that property as a **NoteProperty** on each object passed.</span></span>

```powershell
$customObject = 1 | Select-Object -Property MyCustomProperty
$customObject.MyCustomProperty = "New Custom Property"
$customObject
```

```Output
MyCustomProperty
----------------
New Custom Property
```

### <span data-ttu-id="a92c2-165">例 10: InputObject ごとに計算されるプロパティを作成する</span><span class="sxs-lookup"><span data-stu-id="a92c2-165">Example 10: Create calculated properties for each InputObject</span></span>

<span data-ttu-id="a92c2-166">この例では、を使用して `Select-Object` 、計算されたプロパティを入力に追加します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-166">This example demonstrates using `Select-Object` to add calculated properties to your input.</span></span> <span data-ttu-id="a92c2-167">**ScriptBlock** を **Property** パラメーターに渡すと、 `Select-Object` は渡された各オブジェクトに対して式を評価し、結果を出力に追加します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-167">Passing a **ScriptBlock** to the **Property** parameter causes `Select-Object` to evaluate the expression on each object passed and add the results to the output.</span></span> <span data-ttu-id="a92c2-168">**ScriptBlock** 内では、変数を使用して、 `$_` パイプライン内の現在のオブジェクトを参照できます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-168">Within the **ScriptBlock** , you can use the `$_` variable to reference the current object in the pipeline.</span></span>

<span data-ttu-id="a92c2-169">既定で `Select-Object` は、は、プロパティの名前として **ScriptBlock** 文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-169">By default, `Select-Object` will use the **ScriptBlock** string as the name of the property.</span></span> <span data-ttu-id="a92c2-170">**Hashtable** を使用すると、各オブジェクトに追加されたカスタムプロパティとして **ScriptBlock** の出力にラベルを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-170">Using a **Hashtable** , you can label the output of your **ScriptBlock** as a custom property added to each object.</span></span> <span data-ttu-id="a92c2-171">に渡された各オブジェクトには、複数の計算されるプロパティを追加でき `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-171">You can add multiple calculated properties to each object passed to `Select-Object`.</span></span>

```powershell
# Create a calculated property called $_.StartTime.DayOfWeek
Get-Process | Select-Object -Property ProcessName,{$_.StartTime.DayOfWeek}
```

```Output
ProcessName  $_.StartTime.DayOfWeek
----         ----------------------
alg                       Wednesday
ati2evxx                  Wednesday
ati2evxx                   Thursday
...
```

```powershell
# Add a custom property to calculate the size in KiloBytes of each FileInfo object you pass in.
# Use the pipeline variable to divide each file's length by 1 KiloBytes
$size = @{label="Size(KB)";expression={$_.length/1KB}}
# Create an additional calculated property with the number of Days since the file was last accessed.
# You can also shorten the key names to be 'l', and 'e', or use Name instead of Label.
$days = @{l="Days";e={((Get-Date) - $_.LastAccessTime).Days}}
# You can also shorten the name of your label key to 'l' and your expression key to 'e'.
Get-ChildItem $PSHOME -File | Select-Object Name, $size, $days
```

```Output
Name                        Size(KB)        Days
----                        --------        ----
Certificate.format.ps1xml   12.5244140625   223
Diagnostics.Format.ps1xml   4.955078125     223
DotNetTypes.format.ps1xml   134.9833984375  223
```

## <span data-ttu-id="a92c2-172">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a92c2-172">PARAMETERS</span></span>

### <span data-ttu-id="a92c2-173">-ExcludeProperty</span><span class="sxs-lookup"><span data-stu-id="a92c2-173">-ExcludeProperty</span></span>

<span data-ttu-id="a92c2-174">このコマンドレットによって操作から除外されるプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-174">Specifies the properties that this cmdlet excludes from the operation.</span></span> <span data-ttu-id="a92c2-175">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-175">Wildcards are permitted.</span></span>

<span data-ttu-id="a92c2-176">PowerShell 6 以降では、 **Excludeproperty** の **property** パラメーターを使用する必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a92c2-176">Beginning in PowerShell 6, it is no longer required to include the **Property** parameter for **ExcludeProperty** to work.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DefaultParameter, SkipLastParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a92c2-177">-ExpandProperty</span><span class="sxs-lookup"><span data-stu-id="a92c2-177">-ExpandProperty</span></span>

<span data-ttu-id="a92c2-178">選択するプロパティを指定し、そのプロパティの展開を試みることを示します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-178">Specifies a property to select, and indicates that an attempt should be made to expand that property.</span></span>

- <span data-ttu-id="a92c2-179">指定したプロパティが配列の場合は、配列の各値が出力に含まれます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-179">If the specified property is an array, each value of the array is included in the output.</span></span>
- <span data-ttu-id="a92c2-180">指定されたプロパティがオブジェクトの場合、オブジェクトのプロパティは **InputObject** ごとに展開されます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-180">If the specified property is an object, the objects properties are expanded for every **InputObject**</span></span>

<span data-ttu-id="a92c2-181">どちらの場合も、出力されるオブジェクトの **型** は、展開されたプロパティの **型** と一致します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-181">In either case, the **Type** of objects output will match the **Type** of the expanded property.</span></span>

<span data-ttu-id="a92c2-182">**Property** パラメーターが指定されている場合、 `Select-Object` は、出力されたすべてのオブジェクトに対して、選択した各プロパティを **メモプロパティ** として追加しようとします。</span><span class="sxs-lookup"><span data-stu-id="a92c2-182">If the **Property** parameter is specified, `Select-Object` will attempt to add each selected property as a **NoteProperty** to every outputted object.</span></span>

> [!WARNING]
> <span data-ttu-id="a92c2-183">次のエラーが表示された場合: プロパティが既に存在するため、プロパティを処理できません `<PropertyName>` 。次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="a92c2-183">If you receive the error: Select : Property cannot be processed because property `<PropertyName>` already exists, consider the following.</span></span>
> <span data-ttu-id="a92c2-184">を使用する場合 `-ExpandProperty` 、 `Select-Object` 既存のプロパティを置き換えることはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a92c2-184">Note that when using `-ExpandProperty`, `Select-Object` can not replace an existing property.</span></span>
> <span data-ttu-id="a92c2-185">そのため、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a92c2-185">This means:</span></span>
>
> - <span data-ttu-id="a92c2-186">展開されたオブジェクトに同じ名前のプロパティがある場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-186">If the expanded object has a property of the same name, an error will occur.</span></span>
> - <span data-ttu-id="a92c2-187">*選択し* たオブジェクトに、 *展開* されたオブジェクトのプロパティと同じ名前のプロパティがある場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-187">If the *Selected* object has a property of the same name as an *Expanded* objects property, an error will occur.</span></span>

```yaml
Type: System.String
Parameter Sets: DefaultParameter, SkipLastParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a92c2-188">-最初</span><span class="sxs-lookup"><span data-stu-id="a92c2-188">-First</span></span>

<span data-ttu-id="a92c2-189">入力オブジェクトの配列の先頭から選択するオブジェクトの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-189">Specifies the number of objects to select from the beginning of an array of input objects.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a92c2-190">-インデックス</span><span class="sxs-lookup"><span data-stu-id="a92c2-190">-Index</span></span>

<span data-ttu-id="a92c2-191">インデックス値に基づいて配列からオブジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-191">Selects objects from an array based on their index values.</span></span> <span data-ttu-id="a92c2-192">インデックスをコンマ区切りリスト形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-192">Enter the indexes in a comma-separated list.</span></span> <span data-ttu-id="a92c2-193">配列内インデックスは 0 で始まります。0 は最初の値を表し、(n-1) は最後の値を表します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-193">Indexes in an array begin with 0, where 0 represents the first value and (n-1) represents the last value.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: IndexParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a92c2-194">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a92c2-194">-InputObject</span></span>

<span data-ttu-id="a92c2-195">パイプラインを介してコマンドレットに送信するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-195">Specifies objects to send to the cmdlet through the pipeline.</span></span> <span data-ttu-id="a92c2-196">このパラメーターを使用すると、オブジェクトをにパイプすることができ `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-196">This parameter enables you to pipe objects to `Select-Object`.</span></span>

<span data-ttu-id="a92c2-197">オブジェクトを **inputobject** パラメーターに渡すと、パイプラインを使用する代わりに、は、 `Select-Object` 値がコレクションの場合でも、 **inputobject** を1つのオブジェクトとして扱います。</span><span class="sxs-lookup"><span data-stu-id="a92c2-197">When you pass objects to the **InputObject** parameter, instead of using the pipeline, `Select-Object` treats the **InputObject** as a single object, even if the value is a collection.</span></span> <span data-ttu-id="a92c2-198">にコレクションを渡す場合は、パイプラインを使用することをお勧めし `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-198">It is recommended that you use the pipeline when passing collections to `Select-Object`.</span></span>

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

### <span data-ttu-id="a92c2-199">-Last</span><span class="sxs-lookup"><span data-stu-id="a92c2-199">-Last</span></span>

<span data-ttu-id="a92c2-200">入力オブジェクトの配列の末尾から選択するオブジェクトの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-200">Specifies the number of objects to select from the end of an array of input objects.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a92c2-201">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="a92c2-201">-Property</span></span>

<span data-ttu-id="a92c2-202">選択するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-202">Specifies the properties to select.</span></span> <span data-ttu-id="a92c2-203">これらのプロパティは、出力オブジェクトに **"メモ" プロパティ** メンバーとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-203">These properties are added as **NoteProperty** members to the output objects.</span></span> <span data-ttu-id="a92c2-204">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-204">Wildcards are permitted.</span></span>

<span data-ttu-id="a92c2-205">**Property** パラメーターの値には、新しい集計プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-205">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="a92c2-206">集計プロパティを作成するには、ハッシュ テーブルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-206">To create a calculated, property, use a hash table.</span></span>

<span data-ttu-id="a92c2-207">有効なキーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a92c2-207">Valid keys are:</span></span>

- <span data-ttu-id="a92c2-208">名前 (またはラベル)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="a92c2-208">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="a92c2-209">式 `<string>` または `<script block>`</span><span class="sxs-lookup"><span data-stu-id="a92c2-209">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="a92c2-210">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a92c2-210">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: DefaultParameter, SkipLastParameter
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a92c2-211">-Skip</span><span class="sxs-lookup"><span data-stu-id="a92c2-211">-Skip</span></span>

<span data-ttu-id="a92c2-212">指定した数の項目をスキップします (選択しません)。</span><span class="sxs-lookup"><span data-stu-id="a92c2-212">Skips (does not select) the specified number of items.</span></span> <span data-ttu-id="a92c2-213">既定では、 **Skip** パラメーターは、配列またはオブジェクトのリストの先頭からカウントされますが、コマンドが **最後** のパラメーターを使用する場合は、リストまたは配列の末尾からカウントされます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-213">By default, the **Skip** parameter counts from the beginning of the array or list of objects, but if the command uses the **Last** parameter, it counts from the end of the list or array.</span></span>

<span data-ttu-id="a92c2-214">カウントが 0 から始まる **Index** パラメーターとは異なり、 **Skip** パラメーターではカウントが 1 から始まります。</span><span class="sxs-lookup"><span data-stu-id="a92c2-214">Unlike the **Index** parameter, which starts counting at 0, the **Skip** parameter begins at 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a92c2-215">-SkipLast</span><span class="sxs-lookup"><span data-stu-id="a92c2-215">-SkipLast</span></span>

<span data-ttu-id="a92c2-216">リストまたは配列の末尾から、指定された数の項目をスキップします (選択しません)。</span><span class="sxs-lookup"><span data-stu-id="a92c2-216">Skips (does not select) the specified number of items from the end of the list or array.</span></span> <span data-ttu-id="a92c2-217">**最後** のパラメーターと共に **Skip** を使用する場合と同じ方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-217">Works in the same way as using **Skip** together with **Last** parameter.</span></span>

<span data-ttu-id="a92c2-218">0からカウントを開始する **Index** パラメーターとは異なり、 **SkipLast** パラメーターは1から始まります。</span><span class="sxs-lookup"><span data-stu-id="a92c2-218">Unlike the **Index** parameter, which starts counting at 0, the **SkipLast** parameter begins at 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: SkipLastParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a92c2-219">-一意</span><span class="sxs-lookup"><span data-stu-id="a92c2-219">-Unique</span></span>

<span data-ttu-id="a92c2-220">入力オブジェクトのサブセットが同じプロパティと値を持つ場合にサブセットの 1 つのメンバーのみを選択することを指定します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-220">Specifies that if a subset of the input objects has identical properties and values, only a single member of the subset will be selected.</span></span>

<span data-ttu-id="a92c2-221">このパラメーターでは、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-221">This parameter is case-sensitive.</span></span> <span data-ttu-id="a92c2-222">その結果、大文字と小文字のみが異なる文字列は一意であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-222">As a result, strings that differ only in character casing are considered to be unique.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a92c2-223">-Wait</span><span class="sxs-lookup"><span data-stu-id="a92c2-223">-Wait</span></span>

<span data-ttu-id="a92c2-224">コマンドレットによる最適化がオフになっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="a92c2-224">Indicates that the cmdlet turns off optimization.</span></span> <span data-ttu-id="a92c2-225">PowerShell では、コマンドがコマンドパイプラインに出現する順序で実行され、すべてのオブジェクトを生成できます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-225">PowerShell runs commands in the order that they appear in the command pipeline and lets them generate all objects.</span></span> <span data-ttu-id="a92c2-226">既定では、コマンド `Select-Object` パイプラインに **最初** のパラメーターまたは **インデックス** パラメーターを含むコマンドを含めると、選択したオブジェクト数が生成されるとすぐに、オブジェクトを生成するコマンドが PowerShell によって停止されます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-226">By default, if you include a `Select-Object` command with the **First** or **Index** parameters in a command pipeline, PowerShell stops the command that generates the objects as soon as the selected number of objects is generated.</span></span>

<span data-ttu-id="a92c2-227">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a92c2-227">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultParameter, IndexParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a92c2-228">-SkipIndex</span><span class="sxs-lookup"><span data-stu-id="a92c2-228">-SkipIndex</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SkipIndexParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a92c2-229">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a92c2-229">CommonParameters</span></span>

<span data-ttu-id="a92c2-230">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a92c2-230">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a92c2-231">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a92c2-231">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a92c2-232">入力</span><span class="sxs-lookup"><span data-stu-id="a92c2-232">INPUTS</span></span>

### <span data-ttu-id="a92c2-233">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="a92c2-233">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="a92c2-234">パイプを使用して任意のオブジェクトをにパイプすることができ `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-234">You can pipe any object to `Select-Object`.</span></span>

## <span data-ttu-id="a92c2-235">出力</span><span class="sxs-lookup"><span data-stu-id="a92c2-235">OUTPUTS</span></span>

### <span data-ttu-id="a92c2-236">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="a92c2-236">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="a92c2-237">注</span><span class="sxs-lookup"><span data-stu-id="a92c2-237">NOTES</span></span>

- <span data-ttu-id="a92c2-238">コマンドレットは、組み込みエイリアスであるを使用して参照することもでき `Select-Object` `select` ます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-238">You can also refer to the `Select-Object` cmdlet by its built-in alias, `select`.</span></span> <span data-ttu-id="a92c2-239">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a92c2-239">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

- <span data-ttu-id="a92c2-240">の最適化機能 `Select-Object` は、オブジェクトが処理されるときにパイプラインにオブジェクトを書き込むコマンドに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a92c2-240">The optimization feature of `Select-Object` is available only for commands that write objects to the pipeline as they are processed.</span></span> <span data-ttu-id="a92c2-241">処理したオブジェクトをバッファーに格納してコレクションとして書き込むコマンドには作用しません。</span><span class="sxs-lookup"><span data-stu-id="a92c2-241">It has no effect on commands that buffer processed objects and write them as a collection.</span></span> <span data-ttu-id="a92c2-242">オブジェクトをすぐに書き込むのは、コマンドレットのデザイン上のベスト プラクティスです。</span><span class="sxs-lookup"><span data-stu-id="a92c2-242">Writing objects immediately is a cmdlet design best practice.</span></span> <span data-ttu-id="a92c2-243">詳細については、「 _1 つのレコードをパイプラインに書き込む_ [」を参照](/powershell/scripting/developer/windows-powershell)してください。</span><span class="sxs-lookup"><span data-stu-id="a92c2-243">For more information, see _Write Single Records to the Pipeline_ in [Strongly Encouraged Development Guidelines](/powershell/scripting/developer/windows-powershell).</span></span>

## <span data-ttu-id="a92c2-244">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a92c2-244">RELATED LINKS</span></span>

[<span data-ttu-id="a92c2-245">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="a92c2-245">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="a92c2-246">Group-Object</span><span class="sxs-lookup"><span data-stu-id="a92c2-246">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="a92c2-247">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="a92c2-247">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="a92c2-248">Where-Object</span><span class="sxs-lookup"><span data-stu-id="a92c2-248">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
