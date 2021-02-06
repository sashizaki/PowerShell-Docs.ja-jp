---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Where-Object
ms.openlocfilehash: 667a503d67ac9a9a0f41187cbac079d946247618
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600578"
---
# <span data-ttu-id="5a765-102">Where-Object</span><span class="sxs-lookup"><span data-stu-id="5a765-102">Where-Object</span></span>

## <span data-ttu-id="5a765-103">概要</span><span class="sxs-lookup"><span data-stu-id="5a765-103">SYNOPSIS</span></span>
<span data-ttu-id="5a765-104">プロパティの値に基づいて、コレクションからオブジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a765-104">Selects objects from a collection based on their property values.</span></span>

## <span data-ttu-id="5a765-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5a765-105">SYNTAX</span></span>

### <span data-ttu-id="5a765-106">EqualSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="5a765-106">EqualSet (Default)</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-EQ]
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-107">ScriptBlockSet</span><span class="sxs-lookup"><span data-stu-id="5a765-107">ScriptBlockSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-FilterScript] <ScriptBlock> [<CommonParameters>]
```

### <span data-ttu-id="5a765-108">MatchSet</span><span class="sxs-lookup"><span data-stu-id="5a765-108">MatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Match
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-109">CaseSensitiveEqualSet</span><span class="sxs-lookup"><span data-stu-id="5a765-109">CaseSensitiveEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CEQ
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-110">NotEqualSet</span><span class="sxs-lookup"><span data-stu-id="5a765-110">NotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NE
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-111">CaseSensitiveNotEqualSet</span><span class="sxs-lookup"><span data-stu-id="5a765-111">CaseSensitiveNotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNE
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-112">GreaterThanSet</span><span class="sxs-lookup"><span data-stu-id="5a765-112">GreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GT
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-113">CaseSensitiveGreaterThanSet</span><span class="sxs-lookup"><span data-stu-id="5a765-113">CaseSensitiveGreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGT
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-114">設定しない</span><span class="sxs-lookup"><span data-stu-id="5a765-114">LessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LT
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-115">CaseSensitiveLessThanSet</span><span class="sxs-lookup"><span data-stu-id="5a765-115">CaseSensitiveLessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLT
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-116">GreaterOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="5a765-116">GreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GE
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-117">CaseSensitiveGreaterOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="5a765-117">CaseSensitiveGreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGE
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-118">LessOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="5a765-118">LessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LE
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-119">CaseSensitiveLessOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="5a765-119">CaseSensitiveLessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLE
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-120">数字セット</span><span class="sxs-lookup"><span data-stu-id="5a765-120">LikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Like
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-121">CaseSensitiveLikeSet</span><span class="sxs-lookup"><span data-stu-id="5a765-121">CaseSensitiveLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLike
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-122">Not記法セット</span><span class="sxs-lookup"><span data-stu-id="5a765-122">NotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotLike
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-123">CaseSensitiveNotLikeSet</span><span class="sxs-lookup"><span data-stu-id="5a765-123">CaseSensitiveNotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotLike
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-124">CaseSensitiveMatchSet</span><span class="sxs-lookup"><span data-stu-id="5a765-124">CaseSensitiveMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CMatch
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-125">NotMatchSet</span><span class="sxs-lookup"><span data-stu-id="5a765-125">NotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotMatch
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-126">CaseSensitiveNotMatchSet</span><span class="sxs-lookup"><span data-stu-id="5a765-126">CaseSensitiveNotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotMatch
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-127">集合集合</span><span class="sxs-lookup"><span data-stu-id="5a765-127">ContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Contains
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-128">CaseSensitiveContainsSet</span><span class="sxs-lookup"><span data-stu-id="5a765-128">CaseSensitiveContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CContains
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-129">Not集合セット</span><span class="sxs-lookup"><span data-stu-id="5a765-129">NotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotContains
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-130">CaseSensitiveNotContainsSet</span><span class="sxs-lookup"><span data-stu-id="5a765-130">CaseSensitiveNotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotContains
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-131">ペン</span><span class="sxs-lookup"><span data-stu-id="5a765-131">InSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -In
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-132">CaseSensitiveInSet</span><span class="sxs-lookup"><span data-stu-id="5a765-132">CaseSensitiveInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CIn
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-133">NotInSet</span><span class="sxs-lookup"><span data-stu-id="5a765-133">NotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotIn
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-134">CaseSensitiveNotInSet</span><span class="sxs-lookup"><span data-stu-id="5a765-134">CaseSensitiveNotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotIn
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-135">IsSet</span><span class="sxs-lookup"><span data-stu-id="5a765-135">IsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Is
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-136">IsNotSet</span><span class="sxs-lookup"><span data-stu-id="5a765-136">IsNotSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -IsNot
 [<CommonParameters>]
```

### <span data-ttu-id="5a765-137">Not</span><span class="sxs-lookup"><span data-stu-id="5a765-137">Not</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> -Not [<CommonParameters>]
```

## <span data-ttu-id="5a765-138">Description</span><span class="sxs-lookup"><span data-stu-id="5a765-138">DESCRIPTION</span></span>

<span data-ttu-id="5a765-139">コマンドレットでは、 `Where-Object` 渡されるオブジェクトのコレクションから、特定のプロパティ値を持つオブジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a765-139">The `Where-Object` cmdlet selects objects that have particular property values from the collection of objects that are passed to it.</span></span> <span data-ttu-id="5a765-140">たとえば、コマンドレットを使用して、特定の `Where-Object` 日付以降に作成されたファイル、特定の ID を持つイベント、または特定のバージョンの Windows を使用するコンピューターを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5a765-140">For example, you can use the `Where-Object` cmdlet to select files that were created after a certain date, events with a particular ID, or computers that use a particular version of Windows.</span></span>

<span data-ttu-id="5a765-141">Windows PowerShell 3.0 以降では、コマンドを構築する方法は2つあり `Where-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="5a765-141">Starting in Windows PowerShell 3.0, there are two different ways to construct a `Where-Object` command.</span></span>

- <span data-ttu-id="5a765-142">**スクリプトブロック**。</span><span class="sxs-lookup"><span data-stu-id="5a765-142">**Script block**.</span></span> <span data-ttu-id="5a765-143">スクリプト ブロックを使用すると、プロパティ名、比較演算子、プロパティ値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5a765-143">You can use a script block to specify the property name, a comparison operator, and a property value.</span></span> <span data-ttu-id="5a765-144">`Where-Object` スクリプトブロックステートメントが true であるすべてのオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="5a765-144">`Where-Object` returns all objects for which the script block statement is true.</span></span>

  <span data-ttu-id="5a765-145">たとえば、次のコマンドは、通常の優先度クラスのプロセスを取得します。つまり、"優先度" **クラス** プロパティの値が normal であるプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="5a765-145">For example, the following command gets processes in the Normal priority class, that is, processes where the value of the **PriorityClass** property equals Normal.</span></span>

  `Get-Process | Where-Object {$_.PriorityClass -eq "Normal"}`

  <span data-ttu-id="5a765-146">すべての PowerShell 比較演算子は、スクリプトブロック形式で有効です。</span><span class="sxs-lookup"><span data-stu-id="5a765-146">All PowerShell comparison operators are valid in the script block format.</span></span> <span data-ttu-id="5a765-147">比較演算子の詳細については、「 [about_Comparison_Operators](./About/about_Comparison_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a765-147">For more information about comparison operators, see [about_Comparison_Operators](./About/about_Comparison_Operators.md).</span></span>

- <span data-ttu-id="5a765-148">**比較ステートメント**。</span><span class="sxs-lookup"><span data-stu-id="5a765-148">**Comparison statement**.</span></span> <span data-ttu-id="5a765-149">比較ステートメントを使用すると、自然言語のように記述することができます。</span><span class="sxs-lookup"><span data-stu-id="5a765-149">You can also write a comparison statement, which is much more like natural language.</span></span> <span data-ttu-id="5a765-150">比較ステートメントは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-150">Comparison statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="5a765-151">たとえば、次のコマンドは、priority クラスが Normal のプロセスも取得します。</span><span class="sxs-lookup"><span data-stu-id="5a765-151">For example, the following commands also get processes that have a priority class of Normal.</span></span> <span data-ttu-id="5a765-152">これらのコマンドは同等であり、置き換えて使用することができます。</span><span class="sxs-lookup"><span data-stu-id="5a765-152">These commands are equivalent and can be used interchangeably.</span></span>

  `Get-Process | Where-Object -Property PriorityClass -eq -Value "Normal"`

  `Get-Process | Where-Object PriorityClass -eq "Normal"`

  <span data-ttu-id="5a765-153">Windows PowerShell 3.0 以降では、 `Where-Object` コマンドのパラメーターとして比較演算子が追加さ `Where-Object` れています。</span><span class="sxs-lookup"><span data-stu-id="5a765-153">Starting in Windows PowerShell 3.0, `Where-Object` adds comparison operators as parameters in a `Where-Object` command.</span></span> <span data-ttu-id="5a765-154">すべての演算子は、特に指定しない限り、大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="5a765-154">Unless specified, all operators are case-insensitive.</span></span> <span data-ttu-id="5a765-155">Windows PowerShell 3.0 より前では、PowerShell 言語の比較演算子は、スクリプトブロックでのみ使用できました。</span><span class="sxs-lookup"><span data-stu-id="5a765-155">Prior to Windows PowerShell 3.0, the comparison operators in the PowerShell language could be used only in script blocks.</span></span>

<span data-ttu-id="5a765-156">に1つの **プロパティ** を指定すると `Where-Object` 、プロパティの値はブール式として扱われます。</span><span class="sxs-lookup"><span data-stu-id="5a765-156">When you provide a single **Property** to `Where-Object`, the value of the property is treated as a boolean expression.</span></span> <span data-ttu-id="5a765-157">**Length** の値が0でない場合、式は **True** に評価されます。</span><span class="sxs-lookup"><span data-stu-id="5a765-157">When the value of **Length** is not zero, the expression evaluates to **True**.</span></span> <span data-ttu-id="5a765-158">例: `('hi', '', 'there') | Where-Object Length`</span><span class="sxs-lookup"><span data-stu-id="5a765-158">For example: `('hi', '', 'there') | Where-Object Length`</span></span>

<span data-ttu-id="5a765-159">前の例は、機能的には次のように相当します。</span><span class="sxs-lookup"><span data-stu-id="5a765-159">The previous example is functionally equivalent to:</span></span>

- `('hi', '', 'there') | Where-Object Length -GT 0`
- `('hi', '', 'there') | Where-Object {$_.Length -gt 0}`

## <span data-ttu-id="5a765-160">例</span><span class="sxs-lookup"><span data-stu-id="5a765-160">EXAMPLES</span></span>

### <span data-ttu-id="5a765-161">例 1: 停止したサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="5a765-161">Example 1: Get stopped services</span></span>

<span data-ttu-id="5a765-162">これらのコマンドは、現在停止しているすべてのサービスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="5a765-162">These commands get a list of all services that are currently stopped.</span></span> <span data-ttu-id="5a765-163">`$_`自動変数は、コマンドレットに渡される各オブジェクトを表し `Where-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="5a765-163">The `$_` automatic variable represents each object that is passed to the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="5a765-164">最初のコマンドは、スクリプトブロック形式を使用します。2番目のコマンドは、比較ステートメント形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a765-164">The first command uses the script block format, the second command uses the comparison statement format.</span></span> <span data-ttu-id="5a765-165">コマンドは等価であり、同じ意味で使用することができます。</span><span class="sxs-lookup"><span data-stu-id="5a765-165">The commands are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Stopped"}
Get-Service | where Status -eq "Stopped"
```

### <span data-ttu-id="5a765-166">例 2: ワーキングセットに基づいてプロセスを取得する</span><span class="sxs-lookup"><span data-stu-id="5a765-166">Example 2: Get processes based on working set</span></span>

<span data-ttu-id="5a765-167">これらのコマンドは、ワーキングセットが250メガバイト (KB) を超えるプロセスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-167">These commands list processes that have a working set greater than 250 megabytes (KB).</span></span> <span data-ttu-id="5a765-168">Scriptblock とステートメントの構文は同等であり、同じように使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a765-168">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.WorkingSet -GT 250MB}
Get-Process | Where-Object WorkingSet -GT (250MB)
```

### <span data-ttu-id="5a765-169">例 3: プロセス名に基づいてプロセスを取得する</span><span class="sxs-lookup"><span data-stu-id="5a765-169">Example 3: Get processes based on process name</span></span>

<span data-ttu-id="5a765-170">これらのコマンドは、文字で始まる **ProcessName** プロパティ値を持つプロセスを取得し `p` ます。</span><span class="sxs-lookup"><span data-stu-id="5a765-170">These commands get the processes that have a **ProcessName** property value that begins with the letter `p`.</span></span> <span data-ttu-id="5a765-171">**Match** 演算子を使用すると、正規表現の一致を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a765-171">The **Match** operator lets you use regular expression matches.</span></span>

<span data-ttu-id="5a765-172">Scriptblock とステートメントの構文は同等であり、同じように使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a765-172">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.ProcessName -Match "^p.*"}
Get-Process | Where-Object ProcessName -Match "^p.*"
```

### <span data-ttu-id="5a765-173">例 4: 比較ステートメントの形式を使用する</span><span class="sxs-lookup"><span data-stu-id="5a765-173">Example 4: Use the comparison statement format</span></span>

<span data-ttu-id="5a765-174">この例では、コマンドレットの新しい比較ステートメント形式を使用する方法を示し `Where-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="5a765-174">This example shows how to use the new comparison statement format of the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="5a765-175">最初のコマンドは、比較ステートメント形式を使用しています。</span><span class="sxs-lookup"><span data-stu-id="5a765-175">The first command uses the comparison statement format.</span></span>
<span data-ttu-id="5a765-176">このコマンドでは、エイリアスは使用されず、すべてのパラメーターにパラメーター名が使用されています。</span><span class="sxs-lookup"><span data-stu-id="5a765-176">In this command, no aliases are used and all parameters include the parameter name.</span></span>

<span data-ttu-id="5a765-177">2 番目のコマンドは、比較コマンドの形式をより自然に使用しています。</span><span class="sxs-lookup"><span data-stu-id="5a765-177">The second command is the more natural use of the comparison command format.</span></span> <span data-ttu-id="5a765-178">`where`エイリアスはコマンドレット名の代わりに使用され、 `Where-Object` すべての省略可能なパラメーター名は省略されます。</span><span class="sxs-lookup"><span data-stu-id="5a765-178">The `where` alias is substituted for the `Where-Object` cmdlet name and all optional parameter names are omitted.</span></span>

```powershell
Get-Process | Where-Object -Property Handles -GE -Value 1000
Get-Process | where Handles -GE 1000
```

### <span data-ttu-id="5a765-179">例 5: プロパティに基づいてコマンドを取得する</span><span class="sxs-lookup"><span data-stu-id="5a765-179">Example 5: Get commands based on properties</span></span>

<span data-ttu-id="5a765-180">この例では、true または false の項目、または指定したプロパティの任意の値を持つ項目を返すコマンドを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-180">This example shows how to write commands that return items that are true or false or have any value for a specified property.</span></span> <span data-ttu-id="5a765-181">各例では、コマンドのスクリプトブロック形式と比較ステートメント形式の両方を示しています。</span><span class="sxs-lookup"><span data-stu-id="5a765-181">Each example shows both the script block and comparison statement formats for the command.</span></span>

```powershell
# Use Where-Object to get commands that have any value for the OutputType property of the command.
# This omits commands that do not have an OutputType property and those that have an OutputType property, but no property value.
Get-Command | where OutputType
Get-Command | where {$_.OutputType}
```

```powershell
# Use Where-Object to get objects that are containers.
# This gets objects that have the **PSIsContainer** property with a value of $True and excludes all others.
Get-ChildItem | where PSIsContainer
Get-ChildItem | where {$_.PSIsContainer}
```

```powershell
# Finally, use the Not operator (!) to get objects that are not containers.
# This gets objects that do have the **PSIsContainer** property and those that have a value of $False for the **PSIsContainer** property.
Get-ChildItem | where {!$_.PSIsContainer}
# You cannot use the Not operator (!) in the comparison statement format of the command.
Get-ChildItem | where PSIsContainer -eq $False
```

### <span data-ttu-id="5a765-182">例 6: 複数の条件を使用する</span><span class="sxs-lookup"><span data-stu-id="5a765-182">Example 6: Use multiple conditions</span></span>

```powershell
Get-Module -ListAvailable | where {($_.Name -notlike "Microsoft*" -and $_.Name -notlike "PS*") -and $_.HelpInfoUri}
```

<span data-ttu-id="5a765-183">この例では、 `Where-Object` 複数の条件を持つコマンドを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-183">This example shows how to create a `Where-Object` command with multiple conditions.</span></span>

<span data-ttu-id="5a765-184">このコマンドは、更新可能なヘルプ機能をサポートしている非コア モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="5a765-184">This command gets non-core modules that support the Updatable Help feature.</span></span> <span data-ttu-id="5a765-185">このコマンドは、コマンドレットの **ListAvailable** パラメーターを使用して、 `Get-Module` コンピューター上のすべてのモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="5a765-185">The command uses the **ListAvailable** parameter of the `Get-Module` cmdlet to get all modules on the computer.</span></span> <span data-ttu-id="5a765-186">パイプライン演算子 () は、 `|` モジュールを `Where-Object` コマンドレットに送信します。このコマンドレットは、名前が Microsoft または PS で始まらないモジュールを取得し、 **Helpinfouri** プロパティの値を設定します。これにより、モジュールの更新されたヘルプファイルの検索場所を PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-186">A pipeline operator (`|`) sends the modules to the `Where-Object` cmdlet, which gets modules whose names do not begin with Microsoft or PS, and have a value for the **HelpInfoURI** property, which tells PowerShell where to find updated help files for the module.</span></span> <span data-ttu-id="5a765-187">比較ステートメントは、 **and** 論理演算子によって結合されます。</span><span class="sxs-lookup"><span data-stu-id="5a765-187">The comparison statements are connected by the **And** logical operator.</span></span>

<span data-ttu-id="5a765-188">この例は、スクリプト ブロックのコマンド形式を使用しています。</span><span class="sxs-lookup"><span data-stu-id="5a765-188">The example uses the script block command format.</span></span> <span data-ttu-id="5a765-189">論理演算子 ( **and** や **Or** など) は、スクリプトブロックでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="5a765-189">Logical operators, such as **And** and **Or**, are valid only in script blocks.</span></span> <span data-ttu-id="5a765-190">コマンドの比較ステートメント形式で使用することはできません `Where-Object` 。</span><span class="sxs-lookup"><span data-stu-id="5a765-190">You cannot use them in the comparison statement format of a `Where-Object` command.</span></span>

- <span data-ttu-id="5a765-191">PowerShell の論理演算子の詳細については、「 [about_Logical_Operators](./About/about_logical_operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a765-191">For more information about PowerShell logical operators, see [about_Logical_Operators](./About/about_logical_operators.md).</span></span>
- <span data-ttu-id="5a765-192">更新可能なヘルプ機能の詳細については、「 [about_Updatable_Help](./About/about_Updatable_Help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a765-192">For more information about the Updatable Help feature, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>

## <span data-ttu-id="5a765-193">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5a765-193">PARAMETERS</span></span>

### <span data-ttu-id="5a765-194">-CContains</span><span class="sxs-lookup"><span data-stu-id="5a765-194">-CContains</span></span>

<span data-ttu-id="5a765-195">オブジェクトのプロパティ値が指定した値と完全に一致する場合に、このコマンドレットがコレクションからオブジェクトを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-195">Indicates that this cmdlet gets objects from a collection if the property value of the object is an exact match for the specified value.</span></span> <span data-ttu-id="5a765-196">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="5a765-196">This operation is case-sensitive.</span></span>

<span data-ttu-id="5a765-197">例: `Get-Process | where ProcessName -CContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="5a765-197">For example: `Get-Process | where ProcessName -CContains "svchost"`</span></span>

<span data-ttu-id="5a765-198">**Ccontains** は値のコレクションを参照し、指定された値と完全に一致する項目がコレクションに格納されている場合は true になります。</span><span class="sxs-lookup"><span data-stu-id="5a765-198">**CContains** refers to a collection of values and is true if the collection contains an item that is an exact match for the specified value.</span></span> <span data-ttu-id="5a765-199">入力が単一のオブジェクトの場合、PowerShell はそれを1つのオブジェクトのコレクションに変換します。</span><span class="sxs-lookup"><span data-stu-id="5a765-199">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="5a765-200">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-200">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveContainsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-201">-CEQ</span><span class="sxs-lookup"><span data-stu-id="5a765-201">-CEQ</span></span>

<span data-ttu-id="5a765-202">プロパティ値が指定した値と同じ場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-202">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>
<span data-ttu-id="5a765-203">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="5a765-203">This operation is case-sensitive.</span></span>

<span data-ttu-id="5a765-204">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-204">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-205">-CGE</span><span class="sxs-lookup"><span data-stu-id="5a765-205">-CGE</span></span>

<span data-ttu-id="5a765-206">プロパティ値が指定した値以上の場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-206">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span> <span data-ttu-id="5a765-207">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="5a765-207">This operation is case-sensitive.</span></span>

<span data-ttu-id="5a765-208">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-208">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveGreaterOrEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-209">-CGT</span><span class="sxs-lookup"><span data-stu-id="5a765-209">-CGT</span></span>

<span data-ttu-id="5a765-210">プロパティ値が指定した値よりも大きい場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-210">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>
<span data-ttu-id="5a765-211">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="5a765-211">This operation is case-sensitive.</span></span>

<span data-ttu-id="5a765-212">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-212">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveGreaterThanSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-213">-CIn</span><span class="sxs-lookup"><span data-stu-id="5a765-213">-CIn</span></span>

<span data-ttu-id="5a765-214">プロパティ値に指定した値が含まれている場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-214">Indicates that this cmdlet gets objects if the property value includes the specified value.</span></span> <span data-ttu-id="5a765-215">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="5a765-215">This operation is case-sensitive.</span></span>

<span data-ttu-id="5a765-216">例: `Get-Process | where -Value "svchost" -CIn ProcessName`</span><span class="sxs-lookup"><span data-stu-id="5a765-216">For example: `Get-Process | where -Value "svchost" -CIn ProcessName`</span></span>

<span data-ttu-id="5a765-217">**CIn** は **ccontains** に似ていますが、プロパティと値の位置が逆になる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="5a765-217">**CIn** resembles **CContains**, except that the property and value positions are reversed.</span></span> <span data-ttu-id="5a765-218">たとえば、次のステートメントはどちらも true です。</span><span class="sxs-lookup"><span data-stu-id="5a765-218">For example, the following statements are both true.</span></span>

`"abc", "def" -CContains "abc"`

`"abc" -CIn "abc", "def"`

<span data-ttu-id="5a765-219">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-219">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveInSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-220">-CLE</span><span class="sxs-lookup"><span data-stu-id="5a765-220">-CLE</span></span>

<span data-ttu-id="5a765-221">プロパティ値が指定した値以下の場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-221">Indicates that this cmdlet gets objects if the property value is less-than or equal to the specified value.</span></span> <span data-ttu-id="5a765-222">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="5a765-222">This operation is case-sensitive.</span></span>

<span data-ttu-id="5a765-223">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-223">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLessOrEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-224">-CLike</span><span class="sxs-lookup"><span data-stu-id="5a765-224">-CLike</span></span>

<span data-ttu-id="5a765-225">プロパティ値がワイルドカード文字を含む値と一致する場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-225">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span> <span data-ttu-id="5a765-226">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="5a765-226">This operation is case-sensitive.</span></span>

<span data-ttu-id="5a765-227">例: `Get-Process | where ProcessName -CLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="5a765-227">For example: `Get-Process | where ProcessName -CLike "*host"`</span></span>

<span data-ttu-id="5a765-228">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-228">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLikeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-229">-CLT</span><span class="sxs-lookup"><span data-stu-id="5a765-229">-CLT</span></span>

<span data-ttu-id="5a765-230">プロパティ値が指定した値より小さい場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-230">Indicates that this cmdlet gets objects if the property value is less-than the specified value.</span></span> <span data-ttu-id="5a765-231">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="5a765-231">This operation is case-sensitive.</span></span>

<span data-ttu-id="5a765-232">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-232">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLessThanSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-233">-CMatch</span><span class="sxs-lookup"><span data-stu-id="5a765-233">-CMatch</span></span>

<span data-ttu-id="5a765-234">プロパティ値が指定した正規表現に一致する場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-234">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="5a765-235">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="5a765-235">This operation is case-sensitive.</span></span> <span data-ttu-id="5a765-236">入力がスカラーの場合は、一致した値が自動変数に保存され `$Matches` ます。</span><span class="sxs-lookup"><span data-stu-id="5a765-236">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="5a765-237">例: `Get-Process | where ProcessName -CMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="5a765-237">For example: `Get-Process | where ProcessName -CMatch "Shell"`</span></span>

<span data-ttu-id="5a765-238">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-238">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveMatchSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-239">-CNE</span><span class="sxs-lookup"><span data-stu-id="5a765-239">-CNE</span></span>

<span data-ttu-id="5a765-240">プロパティ値が指定した値と異なる場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-240">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>
<span data-ttu-id="5a765-241">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="5a765-241">This operation is case-sensitive.</span></span>

<span data-ttu-id="5a765-242">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-242">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-243">-CNotContains</span><span class="sxs-lookup"><span data-stu-id="5a765-243">-CNotContains</span></span>

<span data-ttu-id="5a765-244">オブジェクトのプロパティ値が指定した値と完全に一致しない場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-244">Indicates that this cmdlet gets objects if the property value of the object is not an exact match for the specified value.</span></span> <span data-ttu-id="5a765-245">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="5a765-245">This operation is case-sensitive.</span></span>

<span data-ttu-id="5a765-246">例: `Get-Process | where ProcessName -CNotContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="5a765-246">For example: `Get-Process | where ProcessName -CNotContains "svchost"`</span></span>

<span data-ttu-id="5a765-247">**Notcontains** と **cnotcontains** は値のコレクションを参照し、指定された値と完全に一致する項目がコレクションに含まれていない場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="5a765-247">**NotContains** and **CNotContains** refer to a collection of values and are true when the collection does not contains any items that are an exact match for the specified value.</span></span> <span data-ttu-id="5a765-248">入力が単一のオブジェクトの場合、PowerShell はそれを1つのオブジェクトのコレクションに変換します。</span><span class="sxs-lookup"><span data-stu-id="5a765-248">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="5a765-249">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-249">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotContainsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-250">-CNotIn</span><span class="sxs-lookup"><span data-stu-id="5a765-250">-CNotIn</span></span>

<span data-ttu-id="5a765-251">プロパティ値が指定した値と完全に一致しない場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-251">Indicates that this cmdlet gets objects if the property value is not an exact match for the specified value.</span></span> <span data-ttu-id="5a765-252">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="5a765-252">This operation is case-sensitive.</span></span>

<span data-ttu-id="5a765-253">例: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="5a765-253">For example: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span></span>

<span data-ttu-id="5a765-254">**Notin** および **cnotin** 演算子は、プロパティと値の位置が逆になる点を除い **て、Notin** および **cnotin** と似ています。</span><span class="sxs-lookup"><span data-stu-id="5a765-254">**NotIn** and **CNotIn** operators resemble **NotContains** and **CNotContains**, except that the property and value positions are reversed.</span></span> <span data-ttu-id="5a765-255">たとえば、次のステートメントは true です。</span><span class="sxs-lookup"><span data-stu-id="5a765-255">For example, the following statements are true.</span></span>

`"abc", "def" -CNotContains "Abc"`

`"abc" -CNotIn "Abc", "def"`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotInSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-256">-CNotLike</span><span class="sxs-lookup"><span data-stu-id="5a765-256">-CNotLike</span></span>

<span data-ttu-id="5a765-257">プロパティ値がワイルドカード文字を含む値と一致しない場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-257">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span> <span data-ttu-id="5a765-258">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="5a765-258">This operation is case-sensitive.</span></span>

<span data-ttu-id="5a765-259">例: `Get-Process | where ProcessName -CNotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="5a765-259">For example: `Get-Process | where ProcessName -CNotLike "*host"`</span></span>

<span data-ttu-id="5a765-260">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-260">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotLikeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-261">-CNotMatch</span><span class="sxs-lookup"><span data-stu-id="5a765-261">-CNotMatch</span></span>

<span data-ttu-id="5a765-262">プロパティ値が指定した正規表現と一致しない場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-262">Indicates that this cmdlet gets objects if the property value does not match the specified regular expression.</span></span> <span data-ttu-id="5a765-263">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="5a765-263">This operation is case-sensitive.</span></span> <span data-ttu-id="5a765-264">入力がスカラーの場合は、一致した値が自動変数に保存され `$Matches` ます。</span><span class="sxs-lookup"><span data-stu-id="5a765-264">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="5a765-265">例: `Get-Process | where ProcessName -CNotMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="5a765-265">For example: `Get-Process | where ProcessName -CNotMatch "Shell"`</span></span>

<span data-ttu-id="5a765-266">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-266">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotMatchSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-267">-Contains</span><span class="sxs-lookup"><span data-stu-id="5a765-267">-Contains</span></span>

<span data-ttu-id="5a765-268">オブジェクトのプロパティ値の項目が指定した値と完全に一致する場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-268">Indicates that this cmdlet gets objects if any item in the property value of the object is an exact match for the specified value.</span></span>

<span data-ttu-id="5a765-269">例: `Get-Process | where ProcessName -Contains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="5a765-269">For example: `Get-Process | where ProcessName -Contains "Svchost"`</span></span>

<span data-ttu-id="5a765-270">プロパティ値に1つのオブジェクトが含まれている場合、PowerShell はそれを1つのオブジェクトのコレクションに変換します。</span><span class="sxs-lookup"><span data-stu-id="5a765-270">If the property value contains a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="5a765-271">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-271">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainsSet
Aliases: IContains

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-272">-EQ</span><span class="sxs-lookup"><span data-stu-id="5a765-272">-EQ</span></span>

<span data-ttu-id="5a765-273">プロパティ値が指定した値と同じ場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-273">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>

<span data-ttu-id="5a765-274">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-274">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: EqualSet
Aliases: IEQ

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-275">-FilterScript</span><span class="sxs-lookup"><span data-stu-id="5a765-275">-FilterScript</span></span>

<span data-ttu-id="5a765-276">オブジェクトをフィルター処理するために使用するスクリプト ブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="5a765-276">Specifies the script block that is used to filter the objects.</span></span> <span data-ttu-id="5a765-277">スクリプトブロックを中かっこ () で囲み `{}` ます。</span><span class="sxs-lookup"><span data-stu-id="5a765-277">Enclose the script block in braces (`{}`).</span></span>

<span data-ttu-id="5a765-278">パラメーター名 **Filterscript** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5a765-278">The parameter name, **FilterScript**, is optional.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-279">-GE</span><span class="sxs-lookup"><span data-stu-id="5a765-279">-GE</span></span>

<span data-ttu-id="5a765-280">プロパティ値が指定した値以上の場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-280">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span>

<span data-ttu-id="5a765-281">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-281">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GreaterOrEqualSet
Aliases: IGE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-282">-GT</span><span class="sxs-lookup"><span data-stu-id="5a765-282">-GT</span></span>

<span data-ttu-id="5a765-283">プロパティ値が指定した値よりも大きい場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-283">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>

<span data-ttu-id="5a765-284">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-284">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GreaterThanSet
Aliases: IGT

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-285">-In</span><span class="sxs-lookup"><span data-stu-id="5a765-285">-In</span></span>

<span data-ttu-id="5a765-286">プロパティ値が指定した値と一致する場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-286">Indicates that this cmdlet gets objects if the property value matches any of the specified values.</span></span>
<span data-ttu-id="5a765-287">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-287">For example:</span></span>

`Get-Process | where -Property ProcessName -in -Value "Svchost", "TaskHost", "WsmProvHost"`

<span data-ttu-id="5a765-288">**Value** パラメーターの値が単一のオブジェクトの場合、PowerShell はそれを1つのオブジェクトのコレクションに変換します。</span><span class="sxs-lookup"><span data-stu-id="5a765-288">If the value of the **Value** parameter is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="5a765-289">オブジェクトのプロパティ値が配列の場合、PowerShell は参照の等価性を使用して一致を判定します。</span><span class="sxs-lookup"><span data-stu-id="5a765-289">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="5a765-290">`Where-Object`**Property** パラメーターの値と **値** の値がオブジェクトの同じインスタンスである場合にのみ、オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="5a765-290">`Where-Object` returns the object only if the value of the **Property** parameter and any value of **Value** are the same instance of an object.</span></span>

<span data-ttu-id="5a765-291">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-291">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: InSet
Aliases: IIn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-292">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5a765-292">-InputObject</span></span>

<span data-ttu-id="5a765-293">フィルター処理されるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="5a765-293">Specifies the objects to be filtered.</span></span> <span data-ttu-id="5a765-294">パイプを使用してオブジェクトをにパイプすることもでき `Where-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="5a765-294">You can also pipe the objects to `Where-Object`.</span></span>

<span data-ttu-id="5a765-295">で **inputobject** パラメーターを使用すると、 `Where-Object` コマンドの結果をにパイプするのではなく、 `Where-Object` **inputobject** 値が1つのオブジェクトとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="5a765-295">When you use the **InputObject** parameter with `Where-Object`, instead of piping command results to `Where-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="5a765-296">これは、値が、などのコマンドの結果であるコレクションである場合にも当てはまり `-InputObject (Get-Process)` ます。</span><span class="sxs-lookup"><span data-stu-id="5a765-296">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span> <span data-ttu-id="5a765-297">**InputObject** は配列またはオブジェクトのコレクションから個々のプロパティを返すことができないため、を使用し `Where-Object` て、定義されたプロパティに特定の値を持つオブジェクトのコレクションをフィルター処理する場合は、 `Where-Object` このトピックの例に示すように、パイプラインでを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5a765-297">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that, if you use `Where-Object` to filter a collection of objects for those objects that have specific values in defined properties, you use `Where-Object` in the pipeline, as shown in the examples in this topic.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-298">-が</span><span class="sxs-lookup"><span data-stu-id="5a765-298">-Is</span></span>

<span data-ttu-id="5a765-299">プロパティ値が指定された .NET 型のインスタンスの場合に、このコマンドレットがオブジェクトを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-299">Indicates that this cmdlet gets objects if the property value is an instance of the specified .NET type.</span></span> <span data-ttu-id="5a765-300">型名を角かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="5a765-300">Enclose the type name in square brackets.</span></span>

<span data-ttu-id="5a765-301">たとえば、`Get-Process | where StartTime -Is [DateTime]`</span><span class="sxs-lookup"><span data-stu-id="5a765-301">For example, `Get-Process | where StartTime -Is [DateTime]`</span></span>

<span data-ttu-id="5a765-302">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-302">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-303">-IsNot</span><span class="sxs-lookup"><span data-stu-id="5a765-303">-IsNot</span></span>

<span data-ttu-id="5a765-304">プロパティ値が指定した .NET 型のインスタンスでない場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-304">Indicates that this cmdlet gets objects if the property value is not an instance of the specified .NET type.</span></span>

<span data-ttu-id="5a765-305">たとえば、`Get-Process | where StartTime -IsNot [DateTime]`</span><span class="sxs-lookup"><span data-stu-id="5a765-305">For example, `Get-Process | where StartTime -IsNot [DateTime]`</span></span>

<span data-ttu-id="5a765-306">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-306">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsNotSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-307">-LE</span><span class="sxs-lookup"><span data-stu-id="5a765-307">-LE</span></span>

<span data-ttu-id="5a765-308">プロパティ値が指定した値以下の場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-308">Indicates that this cmdlet gets objects if the property value is less than or equal to the specified value.</span></span>

<span data-ttu-id="5a765-309">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-309">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LessOrEqualSet
Aliases: ILE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-310">-Like</span><span class="sxs-lookup"><span data-stu-id="5a765-310">-Like</span></span>

<span data-ttu-id="5a765-311">プロパティ値がワイルドカード文字を含む値と一致する場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-311">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span>

<span data-ttu-id="5a765-312">例: `Get-Process | where ProcessName -Like "*host"`</span><span class="sxs-lookup"><span data-stu-id="5a765-312">For example: `Get-Process | where ProcessName -Like "*host"`</span></span>

<span data-ttu-id="5a765-313">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-313">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LikeSet
Aliases: ILike

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-314">-LT</span><span class="sxs-lookup"><span data-stu-id="5a765-314">-LT</span></span>

<span data-ttu-id="5a765-315">プロパティ値が指定した値よりも小さい場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-315">Indicates that this cmdlet gets objects if the property value is less than the specified value.</span></span>

<span data-ttu-id="5a765-316">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-316">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LessThanSet
Aliases: ILT

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-317">-一致</span><span class="sxs-lookup"><span data-stu-id="5a765-317">-Match</span></span>

<span data-ttu-id="5a765-318">プロパティ値が指定した正規表現に一致する場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-318">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="5a765-319">入力がスカラーの場合は、一致した値が自動変数に保存され `$Matches` ます。</span><span class="sxs-lookup"><span data-stu-id="5a765-319">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="5a765-320">例: `Get-Process | where ProcessName -Match "shell"`</span><span class="sxs-lookup"><span data-stu-id="5a765-320">For example: `Get-Process | where ProcessName -Match "shell"`</span></span>

<span data-ttu-id="5a765-321">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-321">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MatchSet
Aliases: IMatch

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-322">-NE</span><span class="sxs-lookup"><span data-stu-id="5a765-322">-NE</span></span>

<span data-ttu-id="5a765-323">プロパティ値が指定した値と異なる場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-323">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>

<span data-ttu-id="5a765-324">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-324">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotEqualSet
Aliases: INE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-325">-Not</span><span class="sxs-lookup"><span data-stu-id="5a765-325">-Not</span></span>

<span data-ttu-id="5a765-326">プロパティが存在しない場合、または値が null または false の場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-326">Indicates that this cmdlet gets objects if the property does not exist or has a value of null or false.</span></span>

<span data-ttu-id="5a765-327">例: `Get-Service | where -Not "DependentServices"`</span><span class="sxs-lookup"><span data-stu-id="5a765-327">For example: `Get-Service | where -Not "DependentServices"`</span></span>

<span data-ttu-id="5a765-328">このパラメーターは、Windows PowerShell 6.1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-328">This parameter was introduced in Windows PowerShell 6.1.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Not
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-329">-NotContains</span><span class="sxs-lookup"><span data-stu-id="5a765-329">-NotContains</span></span>

<span data-ttu-id="5a765-330">プロパティ値の項目が指定した値と完全に一致しない場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-330">Indicates that this cmdlet gets objects if none of the items in the property value is an exact match for the specified value.</span></span>

<span data-ttu-id="5a765-331">例: `Get-Process | where ProcessName -NotContains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="5a765-331">For example: `Get-Process | where ProcessName -NotContains "Svchost"`</span></span>

<span data-ttu-id="5a765-332">**Notcontains** は値のコレクションを参照し、指定された値と完全に一致する項目がコレクションに含まれていない場合は true になります。</span><span class="sxs-lookup"><span data-stu-id="5a765-332">**NotContains** refers to a collection of values and is true if the collection does not contain any items that are an exact match for the specified value.</span></span> <span data-ttu-id="5a765-333">入力が単一のオブジェクトの場合、PowerShell はそれを1つのオブジェクトのコレクションに変換します。</span><span class="sxs-lookup"><span data-stu-id="5a765-333">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="5a765-334">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-334">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotContainsSet
Aliases: INotContains

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-335">-NotIn</span><span class="sxs-lookup"><span data-stu-id="5a765-335">-NotIn</span></span>

<span data-ttu-id="5a765-336">プロパティ値が指定した値と完全に一致しない場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-336">Indicates that this cmdlet gets objects if the property value is not an exact match for any of the specified values.</span></span>

<span data-ttu-id="5a765-337">例: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="5a765-337">For example: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span></span>

<span data-ttu-id="5a765-338">**Value** の値が単一のオブジェクトの場合、PowerShell はそれを1つのオブジェクトのコレクションに変換します。</span><span class="sxs-lookup"><span data-stu-id="5a765-338">If the value of **Value** is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="5a765-339">オブジェクトのプロパティ値が配列の場合、PowerShell は参照の等価性を使用して一致を判定します。</span><span class="sxs-lookup"><span data-stu-id="5a765-339">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="5a765-340">`Where-Object`**プロパティ** の値と **値** の値がオブジェクトの同じインスタンスでない場合にのみ、オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="5a765-340">`Where-Object` returns the object only if the value of **Property** and any value of **Value** are not the same instance of an object.</span></span>

<span data-ttu-id="5a765-341">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-341">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotInSet
Aliases: INotIn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-342">-NotLike</span><span class="sxs-lookup"><span data-stu-id="5a765-342">-NotLike</span></span>

<span data-ttu-id="5a765-343">プロパティ値がワイルドカード文字を含む値と一致しない場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-343">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span>

<span data-ttu-id="5a765-344">例: `Get-Process | where ProcessName -NotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="5a765-344">For example: `Get-Process | where ProcessName -NotLike "*host"`</span></span>

<span data-ttu-id="5a765-345">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-345">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotLikeSet
Aliases: INotLike

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-346">-NotMatch</span><span class="sxs-lookup"><span data-stu-id="5a765-346">-NotMatch</span></span>

<span data-ttu-id="5a765-347">プロパティ値が指定した正規表現と一致しない場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-347">Indicates that this cmdlet gets objects when the property value does not match the specified regular expression.</span></span> <span data-ttu-id="5a765-348">入力がスカラーの場合は、一致した値が自動変数に保存され `$Matches` ます。</span><span class="sxs-lookup"><span data-stu-id="5a765-348">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="5a765-349">例: `Get-Process | where ProcessName -NotMatch "PowerShell"`</span><span class="sxs-lookup"><span data-stu-id="5a765-349">For example: `Get-Process | where ProcessName -NotMatch "PowerShell"`</span></span>

<span data-ttu-id="5a765-350">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-350">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotMatchSet
Aliases: INotMatch

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-351">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="5a765-351">-Property</span></span>

<span data-ttu-id="5a765-352">オブジェクトのプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5a765-352">Specifies the name of an object property.</span></span> <span data-ttu-id="5a765-353">パラメーター名 ( **Property**) は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5a765-353">The parameter name, **Property**, is optional.</span></span>

<span data-ttu-id="5a765-354">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-354">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: EqualSet, LessOrEqualSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, CaseSensitiveGreaterOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, CaseSensitiveNotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet, Not
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a765-355">-Value</span><span class="sxs-lookup"><span data-stu-id="5a765-355">-Value</span></span>

<span data-ttu-id="5a765-356">プロパティ値を指定します。</span><span class="sxs-lookup"><span data-stu-id="5a765-356">Specifies a property value.</span></span> <span data-ttu-id="5a765-357">パラメーター名 ( **Value**) は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5a765-357">The parameter name, **Value**, is optional.</span></span> <span data-ttu-id="5a765-358">このパラメーターでは、次の比較パラメーターと共にワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a765-358">This parameter accepts wildcard characters when used with the following comparison parameters:</span></span>

- <span data-ttu-id="5a765-359">**CLike**</span><span class="sxs-lookup"><span data-stu-id="5a765-359">**CLike**</span></span>
- <span data-ttu-id="5a765-360">**CNotLike**</span><span class="sxs-lookup"><span data-stu-id="5a765-360">**CNotLike**</span></span>
- <span data-ttu-id="5a765-361">**Like**</span><span class="sxs-lookup"><span data-stu-id="5a765-361">**Like**</span></span>
- <span data-ttu-id="5a765-362">**NotLike**</span><span class="sxs-lookup"><span data-stu-id="5a765-362">**NotLike**</span></span>

<span data-ttu-id="5a765-363">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-363">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: EqualSet, LessOrEqualSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, CaseSensitiveGreaterOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, CaseSensitiveNotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="5a765-364">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a765-364">CommonParameters</span></span>

<span data-ttu-id="5a765-365">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5a765-365">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5a765-366">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a765-366">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5a765-367">入力</span><span class="sxs-lookup"><span data-stu-id="5a765-367">INPUTS</span></span>

### <span data-ttu-id="5a765-368">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="5a765-368">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="5a765-369">パイプを使用してオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="5a765-369">You can pipe the objects to this cmdlet.</span></span>

## <span data-ttu-id="5a765-370">出力</span><span class="sxs-lookup"><span data-stu-id="5a765-370">OUTPUTS</span></span>

### <span data-ttu-id="5a765-371">Object</span><span class="sxs-lookup"><span data-stu-id="5a765-371">Object</span></span>

<span data-ttu-id="5a765-372">このコマンドレットは、入力オブジェクトセットから選択された項目を返します。</span><span class="sxs-lookup"><span data-stu-id="5a765-372">This cmdlet returns selected items from the input object set.</span></span>

## <span data-ttu-id="5a765-373">注</span><span class="sxs-lookup"><span data-stu-id="5a765-373">NOTES</span></span>

<span data-ttu-id="5a765-374">Windows PowerShell 4.0 以降では `Where` 、 `ForEach` コレクションで使用するためのメソッドとメソッドが追加されました。</span><span class="sxs-lookup"><span data-stu-id="5a765-374">Starting in Windows PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span>

<span data-ttu-id="5a765-375">これらの新しいメソッドの詳細については、こちらを参照してください [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="5a765-375">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

## <span data-ttu-id="5a765-376">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5a765-376">RELATED LINKS</span></span>

[<span data-ttu-id="5a765-377">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="5a765-377">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="5a765-378">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="5a765-378">ForEach-Object</span></span>](ForEach-Object.md)

[<span data-ttu-id="5a765-379">Group-Object</span><span class="sxs-lookup"><span data-stu-id="5a765-379">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="5a765-380">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="5a765-380">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="5a765-381">New-Object</span><span class="sxs-lookup"><span data-stu-id="5a765-381">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="5a765-382">Select-Object</span><span class="sxs-lookup"><span data-stu-id="5a765-382">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="5a765-383">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="5a765-383">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="5a765-384">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="5a765-384">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)

