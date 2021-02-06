---
description: 項目のコレクションを格納するように設計されたデータ構造体である配列について説明します。
Locale: en-US
ms.date: 08/26/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Arrays
ms.openlocfilehash: 2e7cf9c8f7d4e6f1d5bc66310f56d3de9461e592
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599317"
---
# <a name="about-arrays"></a><span data-ttu-id="062ef-103">配列について</span><span class="sxs-lookup"><span data-stu-id="062ef-103">About Arrays</span></span>

## <a name="short-description"></a><span data-ttu-id="062ef-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="062ef-104">Short Description</span></span>
<span data-ttu-id="062ef-105">項目のコレクションを格納するように設計されたデータ構造体である配列について説明します。</span><span class="sxs-lookup"><span data-stu-id="062ef-105">Describes arrays, which are data structures designed to store collections of items.</span></span>

## <a name="long-description"></a><span data-ttu-id="062ef-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="062ef-106">Long Description</span></span>

<span data-ttu-id="062ef-107">配列は、項目のコレクションを格納するように設計されたデータ構造体です。</span><span class="sxs-lookup"><span data-stu-id="062ef-107">An array is a data structure that is designed to store a collection of items.</span></span>
<span data-ttu-id="062ef-108">項目は、同じ型または異なる型にすることができます。</span><span class="sxs-lookup"><span data-stu-id="062ef-108">The items can be the same type or different types.</span></span>

<span data-ttu-id="062ef-109">Windows PowerShell 3.0 以降では、0個または1個のオブジェクトのコレクションに配列のプロパティがいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="062ef-109">Beginning in Windows PowerShell 3.0, a collection of zero or one object has some properties of arrays.</span></span>

## <a name="creating-and-initializing-an-array"></a><span data-ttu-id="062ef-110">配列の作成と初期化</span><span class="sxs-lookup"><span data-stu-id="062ef-110">Creating and initializing an array</span></span>

<span data-ttu-id="062ef-111">配列を作成して初期化するには、変数に複数の値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="062ef-111">To create and initialize an array, assign multiple values to a variable.</span></span> <span data-ttu-id="062ef-112">配列に格納されている値は、コンマで区切られ、代入演算子 () によって変数名から区切られ `=` ます。</span><span class="sxs-lookup"><span data-stu-id="062ef-112">The values stored in the array are delimited with a comma and separated from the variable name by the assignment operator (`=`).</span></span>

<span data-ttu-id="062ef-113">たとえば、 `$A` 7 つの数値 (int) 値22、5、10、8、12、9、および80を含むという名前の配列を作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="062ef-113">For example, to create an array named `$A` that contains the seven numeric (int) values of 22, 5, 10, 8, 12, 9, and 80, type:</span></span>

```powershell
$A = 22,5,10,8,12,9,80
```

<span data-ttu-id="062ef-114">コンマは、1つの項目の前にコンマを配置することで、1つの項目配列を初期化するためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="062ef-114">The comma can also be used to initialize a single item array by placing the comma before the single item.</span></span>

<span data-ttu-id="062ef-115">たとえば、単一の値を持つという名前の単一の item 配列を作成するには、次のように `$B` 入力します。</span><span class="sxs-lookup"><span data-stu-id="062ef-115">For example, to create a single item array named `$B` containing the single value of 7, type:</span></span>

```powershell
$B = ,7
```

<span data-ttu-id="062ef-116">範囲演算子 () を使用して、配列を作成および初期化することもでき `..` ます。</span><span class="sxs-lookup"><span data-stu-id="062ef-116">You can also create and initialize an array by using the range operator (`..`).</span></span>
<span data-ttu-id="062ef-117">次の例では、5 ~ 8 の値を含む配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="062ef-117">The following example creates an array containing the values 5 through 8.</span></span>

```powershell
$C = 5..8
```

<span data-ttu-id="062ef-118">結果として、 `$C` 5、6、7、8の4つの値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="062ef-118">As a result, `$C` contains four values: 5, 6, 7, and 8.</span></span>

<span data-ttu-id="062ef-119">データ型が指定されていない場合、PowerShell は各配列をオブジェクト配列 (**system.object []**) として作成します。</span><span class="sxs-lookup"><span data-stu-id="062ef-119">When no data type is specified, PowerShell creates each array as an object array (**System.Object[]**).</span></span> <span data-ttu-id="062ef-120">配列のデータ型を特定するには、 **GetType ()** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="062ef-120">To determine the data type of an array, use the **GetType()** method.</span></span> <span data-ttu-id="062ef-121">たとえば、配列のデータ型を確認するには、次のように `$A` 入力します。</span><span class="sxs-lookup"><span data-stu-id="062ef-121">For example, to determine the data type of the `$A` array, type:</span></span>

```powershell
$A.GetType()
```

<span data-ttu-id="062ef-122">厳密に型指定された配列 (特定の型の値のみを格納できる配列) を作成するには、 **string []**、 **long []**、 **int32 []** などの配列型として変数をキャストします。</span><span class="sxs-lookup"><span data-stu-id="062ef-122">To create a strongly typed array, that is, an array that can contain only values of a particular type, cast the variable as an array type, such as **string[]**, **long[]**, or **int32[]**.</span></span> <span data-ttu-id="062ef-123">配列をキャストするには、変数名の前に、角かっこで囲まれた配列型を使用します。</span><span class="sxs-lookup"><span data-stu-id="062ef-123">To cast an array, precede the variable name with an array type enclosed in brackets.</span></span> <span data-ttu-id="062ef-124">たとえば、 `$ia` 4 つの整数 (1500、2230、3350、および 4000) を含むという名前の32ビット整数配列を作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="062ef-124">For example, to create a 32-bit integer array named `$ia` containing four integers (1500, 2230, 3350, and 4000), type:</span></span>

```powershell
[int32[]]$ia = 1500,2230,3350,4000
```

<span data-ttu-id="062ef-125">そのため、配列には `$ia` 整数のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="062ef-125">As a result, the `$ia` array can contain only integers.</span></span>

<span data-ttu-id="062ef-126">Microsoft .NET Framework では、サポートされている任意の型にキャストされる配列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="062ef-126">You can create arrays that are cast to any supported type in the Microsoft .NET Framework.</span></span> <span data-ttu-id="062ef-127">たとえば、が `Get-Process` プロセスを表すためにを取得するオブジェクトの種類は **、に** なります。</span><span class="sxs-lookup"><span data-stu-id="062ef-127">For example, the objects that `Get-Process` retrieves to represent processes are of the **System.Diagnostics.Process** type.</span></span> <span data-ttu-id="062ef-128">厳密に型指定されたプロセスオブジェクトの配列を作成するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="062ef-128">To create a strongly typed array of process objects, enter the following command:</span></span>

```powershell
[Diagnostics.Process[]]$zz = Get-Process
```

## <a name="the-array-sub-expression-operator"></a><span data-ttu-id="062ef-129">配列のサブ式演算子</span><span class="sxs-lookup"><span data-stu-id="062ef-129">The array sub-expression operator</span></span>

<span data-ttu-id="062ef-130">配列のサブ式演算子は、その内部のステートメントから配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="062ef-130">The array sub-expression operator creates an array from the statements inside it.</span></span> <span data-ttu-id="062ef-131">演算子内のステートメントによって生成される場合は、演算子によって配列に格納されます。</span><span class="sxs-lookup"><span data-stu-id="062ef-131">Whatever the statement inside the operator produces, the operator will place it in an array.</span></span> <span data-ttu-id="062ef-132">0個または1個のオブジェクトがある場合でも同様です。</span><span class="sxs-lookup"><span data-stu-id="062ef-132">Even if there is zero or one object.</span></span>

<span data-ttu-id="062ef-133">配列演算子の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="062ef-133">The syntax of the array operator is as follows:</span></span>

```syntax
@( ... )
```

<span data-ttu-id="062ef-134">配列演算子を使用すると、0個または1個のオブジェクトの配列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="062ef-134">You can use the array operator to create an array of zero or one object.</span></span> <span data-ttu-id="062ef-135">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="062ef-135">For example:</span></span>

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

<span data-ttu-id="062ef-136">配列演算子は、オブジェクトを取得するときにスクリプトで役に立ちますが、取得するオブジェクトの数を把握していません。</span><span class="sxs-lookup"><span data-stu-id="062ef-136">The array operator is useful in scripts when you are getting objects, but do not know how many objects you get.</span></span> <span data-ttu-id="062ef-137">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="062ef-137">For example:</span></span>

```powershell
$p = @(Get-Process Notepad)
```

<span data-ttu-id="062ef-138">配列のサブ式演算子の詳細については、「 [about_Operators](about_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="062ef-138">For more information about the array sub-expression operator, see [about_Operators](about_Operators.md).</span></span>

## <a name="accessing-and-using-array-elements"></a><span data-ttu-id="062ef-139">配列要素へのアクセスと使用</span><span class="sxs-lookup"><span data-stu-id="062ef-139">Accessing and using array elements</span></span>

### <a name="reading-an-array"></a><span data-ttu-id="062ef-140">配列の読み取り</span><span class="sxs-lookup"><span data-stu-id="062ef-140">Reading an array</span></span>

<span data-ttu-id="062ef-141">配列は、変数名を使用して参照できます。</span><span class="sxs-lookup"><span data-stu-id="062ef-141">You can refer to an array by using its variable name.</span></span> <span data-ttu-id="062ef-142">配列内のすべての要素を表示するには、配列名を入力します。</span><span class="sxs-lookup"><span data-stu-id="062ef-142">To display all the elements in the array, type the array name.</span></span> <span data-ttu-id="062ef-143">たとえば、は、 `$a` 整数0、1、2、9までの整数を含む配列で、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="062ef-143">For example, assuming `$a` is an array containing integers 0, 1, 2, until 9; typing:</span></span>

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

<span data-ttu-id="062ef-144">位置0から始まるインデックスを使用して、配列内の要素を参照できます。</span><span class="sxs-lookup"><span data-stu-id="062ef-144">You can refer to the elements in an array by using an index, beginning at position 0.</span></span> <span data-ttu-id="062ef-145">インデックス番号を角かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="062ef-145">Enclose the index number in brackets.</span></span> <span data-ttu-id="062ef-146">たとえば、配列内の最初の要素を表示するには、次のように `$a` 入力します。</span><span class="sxs-lookup"><span data-stu-id="062ef-146">For example, to display the first element in the `$a` array, type:</span></span>

```powershell
$a[0]
```

```Output
0
```

<span data-ttu-id="062ef-147">配列の3番目の要素を表示するには `$a` 、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="062ef-147">To display the third element in the `$a` array, type:</span></span>

```powershell
$a[2]
```

```Output
2
```

<span data-ttu-id="062ef-148">配列の一部を取得するには、インデックスの範囲演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="062ef-148">You can retrieve part of the array using a range operator for the index.</span></span> <span data-ttu-id="062ef-149">たとえば、配列の2番目から5番目の要素を取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="062ef-149">For example, to retrieve the second to fifth elements of the array, you would type:</span></span>

```powershell
$a[1..4]
```

```Output
1
2
3
4
```

<span data-ttu-id="062ef-150">配列の末尾からの負の数。</span><span class="sxs-lookup"><span data-stu-id="062ef-150">Negative numbers count from the end of the array.</span></span> <span data-ttu-id="062ef-151">たとえば、"-1" は配列の最後の要素を参照します。</span><span class="sxs-lookup"><span data-stu-id="062ef-151">For example, "-1" refers to the last element of the array.</span></span> <span data-ttu-id="062ef-152">配列の最後の3つの要素を表示するには、インデックスの昇順で、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="062ef-152">To display the last three elements of the array, in index ascending order, type:</span></span>

```powershell
$a = 0 .. 9
$a[-3..-1]
```

```Output
7
8
9
```

<span data-ttu-id="062ef-153">負のインデックスを降順で入力すると、出力が変わります。</span><span class="sxs-lookup"><span data-stu-id="062ef-153">If you type negative indexes in descending order, your output changes.</span></span>

```powershell
$a = 0 .. 9
$a[-1..-3]
```

```Output
9
8
7
```

<span data-ttu-id="062ef-154">ただし、この表記法を使用する場合は注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="062ef-154">However, be cautious when using this notation.</span></span> <span data-ttu-id="062ef-155">記法は、終了境界から配列の先頭までの間に循環します。</span><span class="sxs-lookup"><span data-stu-id="062ef-155">The notation cycles from the end boundary to the beginning of the array.</span></span>

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

<span data-ttu-id="062ef-156">また、1つの一般的な誤りは、 `$a[0..-2]` 最後の要素を除き、配列のすべての要素を参照するということです。</span><span class="sxs-lookup"><span data-stu-id="062ef-156">Also, one common mistake is to assume `$a[0..-2]` refers to all the elements of the array, except for the last one.</span></span> <span data-ttu-id="062ef-157">これは、配列内の最初、最後、および最後から2番目の要素を参照します。</span><span class="sxs-lookup"><span data-stu-id="062ef-157">It refers to the first, last, and second-to-last elements in the array.</span></span>

<span data-ttu-id="062ef-158">プラス演算子 () を使用し `+` て、範囲を配列内の要素のリストと結合することができます。</span><span class="sxs-lookup"><span data-stu-id="062ef-158">You can use the plus operator (`+`) to combine a ranges with a list of elements in an array.</span></span> <span data-ttu-id="062ef-159">たとえば、インデックス位置0、2、および 4 ~ 6 の要素を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="062ef-159">For example, to display the elements at index positions 0, 2, and 4 through 6, type:</span></span>

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

<span data-ttu-id="062ef-160">また、複数の範囲と個々の要素を一覧表示するには、プラス演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="062ef-160">Also, to list multiple ranges and individual elements you can use the plus operator.</span></span> <span data-ttu-id="062ef-161">たとえば、要素を0から2、4 ~ 6、要素を8番目の位置の型で一覧表示するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="062ef-161">For example, to list elements zero to two, four to six, and the element at eighth positional type:</span></span>

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

### <a name="iterations-over-array-elements"></a><span data-ttu-id="062ef-162">配列要素の反復処理</span><span class="sxs-lookup"><span data-stu-id="062ef-162">Iterations over array elements</span></span>

<span data-ttu-id="062ef-163">ForEach、For、While ループなどのループ構造を使用して、配列内の要素を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="062ef-163">You can also use looping constructs, such as ForEach, For, and While loops, to refer to the elements in an array.</span></span> <span data-ttu-id="062ef-164">たとえば、ForEach ループを使用して配列内の要素を表示するには、次のように `$a` 入力します。</span><span class="sxs-lookup"><span data-stu-id="062ef-164">For example, to use a ForEach loop to display the elements in the `$a` array, type:</span></span>

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

<span data-ttu-id="062ef-165">Foreach ループは配列を反復処理し、配列の末尾に到達するまで配列内の各値を返します。</span><span class="sxs-lookup"><span data-stu-id="062ef-165">The Foreach loop iterates through the array and returns each value in the array until reaching the end of the array.</span></span>

<span data-ttu-id="062ef-166">For ループは、配列内の要素の検査中にカウンターをインクリメントする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="062ef-166">The For loop is useful when you are incrementing counters while examining the elements in an array.</span></span> <span data-ttu-id="062ef-167">たとえば、For ループを使用して配列内の他のすべての値を返すには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="062ef-167">For example, to use a For loop to return every other value in an array, type:</span></span>

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

<span data-ttu-id="062ef-168">While ループを使用すると、定義された条件が満たされなくなるまで、配列内の要素を表示できます。</span><span class="sxs-lookup"><span data-stu-id="062ef-168">You can use a While loop to display the elements in an array until a defined condition is no longer true.</span></span> <span data-ttu-id="062ef-169">たとえば、配列インデックスが4未満のときに配列の要素を表示するには `$a` 、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="062ef-169">For example, to display the elements in the `$a` array while the array index is less than 4, type:</span></span>

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

## <a name="properties-of-arrays"></a><span data-ttu-id="062ef-170">配列のプロパティ</span><span class="sxs-lookup"><span data-stu-id="062ef-170">Properties of arrays</span></span>

### <a name="count-or-length-or-longlength"></a><span data-ttu-id="062ef-171">Count または Length または LongLength</span><span class="sxs-lookup"><span data-stu-id="062ef-171">Count or Length or LongLength</span></span>

<span data-ttu-id="062ef-172">配列内の項目の数を確認するには、 `Length` プロパティまたはそのエイリアスを使用し `Count` ます。</span><span class="sxs-lookup"><span data-stu-id="062ef-172">To determine how many items are in an array, use the `Length` property or its `Count` alias.</span></span> <span data-ttu-id="062ef-173">`Longlength` は、配列に2147483647個を超える要素が含まれている場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="062ef-173">`Longlength` is useful if the array contains more than 2,147,483,647 elements.</span></span>

```powershell
$a = 0..9
$a.Count
$a.Length
```

```Output
10
10
```

### <a name="rank"></a><span data-ttu-id="062ef-174">順位</span><span class="sxs-lookup"><span data-stu-id="062ef-174">Rank</span></span>

<span data-ttu-id="062ef-175">配列内の次元数を返します。</span><span class="sxs-lookup"><span data-stu-id="062ef-175">Returns the number of dimensions in the array.</span></span> <span data-ttu-id="062ef-176">PowerShell のほとんどの配列には、ディメンションが1つだけあります。</span><span class="sxs-lookup"><span data-stu-id="062ef-176">Most arrays in PowerShell have one dimension, only.</span></span> <span data-ttu-id="062ef-177">多次元配列を構築していると思われる場合でも、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="062ef-177">Even when you think you are building a multidimensional array; like the following example:</span></span>

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

<span data-ttu-id="062ef-178">次の例は、.Net Framework を使用して真の多次元配列を作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="062ef-178">The following example shows how to create a truly multidimensional array using the .Net Framework.</span></span>

```powershell
[int[,]]$rank2 = [int[,]]::new(5,5)
$rank2.rank
```

```Output
2
```

## <a name="methods-of-arrays"></a><span data-ttu-id="062ef-179">配列のメソッド</span><span class="sxs-lookup"><span data-stu-id="062ef-179">Methods of arrays</span></span>

### <a name="clear"></a><span data-ttu-id="062ef-180">クリア</span><span class="sxs-lookup"><span data-stu-id="062ef-180">Clear</span></span>

<span data-ttu-id="062ef-181">すべての要素の値を、配列の要素型の _既定値_ に設定します。</span><span class="sxs-lookup"><span data-stu-id="062ef-181">Sets all element values to the _default value_ of the array's element type.</span></span>
<span data-ttu-id="062ef-182">Clear () メソッドでは、配列のサイズはリセットされません。</span><span class="sxs-lookup"><span data-stu-id="062ef-182">The Clear() method does not reset the size of the array.</span></span>

<span data-ttu-id="062ef-183">次の例で `$a` は、オブジェクトの配列です。</span><span class="sxs-lookup"><span data-stu-id="062ef-183">In the following example `$a` is an array of objects.</span></span>

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

<span data-ttu-id="062ef-184">この例で `$intA` は、は整数を含むように明示的に型指定されています。</span><span class="sxs-lookup"><span data-stu-id="062ef-184">In this example, `$intA` is explicitly typed to contain integers.</span></span>

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

### <a name="foreach"></a><span data-ttu-id="062ef-185">ForEach</span><span class="sxs-lookup"><span data-stu-id="062ef-185">ForEach</span></span>

<span data-ttu-id="062ef-186">が配列内のすべての要素を反復処理し、配列の各要素に対して特定の操作を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="062ef-186">Allows to iterate over all elements in the array and perform a given operation for each element of the array.</span></span>

<span data-ttu-id="062ef-187">ForEach メソッドには、さまざまな操作を実行するいくつかのオーバーロードがあります。</span><span class="sxs-lookup"><span data-stu-id="062ef-187">The ForEach method has several overloads that perform different operations.</span></span>

```
ForEach(scriptblock expression)
ForEach(scriptblock expression, object[] arguments)
ForEach(type convertToType)
ForEach(string propertyName)
ForEach(string propertyName, object[] newValue)
ForEach(string methodName)
ForEach(string methodName, object[] arguments)
```

#### <a name="foreachscriptblock-expression"></a><span data-ttu-id="062ef-188">ForEach (scriptblock 式)</span><span class="sxs-lookup"><span data-stu-id="062ef-188">ForEach(scriptblock expression)</span></span>

#### <a name="foreachscriptblock-expression-object-arguments"></a><span data-ttu-id="062ef-189">ForEach (scriptblock 式、object [] 引数)</span><span class="sxs-lookup"><span data-stu-id="062ef-189">ForEach(scriptblock expression, object[] arguments)</span></span>

<span data-ttu-id="062ef-190">このメソッドは、PowerShell v4 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="062ef-190">This method was added in PowerShell v4.</span></span>

> [!NOTE]
> <span data-ttu-id="062ef-191">構文では、スクリプトブロックを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="062ef-191">The syntax requires the usage of a script block.</span></span> <span data-ttu-id="062ef-192">Scriptblock が唯一のパラメーターの場合、かっこは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="062ef-192">Parentheses are optional if the scriptblock is the only parameter.</span></span> <span data-ttu-id="062ef-193">また、メソッドと始めかっこまたは中かっこの間にスペースを配置することはできません。</span><span class="sxs-lookup"><span data-stu-id="062ef-193">Also, there must not be a space between the method and the opening parenthesis or brace.</span></span>

<span data-ttu-id="062ef-194">次の例は、foreach メソッドの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="062ef-194">The following example shows how use the foreach method.</span></span> <span data-ttu-id="062ef-195">この場合、目的は配列内の要素の二乗値を生成することです。</span><span class="sxs-lookup"><span data-stu-id="062ef-195">In this case the intent is to generate the square value of the elements in the array.</span></span>

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

<span data-ttu-id="062ef-196">のパラメーターと同じように、パラメーターを使用すると、 `-ArgumentList` `ForEach-Object` `arguments` 引数の配列を、それを受け入れるように構成されたスクリプトブロックに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="062ef-196">Just like the `-ArgumentList` parameter of `ForEach-Object`, the `arguments` parameter allows the passing of an array of arguments to a script block configured to accept them.</span></span>

<span data-ttu-id="062ef-197">**ArgumentList** の動作の詳細については、「 [about_Splatting](about_Splatting.md#splatting-with-arrays)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="062ef-197">For more information about the behavior of **ArgumentList**, see [about_Splatting](about_Splatting.md#splatting-with-arrays).</span></span>

#### <a name="foreachtype-converttotype"></a><span data-ttu-id="062ef-198">ForEach (型 convertToType)</span><span class="sxs-lookup"><span data-stu-id="062ef-198">ForEach(type convertToType)</span></span>

<span data-ttu-id="062ef-199">メソッドを使用すると、 `ForEach` 要素を別の型に迅速にキャストできます。次の例では、文字列の日付のリストを型に変換する方法を示します `[DateTime]` 。</span><span class="sxs-lookup"><span data-stu-id="062ef-199">The `ForEach` method can be used to swiftly cast the elements to a different type; the following example shows how to convert a list of string dates to `[DateTime]` type.</span></span>

```powershell
@("1/1/2017", "2/1/2017", "3/1/2017").ForEach([datetime])
```

```Output

Sunday, January 1, 2017 12:00:00 AM
Wednesday, February 1, 2017 12:00:00 AM
Wednesday, March 1, 2017 12:00:00 AM
```

#### <a name="foreachstring-propertyname"></a><span data-ttu-id="062ef-200">ForEach (文字列 propertyName)</span><span class="sxs-lookup"><span data-stu-id="062ef-200">ForEach(string propertyName)</span></span>

#### <a name="foreachstring-propertyname-object-newvalue"></a><span data-ttu-id="062ef-201">ForEach (string propertyName, object [] newValue)</span><span class="sxs-lookup"><span data-stu-id="062ef-201">ForEach(string propertyName, object[] newValue)</span></span>

<span data-ttu-id="062ef-202">メソッドを使用して、 `ForEach` コレクション内のすべての項目のプロパティ値をすばやく取得したり、設定したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="062ef-202">The `ForEach` method can also be used to quickly retrieve, or set property values for every item in the collection.</span></span>

```powershell
# Set all LastAccessTime properties of files to the current date.
(dir 'C:\Temp').ForEach('LastAccessTime', (Get-Date))
# View the newly set LastAccessTime of all items, and find Unique entries.
(dir 'C:\Temp').ForEach('LastAccessTime') | Get-Unique
```

```Output
Wednesday, June 20, 2018 9:21:57 AM
```

#### <a name="foreachstring-methodname"></a><span data-ttu-id="062ef-203">ForEach (文字列 methodName)</span><span class="sxs-lookup"><span data-stu-id="062ef-203">ForEach(string methodName)</span></span>

#### <a name="foreachstring-methodname-object-arguments"></a><span data-ttu-id="062ef-204">ForEach (文字列 methodName、object [] 引数)</span><span class="sxs-lookup"><span data-stu-id="062ef-204">ForEach(string methodName, object[] arguments)</span></span>

<span data-ttu-id="062ef-205">最後に、メソッドを使用して、 `ForEach` コレクション内のすべての項目に対してメソッドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="062ef-205">Lastly, `ForEach` methods can be used to execute a method on every item in the collection.</span></span>

```powershell
("one", "two", "three").ForEach("ToUpper")
```

```Output
ONE
TWO
THREE
```

<span data-ttu-id="062ef-206">のパラメーターと同じように、パラメーターを使用すると、 `-ArgumentList` `ForEach-Object` `arguments` 引数の配列を、それを受け入れるように構成されたスクリプトブロックに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="062ef-206">Just like the `-ArgumentList` parameter of `ForEach-Object`, the `arguments` parameter allows the passing of an array of arguments to a script block configured to accept them.</span></span>

> [!NOTE]
> <span data-ttu-id="062ef-207">Windows PowerShell 3.0 以降では、コレクション内の各項目のプロパティを取得し、メソッドを実行することもできます。詳細については、「スカラーオブジェクトとコレクションのメソッド」を参照してください [about_methods](about_methods.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="062ef-207">Starting in Windows PowerShell 3.0 retrieving properties and executing methods for each item in a collection can also be accomplished using "Methods of scalar objects and collections" You can read more about that here [about_methods](about_methods.md).</span></span>

### <a name="where"></a><span data-ttu-id="062ef-208">Where</span><span class="sxs-lookup"><span data-stu-id="062ef-208">Where</span></span>

<span data-ttu-id="062ef-209">配列の要素をフィルター処理または選択できるようにします。</span><span class="sxs-lookup"><span data-stu-id="062ef-209">Allows to filter or select the elements of the array.</span></span> <span data-ttu-id="062ef-210">スクリプトは、ゼロ (0)、空の文字列、 `$false` または `$null` の後に表示する要素に対して、 `Where`</span><span class="sxs-lookup"><span data-stu-id="062ef-210">The script must evaluate to anything different than: zero (0), empty string, `$false` or `$null` for the element to show after the `Where`</span></span>

<span data-ttu-id="062ef-211">メソッドには1つの定義があり `Where` ます。</span><span class="sxs-lookup"><span data-stu-id="062ef-211">There is one definition for the `Where` method.</span></span>

```
Where(scriptblock expression[, WhereOperatorSelectionMode mode
                            [, int numberToReturn]])
```

> [!NOTE]
> <span data-ttu-id="062ef-212">構文では、スクリプトブロックを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="062ef-212">The syntax requires the usage of a script block.</span></span> <span data-ttu-id="062ef-213">Scriptblock が唯一のパラメーターの場合、かっこは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="062ef-213">Parentheses are optional if the scriptblock is the only parameter.</span></span> <span data-ttu-id="062ef-214">また、メソッドと始めかっこまたは中かっこの間にスペースを配置することはできません。</span><span class="sxs-lookup"><span data-stu-id="062ef-214">Also, there must not be a space between the method and the opening parenthesis or brace.</span></span>

<span data-ttu-id="062ef-215">`Expression`は、フィルター処理に必要な scriptblock です `mode` 。オプションの引数を使用すると、追加の選択機能を使用でき `numberToReturn` ます。また、省略可能な引数を使用すると、フィルターから返される項目の数を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="062ef-215">The `Expression` is scriptblock that is required for filtering, the `mode` optional argument allows additional selection capabilities, and the `numberToReturn` optional argument allows the ability to limit how many items are returned from the filter.</span></span>

<span data-ttu-id="062ef-216">に使用できる値 `mode` は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="062ef-216">The acceptable values for `mode` are:</span></span>

- <span data-ttu-id="062ef-217">Default (0)-すべての項目を返す</span><span class="sxs-lookup"><span data-stu-id="062ef-217">Default (0) - Return all items</span></span>
- <span data-ttu-id="062ef-218">最初の (1)-最初の項目を返します。</span><span class="sxs-lookup"><span data-stu-id="062ef-218">First (1) - Return the first item</span></span>
- <span data-ttu-id="062ef-219">Last (2)-最後の項目を返します。</span><span class="sxs-lookup"><span data-stu-id="062ef-219">Last (2) - Return the last item</span></span>
- <span data-ttu-id="062ef-220">延期 (3)-条件が true になるまで項目をスキップし、残りの項目を返します</span><span class="sxs-lookup"><span data-stu-id="062ef-220">SkipUntil (3) - Skip items until condition is true, the return the remaining items</span></span>
- <span data-ttu-id="062ef-221">Until (4)-条件が true になるまですべての項目を返す</span><span class="sxs-lookup"><span data-stu-id="062ef-221">Until (4) - Return all items until condition is true</span></span>
- <span data-ttu-id="062ef-222">Split (5)-2 つの要素の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="062ef-222">Split (5) - Return an array of two elements</span></span>
  - <span data-ttu-id="062ef-223">最初の要素には一致する項目が含まれます</span><span class="sxs-lookup"><span data-stu-id="062ef-223">The first element contains matching items</span></span>
  - <span data-ttu-id="062ef-224">2番目の要素には残りの項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="062ef-224">The second element contains the remaining items</span></span>

<span data-ttu-id="062ef-225">次の例は、配列からすべての奇数を選択する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="062ef-225">The following example shows how to select all odd numbers from the array.</span></span>

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

<span data-ttu-id="062ef-226">この例では、空でない文字列を選択する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="062ef-226">This example show how to select the strings that are not empty.</span></span>

```powershell
('hi', '', 'there').Where({$_.Length})
```

```Output
hi
there
```

#### <a name="default"></a><span data-ttu-id="062ef-227">Default</span><span class="sxs-lookup"><span data-stu-id="062ef-227">Default</span></span>

<span data-ttu-id="062ef-228">モードでは `Default` 、scriptblock を使用して項目をフィルター処理し `Expression` ます。</span><span class="sxs-lookup"><span data-stu-id="062ef-228">The `Default` mode filters items using the `Expression` scriptblock.</span></span>

<span data-ttu-id="062ef-229">が指定されている場合は、 `numberToReturn` 返される項目の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="062ef-229">If a `numberToReturn` is provided, it specifies the maximum number of items to return.</span></span>

```powershell
# Get the zip files in the current users profile, sorted by LastAccessTime.
$Zips = dir $env:userprofile -Recurse '*.zip' | Sort-Object LastAccessTime
# Get the least accessed file over 100MB
$Zips.Where({$_.Length -gt 100MB}, 'Default', 1)
```

> [!NOTE]
> <span data-ttu-id="062ef-230">モードとモードは、どちらも `Default` `First` 最初の ( `numberToReturn` ) 項目を返し、同義に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="062ef-230">Both the `Default` mode and `First` mode return the first (`numberToReturn`) items, and can be used interchangeably.</span></span>

#### <a name="last"></a><span data-ttu-id="062ef-231">Last (最後へ)</span><span class="sxs-lookup"><span data-stu-id="062ef-231">Last</span></span>

```powershell
$h = (Get-Date).AddHours(-1)
$logs = dir 'C:\' -Recurse '*.log' | Sort-Object CreationTime
# Find the last 5 log files created in the past hour.
$logs.Where({$_.CreationTime -gt $h}, 'Last', 5)
```

#### <a name="skipuntil"></a><span data-ttu-id="062ef-232">延期</span><span class="sxs-lookup"><span data-stu-id="062ef-232">SkipUntil</span></span>

<span data-ttu-id="062ef-233">モードでは、 `SkipUntil` オブジェクトがスクリプトブロック式フィルターに合格するまで、コレクション内のすべてのオブジェクトがスキップされます。</span><span class="sxs-lookup"><span data-stu-id="062ef-233">The `SkipUntil` mode skips all objects in a collection until an object passes the script block expression filter.</span></span> <span data-ttu-id="062ef-234">その後、残りの **すべて** のコレクションアイテムをテストせずに返します。</span><span class="sxs-lookup"><span data-stu-id="062ef-234">It then returns **ALL** remaining collection items without testing them.</span></span> <span data-ttu-id="062ef-235">_1 つの渡す項目のみがテストされ_ ます。</span><span class="sxs-lookup"><span data-stu-id="062ef-235">_Only one passing item is tested_.</span></span>

<span data-ttu-id="062ef-236">つまり、返されるコレクションには、テストされていない、 _渡し_ ている項目と _渡し_ ていない項目の両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="062ef-236">This means the returned collection contains both _passing_ and _non-passing_ items that have NOT been tested.</span></span>

<span data-ttu-id="062ef-237">返される項目の数は、引数に値を渡すことによって制限できます `numberToReturn` 。</span><span class="sxs-lookup"><span data-stu-id="062ef-237">The number of items returned can be limited by passing a value to the `numberToReturn` argument.</span></span>

```powershell
$computers = "Server01", "Server02", "Server03", "localhost", "Server04"
# Find the first available online server.
$computers.Where({ Test-Connection $_ }, 'SkipUntil', 1)
```

```Output
localhost
```

#### <a name="until"></a><span data-ttu-id="062ef-238">Until</span><span class="sxs-lookup"><span data-stu-id="062ef-238">Until</span></span>

<span data-ttu-id="062ef-239">モードは、モードを `Until` 反転し `SkipUntil` ます。</span><span class="sxs-lookup"><span data-stu-id="062ef-239">The `Until` mode inverts the `SkipUntil` mode.</span></span>  <span data-ttu-id="062ef-240">コレクション内の **すべて** の項目を返します。これは、項目がスクリプトブロック式に合格するまで続きます。</span><span class="sxs-lookup"><span data-stu-id="062ef-240">It returns **ALL** items in a collection until an item passes the script block expression.</span></span> <span data-ttu-id="062ef-241">項目が scriptblock 式を _渡す_ と、 `Where` メソッドは項目の処理を停止します。</span><span class="sxs-lookup"><span data-stu-id="062ef-241">Once an item _passes_ the scriptblock expression, the `Where` method stops processing items.</span></span>

<span data-ttu-id="062ef-242">これは、メソッドから _渡されない_ 項目の最初のセットを受け取ることを意味し `Where` ます。</span><span class="sxs-lookup"><span data-stu-id="062ef-242">This means that you receive the first set of _non-passing_ items from the `Where` method.</span></span> <span data-ttu-id="062ef-243">1つの項目が成功し _た後_、残りはテストも返されません。</span><span class="sxs-lookup"><span data-stu-id="062ef-243">_After_ one item passes, the rest are NOT tested or returned.</span></span>

<span data-ttu-id="062ef-244">返される項目の数は、引数に値を渡すことによって制限できます `numberToReturn` 。</span><span class="sxs-lookup"><span data-stu-id="062ef-244">The number of items returned can be limited by passing a value to the `numberToReturn` argument.</span></span>

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
> <span data-ttu-id="062ef-245">とはどちらも、 `Until` `SkipUntil` 項目のバッチをテストしないという前提で動作します。</span><span class="sxs-lookup"><span data-stu-id="062ef-245">Both `Until` and `SkipUntil` operate under the premise of NOT testing a batch of items.</span></span>
>
> <span data-ttu-id="062ef-246">`Until`最初の _パス_ の **前に** ある項目を返します。</span><span class="sxs-lookup"><span data-stu-id="062ef-246">`Until` returns the items **BEFORE** the first _pass_.</span></span>
>
> <span data-ttu-id="062ef-247">`SkipUntil`最初の _パス_ の **後** にあるすべての項目 (最初の引き渡し項目を含む) を返します。</span><span class="sxs-lookup"><span data-stu-id="062ef-247">`SkipUntil` returns all the items **AFTER** the first _pass_, including the first passing item.</span></span>

#### <a name="split"></a><span data-ttu-id="062ef-248">Split</span><span class="sxs-lookup"><span data-stu-id="062ef-248">Split</span></span>

<span data-ttu-id="062ef-249">この `Split` モードでは、コレクションアイテムが分割されるか、コレクションアイテムが2つの異なるコレクションにグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="062ef-249">The `Split` mode splits, or groups collection items into two separate collections.</span></span> <span data-ttu-id="062ef-250">Scriptblock 式を渡すこれらの式と、それ以外の式を渡します。</span><span class="sxs-lookup"><span data-stu-id="062ef-250">Those that pass the scriptblock expression, and those that do not.</span></span>

<span data-ttu-id="062ef-251">が指定されている場合、 `numberToReturn` 最初のコレクションには、指定された値を超えるものではなく、 _渡す_ 項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="062ef-251">If a `numberToReturn` is specified, the first collection, contains the _passing_ items, not to exceed the value specified.</span></span>

<span data-ttu-id="062ef-252">残りのオブジェクトは、式フィルターを **通過** したオブジェクトも、2番目のコレクションで返されます。</span><span class="sxs-lookup"><span data-stu-id="062ef-252">The remaining objects, even those that **PASS** the expression filter, are returned in the second collection.</span></span>

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

## <a name="get-the-members-of-an-array"></a><span data-ttu-id="062ef-253">配列のメンバーを取得する</span><span class="sxs-lookup"><span data-stu-id="062ef-253">Get the members of an array</span></span>

<span data-ttu-id="062ef-254">Length プロパティや **SetValue** メソッドなど、配列のプロパティとメソッドを取得するには、コマンドレットの **InputObject** パラメーターを使用し `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="062ef-254">To get the properties and methods of an array, such as the Length property and the **SetValue** method, use the **InputObject** parameter of the `Get-Member` cmdlet.</span></span>

<span data-ttu-id="062ef-255">パイプを使用して配列をに渡した場合 `Get-Member` 、PowerShell は一度に1つずつ項目を送信し、 `Get-Member` 配列内の各項目の型を返します (重複部分は無視されます)。</span><span class="sxs-lookup"><span data-stu-id="062ef-255">When you pipe an array to `Get-Member`, PowerShell sends the items one at a time and `Get-Member` returns the type of each item in the array (ignoring duplicates).</span></span>

<span data-ttu-id="062ef-256">**InputObject** パラメーターを使用すると、は `Get-Member` 配列のメンバーを返します。</span><span class="sxs-lookup"><span data-stu-id="062ef-256">When you use the **InputObject** parameter, `Get-Member` returns the members of the array.</span></span>

<span data-ttu-id="062ef-257">たとえば、次のコマンドは、配列変数のメンバーを取得し `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="062ef-257">For example, the following command gets the members of the `$a` array variable.</span></span>

```powershell
Get-Member -InputObject $a
```

<span data-ttu-id="062ef-258">また、コマンドレットにパイプされる値の前にコンマ (,) を入力して、配列のメンバーを取得することもでき `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="062ef-258">You can also get the members of an array by typing a comma (,) before the value that is piped to the `Get-Member` cmdlet.</span></span> <span data-ttu-id="062ef-259">コンマを使用すると、配列の配列の2番目の項目が配列になります。</span><span class="sxs-lookup"><span data-stu-id="062ef-259">The comma makes the array the second item in an array of arrays.</span></span> <span data-ttu-id="062ef-260">PowerShell は、配列を一度に1つずつパイプし、 `Get-Member` 配列のメンバーを返します。</span><span class="sxs-lookup"><span data-stu-id="062ef-260">PowerShell pipes the arrays one at a time and `Get-Member` returns the members of the array.</span></span> <span data-ttu-id="062ef-261">次の2つの例のようになります。</span><span class="sxs-lookup"><span data-stu-id="062ef-261">Like the next two examples.</span></span>

```powershell
,$a | Get-Member

,(1,2,3) | Get-Member
```

## <a name="manipulating-an-array"></a><span data-ttu-id="062ef-262">配列の操作</span><span class="sxs-lookup"><span data-stu-id="062ef-262">Manipulating an array</span></span>

<span data-ttu-id="062ef-263">配列内の要素を変更し、配列に要素を追加して、2つの配列の値を3番目の配列に結合できます。</span><span class="sxs-lookup"><span data-stu-id="062ef-263">You can change the elements in an array, add an element to an array, and combine the values from two arrays into a third array.</span></span>

<span data-ttu-id="062ef-264">配列内の特定の要素の値を変更するには、変更する要素の配列名とインデックスを指定し、代入演算子 () を使用して `=` 要素に新しい値を指定します。</span><span class="sxs-lookup"><span data-stu-id="062ef-264">To change the value of a particular element in an array, specify the array name and the index of the element that you want to change, and then use the assignment operator (`=`) to specify a new value for the element.</span></span> <span data-ttu-id="062ef-265">たとえば、配列の2番目の項目 (インデックス位置 1) の値を10に変更するには、次のように `$a` 入力します。</span><span class="sxs-lookup"><span data-stu-id="062ef-265">For example, to change the value of the second item in the `$a` array (index position 1) to 10, type:</span></span>

```powershell
$a[1] = 10
```

<span data-ttu-id="062ef-266">配列の **SetValue** メソッドを使用して値を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="062ef-266">You can also use the **SetValue** method of an array to change a value.</span></span> <span data-ttu-id="062ef-267">次の例では、配列の2番目の値 (インデックス位置 1) `$a` を500に変更します。</span><span class="sxs-lookup"><span data-stu-id="062ef-267">The following example changes the second value (index position 1) of the `$a` array to 500:</span></span>

```powershell
$a.SetValue(500,1)
```

<span data-ttu-id="062ef-268">演算子を使用すると、 `+=` 配列に要素を追加できます。</span><span class="sxs-lookup"><span data-stu-id="062ef-268">You can use the `+=` operator to add an element to an array.</span></span> <span data-ttu-id="062ef-269">次の例は、要素を配列に追加する方法を示して `$a` います。</span><span class="sxs-lookup"><span data-stu-id="062ef-269">The following example shows how to add an element to the `$a` array.</span></span>

```powershell
$a = @(0..4)
$a += 5
```

> [!NOTE]
> <span data-ttu-id="062ef-270">演算子を使用すると `+=` 、PowerShell は実際には、元の配列の値と追加された値を使用して、新しい配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="062ef-270">When you use the `+=` operator, PowerShell actually creates a new array with the values of the original array and the added value.</span></span> <span data-ttu-id="062ef-271">この場合、操作が複数回繰り返されるか、配列のサイズが大きすぎると、パフォーマンスの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="062ef-271">This might cause performance issues if the operation is repeated several times or the size of the array is too big.</span></span>

<span data-ttu-id="062ef-272">配列から要素を削除するのは簡単ではありませんが、既存の配列の選択した要素のみを含む新しい配列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="062ef-272">It is not easy to delete elements from an array, but you can create a new array that contains only selected elements of an existing array.</span></span> <span data-ttu-id="062ef-273">たとえば、 `$t` インデックス位置2の値を除いて、配列内のすべての要素を含む配列を作成するには、 `$a` 次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="062ef-273">For example, to create the `$t` array with all the elements in the `$a` array except for the value at index position 2, type:</span></span>

```powershell
$t = $a[0,1 + 3..($a.length - 1)]
```

<span data-ttu-id="062ef-274">2つの配列を1つの配列に結合するには、プラス演算子 () を使用し `+` ます。</span><span class="sxs-lookup"><span data-stu-id="062ef-274">To combine two arrays into a single array, use the plus operator (`+`).</span></span> <span data-ttu-id="062ef-275">次の例では、2つの配列を作成し、それらを結合して、結果として得られる配列を表示します。</span><span class="sxs-lookup"><span data-stu-id="062ef-275">The following example creates two arrays, combines them, and then displays the resulting combined array.</span></span>

```powershell
$x = 1,3
$y = 5,9
$z = $x + $y
```

<span data-ttu-id="062ef-276">結果として、 `$z` 配列には1、3、5、および9が含まれます。</span><span class="sxs-lookup"><span data-stu-id="062ef-276">As a result, the `$z` array contains 1, 3, 5, and 9.</span></span>

<span data-ttu-id="062ef-277">配列を削除するには、配列に値を代入し `$null` ます。</span><span class="sxs-lookup"><span data-stu-id="062ef-277">To delete an array, assign a value of `$null` to the array.</span></span> <span data-ttu-id="062ef-278">次のコマンドは、変数内の配列を削除し `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="062ef-278">The following command deletes the array in the `$a` variable.</span></span>

`$a = $null`

<span data-ttu-id="062ef-279">コマンドレットを使用することもできますが、 `Remove-Item` `$null` 特に大きな配列の場合は、の値を割り当てる方が高速です。</span><span class="sxs-lookup"><span data-stu-id="062ef-279">You can also use the `Remove-Item` cmdlet, but assigning a value of `$null` is faster, especially for large arrays.</span></span>

## <a name="arrays-of-zero-or-one"></a><span data-ttu-id="062ef-280">0個または1個の配列</span><span class="sxs-lookup"><span data-stu-id="062ef-280">Arrays of zero or one</span></span>

<span data-ttu-id="062ef-281">Windows PowerShell 3.0 以降では、0個または1個のオブジェクトのコレクションに Count と Length プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="062ef-281">Beginning in Windows PowerShell 3.0, a collection of zero or one object has the Count and Length property.</span></span> <span data-ttu-id="062ef-282">また、1つのオブジェクトの配列にインデックスを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="062ef-282">Also, you can index into an array of one object.</span></span> <span data-ttu-id="062ef-283">この機能は、コレクションを必要とするコマンドが2つよりも小さい場合に発生するスクリプトエラーを回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="062ef-283">This feature helps you to avoid scripting errors that occur when a command that expects a collection gets fewer than two items.</span></span>

<span data-ttu-id="062ef-284">この機能の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="062ef-284">The following examples demonstrate this feature.</span></span>

### <a name="zero-objects"></a><span data-ttu-id="062ef-285">ゼロオブジェクト</span><span class="sxs-lookup"><span data-stu-id="062ef-285">Zero objects</span></span>

```powershell
$a = $null
$a.Count
$a.Length
```

```Output
0
0
```

### <a name="one-object"></a><span data-ttu-id="062ef-286">1つのオブジェクト</span><span class="sxs-lookup"><span data-stu-id="062ef-286">One object</span></span>

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

## <a name="indexing-support-for-systemtuple-objects"></a><span data-ttu-id="062ef-287">システムの Tuple オブジェクトのインデックス作成のサポート</span><span class="sxs-lookup"><span data-stu-id="062ef-287">Indexing support for System.Tuple objects</span></span>

<span data-ttu-id="062ef-288">PowerShell 6.1 では、配列に似た **タプル** オブジェクトのインデックス付きアクセスのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="062ef-288">PowerShell 6.1 added the support for indexed access of **Tuple** objects, similar to arrays.</span></span>
<span data-ttu-id="062ef-289">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="062ef-289">For example:</span></span>

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

<span data-ttu-id="062ef-290">配列やその他のコレクションオブジェクトとは異なり、 **組** オブジェクトは、パイプラインまたはオブジェクトの配列をサポートするパラメーターによって渡されるときに、単一のオブジェクトとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="062ef-290">Unlike arrays and other collection objects, **Tuple** objects are treated as a single object when passed through the pipeline or by parameters that support arrays of objects.</span></span>

<span data-ttu-id="062ef-291">詳細については、「 [Tuple](/dotnet/api/system.tuple)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="062ef-291">For more information, see [System.Tuple](/dotnet/api/system.tuple).</span></span>

## <a name="see-also"></a><span data-ttu-id="062ef-292">関連項目</span><span class="sxs-lookup"><span data-stu-id="062ef-292">See also</span></span>

- [<span data-ttu-id="062ef-293">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="062ef-293">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)
- [<span data-ttu-id="062ef-294">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="062ef-294">about_Hash_Tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="062ef-295">about_Operators</span><span class="sxs-lookup"><span data-stu-id="062ef-295">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="062ef-296">about_For</span><span class="sxs-lookup"><span data-stu-id="062ef-296">about_For</span></span>](about_For.md)
- [<span data-ttu-id="062ef-297">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="062ef-297">about_Foreach</span></span>](about_Foreach.md)
- [<span data-ttu-id="062ef-298">about_While</span><span class="sxs-lookup"><span data-stu-id="062ef-298">about_While</span></span>](about_While.md)

