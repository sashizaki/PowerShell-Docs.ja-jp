---
description: 現在の範囲 (関数、スクリプト、スクリプト ブロック) を終了します。
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_return?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Return
ms.openlocfilehash: 032f3c694096e11e2800be941eb76b1f442b5088
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602646"
---
# <a name="about-return"></a><span data-ttu-id="13e24-103">戻り値</span><span class="sxs-lookup"><span data-stu-id="13e24-103">About Return</span></span>

## <a name="short-description"></a><span data-ttu-id="13e24-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="13e24-104">Short description</span></span>

<span data-ttu-id="13e24-105">現在の範囲 (関数、スクリプト、スクリプト ブロック) を終了します。</span><span class="sxs-lookup"><span data-stu-id="13e24-105">Exits the current scope, which can be a function, script, or script block.</span></span>

## <a name="long-description"></a><span data-ttu-id="13e24-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="13e24-106">Long description</span></span>

<span data-ttu-id="13e24-107">キーワードは、 `return` 関数、スクリプト、またはスクリプトブロックを終了します。</span><span class="sxs-lookup"><span data-stu-id="13e24-107">The `return` keyword exits a function, script, or script block.</span></span> <span data-ttu-id="13e24-108">特定のポイントでスコープを終了したり、値を返したり、スコープの末尾に達したことを示すために使用できます。</span><span class="sxs-lookup"><span data-stu-id="13e24-108">It can be used to exit a scope at a specific point, to return a value, or to indicate that the end of the scope has been reached.</span></span>

<span data-ttu-id="13e24-109">C や C などの言語に慣れているユーザーは、キーワードを使用して、 \# `return` スコープを明示的にするロジックを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="13e24-109">Users who are familiar with languages like C or C\# might want to use the `return` keyword to make the logic of leaving a scope explicit.</span></span>

<span data-ttu-id="13e24-110">PowerShell では、Return キーワードを含むステートメントを使用せずに、各ステートメントの結果が出力として返されます。</span><span class="sxs-lookup"><span data-stu-id="13e24-110">In PowerShell, the results of each statement are returned as output, even without a statement that contains the Return keyword.</span></span> <span data-ttu-id="13e24-111">C や C などの言語では、 \# キーワードによって指定された値だけが返され `return` ます。</span><span class="sxs-lookup"><span data-stu-id="13e24-111">Languages like C or C\# return only the value or values that are specified by the `return` keyword.</span></span>

> [!NOTE]
> <span data-ttu-id="13e24-112">PowerShell 5.0 以降では、正式な構文を使用して、クラスを定義するための言語が追加されました。</span><span class="sxs-lookup"><span data-stu-id="13e24-112">Beginning in PowerShell 5.0, PowerShell added language for defining classes, by using formal syntax.</span></span>  <span data-ttu-id="13e24-113">PowerShell クラスのコンテキストでは、ステートメントを使用して指定したものを除き、メソッドからの出力は何もありません `return` 。</span><span class="sxs-lookup"><span data-stu-id="13e24-113">In the context of a PowerShell class, nothing is output from a method except what you specify using a `return` statement.</span></span> <span data-ttu-id="13e24-114">PowerShell クラスの詳細については、 [about_Classes](about_Classes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13e24-114">You can read more about PowerShell classes in [about_Classes](about_Classes.md).</span></span>

### <a name="syntax"></a><span data-ttu-id="13e24-115">構文</span><span class="sxs-lookup"><span data-stu-id="13e24-115">Syntax</span></span>

<span data-ttu-id="13e24-116">キーワードの構文 `return` は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="13e24-116">The syntax for the `return` keyword is as follows:</span></span>

```
return [<expression>]
```

<span data-ttu-id="13e24-117">キーワードは、 `return` 単独で使用することも、次のように値または式の後に指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="13e24-117">The `return` keyword can appear alone, or it can be followed by a value or expression, as follows:</span></span>

```powershell
return
return $a
return (2 + $a)
```

### <a name="examples"></a><span data-ttu-id="13e24-118">例</span><span class="sxs-lookup"><span data-stu-id="13e24-118">Examples</span></span>

<span data-ttu-id="13e24-119">次の例では、キーワードを使用して、 `return` 条件が満たされた場合に特定のポイントで関数を終了します。</span><span class="sxs-lookup"><span data-stu-id="13e24-119">The following example uses the `return` keyword to exit a function at a specific point if a conditional is met.</span></span> <span data-ttu-id="13e24-120">ステートメントを実行する前に return ステートメントが終了するため、奇数は乗算されません。</span><span class="sxs-lookup"><span data-stu-id="13e24-120">Odd numbers are not multiplied because the return statement exits before that statement can execute.</span></span>

```powershell
function MultiplyEven
{
    param($number)

    if ($number % 2) { return "$number is not even" }
    $number * 2
}

1..10 | ForEach-Object {MultiplyEven -Number $_}
```

```output
1 is not even
4
3 is not even
8
5 is not even
12
7 is not even
16
9 is not even
20
```

<span data-ttu-id="13e24-121">PowerShell では、キーワードが使用されていない場合でも値を返すことができ `return` ます。</span><span class="sxs-lookup"><span data-stu-id="13e24-121">In PowerShell, values can be returned even if the `return` keyword is not used.</span></span>
<span data-ttu-id="13e24-122">各ステートメントの結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="13e24-122">The results of each statement are returned.</span></span> <span data-ttu-id="13e24-123">たとえば、次のステートメントは変数の値を返し `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="13e24-123">For example, the following statements return the value of the `$a` variable:</span></span>

```powershell
$a
return
```

<span data-ttu-id="13e24-124">次のステートメントでも、の値が返され `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="13e24-124">The following statement also returns the value of `$a`:</span></span>

```powershell
return $a
```

<span data-ttu-id="13e24-125">次の例には、関数が計算を実行していることをユーザーに知らせるためのステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="13e24-125">The following example includes a statement intended to let the user know that the function is performing a calculation:</span></span>

```powershell
function calculation {
    param ($value)

    "Please wait. Working on calculation..."
    $value += 73
    return $value
}

$a = calculation 14
```

<span data-ttu-id="13e24-126">"しばらくお待ちください。</span><span class="sxs-lookup"><span data-stu-id="13e24-126">The "Please wait.</span></span> <span data-ttu-id="13e24-127">計算時に作業しています... "文字列は表示されません。</span><span class="sxs-lookup"><span data-stu-id="13e24-127">Working on calculation..." string is not displayed.</span></span> <span data-ttu-id="13e24-128">代わりに、次の例のように、変数に割り当てられ `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="13e24-128">Instead, it is assigned to the `$a` variable, as in the following example:</span></span>

```
PS> $a
Please wait. Working on calculation...
87
```

<span data-ttu-id="13e24-129">情報文字列と計算結果の両方が関数によって返され、変数に代入され `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="13e24-129">Both the informational string and the result of the calculation are returned by the function and assigned to the `$a` variable.</span></span>

<span data-ttu-id="13e24-130">PowerShell 5.0 以降で、関数内にメッセージを表示する場合は、ストリームを使用でき `Information` ます。</span><span class="sxs-lookup"><span data-stu-id="13e24-130">If you would like to display a message within your function, beginning in PowerShell 5.0, you can use the `Information` stream.</span></span> <span data-ttu-id="13e24-131">次のコードでは、コマンドレットと Continue を使用して、上記の例を修正して `Write-Information` `InformationAction` います。 </span><span class="sxs-lookup"><span data-stu-id="13e24-131">The code below corrects the above example using the `Write-Information` cmdlet with a `InformationAction` of **Continue**.</span></span>

```powershell
function calculation {
    param ($value)

    Write-Information "Please wait. Working on calculation..." -InformationAction Continue
    $value += 73
    return $value
}

$a = calculation 14
```

```output
Please wait. Working on calculation...
C:\PS> $a
87
```

### <a name="return-values-and-the-pipeline"></a><span data-ttu-id="13e24-132">戻り値とパイプライン</span><span class="sxs-lookup"><span data-stu-id="13e24-132">Return values and the Pipeline</span></span>

<span data-ttu-id="13e24-133">スクリプトブロックまたは関数からコレクションを返すと、PowerShell によって自動的にメンバーのロールが解除され、パイプラインを介して一度に1つずつ渡されます。</span><span class="sxs-lookup"><span data-stu-id="13e24-133">When you return a collection from your script block or function, PowerShell automatically unrolls the members and passes them one at a time through the pipeline.</span></span> <span data-ttu-id="13e24-134">これは、PowerShell の1回限りの処理が原因です。</span><span class="sxs-lookup"><span data-stu-id="13e24-134">This is due to PowerShell's one-at-a-time processing.</span></span> <span data-ttu-id="13e24-135">詳細については、「 [about_pipelines](about_pipelines.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13e24-135">For more information, see [about_pipelines](about_pipelines.md).</span></span>

<span data-ttu-id="13e24-136">この概念は、数値の配列を返す次のサンプル関数によって示されています。</span><span class="sxs-lookup"><span data-stu-id="13e24-136">This concept is illustrated by the following sample function that returns an array of numbers.</span></span> <span data-ttu-id="13e24-137">関数からの出力は、 `Measure-Object` パイプライン内のオブジェクトの数をカウントするコマンドレットにパイプ処理されます。</span><span class="sxs-lookup"><span data-stu-id="13e24-137">The output from the function is piped to the `Measure-Object` cmdlet which counts the number of objects in the pipeline.</span></span>

```powershell
function Test-Return
{
    $array = 1,2,3
    return $array
}
Test-Return | Measure-Object
```

```Output
Count    : 3
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

<span data-ttu-id="13e24-138">スクリプトブロックまたは関数が、コレクションを1つのオブジェクトとしてパイプラインに返すように強制するには、次の2つの方法のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="13e24-138">To force a script block or function to return collection as a single object to the pipeline, use one of the following two methods:</span></span>

- <span data-ttu-id="13e24-139">単項配列式</span><span class="sxs-lookup"><span data-stu-id="13e24-139">Unary array expression</span></span>

  <span data-ttu-id="13e24-140">単項式を使用すると、次の例に示すように、戻り値を1つのオブジェクトとして渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="13e24-140">Utilizing a unary expression you can send your return value down the pipeline as a single object as illustrated by the following example.</span></span>

  ```powershell
  function Test-Return
  {
      $array = 1,2,3
      return (, $array)
  }
  Test-Return | Measure-Object
  ```

  ```Output
  Count    : 1
  Average  :
  Sum      :
  Maximum  :
  Minimum  :
  Property :
  ```

- <span data-ttu-id="13e24-141">`Write-Output`**Noenumerate** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="13e24-141">`Write-Output` with **NoEnumerate** parameter.</span></span>

  <span data-ttu-id="13e24-142">`Write-Output` **Noenumerate** パラメーターを指定してコマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="13e24-142">You can also use the `Write-Output` cmdlet with the **NoEnumerate** parameter.</span></span> <span data-ttu-id="13e24-143">次の例では、コマンドレットを使用し `Measure-Object` て、サンプル関数からパイプラインに送信されたオブジェクトをキーワードでカウントし `return` ます。</span><span class="sxs-lookup"><span data-stu-id="13e24-143">The example below uses the `Measure-Object` cmdlet to count the objects sent to the pipeline from the sample function by the `return` keyword.</span></span>

  ```powershell
  function Test-Return
  {
      $array = 1, 2, 3
      return Write-Output -NoEnumerate $array
  }

  Test-Return | Measure-Object
  ```

  ```Output
  Count    : 1
  Average  :
  Sum      :
  Maximum  :
  Minimum  :
  Property :
  ```

## <a name="see-also"></a><span data-ttu-id="13e24-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="13e24-144">See also</span></span>

[<span data-ttu-id="13e24-145">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="13e24-145">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="13e24-146">about_Functions</span><span class="sxs-lookup"><span data-stu-id="13e24-146">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="13e24-147">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="13e24-147">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="13e24-148">about_Classes</span><span class="sxs-lookup"><span data-stu-id="13e24-148">about_Classes</span></span>](about_Classes.md)

[<span data-ttu-id="13e24-149">Write-Information</span><span class="sxs-lookup"><span data-stu-id="13e24-149">Write-Information</span></span>](xref:Microsoft.PowerShell.Utility.Write-Information)

[<span data-ttu-id="13e24-150">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="13e24-150">about_Script_Blocks</span></span>](about_Script_Blocks.md)

