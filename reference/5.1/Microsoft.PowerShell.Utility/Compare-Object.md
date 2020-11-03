---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/compare-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compare-Object
ms.openlocfilehash: 994bed44d9632ad836f204ceafd6c7493591b91a
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "93225200"
---
# <span data-ttu-id="38b65-103">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="38b65-103">Compare-Object</span></span>

## <span data-ttu-id="38b65-104">構文</span><span class="sxs-lookup"><span data-stu-id="38b65-104">Synopsis</span></span>
<span data-ttu-id="38b65-105">2 つのオブジェクトのセットを比較します。</span><span class="sxs-lookup"><span data-stu-id="38b65-105">Compares two sets of objects.</span></span>

## <span data-ttu-id="38b65-106">構文</span><span class="sxs-lookup"><span data-stu-id="38b65-106">Syntax</span></span>

```
Compare-Object [-ReferenceObject] <PSObject[]> [-DifferenceObject] <PSObject[]>
 [-SyncWindow <Int32>] [-Property <Object[]>] [-ExcludeDifferent] [-IncludeEqual] [-PassThru]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="38b65-107">説明</span><span class="sxs-lookup"><span data-stu-id="38b65-107">Description</span></span>

<span data-ttu-id="38b65-108">コマンドレットでは、 `Compare-Object` 2 つのオブジェクトのセットを比較します。</span><span class="sxs-lookup"><span data-stu-id="38b65-108">The `Compare-Object` cmdlet compares two sets of objects.</span></span> <span data-ttu-id="38b65-109">オブジェクトの1つのセットが **参照** で、もう一方のオブジェクトセットが **違い** ます。</span><span class="sxs-lookup"><span data-stu-id="38b65-109">One set of objects is the **reference** , and the other set of objects is the **difference**.</span></span>

<span data-ttu-id="38b65-110">`Compare-Object` オブジェクト全体を比較するために使用できるメソッドがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="38b65-110">`Compare-Object` checks for available methods of comparing a whole object.</span></span> <span data-ttu-id="38b65-111">適切なメソッドが見つからない場合は、入力オブジェクトの **ToString ()** メソッドを呼び出し、文字列の結果を比較します。</span><span class="sxs-lookup"><span data-stu-id="38b65-111">If it can't find a suitable method, it calls the **ToString()** methods of the input objects and compares the string results.</span></span> <span data-ttu-id="38b65-112">比較に使用する1つ以上のプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="38b65-112">You can provide one or more properties to be used for comparison.</span></span> <span data-ttu-id="38b65-113">プロパティが指定されている場合、コマンドレットはこれらのプロパティの値のみを比較します。</span><span class="sxs-lookup"><span data-stu-id="38b65-113">When properties are provided, the cmdlet compares the values of those properties only.</span></span>

<span data-ttu-id="38b65-114">比較の結果は、プロパティ値が **参照** オブジェクトにのみ表示されるか ()、 `<=` または **差分** オブジェクト () にのみ表示されるかを示し `=>` ます。</span><span class="sxs-lookup"><span data-stu-id="38b65-114">The result of the comparison indicates whether a property value appeared only in the **reference** object (`<=`) or only in the **difference** object (`=>`).</span></span> <span data-ttu-id="38b65-115">**Includeequal** パラメーターが使用されている場合、( `==` ) は、値が両方のオブジェクトにあることを示します。</span><span class="sxs-lookup"><span data-stu-id="38b65-115">If the **IncludeEqual** parameter is used, (`==`) indicates the value is in both objects.</span></span>

<span data-ttu-id="38b65-116">**参照** または **差分** オブジェクトが null () の場合 `$null` 、は `Compare-Object` 終了エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="38b65-116">If the **reference** or the **difference** objects are null (`$null`), `Compare-Object` generates a terminating error.</span></span>

<span data-ttu-id="38b65-117">いくつかの例では、スプラッティングを使用して、コードサンプルの行の長さを減らしています。</span><span class="sxs-lookup"><span data-stu-id="38b65-117">Some examples use splatting to reduce the line length of the code samples.</span></span> <span data-ttu-id="38b65-118">詳細については、「 [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b65-118">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="38b65-119">例</span><span class="sxs-lookup"><span data-stu-id="38b65-119">Examples</span></span>

### <span data-ttu-id="38b65-120">例 1-2 つのテキストファイルの内容を比較する</span><span class="sxs-lookup"><span data-stu-id="38b65-120">Example 1 - Compare the content of two text files</span></span>

<span data-ttu-id="38b65-121">この例では、2つのテキストファイルの内容を比較します。</span><span class="sxs-lookup"><span data-stu-id="38b65-121">This example compares the contents of two text files.</span></span> <span data-ttu-id="38b65-122">この例では、次の2つのテキストファイルを使用します。それぞれの値は別々の行にあります。</span><span class="sxs-lookup"><span data-stu-id="38b65-122">The example uses the following two text files, with each value on a separate line.</span></span>

- <span data-ttu-id="38b65-123">`Testfile1.txt` には、dog、squirrel、および鳥の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="38b65-123">`Testfile1.txt` contains the values: dog, squirrel, and bird.</span></span>
- <span data-ttu-id="38b65-124">`Testfile2.txt` には、cat、鳥、および racoon の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="38b65-124">`Testfile2.txt` contains the values: cat, bird, and racoon.</span></span>

<span data-ttu-id="38b65-125">出力には、ファイル間で異なる行のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b65-125">The output displays only the lines that are different between the files.</span></span> <span data-ttu-id="38b65-126">`Testfile1.txt` は **参照** オブジェクト () で、 `<=` `Testfile2.txt` は **相違** オブジェクト ( `=>` ) です。</span><span class="sxs-lookup"><span data-stu-id="38b65-126">`Testfile1.txt` is the **reference** object (`<=`) and `Testfile2.txt`is the **difference** object (`=>`).</span></span> <span data-ttu-id="38b65-127">両方のファイルに表示されるコンテンツを含む行は表示されません。</span><span class="sxs-lookup"><span data-stu-id="38b65-127">Lines with content that appear in both files aren't displayed.</span></span>

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

### <span data-ttu-id="38b65-128">例 2-コンテンツの各行を比較し、その違いを除外する</span><span class="sxs-lookup"><span data-stu-id="38b65-128">Example 2 - Compare each line of content and exclude the differences</span></span>

<span data-ttu-id="38b65-129">この例では、 **Includeequal** と **excludedifferent** パラメーターを使用して、2つのテキストファイルの内容の各行を比較します。</span><span class="sxs-lookup"><span data-stu-id="38b65-129">This example uses the **IncludeEqual** and **ExcludeDifferent** parameters to compare each line of content in two text files.</span></span>

<span data-ttu-id="38b65-130">コマンドは **Excludedifferent** パラメーターを使用するため、出力には両方のファイルに含まれている行のみが含まれます ( **sideindicator** () を参照 `==` )。</span><span class="sxs-lookup"><span data-stu-id="38b65-130">Because the command uses the **ExcludeDifferent** parameter, the output only contains lines contained in both files, as shown by the **SideIndicator** (`==`).</span></span>

```powershell
$objects = @{
  ReferenceObject = (Get-Content -Path C:\Test\Testfile1.txt)
  DifferenceObject = (Get-Content -Path C:\Test\Testfile2.txt)
}
Compare-Object @objects -IncludeEqual -ExcludeDifferent
```

```Output
InputObject SideIndicator
----------- -------------
bird        ==
```

<a id="ex3" />

### <span data-ttu-id="38b65-131">例 3-PassThru パラメーターを使用する場合の相違点の表示</span><span class="sxs-lookup"><span data-stu-id="38b65-131">Example 3 - Show the difference when using the PassThru parameter</span></span>

<span data-ttu-id="38b65-132">通常、は、 `Compare-Object` 次のプロパティを持つ **Pscustomobject** 種類を返します。</span><span class="sxs-lookup"><span data-stu-id="38b65-132">Normally, `Compare-Object` returns a **PSCustomObject** type with the following properties:</span></span>

- <span data-ttu-id="38b65-133">比較対象の **InputObject**</span><span class="sxs-lookup"><span data-stu-id="38b65-133">The **InputObject** being compared</span></span>
- <span data-ttu-id="38b65-134">出力が属する入力オブジェクトを示す **Sideindicator** プロパティ</span><span class="sxs-lookup"><span data-stu-id="38b65-134">The **SideIndicator** property showing which input object the output belongs to</span></span>

<span data-ttu-id="38b65-135">**PassThru** パラメーターを使用する場合、オブジェクトの **型** は変更されませんが、返されたオブジェクトのインスタンスには、 **sideindicator** という名前の追加の **プロパティ** があります。</span><span class="sxs-lookup"><span data-stu-id="38b65-135">When you use the **PassThru** parameter, the **Type** of the object is not changed but the instance of the object returned has an added **NoteProperty** named **SideIndicator**.</span></span> <span data-ttu-id="38b65-136">**Sideindicator** は、出力が属する入力オブジェクトを示します。</span><span class="sxs-lookup"><span data-stu-id="38b65-136">**SideIndicator** shows which input object the output belongs to.</span></span>

<span data-ttu-id="38b65-137">次の例は、さまざまな出力の種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="38b65-137">The following examples shows the different output types.</span></span>

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

<span data-ttu-id="38b65-138">**PassThru** を使用する場合は、元のオブジェクトの **型 (system.string** ) が返されます。</span><span class="sxs-lookup"><span data-stu-id="38b65-138">When using **PassThru** , the original object type ( **System.Boolean** ) is returned.</span></span> <span data-ttu-id="38b65-139">System.string オブジェクトの既定の形式によって表示される出力で、 **Sideindicator** プロパティが表示されないことに注意して **ください。**</span><span class="sxs-lookup"><span data-stu-id="38b65-139">Note how the output displayed by the default format for **System.Boolean** objects didn't display the **SideIndicator** property.</span></span> <span data-ttu-id="38b65-140">ただし **、返される** system.string オブジェクトには、追加された **"メモ" プロパティ** があります。</span><span class="sxs-lookup"><span data-stu-id="38b65-140">However, the returned **System.Boolean** object has the added **NoteProperty**.</span></span>

### <span data-ttu-id="38b65-141">例 4-プロパティを使用して2つの単純なオブジェクトを比較する</span><span class="sxs-lookup"><span data-stu-id="38b65-141">Example 4 - Compare two simple objects using properties</span></span>

<span data-ttu-id="38b65-142">この例では、長さが同じ2つの異なる文字列を比較します。</span><span class="sxs-lookup"><span data-stu-id="38b65-142">In this example, we compare two different string that have the same length.</span></span>

```powershell
Compare-Object -ReferenceObject 'abc' -DifferenceObject 'xyz' -Property Length -IncludeEqual
```

```Output
Length SideIndicator
------ -------------
     3 ==
```

### <span data-ttu-id="38b65-143">例 5-プロパティを使用して複合オブジェクトを比較する</span><span class="sxs-lookup"><span data-stu-id="38b65-143">Example 5 - Comparing complex objects using properties</span></span>

<span data-ttu-id="38b65-144">この例は、複雑なオブジェクトを比較する場合の動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="38b65-144">This example shows the behavior when comparing complex objects.</span></span> <span data-ttu-id="38b65-145">この例では、PowerShell の異なるインスタンスに対して2つの異なるプロセスオブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="38b65-145">In this example we store two different process objects for different instances of PowerShell.</span></span> <span data-ttu-id="38b65-146">両方の変数には、同じ名前のプロセスオブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="38b65-146">Both variables contain process objects with the same name.</span></span> <span data-ttu-id="38b65-147">**プロパティ** パラメーターを指定せずにオブジェクトを比較すると、コマンドレットはオブジェクトが等しいと見なされます。</span><span class="sxs-lookup"><span data-stu-id="38b65-147">When the objects are compared without specifying the **Property** parameter, the cmdlet considers the objects to be equal.</span></span> <span data-ttu-id="38b65-148">**InputObject** の値は、 **ToString ()** メソッドの結果と同じであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="38b65-148">Notice that the value of the **InputObject** is the same as the result of the **ToString()** method.</span></span> <span data-ttu-id="38b65-149">System.icomparable クラス **には** **IComparable** インターフェイスがないため、コマンドレットはオブジェクトを文字列に変換し、結果を比較します。</span><span class="sxs-lookup"><span data-stu-id="38b65-149">Since the **System.Diagnostics.Process** class does not have the **IComparable** interface, the cmdlet converts the objects to strings then compares the results.</span></span>

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

<span data-ttu-id="38b65-150">比較するプロパティを指定すると、コマンドレットによって相違点が示されます。</span><span class="sxs-lookup"><span data-stu-id="38b65-150">When you specify properties to be compared, the cmdlet shows the differences.</span></span>

### <span data-ttu-id="38b65-151">例 6-IComparable を実装する複合オブジェクトを比較する</span><span class="sxs-lookup"><span data-stu-id="38b65-151">Example 6 - Comparing complex objects that implement IComparable</span></span>

<span data-ttu-id="38b65-152">オブジェクトが **IComparable** を実装する場合、コマンドレットはオブジェクトを比較する方法を検索します。オブジェクトの型が異なる場合 **は、比較するオブジェクトが** **referenceobject** の型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="38b65-152">If the object implements **IComparable** , the cmdlet searches for ways to compare the objects.If the objects are different types, the **Difference** object is converted to the type of the **ReferenceObject** then compared.</span></span>

<span data-ttu-id="38b65-153">この例では、文字列を **TimeSpan** オブジェクトと比較しています。</span><span class="sxs-lookup"><span data-stu-id="38b65-153">In this example, we are comparing a string to a **TimeSpan** object.</span></span> <span data-ttu-id="38b65-154">最初の例では、文字列は **TimeSpan** に変換されるため、オブジェクトは同じになります。</span><span class="sxs-lookup"><span data-stu-id="38b65-154">In the first case, the string is converted to a **TimeSpan** so the objects are equal.</span></span>

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

<span data-ttu-id="38b65-155">2番目のケースでは、オブジェクトが異なるように、 **TimeSpan** が文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="38b65-155">In the second case, the **TimeSpan** is converted to a string so the object are different.</span></span>

## <span data-ttu-id="38b65-156">パラメーター</span><span class="sxs-lookup"><span data-stu-id="38b65-156">Parameters</span></span>

### <span data-ttu-id="38b65-157">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="38b65-157">-CaseSensitive</span></span>

<span data-ttu-id="38b65-158">比較においては、大文字と小文字が区別されることを示します。</span><span class="sxs-lookup"><span data-stu-id="38b65-158">Indicates that comparisons should be case-sensitive.</span></span>

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

### <span data-ttu-id="38b65-159">-Culture</span><span class="sxs-lookup"><span data-stu-id="38b65-159">-Culture</span></span>

<span data-ttu-id="38b65-160">比較に使用するカルチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="38b65-160">Specifies the culture to use for comparisons.</span></span>

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

### <span data-ttu-id="38b65-161">-異なるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="38b65-161">-DifferenceObject</span></span>

<span data-ttu-id="38b65-162">**参照** オブジェクトと比較するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="38b65-162">Specifies the objects that are compared to the **reference** objects.</span></span>

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

### <span data-ttu-id="38b65-163">-ExcludeDifferent</span><span class="sxs-lookup"><span data-stu-id="38b65-163">-ExcludeDifferent</span></span>

<span data-ttu-id="38b65-164">このコマンドレットによって、比較対象のオブジェクトの特性のみが表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="38b65-164">Indicates that this cmdlet displays only the characteristics of compared objects that are equal.</span></span> <span data-ttu-id="38b65-165">オブジェクト間の違いは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="38b65-165">The differences between the objects are discarded.</span></span>

<span data-ttu-id="38b65-166">**参照** オブジェクトと **差分** オブジェクトの間で一致する行のみを表示するには、 **excludedifferent** と **includeequal** を使用します。</span><span class="sxs-lookup"><span data-stu-id="38b65-166">Use **ExcludeDifferent** with **IncludeEqual** to display only the lines that match between the **reference** and **difference** objects.</span></span>

<span data-ttu-id="38b65-167">**Excludedifferent** が **includeequal** を指定せずに指定されている場合、出力はありません。</span><span class="sxs-lookup"><span data-stu-id="38b65-167">If **ExcludeDifferent** is specified without **IncludeEqual** , there's no output.</span></span>

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

### <span data-ttu-id="38b65-168">-IncludeEqual</span><span class="sxs-lookup"><span data-stu-id="38b65-168">-IncludeEqual</span></span>

<span data-ttu-id="38b65-169">**Includeequal** **参照** オブジェクトと **差分** オブジェクトの一致を表示します。</span><span class="sxs-lookup"><span data-stu-id="38b65-169">**IncludeEqual** displays the matches between the **reference** and **difference** objects.</span></span>

<span data-ttu-id="38b65-170">既定では、 **参照** オブジェクトと **差分** オブジェクトの違いも出力に含まれます。</span><span class="sxs-lookup"><span data-stu-id="38b65-170">By default, the output also includes the differences between the **reference** and **difference** objects.</span></span>

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

### <span data-ttu-id="38b65-171">-PassThru</span><span class="sxs-lookup"><span data-stu-id="38b65-171">-PassThru</span></span>

<span data-ttu-id="38b65-172">**PassThru** パラメーターを使用する場合、では、 `Compare-Object` 比較対象のオブジェクトを中心に **pscustomobject** 省略し、異なるオブジェクトを変更せずに返します。</span><span class="sxs-lookup"><span data-stu-id="38b65-172">When you use the **PassThru** parameter, `Compare-Object` omits the **PSCustomObject** wrapper around the compared objects and returns the differing objects, unchanged.</span></span>

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

### <span data-ttu-id="38b65-173">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="38b65-173">-Property</span></span>

<span data-ttu-id="38b65-174">比較する **参照** オブジェクトと **差分** オブジェクトのプロパティの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="38b65-174">Specifies an array of properties of the **reference** and **difference** objects to compare.</span></span>

<span data-ttu-id="38b65-175">**Property** パラメーターの値には、新しい集計プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="38b65-175">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="38b65-176">計算されるプロパティには、スクリプトブロックまたはハッシュテーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="38b65-176">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="38b65-177">有効なキーと値のペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="38b65-177">Valid key-value pairs are:</span></span>

- <span data-ttu-id="38b65-178">式 `<string>` または `<script block>`</span><span class="sxs-lookup"><span data-stu-id="38b65-178">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="38b65-179">詳細については、「 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b65-179">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="38b65-180">-ReferenceObject</span><span class="sxs-lookup"><span data-stu-id="38b65-180">-ReferenceObject</span></span>

<span data-ttu-id="38b65-181">比較の参照として使用されるオブジェクトの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="38b65-181">Specifies an array of objects used as a reference for comparison.</span></span>

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

### <span data-ttu-id="38b65-182">-SyncWindow</span><span class="sxs-lookup"><span data-stu-id="38b65-182">-SyncWindow</span></span>

<span data-ttu-id="38b65-183">`Compare-Object`オブジェクトのコレクション内で一致するものを検索するときに、隣接するオブジェクトの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="38b65-183">Specifies the number of adjacent objects that `Compare-Object` inspects while looking for a match in a collection of objects.</span></span> <span data-ttu-id="38b65-184">`Compare-Object` コレクション内の同じ位置にオブジェクトが見つからない場合に、隣接するオブジェクトを調べます。</span><span class="sxs-lookup"><span data-stu-id="38b65-184">`Compare-Object` examines adjacent objects when it doesn't find the object in the same position in a collection.</span></span> <span data-ttu-id="38b65-185">既定値はです `[Int32]::MaxValue` 。これは、が `Compare-Object` オブジェクトコレクション全体を検査することを意味します。</span><span class="sxs-lookup"><span data-stu-id="38b65-185">The default value is `[Int32]::MaxValue`, which means that `Compare-Object` examines the entire object collection.</span></span>

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

### <span data-ttu-id="38b65-186">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="38b65-186">CommonParameters</span></span>

<span data-ttu-id="38b65-187">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="38b65-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="38b65-188">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b65-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="38b65-189">入力</span><span class="sxs-lookup"><span data-stu-id="38b65-189">Inputs</span></span>

### <span data-ttu-id="38b65-190">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="38b65-190">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="38b65-191">オブジェクトをパイプライン **内で他のオブジェクトパラメーターに** 渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="38b65-191">You can send an object down the pipeline to the **DifferenceObject** parameter.</span></span>

## <span data-ttu-id="38b65-192">出力</span><span class="sxs-lookup"><span data-stu-id="38b65-192">Outputs</span></span>

### <span data-ttu-id="38b65-193">なし</span><span class="sxs-lookup"><span data-stu-id="38b65-193">None</span></span>

<span data-ttu-id="38b65-194">**参照** オブジェクトと **差分** オブジェクトが同じ場合、 **includeequal** パラメーターを使用しない限り、出力はありません。</span><span class="sxs-lookup"><span data-stu-id="38b65-194">If the **reference** object and the **difference** object are the same, there's no output, unless you use the **IncludeEqual** parameter.</span></span>

### <span data-ttu-id="38b65-195">システムの管理. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="38b65-195">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="38b65-196">オブジェクトが異なる場合、では、 `Compare-Object` ラッパー内の異なるオブジェクトをラップし `PSCustomObject` て、 **sideindicator** プロパティを使用して相違点を参照します。</span><span class="sxs-lookup"><span data-stu-id="38b65-196">If the objects are different, `Compare-Object` wraps the differing objects in a `PSCustomObject` wrapper with a **SideIndicator** property to reference the differences.</span></span>

<span data-ttu-id="38b65-197">**PassThru** パラメーターを使用する場合、オブジェクトの **型** は変更されませんが、返されたオブジェクトのインスタンスには、 **sideindicator** という名前の追加の **プロパティ** があります。</span><span class="sxs-lookup"><span data-stu-id="38b65-197">When you use the **PassThru** parameter, the **Type** of the object is not changed but the instance of the object returned has an added **NoteProperty** named **SideIndicator**.</span></span> <span data-ttu-id="38b65-198">**Sideindicator** は、出力が属する入力オブジェクトを示します。</span><span class="sxs-lookup"><span data-stu-id="38b65-198">**SideIndicator** shows which input object the output belongs to.</span></span>

## <span data-ttu-id="38b65-199">メモ</span><span class="sxs-lookup"><span data-stu-id="38b65-199">Notes</span></span>

<span data-ttu-id="38b65-200">**PassThru** パラメーターを使用する場合、コンソールに表示される出力には、 **sideindicator** プロパティが含まれないことがあります。</span><span class="sxs-lookup"><span data-stu-id="38b65-200">When using the **PassThru** parameter, the output displayed in the console may not include the **SideIndicator** property.</span></span> <span data-ttu-id="38b65-201">によって出力されるオブジェクト型のの既定の書式ビューに `Compare-Object` は、 **sideindicator** プロパティは含まれません。</span><span class="sxs-lookup"><span data-stu-id="38b65-201">The default format view of the for the object type output by `Compare-Object` does not include the **SideIndicator** property.</span></span> <span data-ttu-id="38b65-202">詳細については、この記事の [例 3](#ex3) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b65-202">For more information see [Example 3](#ex3) in this article.</span></span>

## <span data-ttu-id="38b65-203">関連リンク</span><span class="sxs-lookup"><span data-stu-id="38b65-203">Related links</span></span>

[<span data-ttu-id="38b65-204">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="38b65-204">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="38b65-205">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="38b65-205">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="38b65-206">Group-Object</span><span class="sxs-lookup"><span data-stu-id="38b65-206">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="38b65-207">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="38b65-207">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="38b65-208">New-Object</span><span class="sxs-lookup"><span data-stu-id="38b65-208">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="38b65-209">Select-Object</span><span class="sxs-lookup"><span data-stu-id="38b65-209">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="38b65-210">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="38b65-210">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="38b65-211">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="38b65-211">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="38b65-212">Where-Object</span><span class="sxs-lookup"><span data-stu-id="38b65-212">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)

[<span data-ttu-id="38b65-213">Get-Process</span><span class="sxs-lookup"><span data-stu-id="38b65-213">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)
