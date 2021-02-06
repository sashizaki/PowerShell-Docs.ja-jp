---
description: 条件付きテストに基づいてステートメントを実行するために使用できる言語コマンドについて説明します。
Locale: en-US
ms.date: 03/04/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_for?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_For
ms.openlocfilehash: 3f86505d60837e8e5fa4938092a48eeb10833560
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600396"
---
# <a name="about-for"></a><span data-ttu-id="6d23c-103">について</span><span class="sxs-lookup"><span data-stu-id="6d23c-103">About For</span></span>

## <a name="short-description"></a><span data-ttu-id="6d23c-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="6d23c-104">Short description</span></span>
<span data-ttu-id="6d23c-105">条件付きテストに基づいてステートメントを実行するために使用できる言語コマンドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6d23c-105">Describes a language command you can use to run statements based on a conditional test.</span></span>

## <a name="long-description"></a><span data-ttu-id="6d23c-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="6d23c-106">Long description</span></span>

<span data-ttu-id="6d23c-107">`For`ステートメント (ループとも呼ばれ `For` ます) は、指定した条件がに評価されるときにコマンドブロックでコマンドを実行するループを作成するために使用できる言語構成要素です `$true` 。</span><span class="sxs-lookup"><span data-stu-id="6d23c-107">The `For` statement (also known as a `For` loop) is a language construct you can use to create a loop that runs commands in a command block while a specified condition evaluates to `$true`.</span></span>

<span data-ttu-id="6d23c-108">ループの一般的な用途 `For` は、値の配列を反復処理し、これらの値のサブセットに対して操作を行うことです。</span><span class="sxs-lookup"><span data-stu-id="6d23c-108">A typical use of the `For` loop is to iterate an array of values and to operate on a subset of these values.</span></span> <span data-ttu-id="6d23c-109">ほとんどの場合、配列内のすべての値を反復処理するには、ステートメントを使用することを検討してください `Foreach` 。</span><span class="sxs-lookup"><span data-stu-id="6d23c-109">In most cases, if you want to iterate all the values in an array, consider using a `Foreach` statement.</span></span>

### <a name="syntax"></a><span data-ttu-id="6d23c-110">構文</span><span class="sxs-lookup"><span data-stu-id="6d23c-110">Syntax</span></span>

<span data-ttu-id="6d23c-111">ステートメントの構文を次に示し `For` ます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-111">The following shows the `For` statement syntax.</span></span>

```
for (<Init>; <Condition>; <Repeat>)
{
    <Statement list>
}
```

<span data-ttu-id="6d23c-112">**Init** プレースホルダーは、ループが開始される前に実行される1つ以上のコマンドを表します。</span><span class="sxs-lookup"><span data-stu-id="6d23c-112">The **Init** placeholder represents one or more commands that are run before the loop begins.</span></span> <span data-ttu-id="6d23c-113">通常は、ステートメントの **Init** 部分を使用して、開始値を持つ変数を作成および初期化します。</span><span class="sxs-lookup"><span data-stu-id="6d23c-113">You typically use the **Init** portion of the statement to create and initialize a variable with a starting value.</span></span>

<span data-ttu-id="6d23c-114">この変数は、ステートメントの次の部分でテストされる条件の基礎となり `For` ます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-114">This variable will then be the basis for the condition to be tested in the next portion of the `For` statement.</span></span>

<span data-ttu-id="6d23c-115">**条件** のプレースホルダーは、 `For` `$true` またはの `$false` **ブール** 値に解決されるステートメントの部分を表します。</span><span class="sxs-lookup"><span data-stu-id="6d23c-115">The **Condition** placeholder represents the portion of the `For` statement that resolves to a `$true` or `$false` **Boolean** value.</span></span> <span data-ttu-id="6d23c-116">PowerShell は、ループが実行されるたびに条件を評価し `For` ます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-116">PowerShell evaluates the condition each time the `For` loop runs.</span></span> <span data-ttu-id="6d23c-117">ステートメントがの場合は `$true` 、コマンドブロック内のコマンドが実行され、ステートメントが再び評価されます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-117">If the statement is `$true`, the commands in the command block run, and the statement is evaluated again.</span></span> <span data-ttu-id="6d23c-118">条件がまだの場合は、 `$true` **ステートメントリスト** 内のコマンドが再度実行されます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-118">If the condition is still `$true`, the commands in the **Statement list** run again.</span></span> <span data-ttu-id="6d23c-119">このループは、条件がになるまで繰り返され `$false` ます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-119">The loop is repeated until the condition becomes `$false`.</span></span>

<span data-ttu-id="6d23c-120">**繰り返し** のプレースホルダーは、ループが繰り返されるたびに実行される、コンマで区切られた1つ以上のコマンドを表します。</span><span class="sxs-lookup"><span data-stu-id="6d23c-120">The **Repeat** placeholder represents one or more commands, separated by commas, that are executed each time the loop repeats.</span></span> <span data-ttu-id="6d23c-121">通常、これは、ステートメントの **条件** 部分の内部でテストされる変数を変更するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-121">Typically, this is used to modify a variable that is tested inside the **Condition** part of the statement.</span></span>

<span data-ttu-id="6d23c-122">**ステートメントの一覧** のプレースホルダーは、ループが入力または繰り返されるたびに実行される1つ以上のコマンドのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="6d23c-122">The **Statement list** placeholder represents a set of one or more commands that are run each time the loop is entered or repeated.</span></span> <span data-ttu-id="6d23c-123">**ステートメントリスト** の内容は、中かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="6d23c-123">The contents of the **Statement list** are surrounded by braces.</span></span>

### <a name="support-for-multiple-operations"></a><span data-ttu-id="6d23c-124">複数の操作のサポート</span><span class="sxs-lookup"><span data-stu-id="6d23c-124">Support for multiple operations</span></span>

<span data-ttu-id="6d23c-125">次の構文は、 **Init** ステートメントで複数の代入演算に対してサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6d23c-125">The following syntaxes are supported for multiple assignment operations in the **Init** statement:</span></span>

```powershell
# Comma separated assignment expressions enclosed in parenthesis.
for (($i = 0), ($j = 0); $i -lt 10; $i++)
{
    "`$i:$i"
    "`$j:$j"
}

# Sub-expression using the semicolon to separate statements.
for ($($i = 0;$j = 0); $i -lt 10; $i++)
{
    "`$i:$i"
    "`$j:$j"
}
```

<span data-ttu-id="6d23c-126">次の構文は、 **Repeat** ステートメントで複数の代入演算に対してサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6d23c-126">The following syntaxes are supported for multiple assignment operations in the **Repeat** statement:</span></span>

```powershell
# Comma separated assignment expressions.
for (($i = 0), ($j = 0); $i -lt 10; $i++)
{
    "`$i:$i"
    "`$j:$j"
}

# Comma separated assignment expressions enclosed in parenthesis.
for (($i = 0), ($j = 0); $i -lt 10; ($i++), ($j++))
{
    "`$i:$i"
    "`$j:$j"
}

# Sub-expression using the semicolon to separate statements.
for ($($i = 0;$j = 0); $i -lt 10; $($i++;$j++))
{
    "`$i:$i"
    "`$j:$j"
}
```

> [!NOTE]
> <span data-ttu-id="6d23c-127">プリインクリメントまたはポストインクリメント以外の操作は、すべての構文で動作しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6d23c-127">Operations other than pre or post increment may not work with all syntaxes.</span></span>

<span data-ttu-id="6d23c-128">複数の **条件** については、次の例に示すように論理演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d23c-128">For multiple **Conditions** use logical operators as demonstrated by the following example.</span></span>

```powershell
for (($i = 0), ($j = 0); $i -lt 10 -and $j -lt 10; $i++,$j++)
{
    "`$i:$i"
    "`$j:$j"
}
```

<span data-ttu-id="6d23c-129">詳細については、「 [about_Logical_Operators](about_Logical_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d23c-129">For more information, see [about_Logical_Operators](about_Logical_Operators.md).</span></span>

### <a name="examples"></a><span data-ttu-id="6d23c-130">例</span><span class="sxs-lookup"><span data-stu-id="6d23c-130">Examples</span></span>

<span data-ttu-id="6d23c-131">ステートメントには、少なくとも、ステートメントの `For` **Init**、 **Condition**、および **Repeat** 部分を囲むかっこと、ステートメントの **ステートメントリスト** 部分に中かっこで囲まれたコマンドが必要です。</span><span class="sxs-lookup"><span data-stu-id="6d23c-131">At a minimum, a `For` statement requires the parenthesis surrounding the **Init**, **Condition**, and **Repeat** part of the statement and a command surrounded by braces in the **Statement list** part of the statement.</span></span>

<span data-ttu-id="6d23c-132">今後の例では、ステートメントの外部にコードを意図的に表示することに注意して `For` ください。</span><span class="sxs-lookup"><span data-stu-id="6d23c-132">Note that the upcoming examples intentionally show code outside the `For` statement.</span></span> <span data-ttu-id="6d23c-133">後の例では、コードをステートメントに統合してい `For` ます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-133">In later examples, code is integrated into the `For` statement.</span></span>

<span data-ttu-id="6d23c-134">たとえば、次のステートメントでは、 `For` `$i` CTRL + C キーを押してコマンドを手動で中断するまで、変数の値が継続的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-134">For example, the following `For` statement continually displays the value of the `$i` variable until you manually break out of the command by pressing CTRL+C.</span></span>

```powershell
$i = 1
for (;;)
{
    Write-Host $i
}
```

<span data-ttu-id="6d23c-135">次の例に示すように、ループが実行されるたびにの値が1ずつ増加するように、ステートメントの一覧にコマンドを追加でき `$i` ます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-135">You can add additional commands to the statement list so that the value of `$i` is incremented by 1 each time the loop is run, as the following example shows.</span></span>

```powershell
for (;;)
{
    $i++; Write-Host $i
}
```

<span data-ttu-id="6d23c-136">CTRL + C キーを押してコマンドを中断するまで、このステートメントでは、ループが実行されるたびに1ずつインクリメントされるため、変数の値が継続的に表示され `$i` ます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-136">Until you break out of the command by pressing CTRL+C, this statement will continually display the value of the `$i` variable as it is incremented by 1 each time the loop is run.</span></span>

<span data-ttu-id="6d23c-137">ステートメントのステートメントリストの部分で変数の値を変更するのではなく、 `For` 次のようにステートメントの **繰り返し** 部分を使用でき `For` ます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-137">Rather than change the value of the variable in the statement list part of the `For` statement, you can use the **Repeat** portion of the `For` statement instead, as follows.</span></span>

```powershell
$i=1
for (;;$i++)
{
    Write-Host $i
}
```

<span data-ttu-id="6d23c-138">このステートメントは、CTRL + C キーを押してコマンドを中断するまで、無限に繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-138">This statement will still repeat indefinitely until you break out of the command by pressing CTRL+C.</span></span>

<span data-ttu-id="6d23c-139">`For`*条件* を使用して、ループを終了できます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-139">You can terminate the `For` loop using a *condition*.</span></span> <span data-ttu-id="6d23c-140">条件は、ステートメントの **条件** 部分を使用して配置でき `For` ます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-140">You can place a condition using the **Condition** portion of the `For` statement.</span></span> <span data-ttu-id="6d23c-141">この `For` ループは、条件がと評価されたときに終了し `$false` ます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-141">The `For` loop terminates when the condition evaluates to `$false`.</span></span>

<span data-ttu-id="6d23c-142">次の例では、 `For` の値が10以下の場合、ループが実行 `$i` されます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-142">In the following example, the `For` loop runs while the value of `$i` is less than or equal to 10.</span></span>

```powershell
$i=1
for(;$i -le 10;$i++)
{
    Write-Host $i
}
```

<span data-ttu-id="6d23c-143">ステートメントの外部で変数を作成して初期化する代わりに `For` 、 `For` ステートメントの **Init** 部分を使用して、このタスクをループ内で実行でき `For` ます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-143">Instead of creating and initializing the variable outside the `For` statement, you can perform this task inside the `For` loop by using the **Init** portion of the `For` statement.</span></span>

```powershell
for($i=1; $i -le 10; $i++){Write-Host $i}
```

<span data-ttu-id="6d23c-144">セミコロンではなく復帰を使用して、ステートメントの **Init**、 **Condition**、および **Repeat** 部分を区切ることができ `For` ます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-144">You can use carriage returns instead of semicolons to delimit the **Init**, **Condition**, and **Repeat** portions of the `For` statement.</span></span> <span data-ttu-id="6d23c-145">次の例は、 `For` この代替構文を使用するを示しています。</span><span class="sxs-lookup"><span data-stu-id="6d23c-145">The following example shows a `For` that uses this alternative syntax.</span></span>

```powershell
for ($i = 0
  $i -lt 10
  $i++){
  $i
}
```

<span data-ttu-id="6d23c-146">この代替形式のステートメントは、 `For` powershell スクリプトファイルと powershell コマンドプロンプトで動作します。</span><span class="sxs-lookup"><span data-stu-id="6d23c-146">This alternative form of the `For` statement works in PowerShell script files and at the PowerShell command prompt.</span></span> <span data-ttu-id="6d23c-147">ただし、 `For` コマンドプロンプトで対話型コマンドを入力する場合は、セミコロンでステートメント構文を使用する方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="6d23c-147">However, it is easier to use the `For` statement syntax with semicolons when you enter interactive commands at the command prompt.</span></span>

<span data-ttu-id="6d23c-148">`For`ループは、 `Foreach` パターンを使用して配列またはコレクションの値をインクリメントできるため、ループよりも柔軟です。</span><span class="sxs-lookup"><span data-stu-id="6d23c-148">The `For` loop is more flexible than the `Foreach` loop because it allows you to increment values in an array or collection by using patterns.</span></span> <span data-ttu-id="6d23c-149">次の例では、 `$i` ステートメントの **繰り返し** 部分で、変数が2ずつインクリメントされてい `For` ます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-149">In the following example, the `$i` variable is incremented by 2 in the **Repeat** portion of the `For` statement.</span></span>

```powershell
for ($i = 0; $i -le 20; $i += 2)
{
    Write-Host $i
}
```

<span data-ttu-id="6d23c-150">ループは、 `For` 次の例のように1行に記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="6d23c-150">The `For` loop can also be written on one line as in the following example.</span></span>

```powershell
for ($i = 0; $i -lt 10; $i++) { Write-Host $i }
```

## <a name="see-also"></a><span data-ttu-id="6d23c-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d23c-151">SEE ALSO</span></span>

[<span data-ttu-id="6d23c-152">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="6d23c-152">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="6d23c-153">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="6d23c-153">about_Foreach</span></span>](about_Foreach.md)

