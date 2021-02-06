---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Object
ms.openlocfilehash: 594837b2f85f4d5d5d4125d3f7c63ad2c8a16153
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602786"
---
# <span data-ttu-id="2ff43-102">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="2ff43-102">Measure-Object</span></span>

## <span data-ttu-id="2ff43-103">概要</span><span class="sxs-lookup"><span data-stu-id="2ff43-103">SYNOPSIS</span></span>
<span data-ttu-id="2ff43-104">オブジェクトの数値プロパティと、テキストのファイルなど文字列オブジェクト内の文字、単語、および行を計算します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-104">Calculates the numeric properties of objects, and the characters, words, and lines in string objects, such as files of text.</span></span>

## <span data-ttu-id="2ff43-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2ff43-105">SYNTAX</span></span>

### <span data-ttu-id="2ff43-106">GenericMeasure (既定値)</span><span class="sxs-lookup"><span data-stu-id="2ff43-106">GenericMeasure (Default)</span></span>

```
Measure-Object [[-Property] <PSPropertyExpression[]>] [-InputObject <PSObject>] [-StandardDeviation]
 [-Sum] [-AllStats] [-Average] [-Maximum] [-Minimum] [<CommonParameters>]
```

### <span data-ttu-id="2ff43-107">TextMeasure</span><span class="sxs-lookup"><span data-stu-id="2ff43-107">TextMeasure</span></span>

```
Measure-Object [[-Property] <PSPropertyExpression[]>] [-InputObject <PSObject>] [-Line] [-Word]
 [-Character] [-IgnoreWhiteSpace] [<CommonParameters>]
```

## <span data-ttu-id="2ff43-108">Description</span><span class="sxs-lookup"><span data-stu-id="2ff43-108">DESCRIPTION</span></span>

<span data-ttu-id="2ff43-109">コマンドレットでは、 `Measure-Object` 特定の種類のオブジェクトのプロパティ値を計算します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-109">The `Measure-Object` cmdlet calculates the property values of certain types of object.</span></span>
<span data-ttu-id="2ff43-110">`Measure-Object` コマンド内のパラメーターに応じて、3種類の測定を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-110">`Measure-Object` performs three types of measurements, depending on the parameters in the command.</span></span>

<span data-ttu-id="2ff43-111">コマンドレットでは、 `Measure-Object` オブジェクトのプロパティ値に対して計算を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-111">The `Measure-Object` cmdlet performs calculations on the property values of objects.</span></span> <span data-ttu-id="2ff43-112">を使用すると、 `Measure-Object` オブジェクトをカウントしたり、指定した **プロパティ** を使用してオブジェクトをカウントしたりできます。</span><span class="sxs-lookup"><span data-stu-id="2ff43-112">You can use `Measure-Object` to count objects or count objects with a specified **Property**.</span></span> <span data-ttu-id="2ff43-113">また、を使用して、 `Measure-Object` 数値の **最小** 値、 **最大** 値、 **合計**、 **標準偏差** 、 **平均** を計算することもできます。</span><span class="sxs-lookup"><span data-stu-id="2ff43-113">You can also use `Measure-Object` to calculate the **Minimum**, **Maximum**, **Sum**, **StandardDeviation** and **Average** of numeric values.</span></span> <span data-ttu-id="2ff43-114">**文字列** オブジェクトの場合は、を使用して、 `Measure-Object` 行、単語、および文字の数をカウントすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2ff43-114">For **String** objects, you can also use `Measure-Object` to count the number of lines, words, and characters.</span></span>

## <span data-ttu-id="2ff43-115">例</span><span class="sxs-lookup"><span data-stu-id="2ff43-115">EXAMPLES</span></span>

### <span data-ttu-id="2ff43-116">例 1: ディレクトリ内のファイルとフォルダーの数をカウントする</span><span class="sxs-lookup"><span data-stu-id="2ff43-116">Example 1: Count the files and folders in a directory</span></span>

<span data-ttu-id="2ff43-117">このコマンドは、現在のディレクトリ内のファイルとフォルダーをカウントします。</span><span class="sxs-lookup"><span data-stu-id="2ff43-117">This command counts the files and folders in the current directory.</span></span>

```powershell
Get-ChildItem | Measure-Object
```

### <span data-ttu-id="2ff43-118">例 2: ディレクトリ内のファイルを測定する</span><span class="sxs-lookup"><span data-stu-id="2ff43-118">Example 2: Measure the files in a directory</span></span>

<span data-ttu-id="2ff43-119">このコマンドは、現在のディレクトリにあるすべてのファイルのサイズの **最小値**、 **最大** 値、および **合計** 値と、ディレクトリ内のファイルの平均サイズを表示します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-119">This command displays the **Minimum**, **Maximum**, and **Sum** of the sizes of all files in the current directory, and the average size of a file in the directory.</span></span>

```powershell
Get-ChildItem | Measure-Object -Property length -Minimum -Maximum -Average
```

### <span data-ttu-id="2ff43-120">例 3: テキストファイル内のテキストを測定する</span><span class="sxs-lookup"><span data-stu-id="2ff43-120">Example 3: Measure text in a text file</span></span>

<span data-ttu-id="2ff43-121">このコマンドは、Text.txt ファイル内の文字数、単語数、および行数を表示します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-121">This command displays the number of characters, words, and lines in the Text.txt file.</span></span>
<span data-ttu-id="2ff43-122">**Raw** パラメーターを指定しない場合、は `Get-Content` ファイルを行の配列として出力します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-122">Without the **Raw** parameter, `Get-Content` outputs the file as an array of lines.</span></span>

<span data-ttu-id="2ff43-123">最初のコマンドは、を使用して、 `Set-Content` いくつかの既定のテキストをファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-123">The first command uses `Set-Content` to add some default text to a file.</span></span>

```powershell
"One", "Two", "Three", "Four" | Set-Content -Path C:\Temp\tmp.txt
Get-Content C:\Temp\tmp.txt | Measure-Object -Character -Line -Word
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    4     4         15
```

### <span data-ttu-id="2ff43-124">例 4: 指定されたプロパティを含む Measure オブジェクト</span><span class="sxs-lookup"><span data-stu-id="2ff43-124">Example 4: Measure objects containing a specified Property</span></span>

<span data-ttu-id="2ff43-125">この例では、 **DisplayName** プロパティを持つオブジェクトの数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="2ff43-125">This example counts the number of objects that have a **DisplayName** property.</span></span> <span data-ttu-id="2ff43-126">最初の2つのコマンドは、ローカルコンピューター上のすべてのサービスとプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-126">The first two commands retrieve all the services and processes on the local machine.</span></span> <span data-ttu-id="2ff43-127">3番目のコマンドは、結合されたサービスとプロセスの数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="2ff43-127">The third command counts the combined number of services and processes.</span></span> <span data-ttu-id="2ff43-128">最後のコマンドは、2つのコレクションを結合し、結果をにパイプし `Measure-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="2ff43-128">The last command combines the two collections and pipes the result to `Measure-Object`.</span></span>

<span data-ttu-id="2ff43-129">System.string **オブジェクトに** は **DisplayName** プロパティがないため、最終的なカウントから除外されます。</span><span class="sxs-lookup"><span data-stu-id="2ff43-129">The **System.Diagnostics.Process** object does not have a **DisplayName** property, and is left out of the final count.</span></span>

```powershell
$services = Get-Service
$processes = Get-Process
$services + $processes | Measure-Object
$services + $processes | Measure-Object -Property DisplayName
```

```Output
Count    : 682
Average  :
Sum      :
Maximum  :
Minimum  :
Property :

Count    : 290
Average  :
Sum      :
Maximum  :
Minimum  :
Property : DisplayName
```

### <span data-ttu-id="2ff43-130">例 5: CSV ファイルの内容を測定する</span><span class="sxs-lookup"><span data-stu-id="2ff43-130">Example 5: Measure the contents of a CSV file</span></span>

<span data-ttu-id="2ff43-131">このコマンドは、企業の従業員のサービスの平均年数を計算します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-131">This command calculates the average years of service of the employees of a company.</span></span>

<span data-ttu-id="2ff43-132">この `ServiceYrs.csv` ファイルは、各従業員の従業員番号とサービス年数を含む CSV ファイルです。</span><span class="sxs-lookup"><span data-stu-id="2ff43-132">The `ServiceYrs.csv` file is a CSV file that contains the employee number and years of service of each employee.</span></span> <span data-ttu-id="2ff43-133">テーブルの最初の行は、 **Empno**, **Years** のヘッダー行です。</span><span class="sxs-lookup"><span data-stu-id="2ff43-133">The first row in the table is a header row of **EmpNo**, **Years**.</span></span>

<span data-ttu-id="2ff43-134">を使用してファイルをインポートすると、結果として、 `Import-Csv` **empno** と **Years** の Note プロパティを含む **pscustomobject** 生成されます。</span><span class="sxs-lookup"><span data-stu-id="2ff43-134">When you use `Import-Csv` to import the file, the result is a **PSCustomObject** with note properties of **EmpNo** and **Years**.</span></span>
<span data-ttu-id="2ff43-135">を使用すると `Measure-Object` 、オブジェクトの他のプロパティと同じように、これらのプロパティの値を計算できます。</span><span class="sxs-lookup"><span data-stu-id="2ff43-135">You can use `Measure-Object` to calculate the values of these properties, just like any other property of an object.</span></span>

```powershell
Import-Csv d:\test\serviceyrs.csv | Measure-Object -Property years -Minimum -Maximum -Average
```

### <span data-ttu-id="2ff43-136">例 6: ブール値を測定する</span><span class="sxs-lookup"><span data-stu-id="2ff43-136">Example 6: Measure Boolean values</span></span>

<span data-ttu-id="2ff43-137">この例では、が `Measure-Object` ブール値を測定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-137">This example demonstrates how the `Measure-Object` can measure Boolean values.</span></span>
<span data-ttu-id="2ff43-138">この場合、 **PSIsContainer** の **ブール型** プロパティを使用して、現在のディレクトリ内のフォルダー (またはファイル) の発生を測定します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-138">In this case, it uses the **PSIsContainer** **Boolean** property to measure the incidence of folders (vs. files) in the current directory.</span></span>

```powershell
Get-ChildItem | Measure-Object -Property psiscontainer -Maximum -Sum -Minimum -Average
```

```Output
Count             : 126
Average           : 0.0634920634920635
Sum               : 8
Maximum           : 1
Minimum           : 0
StandardDeviation :
Property          : PSIsContainer
```

### <span data-ttu-id="2ff43-139">例 7: メジャー文字列</span><span class="sxs-lookup"><span data-stu-id="2ff43-139">Example 7: Measure strings</span></span>

<span data-ttu-id="2ff43-140">次の例では、複数の文字列に対して、行の数、1つ目の文字列を測定します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-140">The following example measures the number of lines, first a single string, then across several strings.</span></span> <span data-ttu-id="2ff43-141">改行文字は、 <code>\`n</code> 文字列を複数の行に分割します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-141">The newline character <code>\`n</code> separates strings into multiple lines.</span></span>

```powershell
# The newline character `n separates the string into separate lines, as shown in the output.
"One`nTwo`nThree"
"One`nTwo`nThree" | Measure-Object -Line
```

```Output
One
Two
Three


Lines Words Characters Property
----- ----- ---------- --------
    3
```

```powershell
# The first string counts as a single line.
# The second string is separated into two lines by the newline character.
"One", "Two`nThree" | Measure-Object -Line
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    3
```

```powershell
# The Word switch counts the number of words in each InputObject
# Each InputObject is treated as a single line.
"One, Two", "Three", "Four Five" | Measure-Object -Word -Line
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    3     5
```

### <span data-ttu-id="2ff43-142">例 8: すべての値を測定する</span><span class="sxs-lookup"><span data-stu-id="2ff43-142">Example 8: Measure all the values</span></span>

<span data-ttu-id="2ff43-143">PowerShell 6 以降では、の **Allstats** パラメーターを使用して、 `Measure-Object` すべての統計をまとめて測定できます。</span><span class="sxs-lookup"><span data-stu-id="2ff43-143">Beginning in PowerShell 6, the **AllStats** parameter of `Measure-Object` allows you to measure all the statistics together.</span></span>

```powershell
1..5 | Measure-Object -AllStats
```

```output
Count             : 5
Average           : 3
Sum               : 15
Maximum           : 5
Minimum           : 1
StandardDeviation : 1.58113883008419
Property          :
```

### <span data-ttu-id="2ff43-144">例 9: scriptblock プロパティを使用してメジャーを実行する</span><span class="sxs-lookup"><span data-stu-id="2ff43-144">Example 9: Measure using scriptblock properties</span></span>

<span data-ttu-id="2ff43-145">PowerShell 6 以降では `Measure-Object` 、 **ScriptBlock** プロパティがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2ff43-145">Beginning in PowerShell 6, `Measure-Object` supports **ScriptBlock** properties.</span></span> <span data-ttu-id="2ff43-146">次の例では、 **ScriptBlock** プロパティを使用して、ディレクトリ内のすべてのファイルのサイズを mb 単位で確認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-146">The following example demonstrates how to use a **ScriptBlock** property to determine the size, in MegaBytes, of all the files in a directory.</span></span>

```powershell
Get-ChildItem | Measure-Object -Sum {$_.Length/1MB}
```

### <span data-ttu-id="2ff43-147">例 10: ハッシュテーブルのメジャー</span><span class="sxs-lookup"><span data-stu-id="2ff43-147">Example 10: Measure hashtables</span></span>

<span data-ttu-id="2ff43-148">PowerShell 6 以降では、で `Measure-Object` **ハッシュテーブル** 入力の測定がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2ff43-148">Beginning in PowerShell 6, `Measure-Object` supports measurement of **hashtable** input.</span></span> <span data-ttu-id="2ff43-149">次の例では、 `num` 3 つの **ハッシュテーブル** オブジェクトのキーの最大値を決定します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-149">The following example determines the largest value for the `num` key of 3 **hashtable** objects.</span></span>

```powershell
@{num=3}, @{num=4}, @{num=5} | Measure-Object -Maximum Num
```

```output
Count             : 3
Average           :
Sum               :
Maximum           : 5
Minimum           :
StandardDeviation :
Property          : num
```

### <span data-ttu-id="2ff43-150">例 11: 標準偏差を測定する</span><span class="sxs-lookup"><span data-stu-id="2ff43-150">Example 11: Measure the Standard Deviation</span></span>

<span data-ttu-id="2ff43-151">PowerShell 6 以降では、 `Measure-Object` パラメーターがサポートされてい `-StandardDeviation` ます。</span><span class="sxs-lookup"><span data-stu-id="2ff43-151">Beginning in PowerShell 6, `Measure-Object` supports the `-StandardDeviation` parameter.</span></span> <span data-ttu-id="2ff43-152">次の例では、すべてのプロセスで使用される CPU の *標準偏差* を決定します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-152">The following example determines the *standard deviation* for the CPU used by all processes.</span></span> <span data-ttu-id="2ff43-153">大きな偏差は、CPU を大量に消費しているプロセスの数が少ないことを示します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-153">A large deviation would indicate a small number of processes consuming the most CPU.</span></span>

```powershell
Get-Process | Measure-Object -Average -StandardDeviation CPU
```

```output
Count             : 303
Average           : 163.032384488449
Sum               :
Maximum           :
Minimum           :
StandardDeviation : 859.444048419069
Property          : CPU
```

### <span data-ttu-id="2ff43-154">例 12: ワイルドカードを使用してメジャーを使用する</span><span class="sxs-lookup"><span data-stu-id="2ff43-154">Example 12: Measure using wildcards</span></span>

<span data-ttu-id="2ff43-155">PowerShell 6 以降、では、 `Measure-Object` プロパティ名にワイルドカードを使用して、オブジェクトの測定をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2ff43-155">Beginning in PowerShell 6, `Measure-Object` supports measurement of objects by using wildcards in property names.</span></span> <span data-ttu-id="2ff43-156">次の例では、一連のプロセスのページメモリ使用量の最大値を決定します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-156">The following example determines the maximum of any type of paged memory usage among a set of processes.</span></span>

```powershell
Get-Process | Measure-Object -Maximum *paged*memory*size
```

```output
Count             : 303
Average           :
Sum               :
Maximum           : 735784
Minimum           :
StandardDeviation :
Property          : NonpagedSystemMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 352104448
Minimum           :
StandardDeviation :
Property          : PagedMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 2201968
Minimum           :
StandardDeviation :
Property          : PagedSystemMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 719032320
Minimum           :
StandardDeviation :
Property          : PeakPagedMemorySize
```

## <span data-ttu-id="2ff43-157">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2ff43-157">PARAMETERS</span></span>

### <span data-ttu-id="2ff43-158">-平均</span><span class="sxs-lookup"><span data-stu-id="2ff43-158">-Average</span></span>

<span data-ttu-id="2ff43-159">コマンドレットによって、指定されたプロパティの平均値が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-159">Indicates that the cmdlet displays the average value of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ff43-160">-文字</span><span class="sxs-lookup"><span data-stu-id="2ff43-160">-Character</span></span>

<span data-ttu-id="2ff43-161">コマンドレットが入力オブジェクトの文字数をカウントすることを示します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-161">Indicates that the cmdlet counts the number of characters in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="2ff43-162">*各入力* オブジェクトと入力オブジェクトの *間* で、 **Word**、 **Char** 、および **Line** スイッチがカウントされます。</span><span class="sxs-lookup"><span data-stu-id="2ff43-162">The **Word**, **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="2ff43-163">例7を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ff43-163">See Example 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ff43-164">-IgnoreWhiteSpace</span><span class="sxs-lookup"><span data-stu-id="2ff43-164">-IgnoreWhiteSpace</span></span>

<span data-ttu-id="2ff43-165">コマンドレットが文字数の空白を無視することを示します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-165">Indicates that the cmdlet ignores white space in character counts.</span></span>
<span data-ttu-id="2ff43-166">既定では、空白は無視されません。</span><span class="sxs-lookup"><span data-stu-id="2ff43-166">By default, white space is not ignored.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ff43-167">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2ff43-167">-InputObject</span></span>

<span data-ttu-id="2ff43-168">測定するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-168">Specifies the objects to be measured.</span></span>
<span data-ttu-id="2ff43-169">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-169">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="2ff43-170">で **inputobject** パラメーターを使用すると、 `Measure-Object` コマンドの結果をにパイプするのではなく、 `Measure-Object` **inputobject** 値が1つのオブジェクトとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="2ff43-170">When you use the **InputObject** parameter with `Measure-Object`, instead of piping command results to `Measure-Object`, the **InputObject** value is treated as a single object.</span></span>

<span data-ttu-id="2ff43-171">オブジェクトが `Measure-Object` 定義されたプロパティに特定の値を持つかどうかに基づいてオブジェクトのコレクションを測定する場合は、パイプラインでを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2ff43-171">It is recommended that you use `Measure-Object` in the pipeline if you want to measure a collection of objects based on whether the objects have specific values in defined properties.</span></span>

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

### <span data-ttu-id="2ff43-172">-Line</span><span class="sxs-lookup"><span data-stu-id="2ff43-172">-Line</span></span>

<span data-ttu-id="2ff43-173">コマンドレットによって入力オブジェクトの行数がカウントされることを示します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-173">Indicates that the cmdlet counts the number of lines in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="2ff43-174">*各入力* オブジェクトと入力オブジェクトの *間* で、 **Word**、 **Char** 、および **Line** スイッチがカウントされます。</span><span class="sxs-lookup"><span data-stu-id="2ff43-174">The **Word**, **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="2ff43-175">例7を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ff43-175">See Example 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ff43-176">-最大</span><span class="sxs-lookup"><span data-stu-id="2ff43-176">-Maximum</span></span>

<span data-ttu-id="2ff43-177">コマンドレットによって、指定されたプロパティの最大値が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-177">Indicates that the cmdlet displays the maximum value of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ff43-178">-最小</span><span class="sxs-lookup"><span data-stu-id="2ff43-178">-Minimum</span></span>

<span data-ttu-id="2ff43-179">コマンドレットによって、指定されたプロパティの最小値が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-179">Indicates that the cmdlet displays the minimum value of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ff43-180">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="2ff43-180">-Property</span></span>

<span data-ttu-id="2ff43-181">測定する1つ以上のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-181">Specifies one or more properties to measure.</span></span> <span data-ttu-id="2ff43-182">他のメジャーを指定しない場合は、によって、指定した `Measure-Object` プロパティを持つオブジェクトがカウントされます。</span><span class="sxs-lookup"><span data-stu-id="2ff43-182">If you do not specify any other measures, `Measure-Object` counts the objects that have the properties you specify.</span></span>

<span data-ttu-id="2ff43-183">**Property** パラメーターの値には、新しい集計プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2ff43-183">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="2ff43-184">計算されるプロパティは、スクリプトブロックである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ff43-184">The calculated property must be a script block.</span></span> <span data-ttu-id="2ff43-185">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ff43-185">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.PSPropertyExpression[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="2ff43-186">-StandardDeviation</span><span class="sxs-lookup"><span data-stu-id="2ff43-186">-StandardDeviation</span></span>

<span data-ttu-id="2ff43-187">コマンドレットによって、指定されたプロパティの値の標準偏差が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-187">Indicates that the cmdlet displays the standard deviation of the values of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ff43-188">-Sum</span><span class="sxs-lookup"><span data-stu-id="2ff43-188">-Sum</span></span>

<span data-ttu-id="2ff43-189">コマンドレットによって、指定されたプロパティの値の合計が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-189">Indicates that the cmdlet displays the sum of the values of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ff43-190">-AllStats</span><span class="sxs-lookup"><span data-stu-id="2ff43-190">-AllStats</span></span>

<span data-ttu-id="2ff43-191">コマンドレットによって、指定されたプロパティのすべての統計が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-191">Indicates that the cmdlet displays all the statistics of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ff43-192">-Word</span><span class="sxs-lookup"><span data-stu-id="2ff43-192">-Word</span></span>

<span data-ttu-id="2ff43-193">コマンドレットによって入力オブジェクト内の単語数がカウントされることを示します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-193">Indicates that the cmdlet counts the number of words in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="2ff43-194">*各入力* オブジェクトと入力オブジェクトの *間* で、 **Word**、 **Char** 、および **Line** スイッチがカウントされます。</span><span class="sxs-lookup"><span data-stu-id="2ff43-194">The **Word**, **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="2ff43-195">例7を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ff43-195">See Example 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ff43-196">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2ff43-196">CommonParameters</span></span>

<span data-ttu-id="2ff43-197">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2ff43-197">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2ff43-198">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ff43-198">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2ff43-199">入力</span><span class="sxs-lookup"><span data-stu-id="2ff43-199">INPUTS</span></span>

### <span data-ttu-id="2ff43-200">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="2ff43-200">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="2ff43-201">パイプを使用してオブジェクトをにパイプ処理でき `Measure-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="2ff43-201">You can pipe objects to `Measure-Object`.</span></span>

## <span data-ttu-id="2ff43-202">出力</span><span class="sxs-lookup"><span data-stu-id="2ff43-202">OUTPUTS</span></span>

### <span data-ttu-id="2ff43-203">Microsoft. PowerShell. GenericMeasureInfo</span><span class="sxs-lookup"><span data-stu-id="2ff43-203">Microsoft.PowerShell.Commands.GenericMeasureInfo</span></span>

### <span data-ttu-id="2ff43-204">Microsoft. PowerShell. TextMeasureInfo</span><span class="sxs-lookup"><span data-stu-id="2ff43-204">Microsoft.PowerShell.Commands.TextMeasureInfo</span></span>

<span data-ttu-id="2ff43-205">**Word** パラメーターを使用すると、は `Measure-Object` **textmeasureinfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-205">If you use the **Word** parameter, `Measure-Object` returns a **TextMeasureInfo** object.</span></span>
<span data-ttu-id="2ff43-206">それ以外の場合は、 **Genericmeasureinfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="2ff43-206">Otherwise, it returns a **GenericMeasureInfo** object.</span></span>

## <span data-ttu-id="2ff43-207">注</span><span class="sxs-lookup"><span data-stu-id="2ff43-207">NOTES</span></span>

## <span data-ttu-id="2ff43-208">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2ff43-208">RELATED LINKS</span></span>

[<span data-ttu-id="2ff43-209">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="2ff43-209">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="2ff43-210">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="2ff43-210">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="2ff43-211">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="2ff43-211">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="2ff43-212">Group-Object</span><span class="sxs-lookup"><span data-stu-id="2ff43-212">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="2ff43-213">New-Object</span><span class="sxs-lookup"><span data-stu-id="2ff43-213">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="2ff43-214">Select-Object</span><span class="sxs-lookup"><span data-stu-id="2ff43-214">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="2ff43-215">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="2ff43-215">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="2ff43-216">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="2ff43-216">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="2ff43-217">Where-Object</span><span class="sxs-lookup"><span data-stu-id="2ff43-217">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
