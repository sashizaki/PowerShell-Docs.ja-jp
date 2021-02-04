---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 02/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-random?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Random
ms.openlocfilehash: 007f8f2e377af0620d439f5a35be51aace032dc1
ms.sourcegitcommit: fa1a84c81e15f1ffac962110b0b4c850c1b173a0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99496051"
---
# <span data-ttu-id="697b8-102">Get-Random</span><span class="sxs-lookup"><span data-stu-id="697b8-102">Get-Random</span></span>

## <span data-ttu-id="697b8-103">概要</span><span class="sxs-lookup"><span data-stu-id="697b8-103">SYNOPSIS</span></span>
<span data-ttu-id="697b8-104">乱数を取得するか、オブジェクトをコレクションからランダムに選択します。</span><span class="sxs-lookup"><span data-stu-id="697b8-104">Gets a random number, or selects objects randomly from a collection.</span></span>

## <span data-ttu-id="697b8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="697b8-105">SYNTAX</span></span>

### <span data-ttu-id="697b8-106">RandomNumberParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="697b8-106">RandomNumberParameterSet (Default)</span></span>

```
Get-Random [-SetSeed <Int32>] [[-Maximum] <Object>] [-Minimum <Object>] [-Count <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="697b8-107">RandomListItemParameterSet</span><span class="sxs-lookup"><span data-stu-id="697b8-107">RandomListItemParameterSet</span></span>

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Count <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="697b8-108">Description</span><span class="sxs-lookup"><span data-stu-id="697b8-108">DESCRIPTION</span></span>

<span data-ttu-id="697b8-109">`Get-Random`コマンドレットでは、ランダムに選択された番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="697b8-109">The `Get-Random` cmdlet gets a randomly selected number.</span></span> <span data-ttu-id="697b8-110">オブジェクトのコレクションをに送信すると `Get-Random` 、コレクションからランダムに選択された1つ以上のオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="697b8-110">If you submit a collection of objects to `Get-Random`, it gets one or more randomly selected objects from the collection.</span></span>

<span data-ttu-id="697b8-111">パラメーターまたは入力を指定しない場合、コマンドは、 `Get-Random` 0 (ゼロ) ~ int32.maxvalue (,) の間でランダムに選択された32ビット符号なし整数を返し `0x7FFFFFFF` `2,147,483,647` ます。</span><span class="sxs-lookup"><span data-stu-id="697b8-111">Without parameters or input, a `Get-Random` command returns a randomly selected 32-bit unsigned integer between 0 (zero) and **Int32.MaxValue** (`0x7FFFFFFF`, `2,147,483,647`).</span></span>

<span data-ttu-id="697b8-112">既定では、は `Get-Random` [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) クラスを使用して、暗号的に安全なランダム性を生成します。</span><span class="sxs-lookup"><span data-stu-id="697b8-112">By default, `Get-Random` generates cryptographically secure randomness using the [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) class.</span></span>

<span data-ttu-id="697b8-113">のパラメーターを使用して、 `Get-Random` 最小値と最大値、コレクションから返されるオブジェクトの数、またはシード番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="697b8-113">You can use the parameters of `Get-Random` to specify the minimum and maximum values, the number of objects returned from a collection, or a seed number.</span></span>

> [!CAUTION]
> <span data-ttu-id="697b8-114">シードを意図的に設定すると、ランダムではない反復可能な動作になります。</span><span class="sxs-lookup"><span data-stu-id="697b8-114">Setting the seed deliberately results in non-random, repeatable behavior.</span></span> <span data-ttu-id="697b8-115">コマンドを含むスクリプトをデバッグまたは分析する場合など、動作を再現するときにのみ使用してください `Get-Random` 。</span><span class="sxs-lookup"><span data-stu-id="697b8-115">It should only be used when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>
>
> <span data-ttu-id="697b8-116">このシード値は、現在のコマンドと、 `Get-Random` **setseed** を再度使用するかセッションを閉じるまで、現在のセッションの後続のすべてのコマンドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="697b8-116">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="697b8-117">シードを既定値にリセットすることはできません。</span><span class="sxs-lookup"><span data-stu-id="697b8-117">You can't reset the seed to its default value.</span></span>

## <span data-ttu-id="697b8-118">例</span><span class="sxs-lookup"><span data-stu-id="697b8-118">EXAMPLES</span></span>

### <span data-ttu-id="697b8-119">例 1: ランダムな整数を取得する</span><span class="sxs-lookup"><span data-stu-id="697b8-119">Example 1: Get a random integer</span></span>

<span data-ttu-id="697b8-120">このコマンド **は、0**(ゼロ) ~ int32.maxvalue のランダムな整数を取得します。</span><span class="sxs-lookup"><span data-stu-id="697b8-120">This command gets a random integer between 0 (zero) and **Int32.MaxValue**.</span></span>

```powershell
Get-Random
```

```Output
3951433
```

### <span data-ttu-id="697b8-121">例 2: 0 と99の間のランダムな整数を取得する</span><span class="sxs-lookup"><span data-stu-id="697b8-121">Example 2: Get a random integer between 0 and 99</span></span>

```powershell
Get-Random -Maximum 100
```

```Output
47
```

### <span data-ttu-id="697b8-122">例 3:-100 と99の間のランダムな整数を取得する</span><span class="sxs-lookup"><span data-stu-id="697b8-122">Example 3: Get a random integer between -100 and 99</span></span>

```powershell
Get-Random -Minimum -100 -Maximum 100
```

```Output
56
```

### <span data-ttu-id="697b8-123">例 4: ランダムな浮動小数点数を取得する</span><span class="sxs-lookup"><span data-stu-id="697b8-123">Example 4: Get a random floating-point number</span></span>

<span data-ttu-id="697b8-124">このコマンドは 10.7 以上 20.92 未満の浮動小数点乱数を取得します。</span><span class="sxs-lookup"><span data-stu-id="697b8-124">This command gets a random floating-point number greater than or equal to 10.7 and less than 20.92.</span></span>

```powershell
Get-Random -Minimum 10.7 -Maximum 20.93
```

```Output
18.08467273887
```

### <span data-ttu-id="697b8-125">例 5: 配列からランダムな整数を取得する</span><span class="sxs-lookup"><span data-stu-id="697b8-125">Example 5: Get a random integer from an array</span></span>

<span data-ttu-id="697b8-126">このコマンドは、指定された配列からランダムに選択された数値を取得します。</span><span class="sxs-lookup"><span data-stu-id="697b8-126">This command gets a randomly selected number from the specified array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random
```

```Output
8
```

### <span data-ttu-id="697b8-127">例 6: 配列から複数のランダムな整数を取得する</span><span class="sxs-lookup"><span data-stu-id="697b8-127">Example 6: Get several random integers from an array</span></span>

<span data-ttu-id="697b8-128">このコマンドは、ランダムに選択された3つの数値を配列からランダムな順序で取得します。</span><span class="sxs-lookup"><span data-stu-id="697b8-128">This command gets three randomly selected numbers in random order from an array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count 3
```

```Output
3
1
13
```

### <span data-ttu-id="697b8-129">例 7: コレクション全体をランダム化する</span><span class="sxs-lookup"><span data-stu-id="697b8-129">Example 7: Randomize an entire collection</span></span>

<span data-ttu-id="697b8-130">このコマンドは、ランダムな順序でコレクション全体を返します。</span><span class="sxs-lookup"><span data-stu-id="697b8-130">This command returns the entire collection in random order.</span></span>

<span data-ttu-id="697b8-131">**Count** パラメーターの値は、整数の **MaxValue** 静的プロパティです。</span><span class="sxs-lookup"><span data-stu-id="697b8-131">The value of the **Count** parameter is the **MaxValue** static property of integers.</span></span>

<span data-ttu-id="697b8-132">ランダムな順序でコレクション全体を返すには、コレクション内のオブジェクトの数以上の任意の数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="697b8-132">To return an entire collection in random order, enter any number that is greater than or equal to the number of objects in the collection.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count ([int]::MaxValue)
```

```Output
2
3
5
1
8
13
```

### <span data-ttu-id="697b8-133">例 8: ランダムな数値以外の値を取得する</span><span class="sxs-lookup"><span data-stu-id="697b8-133">Example 8: Get a random non-numeric value</span></span>

<span data-ttu-id="697b8-134">このコマンドは、数値以外のコレクションから、乱数値を返します。</span><span class="sxs-lookup"><span data-stu-id="697b8-134">This command returns a random value from a non-numeric collection.</span></span>

```powershell
"red", "yellow", "blue" | Get-Random
```

```Output
yellow
```

### <span data-ttu-id="697b8-135">例 9: SetSeed パラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="697b8-135">Example 9: Use the SetSeed parameter</span></span>

<span data-ttu-id="697b8-136">この例は、**SetSeed** パラメーターを使用した場合の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="697b8-136">This example shows the effect of using the **SetSeed** parameter.</span></span>

<span data-ttu-id="697b8-137">**Setseed** は、ランダムではない動作を生成するため、通常は、スクリプトのデバッグや分析などの結果を再現するためだけに使用されます。</span><span class="sxs-lookup"><span data-stu-id="697b8-137">Because **SetSeed** produces non-random behavior, it's typically used only to reproduce results, such as when debugging or analyzing a script.</span></span>

```powershell
# Commands with the default seed are pseudorandom
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100
Get-Random -Maximum 100
Get-Random -Maximum 100
```

```Output
74
56
84
46
```

```powershell
# Commands with the same seed are not random
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100 -SetSeed 23
```

```Output
74
74
74
```

```powershell
# SetSeed results in a repeatable series
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100
Get-Random -Maximum 100
Get-Random -Maximum 100
```

```Output
74
56
84
46
```

### <span data-ttu-id="697b8-138">例 10: ランダムファイルを取得する</span><span class="sxs-lookup"><span data-stu-id="697b8-138">Example 10: Get random files</span></span>

<span data-ttu-id="697b8-139">これらのコマンドは、ローカルコンピューターのドライブからランダムに選択された50ファイルのサンプルを取得し `C:` ます。</span><span class="sxs-lookup"><span data-stu-id="697b8-139">These commands get a randomly selected sample of 50 files from the `C:` drive of the local computer.</span></span>

```powershell
$Files = Get-ChildItem -Path C:\* -Recurse
$Sample = $Files | Get-Random -Count 50
```

### <span data-ttu-id="697b8-140">例 11: ロールフェアダイス</span><span class="sxs-lookup"><span data-stu-id="697b8-140">Example 11: Roll fair dice</span></span>

<span data-ttu-id="697b8-141">この例では、公正な1200回をロールし、結果をカウントします。</span><span class="sxs-lookup"><span data-stu-id="697b8-141">This example rolls a fair die 1200 times and counts the outcomes.</span></span> <span data-ttu-id="697b8-142">最初のコマンドは、 `ForEach-Object` `Get-Random` パイプされた数 (1-6) からの呼び出しを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="697b8-142">The first command, `ForEach-Object` repeats the call to `Get-Random` from the piped in numbers (1-6).</span></span> <span data-ttu-id="697b8-143">結果は、の値によってグループ化され、 `Group-Object` でテーブルとして書式設定され `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="697b8-143">The results are grouped by their value with `Group-Object` and formatted as a table with `Select-Object`.</span></span>

```powershell
1..1200 | ForEach-Object {
    1..6 | Get-Random
} | Group-Object | Select-Object Name,Count
```

```Output
Name Count
---- -----
1      206
2      199
3      196
4      226
5      185
6      188
```

### <span data-ttu-id="697b8-144">例 12: Count パラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="697b8-144">Example 12: Use the Count parameter</span></span>

<span data-ttu-id="697b8-145">これで、オブジェクトをにパイプせずに **Count** パラメーターを使用できるようになりました `Get-Random` 。</span><span class="sxs-lookup"><span data-stu-id="697b8-145">You can now use the **Count** parameter without piping objects to `Get-Random`.</span></span>
<span data-ttu-id="697b8-146">次の例では、10未満の乱数を3つ取得します。</span><span class="sxs-lookup"><span data-stu-id="697b8-146">The following example gets three random numbers less than 10.</span></span>

```powershell
Get-Random -Count 3 -Maximum 10
```

```Output
9
0
8
```

### <span data-ttu-id="697b8-147">例 13: InputObject パラメーターに空の文字列または $null を使用する</span><span class="sxs-lookup"><span data-stu-id="697b8-147">Example 13: Use the InputObject parameter with an empty string or $null</span></span>

<span data-ttu-id="697b8-148">この例では、 **InputObject** パラメーターで、空の文字列 () とを含む配列を指定して `''` `$null` います。</span><span class="sxs-lookup"><span data-stu-id="697b8-148">In this example, the **InputObject** parameter specifies an array that contains an empty string (`''`) and `$null`.</span></span>

```powershell
Get-Random -InputObject @('a','',$null)
```

<span data-ttu-id="697b8-149">`Get-Random` は `a` 、、空の文字列、またはを返し `$null` ます。</span><span class="sxs-lookup"><span data-stu-id="697b8-149">`Get-Random` will return either `a`, empty string, or `$null`.</span></span> <span data-ttu-id="697b8-150">空の入力は空白行として表示され、 `$null` PowerShell プロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="697b8-150">The empty sting displays as a blank line and `$null` returns to a PowerShell prompt.</span></span>

## <span data-ttu-id="697b8-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="697b8-151">PARAMETERS</span></span>

### <span data-ttu-id="697b8-152">-カウント</span><span class="sxs-lookup"><span data-stu-id="697b8-152">-Count</span></span>

<span data-ttu-id="697b8-153">ランダムに返されるオブジェクトまたは数値の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="697b8-153">Specifies the number of random objects or numbers to return.</span></span> <span data-ttu-id="697b8-154">既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="697b8-154">The default is 1.</span></span>

<span data-ttu-id="697b8-155">と共に使用する場合、 `InputObject` **Count** の値がコレクション内のオブジェクトの数を超えると、 `Get-Random` はランダムな順序ですべてのオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="697b8-155">When used with `InputObject`, if the value of **Count** exceeds the number of objects in the collection, `Get-Random` returns all of the objects in random order.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="697b8-156">-InputObject</span><span class="sxs-lookup"><span data-stu-id="697b8-156">-InputObject</span></span>

<span data-ttu-id="697b8-157">オブジェクトのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="697b8-157">Specifies a collection of objects.</span></span> <span data-ttu-id="697b8-158">`Get-Random` コレクションから、 **Count** で指定した数までランダムに選択されたオブジェクトをランダムな順序で取得します。</span><span class="sxs-lookup"><span data-stu-id="697b8-158">`Get-Random` gets randomly selected objects in random order from the collection up to the number specified by **Count**.</span></span> <span data-ttu-id="697b8-159">オブジェクト、オブジェクトを含む変数、またはオブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="697b8-159">Enter the objects, a variable that contains the objects, or a command or expression that gets the objects.</span></span> <span data-ttu-id="697b8-160">パイプを使用してオブジェクトのコレクションをにパイプすることもでき `Get-Random` ます。</span><span class="sxs-lookup"><span data-stu-id="697b8-160">You can also pipe a collection of objects to `Get-Random`.</span></span>

<span data-ttu-id="697b8-161">PowerShell 7 以降では、 **InputObject** パラメーターは、空の文字列またはを含むことのできる配列を受け入れ `$null` ます。</span><span class="sxs-lookup"><span data-stu-id="697b8-161">Beginning in PowerShell 7, the **InputObject** parameter accepts arrays that can contain an empty string or `$null`.</span></span> <span data-ttu-id="697b8-162">配列は、パイプラインまたは **InputObject** パラメーター値として送信できます。</span><span class="sxs-lookup"><span data-stu-id="697b8-162">The array can be sent down the pipeline or as an **InputObject** parameter value.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: RandomListItemParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="697b8-163">-最大</span><span class="sxs-lookup"><span data-stu-id="697b8-163">-Maximum</span></span>

<span data-ttu-id="697b8-164">乱数の最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="697b8-164">Specifies a maximum value for the random number.</span></span> <span data-ttu-id="697b8-165">`Get-Random` は、最大値 (等しくない) より小さい値を返します。</span><span class="sxs-lookup"><span data-stu-id="697b8-165">`Get-Random` returns a value that is less than the maximum (not equal).</span></span> <span data-ttu-id="697b8-166">整数、倍精度浮動小数点数、または数値文字列 ("100") などの整数または倍精度に変換できるオブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="697b8-166">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span>

<span data-ttu-id="697b8-167">**Maximum** の値は、**Minimum** の値より大きくする必要があります (等しくない)。</span><span class="sxs-lookup"><span data-stu-id="697b8-167">The value of **Maximum** must be greater than (not equal to) the value of **Minimum**.</span></span> <span data-ttu-id="697b8-168">**最大** 値または **最小** 値が浮動小数点数の場合、は `Get-Random` ランダムに選択された浮動小数点数を返します。</span><span class="sxs-lookup"><span data-stu-id="697b8-168">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

<span data-ttu-id="697b8-169">64ビットのコンピューターでは、[ **最小** ] の値が32ビットの整数の場合、[ **最大** 値] の既定値は int32.maxvalue. **MaxValue** です。</span><span class="sxs-lookup"><span data-stu-id="697b8-169">On a 64-bit computer, if the value of **Minimum** is a 32-bit integer, the default value of **Maximum** is **Int32.MaxValue**.</span></span>

<span data-ttu-id="697b8-170">**Minimum** の値が double (浮動小数点数) の場合、 **Maximum** の既定値は **2 倍** です。</span><span class="sxs-lookup"><span data-stu-id="697b8-170">If the value of **Minimum** is a double (a floating-point number), the default value of **Maximum** is **Double.MaxValue**.</span></span> <span data-ttu-id="697b8-171">それ以外の場合、既定 **値は int32.maxvalue です。**</span><span class="sxs-lookup"><span data-stu-id="697b8-171">Otherwise, the default value is **Int32.MaxValue**.</span></span>

```yaml
Type: System.Object
Parameter Sets: RandomNumberParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="697b8-172">-最小</span><span class="sxs-lookup"><span data-stu-id="697b8-172">-Minimum</span></span>

<span data-ttu-id="697b8-173">乱数の最小値を指定します。</span><span class="sxs-lookup"><span data-stu-id="697b8-173">Specifies a minimum value for the random number.</span></span> <span data-ttu-id="697b8-174">整数、倍精度浮動小数点数、または数値文字列 ("100") などの整数または倍精度に変換できるオブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="697b8-174">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span> <span data-ttu-id="697b8-175">既定値は 0 (ゼロ) です。</span><span class="sxs-lookup"><span data-stu-id="697b8-175">The default value is 0 (zero).</span></span>

<span data-ttu-id="697b8-176">**Minimum** の値は、**Maximum** の値より小さくする必要があります (等しくない)。</span><span class="sxs-lookup"><span data-stu-id="697b8-176">The value of **Minimum** must be less than (not equal to) the value of **Maximum**.</span></span> <span data-ttu-id="697b8-177">**最大** 値または **最小** 値が浮動小数点数の場合、は `Get-Random` ランダムに選択された浮動小数点数を返します。</span><span class="sxs-lookup"><span data-stu-id="697b8-177">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

```yaml
Type: System.Object
Parameter Sets: RandomNumberParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="697b8-178">-SetSeed</span><span class="sxs-lookup"><span data-stu-id="697b8-178">-SetSeed</span></span>

<span data-ttu-id="697b8-179">乱数ジェネレーターのシード値を指定します。</span><span class="sxs-lookup"><span data-stu-id="697b8-179">Specifies a seed value for the random number generator.</span></span> <span data-ttu-id="697b8-180">**Setseed** を使用する場合、コマンドレットは、 [Random](/dotnet/api/system.random)メソッドを使用して、暗号的に安全ではない擬似乱数を生成します。</span><span class="sxs-lookup"><span data-stu-id="697b8-180">When you use **SetSeed**, the cmdlet uses the [System.Random](/dotnet/api/system.random) method to generate pseudorandom numbers, which is not cryptographically secure.</span></span>

> [!CAUTION]
> <span data-ttu-id="697b8-181">シードを設定すると、ランダムではない動作になります。</span><span class="sxs-lookup"><span data-stu-id="697b8-181">Setting the seed results in non-random behavior.</span></span> <span data-ttu-id="697b8-182">コマンドを含むスクリプトをデバッグまたは分析する場合など、動作を再現するときにのみ使用してください `Get-Random` 。</span><span class="sxs-lookup"><span data-stu-id="697b8-182">It should only be used when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>
>
> <span data-ttu-id="697b8-183">このシード値は、現在のコマンドと、 `Get-Random` **setseed** を再度使用するかセッションを閉じるまで、現在のセッションの後続のすべてのコマンドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="697b8-183">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="697b8-184">シードを既定値にリセットすることはできません。</span><span class="sxs-lookup"><span data-stu-id="697b8-184">You can't reset the seed to its default value.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="697b8-185">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="697b8-185">CommonParameters</span></span>

<span data-ttu-id="697b8-186">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="697b8-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="697b8-187">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="697b8-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="697b8-188">入力</span><span class="sxs-lookup"><span data-stu-id="697b8-188">INPUTS</span></span>

### <span data-ttu-id="697b8-189">System.Object</span><span class="sxs-lookup"><span data-stu-id="697b8-189">System.Object</span></span>

<span data-ttu-id="697b8-190">パイプを使用して1つ以上のオブジェクトをパイプ処理できます。</span><span class="sxs-lookup"><span data-stu-id="697b8-190">You can pipe one or more objects.</span></span> <span data-ttu-id="697b8-191">`Get-Random` パイプされたオブジェクトからランダムに値を選択します。</span><span class="sxs-lookup"><span data-stu-id="697b8-191">`Get-Random` selects values randomly from the piped objects.</span></span>

## <span data-ttu-id="697b8-192">出力</span><span class="sxs-lookup"><span data-stu-id="697b8-192">OUTPUTS</span></span>

### <span data-ttu-id="697b8-193">System.string, system.string, system.string, system.string</span><span class="sxs-lookup"><span data-stu-id="697b8-193">System.Int32, System.Int64, System.Double</span></span>

<span data-ttu-id="697b8-194">`Get-Random` 整数または浮動小数点数、または送信されたコレクションからランダムに選択されたオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="697b8-194">`Get-Random` returns an integer or floating-point number, or an object selected randomly from a submitted collection.</span></span>

## <span data-ttu-id="697b8-195">注</span><span class="sxs-lookup"><span data-stu-id="697b8-195">NOTES</span></span>

<span data-ttu-id="697b8-196">既定では、は `Get-Random` [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) クラスを使用して、暗号的に安全なランダム性を生成します。</span><span class="sxs-lookup"><span data-stu-id="697b8-196">By default, `Get-Random` generates cryptographically secure randomness using the [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) class.</span></span>

<span data-ttu-id="697b8-197">`Get-Random` は、必ずしも入力値と同じデータ型を返すとは限りません。</span><span class="sxs-lookup"><span data-stu-id="697b8-197">`Get-Random` does not alway return the same data type as the input value.</span></span> <span data-ttu-id="697b8-198">次の表は、各数値入力型の出力の種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="697b8-198">The following table shows the output type for each of the numeric input types.</span></span>

| <span data-ttu-id="697b8-199">入力タイプ</span><span class="sxs-lookup"><span data-stu-id="697b8-199">Input Type</span></span> | <span data-ttu-id="697b8-200">出力の種類</span><span class="sxs-lookup"><span data-stu-id="697b8-200">Output Type</span></span> |
| :--------: | :---------: |
|   <span data-ttu-id="697b8-201">SByte</span><span class="sxs-lookup"><span data-stu-id="697b8-201">SByte</span></span>    |   <span data-ttu-id="697b8-202">Double</span><span class="sxs-lookup"><span data-stu-id="697b8-202">Double</span></span>    |
|    <span data-ttu-id="697b8-203">Byte</span><span class="sxs-lookup"><span data-stu-id="697b8-203">Byte</span></span>    |   <span data-ttu-id="697b8-204">Double</span><span class="sxs-lookup"><span data-stu-id="697b8-204">Double</span></span>    |
|   <span data-ttu-id="697b8-205">Int16</span><span class="sxs-lookup"><span data-stu-id="697b8-205">Int16</span></span>    |   <span data-ttu-id="697b8-206">Double</span><span class="sxs-lookup"><span data-stu-id="697b8-206">Double</span></span>    |
|   <span data-ttu-id="697b8-207">UInt16</span><span class="sxs-lookup"><span data-stu-id="697b8-207">UInt16</span></span>   |   <span data-ttu-id="697b8-208">Double</span><span class="sxs-lookup"><span data-stu-id="697b8-208">Double</span></span>    |
|   <span data-ttu-id="697b8-209">Int32</span><span class="sxs-lookup"><span data-stu-id="697b8-209">Int32</span></span>    |    <span data-ttu-id="697b8-210">Int32</span><span class="sxs-lookup"><span data-stu-id="697b8-210">Int32</span></span>    |
|   <span data-ttu-id="697b8-211">UInt32</span><span class="sxs-lookup"><span data-stu-id="697b8-211">UInt32</span></span>   |   <span data-ttu-id="697b8-212">Double</span><span class="sxs-lookup"><span data-stu-id="697b8-212">Double</span></span>    |
|   <span data-ttu-id="697b8-213">Int64</span><span class="sxs-lookup"><span data-stu-id="697b8-213">Int64</span></span>    |    <span data-ttu-id="697b8-214">Int64</span><span class="sxs-lookup"><span data-stu-id="697b8-214">Int64</span></span>    |
|   <span data-ttu-id="697b8-215">UInt64</span><span class="sxs-lookup"><span data-stu-id="697b8-215">UInt64</span></span>   |   <span data-ttu-id="697b8-216">Double</span><span class="sxs-lookup"><span data-stu-id="697b8-216">Double</span></span>    |
|   <span data-ttu-id="697b8-217">Double</span><span class="sxs-lookup"><span data-stu-id="697b8-217">Double</span></span>   |   <span data-ttu-id="697b8-218">Double</span><span class="sxs-lookup"><span data-stu-id="697b8-218">Double</span></span>    |
|   <span data-ttu-id="697b8-219">Single</span><span class="sxs-lookup"><span data-stu-id="697b8-219">Single</span></span>   |   <span data-ttu-id="697b8-220">Double</span><span class="sxs-lookup"><span data-stu-id="697b8-220">Double</span></span>    |

<span data-ttu-id="697b8-221">Windows PowerShell 3.0 以降では、は `Get-Random` 64 ビット整数をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="697b8-221">Beginning in Windows PowerShell 3.0, `Get-Random` supports 64-bit integers.</span></span> <span data-ttu-id="697b8-222">Windows PowerShell 2.0 では、すべての値が **system.string にキャストされます。**</span><span class="sxs-lookup"><span data-stu-id="697b8-222">In Windows PowerShell 2.0, all values are cast to **System.Int32**.</span></span>

<span data-ttu-id="697b8-223">PowerShell 7 以降では、 **RandomListItemParameterSet** パラメーターセットの **InputObject** パラメーターで、空の文字列またはを含む配列を受け取ることが `$null` できます。</span><span class="sxs-lookup"><span data-stu-id="697b8-223">Beginning in PowerShell 7, the **InputObject** parameter in the **RandomListItemParameterSet** parameter set accepts arrays that contain an empty string or `$null`.</span></span> <span data-ttu-id="697b8-224">以前のバージョンの PowerShell では、 **RandomNumberParameterSet** パラメーターセット内の **最大** パラメーターだけが、空の文字列またはを受け入れました `$null` 。</span><span class="sxs-lookup"><span data-stu-id="697b8-224">In earlier PowerShell versions, only the **Maximum** parameter in the **RandomNumberParameterSet** parameter set accepted an empty string or `$null`.</span></span>

## <span data-ttu-id="697b8-225">関連リンク</span><span class="sxs-lookup"><span data-stu-id="697b8-225">RELATED LINKS</span></span>

[<span data-ttu-id="697b8-226">RandomNumberGenerator () です。</span><span class="sxs-lookup"><span data-stu-id="697b8-226">System.Security.Cryptography.RandomNumberGenerator()</span></span>](/dotnet/api/system.security.cryptography.randomnumbergenerator)

[<span data-ttu-id="697b8-227">システム。ランダム</span><span class="sxs-lookup"><span data-stu-id="697b8-227">Sytem.Random</span></span>](/dotnet/api/system.random)
