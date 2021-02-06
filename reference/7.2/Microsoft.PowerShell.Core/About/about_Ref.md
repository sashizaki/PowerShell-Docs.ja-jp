---
description: 参照型の変数を作成して使用する方法について説明します。 参照型の変数を使用すると、関数に渡される変数の値を変更することができます。
Locale: en-US
ms.date: 08/24/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_ref?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Ref
ms.openlocfilehash: 5b966816c8ac1ef91e03c78378f57fa20b5697de
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602620"
---
# <a name="about-ref"></a><span data-ttu-id="ebb85-104">Ref について</span><span class="sxs-lookup"><span data-stu-id="ebb85-104">About Ref</span></span>

## <a name="short-description"></a><span data-ttu-id="ebb85-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="ebb85-105">Short description</span></span>
<span data-ttu-id="ebb85-106">参照型の変数を作成して使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ebb85-106">Describes how to create and use a reference type variable.</span></span> <span data-ttu-id="ebb85-107">参照型の変数を使用すると、関数に渡される変数の値を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="ebb85-107">You can use reference type variables to permit a function to change the value of a variable that is passed to it.</span></span>

## <a name="long-description"></a><span data-ttu-id="ebb85-108">長い説明</span><span class="sxs-lookup"><span data-stu-id="ebb85-108">Long description</span></span>

<span data-ttu-id="ebb85-109">変数は、参照または *値* に *よって* 関数に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="ebb85-109">You can pass variables to functions *by reference* or *by value*.</span></span>

<span data-ttu-id="ebb85-110">変数を *値で* 渡すと、データのコピーが渡されます。</span><span class="sxs-lookup"><span data-stu-id="ebb85-110">When you pass a variable *by value*, you are passing a copy of the data.</span></span>

<span data-ttu-id="ebb85-111">次の例では、関数は、渡された変数の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="ebb85-111">In the following example, the function changes the value of the variable passed to it.</span></span> <span data-ttu-id="ebb85-112">PowerShell では、整数は値型であるため、値によって渡されます。</span><span class="sxs-lookup"><span data-stu-id="ebb85-112">In PowerShell, integers are value types so they are passed by value.</span></span>
<span data-ttu-id="ebb85-113">したがって、の値 `$var` は、関数のスコープ外でも変更されません。</span><span class="sxs-lookup"><span data-stu-id="ebb85-113">Therefore, the value of `$var` is unchanged outside the scope of the function.</span></span>

```powershell
Function Test($data)
{
    $data = 3
}

$var = 10
Test -data $var
$var
```

```output
10
```

<span data-ttu-id="ebb85-114">次の例では、を含む変数 `Hashtable` が関数に渡されます。</span><span class="sxs-lookup"><span data-stu-id="ebb85-114">In the following example, a variable containing a `Hashtable` is passed to a function.</span></span> <span data-ttu-id="ebb85-115">`Hashtable` はオブジェクト型であるため、既定では、 *参照によって* 関数に渡されます。</span><span class="sxs-lookup"><span data-stu-id="ebb85-115">`Hashtable` is an object type so by default it is passed to the function *by reference*.</span></span>

<span data-ttu-id="ebb85-116">変数を *参照* 渡しで渡す場合、関数はデータを変更することができ、関数が実行された後もその変更は保持されます。</span><span class="sxs-lookup"><span data-stu-id="ebb85-116">When passing a variable *by reference*, the function can change the data and that change persists after the function executes.</span></span>

```powershell
Function Test($data)
{
    $data.Test = "New Text"
}

$var = @{}
Test -data $var
$var
```

```output
Name                           Value
----                           -----
Test                           New Text
```

<span data-ttu-id="ebb85-117">関数は、関数のスコープの外部に保持される新しいキーと値のペアを追加します。</span><span class="sxs-lookup"><span data-stu-id="ebb85-117">The function adds a new key-value pair that persists outside of the function's scope.</span></span>

### <a name="writing-functions-to-accept-reference-parameters"></a><span data-ttu-id="ebb85-118">参照パラメーターを受け取る関数の記述</span><span class="sxs-lookup"><span data-stu-id="ebb85-118">Writing functions to accept reference parameters</span></span>

<span data-ttu-id="ebb85-119">渡されたデータの型に関係なく、パラメーターを参照として取得するように関数をコーディングできます。</span><span class="sxs-lookup"><span data-stu-id="ebb85-119">You can code your functions to take a parameter as a reference, regardless of the type of data passed.</span></span> <span data-ttu-id="ebb85-120">そのためには、パラメーターの型を、またはとして指定する必要があり `System.Management.Automation.PSReference` `[ref]` ます。</span><span class="sxs-lookup"><span data-stu-id="ebb85-120">This requires that you specify the parameters type as `System.Management.Automation.PSReference`, or `[ref]`.</span></span>

<span data-ttu-id="ebb85-121">参照を使用する場合は、型のプロパティを使用してデータにアクセスする必要があり `Value` `System.Management.Automation.PSReference` ます。</span><span class="sxs-lookup"><span data-stu-id="ebb85-121">When using references, you must use the `Value` property of the `System.Management.Automation.PSReference` type to access your data.</span></span>

```powershell
Function Test([ref]$data)
{
    $data.Value = 3
}
```

<span data-ttu-id="ebb85-122">参照を必要とするパラメーターに変数を渡すには、「変数を参照としてキャストする」と入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebb85-122">To pass a variable to a parameter that expects a reference, you must type cast your variable as a reference.</span></span>

> [!NOTE]
> <span data-ttu-id="ebb85-123">角かっことかっこは両方とも必要です。</span><span class="sxs-lookup"><span data-stu-id="ebb85-123">The brackets and parenthesis are BOTH required.</span></span>

```powershell
$var = 10
Test -data ([ref]$var)
$var
```

```output
3
```

### <a name="passing-references-to-net-methods"></a><span data-ttu-id="ebb85-124">.NET メソッドへの参照の引き渡し</span><span class="sxs-lookup"><span data-stu-id="ebb85-124">Passing references to .NET methods</span></span>

<span data-ttu-id="ebb85-125">一部の .NET メソッドでは、参照として変数を渡すことが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ebb85-125">Some .NET methods may require you to pass a variable as a reference.</span></span> <span data-ttu-id="ebb85-126">メソッドの定義で、 `in` パラメーターにキーワード、、またはが使用されている場合は、 `out` `ref` 参照が想定されます。</span><span class="sxs-lookup"><span data-stu-id="ebb85-126">When the method's definition uses the keywords `in`, `out`, or `ref` on a parameter, it expects a reference.</span></span>

```powershell
[int] | Get-Member -Static -Name TryParse
```

```output
Name     MemberType Definition
----     ---------- ----------
TryParse Method     static bool TryParse(string s, [ref] int result)
```

<span data-ttu-id="ebb85-127">メソッドは、 `TryParse` 文字列を整数として解析しようとします。</span><span class="sxs-lookup"><span data-stu-id="ebb85-127">The `TryParse` method attempts to parse a string as an integer.</span></span> <span data-ttu-id="ebb85-128">メソッドが成功すると、が返され、 `$true` 結果は **参照によって** 渡された変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="ebb85-128">If the method succeeds, it returns `$true`, and the result is stored in the variable you passed **by reference**.</span></span>

```
PS> $number = 0
PS> [int]::TryParse("15", ([ref]$number))
True
PS> $number
15
```

### <a name="references-and-scopes"></a><span data-ttu-id="ebb85-129">参照とスコープ</span><span class="sxs-lookup"><span data-stu-id="ebb85-129">References and scopes</span></span>

<span data-ttu-id="ebb85-130">参照を使用すると、親スコープ内の変数の値を子スコープ内で変更できます。</span><span class="sxs-lookup"><span data-stu-id="ebb85-130">References allow the value of a variable in the parent scope to be changed within a child scope.</span></span>

```powershell
# Create a value type variable.
$i = 0
# Create a reference type variable.
$iRef = [ref]0
# Invoke a scriptblock to attempt to change both values.
&{$i++;$iRef.Value++}
# Output the results.
"`$i = $i;`$iRef = $($iRef.Value)"
```

```output
$i = 0;$iRef = 1
```

<span data-ttu-id="ebb85-131">参照型の変数のみが変更されました。</span><span class="sxs-lookup"><span data-stu-id="ebb85-131">Only the reference type's variable was changed.</span></span>

## <a name="see-also"></a><span data-ttu-id="ebb85-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebb85-132">See also</span></span>

[<span data-ttu-id="ebb85-133">about_Variables</span><span class="sxs-lookup"><span data-stu-id="ebb85-133">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="ebb85-134">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="ebb85-134">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="ebb85-135">about_Functions</span><span class="sxs-lookup"><span data-stu-id="ebb85-135">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="ebb85-136">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="ebb85-136">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="ebb85-137">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="ebb85-137">about_Scopes</span></span>](about_scopes.md)

