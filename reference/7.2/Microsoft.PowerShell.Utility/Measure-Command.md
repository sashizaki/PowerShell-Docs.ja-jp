---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-command?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Command
ms.openlocfilehash: 0c2346dc7177e091c0921cd4775422938305e2be
ms.sourcegitcommit: 165d10405d9db3a68c417a239d3181378fd02b9b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "99599909"
---
# <span data-ttu-id="c5886-102">Measure-Command</span><span class="sxs-lookup"><span data-stu-id="c5886-102">Measure-Command</span></span>

## <span data-ttu-id="c5886-103">概要</span><span class="sxs-lookup"><span data-stu-id="c5886-103">SYNOPSIS</span></span>
<span data-ttu-id="c5886-104">スクリプト ブロックとコマンドレットの実行に要する時間を計測します。</span><span class="sxs-lookup"><span data-stu-id="c5886-104">Measures the time it takes to run script blocks and cmdlets.</span></span>

## <span data-ttu-id="c5886-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c5886-105">SYNTAX</span></span>

```
Measure-Command [-InputObject <PSObject>] [-Expression] <ScriptBlock> [<CommonParameters>]
```

## <span data-ttu-id="c5886-106">Description</span><span class="sxs-lookup"><span data-stu-id="c5886-106">DESCRIPTION</span></span>

<span data-ttu-id="c5886-107">コマンドレットでは、 `Measure-Command` スクリプトブロックまたはコマンドレットを内部で実行し、操作の実行時間を指定して、実行時間を返します。</span><span class="sxs-lookup"><span data-stu-id="c5886-107">The `Measure-Command` cmdlet runs a script block or cmdlet internally, times the execution of the operation, and returns the execution time.</span></span>

> [!NOTE]
> <span data-ttu-id="c5886-108">スクリプトブロックは、 `Measure-Command` 子スコープではなく、現在のスコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="c5886-108">Script blocks run by `Measure-Command` run in the current scope, not a child scope.</span></span>

## <span data-ttu-id="c5886-109">例</span><span class="sxs-lookup"><span data-stu-id="c5886-109">EXAMPLES</span></span>

### <span data-ttu-id="c5886-110">例 1: コマンドを測定する</span><span class="sxs-lookup"><span data-stu-id="c5886-110">Example 1: Measure a command</span></span>

<span data-ttu-id="c5886-111">この例では、 `Get-EventLog` Windows PowerShell イベントログ内のイベントを取得するコマンドの実行にかかる時間を計測します。</span><span class="sxs-lookup"><span data-stu-id="c5886-111">This example measures the time it takes to run a `Get-EventLog` command that gets the events in the Windows PowerShell event log.</span></span>

```powershell
Measure-Command { Get-EventLog "windows powershell" }
```

### <span data-ttu-id="c5886-112">例 2: Measure-Command の2つの出力を比較する</span><span class="sxs-lookup"><span data-stu-id="c5886-112">Example 2: Compare two outputs from Measure-Command</span></span>

<span data-ttu-id="c5886-113">最初のコマンドは、 `Get-ChildItem` **Path** パラメーターを使用して `.txt` `C:\Windows` ディレクトリとそのサブディレクトリ内のファイルのみを取得する再帰コマンドを処理するためにかかる時間を計測します。</span><span class="sxs-lookup"><span data-stu-id="c5886-113">The first command measures the time it takes to process a recursive `Get-ChildItem` command that uses the **Path** parameter to get only `.txt` files in the `C:\Windows` directory and its subdirectories.</span></span>

<span data-ttu-id="c5886-114">2番目のコマンドは、プロバイダー固有の ' パラメーターを使用する再帰コマンドの処理にかかる時間を測定し `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="c5886-114">The second command measures the time it takes to process a recursive `Get-ChildItem` command that uses the provider-specific \` parameter.</span></span>

<span data-ttu-id="c5886-115">これらのコマンドは、PowerShell コマンドでプロバイダー固有のフィルターを使用した値を表示します。</span><span class="sxs-lookup"><span data-stu-id="c5886-115">These commands show the value of using a provider-specific filter in PowerShell commands.</span></span>

```powershell
Measure-Command { Get-ChildItem -Path C:\Windows\*.txt -Recurse }
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 8
Milliseconds      : 618
Ticks             : 86182763
TotalDays         : 9.9748568287037E-05
TotalHours        : 0.00239396563888889
TotalMinutes      : 0.143637938333333
TotalSeconds      : 8.6182763
TotalMilliseconds : 8618.2763
```

```powershell
Measure-Command {Get-ChildItem C:\Windows -Filter "*.txt" -Recurse}
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 1
Milliseconds      : 140
Ticks             : 11409189
TotalDays         : 1.32050798611111E-05
TotalHours        : 0.000316921916666667
TotalMinutes      : 0.019015315
TotalSeconds      : 1.1409189
TotalMilliseconds : 1140.9189
```

### <span data-ttu-id="c5886-116">例 3: 入力を Measure-Command にパイプする</span><span class="sxs-lookup"><span data-stu-id="c5886-116">Example 3: Piping input to Measure-Command</span></span>

<span data-ttu-id="c5886-117">パイプ処理されたオブジェクト `Measure-Command` は、 **Expression** パラメーターに渡されるスクリプトブロックで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5886-117">Objects that are piped to `Measure-Command` are available to the script block that is passed to the **Expression** parameter.</span></span> <span data-ttu-id="c5886-118">スクリプトブロックは、パイプラインのオブジェクトごとに1回実行されます。</span><span class="sxs-lookup"><span data-stu-id="c5886-118">The script block is executed once for each object on the pipeline.</span></span>

```powershell
# Perform a simple operation to demonstrate the InputObject parameter
# Note that no output is displayed.
10, 20, 50 | Measure-Command -Expression { for ($i=0; $i -lt $_; $i++) {$i} }
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 12
Ticks             : 122672
TotalDays         : 1.41981481481481E-07
TotalHours        : 3.40755555555556E-06
TotalMinutes      : 0.000204453333333333
TotalSeconds      : 0.0122672
TotalMilliseconds : 12.2672
```

### <span data-ttu-id="c5886-119">例 4: 測定されたコマンドの出力を表示する</span><span class="sxs-lookup"><span data-stu-id="c5886-119">Example 4: Displaying output of measured command</span></span>

<span data-ttu-id="c5886-120">に式の出力を表示するに `Measure-Command` は、パイプを使用し `Out-Default` ます。</span><span class="sxs-lookup"><span data-stu-id="c5886-120">To display output of expression in `Measure-Command` you can use a pipe to `Out-Default`.</span></span>

```powershell
# Perform the same operation as above adding Out-Default to every execution.
# This will show that the ScriptBlock is in fact executing for every item.
10, 20, 50 | Measure-Command -Expression {for ($i=0; $i -lt $_; $i++) {$i}; "$($_)" | Out-Default }
```

```Output
10
20
50


Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 11
Ticks             : 113745
TotalDays         : 1.31649305555556E-07
TotalHours        : 3.15958333333333E-06
TotalMinutes      : 0.000189575
TotalSeconds      : 0.0113745
TotalMilliseconds : 11.3745
```

### <span data-ttu-id="c5886-121">例 5: 子スコープで実行を測定する</span><span class="sxs-lookup"><span data-stu-id="c5886-121">Example 5: Measuring execution in a child scope</span></span>

<span data-ttu-id="c5886-122">`Measure-Command` 現在のスコープでスクリプトブロックを実行します。これにより、スクリプトブロックは現在のスコープ内の値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c5886-122">`Measure-Command` runs the script block in the current scope, so the script block can modify values in the current scope.</span></span> <span data-ttu-id="c5886-123">現在のスコープが変更されないようにするには、スクリプトブロックを中かっこ () で囲み、 `{}` 呼び出し演算子 () を使用して `&` 子スコープでブロックを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5886-123">To avoid changes to the current scope, you must wrap the script block in braces (`{}`) and use the invocation operator (`&`) to execute the block in a child scope.</span></span>

```powershell
$foo = 'Value 1'
$null = Measure-Command { $foo = 'Value 2' }
$foo
$null = Measure-Command { & { $foo = 'Value 3' } }
$foo
```

```Output
Value 2
Value 2
```

<span data-ttu-id="c5886-124">呼び出し演算子の詳細については、「 [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md#call-operator-)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5886-124">For more information about the invocation operator, see [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md#call-operator-).</span></span>

## <span data-ttu-id="c5886-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c5886-125">PARAMETERS</span></span>

### <span data-ttu-id="c5886-126">-式</span><span class="sxs-lookup"><span data-stu-id="c5886-126">-Expression</span></span>

<span data-ttu-id="c5886-127">時間の計測する式を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5886-127">Specifies the expression that is being timed.</span></span> <span data-ttu-id="c5886-128">式を中かっこ () で囲み `{}` ます。</span><span class="sxs-lookup"><span data-stu-id="c5886-128">Enclose the expression in braces (`{}`).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c5886-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c5886-129">-InputObject</span></span>

<span data-ttu-id="c5886-130">**InputObject** パラメーターにバインドされたオブジェクトは、 **Expression** パラメーターに渡されるスクリプトブロックに対する省略可能な入力です。</span><span class="sxs-lookup"><span data-stu-id="c5886-130">Objects bound to the **InputObject** parameter are optional input for the script block passed to the **Expression** parameter.</span></span> <span data-ttu-id="c5886-131">スクリプトブロック内では、を使用して、 `$_` パイプライン内の現在のオブジェクトを参照できます。</span><span class="sxs-lookup"><span data-stu-id="c5886-131">Inside the script block, `$_` can be used to reference the current object in the pipeline.</span></span>

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

### <span data-ttu-id="c5886-132">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c5886-132">CommonParameters</span></span>

<span data-ttu-id="c5886-133">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c5886-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c5886-134">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5886-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c5886-135">入力</span><span class="sxs-lookup"><span data-stu-id="c5886-135">INPUTS</span></span>

### <span data-ttu-id="c5886-136">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="c5886-136">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="c5886-137">パイプを使用してオブジェクトをにパイプすることができ `Measure-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="c5886-137">You can pipe an object to `Measure-Command`.</span></span>

## <span data-ttu-id="c5886-138">出力</span><span class="sxs-lookup"><span data-stu-id="c5886-138">OUTPUTS</span></span>

### <span data-ttu-id="c5886-139">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="c5886-139">System.TimeSpan</span></span>

<span data-ttu-id="c5886-140">`Measure-Command` 結果を表す期間オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c5886-140">`Measure-Command` returns a time span object that represents the result.</span></span>

## <span data-ttu-id="c5886-141">注</span><span class="sxs-lookup"><span data-stu-id="c5886-141">NOTES</span></span>

## <span data-ttu-id="c5886-142">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c5886-142">RELATED LINKS</span></span>

[<span data-ttu-id="c5886-143">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="c5886-143">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="c5886-144">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="c5886-144">Trace-Command</span></span>](Trace-Command.md)

