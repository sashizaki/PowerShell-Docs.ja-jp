---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/compare-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compare-Object
ms.openlocfilehash: 6bed0e8d13cb834fab97dc0265ef7d46a2caea97
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599734"
---
# <span data-ttu-id="916ad-102">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="916ad-102">Compare-Object</span></span>

## <span data-ttu-id="916ad-103">構文</span><span class="sxs-lookup"><span data-stu-id="916ad-103">Synopsis</span></span>
<span data-ttu-id="916ad-104">2 つのオブジェクトのセットを比較します。</span><span class="sxs-lookup"><span data-stu-id="916ad-104">Compares two sets of objects.</span></span>

## <span data-ttu-id="916ad-105">構文</span><span class="sxs-lookup"><span data-stu-id="916ad-105">Syntax</span></span>

```
Compare-Object [-ReferenceObject] <PSObject[]> [-DifferenceObject] <PSObject[]>
 [-SyncWindow <Int32>] [-Property <Object[]>] [-ExcludeDifferent] [-IncludeEqual] [-PassThru]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="916ad-106">説明</span><span class="sxs-lookup"><span data-stu-id="916ad-106">Description</span></span>

<span data-ttu-id="916ad-107">コマンドレットでは、 `Compare-Object` 2 つのオブジェクトのセットを比較します。</span><span class="sxs-lookup"><span data-stu-id="916ad-107">The `Compare-Object` cmdlet compares two sets of objects.</span></span> <span data-ttu-id="916ad-108">オブジェクトの1つのセットが **参照** で、もう一方のオブジェクトセットが **違い** ます。</span><span class="sxs-lookup"><span data-stu-id="916ad-108">One set of objects is the **reference**, and the other set of objects is the **difference**.</span></span>

<span data-ttu-id="916ad-109">`Compare-Object` オブジェクト全体を比較するために使用できるメソッドがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="916ad-109">`Compare-Object` checks for available methods of comparing a whole object.</span></span> <span data-ttu-id="916ad-110">適切なメソッドが見つからない場合は、入力オブジェクトの **ToString ()** メソッドを呼び出し、文字列の結果を比較します。</span><span class="sxs-lookup"><span data-stu-id="916ad-110">If it can't find a suitable method, it calls the **ToString()** methods of the input objects and compares the string results.</span></span> <span data-ttu-id="916ad-111">比較に使用する1つ以上のプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="916ad-111">You can provide one or more properties to be used for comparison.</span></span> <span data-ttu-id="916ad-112">プロパティが指定されている場合、コマンドレットはこれらのプロパティの値のみを比較します。</span><span class="sxs-lookup"><span data-stu-id="916ad-112">When properties are provided, the cmdlet compares the values of those properties only.</span></span>

<span data-ttu-id="916ad-113">比較の結果は、プロパティ値が **参照** オブジェクトにのみ表示されるか ()、 `<=` または **差分** オブジェクト () にのみ表示されるかを示し `=>` ます。</span><span class="sxs-lookup"><span data-stu-id="916ad-113">The result of the comparison indicates whether a property value appeared only in the **reference** object (`<=`) or only in the **difference** object (`=>`).</span></span> <span data-ttu-id="916ad-114">**Includeequal** パラメーターが使用されている場合、( `==` ) は、値が両方のオブジェクトにあることを示します。</span><span class="sxs-lookup"><span data-stu-id="916ad-114">If the **IncludeEqual** parameter is used, (`==`) indicates the value is in both objects.</span></span>

<span data-ttu-id="916ad-115">**参照** または **差分** オブジェクトが null () の場合 `$null` 、は `Compare-Object` 終了エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="916ad-115">If the **reference** or the **difference** objects are null (`$null`), `Compare-Object` generates a terminating error.</span></span>

<span data-ttu-id="916ad-116">いくつかの例では、スプラッティングを使用して、コードサンプルの行の長さを減らしています。</span><span class="sxs-lookup"><span data-stu-id="916ad-116">Some examples use splatting to reduce the line length of the code samples.</span></span> <span data-ttu-id="916ad-117">詳細については、「 [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="916ad-117">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="916ad-118">例</span><span class="sxs-lookup"><span data-stu-id="916ad-118">Examples</span></span>

### <span data-ttu-id="916ad-119">例 1-2 つのテキストファイルの内容を比較する</span><span class="sxs-lookup"><span data-stu-id="916ad-119">Example 1 - Compare the content of two text files</span></span>

<span data-ttu-id="916ad-120">この例では、2つのテキストファイルの内容を比較します。</span><span class="sxs-lookup"><span data-stu-id="916ad-120">This example compares the contents of two text files.</span></span> <span data-ttu-id="916ad-121">この例では、次の2つのテキストファイルを使用します。それぞれの値は別々の行にあります。</span><span class="sxs-lookup"><span data-stu-id="916ad-121">The example uses the following two text files, with each value on a separate line.</span></span>

- <span data-ttu-id="916ad-122">`Testfile1.txt` には、dog、squirrel、および鳥の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="916ad-122">`Testfile1.txt` contains the values: dog, squirrel, and bird.</span></span>
- <span data-ttu-id="916ad-123">`Testfile2.txt` には、cat、鳥、および racoon の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="916ad-123">`Testfile2.txt` contains the values: cat, bird, and racoon.</span></span>

<span data-ttu-id="916ad-124">出力には、ファイル間で異なる行のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="916ad-124">The output displays only the lines that are different between the files.</span></span> <span data-ttu-id="916ad-125">`Testfile1.txt` は **参照** オブジェクト () で、 `<=` `Testfile2.txt` は **相違** オブジェクト ( `=>` ) です。</span><span class="sxs-lookup"><span data-stu-id="916ad-125">`Testfile1.txt` is the **reference** object (`<=`) and `Testfile2.txt`is the **difference** object (`=>`).</span></span> <span data-ttu-id="916ad-126">両方のファイルに表示されるコンテンツを含む行は表示されません。</span><span class="sxs-lookup"><span data-stu-id="916ad-126">Lines with content that appear in both files aren't displayed.</span></span>

```powershell
Compare-Object -ReferenceObject (Get-Content -Path C:\Test\Testfile1.txt) -DifferenceObject (Get-Content -Path C:\Test\Testfile2.txt)
```

```Output
InputObject SideIndicator
----------- -------------
cat         =>
racoon      =>
dog         <=
squirrel    <=
```

### <span data-ttu-id="916ad-127">例 2-コンテンツの各行を比較し、その違いを除外する</span><span class="sxs-lookup"><span data-stu-id="916ad-127">Example 2 - Compare each line of content and exclude the differences</span></span>

<span data-ttu-id="916ad-128">この例では、 **excludedifferent** パラメーターを使用して、2つのテキストファイルの内容の各行を比較します。</span><span class="sxs-lookup"><span data-stu-id="916ad-128">This example uses the **ExcludeDifferent** parameter to compare each line of content in two text files.</span></span>

<span data-ttu-id="916ad-129">PowerShell 7.1 の時点で、 **Excludedifferent** パラメーターを使用すると、 **includeequal** が推論され、出力には両方のファイルに含まれる行のみが含まれます ( **sideindicator** () を参照 `==` )。</span><span class="sxs-lookup"><span data-stu-id="916ad-129">As of PowerShell 7.1, when using the **ExcludeDifferent** parameter, **IncludeEqual** is inferred and the output only contains lines contained in both files, as shown by the **SideIndicator** (`==`).</span></span>

```powershell
$objects = @{
  ReferenceObject = (Get-Content -Path C:\Test\Testfile1.txt)
  DifferenceObject = (Get-Content -Path C:\Test\Testfile2.txt)
}
Compare-Object @objects -ExcludeDifferent
```

```Output
InputObject SideIndicator
----------- -------------
bird        ==
```

<a id="ex3" />

### <span data-ttu-id="916ad-130">例 3-PassThru パラメーターを使用する場合の相違点の表示</span><span class="sxs-lookup"><span data-stu-id="916ad-130">Example 3 - Show the difference when using the PassThru parameter</span></span>

<span data-ttu-id="916ad-131">通常、は、 `Compare-Object` 次のプロパティを持つ **Pscustomobject** 種類を返します。</span><span class="sxs-lookup"><span data-stu-id="916ad-131">Normally, `Compare-Object` returns a **PSCustomObject** type with the following properties:</span></span>

- <span data-ttu-id="916ad-132">比較対象の **InputObject**</span><span class="sxs-lookup"><span data-stu-id="916ad-132">The **InputObject** being compared</span></span>
- <span data-ttu-id="916ad-133">出力が属する入力オブジェクトを示す **Sideindicator** プロパティ</span><span class="sxs-lookup"><span data-stu-id="916ad-133">The **SideIndicator** property showing which input object the output belongs to</span></span>

<span data-ttu-id="916ad-134">**PassThru** パラメーターを使用する場合、オブジェクトの **型** は変更されませんが、返されたオブジェクトのインスタンスには、 **sideindicator** という名前の追加の **プロパティ** があります。</span><span class="sxs-lookup"><span data-stu-id="916ad-134">When you use the **PassThru** parameter, the **Type** of the object is not changed but the instance of the object returned has an added **NoteProperty** named **SideIndicator**.</span></span> <span data-ttu-id="916ad-135">**Sideindicator** は、出力が属する入力オブジェクトを示します。</span><span class="sxs-lookup"><span data-stu-id="916ad-135">**SideIndicator** shows which input object the output belongs to.</span></span>

<span data-ttu-id="916ad-136">次の例は、さまざまな出力の種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="916ad-136">The following examples shows the different output types.</span></span>

```powershell
$a = $True
Compare-Object -IncludeEqual $a $a
(Compare-Object -IncludeEqual $a $a) | Get-Member
```

```Output
InputObject SideIndicator
----------- -------------
       True ==

   TypeName: System.Management.Automation.PSCustomObject
Name          MemberType   Definition
----          ----------   ----------
Equals        Method       bool Equals(System.Object obj)
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
ToString      Method       string ToString()
InputObject   NoteProperty System.Boolean InputObject=True
SideIndicator NoteProperty string SideIndicator===
```

```powershell
Compare-Object -IncludeEqual $a $a -PassThru
(Compare-Object -IncludeEqual $a $a -PassThru) | Get-Member
```

```Output
True

   TypeName: System.Boolean
Name          MemberType   Definition
----          ----------   ----------
CompareTo     Method       int CompareTo(System.Object obj), int CompareTo(bool value), int IComparable.CompareTo(Syst
Equals        Method       bool Equals(System.Object obj), bool Equals(bool obj), bool IEquatable[bool].Equals(bool ot
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
GetTypeCode   Method       System.TypeCode GetTypeCode(), System.TypeCode IConvertible.GetTypeCode()
ToBoolean     Method       bool IConvertible.ToBoolean(System.IFormatProvider provider)
ToByte        Method       byte IConvertible.ToByte(System.IFormatProvider provider)
ToChar        Method       char IConvertible.ToChar(System.IFormatProvider provider)
ToDateTime    Method       datetime IConvertible.ToDateTime(System.IFormatProvider provider)
ToDecimal     Method       decimal IConvertible.ToDecimal(System.IFormatProvider provider)
ToDouble      Method       double IConvertible.ToDouble(System.IFormatProvider provider)
ToInt16       Method       short IConvertible.ToInt16(System.IFormatProvider provider)
ToInt32       Method       int IConvertible.ToInt32(System.IFormatProvider provider)
ToInt64       Method       long IConvertible.ToInt64(System.IFormatProvider provider)
ToSByte       Method       sbyte IConvertible.ToSByte(System.IFormatProvider provider)
ToSingle      Method       float IConvertible.ToSingle(System.IFormatProvider provider)
ToString      Method       string ToString(), string ToString(System.IFormatProvider provider), string IConvertible.To
ToType        Method       System.Object IConvertible.ToType(type conversionType, System.IFormatProvider provider)
ToUInt16      Method       ushort IConvertible.ToUInt16(System.IFormatProvider provider)
ToUInt32      Method       uint IConvertible.ToUInt32(System.IFormatProvider provider)
ToUInt64      Method       ulong IConvertible.ToUInt64(System.IFormatProvider provider)
TryFormat     Method       bool TryFormat(System.Span[char] destination, [ref] int charsWritten)
SideIndicator NoteProperty string SideIndicator===
```

<span data-ttu-id="916ad-137">**PassThru** を使用する場合は、元のオブジェクトの **型 (system.string**) が返されます。</span><span class="sxs-lookup"><span data-stu-id="916ad-137">When using **PassThru**, the original object type (**System.Boolean**) is returned.</span></span> <span data-ttu-id="916ad-138">System.string オブジェクトの既定の形式によって表示される出力で、 **Sideindicator** プロパティが表示されないことに注意して **ください。**</span><span class="sxs-lookup"><span data-stu-id="916ad-138">Note how the output displayed by the default format for **System.Boolean** objects didn't display the **SideIndicator** property.</span></span> <span data-ttu-id="916ad-139">ただし **、返される** system.string オブジェクトには、追加された **"メモ" プロパティ** があります。</span><span class="sxs-lookup"><span data-stu-id="916ad-139">However, the returned **System.Boolean** object has the added **NoteProperty**.</span></span>

### <span data-ttu-id="916ad-140">例 4-プロパティを使用して2つの単純なオブジェクトを比較する</span><span class="sxs-lookup"><span data-stu-id="916ad-140">Example 4 - Compare two simple objects using properties</span></span>

<span data-ttu-id="916ad-141">この例では、長さが同じ2つの異なる文字列を比較します。</span><span class="sxs-lookup"><span data-stu-id="916ad-141">In this example, we compare two different string that have the same length.</span></span>

```powershell
Compare-Object -ReferenceObject 'abc' -DifferenceObject 'xyz' -Property Length -IncludeEqual
```

```Output
Length SideIndicator
------ -------------
     3 ==
```

### <span data-ttu-id="916ad-142">例 5-プロパティを使用して複合オブジェクトを比較する</span><span class="sxs-lookup"><span data-stu-id="916ad-142">Example 5 - Comparing complex objects using properties</span></span>

<span data-ttu-id="916ad-143">この例は、複雑なオブジェクトを比較する場合の動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="916ad-143">This example shows the behavior when comparing complex objects.</span></span> <span data-ttu-id="916ad-144">この例では、PowerShell の異なるインスタンスに対して2つの異なるプロセスオブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="916ad-144">In this example we store two different process objects for different instances of PowerShell.</span></span> <span data-ttu-id="916ad-145">両方の変数には、同じ名前のプロセスオブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="916ad-145">Both variables contain process objects with the same name.</span></span> <span data-ttu-id="916ad-146">**プロパティ** パラメーターを指定せずにオブジェクトを比較すると、コマンドレットはオブジェクトが等しいと見なされます。</span><span class="sxs-lookup"><span data-stu-id="916ad-146">When the objects are compared without specifying the **Property** parameter, the cmdlet considers the objects to be equal.</span></span> <span data-ttu-id="916ad-147">**InputObject** の値は、 **ToString ()** メソッドの結果と同じであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="916ad-147">Notice that the value of the **InputObject** is the same as the result of the **ToString()** method.</span></span> <span data-ttu-id="916ad-148">System.icomparable クラス **には** **IComparable** インターフェイスがないため、コマンドレットはオブジェクトを文字列に変換し、結果を比較します。</span><span class="sxs-lookup"><span data-stu-id="916ad-148">Since the **System.Diagnostics.Process** class does not have the **IComparable** interface, the cmdlet converts the objects to strings then compares the results.</span></span>

```powershell
PS> Get-Process pwsh

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    101   123.32     139.10      35.81   11168   1 pwsh
     89   107.55      66.97      11.44   17600   1 pwsh

PS> $a = Get-Process -Id 11168
PS> $b = Get-Process -Id 17600
PS> $a.ToString()
System.Diagnostics.Process (pwsh)
PS> $b.ToString()
System.Diagnostics.Process (pwsh)
PS> Compare-Object $a $b -IncludeEqual

InputObject                       SideIndicator
-----------                       -------------
System.Diagnostics.Process (pwsh) ==

PS> Compare-Object $a $b -Property ProcessName, Id, CPU

ProcessName    Id       CPU SideIndicator
-----------    --       --- -------------
pwsh        17600   11.4375 =>
pwsh        11168 36.203125 <=
```

<span data-ttu-id="916ad-149">比較するプロパティを指定すると、コマンドレットによって相違点が示されます。</span><span class="sxs-lookup"><span data-stu-id="916ad-149">When you specify properties to be compared, the cmdlet shows the differences.</span></span>

### <span data-ttu-id="916ad-150">例 6-IComparable を実装する複合オブジェクトを比較する</span><span class="sxs-lookup"><span data-stu-id="916ad-150">Example 6 - Comparing complex objects that implement IComparable</span></span>

<span data-ttu-id="916ad-151">オブジェクトが **IComparable** を実装する場合、コマンドレットはオブジェクトを比較する方法を検索します。オブジェクトの型が異なる場合 **は、比較するオブジェクトが** **referenceobject** の型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="916ad-151">If the object implements **IComparable**, the cmdlet searches for ways to compare the objects.If the objects are different types, the **Difference** object is converted to the type of the **ReferenceObject** then compared.</span></span>

<span data-ttu-id="916ad-152">この例では、文字列を **TimeSpan** オブジェクトと比較しています。</span><span class="sxs-lookup"><span data-stu-id="916ad-152">In this example, we are comparing a string to a **TimeSpan** object.</span></span> <span data-ttu-id="916ad-153">最初の例では、文字列は **TimeSpan** に変換されるため、オブジェクトは同じになります。</span><span class="sxs-lookup"><span data-stu-id="916ad-153">In the first case, the string is converted to a **TimeSpan** so the objects are equal.</span></span>

```powershell
Compare-Object ([TimeSpan]"0:0:1") "0:0:1" -IncludeEqual
```

```Output
InputObject SideIndicator
----------- -------------
00:00:01    ==
```

```powershell
Compare-Object "0:0:1" ([TimeSpan]"0:0:1")
```

```Output
InputObject SideIndicator
----------- -------------
00:00:01    =>
0:0:1       <=
```

<span data-ttu-id="916ad-154">2番目のケースでは、オブジェクトが異なるように、 **TimeSpan** が文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="916ad-154">In the second case, the **TimeSpan** is converted to a string so the object are different.</span></span>

## <span data-ttu-id="916ad-155">パラメーター</span><span class="sxs-lookup"><span data-stu-id="916ad-155">Parameters</span></span>

### <span data-ttu-id="916ad-156">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="916ad-156">-CaseSensitive</span></span>

<span data-ttu-id="916ad-157">比較においては、大文字と小文字が区別されることを示します。</span><span class="sxs-lookup"><span data-stu-id="916ad-157">Indicates that comparisons should be case-sensitive.</span></span>

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

### <span data-ttu-id="916ad-158">-Culture</span><span class="sxs-lookup"><span data-stu-id="916ad-158">-Culture</span></span>

<span data-ttu-id="916ad-159">比較に使用するカルチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="916ad-159">Specifies the culture to use for comparisons.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="916ad-160">-異なるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="916ad-160">-DifferenceObject</span></span>

<span data-ttu-id="916ad-161">**参照** オブジェクトと比較するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="916ad-161">Specifies the objects that are compared to the **reference** objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="916ad-162">-ExcludeDifferent</span><span class="sxs-lookup"><span data-stu-id="916ad-162">-ExcludeDifferent</span></span>

<span data-ttu-id="916ad-163">このコマンドレットによって、比較対象のオブジェクトの特性のみが表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="916ad-163">Indicates that this cmdlet displays only the characteristics of compared objects that are equal.</span></span> <span data-ttu-id="916ad-164">オブジェクト間の違いは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="916ad-164">The differences between the objects are discarded.</span></span>

<span data-ttu-id="916ad-165">**参照** オブジェクトと **差分** オブジェクトの間で一致する行のみを表示するには、 **excludedifferent** と **includeequal** を使用します。</span><span class="sxs-lookup"><span data-stu-id="916ad-165">Use **ExcludeDifferent** with **IncludeEqual** to display only the lines that match between the **reference** and **difference** objects.</span></span>

<span data-ttu-id="916ad-166">**Excludedifferent** が **includeequal** を指定せずに指定されている場合、出力はありません。</span><span class="sxs-lookup"><span data-stu-id="916ad-166">If **ExcludeDifferent** is specified without **IncludeEqual**, there's no output.</span></span>

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

### <span data-ttu-id="916ad-167">-IncludeEqual</span><span class="sxs-lookup"><span data-stu-id="916ad-167">-IncludeEqual</span></span>

<span data-ttu-id="916ad-168">**Includeequal** **参照** オブジェクトと **差分** オブジェクトの一致を表示します。</span><span class="sxs-lookup"><span data-stu-id="916ad-168">**IncludeEqual** displays the matches between the **reference** and **difference** objects.</span></span>

<span data-ttu-id="916ad-169">既定では、 **参照** オブジェクトと **差分** オブジェクトの違いも出力に含まれます。</span><span class="sxs-lookup"><span data-stu-id="916ad-169">By default, the output also includes the differences between the **reference** and **difference** objects.</span></span>

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

### <span data-ttu-id="916ad-170">-PassThru</span><span class="sxs-lookup"><span data-stu-id="916ad-170">-PassThru</span></span>

<span data-ttu-id="916ad-171">**PassThru** パラメーターを使用する場合、では、 `Compare-Object` 比較対象のオブジェクトを中心に **pscustomobject** 省略し、異なるオブジェクトを変更せずに返します。</span><span class="sxs-lookup"><span data-stu-id="916ad-171">When you use the **PassThru** parameter, `Compare-Object` omits the **PSCustomObject** wrapper around the compared objects and returns the differing objects, unchanged.</span></span>

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

### <span data-ttu-id="916ad-172">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="916ad-172">-Property</span></span>

<span data-ttu-id="916ad-173">比較する **参照** オブジェクトと **差分** オブジェクトのプロパティの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="916ad-173">Specifies an array of properties of the **reference** and **difference** objects to compare.</span></span>

<span data-ttu-id="916ad-174">**Property** パラメーターの値には、新しい集計プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="916ad-174">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="916ad-175">計算されるプロパティには、スクリプトブロックまたはハッシュテーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="916ad-175">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="916ad-176">有効なキーと値のペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="916ad-176">Valid key-value pairs are:</span></span>

- <span data-ttu-id="916ad-177">式 `<string>` または `<script block>`</span><span class="sxs-lookup"><span data-stu-id="916ad-177">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="916ad-178">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="916ad-178">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="916ad-179">-ReferenceObject</span><span class="sxs-lookup"><span data-stu-id="916ad-179">-ReferenceObject</span></span>

<span data-ttu-id="916ad-180">比較の参照として使用されるオブジェクトの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="916ad-180">Specifies an array of objects used as a reference for comparison.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="916ad-181">-SyncWindow</span><span class="sxs-lookup"><span data-stu-id="916ad-181">-SyncWindow</span></span>

<span data-ttu-id="916ad-182">`Compare-Object`オブジェクトのコレクション内で一致するものを検索するときに、隣接するオブジェクトの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="916ad-182">Specifies the number of adjacent objects that `Compare-Object` inspects while looking for a match in a collection of objects.</span></span> <span data-ttu-id="916ad-183">`Compare-Object` コレクション内の同じ位置にオブジェクトが見つからない場合に、隣接するオブジェクトを調べます。</span><span class="sxs-lookup"><span data-stu-id="916ad-183">`Compare-Object` examines adjacent objects when it doesn't find the object in the same position in a collection.</span></span> <span data-ttu-id="916ad-184">既定値はです `[Int32]::MaxValue` 。これは、が `Compare-Object` オブジェクトコレクション全体を検査することを意味します。</span><span class="sxs-lookup"><span data-stu-id="916ad-184">The default value is `[Int32]::MaxValue`, which means that `Compare-Object` examines the entire object collection.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: [Int32]::MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="916ad-185">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="916ad-185">CommonParameters</span></span>

<span data-ttu-id="916ad-186">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="916ad-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="916ad-187">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="916ad-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="916ad-188">入力</span><span class="sxs-lookup"><span data-stu-id="916ad-188">Inputs</span></span>

### <span data-ttu-id="916ad-189">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="916ad-189">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="916ad-190">オブジェクトをパイプライン **内で他のオブジェクトパラメーターに** 渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="916ad-190">You can send an object down the pipeline to the **DifferenceObject** parameter.</span></span>

## <span data-ttu-id="916ad-191">出力</span><span class="sxs-lookup"><span data-stu-id="916ad-191">Outputs</span></span>

### <span data-ttu-id="916ad-192">なし</span><span class="sxs-lookup"><span data-stu-id="916ad-192">None</span></span>

<span data-ttu-id="916ad-193">**参照** オブジェクトと **差分** オブジェクトが同じ場合、 **includeequal** パラメーターを使用しない限り、出力はありません。</span><span class="sxs-lookup"><span data-stu-id="916ad-193">If the **reference** object and the **difference** object are the same, there's no output, unless you use the **IncludeEqual** parameter.</span></span>

### <span data-ttu-id="916ad-194">システムの管理. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="916ad-194">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="916ad-195">オブジェクトが異なる場合、では、 `Compare-Object` ラッパー内の異なるオブジェクトをラップし `PSCustomObject` て、 **sideindicator** プロパティを使用して相違点を参照します。</span><span class="sxs-lookup"><span data-stu-id="916ad-195">If the objects are different, `Compare-Object` wraps the differing objects in a `PSCustomObject` wrapper with a **SideIndicator** property to reference the differences.</span></span>

<span data-ttu-id="916ad-196">**PassThru** パラメーターを使用する場合、オブジェクトの **型** は変更されませんが、返されたオブジェクトのインスタンスには、 **sideindicator** という名前の追加の **プロパティ** があります。</span><span class="sxs-lookup"><span data-stu-id="916ad-196">When you use the **PassThru** parameter, the **Type** of the object is not changed but the instance of the object returned has an added **NoteProperty** named **SideIndicator**.</span></span> <span data-ttu-id="916ad-197">**Sideindicator** は、出力が属する入力オブジェクトを示します。</span><span class="sxs-lookup"><span data-stu-id="916ad-197">**SideIndicator** shows which input object the output belongs to.</span></span>

## <span data-ttu-id="916ad-198">メモ</span><span class="sxs-lookup"><span data-stu-id="916ad-198">Notes</span></span>

<span data-ttu-id="916ad-199">**PassThru** パラメーターを使用する場合、コンソールに表示される出力には、 **sideindicator** プロパティが含まれないことがあります。</span><span class="sxs-lookup"><span data-stu-id="916ad-199">When using the **PassThru** parameter, the output displayed in the console may not include the **SideIndicator** property.</span></span> <span data-ttu-id="916ad-200">によって出力されるオブジェクト型のの既定の書式ビューに `Compare-Object` は、 **sideindicator** プロパティは含まれません。</span><span class="sxs-lookup"><span data-stu-id="916ad-200">The default format view of the for the object type output by `Compare-Object` does not include the **SideIndicator** property.</span></span> <span data-ttu-id="916ad-201">詳細については、この記事の [例 3](#ex3) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="916ad-201">For more information see [Example 3](#ex3) in this article.</span></span>

## <span data-ttu-id="916ad-202">関連リンク</span><span class="sxs-lookup"><span data-stu-id="916ad-202">Related links</span></span>

[<span data-ttu-id="916ad-203">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="916ad-203">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="916ad-204">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="916ad-204">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="916ad-205">Group-Object</span><span class="sxs-lookup"><span data-stu-id="916ad-205">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="916ad-206">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="916ad-206">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="916ad-207">New-Object</span><span class="sxs-lookup"><span data-stu-id="916ad-207">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="916ad-208">Select-Object</span><span class="sxs-lookup"><span data-stu-id="916ad-208">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="916ad-209">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="916ad-209">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="916ad-210">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="916ad-210">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="916ad-211">Where-Object</span><span class="sxs-lookup"><span data-stu-id="916ad-211">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)

[<span data-ttu-id="916ad-212">Get-Process</span><span class="sxs-lookup"><span data-stu-id="916ad-212">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)
