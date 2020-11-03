---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Object
ms.openlocfilehash: 5d4a27f1a1949056ca63b9b6a2340bf1226592e0
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219216"
---
# <span data-ttu-id="7d51a-103">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="7d51a-103">Measure-Object</span></span>

## <span data-ttu-id="7d51a-104">概要</span><span class="sxs-lookup"><span data-stu-id="7d51a-104">SYNOPSIS</span></span>
<span data-ttu-id="7d51a-105">オブジェクトの数値プロパティと、テキストのファイルなど文字列オブジェクト内の文字、単語、および行を計算します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-105">Calculates the numeric properties of objects, and the characters, words, and lines in string objects, such as files of text.</span></span>

## <span data-ttu-id="7d51a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7d51a-106">SYNTAX</span></span>

### <span data-ttu-id="7d51a-107">GenericMeasure (既定値)</span><span class="sxs-lookup"><span data-stu-id="7d51a-107">GenericMeasure (Default)</span></span>

```
Measure-Object [-InputObject <PSObject>] [[-Property] <String[]>] [-Sum] [-Average] [-Maximum] [-Minimum]
 [<CommonParameters>]
```

### <span data-ttu-id="7d51a-108">TextMeasure</span><span class="sxs-lookup"><span data-stu-id="7d51a-108">TextMeasure</span></span>

```
Measure-Object [-InputObject <PSObject>] [[-Property] <String[]>] [-Line] [-Word] [-Character]
 [-IgnoreWhiteSpace] [<CommonParameters>]
```

## <span data-ttu-id="7d51a-109">Description</span><span class="sxs-lookup"><span data-stu-id="7d51a-109">DESCRIPTION</span></span>

<span data-ttu-id="7d51a-110">コマンドレットでは、 `Measure-Object` 特定の種類のオブジェクトのプロパティ値を計算します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-110">The `Measure-Object` cmdlet calculates the property values of certain types of object.</span></span>
<span data-ttu-id="7d51a-111">`Measure-Object` コマンド内のパラメーターに応じて、3種類の測定を実行します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-111">`Measure-Object` performs three types of measurements, depending on the parameters in the command.</span></span>

<span data-ttu-id="7d51a-112">コマンドレットでは、 `Measure-Object` オブジェクトのプロパティ値に対して計算を実行します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-112">The `Measure-Object` cmdlet performs calculations on the property values of objects.</span></span> <span data-ttu-id="7d51a-113">を使用すると、 `Measure-Object` オブジェクトをカウントしたり、指定した **プロパティ** を使用してオブジェクトをカウントしたりできます。</span><span class="sxs-lookup"><span data-stu-id="7d51a-113">You can use `Measure-Object` to count objects or count objects with a specified **Property**.</span></span> <span data-ttu-id="7d51a-114">また、を使用して、 `Measure-Object` 数値の **最小** 値、 **最大** 値、 **合計** 、 **標準偏差** 、 **平均** を計算することもできます。</span><span class="sxs-lookup"><span data-stu-id="7d51a-114">You can also use `Measure-Object` to calculate the **Minimum** , **Maximum** , **Sum** , **StandardDeviation** and **Average** of numeric values.</span></span> <span data-ttu-id="7d51a-115">**文字列** オブジェクトの場合は、を使用して、 `Measure-Object` 行、単語、および文字の数をカウントすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7d51a-115">For **String** objects, you can also use `Measure-Object` to count the number of lines, words, and characters.</span></span>

## <span data-ttu-id="7d51a-116">例</span><span class="sxs-lookup"><span data-stu-id="7d51a-116">EXAMPLES</span></span>

### <span data-ttu-id="7d51a-117">例 1: ディレクトリ内のファイルとフォルダーの数をカウントする</span><span class="sxs-lookup"><span data-stu-id="7d51a-117">Example 1: Count the files and folders in a directory</span></span>

<span data-ttu-id="7d51a-118">このコマンドは、現在のディレクトリ内のファイルとフォルダーをカウントします。</span><span class="sxs-lookup"><span data-stu-id="7d51a-118">This command counts the files and folders in the current directory.</span></span>

```powershell
Get-ChildItem | Measure-Object
```

### <span data-ttu-id="7d51a-119">例 2: ディレクトリ内のファイルを測定する</span><span class="sxs-lookup"><span data-stu-id="7d51a-119">Example 2: Measure the files in a directory</span></span>

<span data-ttu-id="7d51a-120">このコマンドは、現在のディレクトリにあるすべてのファイルのサイズの **最小値** 、 **最大** 値、および **合計** 値と、ディレクトリ内のファイルの平均サイズを表示します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-120">This command displays the **Minimum** , **Maximum** , and **Sum** of the sizes of all files in the current directory, and the average size of a file in the directory.</span></span>

```powershell
Get-ChildItem | Measure-Object -Property length -Minimum -Maximum -Average
```

### <span data-ttu-id="7d51a-121">例 3: テキストファイル内のテキストを測定する</span><span class="sxs-lookup"><span data-stu-id="7d51a-121">Example 3: Measure text in a text file</span></span>

<span data-ttu-id="7d51a-122">このコマンドは、Text.txt ファイル内の文字数、単語数、および行数を表示します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-122">This command displays the number of characters, words, and lines in the Text.txt file.</span></span>
<span data-ttu-id="7d51a-123">**Raw** パラメーターを指定しない場合、は `Get-Content` ファイルを行の配列として出力します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-123">Without the **Raw** parameter, `Get-Content` outputs the file as an array of lines.</span></span>

<span data-ttu-id="7d51a-124">最初のコマンドは、を使用して、 `Set-Content` いくつかの既定のテキストをファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-124">The first command uses `Set-Content` to add some default text to a file.</span></span>

```powershell
"One", "Two", "Three", "Four" | Set-Content -Path C:\Temp\tmp.txt
Get-Content C:\Temp\tmp.txt | Measure-Object -Character -Line -Word
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    4     4         15
```

### <span data-ttu-id="7d51a-125">例 4: 指定されたプロパティを含む Measure オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7d51a-125">Example 4: Measure objects containing a specified Property</span></span>

<span data-ttu-id="7d51a-126">この例では、 **DisplayName** プロパティを持つオブジェクトの数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="7d51a-126">This example counts the number of objects that have a **DisplayName** property.</span></span> <span data-ttu-id="7d51a-127">最初の2つのコマンドは、ローカルコンピューター上のすべてのサービスとプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-127">The first two commands retrieve all the services and processes on the local machine.</span></span> <span data-ttu-id="7d51a-128">3番目のコマンドは、結合されたサービスとプロセスの数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="7d51a-128">The third command counts the combined number of services and processes.</span></span> <span data-ttu-id="7d51a-129">最後のコマンドは、2つのコレクションを結合し、結果をにパイプし `Measure-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="7d51a-129">The last command combines the two collections and pipes the result to `Measure-Object`.</span></span>

<span data-ttu-id="7d51a-130">System.string **オブジェクトに** は **DisplayName** プロパティがないため、最終的なカウントから除外されます。</span><span class="sxs-lookup"><span data-stu-id="7d51a-130">The **System.Diagnostics.Process** object does not have a **DisplayName** property, and is left out of the final count.</span></span>

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

### <span data-ttu-id="7d51a-131">例 5: CSV ファイルの内容を測定する</span><span class="sxs-lookup"><span data-stu-id="7d51a-131">Example 5: Measure the contents of a CSV file</span></span>

<span data-ttu-id="7d51a-132">このコマンドは、企業の従業員のサービスの平均年数を計算します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-132">This command calculates the average years of service of the employees of a company.</span></span>

<span data-ttu-id="7d51a-133">この `ServiceYrs.csv` ファイルは、各従業員の従業員番号とサービス年数を含む CSV ファイルです。</span><span class="sxs-lookup"><span data-stu-id="7d51a-133">The `ServiceYrs.csv` file is a CSV file that contains the employee number and years of service of each employee.</span></span> <span data-ttu-id="7d51a-134">テーブルの最初の行は、 **Empno** , **Years** のヘッダー行です。</span><span class="sxs-lookup"><span data-stu-id="7d51a-134">The first row in the table is a header row of **EmpNo** , **Years**.</span></span>

<span data-ttu-id="7d51a-135">を使用してファイルをインポートすると、結果として、 `Import-Csv` **empno** と **Years** の Note プロパティを含む **pscustomobject** 生成されます。</span><span class="sxs-lookup"><span data-stu-id="7d51a-135">When you use `Import-Csv` to import the file, the result is a **PSCustomObject** with note properties of **EmpNo** and **Years**.</span></span>
<span data-ttu-id="7d51a-136">を使用すると `Measure-Object` 、オブジェクトの他のプロパティと同じように、これらのプロパティの値を計算できます。</span><span class="sxs-lookup"><span data-stu-id="7d51a-136">You can use `Measure-Object` to calculate the values of these properties, just like any other property of an object.</span></span>

```powershell
Import-Csv d:\test\serviceyrs.csv | Measure-Object -Property years -Minimum -Maximum -Average
```

### <span data-ttu-id="7d51a-137">例 6: ブール値を測定する</span><span class="sxs-lookup"><span data-stu-id="7d51a-137">Example 6: Measure Boolean values</span></span>

<span data-ttu-id="7d51a-138">この例では、が `Measure-Object` ブール値を測定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-138">This example demonstrates how the `Measure-Object` can measure Boolean values.</span></span>
<span data-ttu-id="7d51a-139">この場合、 **PSIsContainer** の **ブール型** プロパティを使用して、現在のディレクトリ内のフォルダー (またはファイル) の発生を測定します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-139">In this case, it uses the **PSIsContainer** **Boolean** property to measure the incidence of folders (vs. files) in the current directory.</span></span>

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

### <span data-ttu-id="7d51a-140">例 7: メジャー文字列</span><span class="sxs-lookup"><span data-stu-id="7d51a-140">Example 7: Measure strings</span></span>

<span data-ttu-id="7d51a-141">次の例では、複数の文字列に対して、行の数、1つ目の文字列を測定します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-141">The following example measures the number of lines, first a single string, then across several strings.</span></span> <span data-ttu-id="7d51a-142">改行文字は、 <code>\`n</code> 文字列を複数の行に分割します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-142">The newline character <code>\`n</code> separates strings into multiple lines.</span></span>

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

## <span data-ttu-id="7d51a-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7d51a-143">PARAMETERS</span></span>

### <span data-ttu-id="7d51a-144">-平均</span><span class="sxs-lookup"><span data-stu-id="7d51a-144">-Average</span></span>

<span data-ttu-id="7d51a-145">コマンドレットによって、指定されたプロパティの平均値が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-145">Indicates that the cmdlet displays the average value of the specified properties.</span></span>

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

### <span data-ttu-id="7d51a-146">-文字</span><span class="sxs-lookup"><span data-stu-id="7d51a-146">-Character</span></span>

<span data-ttu-id="7d51a-147">コマンドレットが入力オブジェクトの文字数をカウントすることを示します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-147">Indicates that the cmdlet counts the number of characters in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="7d51a-148">*各入力* オブジェクトと入力オブジェクトの *間* で、 **Word** 、 **Char** 、および **Line** スイッチがカウントされます。</span><span class="sxs-lookup"><span data-stu-id="7d51a-148">The **Word** , **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="7d51a-149">例7を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d51a-149">See Example 7.</span></span>

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

### <span data-ttu-id="7d51a-150">-IgnoreWhiteSpace</span><span class="sxs-lookup"><span data-stu-id="7d51a-150">-IgnoreWhiteSpace</span></span>

<span data-ttu-id="7d51a-151">コマンドレットが文字数の空白を無視することを示します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-151">Indicates that the cmdlet ignores white space in character counts.</span></span>
<span data-ttu-id="7d51a-152">既定では、空白は無視されません。</span><span class="sxs-lookup"><span data-stu-id="7d51a-152">By default, white space is not ignored.</span></span>

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

### <span data-ttu-id="7d51a-153">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7d51a-153">-InputObject</span></span>

<span data-ttu-id="7d51a-154">測定するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-154">Specifies the objects to be measured.</span></span>
<span data-ttu-id="7d51a-155">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-155">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="7d51a-156">で **inputobject** パラメーターを使用すると、 `Measure-Object` コマンドの結果をにパイプするのではなく、 `Measure-Object` **inputobject** 値が1つのオブジェクトとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="7d51a-156">When you use the **InputObject** parameter with `Measure-Object`, instead of piping command results to `Measure-Object`, the **InputObject** value is treated as a single object.</span></span>

<span data-ttu-id="7d51a-157">オブジェクトが `Measure-Object` 定義されたプロパティに特定の値を持つかどうかに基づいてオブジェクトのコレクションを測定する場合は、パイプラインでを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7d51a-157">It is recommended that you use `Measure-Object` in the pipeline if you want to measure a collection of objects based on whether the objects have specific values in defined properties.</span></span>

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

### <span data-ttu-id="7d51a-158">-Line</span><span class="sxs-lookup"><span data-stu-id="7d51a-158">-Line</span></span>

<span data-ttu-id="7d51a-159">コマンドレットによって入力オブジェクトの行数がカウントされることを示します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-159">Indicates that the cmdlet counts the number of lines in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="7d51a-160">*各入力* オブジェクトと入力オブジェクトの *間* で、 **Word** 、 **Char** 、および **Line** スイッチがカウントされます。</span><span class="sxs-lookup"><span data-stu-id="7d51a-160">The **Word** , **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="7d51a-161">例7を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d51a-161">See Example 7.</span></span>

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

### <span data-ttu-id="7d51a-162">-最大</span><span class="sxs-lookup"><span data-stu-id="7d51a-162">-Maximum</span></span>

<span data-ttu-id="7d51a-163">コマンドレットによって、指定されたプロパティの最大値が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-163">Indicates that the cmdlet displays the maximum value of the specified properties.</span></span>

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

### <span data-ttu-id="7d51a-164">-最小</span><span class="sxs-lookup"><span data-stu-id="7d51a-164">-Minimum</span></span>

<span data-ttu-id="7d51a-165">コマンドレットによって、指定されたプロパティの最小値が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-165">Indicates that the cmdlet displays the minimum value of the specified properties.</span></span>

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

### <span data-ttu-id="7d51a-166">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="7d51a-166">-Property</span></span>

<span data-ttu-id="7d51a-167">測定する1つ以上のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-167">Specifies one or more properties to measure.</span></span> <span data-ttu-id="7d51a-168">他のメジャーを指定しない場合は、によって、指定した `Measure-Object` プロパティを持つオブジェクトがカウントされます。</span><span class="sxs-lookup"><span data-stu-id="7d51a-168">If you do not specify any other measures, `Measure-Object` counts the objects that have the properties you specify.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="7d51a-169">-Sum</span><span class="sxs-lookup"><span data-stu-id="7d51a-169">-Sum</span></span>

<span data-ttu-id="7d51a-170">コマンドレットによって、指定されたプロパティの値の合計が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-170">Indicates that the cmdlet displays the sum of the values of the specified properties.</span></span>

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

### <span data-ttu-id="7d51a-171">-Word</span><span class="sxs-lookup"><span data-stu-id="7d51a-171">-Word</span></span>

<span data-ttu-id="7d51a-172">コマンドレットによって入力オブジェクト内の単語数がカウントされることを示します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-172">Indicates that the cmdlet counts the number of words in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="7d51a-173">*各入力* オブジェクトと入力オブジェクトの *間* で、 **Word** 、 **Char** 、および **Line** スイッチがカウントされます。</span><span class="sxs-lookup"><span data-stu-id="7d51a-173">The **Word** , **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="7d51a-174">例7を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d51a-174">See Example 7.</span></span>

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

### <span data-ttu-id="7d51a-175">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7d51a-175">CommonParameters</span></span>

<span data-ttu-id="7d51a-176">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="7d51a-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7d51a-177">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d51a-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7d51a-178">入力</span><span class="sxs-lookup"><span data-stu-id="7d51a-178">INPUTS</span></span>

### <span data-ttu-id="7d51a-179">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="7d51a-179">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="7d51a-180">パイプを使用してオブジェクトをにパイプ処理でき `Measure-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="7d51a-180">You can pipe objects to `Measure-Object`.</span></span>

## <span data-ttu-id="7d51a-181">出力</span><span class="sxs-lookup"><span data-stu-id="7d51a-181">OUTPUTS</span></span>

### <span data-ttu-id="7d51a-182">Microsoft. PowerShell. GenericMeasureInfo</span><span class="sxs-lookup"><span data-stu-id="7d51a-182">Microsoft.PowerShell.Commands.GenericMeasureInfo</span></span>

### <span data-ttu-id="7d51a-183">Microsoft. PowerShell. TextMeasureInfo</span><span class="sxs-lookup"><span data-stu-id="7d51a-183">Microsoft.PowerShell.Commands.TextMeasureInfo</span></span>

<span data-ttu-id="7d51a-184">**Word** パラメーターを使用すると、は `Measure-Object` **textmeasureinfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-184">If you use the **Word** parameter, `Measure-Object` returns a **TextMeasureInfo** object.</span></span>
<span data-ttu-id="7d51a-185">それ以外の場合は、 **Genericmeasureinfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7d51a-185">Otherwise, it returns a **GenericMeasureInfo** object.</span></span>

## <span data-ttu-id="7d51a-186">注</span><span class="sxs-lookup"><span data-stu-id="7d51a-186">NOTES</span></span>

## <span data-ttu-id="7d51a-187">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7d51a-187">RELATED LINKS</span></span>

[<span data-ttu-id="7d51a-188">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="7d51a-188">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="7d51a-189">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="7d51a-189">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="7d51a-190">Group-Object</span><span class="sxs-lookup"><span data-stu-id="7d51a-190">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="7d51a-191">New-Object</span><span class="sxs-lookup"><span data-stu-id="7d51a-191">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="7d51a-192">Select-Object</span><span class="sxs-lookup"><span data-stu-id="7d51a-192">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="7d51a-193">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="7d51a-193">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="7d51a-194">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="7d51a-194">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="7d51a-195">Where-Object</span><span class="sxs-lookup"><span data-stu-id="7d51a-195">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
