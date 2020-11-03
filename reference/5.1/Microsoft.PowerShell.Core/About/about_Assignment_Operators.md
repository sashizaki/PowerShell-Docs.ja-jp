---
description: 演算子を使用して変数に値を割り当てる方法について説明します。
keywords: powershell,コマンドレット
ms.date: 04/26/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_assignment_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Assignment_Operators
ms.openlocfilehash: b9cb0f6a972ef627b7ce2621db489896992b406e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222816"
---
# <a name="about-assignment-operators"></a><span data-ttu-id="88d1b-104">代入演算子の概要</span><span class="sxs-lookup"><span data-stu-id="88d1b-104">About Assignment Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="88d1b-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="88d1b-105">Short description</span></span>
<span data-ttu-id="88d1b-106">演算子を使用して変数に値を割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-106">Describes how to use operators to assign values to variables.</span></span>

## <a name="long-description"></a><span data-ttu-id="88d1b-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="88d1b-107">Long description</span></span>

<span data-ttu-id="88d1b-108">代入演算子は、1つまたは複数の値を変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-108">Assignment operators assign one or more values to a variable.</span></span> <span data-ttu-id="88d1b-109">割り当ての前に、値に対して数値演算を実行できます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-109">They can perform numeric operations on the values before the assignment.</span></span>

<span data-ttu-id="88d1b-110">PowerShell では、次の代入演算子がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="88d1b-110">PowerShell supports the following assignment operators.</span></span>

|<span data-ttu-id="88d1b-111">演算子</span><span class="sxs-lookup"><span data-stu-id="88d1b-111">Operator</span></span>|<span data-ttu-id="88d1b-112">説明</span><span class="sxs-lookup"><span data-stu-id="88d1b-112">Description</span></span>                                                  |
|--------|-------------------------------------------------------------|
|=       |<span data-ttu-id="88d1b-113">変数の値を指定された値に設定します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-113">Sets the value of a variable to the specified value.</span></span>         |
|+=      |<span data-ttu-id="88d1b-114">指定された値で変数の値を増やします。</span><span class="sxs-lookup"><span data-stu-id="88d1b-114">Increases the value of a variable by the specified value, or</span></span> |
|        |<span data-ttu-id="88d1b-115">指定された値を既存の値に追加します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-115">appends the specified value to the existing value.</span></span>           |
|-=      |<span data-ttu-id="88d1b-116">指定された値で変数の値を減らします。</span><span class="sxs-lookup"><span data-stu-id="88d1b-116">Decreases the value of a variable by the specified value.</span></span>    |
|*=      |<span data-ttu-id="88d1b-117">変数の値を指定した値で乗算します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-117">Multiplies the value of a variable by the specified value, or</span></span>|
|        |<span data-ttu-id="88d1b-118">指定された値を既存の値に追加します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-118">appends the specified value to the existing value.</span></span>           |
|/=      |<span data-ttu-id="88d1b-119">指定された値で変数の値を除算します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-119">Divides the value of a variable by the specified value.</span></span>      |
|%=      |<span data-ttu-id="88d1b-120">変数の値を指定された値で除算します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-120">Divides the value of a variable by the specified value and</span></span>   |
|        |<span data-ttu-id="88d1b-121">次に、剰余 (剰余) を変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-121">then assigns the remainder (modulus) to the variable.</span></span>        |
|++      |<span data-ttu-id="88d1b-122">変数の値を増やすか、割り当て可能なプロパティを増やします。</span><span class="sxs-lookup"><span data-stu-id="88d1b-122">Increases the value of a variable, assignable property, or</span></span>   |
|        |<span data-ttu-id="88d1b-123">配列要素を1つ。</span><span class="sxs-lookup"><span data-stu-id="88d1b-123">array element by 1.</span></span>                                          |
|--      |<span data-ttu-id="88d1b-124">変数の値、割り当て可能なプロパティ、またはを減らします。</span><span class="sxs-lookup"><span data-stu-id="88d1b-124">Decreases the value of a variable, assignable property, or</span></span>   |
|        |<span data-ttu-id="88d1b-125">配列要素を1つ。</span><span class="sxs-lookup"><span data-stu-id="88d1b-125">array element by 1.</span></span>                                          |

## <a name="syntax"></a><span data-ttu-id="88d1b-126">構文</span><span class="sxs-lookup"><span data-stu-id="88d1b-126">Syntax</span></span>

<span data-ttu-id="88d1b-127">代入演算子の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="88d1b-127">The syntax of the assignment operators is as follows:</span></span>

<span data-ttu-id="88d1b-128">`<assignable-expression>` `<assignment-operator>` `<value>`</span><span class="sxs-lookup"><span data-stu-id="88d1b-128">`<assignable-expression>` `<assignment-operator>` `<value>`</span></span>

<span data-ttu-id="88d1b-129">割り当て可能な式には、変数とプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="88d1b-129">Assignable expressions include variables and properties.</span></span> <span data-ttu-id="88d1b-130">値には、単一の値、値の配列、またはコマンド、式、またはステートメントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-130">The value can be a single value, an array of values, or a command, expression, or statement.</span></span>

<span data-ttu-id="88d1b-131">インクリメント演算子とデクリメント演算子は単項演算子です。</span><span class="sxs-lookup"><span data-stu-id="88d1b-131">The increment and decrement operators are unary operators.</span></span> <span data-ttu-id="88d1b-132">各には、プレフィックスと後置バージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="88d1b-132">Each has prefix and postfix versions.</span></span>

`<assignable-expression><operator>`
`<operator><assignable-expression>`

<span data-ttu-id="88d1b-133">割り当て可能な式は数値であるか、数値に変換可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="88d1b-133">The assignable expression must be a number or it must be convertible to a number.</span></span>

## <a name="assigning-values"></a><span data-ttu-id="88d1b-134">値の割り当て</span><span class="sxs-lookup"><span data-stu-id="88d1b-134">Assigning values</span></span>

<span data-ttu-id="88d1b-135">変数は、値を格納するメモリ空間という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-135">Variables are named memory spaces that store values.</span></span> <span data-ttu-id="88d1b-136">変数に値を格納するには、代入演算子を使用し `=` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-136">You store the values in variables by using the assignment operator `=`.</span></span> <span data-ttu-id="88d1b-137">新しい値を使用すると、変数の既存の値を置き換えることができます。また、既存の値に新しい値を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-137">The new value can replace the existing value of the variable, or you can append a new value to the existing value.</span></span>

<span data-ttu-id="88d1b-138">基本代入演算子は等号 `=` `(ASCII 61)` です。</span><span class="sxs-lookup"><span data-stu-id="88d1b-138">The basic assignment operator is the equal sign `=` `(ASCII 61)`.</span></span> <span data-ttu-id="88d1b-139">たとえば、次のステートメントは、値 PowerShell を変数に割り当て `$MyShell` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-139">For example, the following statement assigns the value PowerShell to the `$MyShell` variable:</span></span>

```powershell
$MyShell = "PowerShell"
```

<span data-ttu-id="88d1b-140">PowerShell で変数に値を割り当てると、変数がまだ存在しない場合は作成されます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-140">When you assign a value to a variable in PowerShell, the variable is created if it did not already exist.</span></span> <span data-ttu-id="88d1b-141">たとえば、次の2つの代入ステートメントの最初のステートメントは、変数を作成 `$a` し、値6をに割り当て `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-141">For example, the first of the following two assignment statements creates the `$a` variable and assigns a value of 6 to `$a`.</span></span> <span data-ttu-id="88d1b-142">2番目の代入ステートメントでは、12の値をに代入し `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-142">The second assignment statement assigns a value of 12 to `$a`.</span></span> <span data-ttu-id="88d1b-143">最初のステートメントは、新しい変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-143">The first statement creates a new variable.</span></span> <span data-ttu-id="88d1b-144">2番目のステートメントは、値のみを変更します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-144">The second statement changes only its value:</span></span>

```powershell
$a = 6
$a = 12
```

<span data-ttu-id="88d1b-145">PowerShell の変数には、キャストしない限り、特定のデータ型はありません。</span><span class="sxs-lookup"><span data-stu-id="88d1b-145">Variables in PowerShell do not have a specific data type unless you cast them.</span></span>
<span data-ttu-id="88d1b-146">変数に1つのオブジェクトしか含まれていない場合、変数はそのオブジェクトのデータ型を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="88d1b-146">When a variable contains only one object, the variable takes the data type of that object.</span></span> <span data-ttu-id="88d1b-147">変数にオブジェクトのコレクションが含まれている場合、変数には System.object データ型があります。</span><span class="sxs-lookup"><span data-stu-id="88d1b-147">When a variable contains a collection of objects, the variable has the System.Object data type.</span></span> <span data-ttu-id="88d1b-148">そのため、任意の型のオブジェクトをコレクションに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-148">Therefore, you can assign any type of object to the collection.</span></span> <span data-ttu-id="88d1b-149">次の例は、エラーを生成せずに、変数にプロセスオブジェクト、サービスオブジェクト、文字列、および整数を追加できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="88d1b-149">The following example shows that you can add process objects, service objects, strings, and integers to a variable without generating an error:</span></span>

```powershell
$a = Get-Process
$a += Get-Service
$a += "string"
$a += 12
```

<span data-ttu-id="88d1b-150">代入演算子は `=` パイプライン演算子よりも優先順位が低いため `|` 、コマンドパイプラインの結果を変数に割り当てるためにかっこは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="88d1b-150">Because the assignment operator `=` has a lower precedence than the pipeline operator `|`, parentheses are not required to assign the result of a command pipeline to a variable.</span></span> <span data-ttu-id="88d1b-151">たとえば、次のコマンドは、コンピューター上のサービスを並べ替え、並べ替えられたサービスを `$a` 変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-151">For example, the following command sorts the services on the computer and then assigns the sorted services to the `$a` variable:</span></span>

```powershell
$a = Get-Service | Sort-Object -Property name
```

<span data-ttu-id="88d1b-152">次の例のように、ステートメントによって作成された値を変数に割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-152">You can also assign the value created by a statement to a variable, as in the following example:</span></span>

```powershell
$a = if ($b -lt 0) { 0 } else { $b }
```

<span data-ttu-id="88d1b-153">この例で `$a` は、の値が0未満の場合、変数に0が割り当てられ `$b` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-153">This example assigns zero to the `$a` variable if the value of `$b` is less than zero.</span></span> <span data-ttu-id="88d1b-154">の値が0未満でない場合は、の値 `$b` をに代入し `$a` `$b` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-154">It assigns the value of `$b` to `$a` if the value of `$b` is not less than zero.</span></span>

### <a name="the-assignment-operator"></a><span data-ttu-id="88d1b-155">代入演算子</span><span class="sxs-lookup"><span data-stu-id="88d1b-155">The assignment operator</span></span>

<span data-ttu-id="88d1b-156">代入演算子は、 `=` 変数に値を代入します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-156">The assignment operator `=` assigns values to variables.</span></span> <span data-ttu-id="88d1b-157">変数に既に値がある場合、代入演算子は `=` 警告なしで値を置換します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-157">If the variable already has a value, the assignment operator `=` replaces the value without warning.</span></span>

<span data-ttu-id="88d1b-158">次のステートメントでは、変数に整数値6が割り当てられ `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-158">The following statement assigns the integer value 6 to the `$a` variable:</span></span>

```powershell
$a = 6
```

<span data-ttu-id="88d1b-159">文字列値を変数に割り当てるには、次のように文字列値を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-159">To assign a string value to a variable, enclose the string value in quotation marks, as follows:</span></span>

```powershell
$a = "baseball"
```

<span data-ttu-id="88d1b-160">変数に配列 (複数値) を割り当てるには、次のように、値をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="88d1b-160">To assign an array (multiple values) to a variable, separate the values with commas, as follows:</span></span>

```powershell
$a = "apple", "orange", "lemon", "grape"
```

<span data-ttu-id="88d1b-161">ハッシュテーブルを変数に割り当てるには、PowerShell で標準のハッシュテーブル表記を使用します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-161">To assign a hash table to a variable, use the standard hash table notation in PowerShell.</span></span> <span data-ttu-id="88d1b-162">アットマークの後に、 `@` セミコロンで区切られ `;` 、中かっこで囲まれたキーと値のペアを入力し `{ }` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-162">Type an at sign `@` followed by key/value pairs that are separated by semicolons `;` and enclosed in braces `{ }`.</span></span> <span data-ttu-id="88d1b-163">たとえば、ハッシュテーブルを変数に割り当てるには `$a` 、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-163">For example, to assign a hash table to the `$a` variable, type:</span></span>

```powershell
$a = @{one=1; two=2; three=3}
```

<span data-ttu-id="88d1b-164">16進値を変数に割り当てるには、値の前にを指定 `0x` します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-164">To assign hexadecimal values to a variable, precede the value with `0x`.</span></span>
<span data-ttu-id="88d1b-165">PowerShell は、16進数値 (0x10) を10進値 (この場合は 16) に変換し、その値を変数に代入し `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-165">PowerShell converts the hexadecimal value (0x10) to a decimal value (in this case, 16) and assigns that value to the `$a` variable.</span></span> <span data-ttu-id="88d1b-166">たとえば、変数に0x10 の値を割り当てるには `$a` 、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-166">For example, to assign a value of 0x10 to the `$a` variable, type:</span></span>

```powershell
$a = 0x10
```

<span data-ttu-id="88d1b-167">指数値を変数に割り当てるには、ルート番号、文字、 `e` および10の倍数を表す数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-167">To assign an exponential value to a variable, type the root number, the letter `e`, and a number that represents a multiple of 10.</span></span> <span data-ttu-id="88d1b-168">たとえば、3.1415 の値を変数に1000の累乗に割り当てるには、次のように `$a` 入力します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-168">For example, to assign a value of 3.1415 to the power of 1,000 to the `$a` variable, type:</span></span>

```powershell
$a = 3.1415e3
```

<span data-ttu-id="88d1b-169">PowerShell では、キロバイト、メガバイト、ギガバイトをバイトに変換することもでき `KB` `MB` `GB` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-169">PowerShell can also convert kilobytes `KB`, megabytes `MB`, and gigabytes `GB` into bytes.</span></span> <span data-ttu-id="88d1b-170">たとえば、変数に 10 kb の値を割り当てるには `$a` 、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-170">For example, to assign a value of 10 kilobytes to the `$a` variable, type:</span></span>

```powershell
$a = 10kb
```

### <a name="the-assignment-by-addition-operator"></a><span data-ttu-id="88d1b-171">加算演算子による代入</span><span class="sxs-lookup"><span data-stu-id="88d1b-171">The assignment by addition operator</span></span>

<span data-ttu-id="88d1b-172">加算演算子による代入では、 `+=` 変数の値がインクリメントされるか、または指定した値が既存の値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-172">The assignment by addition operator `+=` either increments the value of a variable or appends the specified value to the existing value.</span></span> <span data-ttu-id="88d1b-173">アクションは、変数に数値型または文字列型があるかどうか、および変数に1つの値 (スカラー) または複数の値 (コレクション) が含まれているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="88d1b-173">The action depends on whether the variable has a numeric or string type and whether the variable contains a single value (a scalar) or multiple values (a collection).</span></span>

<span data-ttu-id="88d1b-174">演算子は、 `+=` 2 つの操作を結合します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-174">The `+=` operator combines two operations.</span></span> <span data-ttu-id="88d1b-175">まず、を追加してから、を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-175">First, it adds, and then it assigns.</span></span>
<span data-ttu-id="88d1b-176">したがって、次のステートメントは同等です。</span><span class="sxs-lookup"><span data-stu-id="88d1b-176">Therefore, the following statements are equivalent:</span></span>

```powershell
$a += 2
$a = ($a + 2)
```

<span data-ttu-id="88d1b-177">変数に1つの数値が含まれている場合、演算子は、 `+=` 演算子の右辺にある量だけ既存の値をインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="88d1b-177">When the variable contains a single numeric value, the `+=` operator increments the existing value by the amount on the right side of the operator.</span></span> <span data-ttu-id="88d1b-178">次に、演算子は、結果の値を変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-178">Then, the operator assigns the resulting value to the variable.</span></span> <span data-ttu-id="88d1b-179">次の例では、演算子を使用して `+=` 変数の値を増やす方法を示します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-179">The following example shows how to use the `+=` operator to increase the value of a variable:</span></span>

```powershell
$a = 4
$a += 2
$a
```

```
6
```

<span data-ttu-id="88d1b-180">変数の値が文字列の場合、演算子の右側の値が文字列に追加されます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-180">When the value of the variable is a string, the value on the right side of the operator is appended to the string, as follows:</span></span>

```powershell
$a = "Windows"
$a += " PowerShell"
$a
```

```
Windows PowerShell
```

<span data-ttu-id="88d1b-181">変数の値が配列の場合、演算子は `+=` 演算子の右側にある値を配列に追加します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-181">When the value of the variable is an array, the `+=` operator appends the values on the right side of the operator to the array.</span></span> <span data-ttu-id="88d1b-182">キャストによって配列が明示的に型指定されない限り、次のように任意の型の値を配列に追加できます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-182">Unless the array is explicitly typed by casting, you can append any type of value to the array, as follows:</span></span>

```powershell
$a = 1,2,3
$a += 2
$a
```

```
1
2
3
2
```

<span data-ttu-id="88d1b-183">and</span><span class="sxs-lookup"><span data-stu-id="88d1b-183">and</span></span>

```powershell
$a += "String"
$a
```

```
1
2
3
2
String
```

<span data-ttu-id="88d1b-184">変数の値がハッシュテーブルの場合、演算子は `+=` 演算子の右側にある値をハッシュテーブルに追加します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-184">When the value of a variable is a hash table, the `+=` operator appends the value on the right side of the operator to the hash table.</span></span> <span data-ttu-id="88d1b-185">ただし、ハッシュテーブルに追加できる型はもう1つのハッシュテーブルだけなので、他のすべての割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-185">However, because the only type that you can add to a hash table is another hash table, all other assignments fail.</span></span>

<span data-ttu-id="88d1b-186">たとえば、次のコマンドは、ハッシュテーブルを変数に割り当て `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-186">For example, the following command assigns a hash table to the `$a` variable.</span></span>
<span data-ttu-id="88d1b-187">次に、演算子を使用して、既存のハッシュテーブル `+=` に別のハッシュテーブルを追加します。これにより、新しいキーと値のペアが既存のハッシュテーブルに実質的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-187">Then, it uses the `+=` operator to append another hash table to the existing hash table, effectively adding a new key/value pair to the existing hash table.</span></span>
<span data-ttu-id="88d1b-188">出力に示されているように、このコマンドは成功します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-188">This command succeeds, as shown in the output:</span></span>

```powershell
$a = @{a = 1; b = 2; c = 3}
$a += @{mode = "write"}
$a
```

```
Name                           Value
----                           -----
a                              1
b                              2
mode                           write
c                              3
```

<span data-ttu-id="88d1b-189">次のコマンドは、変数のハッシュテーブルに整数 "1" を追加しようとし `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-189">The following command attempts to append an integer "1" to the hash table in the `$a` variable.</span></span> <span data-ttu-id="88d1b-190">このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-190">This command fails:</span></span>

```powershell
$a = @{a = 1; b = 2; c = 3}
$a += 1
```

```
You can add another hash table only to a hash table.
At line:1 char:6
+ $a += <<<<  1
```

### <a name="the-assignment-by-subtraction-operator"></a><span data-ttu-id="88d1b-191">減算演算子による代入</span><span class="sxs-lookup"><span data-stu-id="88d1b-191">The assignment by subtraction operator</span></span>

<span data-ttu-id="88d1b-192">減算による代入演算子は、 `-=` 演算子の右辺に指定されている値によって変数の値をデクリメントします。</span><span class="sxs-lookup"><span data-stu-id="88d1b-192">The assignment by subtraction operator `-=` decrements the value of a variable by the value that is specified on the right side of the operator.</span></span> <span data-ttu-id="88d1b-193">この演算子は、文字列変数と共に使用することはできません。また、この演算子を使用してコレクションから要素を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="88d1b-193">This operator cannot be used with string variables, and it cannot be used to remove an element from a collection.</span></span>

<span data-ttu-id="88d1b-194">演算子は、 `-=` 2 つの操作を結合します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-194">The `-=` operator combines two operations.</span></span> <span data-ttu-id="88d1b-195">まず、を減算してから、を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-195">First, it subtracts, and then it assigns.</span></span> <span data-ttu-id="88d1b-196">したがって、次のステートメントは同等です。</span><span class="sxs-lookup"><span data-stu-id="88d1b-196">Therefore, the following statements are equivalent:</span></span>

```powershell
$a -= 2
$a = ($a - 2)
```

<span data-ttu-id="88d1b-197">次の例では、演算子を使用して変数の値を小さくする方法を示し `-=` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-197">The following example shows how to use of the `-=` operator to decrease the value of a variable:</span></span>

```powershell
$a = 8
$a -= 2
$a
```

```
6
```

<span data-ttu-id="88d1b-198">また、代入演算子を使用して、 `-=` 数値配列のメンバーの値を小さくすることもできます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-198">You can also use the `-=` assignment operator to decrease the value of a member of a numeric array.</span></span> <span data-ttu-id="88d1b-199">これを行うには、変更する配列要素のインデックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-199">To do this, specify the index of the array element that you want to change.</span></span> <span data-ttu-id="88d1b-200">次の例では、配列の3番目の要素の値 (要素 2) が1ずつ減少しています。</span><span class="sxs-lookup"><span data-stu-id="88d1b-200">In the following example, the value of the third element of an array (element 2) is decreased by 1:</span></span>

```powershell
$a = 1,2,3
$a[2] -= 1
$a
```

```
1
2
2
```

<span data-ttu-id="88d1b-201">演算子を使用して変数の値を削除することはできません `-=` 。</span><span class="sxs-lookup"><span data-stu-id="88d1b-201">You cannot use the `-=` operator to delete the values of a variable.</span></span> <span data-ttu-id="88d1b-202">変数に割り当てられているすべての値を削除するには、 [Clear Item](xref:Microsoft.PowerShell.Management.Clear-Item) または [clear variable](xref:Microsoft.PowerShell.Utility.Clear-Variable) コマンドレットを使用して、 `$null` 変数にまたはの値を割り当て `""` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-202">To delete all the values that are assigned to a variable, use the [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item) or [Clear-Variable](xref:Microsoft.PowerShell.Utility.Clear-Variable) cmdlets to assign a value of `$null` or `""` to the variable.</span></span>

```powershell
$a = $null
```

<span data-ttu-id="88d1b-203">特定の値を配列から削除するには、配列表記を使用して、特定の項目に値を割り当て `$null` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-203">To delete a particular value from an array, use array notation to assign a value of `$null` to the particular item.</span></span> <span data-ttu-id="88d1b-204">たとえば、次のステートメントは、配列から2番目の値 (インデックス位置 1) を削除します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-204">For example, the following statement deletes the second value (index position 1) from an array:</span></span>

```powershell
$a = 1,2,3
$a
```

```
1
2
3
```

```powershell
$a[1] = $null
$a
```

```
1
3
```

<span data-ttu-id="88d1b-205">変数を削除するには、 [変数の削除](xref:Microsoft.PowerShell.Utility.Remove-Variable) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-205">To delete a variable, use the [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) cmdlet.</span></span> <span data-ttu-id="88d1b-206">このメソッドは、変数が特定のデータ型に明示的にキャストされ、型指定されていない変数を必要とする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="88d1b-206">This method is useful when the variable is explicitly cast to a particular data type, and you want an untyped variable.</span></span> <span data-ttu-id="88d1b-207">次のコマンドを実行すると、変数が削除され `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-207">The following command deletes the `$a` variable:</span></span>

```powershell
Remove-Variable -Name a
```

### <a name="the-assignment-by-multiplication-operator"></a><span data-ttu-id="88d1b-208">乗算演算子による代入</span><span class="sxs-lookup"><span data-stu-id="88d1b-208">The assignment by multiplication operator</span></span>

<span data-ttu-id="88d1b-209">乗算演算子による代入で `*=` は、数値を乗算するか、変数の文字列値の指定された数のコピーを追加します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-209">The assignment by multiplication operator `*=` multiplies a numeric value or appends the specified number of copies of the string value of a variable.</span></span>

<span data-ttu-id="88d1b-210">変数に1つの数値が含まれている場合、その値には演算子の右側の値が乗算されます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-210">When a variable contains a single numeric value, that value is multiplied by the value on the right side of the operator.</span></span> <span data-ttu-id="88d1b-211">たとえば、次の例では、演算子を使用して変数の値を乗算する方法を示してい `*=` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-211">For example, the following example shows how to use the `*=` operator to multiply the value of a variable:</span></span>

```powershell
$a = 3
$a *= 4
$a
```

```
12
```

<span data-ttu-id="88d1b-212">この場合、演算子は `*=` 2 つの操作を結合します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-212">In this case, the `*=` operator combines two operations.</span></span> <span data-ttu-id="88d1b-213">まず、とを乗算し、次にを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-213">First, it multiplies, and then it assigns.</span></span> <span data-ttu-id="88d1b-214">したがって、次のステートメントは同等です。</span><span class="sxs-lookup"><span data-stu-id="88d1b-214">Therefore, the following statements are equivalent:</span></span>

```powershell
$a *= 2
$a = ($a * 2)
```

<span data-ttu-id="88d1b-215">変数に文字列値が含まれている場合、PowerShell は次のように、指定された数の文字列を値に追加します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-215">When a variable contains a string value, PowerShell appends the specified number of strings to the value, as follows:</span></span>

```powershell
$a = "file"
$a *= 4
$a
```

```
filefilefilefile
```

<span data-ttu-id="88d1b-216">配列の要素を乗算するには、インデックスを使用して、乗算する要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-216">To multiply an element of an array, use an index to identify the element that you want to multiply.</span></span> <span data-ttu-id="88d1b-217">たとえば、次のコマンドは、配列の最初の要素 (インデックス位置 0) を2で乗算します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-217">For example, the following command multiplies the first element in the array (index position 0) by 2:</span></span>

```powershell
$a[0] *= 2
```

### <a name="the-assignment-by-division-operator"></a><span data-ttu-id="88d1b-218">除算演算子による代入</span><span class="sxs-lookup"><span data-stu-id="88d1b-218">The assignment by division operator</span></span>

<span data-ttu-id="88d1b-219">除算による代入演算子は、 `/=` 演算子の右辺に指定されている値で数値を除算します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-219">The assignment by division operator `/=` divides a numeric value by the value that is specified on the right side of the operator.</span></span> <span data-ttu-id="88d1b-220">演算子は、文字列変数と共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="88d1b-220">The operator cannot be used with string variables.</span></span>

<span data-ttu-id="88d1b-221">演算子は、 `/=` 2 つの操作を結合します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-221">The `/=` operator combines two operations.</span></span> <span data-ttu-id="88d1b-222">まず、を分割し、次にを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-222">First, it divides, and then it assigns.</span></span> <span data-ttu-id="88d1b-223">したがって、次の2つのステートメントは同等です。</span><span class="sxs-lookup"><span data-stu-id="88d1b-223">Therefore, the following two statements are equivalent:</span></span>

```powershell
$a /= 2
$a = ($a / 2)
```

<span data-ttu-id="88d1b-224">たとえば、次のコマンドでは、演算子を使用して `/=` 変数の値を除算しています。</span><span class="sxs-lookup"><span data-stu-id="88d1b-224">For example, the following command uses the `/=` operator to divide the value of a variable:</span></span>

```powershell
$a = 8
$a /=2
$a
```

```
4
```

<span data-ttu-id="88d1b-225">配列の要素を分割するには、インデックスを使用して、変更する要素を識別します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-225">To divide an element of an array, use an index to identify the element that you want to change.</span></span> <span data-ttu-id="88d1b-226">たとえば、次のコマンドは、配列内の2番目の要素 (インデックス位置 1) を2で除算します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-226">For example, the following command divides the second element in the array (index position 1) by 2:</span></span>

```powershell
$a[1] /= 2
```

### <a name="the-assignment-by-modulus-operator"></a><span data-ttu-id="88d1b-227">剰余演算子による代入</span><span class="sxs-lookup"><span data-stu-id="88d1b-227">The assignment by modulus operator</span></span>

<span data-ttu-id="88d1b-228">剰余演算子による代入では、 `%=` 変数の値が演算子の右辺の値によって除算されます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-228">The assignment by modulus operator `%=` divides the value of a variable by the value on the right side of the operator.</span></span> <span data-ttu-id="88d1b-229">次に、 `%=` 演算子は剰余 (剰余と呼ばれる) を変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-229">Then, the `%=` operator assigns the remainder (known as the modulus) to the variable.</span></span> <span data-ttu-id="88d1b-230">この演算子は、変数に1つの数値が含まれている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-230">You can use this operator only when a variable contains a single numeric value.</span></span> <span data-ttu-id="88d1b-231">変数に文字列変数または配列が含まれている場合、この演算子は使用できません。</span><span class="sxs-lookup"><span data-stu-id="88d1b-231">You cannot use this operator when a variable contains a string variable or an array.</span></span>

<span data-ttu-id="88d1b-232">演算子は、 `%=` 2 つの操作を結合します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-232">The `%=` operator combines two operations.</span></span> <span data-ttu-id="88d1b-233">まず、剰余を分割して決定し、その剰余を変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-233">First, it divides and determines the remainder, and then it assigns the remainder to the variable.</span></span> <span data-ttu-id="88d1b-234">したがって、次のステートメントは同等です。</span><span class="sxs-lookup"><span data-stu-id="88d1b-234">Therefore, the following statements are equivalent:</span></span>

```powershell
$a %= 2
$a = ($a % 2)
```

<span data-ttu-id="88d1b-235">次の例は、演算子を使用して商の剰余を保存する方法を示してい `%=` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-235">The following example shows how to use the `%=` operator to save the modulus of a quotient:</span></span>

```powershell
$a = 7
$a %= 4
$a
```

```
3
```

## <a name="the-increment-and-decrement-operators"></a><span data-ttu-id="88d1b-236">インクリメント演算子とデクリメント演算子</span><span class="sxs-lookup"><span data-stu-id="88d1b-236">The increment and decrement operators</span></span>

<span data-ttu-id="88d1b-237">インクリメント演算子は、 `++` 変数の値を1つ増やします。</span><span class="sxs-lookup"><span data-stu-id="88d1b-237">The increment operator `++` increases the value of a variable by 1.</span></span> <span data-ttu-id="88d1b-238">単純なステートメントでインクリメント演算子を使用すると、値は返されません。</span><span class="sxs-lookup"><span data-stu-id="88d1b-238">When you use the increment operator in a simple statement, no value is returned.</span></span> <span data-ttu-id="88d1b-239">結果を表示するには、次のように変数の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-239">To view the result, display the value of the variable, as follows:</span></span>

```powershell
$a = 7
++$a
$a
```

```
8
```

<span data-ttu-id="88d1b-240">値を強制的に返すには、次のように、変数と演算子をかっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-240">To force a value to be returned, enclose the variable and the operator in parentheses, as follows:</span></span>

```powershell
$a = 7
(++$a)
```

```
8
```

<span data-ttu-id="88d1b-241">インクリメント演算子は、変数の前 (プレフィックス) または後 (後置) に配置できます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-241">The increment operator can be placed before (prefix) or after (postfix) a variable.</span></span> <span data-ttu-id="88d1b-242">プレフィックスバージョンの演算子は、次のように、ステートメントでその値が使用される前に変数をインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="88d1b-242">The prefix version of the operator increments a variable before its value is used in the statement, as follows:</span></span>

```powershell
$a = 7
$c = ++$a
$a
```

```
8
```

```powershell
$c
```

```
8
```

<span data-ttu-id="88d1b-243">後置バージョンの演算子は、その値がステートメントで使用された後に変数をインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="88d1b-243">The postfix version of the operator increments a variable after its value is used in the statement.</span></span> <span data-ttu-id="88d1b-244">次の例では、 `$c` `$a` 値が変更前にに割り当てられているため、変数と変数の値が異なり `$c` `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-244">In the following example, the `$c` and `$a` variables have different values because the value is assigned to `$c` before `$a` changes:</span></span>

```powershell
$a = 7
$c = $a++
$a
```

```
8
```

```powershell
$c
```

```
7
```

<span data-ttu-id="88d1b-245">デクリメント演算子は、 `--` 変数の値を1つ減らします。</span><span class="sxs-lookup"><span data-stu-id="88d1b-245">The decrement operator `--` decreases the value of a variable by 1.</span></span> <span data-ttu-id="88d1b-246">インクリメント演算子と同様に、単純なステートメントで演算子を使用した場合、値は返されません。</span><span class="sxs-lookup"><span data-stu-id="88d1b-246">As with the increment operator, no value is returned when you use the operator in a simple statement.</span></span> <span data-ttu-id="88d1b-247">次のように、かっこを使用して値を返します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-247">Use parentheses to return a value, as follows:</span></span>

```powershell
$a = 7
--$a
$a
```

```
6
```

```powershell
(--$a)
```

```
5
```

<span data-ttu-id="88d1b-248">前置バージョンの演算子は、次のように、ステートメントでその値が使用される前に変数をデクリメントします。</span><span class="sxs-lookup"><span data-stu-id="88d1b-248">The prefix version of the operator decrements a variable before its value is used in the statement, as follows:</span></span>

```powershell
$a = 7
$c = --$a
$a
```

```
6
```

```powershell
$c
```

```
6
```

<span data-ttu-id="88d1b-249">後置バージョンの演算子は、その値がステートメントで使用された後に変数をデクリメントします。</span><span class="sxs-lookup"><span data-stu-id="88d1b-249">The postfix version of the operator decrements a variable after its value is used in the statement.</span></span> <span data-ttu-id="88d1b-250">次の例では、 `$d` `$a` 値が変更前にに割り当てられているため、変数と変数の値が異なり `$d` `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-250">In the following example, the `$d` and `$a` variables have different values because the value is assigned to `$d` before `$a` changes:</span></span>

```powershell
$a = 7
$d = $a--
$a
```

```
6
```

```powershell
$d
```

```
7
```

## <a name="microsoft-net-framework-types"></a><span data-ttu-id="88d1b-251">Microsoft .NET Framework の型</span><span class="sxs-lookup"><span data-stu-id="88d1b-251">Microsoft .NET Framework types</span></span>

<span data-ttu-id="88d1b-252">既定では、変数に値が1つしかない場合、変数に割り当てられた値によって変数のデータ型が決まります。</span><span class="sxs-lookup"><span data-stu-id="88d1b-252">By default, when a variable has only one value, the value that is assigned to the variable determines the data type of the variable.</span></span> <span data-ttu-id="88d1b-253">たとえば、次のコマンドでは、"Integer" (system.string) 型の変数が作成されます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-253">For example, the following command creates a variable that has the "Integer" (System.Int32) type:</span></span>

```powershell
$a = 6
```

<span data-ttu-id="88d1b-254">変数の .NET Framework 型を確認するには、次のように **GetType** メソッドとその **FullName** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-254">To find the .NET Framework type of a variable, use the **GetType** method and its **FullName** property, as follows.</span></span> <span data-ttu-id="88d1b-255">メソッド呼び出しに引数がない場合でも、必ず **GetType** メソッド名の後にかっこを含めてください。</span><span class="sxs-lookup"><span data-stu-id="88d1b-255">Be sure to include the parentheses after the **GetType** method name, even though the method call has no arguments:</span></span>

```powershell
$a = 6
$a.GetType().FullName
```

```
System.Int32
```

<span data-ttu-id="88d1b-256">文字列を含む変数を作成するには、変数に文字列値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-256">To create a variable that contains a string, assign a string value to the variable.</span></span> <span data-ttu-id="88d1b-257">値が文字列であることを示すには、次のように引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-257">To indicate that the value is a string, enclose it in quotation marks, as follows:</span></span>

```powershell
$a = "6"
$a.GetType().FullName
```

```
System.String
```

<span data-ttu-id="88d1b-258">変数に割り当てられた最初の値が文字列の場合、PowerShell はすべての操作を文字列操作として扱い、新しい値を文字列にキャストします。</span><span class="sxs-lookup"><span data-stu-id="88d1b-258">If the first value that is assigned to the variable is a string, PowerShell treats all operations as string operations and casts new values to strings.</span></span>
<span data-ttu-id="88d1b-259">これは、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="88d1b-259">This occurs in the following example:</span></span>

```powershell
$a = "file"
$a += 3
$a
```

```
file3
```

<span data-ttu-id="88d1b-260">最初の値が整数の場合、PowerShell はすべての操作を整数演算として扱い、新しい値を整数にキャストします。</span><span class="sxs-lookup"><span data-stu-id="88d1b-260">If the first value is an integer, PowerShell treats all operations as integer operations and casts new values to integers.</span></span> <span data-ttu-id="88d1b-261">これは、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="88d1b-261">This occurs in the following example:</span></span>

```powershell
$a = 6
$a += "3"
$a
```

```
9
```

<span data-ttu-id="88d1b-262">変数名または最初の代入値の前に角かっこで囲んで型名を指定することにより、新しいスカラー変数を任意の .NET Framework 型としてキャストできます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-262">You can cast a new scalar variable as any .NET Framework type by placing the type name in brackets that precede either the variable name or the first assignment value.</span></span> <span data-ttu-id="88d1b-263">変数をキャストするときに、変数に格納できるデータの種類を決定できます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-263">When you cast a variable, you can determine the types of data that can be stored in the variable.</span></span> <span data-ttu-id="88d1b-264">また、変数を操作するときの動作を決定することもできます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-264">And, you can determine how the variable behaves when you manipulate it.</span></span>

<span data-ttu-id="88d1b-265">たとえば、次のコマンドは、変数を文字列型としてキャストします。</span><span class="sxs-lookup"><span data-stu-id="88d1b-265">For example, the following command casts the variable as a string type:</span></span>

```powershell
[string]$a = 27
$a += 3
$a
```

```
273
```

<span data-ttu-id="88d1b-266">次の例では、変数をキャストするのではなく、最初の値をキャストしています。</span><span class="sxs-lookup"><span data-stu-id="88d1b-266">The following example casts the first value, instead of casting the variable:</span></span>

```powershell
$a = [string]27
```

<span data-ttu-id="88d1b-267">変数を特定の型にキャストする場合、一般的な規則として、値ではなく変数をキャストします。</span><span class="sxs-lookup"><span data-stu-id="88d1b-267">When you cast a variable to a specific type, the common convention is to cast the variable, not the value.</span></span> <span data-ttu-id="88d1b-268">ただし、既存の変数の値を新しいデータ型に変換できない場合は、その変数のデータ型を再キャストすることはできません。</span><span class="sxs-lookup"><span data-stu-id="88d1b-268">However, you cannot recast the data type of an existing variable if its value cannot be converted to the new data type.</span></span> <span data-ttu-id="88d1b-269">データ型を変更するには、次のように値を置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="88d1b-269">To change the data type, you must replace its value, as follows:</span></span>

```powershell
$a = "string"
[int]$a
```

```
Cannot convert value "string" to type "System.Int32". Error: "Input string was
not in a correct format." At line:1 char:8 + [int]$a <<<<
```

```powershell
[int]$a = 3
```

<span data-ttu-id="88d1b-270">さらに、変数名の前にデータ型を指定した場合は、別のデータ型を指定して明示的に型をオーバーライドしない限り、その変数の型はロックされます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-270">In addition, when you precede a variable name with a data type, the type of that variable is locked unless you explicitly override the type by specifying another data type.</span></span> <span data-ttu-id="88d1b-271">既存の型と互換性のない値を割り当てようとし、明示的に型をオーバーライドしていない場合は、次の例に示すように、PowerShell によってエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-271">If you try to assign a value that is incompatible with the existing type, and you do not explicitly override the type, PowerShell displays an error, as shown in the following example:</span></span>

```powershell
$a = 3
$a = "string"
[int]$a = 3
$a = "string"
```

```
Cannot convert value "string" to type "System.Int32". Error: "Input
string was not in a correct format."
At line:1 char:3
+ $a <<<<  = "string"
```

```powershell
[string]$a = "string"
```

<span data-ttu-id="88d1b-272">PowerShell では、配列内の複数の項目を含む変数のデータ型は、1つの項目を含む変数のデータ型とは異なる方法で処理されます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-272">In PowerShell, the data types of variables that contain multiple items in an array are handled differently from the data types of variables that contain a single item.</span></span> <span data-ttu-id="88d1b-273">データ型が明示的に配列変数に代入されていない限り、データ型は常にに `System.Object []` なります。</span><span class="sxs-lookup"><span data-stu-id="88d1b-273">Unless a data type is specifically assigned to an array variable, the data type is always `System.Object []`.</span></span> <span data-ttu-id="88d1b-274">このデータ型は配列に固有です。</span><span class="sxs-lookup"><span data-stu-id="88d1b-274">This data type is specific to arrays.</span></span>

<span data-ttu-id="88d1b-275">場合によっては、別の型を指定することで既定の型をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-275">Sometimes, you can override the default type by specifying another type.</span></span> <span data-ttu-id="88d1b-276">たとえば、次のコマンドは、変数を配列型としてキャストし `string []` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-276">For example, the following command casts the variable as a `string []` array type:</span></span>

```powershell
[string []] $a = "one", "two", "three"
```

<span data-ttu-id="88d1b-277">PowerShell 変数は、任意の .NET Framework データ型にすることができます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-277">PowerShell variables can be any .NET Framework data type.</span></span> <span data-ttu-id="88d1b-278">また、現在のプロセスで使用できる任意の完全修飾 .NET Framework データ型を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-278">In addition, you can assign any fully qualified .NET Framework data type that is available in the current process.</span></span> <span data-ttu-id="88d1b-279">たとえば、次のコマンドはデータ型を指定し `System.DateTime` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-279">For example, the following command specifies a `System.DateTime` data type:</span></span>

```powershell
[System.DateTime]$a = "5/31/2005"
```

<span data-ttu-id="88d1b-280">変数には、データ型に準拠した値が割り当てられ `System.DateTime` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-280">The variable will be assigned a value that conforms to the `System.DateTime` data type.</span></span> <span data-ttu-id="88d1b-281">変数の値は `$a` 次のようになります。</span><span class="sxs-lookup"><span data-stu-id="88d1b-281">The value of the `$a` variable would be the following:</span></span>

```
Tuesday, May 31, 2005 12:00:00 AM
```

## <a name="assigning-multiple-variables"></a><span data-ttu-id="88d1b-282">複数の変数の割り当て</span><span class="sxs-lookup"><span data-stu-id="88d1b-282">Assigning multiple variables</span></span>

<span data-ttu-id="88d1b-283">PowerShell では、1つのコマンドを使用して、複数の変数に値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-283">In PowerShell, you can assign values to multiple variables by using a single command.</span></span> <span data-ttu-id="88d1b-284">代入値の最初の要素が最初の変数に割り当てられ、2番目の要素が2番目の変数に割り当てられ、3番目の要素が3番目の変数に代入されます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-284">The first element of the assignment value is assigned to the first variable, the second element is assigned to the second variable, the third element to the third variable, and so on.</span></span> <span data-ttu-id="88d1b-285">たとえば、次のコマンドでは、変数に値1、値2を変数に、値3を変数に代入してい `$a` `$b` `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-285">For example, the following command assigns the value 1 to the `$a` variable, the value 2 to the `$b` variable, and the value 3 to the `$c` variable:</span></span>

```powershell
$a, $b, $c = 1, 2, 3
```

<span data-ttu-id="88d1b-286">代入値に変数よりも多くの要素が含まれている場合は、残りのすべての値が最後の変数に代入されます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-286">If the assignment value contains more elements than variables, all the remaining values are assigned to the last variable.</span></span> <span data-ttu-id="88d1b-287">たとえば、次のコマンドには、3つの変数と5つの値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="88d1b-287">For example, the following command contains three variables and five values:</span></span>

```powershell
$a, $b, $c = 1, 2, 3, 4, 5
```

<span data-ttu-id="88d1b-288">したがって、PowerShell は変数に値1を代入 `$a` し、値2を `$b` 変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-288">Therefore, PowerShell assigns the value 1 to the `$a` variable and the value 2 to the `$b` variable.</span></span> <span data-ttu-id="88d1b-289">変数に値3、4、および5が割り当てられ `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-289">It assigns the values 3, 4, and 5 to the `$c` variable.</span></span>
<span data-ttu-id="88d1b-290">変数の値を `$c` 他の3つの変数に割り当てるには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="88d1b-290">To assign the values in the `$c` variable to three other variables, use the following format:</span></span>

```powershell
$d, $e, $f = $c
```

<span data-ttu-id="88d1b-291">このコマンドは、変数に値3を代入し、 `$d` 値4を変数に、 `$e` 値5を変数に代入し `$f` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-291">This command assigns the value 3 to the `$d` variable, the value 4 to the `$e` variable, and the value 5 to the `$f` variable.</span></span>

<span data-ttu-id="88d1b-292">代入値に含まれる要素の数が変数よりも少ない場合、末尾の残りのすべての変数には値が割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="88d1b-292">If the assignment value contains less elements than variables, all the remaining variables at the end are not assigned any values.</span></span> <span data-ttu-id="88d1b-293">たとえば、次のコマンドには、3つの変数と2つの値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="88d1b-293">For example, the following command contains three variables and two values:</span></span>

```powershell
$a, $b, $c = 1, 2
```

<span data-ttu-id="88d1b-294">したがって、PowerShell は変数に値1を代入 `$a` し、値2を `$b` 変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-294">Therefore, PowerShell assigns the value 1 to the `$a` variable and the value 2 to the `$b` variable.</span></span> <span data-ttu-id="88d1b-295">変数に値は割り当てられません `$c` 。</span><span class="sxs-lookup"><span data-stu-id="88d1b-295">It will not assign any value to the `$c` variable.</span></span>

<span data-ttu-id="88d1b-296">変数を連結することによって、複数の変数に1つの値を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-296">You can also assign a single value to multiple variables by chaining the variables.</span></span> <span data-ttu-id="88d1b-297">たとえば、次のコマンドでは、4つの変数すべてに "3" という値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-297">For example, the following command assigns a value of "three" to all four variables:</span></span>

```powershell
$a = $b = $c = $d = "three"
```

## <a name="variable-related-cmdlets"></a><span data-ttu-id="88d1b-298">変数関連のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="88d1b-298">Variable-related cmdlets</span></span>

<span data-ttu-id="88d1b-299">代入演算を使用して変数の値を設定するだけでなく、変数の [設定](xref:Microsoft.PowerShell.Utility.Set-Variable) コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-299">In addition to using an assignment operation to set a variable value, you can also use the [Set-Variable](xref:Microsoft.PowerShell.Utility.Set-Variable) cmdlet.</span></span> <span data-ttu-id="88d1b-300">たとえば、次のコマンドでは、を使用して、 `Set-Variable` 変数に1、2、3の配列を割り当て `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="88d1b-300">For example, the following command uses `Set-Variable` to assign an array of 1, 2, 3 to the `$a` variable.</span></span>

```powershell
Set-Variable -Name a -Value 1, 2, 3
```

## <a name="see-also"></a><span data-ttu-id="88d1b-301">関連項目</span><span class="sxs-lookup"><span data-stu-id="88d1b-301">See also</span></span>

[<span data-ttu-id="88d1b-302">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="88d1b-302">about_Arrays</span></span>](about_Arrays.md)

[<span data-ttu-id="88d1b-303">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="88d1b-303">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="88d1b-304">about_Variables</span><span class="sxs-lookup"><span data-stu-id="88d1b-304">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="88d1b-305">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="88d1b-305">Clear-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Clear-Variable)

[<span data-ttu-id="88d1b-306">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="88d1b-306">Remove-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Remove-Variable)

[<span data-ttu-id="88d1b-307">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="88d1b-307">Set-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Set-Variable)
