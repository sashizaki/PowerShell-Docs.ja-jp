---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-random?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Random
ms.openlocfilehash: 6aa7d6db9e8c2fb8a3001c8ddb9593a7ceafe2ab
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213955"
---
# <span data-ttu-id="fa2a8-103">Get-Random</span><span class="sxs-lookup"><span data-stu-id="fa2a8-103">Get-Random</span></span>

## <span data-ttu-id="fa2a8-104">概要</span><span class="sxs-lookup"><span data-stu-id="fa2a8-104">SYNOPSIS</span></span>
<span data-ttu-id="fa2a8-105">乱数を取得するか、オブジェクトをコレクションからランダムに選択します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-105">Gets a random number, or selects objects randomly from a collection.</span></span>

## <span data-ttu-id="fa2a8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fa2a8-106">SYNTAX</span></span>

### <span data-ttu-id="fa2a8-107">RandomNumberParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="fa2a8-107">RandomNumberParameterSet (Default)</span></span>

```
Get-Random [-SetSeed <Int32>] [[-Maximum] <Object>] [-Minimum <Object>] [<CommonParameters>]
```

### <span data-ttu-id="fa2a8-108">RandomListItemParameterSet</span><span class="sxs-lookup"><span data-stu-id="fa2a8-108">RandomListItemParameterSet</span></span>

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Count <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="fa2a8-109">Description</span><span class="sxs-lookup"><span data-stu-id="fa2a8-109">DESCRIPTION</span></span>

<span data-ttu-id="fa2a8-110">`Get-Random`コマンドレットでは、ランダムに選択された番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-110">The `Get-Random` cmdlet gets a randomly selected number.</span></span> <span data-ttu-id="fa2a8-111">オブジェクトのコレクションをに送信すると `Get-Random` 、コレクションからランダムに選択された1つ以上のオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-111">If you submit a collection of objects to `Get-Random`, it gets one or more randomly selected objects from the collection.</span></span>

<span data-ttu-id="fa2a8-112">パラメーターまたは入力を指定しない場合、コマンドは、 `Get-Random` 0 (ゼロ) ~ int32.maxvalue (,) **Int32.MaxValue** の間でランダムに選択された32ビット符号なし整数を返し `0x7FFFFFFF` `2,147,483,647` ます。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-112">Without parameters or input, a `Get-Random` command returns a randomly selected 32-bit unsigned integer between 0 (zero) and **Int32.MaxValue** (`0x7FFFFFFF`, `2,147,483,647`).</span></span>

<span data-ttu-id="fa2a8-113">のパラメーターを使用して、 `Get-Random` シード番号、最小値と最大値、および送信されたコレクションから返されるオブジェクトの数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-113">You can use the parameters of `Get-Random` to specify a seed number, minimum and maximum values, and the number of objects returned from a submitted collection.</span></span>

## <span data-ttu-id="fa2a8-114">例</span><span class="sxs-lookup"><span data-stu-id="fa2a8-114">EXAMPLES</span></span>

### <span data-ttu-id="fa2a8-115">例 1: ランダムな整数を取得する</span><span class="sxs-lookup"><span data-stu-id="fa2a8-115">Example 1: Get a random integer</span></span>

<span data-ttu-id="fa2a8-116">このコマンド **は、0** (ゼロ) ~ int32.maxvalue のランダムな整数を取得します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-116">This command gets a random integer between 0 (zero) and **Int32.MaxValue** .</span></span>

```powershell
Get-Random
```

```Output
3951433
```

### <span data-ttu-id="fa2a8-117">例 2: 0 と99の間のランダムな整数を取得する</span><span class="sxs-lookup"><span data-stu-id="fa2a8-117">Example 2: Get a random integer between 0 and 99</span></span>

```powershell
Get-Random -Maximum 100
```

```Output
47
```

### <span data-ttu-id="fa2a8-118">例 3:-100 と99の間のランダムな整数を取得する</span><span class="sxs-lookup"><span data-stu-id="fa2a8-118">Example 3: Get a random integer between -100 and 99</span></span>

```powershell
Get-Random -Minimum -100 -Maximum 100
```

```Output
56
```

### <span data-ttu-id="fa2a8-119">例 4: ランダムな浮動小数点数を取得する</span><span class="sxs-lookup"><span data-stu-id="fa2a8-119">Example 4: Get a random floating-point number</span></span>

<span data-ttu-id="fa2a8-120">このコマンドは 10.7 以上 20.92 未満の浮動小数点乱数を取得します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-120">This command gets a random floating-point number greater than or equal to 10.7 and less than 20.92.</span></span>

```powershell
Get-Random -Minimum 10.7 -Maximum 20.93
```

```Output
18.08467273887
```

### <span data-ttu-id="fa2a8-121">例 5: 配列からランダムな整数を取得する</span><span class="sxs-lookup"><span data-stu-id="fa2a8-121">Example 5: Get a random integer from an array</span></span>

<span data-ttu-id="fa2a8-122">このコマンドは、指定された配列からランダムに選択された数値を取得します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-122">This command gets a randomly selected number from the specified array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random
```

```Output
8
```

### <span data-ttu-id="fa2a8-123">例 6: 配列から複数のランダムな整数を取得する</span><span class="sxs-lookup"><span data-stu-id="fa2a8-123">Example 6: Get several random integers from an array</span></span>

<span data-ttu-id="fa2a8-124">このコマンドは、ランダムに選択された3つの数値を配列からランダムな順序で取得します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-124">This command gets three randomly selected numbers in random order from an array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count 3
```

```Output
3
1
13
```

### <span data-ttu-id="fa2a8-125">例 7: コレクション全体をランダム化する</span><span class="sxs-lookup"><span data-stu-id="fa2a8-125">Example 7: Randomize an entire collection</span></span>

<span data-ttu-id="fa2a8-126">このコマンドは、ランダムな順序でコレクション全体を返します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-126">This command returns the entire collection in random order.</span></span>

<span data-ttu-id="fa2a8-127">**Count** パラメーターの値は、整数の **MaxValue** 静的プロパティです。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-127">The value of the **Count** parameter is the **MaxValue** static property of integers.</span></span>

<span data-ttu-id="fa2a8-128">ランダムな順序でコレクション全体を返すには、コレクション内のオブジェクトの数以上の任意の数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-128">To return an entire collection in random order, enter any number that is greater than or equal to the number of objects in the collection.</span></span>

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

### <span data-ttu-id="fa2a8-129">例 8: ランダムな数値以外の値を取得する</span><span class="sxs-lookup"><span data-stu-id="fa2a8-129">Example 8: Get a random non-numeric value</span></span>

<span data-ttu-id="fa2a8-130">このコマンドは、数値以外のコレクションから、乱数値を返します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-130">This command returns a random value from a non-numeric collection.</span></span>

```powershell
"red", "yellow", "blue" | Get-Random
```

```Output
yellow
```

### <span data-ttu-id="fa2a8-131">例 9: SetSeed パラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="fa2a8-131">Example 9: Use the SetSeed parameter</span></span>

<span data-ttu-id="fa2a8-132">この例は、 **SetSeed** パラメーターを使用した場合の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-132">This example shows the effect of using the **SetSeed** parameter.</span></span>

<span data-ttu-id="fa2a8-133">**Setseed** は、ランダムではない動作を生成するため、通常は、スクリプトのデバッグや分析などの結果を再現するためだけに使用されます。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-133">Because **SetSeed** produces non-random behavior, it's typically used only to reproduce results, such as when debugging or analyzing a script.</span></span>

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

### <span data-ttu-id="fa2a8-134">例 10: ランダムファイルを取得する</span><span class="sxs-lookup"><span data-stu-id="fa2a8-134">Example 10: Get random files</span></span>

<span data-ttu-id="fa2a8-135">これらのコマンドは、ローカルコンピューターのドライブからランダムに選択された50ファイルのサンプルを取得し `C:` ます。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-135">These commands get a randomly selected sample of 50 files from the `C:` drive of the local computer.</span></span>

```powershell
$Files = Get-ChildItem -Path C:\* -Recurse
$Sample = $Files | Get-Random -Count 50
```

### <span data-ttu-id="fa2a8-136">例 11: ロールフェアダイス</span><span class="sxs-lookup"><span data-stu-id="fa2a8-136">Example 11: Roll fair dice</span></span>

<span data-ttu-id="fa2a8-137">この例では、公正な1200回をロールし、結果をカウントします。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-137">This example rolls a fair die 1200 times and counts the outcomes.</span></span> <span data-ttu-id="fa2a8-138">最初のコマンドは、 `For-EachObject` `Get-Random` パイプされた数 (1-6) からの呼び出しを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-138">The first command, `For-EachObject` repeats the call to `Get-Random` from the piped in numbers (1-6).</span></span> <span data-ttu-id="fa2a8-139">結果は、の値によってグループ化され、 `Group-Object` でテーブルとして書式設定され `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-139">The results are grouped by their value with `Group-Object` and formatted as a table with `Select-Object`.</span></span>

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

## <span data-ttu-id="fa2a8-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fa2a8-140">PARAMETERS</span></span>

### <span data-ttu-id="fa2a8-141">-カウント</span><span class="sxs-lookup"><span data-stu-id="fa2a8-141">-Count</span></span>

<span data-ttu-id="fa2a8-142">ランダムに返されるオブジェクトまたは数値の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-142">Specifies the number of random objects or numbers to return.</span></span> <span data-ttu-id="fa2a8-143">既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-143">The default is 1.</span></span>

<span data-ttu-id="fa2a8-144">と共に使用する場合、 `InputObject` **Count** の値がコレクション内のオブジェクトの数を超えると、 `Get-Random` はランダムな順序ですべてのオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-144">When used with `InputObject`, if the value of **Count** exceeds the number of objects in the collection, `Get-Random` returns all of the objects in random order.</span></span>

```yaml
Type: System.Int32
Parameter Sets: RandomListItemParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fa2a8-145">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fa2a8-145">-InputObject</span></span>

<span data-ttu-id="fa2a8-146">オブジェクトのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-146">Specifies a collection of objects.</span></span> <span data-ttu-id="fa2a8-147">`Get-Random` コレクションから、 **Count** で指定した数までランダムに選択されたオブジェクトをランダムな順序で取得します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-147">`Get-Random` gets randomly selected objects in random order from the collection up to the number specified by **Count** .</span></span> <span data-ttu-id="fa2a8-148">オブジェクト、オブジェクトを含む変数、またはオブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-148">Enter the objects, a variable that contains the objects, or a command or expression that gets the objects.</span></span> <span data-ttu-id="fa2a8-149">パイプを使用してオブジェクトのコレクションをにパイプすることもでき `Get-Random` ます。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-149">You can also pipe a collection of objects to `Get-Random`.</span></span>

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

### <span data-ttu-id="fa2a8-150">-最大</span><span class="sxs-lookup"><span data-stu-id="fa2a8-150">-Maximum</span></span>

<span data-ttu-id="fa2a8-151">乱数の最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-151">Specifies a maximum value for the random number.</span></span> <span data-ttu-id="fa2a8-152">`Get-Random` は、最大値 (等しくない) より小さい値を返します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-152">`Get-Random` returns a value that is less than the maximum (not equal).</span></span> <span data-ttu-id="fa2a8-153">整数、倍精度浮動小数点数、または数値文字列 ("100") などの整数または倍精度に変換できるオブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-153">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span>

<span data-ttu-id="fa2a8-154">**Maximum** の値は、 **Minimum** の値より大きくする必要があります (等しくない)。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-154">The value of **Maximum** must be greater than (not equal to) the value of **Minimum** .</span></span> <span data-ttu-id="fa2a8-155">**最大** 値または **最小** 値が浮動小数点数の場合、は `Get-Random` ランダムに選択された浮動小数点数を返します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-155">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

<span data-ttu-id="fa2a8-156">64ビットのコンピューターでは、[ **最小** ] の値が32ビットの整数の場合、[ **最大** 値] の既定値は int32.maxvalue. **MaxValue** です。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-156">On a 64-bit computer, if the value of **Minimum** is a 32-bit integer, the default value of **Maximum** is **Int32.MaxValue** .</span></span>

<span data-ttu-id="fa2a8-157">**Minimum** の値が double (浮動小数点数) の場合、 **Maximum** の既定値は **2 倍** です。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-157">If the value of **Minimum** is a double (a floating-point number), the default value of **Maximum** is **Double.MaxValue** .</span></span> <span data-ttu-id="fa2a8-158">それ以外の場合、既定 **値は int32.maxvalue です。**</span><span class="sxs-lookup"><span data-stu-id="fa2a8-158">Otherwise, the default value is **Int32.MaxValue** .</span></span>

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

### <span data-ttu-id="fa2a8-159">-最小</span><span class="sxs-lookup"><span data-stu-id="fa2a8-159">-Minimum</span></span>

<span data-ttu-id="fa2a8-160">乱数の最小値を指定します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-160">Specifies a minimum value for the random number.</span></span> <span data-ttu-id="fa2a8-161">整数、倍精度浮動小数点数、または数値文字列 ("100") などの整数または倍精度に変換できるオブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-161">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span> <span data-ttu-id="fa2a8-162">既定値は 0 (ゼロ) です。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-162">The default value is 0 (zero).</span></span>

<span data-ttu-id="fa2a8-163">**Minimum** の値は、 **Maximum** の値より小さくする必要があります (等しくない)。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-163">The value of **Minimum** must be less than (not equal to) the value of **Maximum** .</span></span> <span data-ttu-id="fa2a8-164">**最大** 値または **最小** 値が浮動小数点数の場合、は `Get-Random` ランダムに選択された浮動小数点数を返します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-164">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

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

### <span data-ttu-id="fa2a8-165">-SetSeed</span><span class="sxs-lookup"><span data-stu-id="fa2a8-165">-SetSeed</span></span>

<span data-ttu-id="fa2a8-166">乱数ジェネレーターのシード値を指定します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-166">Specifies a seed value for the random number generator.</span></span> <span data-ttu-id="fa2a8-167">このシード値は、現在のコマンドと、 `Get-Random` **setseed** を再度使用するかセッションを閉じるまで、現在のセッションの後続のすべてのコマンドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-167">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="fa2a8-168">シードを既定値にリセットすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-168">You can't reset the seed to its default value.</span></span>

<span data-ttu-id="fa2a8-169">**Setseed** パラメーターは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-169">The **SetSeed** parameter is not required.</span></span> <span data-ttu-id="fa2a8-170">既定では、は `Get-Random` [RandomNumberGenerator ()](/dotnet/api/system.security.cryptography.randomnumbergenerator) メソッドを使用してシード値を生成します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-170">By default, `Get-Random` uses the [RandomNumberGenerator()](/dotnet/api/system.security.cryptography.randomnumbergenerator) method to generate a seed value.</span></span> <span data-ttu-id="fa2a8-171">**Setseed** は、ランダムではない動作をするため、通常は、コマンドを含むスクリプトをデバッグまたは分析する場合など、動作を再現しようとした場合にのみ使用され `Get-Random` ます。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-171">Because **SetSeed** results in non-random behavior, it's typically used only when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>

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

### <span data-ttu-id="fa2a8-172">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="fa2a8-172">CommonParameters</span></span>

<span data-ttu-id="fa2a8-173">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fa2a8-174">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-174">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fa2a8-175">入力</span><span class="sxs-lookup"><span data-stu-id="fa2a8-175">INPUTS</span></span>

### <span data-ttu-id="fa2a8-176">System.Object</span><span class="sxs-lookup"><span data-stu-id="fa2a8-176">System.Object</span></span>

<span data-ttu-id="fa2a8-177">パイプを使用して1つ以上のオブジェクトをパイプ処理できます。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-177">You can pipe one or more objects.</span></span> <span data-ttu-id="fa2a8-178">`Get-Random` パイプされたオブジェクトからランダムに値を選択します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-178">`Get-Random` selects values randomly from the piped objects.</span></span>

## <span data-ttu-id="fa2a8-179">出力</span><span class="sxs-lookup"><span data-stu-id="fa2a8-179">OUTPUTS</span></span>

### <span data-ttu-id="fa2a8-180">System.string, system.string, system.string, system.string</span><span class="sxs-lookup"><span data-stu-id="fa2a8-180">System.Int32, System.Int64, System.Double</span></span>

<span data-ttu-id="fa2a8-181">`Get-Random` 整数または浮動小数点数、または送信されたコレクションからランダムに選択されたオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-181">`Get-Random` returns an integer or floating-point number, or an object selected randomly from a submitted collection.</span></span>

## <span data-ttu-id="fa2a8-182">注</span><span class="sxs-lookup"><span data-stu-id="fa2a8-182">NOTES</span></span>

<span data-ttu-id="fa2a8-183">`Get-Random` セッションの開始時に、システム時刻のクロックに基づいて、各セッションの既定のシードを設定します。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-183">`Get-Random` sets a default seed for each session based on the system time clock when the session starts.</span></span>

<span data-ttu-id="fa2a8-184">`Get-Random` は、必ずしも入力値と同じデータ型を返すとは限りません。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-184">`Get-Random` does not alway return the same data type as the input value.</span></span> <span data-ttu-id="fa2a8-185">次の表は、各数値入力型の出力の種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-185">The following table shows the output type for each of the numeric input types.</span></span>

| <span data-ttu-id="fa2a8-186">入力タイプ</span><span class="sxs-lookup"><span data-stu-id="fa2a8-186">Input Type</span></span> | <span data-ttu-id="fa2a8-187">出力の種類</span><span class="sxs-lookup"><span data-stu-id="fa2a8-187">Output Type</span></span> |
| :--------: | :---------: |
|   <span data-ttu-id="fa2a8-188">SByte</span><span class="sxs-lookup"><span data-stu-id="fa2a8-188">SByte</span></span>    |   <span data-ttu-id="fa2a8-189">Double</span><span class="sxs-lookup"><span data-stu-id="fa2a8-189">Double</span></span>    |
|    <span data-ttu-id="fa2a8-190">Byte</span><span class="sxs-lookup"><span data-stu-id="fa2a8-190">Byte</span></span>    |   <span data-ttu-id="fa2a8-191">Double</span><span class="sxs-lookup"><span data-stu-id="fa2a8-191">Double</span></span>    |
|   <span data-ttu-id="fa2a8-192">Int16</span><span class="sxs-lookup"><span data-stu-id="fa2a8-192">Int16</span></span>    |   <span data-ttu-id="fa2a8-193">Double</span><span class="sxs-lookup"><span data-stu-id="fa2a8-193">Double</span></span>    |
|   <span data-ttu-id="fa2a8-194">UInt16</span><span class="sxs-lookup"><span data-stu-id="fa2a8-194">UInt16</span></span>   |   <span data-ttu-id="fa2a8-195">Double</span><span class="sxs-lookup"><span data-stu-id="fa2a8-195">Double</span></span>    |
|   <span data-ttu-id="fa2a8-196">Int32</span><span class="sxs-lookup"><span data-stu-id="fa2a8-196">Int32</span></span>    |    <span data-ttu-id="fa2a8-197">Int32</span><span class="sxs-lookup"><span data-stu-id="fa2a8-197">Int32</span></span>    |
|   <span data-ttu-id="fa2a8-198">UInt32</span><span class="sxs-lookup"><span data-stu-id="fa2a8-198">UInt32</span></span>   |   <span data-ttu-id="fa2a8-199">Double</span><span class="sxs-lookup"><span data-stu-id="fa2a8-199">Double</span></span>    |
|   <span data-ttu-id="fa2a8-200">Int64</span><span class="sxs-lookup"><span data-stu-id="fa2a8-200">Int64</span></span>    |    <span data-ttu-id="fa2a8-201">Int64</span><span class="sxs-lookup"><span data-stu-id="fa2a8-201">Int64</span></span>    |
|   <span data-ttu-id="fa2a8-202">UInt64</span><span class="sxs-lookup"><span data-stu-id="fa2a8-202">UInt64</span></span>   |   <span data-ttu-id="fa2a8-203">Double</span><span class="sxs-lookup"><span data-stu-id="fa2a8-203">Double</span></span>    |
|   <span data-ttu-id="fa2a8-204">Double</span><span class="sxs-lookup"><span data-stu-id="fa2a8-204">Double</span></span>   |   <span data-ttu-id="fa2a8-205">Double</span><span class="sxs-lookup"><span data-stu-id="fa2a8-205">Double</span></span>    |
|   <span data-ttu-id="fa2a8-206">Single</span><span class="sxs-lookup"><span data-stu-id="fa2a8-206">Single</span></span>   |   <span data-ttu-id="fa2a8-207">Double</span><span class="sxs-lookup"><span data-stu-id="fa2a8-207">Double</span></span>    |

<span data-ttu-id="fa2a8-208">Windows PowerShell 3.0 以降では、は `Get-Random` 64 ビット整数をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fa2a8-208">Beginning in Windows PowerShell 3.0, `Get-Random` supports 64-bit integers.</span></span> <span data-ttu-id="fa2a8-209">Windows PowerShell 2.0 では、すべての値が **system.string にキャストされます。**</span><span class="sxs-lookup"><span data-stu-id="fa2a8-209">In Windows PowerShell 2.0, all values are cast to **System.Int32** .</span></span>

## <span data-ttu-id="fa2a8-210">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fa2a8-210">RELATED LINKS</span></span>
