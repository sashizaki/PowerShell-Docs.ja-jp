---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 02/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-random?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Random
ms.openlocfilehash: 97576832ea851f01b463f63948fbd80028c9a6fb
ms.sourcegitcommit: fa1a84c81e15f1ffac962110b0b4c850c1b173a0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99495844"
---
# <span data-ttu-id="65fb7-102">Get-Random</span><span class="sxs-lookup"><span data-stu-id="65fb7-102">Get-Random</span></span>

## <span data-ttu-id="65fb7-103">概要</span><span class="sxs-lookup"><span data-stu-id="65fb7-103">SYNOPSIS</span></span>
<span data-ttu-id="65fb7-104">乱数を取得するか、オブジェクトをコレクションからランダムに選択します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-104">Gets a random number, or selects objects randomly from a collection.</span></span>

## <span data-ttu-id="65fb7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="65fb7-105">SYNTAX</span></span>

### <span data-ttu-id="65fb7-106">RandomNumberParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="65fb7-106">RandomNumberParameterSet (Default)</span></span>

```
Get-Random [-SetSeed <Int32>] [[-Maximum] <Object>] [-Minimum <Object>] [<CommonParameters>]
```

### <span data-ttu-id="65fb7-107">RandomListItemParameterSet</span><span class="sxs-lookup"><span data-stu-id="65fb7-107">RandomListItemParameterSet</span></span>

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Count <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="65fb7-108">Description</span><span class="sxs-lookup"><span data-stu-id="65fb7-108">DESCRIPTION</span></span>

<span data-ttu-id="65fb7-109">`Get-Random`コマンドレットでは、ランダムに選択された番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-109">The `Get-Random` cmdlet gets a randomly selected number.</span></span> <span data-ttu-id="65fb7-110">オブジェクトのコレクションをに送信すると `Get-Random` 、コレクションからランダムに選択された1つ以上のオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-110">If you submit a collection of objects to `Get-Random`, it gets one or more randomly selected objects from the collection.</span></span>

<span data-ttu-id="65fb7-111">パラメーターまたは入力を指定しない場合、コマンドは、 `Get-Random` 0 (ゼロ) ~ int32.maxvalue (,) の間でランダムに選択された32ビット符号なし整数を返し `0x7FFFFFFF` `2,147,483,647` ます。</span><span class="sxs-lookup"><span data-stu-id="65fb7-111">Without parameters or input, a `Get-Random` command returns a randomly selected 32-bit unsigned integer between 0 (zero) and **Int32.MaxValue** (`0x7FFFFFFF`, `2,147,483,647`).</span></span>

<span data-ttu-id="65fb7-112">既定では、は `Get-Random` [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) クラスを使用して、暗号的に安全なランダム性を生成します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-112">By default, `Get-Random` generates cryptographically secure randomness using the [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) class.</span></span>

<span data-ttu-id="65fb7-113">のパラメーターを使用して、 `Get-Random` 最小値と最大値、コレクションから返されるオブジェクトの数、またはシード番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="65fb7-113">You can use the parameters of `Get-Random` to specify the minimum and maximum values, the number of objects returned from a collection, or a seed number.</span></span>

> [!CAUTION]
> <span data-ttu-id="65fb7-114">シードを意図的に設定すると、ランダムではない反復可能な動作になります。</span><span class="sxs-lookup"><span data-stu-id="65fb7-114">Setting the seed deliberately results in non-random, repeatable behavior.</span></span> <span data-ttu-id="65fb7-115">コマンドを含むスクリプトをデバッグまたは分析する場合など、動作を再現するときにのみ使用してください `Get-Random` 。</span><span class="sxs-lookup"><span data-stu-id="65fb7-115">It should only be used when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>
>
> <span data-ttu-id="65fb7-116">このシード値は、現在のコマンドと、 `Get-Random` **setseed** を再度使用するかセッションを閉じるまで、現在のセッションの後続のすべてのコマンドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="65fb7-116">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="65fb7-117">シードを既定値にリセットすることはできません。</span><span class="sxs-lookup"><span data-stu-id="65fb7-117">You can't reset the seed to its default value.</span></span>

## <span data-ttu-id="65fb7-118">例</span><span class="sxs-lookup"><span data-stu-id="65fb7-118">EXAMPLES</span></span>

### <span data-ttu-id="65fb7-119">例 1: ランダムな整数を取得する</span><span class="sxs-lookup"><span data-stu-id="65fb7-119">Example 1: Get a random integer</span></span>

<span data-ttu-id="65fb7-120">このコマンド **は、0**(ゼロ) ~ int32.maxvalue のランダムな整数を取得します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-120">This command gets a random integer between 0 (zero) and **Int32.MaxValue**.</span></span>

```powershell
Get-Random
```

```Output
3951433
```

### <span data-ttu-id="65fb7-121">例 2: 0 と99の間のランダムな整数を取得する</span><span class="sxs-lookup"><span data-stu-id="65fb7-121">Example 2: Get a random integer between 0 and 99</span></span>

```powershell
Get-Random -Maximum 100
```

```Output
47
```

### <span data-ttu-id="65fb7-122">例 3:-100 と99の間のランダムな整数を取得する</span><span class="sxs-lookup"><span data-stu-id="65fb7-122">Example 3: Get a random integer between -100 and 99</span></span>

```powershell
Get-Random -Minimum -100 -Maximum 100
```

```Output
56
```

### <span data-ttu-id="65fb7-123">例 4: ランダムな浮動小数点数を取得する</span><span class="sxs-lookup"><span data-stu-id="65fb7-123">Example 4: Get a random floating-point number</span></span>

<span data-ttu-id="65fb7-124">このコマンドは 10.7 以上 20.92 未満の浮動小数点乱数を取得します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-124">This command gets a random floating-point number greater than or equal to 10.7 and less than 20.92.</span></span>

```powershell
Get-Random -Minimum 10.7 -Maximum 20.93
```

```Output
18.08467273887
```

### <span data-ttu-id="65fb7-125">例 5: 配列からランダムな整数を取得する</span><span class="sxs-lookup"><span data-stu-id="65fb7-125">Example 5: Get a random integer from an array</span></span>

<span data-ttu-id="65fb7-126">このコマンドは、指定された配列からランダムに選択された数値を取得します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-126">This command gets a randomly selected number from the specified array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random
```

```Output
8
```

### <span data-ttu-id="65fb7-127">例 6: 配列から複数のランダムな整数を取得する</span><span class="sxs-lookup"><span data-stu-id="65fb7-127">Example 6: Get several random integers from an array</span></span>

<span data-ttu-id="65fb7-128">このコマンドは、ランダムに選択された3つの数値を配列からランダムな順序で取得します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-128">This command gets three randomly selected numbers in random order from an array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count 3
```

```Output
3
1
13
```

### <span data-ttu-id="65fb7-129">例 7: コレクション全体をランダム化する</span><span class="sxs-lookup"><span data-stu-id="65fb7-129">Example 7: Randomize an entire collection</span></span>

<span data-ttu-id="65fb7-130">このコマンドは、ランダムな順序でコレクション全体を返します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-130">This command returns the entire collection in random order.</span></span>

<span data-ttu-id="65fb7-131">**Count** パラメーターの値は、整数の **MaxValue** 静的プロパティです。</span><span class="sxs-lookup"><span data-stu-id="65fb7-131">The value of the **Count** parameter is the **MaxValue** static property of integers.</span></span>

<span data-ttu-id="65fb7-132">ランダムな順序でコレクション全体を返すには、コレクション内のオブジェクトの数以上の任意の数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-132">To return an entire collection in random order, enter any number that is greater than or equal to the number of objects in the collection.</span></span>

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

### <span data-ttu-id="65fb7-133">例 8: ランダムな数値以外の値を取得する</span><span class="sxs-lookup"><span data-stu-id="65fb7-133">Example 8: Get a random non-numeric value</span></span>

<span data-ttu-id="65fb7-134">このコマンドは、数値以外のコレクションから、乱数値を返します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-134">This command returns a random value from a non-numeric collection.</span></span>

```powershell
"red", "yellow", "blue" | Get-Random
```

```Output
yellow
```

### <span data-ttu-id="65fb7-135">例 9: SetSeed パラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="65fb7-135">Example 9: Use the SetSeed parameter</span></span>

<span data-ttu-id="65fb7-136">この例は、**SetSeed** パラメーターを使用した場合の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="65fb7-136">This example shows the effect of using the **SetSeed** parameter.</span></span>

<span data-ttu-id="65fb7-137">**Setseed** は、ランダムではない動作を生成するため、通常は、スクリプトのデバッグや分析などの結果を再現するためだけに使用されます。</span><span class="sxs-lookup"><span data-stu-id="65fb7-137">Because **SetSeed** produces non-random behavior, it's typically used only to reproduce results, such as when debugging or analyzing a script.</span></span>

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

### <span data-ttu-id="65fb7-138">例 10: ランダムファイルを取得する</span><span class="sxs-lookup"><span data-stu-id="65fb7-138">Example 10: Get random files</span></span>

<span data-ttu-id="65fb7-139">これらのコマンドは、ローカルコンピューターのドライブからランダムに選択された50ファイルのサンプルを取得し `C:` ます。</span><span class="sxs-lookup"><span data-stu-id="65fb7-139">These commands get a randomly selected sample of 50 files from the `C:` drive of the local computer.</span></span>

```powershell
$Files = Get-ChildItem -Path C:\* -Recurse
$Sample = $Files | Get-Random -Count 50
```

### <span data-ttu-id="65fb7-140">例 11: ロールフェアダイス</span><span class="sxs-lookup"><span data-stu-id="65fb7-140">Example 11: Roll fair dice</span></span>

<span data-ttu-id="65fb7-141">この例では、公正な1200回をロールし、結果をカウントします。</span><span class="sxs-lookup"><span data-stu-id="65fb7-141">This example rolls a fair die 1200 times and counts the outcomes.</span></span> <span data-ttu-id="65fb7-142">最初のコマンドは、 `ForEach-Object` `Get-Random` パイプされた数 (1-6) からの呼び出しを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-142">The first command, `ForEach-Object` repeats the call to `Get-Random` from the piped in numbers (1-6).</span></span> <span data-ttu-id="65fb7-143">結果は、の値によってグループ化され、 `Group-Object` でテーブルとして書式設定され `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="65fb7-143">The results are grouped by their value with `Group-Object` and formatted as a table with `Select-Object`.</span></span>

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

## <span data-ttu-id="65fb7-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="65fb7-144">PARAMETERS</span></span>

### <span data-ttu-id="65fb7-145">-カウント</span><span class="sxs-lookup"><span data-stu-id="65fb7-145">-Count</span></span>

<span data-ttu-id="65fb7-146">ランダムに返されるオブジェクトまたは数値の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-146">Specifies the number of random objects or numbers to return.</span></span> <span data-ttu-id="65fb7-147">既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="65fb7-147">The default is 1.</span></span>

<span data-ttu-id="65fb7-148">と共に使用する場合、 `InputObject` **Count** の値がコレクション内のオブジェクトの数を超えると、 `Get-Random` はランダムな順序ですべてのオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-148">When used with `InputObject`, if the value of **Count** exceeds the number of objects in the collection, `Get-Random` returns all of the objects in random order.</span></span>

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

### <span data-ttu-id="65fb7-149">-InputObject</span><span class="sxs-lookup"><span data-stu-id="65fb7-149">-InputObject</span></span>

<span data-ttu-id="65fb7-150">オブジェクトのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-150">Specifies a collection of objects.</span></span> <span data-ttu-id="65fb7-151">`Get-Random` コレクションから、 **Count** で指定した数までランダムに選択されたオブジェクトをランダムな順序で取得します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-151">`Get-Random` gets randomly selected objects in random order from the collection up to the number specified by **Count**.</span></span> <span data-ttu-id="65fb7-152">オブジェクト、オブジェクトを含む変数、またはオブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-152">Enter the objects, a variable that contains the objects, or a command or expression that gets the objects.</span></span> <span data-ttu-id="65fb7-153">パイプを使用してオブジェクトのコレクションをにパイプすることもでき `Get-Random` ます。</span><span class="sxs-lookup"><span data-stu-id="65fb7-153">You can also pipe a collection of objects to `Get-Random`.</span></span>

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

### <span data-ttu-id="65fb7-154">-最大</span><span class="sxs-lookup"><span data-stu-id="65fb7-154">-Maximum</span></span>

<span data-ttu-id="65fb7-155">乱数の最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-155">Specifies a maximum value for the random number.</span></span> <span data-ttu-id="65fb7-156">`Get-Random` は、最大値 (等しくない) より小さい値を返します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-156">`Get-Random` returns a value that is less than the maximum (not equal).</span></span> <span data-ttu-id="65fb7-157">整数、倍精度浮動小数点数、または数値文字列 ("100") などの整数または倍精度に変換できるオブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-157">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span>

<span data-ttu-id="65fb7-158">**Maximum** の値は、**Minimum** の値より大きくする必要があります (等しくない)。</span><span class="sxs-lookup"><span data-stu-id="65fb7-158">The value of **Maximum** must be greater than (not equal to) the value of **Minimum**.</span></span> <span data-ttu-id="65fb7-159">**最大** 値または **最小** 値が浮動小数点数の場合、は `Get-Random` ランダムに選択された浮動小数点数を返します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-159">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

<span data-ttu-id="65fb7-160">64ビットのコンピューターでは、[ **最小** ] の値が32ビットの整数の場合、[ **最大** 値] の既定値は int32.maxvalue. **MaxValue** です。</span><span class="sxs-lookup"><span data-stu-id="65fb7-160">On a 64-bit computer, if the value of **Minimum** is a 32-bit integer, the default value of **Maximum** is **Int32.MaxValue**.</span></span>

<span data-ttu-id="65fb7-161">**Minimum** の値が double (浮動小数点数) の場合、 **Maximum** の既定値は **2 倍** です。</span><span class="sxs-lookup"><span data-stu-id="65fb7-161">If the value of **Minimum** is a double (a floating-point number), the default value of **Maximum** is **Double.MaxValue**.</span></span> <span data-ttu-id="65fb7-162">それ以外の場合、既定 **値は int32.maxvalue です。**</span><span class="sxs-lookup"><span data-stu-id="65fb7-162">Otherwise, the default value is **Int32.MaxValue**.</span></span>

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

### <span data-ttu-id="65fb7-163">-最小</span><span class="sxs-lookup"><span data-stu-id="65fb7-163">-Minimum</span></span>

<span data-ttu-id="65fb7-164">乱数の最小値を指定します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-164">Specifies a minimum value for the random number.</span></span> <span data-ttu-id="65fb7-165">整数、倍精度浮動小数点数、または数値文字列 ("100") などの整数または倍精度に変換できるオブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-165">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span> <span data-ttu-id="65fb7-166">既定値は 0 (ゼロ) です。</span><span class="sxs-lookup"><span data-stu-id="65fb7-166">The default value is 0 (zero).</span></span>

<span data-ttu-id="65fb7-167">**Minimum** の値は、**Maximum** の値より小さくする必要があります (等しくない)。</span><span class="sxs-lookup"><span data-stu-id="65fb7-167">The value of **Minimum** must be less than (not equal to) the value of **Maximum**.</span></span> <span data-ttu-id="65fb7-168">**最大** 値または **最小** 値が浮動小数点数の場合、は `Get-Random` ランダムに選択された浮動小数点数を返します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-168">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

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

### <span data-ttu-id="65fb7-169">-SetSeed</span><span class="sxs-lookup"><span data-stu-id="65fb7-169">-SetSeed</span></span>

<span data-ttu-id="65fb7-170">乱数ジェネレーターのシード値を指定します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-170">Specifies a seed value for the random number generator.</span></span> <span data-ttu-id="65fb7-171">**Setseed** を使用する場合、コマンドレットは、 [Random](/dotnet/api/system.random)メソッドを使用して、暗号的に安全ではない擬似乱数を生成します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-171">When you use **SetSeed**, the cmdlet uses the [System.Random](/dotnet/api/system.random) method to generate pseudorandom numbers, which is not cryptographically secure.</span></span>

> [!CAUTION]
> <span data-ttu-id="65fb7-172">シードを設定すると、ランダムではない動作になります。</span><span class="sxs-lookup"><span data-stu-id="65fb7-172">Setting the seed results in non-random behavior.</span></span> <span data-ttu-id="65fb7-173">コマンドを含むスクリプトをデバッグまたは分析する場合など、動作を再現するときにのみ使用してください `Get-Random` 。</span><span class="sxs-lookup"><span data-stu-id="65fb7-173">It should only be used when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>
>
> <span data-ttu-id="65fb7-174">このシード値は、現在のコマンドと、 `Get-Random` **setseed** を再度使用するかセッションを閉じるまで、現在のセッションの後続のすべてのコマンドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="65fb7-174">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="65fb7-175">シードを既定値にリセットすることはできません。</span><span class="sxs-lookup"><span data-stu-id="65fb7-175">You can't reset the seed to its default value.</span></span>

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

### <span data-ttu-id="65fb7-176">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="65fb7-176">CommonParameters</span></span>

<span data-ttu-id="65fb7-177">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="65fb7-177">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="65fb7-178">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65fb7-178">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="65fb7-179">入力</span><span class="sxs-lookup"><span data-stu-id="65fb7-179">INPUTS</span></span>

### <span data-ttu-id="65fb7-180">System.Object</span><span class="sxs-lookup"><span data-stu-id="65fb7-180">System.Object</span></span>

<span data-ttu-id="65fb7-181">パイプを使用して1つ以上のオブジェクトをパイプ処理できます。</span><span class="sxs-lookup"><span data-stu-id="65fb7-181">You can pipe one or more objects.</span></span> <span data-ttu-id="65fb7-182">`Get-Random` パイプされたオブジェクトからランダムに値を選択します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-182">`Get-Random` selects values randomly from the piped objects.</span></span>

## <span data-ttu-id="65fb7-183">出力</span><span class="sxs-lookup"><span data-stu-id="65fb7-183">OUTPUTS</span></span>

### <span data-ttu-id="65fb7-184">System.string, system.string, system.string, system.string</span><span class="sxs-lookup"><span data-stu-id="65fb7-184">System.Int32, System.Int64, System.Double</span></span>

<span data-ttu-id="65fb7-185">`Get-Random` 整数または浮動小数点数、または送信されたコレクションからランダムに選択されたオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-185">`Get-Random` returns an integer or floating-point number, or an object selected randomly from a submitted collection.</span></span>

## <span data-ttu-id="65fb7-186">注</span><span class="sxs-lookup"><span data-stu-id="65fb7-186">NOTES</span></span>

<span data-ttu-id="65fb7-187">既定では、は `Get-Random` [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) クラスを使用して、暗号的に安全なランダム性を生成します。</span><span class="sxs-lookup"><span data-stu-id="65fb7-187">By default, `Get-Random` generates cryptographically secure randomness using the [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) class.</span></span>

<span data-ttu-id="65fb7-188">`Get-Random` は、必ずしも入力値と同じデータ型を返すとは限りません。</span><span class="sxs-lookup"><span data-stu-id="65fb7-188">`Get-Random` does not alway return the same data type as the input value.</span></span> <span data-ttu-id="65fb7-189">次の表は、各数値入力型の出力の種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="65fb7-189">The following table shows the output type for each of the numeric input types.</span></span>

| <span data-ttu-id="65fb7-190">入力タイプ</span><span class="sxs-lookup"><span data-stu-id="65fb7-190">Input Type</span></span> | <span data-ttu-id="65fb7-191">出力の種類</span><span class="sxs-lookup"><span data-stu-id="65fb7-191">Output Type</span></span> |
| :--------: | :---------: |
|   <span data-ttu-id="65fb7-192">SByte</span><span class="sxs-lookup"><span data-stu-id="65fb7-192">SByte</span></span>    |   <span data-ttu-id="65fb7-193">Double</span><span class="sxs-lookup"><span data-stu-id="65fb7-193">Double</span></span>    |
|    <span data-ttu-id="65fb7-194">Byte</span><span class="sxs-lookup"><span data-stu-id="65fb7-194">Byte</span></span>    |   <span data-ttu-id="65fb7-195">Double</span><span class="sxs-lookup"><span data-stu-id="65fb7-195">Double</span></span>    |
|   <span data-ttu-id="65fb7-196">Int16</span><span class="sxs-lookup"><span data-stu-id="65fb7-196">Int16</span></span>    |   <span data-ttu-id="65fb7-197">Double</span><span class="sxs-lookup"><span data-stu-id="65fb7-197">Double</span></span>    |
|   <span data-ttu-id="65fb7-198">UInt16</span><span class="sxs-lookup"><span data-stu-id="65fb7-198">UInt16</span></span>   |   <span data-ttu-id="65fb7-199">Double</span><span class="sxs-lookup"><span data-stu-id="65fb7-199">Double</span></span>    |
|   <span data-ttu-id="65fb7-200">Int32</span><span class="sxs-lookup"><span data-stu-id="65fb7-200">Int32</span></span>    |    <span data-ttu-id="65fb7-201">Int32</span><span class="sxs-lookup"><span data-stu-id="65fb7-201">Int32</span></span>    |
|   <span data-ttu-id="65fb7-202">UInt32</span><span class="sxs-lookup"><span data-stu-id="65fb7-202">UInt32</span></span>   |   <span data-ttu-id="65fb7-203">Double</span><span class="sxs-lookup"><span data-stu-id="65fb7-203">Double</span></span>    |
|   <span data-ttu-id="65fb7-204">Int64</span><span class="sxs-lookup"><span data-stu-id="65fb7-204">Int64</span></span>    |    <span data-ttu-id="65fb7-205">Int64</span><span class="sxs-lookup"><span data-stu-id="65fb7-205">Int64</span></span>    |
|   <span data-ttu-id="65fb7-206">UInt64</span><span class="sxs-lookup"><span data-stu-id="65fb7-206">UInt64</span></span>   |   <span data-ttu-id="65fb7-207">Double</span><span class="sxs-lookup"><span data-stu-id="65fb7-207">Double</span></span>    |
|   <span data-ttu-id="65fb7-208">Double</span><span class="sxs-lookup"><span data-stu-id="65fb7-208">Double</span></span>   |   <span data-ttu-id="65fb7-209">Double</span><span class="sxs-lookup"><span data-stu-id="65fb7-209">Double</span></span>    |
|   <span data-ttu-id="65fb7-210">Single</span><span class="sxs-lookup"><span data-stu-id="65fb7-210">Single</span></span>   |   <span data-ttu-id="65fb7-211">Double</span><span class="sxs-lookup"><span data-stu-id="65fb7-211">Double</span></span>    |

<span data-ttu-id="65fb7-212">Windows PowerShell 3.0 以降では、は `Get-Random` 64 ビット整数をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="65fb7-212">Beginning in Windows PowerShell 3.0, `Get-Random` supports 64-bit integers.</span></span> <span data-ttu-id="65fb7-213">Windows PowerShell 2.0 では、すべての値が **system.string にキャストされます。**</span><span class="sxs-lookup"><span data-stu-id="65fb7-213">In Windows PowerShell 2.0, all values are cast to **System.Int32**.</span></span>

## <span data-ttu-id="65fb7-214">関連リンク</span><span class="sxs-lookup"><span data-stu-id="65fb7-214">RELATED LINKS</span></span>

[<span data-ttu-id="65fb7-215">RandomNumberGenerator () です。</span><span class="sxs-lookup"><span data-stu-id="65fb7-215">System.Security.Cryptography.RandomNumberGenerator()</span></span>](/dotnet/api/system.security.cryptography.randomnumbergenerator)

[<span data-ttu-id="65fb7-216">システム。ランダム</span><span class="sxs-lookup"><span data-stu-id="65fb7-216">Sytem.Random</span></span>](/dotnet/api/system.random)
