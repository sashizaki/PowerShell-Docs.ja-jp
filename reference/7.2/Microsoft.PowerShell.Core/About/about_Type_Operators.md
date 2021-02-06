---
description: Microsoft .NET 型を操作する演算子について説明します。
Locale: en-US
ms.date: 10/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_type_operators?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Type_Operators
ms.openlocfilehash: 66687a2282cfd321146888daad92fef40ef6cb0a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599729"
---
# <a name="about-type-operators"></a><span data-ttu-id="60c63-103">型演算子の概要</span><span class="sxs-lookup"><span data-stu-id="60c63-103">About Type Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="60c63-104">概要</span><span class="sxs-lookup"><span data-stu-id="60c63-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="60c63-105">Microsoft .NET 型を操作する演算子について説明します。</span><span class="sxs-lookup"><span data-stu-id="60c63-105">Describes the operators that work with Microsoft .NET types.</span></span>

## <a name="long-description"></a><span data-ttu-id="60c63-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="60c63-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="60c63-107">ブール型の演算子 ( `-is` および `-isNot` ) は、オブジェクトが指定された .net 型のインスタンスであるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="60c63-107">The Boolean type operators (`-is` and `-isNot`) tell whether an object is an instance of a specified .NET type.</span></span> <span data-ttu-id="60c63-108">演算子は、 `-is` 型がと一致する場合は **TRUE** 、それ以外の場合は **FALSE** の値を返します。</span><span class="sxs-lookup"><span data-stu-id="60c63-108">The `-is` operator returns a value of **TRUE** if the type matches and a value of **FALSE** otherwise.</span></span> <span data-ttu-id="60c63-109">`-isNot`型がと一致する場合、演算子は値 **FALSE** を返します。それ以外の場合は **TRUE** の値を返します。</span><span class="sxs-lookup"><span data-stu-id="60c63-109">The `-isNot` operator returns a value of **FALSE** if the type matches and a value of **TRUE** otherwise.</span></span>

<span data-ttu-id="60c63-110">演算子は、 `-as` 入力オブジェクトから指定された .net 型への変換を試みます。</span><span class="sxs-lookup"><span data-stu-id="60c63-110">The `-as` operator tries to convert the input object to the specified .NET type.</span></span> <span data-ttu-id="60c63-111">成功した場合は、変換されたオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="60c63-111">If it succeeds, it returns the converted object.</span></span> <span data-ttu-id="60c63-112">失敗した場合は、を返し `$null` ます。</span><span class="sxs-lookup"><span data-stu-id="60c63-112">If it fails, it returns `$null`.</span></span> <span data-ttu-id="60c63-113">エラーは返されません。</span><span class="sxs-lookup"><span data-stu-id="60c63-113">It does not return an error.</span></span>

<span data-ttu-id="60c63-114">次の表に、PowerShell の型演算子を示します。</span><span class="sxs-lookup"><span data-stu-id="60c63-114">The following table lists the type operators in PowerShell.</span></span>

|<span data-ttu-id="60c63-115">演算子</span><span class="sxs-lookup"><span data-stu-id="60c63-115">Operator</span></span>|<span data-ttu-id="60c63-116">説明</span><span class="sxs-lookup"><span data-stu-id="60c63-116">Description</span></span>                |<span data-ttu-id="60c63-117">例</span><span class="sxs-lookup"><span data-stu-id="60c63-117">Example</span></span>                          |
|--------|---------------------------|---------------------------------|
|`-is`   |<span data-ttu-id="60c63-118">入力時に TRUE を返します</span><span class="sxs-lookup"><span data-stu-id="60c63-118">Returns TRUE when the input</span></span>|`(get-date) -is [DateTime]`      |
|        |<span data-ttu-id="60c63-119">はのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="60c63-119">is an instance of the</span></span>      |`True`                           |
|        |<span data-ttu-id="60c63-120">指定された .NET 型。</span><span class="sxs-lookup"><span data-stu-id="60c63-120">specified .NET type.</span></span>       |                                 |
|`-isNot`|<span data-ttu-id="60c63-121">入力時に TRUE を返します</span><span class="sxs-lookup"><span data-stu-id="60c63-121">Returns TRUE when the input</span></span>|`(get-date) -isNot [DateTime]`   |
|        |<span data-ttu-id="60c63-122">のインスタンスではありません。</span><span class="sxs-lookup"><span data-stu-id="60c63-122">not an instance of the</span></span>     |`False`                          |
|        |<span data-ttu-id="60c63-123">specified.NET 型。</span><span class="sxs-lookup"><span data-stu-id="60c63-123">specified.NET type.</span></span>        |                                 |
|`-as`   |<span data-ttu-id="60c63-124">入力をに変換します。</span><span class="sxs-lookup"><span data-stu-id="60c63-124">Converts the input to the</span></span>  |`"5/7/07" -as [DateTime]`        |
|        |<span data-ttu-id="60c63-125">指定された .NET 型。</span><span class="sxs-lookup"><span data-stu-id="60c63-125">specified .NET type.</span></span>       |`Monday, May 7, 2007 12:00:00 AM`|

<span data-ttu-id="60c63-126">型演算子の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="60c63-126">The syntax of the type operators is as follows:</span></span>

```powershell
<input> <operator> [.NET type]
```

<span data-ttu-id="60c63-127">また、次の構文を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="60c63-127">You can also use the following syntax:</span></span>

```powershell
<input> <operator> ".NET type"
```

<span data-ttu-id="60c63-128">.NET 型は、角かっこで囲んだ型名として、 `[DateTime]` または system.string 用やなどの文字列として書き込むことができます `"DateTime"` **。**</span><span class="sxs-lookup"><span data-stu-id="60c63-128">The .NET type can be written as a type name in brackets or a string, such as `[DateTime]` or `"DateTime"` for **System.DateTime**.</span></span> <span data-ttu-id="60c63-129">型が system 名前空間のルートにない場合は、オブジェクトの種類の完全な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="60c63-129">If the type is not at the root of the system namespace, specify the full name of the object type.</span></span> <span data-ttu-id="60c63-130">"System." を省略できます。</span><span class="sxs-lookup"><span data-stu-id="60c63-130">You can omit "System.".</span></span> <span data-ttu-id="60c63-131">たとえば、system.string **を指定する** には、 `[System.Diagnostics.Process]` 、 `[Diagnostics.Process]` 、またはを入力します `"Diagnostics.Process"` 。</span><span class="sxs-lookup"><span data-stu-id="60c63-131">For example, to specify **System.Diagnostics.Process**, enter `[System.Diagnostics.Process]`, `[Diagnostics.Process]`, or `"Diagnostics.Process"`.</span></span>

<span data-ttu-id="60c63-132">型演算子は、常に入力オブジェクト全体を操作します。</span><span class="sxs-lookup"><span data-stu-id="60c63-132">The type operators always operate on the input object as a whole.</span></span> <span data-ttu-id="60c63-133">つまり、入力オブジェクトがコレクションである場合は、コレクションの _要素_ の型ではなく、テストされる _コレクション_ 型です。</span><span class="sxs-lookup"><span data-stu-id="60c63-133">That is, if the input object is a collection, it is the _collection_ type that is tested, not the types of the collection's _elements_.</span></span>

### <a name="-isisnot-operators"></a><span data-ttu-id="60c63-134">-is/isNot 演算子</span><span class="sxs-lookup"><span data-stu-id="60c63-134">-is/isNot operators</span></span>

<span data-ttu-id="60c63-135">**ブール** 型の演算子 ( `-is` および `-isNot` ) は、入力がオブジェクトのコレクションであっても、常に **ブール** 値を返します。</span><span class="sxs-lookup"><span data-stu-id="60c63-135">The **Boolean** type operators (`-is` and `-isNot`) always return a **Boolean** value, even if the input is a collection of objects.</span></span>

<span data-ttu-id="60c63-136">`<input>`がと同じか、または .Net 型から _派生_ した型である場合、 `-is` 演算子はを返し `$True` ます。</span><span class="sxs-lookup"><span data-stu-id="60c63-136">If `<input>` is a type that is the same as or is _derived_ from the .NET Type, the `-is` operator returns `$True`.</span></span>

<span data-ttu-id="60c63-137">たとえば、 **DirectoryInfo** 型は、 **filesysteminfo** 型から派生します。</span><span class="sxs-lookup"><span data-stu-id="60c63-137">For example, the **DirectoryInfo** type is derived from the **FileSystemInfo** type.</span></span> <span data-ttu-id="60c63-138">したがって、両方の例で **True** が返されます。</span><span class="sxs-lookup"><span data-stu-id="60c63-138">Therefore, both of these examples return **True**.</span></span>

```powershell
PS> (Get-Item /) -is [System.IO.DirectoryInfo]
True
PS> (Get-Item /) -is [System.IO.FileSystemInfo]
True
```

<span data-ttu-id="60c63-139">`-is`が `<input>` 比較でインターフェイスを実装している場合、演算子はインターフェイスを照合することもできます。</span><span class="sxs-lookup"><span data-stu-id="60c63-139">The `-is` operator can also match interfaces if the `<input>` implements the interface in the comparison.</span></span> <span data-ttu-id="60c63-140">この例では、入力は配列です。</span><span class="sxs-lookup"><span data-stu-id="60c63-140">In this example, the input is an array.</span></span> <span data-ttu-id="60c63-141">配列は、system.string インターフェイスを実装 **します。**</span><span class="sxs-lookup"><span data-stu-id="60c63-141">Arrays implement the **System.Collections.IList** interface.</span></span>

```powershell
PS> 1, 2 -is [System.Collections.IList]
True
```

### <a name="-as-operator"></a><span data-ttu-id="60c63-142">-as 演算子</span><span class="sxs-lookup"><span data-stu-id="60c63-142">-as operator</span></span>

<span data-ttu-id="60c63-143">演算子は、 `-as` 入力オブジェクトから指定された .net 型への変換を試みます。</span><span class="sxs-lookup"><span data-stu-id="60c63-143">The `-as` operator tries to convert the input object to the specified .NET type.</span></span> <span data-ttu-id="60c63-144">成功した場合は、変換されたオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="60c63-144">If it succeeds, it returns the converted object.</span></span> <span data-ttu-id="60c63-145">失敗した場合は、を返し `$null` ます。</span><span class="sxs-lookup"><span data-stu-id="60c63-145">It if fails, it returns `$null`.</span></span> <span data-ttu-id="60c63-146">エラーは返されません。</span><span class="sxs-lookup"><span data-stu-id="60c63-146">It does not return an error.</span></span>

<span data-ttu-id="60c63-147">`<input>`が .Net 型から _派生_ した型である場合、は、 `-as` _渡さ_ れた入力オブジェクトを変更せずに返します。</span><span class="sxs-lookup"><span data-stu-id="60c63-147">If the `<input>` is a type that is _derived_ from the .NET Type `-as` _passes through_ returns input object unchanged.</span></span> <span data-ttu-id="60c63-148">たとえば、 **DirectoryInfo** 型は、 **filesysteminfo** 型から派生します。</span><span class="sxs-lookup"><span data-stu-id="60c63-148">For example, the **DirectoryInfo** type is derived from the **FileSystemInfo** type.</span></span> <span data-ttu-id="60c63-149">そのため、次の例では、オブジェクトの種類が変更されていません。</span><span class="sxs-lookup"><span data-stu-id="60c63-149">Therefore, the object type is unchanged in the following example:</span></span>

```powershell
PS> $fsroot = (Get-Item /) -as [System.IO.FileSystemInfo]
PS> $fsroot.GetType().FullName
System.IO.DirectoryInfo
```

#### <a name="converting-the-datetime-type-is-culture-sensitive"></a><span data-ttu-id="60c63-150">DateTime 型の変換はカルチャに依存します</span><span class="sxs-lookup"><span data-stu-id="60c63-150">Converting the DateTime type is culture-sensitive</span></span>

<span data-ttu-id="60c63-151">型キャストとは異なり、 `[DateTime]` 演算子を使用した型への変換は、 `-as` 現在のカルチャの規則に従って書式設定された文字列に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="60c63-151">Unlike type casting, converting to `[DateTime]` type using the `-as` operator only works with strings that are formatted according to the rules of the current culture.</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr-FR'
PS> '13/5/20' -as [datetime]

mercredi 13 mai 2020 00:00:00

PS> '05/13/20' -as [datetime]
PS> [datetime]'05/13/20'

mercredi 13 mai 2020 00:00:00

PS> [datetime]'13/05/20'
InvalidArgument: Cannot convert value "13/05/20" to type "System.DateTime".
Error: "String '13/05/20' was not recognized as a valid DateTime."
```

<span data-ttu-id="60c63-152">オブジェクトの .NET 型を検索するには、コマンドレットを使用し `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="60c63-152">To find the .NET type of an object, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="60c63-153">または、すべてのオブジェクトの **GetType** メソッドを、このメソッドの **FullName** プロパティと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="60c63-153">Or, use the **GetType** method of all the objects together with the **FullName** property of this method.</span></span> <span data-ttu-id="60c63-154">たとえば、次のステートメントは、コマンドの戻り値の型を取得し `Get-Culture` ます。</span><span class="sxs-lookup"><span data-stu-id="60c63-154">For example, the following statement gets the type of the return value of a `Get-Culture` command:</span></span>

```powershell
PS> (Get-Culture).GetType().FullName
System.Globalization.CultureInfo
```

## <a name="examples"></a><span data-ttu-id="60c63-155">例</span><span class="sxs-lookup"><span data-stu-id="60c63-155">EXAMPLES</span></span>

<span data-ttu-id="60c63-156">次の例では、型演算子の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="60c63-156">The following examples show some uses of the Type operators:</span></span>

```powershell
PS> 32 -is [Float]
False

PS> 32 -is "int"
True

PS> (get-date) -is [DateTime]
True

PS> "12/31/2007" -is [DateTime]
False

PS> "12/31/2007" -is [String]
True

PS> (get-process PowerShell)[0] -is [System.Diagnostics.Process]
True

PS> (get-command get-member) -is [System.Management.Automation.CmdletInfo]
True
```

<span data-ttu-id="60c63-157">次の例は、入力がオブジェクトのコレクションである場合、一致する型がコレクションの .NET 型であり、コレクション内の個々のオブジェクトの型ではないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="60c63-157">The following example shows that when the input is a collection of objects, the matching type is the .NET type of the collection, not the type of the individual objects in the collection.</span></span>

<span data-ttu-id="60c63-158">この例では、 `Get-Culture` コマンドレットとコマンドレットはどちらも、system.string `Get-UICulture` オブジェクトを返しますが、これらのオブジェクトのコレクションは system.object 配列です。 </span><span class="sxs-lookup"><span data-stu-id="60c63-158">In this example, although both the `Get-Culture` and `Get-UICulture` cmdlets return **System.Globalization.CultureInfo** objects, a collection of these objects is a System.Object array.</span></span>

```powershell
PS> (get-culture) -is [System.Globalization.CultureInfo]
True

PS> (get-uiculture) -is [System.Globalization.CultureInfo]
True

PS> (get-culture), (get-uiculture) -is [System.Globalization.CultureInfo]
False

PS> (get-culture), (get-uiculture) -is [Array]
True

PS> (get-culture), (get-uiculture) | foreach {
  $_ -is [System.Globalization.CultureInfo])
}
True
True

PS> (get-culture), (get-uiculture) -is [Object]
True
```

<span data-ttu-id="60c63-159">次の例は、演算子の使用方法を示して `-as` います。</span><span class="sxs-lookup"><span data-stu-id="60c63-159">The following examples show how to use the `-as` operator.</span></span>

```powershell
PS> "12/31/07" -is [DateTime]
False

PS> "12/31/07" -as [DateTime]
Monday, December 31, 2007 12:00:00 AM

PS> $date = "12/31/07" -as [DateTime]

C:\PS>$a -is [DateTime]
True

PS> 1031 -as [System.Globalization.CultureInfo]

LCID      Name      DisplayName
----      ----      -----------
1031      de-DE     German (Germany)
```

<span data-ttu-id="60c63-160">次の例は、演算子が `-as` 入力オブジェクトを .net 型に変換できない場合にを返すことを示して `$null` います。</span><span class="sxs-lookup"><span data-stu-id="60c63-160">The following example shows that when the `-as` operator cannot convert the input object to the .NET type, it returns `$null`.</span></span>

```powershell
PS> 1031 -as [System.Diagnostics.Process]
PS>
```

## <a name="see-also"></a><span data-ttu-id="60c63-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="60c63-161">SEE ALSO</span></span>

[<span data-ttu-id="60c63-162">about_Operators</span><span class="sxs-lookup"><span data-stu-id="60c63-162">about_Operators</span></span>](about_Operators.md)
