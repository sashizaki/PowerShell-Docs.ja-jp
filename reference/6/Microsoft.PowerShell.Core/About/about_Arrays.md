---
description: 項目のコレクションを格納するように設計されたデータ構造体である配列について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 08/26/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Arrays
ms.openlocfilehash: 98ba824cfc92dfd28b5bf4fe13db65efbfdcb575
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221819"
---
# <a name="about-arrays"></a><span data-ttu-id="34d78-104">配列について</span><span class="sxs-lookup"><span data-stu-id="34d78-104">About Arrays</span></span>

## <a name="short-description"></a><span data-ttu-id="34d78-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="34d78-105">Short Description</span></span>
<span data-ttu-id="34d78-106">項目のコレクションを格納するように設計されたデータ構造体である配列について説明します。</span><span class="sxs-lookup"><span data-stu-id="34d78-106">Describes arrays, which are data structures designed to store collections of items.</span></span>

## <a name="long-description"></a><span data-ttu-id="34d78-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="34d78-107">Long Description</span></span>

<span data-ttu-id="34d78-108">配列は、項目のコレクションを格納するように設計されたデータ構造体です。</span><span class="sxs-lookup"><span data-stu-id="34d78-108">An array is a data structure that is designed to store a collection of items.</span></span>
<span data-ttu-id="34d78-109">項目は、同じ型または異なる型にすることができます。</span><span class="sxs-lookup"><span data-stu-id="34d78-109">The items can be the same type or different types.</span></span>

<span data-ttu-id="34d78-110">Windows PowerShell 3.0 以降では、0個または1個のオブジェクトのコレクションに配列のプロパティがいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="34d78-110">Beginning in Windows PowerShell 3.0, a collection of zero or one object has some properties of arrays.</span></span>

## <a name="creating-and-initializing-an-array"></a><span data-ttu-id="34d78-111">配列の作成と初期化</span><span class="sxs-lookup"><span data-stu-id="34d78-111">Creating and initializing an array</span></span>

<span data-ttu-id="34d78-112">配列を作成して初期化するには、変数に複数の値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="34d78-112">To create and initialize an array, assign multiple values to a variable.</span></span> <span data-ttu-id="34d78-113">配列に格納されている値は、コンマで区切られ、代入演算子 () によって変数名から区切られ `=` ます。</span><span class="sxs-lookup"><span data-stu-id="34d78-113">The values stored in the array are delimited with a comma and separated from the variable name by the assignment operator (`=`).</span></span>

<span data-ttu-id="34d78-114">たとえば、 `$A` 7 つの数値 (int) 値22、5、10、8、12、9、および80を含むという名前の配列を作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="34d78-114">For example, to create an array named `$A` that contains the seven numeric (int) values of 22, 5, 10, 8, 12, 9, and 80, type:</span></span>

```powershell
$A = 22,5,10,8,12,9,80
```

<span data-ttu-id="34d78-115">コンマは、1つの項目の前にコンマを配置することで、1つの項目配列を初期化するためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="34d78-115">The comma can also be used to initialize a single item array by placing the comma before the single item.</span></span>

<span data-ttu-id="34d78-116">たとえば、単一の値を持つという名前の単一の item 配列を作成するには、次のように `$B` 入力します。</span><span class="sxs-lookup"><span data-stu-id="34d78-116">For example, to create a single item array named `$B` containing the single value of 7, type:</span></span>

```powershell
$B = ,7
```

<span data-ttu-id="34d78-117">範囲演算子 () を使用して、配列を作成および初期化することもでき `..` ます。</span><span class="sxs-lookup"><span data-stu-id="34d78-117">You can also create and initialize an array by using the range operator (`..`).</span></span>
<span data-ttu-id="34d78-118">次の例では、5 ~ 8 の値を含む配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="34d78-118">The following example creates an array containing the values 5 through 8.</span></span>

```powershell
$C = 5..8
```

<span data-ttu-id="34d78-119">結果として、 `$C` 5、6、7、8の4つの値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="34d78-119">As a result, `$C` contains four values: 5, 6, 7, and 8.</span></span>

<span data-ttu-id="34d78-120">データ型が指定されていない場合、PowerShell は各配列をオブジェクト配列 ( **system.object []** ) として作成します。</span><span class="sxs-lookup"><span data-stu-id="34d78-120">When no data type is specified, PowerShell creates each array as an object array ( **System.Object[]** ).</span></span> <span data-ttu-id="34d78-121">配列のデータ型を特定するには、 **GetType ()** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="34d78-121">To determine the data type of an array, use the **GetType()** method.</span></span> <span data-ttu-id="34d78-122">たとえば、配列のデータ型を確認するには、次のように `$A` 入力します。</span><span class="sxs-lookup"><span data-stu-id="34d78-122">For example, to determine the data type of the `$A` array, type:</span></span>

```powershell
$A.GetType()
```

<span data-ttu-id="34d78-123">厳密に型指定された配列 (特定の型の値のみを格納できる配列) を作成するには、 **string []** 、 **long []** 、 **int32 []** などの配列型として変数をキャストします。</span><span class="sxs-lookup"><span data-stu-id="34d78-123">To create a strongly typed array, that is, an array that can contain only values of a particular type, cast the variable as an array type, such as **string[]** , **long[]** , or **int32[]**.</span></span> <span data-ttu-id="34d78-124">配列をキャストするには、変数名の前に、角かっこで囲まれた配列型を使用します。</span><span class="sxs-lookup"><span data-stu-id="34d78-124">To cast an array, precede the variable name with an array type enclosed in brackets.</span></span> <span data-ttu-id="34d78-125">たとえば、 `$ia` 4 つの整数 (1500、2230、3350、および 4000) を含むという名前の32ビット整数配列を作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="34d78-125">For example, to create a 32-bit integer array named `$ia` containing four integers (1500, 2230, 3350, and 4000), type:</span></span>

```powershell
[int32[]]$ia = 1500,2230,3350,4000
```

<span data-ttu-id="34d78-126">そのため、配列には `$ia` 整数のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="34d78-126">As a result, the `$ia` array can contain only integers.</span></span>

<span data-ttu-id="34d78-127">Microsoft .NET Framework では、サポートされている任意の型にキャストされる配列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="34d78-127">You can create arrays that are cast to any supported type in the Microsoft .NET Framework.</span></span> <span data-ttu-id="34d78-128">たとえば、が `Get-Process` プロセスを表すためにを取得するオブジェクトの種類は **、に** なります。</span><span class="sxs-lookup"><span data-stu-id="34d78-128">For example, the objects that `Get-Process` retrieves to represent processes are of the **System.Diagnostics.Process** type.</span></span> <span data-ttu-id="34d78-129">厳密に型指定されたプロセスオブジェクトの配列を作成するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="34d78-129">To create a strongly typed array of process objects, enter the following command:</span></span>

```powershell
[Diagnostics.Process[]]$zz = Get-Process
```

## <a name="the-array-sub-expression-operator"></a><span data-ttu-id="34d78-130">配列のサブ式演算子</span><span class="sxs-lookup"><span data-stu-id="34d78-130">The array sub-expression operator</span></span>

<span data-ttu-id="34d78-131">配列のサブ式演算子は、その内部のステートメントから配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="34d78-131">The array sub-expression operator creates an array from the statements inside it.</span></span> <span data-ttu-id="34d78-132">演算子内のステートメントによって生成される場合は、演算子によって配列に格納されます。</span><span class="sxs-lookup"><span data-stu-id="34d78-132">Whatever the statement inside the operator produces, the operator will place it in an array.</span></span> <span data-ttu-id="34d78-133">0個または1個のオブジェクトがある場合でも同様です。</span><span class="sxs-lookup"><span data-stu-id="34d78-133">Even if there is zero or one object.</span></span>

<span data-ttu-id="34d78-134">配列演算子の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="34d78-134">The syntax of the array operator is as follows:</span></span>

```syntax
@( ... )
```

<span data-ttu-id="34d78-135">配列演算子を使用すると、0個または1個のオブジェクトの配列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="34d78-135">You can use the array operator to create an array of zero or one object.</span></span> <span data-ttu-id="34d78-136">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="34d78-136">For example:</span></span>

```powershell
$a = @("Hello World")
$a.Count
```

```Output
1
```

```powershell
$b = @()
$b.Count
```

```Output
0
```

<span data-ttu-id="34d78-137">配列演算子は、オブジェクトを取得するときにスクリプトで役に立ちますが、取得するオブジェクトの数を把握していません。</span><span class="sxs-lookup"><span data-stu-id="34d78-137">The array operator is useful in scripts when you are getting objects, but do not know how many objects you get.</span></span> <span data-ttu-id="34d78-138">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="34d78-138">For example:</span></span>

```powershell
$p = @(Get-Process Notepad)
```

<span data-ttu-id="34d78-139">配列のサブ式演算子の詳細については、「 [about_Operators](about_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34d78-139">For more information about the array sub-expression operator, see [about_Operators](about_Operators.md).</span></span>

## <a name="accessing-and-using-array-elements"></a><span data-ttu-id="34d78-140">配列要素へのアクセスと使用</span><span class="sxs-lookup"><span data-stu-id="34d78-140">Accessing and using array elements</span></span>

### <a name="reading-an-array"></a><span data-ttu-id="34d78-141">配列の読み取り</span><span class="sxs-lookup"><span data-stu-id="34d78-141">Reading an array</span></span>

<span data-ttu-id="34d78-142">配列は、変数名を使用して参照できます。</span><span class="sxs-lookup"><span data-stu-id="34d78-142">You can refer to an array by using its variable name.</span></span> <span data-ttu-id="34d78-143">配列内のすべての要素を表示するには、配列名を入力します。</span><span class="sxs-lookup"><span data-stu-id="34d78-143">To display all the elements in the array, type the array name.</span></span> <span data-ttu-id="34d78-144">たとえば、は、 `$a` 整数0、1、2、9までの整数を含む配列で、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="34d78-144">For example, assuming `$a` is an array containing integers 0, 1, 2, until 9; typing:</span></span>

```powershell
$a
```

```Output
0
1
2
3
4
5
6
7
8
9
```

<span data-ttu-id="34d78-145">位置0から始まるインデックスを使用して、配列内の要素を参照できます。</span><span class="sxs-lookup"><span data-stu-id="34d78-145">You can refer to the elements in an array by using an index, beginning at position 0.</span></span> <span data-ttu-id="34d78-146">インデックス番号を角かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="34d78-146">Enclose the index number in brackets.</span></span> <span data-ttu-id="34d78-147">たとえば、配列内の最初の要素を表示するには、次のように `$a` 入力します。</span><span class="sxs-lookup"><span data-stu-id="34d78-147">For example, to display the first element in the `$a` array, type:</span></span>

```powershell
$a[0]
```

```Output
0
```

<span data-ttu-id="34d78-148">配列の3番目の要素を表示するには `$a` 、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="34d78-148">To display the third element in the `$a` array, type:</span></span>

```powershell
$a[2]
```

```Output
2
```

<span data-ttu-id="34d78-149">配列の一部を取得するには、インデックスの範囲演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="34d78-149">You can retrieve part of the array using a range operator for the index.</span></span> <span data-ttu-id="34d78-150">たとえば、配列の2番目から5番目の要素を取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="34d78-150">For example, to retrieve the second to fifth elements of the array, you would type:</span></span>

```powershell
$a[1..4]
```

```Output
1
2
3
4
```

<span data-ttu-id="34d78-151">配列の末尾からの負の数。</span><span class="sxs-lookup"><span data-stu-id="34d78-151">Negative numbers count from the end of the array.</span></span> <span data-ttu-id="34d78-152">たとえば、"-1" は配列の最後の要素を参照します。</span><span class="sxs-lookup"><span data-stu-id="34d78-152">For example, "-1" refers to the last element of the array.</span></span> <span data-ttu-id="34d78-153">配列の最後の3つの要素を表示するには、インデックスの昇順で、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="34d78-153">To display the last three elements of the array, in index ascending order, type:</span></span>

```powershell
$a = 0 .. 9
$a[-3..-1]
```

```Output
7
8
9
```

<span data-ttu-id="34d78-154">負のインデックスを降順で入力すると、出力が変わります。</span><span class="sxs-lookup"><span data-stu-id="34d78-154">If you type negative indexes in descending order, your output changes.</span></span>

```powershell
$a = 0 .. 9
$a[-1..-3]
```

```Output
9
8
7
```

<span data-ttu-id="34d78-155">ただし、この表記法を使用する場合は注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="34d78-155">However, be cautious when using this notation.</span></span> <span data-ttu-id="34d78-156">記法は、終了境界から配列の先頭までの間に循環します。</span><span class="sxs-lookup"><span data-stu-id="34d78-156">The notation cycles from the end boundary to the beginning of the array.</span></span>

```powershell
$a = 0 .. 9
$a[2..-2]
```

```Output
2
1
0
9
8
```

<span data-ttu-id="34d78-157">また、1つの一般的な誤りは、 `$a[0..-2]` 最後の要素を除き、配列のすべての要素を参照するということです。</span><span class="sxs-lookup"><span data-stu-id="34d78-157">Also, one common mistake is to assume `$a[0..-2]` refers to all the elements of the array, except for the last one.</span></span> <span data-ttu-id="34d78-158">これは、配列内の最初、最後、および最後から2番目の要素を参照します。</span><span class="sxs-lookup"><span data-stu-id="34d78-158">It refers to the first, last, and second-to-last elements in the array.</span></span>

<span data-ttu-id="34d78-159">プラス演算子 () を使用し `+` て、範囲を配列内の要素のリストと結合することができます。</span><span class="sxs-lookup"><span data-stu-id="34d78-159">You can use the plus operator (`+`) to combine a ranges with a list of elements in an array.</span></span> <span data-ttu-id="34d78-160">たとえば、インデックス位置0、2、および 4 ~ 6 の要素を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="34d78-160">For example, to display the elements at index positions 0, 2, and 4 through 6, type:</span></span>

```powershell
$a = 0 .. 9
$a[0,2+4..6]
```

```Output
0
2
4
5
6
```

<span data-ttu-id="34d78-161">また、複数の範囲と個々の要素を一覧表示するには、プラス演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="34d78-161">Also, to list multiple ranges and individual elements you can use the plus operator.</span></span> <span data-ttu-id="34d78-162">たとえば、要素を0から2、4 ~ 6、要素を8番目の位置の型で一覧表示するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="34d78-162">For example, to list elements zero to two, four to six, and the element at eighth positional type:</span></span>

```powershell
$a = 0..9
$a[+0..2+4..6+8]
```

```Output
0
1
2
4
5
6
8
```

### <a name="iterations-over-array-elements"></a><span data-ttu-id="34d78-163">配列要素の反復処理</span><span class="sxs-lookup"><span data-stu-id="34d78-163">Iterations over array elements</span></span>

<span data-ttu-id="34d78-164">ForEach、For、While ループなどのループ構造を使用して、配列内の要素を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="34d78-164">You can also use looping constructs, such as ForEach, For, and While loops, to refer to the elements in an array.</span></span> <span data-ttu-id="34d78-165">たとえば、ForEach ループを使用して配列内の要素を表示するには、次のように `$a` 入力します。</span><span class="sxs-lookup"><span data-stu-id="34d78-165">For example, to use a ForEach loop to display the elements in the `$a` array, type:</span></span>

```powershell
$a = 0..9
foreach ($element in $a) {
  $element
}
```

```Output
0
1
2
3
4
5
6
7
8
9
```

<span data-ttu-id="34d78-166">Foreach ループは配列を反復処理し、配列の末尾に到達するまで配列内の各値を返します。</span><span class="sxs-lookup"><span data-stu-id="34d78-166">The Foreach loop iterates through the array and returns each value in the array until reaching the end of the array.</span></span>

<span data-ttu-id="34d78-167">For ループは、配列内の要素の検査中にカウンターをインクリメントする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="34d78-167">The For loop is useful when you are incrementing counters while examining the elements in an array.</span></span> <span data-ttu-id="34d78-168">たとえば、For ループを使用して配列内の他のすべての値を返すには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="34d78-168">For example, to use a For loop to return every other value in an array, type:</span></span>

```powershell
$a = 0..9
for ($i = 0; $i -le ($a.length - 1); $i += 2) {
  $a[$i]
}
```

```Output
0
2
4
6
8
```

<span data-ttu-id="34d78-169">While ループを使用すると、定義された条件が満たされなくなるまで、配列内の要素を表示できます。</span><span class="sxs-lookup"><span data-stu-id="34d78-169">You can use a While loop to display the elements in an array until a defined condition is no longer true.</span></span> <span data-ttu-id="34d78-170">たとえば、配列インデックスが4未満のときに配列の要素を表示するには `$a` 、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="34d78-170">For example, to display the elements in the `$a` array while the array index is less than 4, type:</span></span>

```powershell
$a = 0..9
$i=0
while($i -lt 4) {
  $a[$i];
  $i++
}
```

```Output
0
1
2
3
```

## <a name="properties-of-arrays"></a><span data-ttu-id="34d78-171">配列のプロパティ</span><span class="sxs-lookup"><span data-stu-id="34d78-171">Properties of arrays</span></span>

### <a name="count-or-length-or-longlength"></a><span data-ttu-id="34d78-172">Count または Length または LongLength</span><span class="sxs-lookup"><span data-stu-id="34d78-172">Count or Length or LongLength</span></span>

<span data-ttu-id="34d78-173">配列内の項目の数を確認するには、 `Length` プロパティまたはそのエイリアスを使用し `Count` ます。</span><span class="sxs-lookup"><span data-stu-id="34d78-173">To determine how many items are in an array, use the `Length` property or its `Count` alias.</span></span> <span data-ttu-id="34d78-174">`Longlength` は、配列に2147483647個を超える要素が含まれている場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="34d78-174">`Longlength` is useful if the array contains more than 2,147,483,647 elements.</span></span>

```powershell
$a = 0..9
$a.Count
$a.Length
```

```Output
10
10
```

### <a name="rank"></a><span data-ttu-id="34d78-175">順位</span><span class="sxs-lookup"><span data-stu-id="34d78-175">Rank</span></span>

<span data-ttu-id="34d78-176">配列内の次元数を返します。</span><span class="sxs-lookup"><span data-stu-id="34d78-176">Returns the number of dimensions in the array.</span></span> <span data-ttu-id="34d78-177">PowerShell のほとんどの配列には、ディメンションが1つだけあります。</span><span class="sxs-lookup"><span data-stu-id="34d78-177">Most arrays in PowerShell have one dimension, only.</span></span> <span data-ttu-id="34d78-178">多次元配列を構築していると思われる場合でも、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="34d78-178">Even when you think you are building a multidimensional array; like the following example:</span></span>

```powershell
$a = @(
  @(0,1),
  @("b", "c"),
  @(Get-Process)
)

[int]$r = $a.Rank
"`$a rank: $r"
```

```Output
$a rank: 1
```

<span data-ttu-id="34d78-179">次の例は、.Net Framework を使用して真の多次元配列を作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="34d78-179">The following example shows how to create a truly multidimensional array using the .Net Framework.</span></span>

```powershell
[int[,]]$rank2 = [int[,]]::new(5,5)
$rank2.rank
```

```Output
2
```

## <a name="methods-of-arrays"></a><span data-ttu-id="34d78-180">配列のメソッド</span><span class="sxs-lookup"><span data-stu-id="34d78-180">Methods of arrays</span></span>

### <a name="clear"></a><span data-ttu-id="34d78-181">Clear</span><span class="sxs-lookup"><span data-stu-id="34d78-181">Clear</span></span>

<span data-ttu-id="34d78-182">すべての要素の値を、配列の要素型の _既定値_ に設定します。</span><span class="sxs-lookup"><span data-stu-id="34d78-182">Sets all element values to the _default value_ of the array's element type.</span></span>
<span data-ttu-id="34d78-183">Clear () メソッドでは、配列のサイズはリセットされません。</span><span class="sxs-lookup"><span data-stu-id="34d78-183">The Clear() method does not reset the size of the array.</span></span>

<span data-ttu-id="34d78-184">次の例で `$a` は、オブジェクトの配列です。</span><span class="sxs-lookup"><span data-stu-id="34d78-184">In the following example `$a` is an array of objects.</span></span>

```powershell
$a = 1, 2, 3
$a.Clear()
$a | % { $null -eq $_ }
```

```Output
True
True
True
```

<span data-ttu-id="34d78-185">この例で `$intA` は、は整数を含むように明示的に型指定されています。</span><span class="sxs-lookup"><span data-stu-id="34d78-185">In this example, `$intA` is explicitly typed to contain integers.</span></span>

```powershell
[int[]] $intA = 1, 2, 3
$intA.Clear()
$intA
```

```Output
0
0
0
```

### <a name="foreach"></a><span data-ttu-id="34d78-186">ForEach</span><span class="sxs-lookup"><span data-stu-id="34d78-186">ForEach</span></span>

<span data-ttu-id="34d78-187">が配列内のすべての要素を反復処理し、配列の各要素に対して特定の操作を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="34d78-187">Allows to iterate over all elements in the array and perform a given operation for each element of the array.</span></span>

<span data-ttu-id="34d78-188">ForEach メソッドには、さまざまな操作を実行するいくつかのオーバーロードがあります。</span><span class="sxs-lookup"><span data-stu-id="34d78-188">The ForEach method has several overloads that perform different operations.</span></span>

```
ForEach(scriptblock expression)
ForEach(scriptblock expression, object[] arguments)
ForEach(type convertToType)
ForEach(string propertyName)
ForEach(string propertyName, object[] newValue)
ForEach(string methodName)
ForEach(string methodName, object[] arguments)
```

#### <a name="foreachscriptblock-expression"></a><span data-ttu-id="34d78-189">ForEach (scriptblock 式)</span><span class="sxs-lookup"><span data-stu-id="34d78-189">ForEach(scriptblock expression)</span></span>

#### <a name="foreachscriptblock-expression-object-arguments"></a><span data-ttu-id="34d78-190">ForEach (scriptblock 式、object [] 引数)</span><span class="sxs-lookup"><span data-stu-id="34d78-190">ForEach(scriptblock expression, object[] arguments)</span></span>

<span data-ttu-id="34d78-191">このメソッドは、PowerShell v4 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="34d78-191">This method was added in PowerShell v4.</span></span>

> [!NOTE]
> <span data-ttu-id="34d78-192">構文では、スクリプトブロックを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34d78-192">The syntax requires the usage of a script block.</span></span> <span data-ttu-id="34d78-193">Scriptblock が唯一のパラメーターの場合、かっこは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="34d78-193">Parentheses are optional if the scriptblock is the only parameter.</span></span> <span data-ttu-id="34d78-194">また、メソッドと始めかっこまたは中かっこの間にスペースを配置することはできません。</span><span class="sxs-lookup"><span data-stu-id="34d78-194">Also, there must not be a space between the method and the opening parenthesis or brace.</span></span>

<span data-ttu-id="34d78-195">次の例は、foreach メソッドの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="34d78-195">The following example shows how use the foreach method.</span></span> <span data-ttu-id="34d78-196">この場合、目的は配列内の要素の二乗値を生成することです。</span><span class="sxs-lookup"><span data-stu-id="34d78-196">In this case the intent is to generate the square value of the elements in the array.</span></span>

```powershell
$a = @(0 .. 3)
$a.ForEach({ $_ * $_})
```

```Output
0
1
4
9
```

<span data-ttu-id="34d78-197">のパラメーターと同じように、パラメーターを使用すると、 `-ArgumentList` `ForEach-Object` `arguments` 引数の配列を、それを受け入れるように構成されたスクリプトブロックに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="34d78-197">Just like the `-ArgumentList` parameter of `ForEach-Object`, the `arguments` parameter allows the passing of an array of arguments to a script block configured to accept them.</span></span>

<span data-ttu-id="34d78-198">**ArgumentList** の動作の詳細については、「 [about_Splatting](about_Splatting.md#splatting-with-arrays)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34d78-198">For more information about the behavior of **ArgumentList** , see [about_Splatting](about_Splatting.md#splatting-with-arrays).</span></span>

#### <a name="foreachtype-converttotype"></a><span data-ttu-id="34d78-199">ForEach (型 convertToType)</span><span class="sxs-lookup"><span data-stu-id="34d78-199">ForEach(type convertToType)</span></span>

<span data-ttu-id="34d78-200">メソッドを使用すると、 `ForEach` 要素を別の型に迅速にキャストできます。次の例では、文字列の日付のリストを型に変換する方法を示します `[DateTime]` 。</span><span class="sxs-lookup"><span data-stu-id="34d78-200">The `ForEach` method can be used to swiftly cast the elements to a different type; the following example shows how to convert a list of string dates to `[DateTime]` type.</span></span>

```powershell
@("1/1/2017", "2/1/2017", "3/1/2017").ForEach([datetime])
```

```Output

Sunday, January 1, 2017 12:00:00 AM
Wednesday, February 1, 2017 12:00:00 AM
Wednesday, March 1, 2017 12:00:00 AM
```

#### <a name="foreachstring-propertyname"></a><span data-ttu-id="34d78-201">ForEach (文字列 propertyName)</span><span class="sxs-lookup"><span data-stu-id="34d78-201">ForEach(string propertyName)</span></span>

#### <a name="foreachstring-propertyname-object-newvalue"></a><span data-ttu-id="34d78-202">ForEach (string propertyName, object [] newValue)</span><span class="sxs-lookup"><span data-stu-id="34d78-202">ForEach(string propertyName, object[] newValue)</span></span>

<span data-ttu-id="34d78-203">メソッドを使用して、 `ForEach` コレクション内のすべての項目のプロパティ値をすばやく取得したり、設定したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="34d78-203">The `ForEach` method can also be used to quickly retrieve, or set property values for every item in the collection.</span></span>

```powershell
# Set all LastAccessTime properties of files to the current date.
(dir 'C:\Temp').ForEach('LastAccessTime', (Get-Date))
# View the newly set LastAccessTime of all items, and find Unique entries.
(dir 'C:\Temp').ForEach('LastAccessTime') | Get-Unique
```

```Output
Wednesday, June 20, 2018 9:21:57 AM
```

#### <a name="foreachstring-methodname"></a><span data-ttu-id="34d78-204">ForEach (文字列 methodName)</span><span class="sxs-lookup"><span data-stu-id="34d78-204">ForEach(string methodName)</span></span>

#### <a name="foreachstring-methodname-object-arguments"></a><span data-ttu-id="34d78-205">ForEach (文字列 methodName、object [] 引数)</span><span class="sxs-lookup"><span data-stu-id="34d78-205">ForEach(string methodName, object[] arguments)</span></span>

<span data-ttu-id="34d78-206">最後に、メソッドを使用して、 `ForEach` コレクション内のすべての項目に対してメソッドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="34d78-206">Lastly, `ForEach` methods can be used to execute a method on every item in the collection.</span></span>

```powershell
("one", "two", "three").ForEach("ToUpper")
```

```Output
ONE
TWO
THREE
```

<span data-ttu-id="34d78-207">のパラメーターと同じように、パラメーターを使用すると、 `-ArgumentList` `ForEach-Object` `arguments` 引数の配列を、それを受け入れるように構成されたスクリプトブロックに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="34d78-207">Just like the `-ArgumentList` parameter of `ForEach-Object`, the `arguments` parameter allows the passing of an array of arguments to a script block configured to accept them.</span></span>

> [!NOTE]
> <span data-ttu-id="34d78-208">Windows PowerShell 3.0 以降では、コレクション内の各項目のプロパティを取得し、メソッドを実行することもできます。詳細については、「スカラーオブジェクトとコレクションのメソッド」を参照してください [about_methods](about_methods.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34d78-208">Starting in Windows PowerShell 3.0 retrieving properties and executing methods for each item in a collection can also be accomplished using "Methods of scalar objects and collections" You can read more about that here [about_methods](about_methods.md).</span></span>

### <a name="where"></a><span data-ttu-id="34d78-209">Where</span><span class="sxs-lookup"><span data-stu-id="34d78-209">Where</span></span>

<span data-ttu-id="34d78-210">配列の要素をフィルター処理または選択できるようにします。</span><span class="sxs-lookup"><span data-stu-id="34d78-210">Allows to filter or select the elements of the array.</span></span> <span data-ttu-id="34d78-211">スクリプトは、ゼロ (0)、空の文字列、 `$false` または `$null` の後に表示する要素に対して、 `Where`</span><span class="sxs-lookup"><span data-stu-id="34d78-211">The script must evaluate to anything different than: zero (0), empty string, `$false` or `$null` for the element to show after the `Where`</span></span>

<span data-ttu-id="34d78-212">メソッドには1つの定義があり `Where` ます。</span><span class="sxs-lookup"><span data-stu-id="34d78-212">There is one definition for the `Where` method.</span></span>

```
Where(scriptblock expression[, WhereOperatorSelectionMode mode
                            [, int numberToReturn]])
```

> [!NOTE]
> <span data-ttu-id="34d78-213">構文では、スクリプトブロックを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34d78-213">The syntax requires the usage of a script block.</span></span> <span data-ttu-id="34d78-214">Scriptblock が唯一のパラメーターの場合、かっこは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="34d78-214">Parentheses are optional if the scriptblock is the only parameter.</span></span> <span data-ttu-id="34d78-215">また、メソッドと始めかっこまたは中かっこの間にスペースを配置することはできません。</span><span class="sxs-lookup"><span data-stu-id="34d78-215">Also, there must not be a space between the method and the opening parenthesis or brace.</span></span>

<span data-ttu-id="34d78-216">`Expression`は、フィルター処理に必要な scriptblock です `mode` 。オプションの引数を使用すると、追加の選択機能を使用でき `numberToReturn` ます。また、省略可能な引数を使用すると、フィルターから返される項目の数を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="34d78-216">The `Expression` is scriptblock that is required for filtering, the `mode` optional argument allows additional selection capabilities, and the `numberToReturn` optional argument allows the ability to limit how many items are returned from the filter.</span></span>

<span data-ttu-id="34d78-217">に使用できる値 `mode` は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="34d78-217">The acceptable values for `mode` are:</span></span>

- <span data-ttu-id="34d78-218">Default (0)-すべての項目を返す</span><span class="sxs-lookup"><span data-stu-id="34d78-218">Default (0) - Return all items</span></span>
- <span data-ttu-id="34d78-219">最初の (1)-最初の項目を返します。</span><span class="sxs-lookup"><span data-stu-id="34d78-219">First (1) - Return the first item</span></span>
- <span data-ttu-id="34d78-220">Last (2)-最後の項目を返します。</span><span class="sxs-lookup"><span data-stu-id="34d78-220">Last (2) - Return the last item</span></span>
- <span data-ttu-id="34d78-221">延期 (3)-条件が true になるまで項目をスキップし、残りの項目を返します</span><span class="sxs-lookup"><span data-stu-id="34d78-221">SkipUntil (3) - Skip items until condition is true, the return the remaining items</span></span>
- <span data-ttu-id="34d78-222">Until (4)-条件が true になるまですべての項目を返す</span><span class="sxs-lookup"><span data-stu-id="34d78-222">Until (4) - Return all items until condition is true</span></span>
- <span data-ttu-id="34d78-223">Split (5)-2 つの要素の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="34d78-223">Split (5) - Return an array of two elements</span></span>
  - <span data-ttu-id="34d78-224">最初の要素には一致する項目が含まれます</span><span class="sxs-lookup"><span data-stu-id="34d78-224">The first element contains matching items</span></span>
  - <span data-ttu-id="34d78-225">2番目の要素には残りの項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="34d78-225">The second element contains the remaining items</span></span>

<span data-ttu-id="34d78-226">次の例は、配列からすべての奇数を選択する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="34d78-226">The following example shows how to select all odd numbers from the array.</span></span>

```powershell
(0..9).Where{ $_ % 2 }
```

```Output
1
3
5
7
9
```

<span data-ttu-id="34d78-227">この例では、空でない文字列を選択する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="34d78-227">This example show how to select the strings that are not empty.</span></span>

```powershell
('hi', '', 'there').Where({$_.Length})
```

```Output
hi
there
```

#### <a name="default"></a><span data-ttu-id="34d78-228">Default</span><span class="sxs-lookup"><span data-stu-id="34d78-228">Default</span></span>

<span data-ttu-id="34d78-229">モードでは `Default` 、scriptblock を使用して項目をフィルター処理し `Expression` ます。</span><span class="sxs-lookup"><span data-stu-id="34d78-229">The `Default` mode filters items using the `Expression` scriptblock.</span></span>

<span data-ttu-id="34d78-230">が指定されている場合は、 `numberToReturn` 返される項目の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="34d78-230">If a `numberToReturn` is provided, it specifies the maximum number of items to return.</span></span>

```powershell
# Get the zip files in the current users profile, sorted by LastAccessTime.
$Zips = dir $env:userprofile -Recurse '*.zip' | Sort-Object LastAccessTime
# Get the least accessed file over 100MB
$Zips.Where({$_.Length -gt 100MB}, 'Default', 1)
```

> [!NOTE]
> <span data-ttu-id="34d78-231">モードとモードは、どちらも `Default` `First` 最初の ( `numberToReturn` ) 項目を返し、同義に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="34d78-231">Both the `Default` mode and `First` mode return the first (`numberToReturn`) items, and can be used interchangeably.</span></span>

#### <a name="last"></a><span data-ttu-id="34d78-232">Last (最後へ)</span><span class="sxs-lookup"><span data-stu-id="34d78-232">Last</span></span>

```powershell
$h = (Get-Date).AddHours(-1)
$logs = dir 'C:\' -Recurse '*.log' | Sort-Object CreationTime
# Find the last 5 log files created in the past hour.
$logs.Where({$_.CreationTime -gt $h}, 'Last', 5)
```

#### <a name="skipuntil"></a><span data-ttu-id="34d78-233">延期</span><span class="sxs-lookup"><span data-stu-id="34d78-233">SkipUntil</span></span>

<span data-ttu-id="34d78-234">モードでは、 `SkipUntil` オブジェクトがスクリプトブロック式フィルターに合格するまで、コレクション内のすべてのオブジェクトがスキップされます。</span><span class="sxs-lookup"><span data-stu-id="34d78-234">The `SkipUntil` mode skips all objects in a collection until an object passes the script block expression filter.</span></span> <span data-ttu-id="34d78-235">その後、残りの **すべて** のコレクションアイテムをテストせずに返します。</span><span class="sxs-lookup"><span data-stu-id="34d78-235">It then returns **ALL** remaining collection items without testing them.</span></span> <span data-ttu-id="34d78-236">_1 つの渡す項目のみがテストされ_ ます。</span><span class="sxs-lookup"><span data-stu-id="34d78-236">_Only one passing item is tested_.</span></span>

<span data-ttu-id="34d78-237">つまり、返されるコレクションには、テストされていない、 _渡し_ ている項目と _渡し_ ていない項目の両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="34d78-237">This means the returned collection contains both _passing_ and _non-passing_ items that have NOT been tested.</span></span>

<span data-ttu-id="34d78-238">返される項目の数は、引数に値を渡すことによって制限できます `numberToReturn` 。</span><span class="sxs-lookup"><span data-stu-id="34d78-238">The number of items returned can be limited by passing a value to the `numberToReturn` argument.</span></span>

```powershell
$computers = "Server01", "Server02", "Server03", "localhost", "Server04"
# Find the first available online server.
$computers.Where({ Test-Connection $_ }, 'SkipUntil', 1)
```

```Output
localhost
```

#### <a name="until"></a><span data-ttu-id="34d78-239">Until</span><span class="sxs-lookup"><span data-stu-id="34d78-239">Until</span></span>

<span data-ttu-id="34d78-240">モードは、モードを `Until` 反転し `SkipUntil` ます。</span><span class="sxs-lookup"><span data-stu-id="34d78-240">The `Until` mode inverts the `SkipUntil` mode.</span></span>  <span data-ttu-id="34d78-241">コレクション内の **すべて** の項目を返します。これは、項目がスクリプトブロック式に合格するまで続きます。</span><span class="sxs-lookup"><span data-stu-id="34d78-241">It returns **ALL** items in a collection until an item passes the script block expression.</span></span> <span data-ttu-id="34d78-242">項目が scriptblock 式を _渡す_ と、 `Where` メソッドは項目の処理を停止します。</span><span class="sxs-lookup"><span data-stu-id="34d78-242">Once an item _passes_ the scriptblock expression, the `Where` method stops processing items.</span></span>

<span data-ttu-id="34d78-243">これは、メソッドから _渡されない_ 項目の最初のセットを受け取ることを意味し `Where` ます。</span><span class="sxs-lookup"><span data-stu-id="34d78-243">This means that you receive the first set of _non-passing_ items from the `Where` method.</span></span> <span data-ttu-id="34d78-244">1つの項目が成功し _た後_ 、残りはテストも返されません。</span><span class="sxs-lookup"><span data-stu-id="34d78-244">_After_ one item passes, the rest are NOT tested or returned.</span></span>

<span data-ttu-id="34d78-245">返される項目の数は、引数に値を渡すことによって制限できます `numberToReturn` 。</span><span class="sxs-lookup"><span data-stu-id="34d78-245">The number of items returned can be limited by passing a value to the `numberToReturn` argument.</span></span>

```powershell
# Retrieve the first set of numbers less than or equal to 10.
(1..50).Where({$_ -gt 10}, 'Until')
# This would perform the same operation.
(1..50).Where({$_ -le 10})
```

```Output
1
2
3
4
5
6
7
8
9
10
```

> [!NOTE]
> <span data-ttu-id="34d78-246">とはどちらも、 `Until` `SkipUntil` 項目のバッチをテストしないという前提で動作します。</span><span class="sxs-lookup"><span data-stu-id="34d78-246">Both `Until` and `SkipUntil` operate under the premise of NOT testing a batch of items.</span></span>
>
> <span data-ttu-id="34d78-247">`Until`最初の _パス_ の **前に** ある項目を返します。</span><span class="sxs-lookup"><span data-stu-id="34d78-247">`Until` returns the items **BEFORE** the first _pass_.</span></span>
>
> <span data-ttu-id="34d78-248">`SkipUntil`最初の _パス_ の **後** にあるすべての項目 (最初の引き渡し項目を含む) を返します。</span><span class="sxs-lookup"><span data-stu-id="34d78-248">`SkipUntil` returns all the items **AFTER** the first _pass_ , including the first passing item.</span></span>

#### <a name="split"></a><span data-ttu-id="34d78-249">Split</span><span class="sxs-lookup"><span data-stu-id="34d78-249">Split</span></span>

<span data-ttu-id="34d78-250">この `Split` モードでは、コレクションアイテムが分割されるか、コレクションアイテムが2つの異なるコレクションにグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="34d78-250">The `Split` mode splits, or groups collection items into two separate collections.</span></span> <span data-ttu-id="34d78-251">Scriptblock 式を渡すこれらの式と、それ以外の式を渡します。</span><span class="sxs-lookup"><span data-stu-id="34d78-251">Those that pass the scriptblock expression, and those that do not.</span></span>

<span data-ttu-id="34d78-252">が指定されている場合、 `numberToReturn` 最初のコレクションには、指定された値を超えるものではなく、 _渡す_ 項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="34d78-252">If a `numberToReturn` is specified, the first collection, contains the _passing_ items, not to exceed the value specified.</span></span>

<span data-ttu-id="34d78-253">残りのオブジェクトは、式フィルターを **通過** したオブジェクトも、2番目のコレクションで返されます。</span><span class="sxs-lookup"><span data-stu-id="34d78-253">The remaining objects, even those that **PASS** the expression filter, are returned in the second collection.</span></span>

```powershell
$running, $stopped = (Get-Service).Where({$_.Status -eq 'Running'}, 'Split')
$running
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  Appinfo            Application Information
Running  AudioEndpointBu... Windows Audio Endpoint Builder
Running  Audiosrv           Windows Audio
...
```

```powershell
$stopped
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  AJRouter           AllJoyn Router Service
Stopped  ALG                Application Layer Gateway Service
Stopped  AppIDSvc           Application Identity
...
```

## <a name="get-the-members-of-an-array"></a><span data-ttu-id="34d78-254">配列のメンバーを取得する</span><span class="sxs-lookup"><span data-stu-id="34d78-254">Get the members of an array</span></span>

<span data-ttu-id="34d78-255">Length プロパティや **SetValue** メソッドなど、配列のプロパティとメソッドを取得するには、コマンドレットの **InputObject** パラメーターを使用し `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="34d78-255">To get the properties and methods of an array, such as the Length property and the **SetValue** method, use the **InputObject** parameter of the `Get-Member` cmdlet.</span></span>

<span data-ttu-id="34d78-256">パイプを使用して配列をに渡した場合 `Get-Member` 、PowerShell は一度に1つずつ項目を送信し、 `Get-Member` 配列内の各項目の型を返します (重複部分は無視されます)。</span><span class="sxs-lookup"><span data-stu-id="34d78-256">When you pipe an array to `Get-Member`, PowerShell sends the items one at a time and `Get-Member` returns the type of each item in the array (ignoring duplicates).</span></span>

<span data-ttu-id="34d78-257">**InputObject** パラメーターを使用すると、は `Get-Member` 配列のメンバーを返します。</span><span class="sxs-lookup"><span data-stu-id="34d78-257">When you use the **InputObject** parameter, `Get-Member` returns the members of the array.</span></span>

<span data-ttu-id="34d78-258">たとえば、次のコマンドは、配列変数のメンバーを取得し `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="34d78-258">For example, the following command gets the members of the `$a` array variable.</span></span>

```powershell
Get-Member -InputObject $a
```

<span data-ttu-id="34d78-259">また、コマンドレットにパイプされる値の前にコンマ (,) を入力して、配列のメンバーを取得することもでき `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="34d78-259">You can also get the members of an array by typing a comma (,) before the value that is piped to the `Get-Member` cmdlet.</span></span> <span data-ttu-id="34d78-260">コンマを使用すると、配列の配列の2番目の項目が配列になります。</span><span class="sxs-lookup"><span data-stu-id="34d78-260">The comma makes the array the second item in an array of arrays.</span></span> <span data-ttu-id="34d78-261">PowerShell は、配列を一度に1つずつパイプし、 `Get-Member` 配列のメンバーを返します。</span><span class="sxs-lookup"><span data-stu-id="34d78-261">PowerShell pipes the arrays one at a time and `Get-Member` returns the members of the array.</span></span> <span data-ttu-id="34d78-262">次の2つの例のようになります。</span><span class="sxs-lookup"><span data-stu-id="34d78-262">Like the next two examples.</span></span>

```powershell
,$a | Get-Member

,(1,2,3) | Get-Member
```

## <a name="manipulating-an-array"></a><span data-ttu-id="34d78-263">配列の操作</span><span class="sxs-lookup"><span data-stu-id="34d78-263">Manipulating an array</span></span>

<span data-ttu-id="34d78-264">配列内の要素を変更し、配列に要素を追加して、2つの配列の値を3番目の配列に結合できます。</span><span class="sxs-lookup"><span data-stu-id="34d78-264">You can change the elements in an array, add an element to an array, and combine the values from two arrays into a third array.</span></span>

<span data-ttu-id="34d78-265">配列内の特定の要素の値を変更するには、変更する要素の配列名とインデックスを指定し、代入演算子 () を使用して `=` 要素に新しい値を指定します。</span><span class="sxs-lookup"><span data-stu-id="34d78-265">To change the value of a particular element in an array, specify the array name and the index of the element that you want to change, and then use the assignment operator (`=`) to specify a new value for the element.</span></span> <span data-ttu-id="34d78-266">たとえば、配列の2番目の項目 (インデックス位置 1) の値を10に変更するには、次のように `$a` 入力します。</span><span class="sxs-lookup"><span data-stu-id="34d78-266">For example, to change the value of the second item in the `$a` array (index position 1) to 10, type:</span></span>

```powershell
$a[1] = 10
```

<span data-ttu-id="34d78-267">配列の **SetValue** メソッドを使用して値を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="34d78-267">You can also use the **SetValue** method of an array to change a value.</span></span> <span data-ttu-id="34d78-268">次の例では、配列の2番目の値 (インデックス位置 1) `$a` を500に変更します。</span><span class="sxs-lookup"><span data-stu-id="34d78-268">The following example changes the second value (index position 1) of the `$a` array to 500:</span></span>

```powershell
$a.SetValue(500,1)
```

<span data-ttu-id="34d78-269">演算子を使用すると、 `+=` 配列に要素を追加できます。</span><span class="sxs-lookup"><span data-stu-id="34d78-269">You can use the `+=` operator to add an element to an array.</span></span> <span data-ttu-id="34d78-270">次の例は、要素を配列に追加する方法を示して `$a` います。</span><span class="sxs-lookup"><span data-stu-id="34d78-270">The following example shows how to add an element to the `$a` array.</span></span>

```powershell
$a = @(0..4)
$a += 5
```

> [!NOTE]
> <span data-ttu-id="34d78-271">演算子を使用すると `+=` 、PowerShell は実際には、元の配列の値と追加された値を使用して、新しい配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="34d78-271">When you use the `+=` operator, PowerShell actually creates a new array with the values of the original array and the added value.</span></span> <span data-ttu-id="34d78-272">この場合、操作が複数回繰り返されるか、配列のサイズが大きすぎると、パフォーマンスの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="34d78-272">This might cause performance issues if the operation is repeated several times or the size of the array is too big.</span></span>

<span data-ttu-id="34d78-273">配列から要素を削除するのは簡単ではありませんが、既存の配列の選択した要素のみを含む新しい配列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="34d78-273">It is not easy to delete elements from an array, but you can create a new array that contains only selected elements of an existing array.</span></span> <span data-ttu-id="34d78-274">たとえば、 `$t` インデックス位置2の値を除いて、配列内のすべての要素を含む配列を作成するには、 `$a` 次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="34d78-274">For example, to create the `$t` array with all the elements in the `$a` array except for the value at index position 2, type:</span></span>

```powershell
$t = $a[0,1 + 3..($a.length - 1)]
```

<span data-ttu-id="34d78-275">2つの配列を1つの配列に結合するには、プラス演算子 () を使用し `+` ます。</span><span class="sxs-lookup"><span data-stu-id="34d78-275">To combine two arrays into a single array, use the plus operator (`+`).</span></span> <span data-ttu-id="34d78-276">次の例では、2つの配列を作成し、それらを結合して、結果として得られる配列を表示します。</span><span class="sxs-lookup"><span data-stu-id="34d78-276">The following example creates two arrays, combines them, and then displays the resulting combined array.</span></span>

```powershell
$x = 1,3
$y = 5,9
$z = $x + $y
```

<span data-ttu-id="34d78-277">結果として、 `$z` 配列には1、3、5、および9が含まれます。</span><span class="sxs-lookup"><span data-stu-id="34d78-277">As a result, the `$z` array contains 1, 3, 5, and 9.</span></span>

<span data-ttu-id="34d78-278">配列を削除するには、配列に値を代入し `$null` ます。</span><span class="sxs-lookup"><span data-stu-id="34d78-278">To delete an array, assign a value of `$null` to the array.</span></span> <span data-ttu-id="34d78-279">次のコマンドは、変数内の配列を削除し `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="34d78-279">The following command deletes the array in the `$a` variable.</span></span>

`$a = $null`

<span data-ttu-id="34d78-280">コマンドレットを使用することもできますが、 `Remove-Item` `$null` 特に大きな配列の場合は、の値を割り当てる方が高速です。</span><span class="sxs-lookup"><span data-stu-id="34d78-280">You can also use the `Remove-Item` cmdlet, but assigning a value of `$null` is faster, especially for large arrays.</span></span>

## <a name="arrays-of-zero-or-one"></a><span data-ttu-id="34d78-281">0個または1個の配列</span><span class="sxs-lookup"><span data-stu-id="34d78-281">Arrays of zero or one</span></span>

<span data-ttu-id="34d78-282">Windows PowerShell 3.0 以降では、0個または1個のオブジェクトのコレクションに Count と Length プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="34d78-282">Beginning in Windows PowerShell 3.0, a collection of zero or one object has the Count and Length property.</span></span> <span data-ttu-id="34d78-283">また、1つのオブジェクトの配列にインデックスを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="34d78-283">Also, you can index into an array of one object.</span></span> <span data-ttu-id="34d78-284">この機能は、コレクションを必要とするコマンドが2つよりも小さい場合に発生するスクリプトエラーを回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="34d78-284">This feature helps you to avoid scripting errors that occur when a command that expects a collection gets fewer than two items.</span></span>

<span data-ttu-id="34d78-285">この機能の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="34d78-285">The following examples demonstrate this feature.</span></span>

### <a name="zero-objects"></a><span data-ttu-id="34d78-286">ゼロオブジェクト</span><span class="sxs-lookup"><span data-stu-id="34d78-286">Zero objects</span></span>

```powershell
$a = $null
$a.Count
$a.Length
```

```Output
0
0
```

### <a name="one-object"></a><span data-ttu-id="34d78-287">1つのオブジェクト</span><span class="sxs-lookup"><span data-stu-id="34d78-287">One object</span></span>

```powershell
$a = 4
$a.Count
$a.Length
$a[0]
$a[-1]
```

```Output
1
1
4
4
```

## <a name="indexing-support-for-systemtuple-objects"></a><span data-ttu-id="34d78-288">システムの Tuple オブジェクトのインデックス作成のサポート</span><span class="sxs-lookup"><span data-stu-id="34d78-288">Indexing support for System.Tuple objects</span></span>

<span data-ttu-id="34d78-289">PowerShell 6.1 では、配列に似た **タプル** オブジェクトのインデックス付きアクセスのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="34d78-289">PowerShell 6.1 added the support for indexed access of **Tuple** objects, similar to arrays.</span></span>
<span data-ttu-id="34d78-290">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="34d78-290">For example:</span></span>

```powershell
PS> $tuple = [Tuple]::Create(1, 'test')
PS> $tuple[0]
1
PS> $tuple[1]
test
PS> $tuple[0..1]
1
test
PS> $tuple[-1]
test
```

<span data-ttu-id="34d78-291">配列やその他のコレクションオブジェクトとは異なり、 **組** オブジェクトは、パイプラインまたはオブジェクトの配列をサポートするパラメーターによって渡されるときに、単一のオブジェクトとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="34d78-291">Unlike arrays and other collection objects, **Tuple** objects are treated as a single object when passed through the pipeline or by parameters that support arrays of objects.</span></span>

<span data-ttu-id="34d78-292">詳細については、「 [Tuple](/dotnet/api/system.tuple)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34d78-292">For more information, see [System.Tuple](/dotnet/api/system.tuple).</span></span>

## <a name="see-also"></a><span data-ttu-id="34d78-293">関連項目</span><span class="sxs-lookup"><span data-stu-id="34d78-293">See also</span></span>

- [<span data-ttu-id="34d78-294">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="34d78-294">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)
- [<span data-ttu-id="34d78-295">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="34d78-295">about_Hash_Tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="34d78-296">about_Operators</span><span class="sxs-lookup"><span data-stu-id="34d78-296">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="34d78-297">about_For</span><span class="sxs-lookup"><span data-stu-id="34d78-297">about_For</span></span>](about_For.md)
- [<span data-ttu-id="34d78-298">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="34d78-298">about_Foreach</span></span>](about_Foreach.md)
- [<span data-ttu-id="34d78-299">about_While</span><span class="sxs-lookup"><span data-stu-id="34d78-299">about_While</span></span>](about_While.md)
