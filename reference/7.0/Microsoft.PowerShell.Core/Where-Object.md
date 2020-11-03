---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Where-Object
ms.openlocfilehash: 0d9101c751e9ebc0b0c6fe80564bb76524de8bb6
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209827"
---
# <span data-ttu-id="3ab3c-103">Where-Object</span><span class="sxs-lookup"><span data-stu-id="3ab3c-103">Where-Object</span></span>

## <span data-ttu-id="3ab3c-104">概要</span><span class="sxs-lookup"><span data-stu-id="3ab3c-104">SYNOPSIS</span></span>
<span data-ttu-id="3ab3c-105">プロパティの値に基づいて、コレクションからオブジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-105">Selects objects from a collection based on their property values.</span></span>

## <span data-ttu-id="3ab3c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3ab3c-106">SYNTAX</span></span>

### <span data-ttu-id="3ab3c-107">EqualSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="3ab3c-107">EqualSet (Default)</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-EQ]
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-108">ScriptBlockSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-108">ScriptBlockSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-FilterScript] <ScriptBlock> [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-109">MatchSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-109">MatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Match
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-110">CaseSensitiveEqualSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-110">CaseSensitiveEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CEQ
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-111">NotEqualSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-111">NotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NE
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-112">CaseSensitiveNotEqualSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-112">CaseSensitiveNotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNE
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-113">GreaterThanSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-113">GreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GT
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-114">CaseSensitiveGreaterThanSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-114">CaseSensitiveGreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGT
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-115">設定しない</span><span class="sxs-lookup"><span data-stu-id="3ab3c-115">LessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LT
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-116">CaseSensitiveLessThanSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-116">CaseSensitiveLessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLT
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-117">GreaterOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-117">GreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GE
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-118">CaseSensitiveGreaterOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-118">CaseSensitiveGreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGE
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-119">LessOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-119">LessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LE
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-120">CaseSensitiveLessOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-120">CaseSensitiveLessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLE
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-121">数字セット</span><span class="sxs-lookup"><span data-stu-id="3ab3c-121">LikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Like
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-122">CaseSensitiveLikeSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-122">CaseSensitiveLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLike
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-123">Not記法セット</span><span class="sxs-lookup"><span data-stu-id="3ab3c-123">NotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotLike
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-124">CaseSensitiveNotLikeSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-124">CaseSensitiveNotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotLike
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-125">CaseSensitiveMatchSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-125">CaseSensitiveMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CMatch
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-126">NotMatchSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-126">NotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotMatch
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-127">CaseSensitiveNotMatchSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-127">CaseSensitiveNotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotMatch
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-128">集合集合</span><span class="sxs-lookup"><span data-stu-id="3ab3c-128">ContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Contains
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-129">CaseSensitiveContainsSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-129">CaseSensitiveContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CContains
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-130">Not集合セット</span><span class="sxs-lookup"><span data-stu-id="3ab3c-130">NotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotContains
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-131">CaseSensitiveNotContainsSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-131">CaseSensitiveNotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotContains
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-132">ペン</span><span class="sxs-lookup"><span data-stu-id="3ab3c-132">InSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -In
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-133">CaseSensitiveInSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-133">CaseSensitiveInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CIn
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-134">NotInSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-134">NotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotIn
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-135">CaseSensitiveNotInSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-135">CaseSensitiveNotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotIn
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-136">IsSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-136">IsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Is
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-137">IsNotSet</span><span class="sxs-lookup"><span data-stu-id="3ab3c-137">IsNotSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -IsNot
 [<CommonParameters>]
```

### <span data-ttu-id="3ab3c-138">Not</span><span class="sxs-lookup"><span data-stu-id="3ab3c-138">Not</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> -Not [<CommonParameters>]
```

## <span data-ttu-id="3ab3c-139">Description</span><span class="sxs-lookup"><span data-stu-id="3ab3c-139">DESCRIPTION</span></span>

<span data-ttu-id="3ab3c-140">コマンドレットでは、 `Where-Object` 渡されるオブジェクトのコレクションから、特定のプロパティ値を持つオブジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-140">The `Where-Object` cmdlet selects objects that have particular property values from the collection of objects that are passed to it.</span></span> <span data-ttu-id="3ab3c-141">たとえば、コマンドレットを使用して、特定の `Where-Object` 日付以降に作成されたファイル、特定の ID を持つイベント、または特定のバージョンの Windows を使用するコンピューターを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-141">For example, you can use the `Where-Object` cmdlet to select files that were created after a certain date, events with a particular ID, or computers that use a particular version of Windows.</span></span>

<span data-ttu-id="3ab3c-142">Windows PowerShell 3.0 以降では、コマンドを構築する方法は2つあり `Where-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-142">Starting in Windows PowerShell 3.0, there are two different ways to construct a `Where-Object` command.</span></span>

- <span data-ttu-id="3ab3c-143">**スクリプトブロック** 。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-143">**Script block** .</span></span> <span data-ttu-id="3ab3c-144">スクリプト ブロックを使用すると、プロパティ名、比較演算子、プロパティ値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-144">You can use a script block to specify the property name, a comparison operator, and a property value.</span></span> <span data-ttu-id="3ab3c-145">`Where-Object` スクリプトブロックステートメントが true であるすべてのオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-145">`Where-Object` returns all objects for which the script block statement is true.</span></span>

  <span data-ttu-id="3ab3c-146">たとえば、次のコマンドは、通常の優先度クラスのプロセスを取得します。つまり、"優先度" **クラス** プロパティの値が normal であるプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-146">For example, the following command gets processes in the Normal priority class, that is, processes where the value of the **PriorityClass** property equals Normal.</span></span>

  `Get-Process | Where-Object {$_.PriorityClass -eq "Normal"}`

  <span data-ttu-id="3ab3c-147">すべての PowerShell 比較演算子は、スクリプトブロック形式で有効です。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-147">All PowerShell comparison operators are valid in the script block format.</span></span> <span data-ttu-id="3ab3c-148">比較演算子の詳細については、「 [about_Comparison_Operators](./About/about_Comparison_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-148">For more information about comparison operators, see [about_Comparison_Operators](./About/about_Comparison_Operators.md).</span></span>

- <span data-ttu-id="3ab3c-149">**比較ステートメント** 。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-149">**Comparison statement** .</span></span> <span data-ttu-id="3ab3c-150">比較ステートメントを使用すると、自然言語のように記述することができます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-150">You can also write a comparison statement, which is much more like natural language.</span></span> <span data-ttu-id="3ab3c-151">比較ステートメントは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-151">Comparison statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="3ab3c-152">たとえば、次のコマンドは、priority クラスが Normal のプロセスも取得します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-152">For example, the following commands also get processes that have a priority class of Normal.</span></span> <span data-ttu-id="3ab3c-153">これらのコマンドは同等であり、置き換えて使用することができます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-153">These commands are equivalent and can be used interchangeably.</span></span>

  `Get-Process | Where-Object -Property PriorityClass -eq -Value "Normal"`

  `Get-Process | Where-Object PriorityClass -eq "Normal"`

  <span data-ttu-id="3ab3c-154">Windows PowerShell 3.0 以降では、 `Where-Object` コマンドのパラメーターとして比較演算子が追加さ `Where-Object` れています。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-154">Starting in Windows PowerShell 3.0, `Where-Object` adds comparison operators as parameters in a `Where-Object` command.</span></span> <span data-ttu-id="3ab3c-155">すべての演算子は、特に指定しない限り、大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-155">Unless specified, all operators are case-insensitive.</span></span> <span data-ttu-id="3ab3c-156">Windows PowerShell 3.0 より前では、PowerShell 言語の比較演算子は、スクリプトブロックでのみ使用できました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-156">Prior to Windows PowerShell 3.0, the comparison operators in the PowerShell language could be used only in script blocks.</span></span>

<span data-ttu-id="3ab3c-157">に1つの **プロパティ** を指定すると `Where-Object` 、プロパティの値はブール式として扱われます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-157">When you provide a single **Property** to `Where-Object`, the value of the property is treated as a boolean expression.</span></span> <span data-ttu-id="3ab3c-158">**Length** の値が0でない場合、式は **True** に評価されます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-158">When the value of **Length** is not zero, the expression evaluates to **True** .</span></span> <span data-ttu-id="3ab3c-159">例: `('hi', '', 'there') | Where-Object Length`</span><span class="sxs-lookup"><span data-stu-id="3ab3c-159">For example: `('hi', '', 'there') | Where-Object Length`</span></span>

<span data-ttu-id="3ab3c-160">前の例は、機能的には次のように相当します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-160">The previous example is functionally equivalent to:</span></span>

- `('hi', '', 'there') | Where-Object Length -GT 0`
- `('hi', '', 'there') | Where-Object {$_.Length -gt 0}`

## <span data-ttu-id="3ab3c-161">例</span><span class="sxs-lookup"><span data-stu-id="3ab3c-161">EXAMPLES</span></span>

### <span data-ttu-id="3ab3c-162">例 1: 停止したサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="3ab3c-162">Example 1: Get stopped services</span></span>

<span data-ttu-id="3ab3c-163">これらのコマンドは、現在停止しているすべてのサービスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-163">These commands get a list of all services that are currently stopped.</span></span> <span data-ttu-id="3ab3c-164">`$_`自動変数は、コマンドレットに渡される各オブジェクトを表し `Where-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-164">The `$_` automatic variable represents each object that is passed to the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="3ab3c-165">最初のコマンドは、スクリプトブロック形式を使用します。2番目のコマンドは、比較ステートメント形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-165">The first command uses the script block format, the second command uses the comparison statement format.</span></span> <span data-ttu-id="3ab3c-166">コマンドは等価であり、同じ意味で使用することができます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-166">The commands are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Stopped"}
Get-Service | where Status -eq "Stopped"
```

### <span data-ttu-id="3ab3c-167">例 2: ワーキングセットに基づいてプロセスを取得する</span><span class="sxs-lookup"><span data-stu-id="3ab3c-167">Example 2: Get processes based on working set</span></span>

<span data-ttu-id="3ab3c-168">これらのコマンドは、ワーキングセットが250メガバイト (KB) を超えるプロセスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-168">These commands list processes that have a working set greater than 250 megabytes (KB).</span></span> <span data-ttu-id="3ab3c-169">Scriptblock とステートメントの構文は同等であり、同じように使用できます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-169">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.WorkingSet -GT 250MB}
Get-Process | Where-Object WorkingSet -GT (250MB)
```

### <span data-ttu-id="3ab3c-170">例 3: プロセス名に基づいてプロセスを取得する</span><span class="sxs-lookup"><span data-stu-id="3ab3c-170">Example 3: Get processes based on process name</span></span>

<span data-ttu-id="3ab3c-171">これらのコマンドは、文字で始まる **ProcessName** プロパティ値を持つプロセスを取得し `p` ます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-171">These commands get the processes that have a **ProcessName** property value that begins with the letter `p`.</span></span> <span data-ttu-id="3ab3c-172">**Match** 演算子を使用すると、正規表現の一致を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-172">The **Match** operator lets you use regular expression matches.</span></span>

<span data-ttu-id="3ab3c-173">Scriptblock とステートメントの構文は同等であり、同じように使用できます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-173">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.ProcessName -Match "^p.*"}
Get-Process | Where-Object ProcessName -Match "^p.*"
```

### <span data-ttu-id="3ab3c-174">例 4: 比較ステートメントの形式を使用する</span><span class="sxs-lookup"><span data-stu-id="3ab3c-174">Example 4: Use the comparison statement format</span></span>

<span data-ttu-id="3ab3c-175">この例では、コマンドレットの新しい比較ステートメント形式を使用する方法を示し `Where-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-175">This example shows how to use the new comparison statement format of the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="3ab3c-176">最初のコマンドは、比較ステートメント形式を使用しています。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-176">The first command uses the comparison statement format.</span></span>
<span data-ttu-id="3ab3c-177">このコマンドでは、エイリアスは使用されず、すべてのパラメーターにパラメーター名が使用されています。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-177">In this command, no aliases are used and all parameters include the parameter name.</span></span>

<span data-ttu-id="3ab3c-178">2 番目のコマンドは、比較コマンドの形式をより自然に使用しています。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-178">The second command is the more natural use of the comparison command format.</span></span> <span data-ttu-id="3ab3c-179">`where`エイリアスはコマンドレット名の代わりに使用され、 `Where-Object` すべての省略可能なパラメーター名は省略されます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-179">The `where` alias is substituted for the `Where-Object` cmdlet name and all optional parameter names are omitted.</span></span>

```powershell
Get-Process | Where-Object -Property Handles -GE -Value 1000
Get-Process | where Handles -GE 1000
```

### <span data-ttu-id="3ab3c-180">例 5: プロパティに基づいてコマンドを取得する</span><span class="sxs-lookup"><span data-stu-id="3ab3c-180">Example 5: Get commands based on properties</span></span>

<span data-ttu-id="3ab3c-181">この例では、true または false の項目、または指定したプロパティの任意の値を持つ項目を返すコマンドを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-181">This example shows how to write commands that return items that are true or false or have any value for a specified property.</span></span> <span data-ttu-id="3ab3c-182">各例では、コマンドのスクリプトブロック形式と比較ステートメント形式の両方を示しています。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-182">Each example shows both the script block and comparison statement formats for the command.</span></span>

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

### <span data-ttu-id="3ab3c-183">例 6: 複数の条件を使用する</span><span class="sxs-lookup"><span data-stu-id="3ab3c-183">Example 6: Use multiple conditions</span></span>

```powershell
Get-Module -ListAvailable | where {($_.Name -notlike "Microsoft*" -and $_.Name -notlike "PS*") -and $_.HelpInfoUri}
```

<span data-ttu-id="3ab3c-184">この例では、 `Where-Object` 複数の条件を持つコマンドを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-184">This example shows how to create a `Where-Object` command with multiple conditions.</span></span>

<span data-ttu-id="3ab3c-185">このコマンドは、更新可能なヘルプ機能をサポートしている非コア モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-185">This command gets non-core modules that support the Updatable Help feature.</span></span> <span data-ttu-id="3ab3c-186">このコマンドは、コマンドレットの **ListAvailable** パラメーターを使用して、 `Get-Module` コンピューター上のすべてのモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-186">The command uses the **ListAvailable** parameter of the `Get-Module` cmdlet to get all modules on the computer.</span></span> <span data-ttu-id="3ab3c-187">パイプライン演算子 () は、 `|` モジュールを `Where-Object` コマンドレットに送信します。このコマンドレットは、名前が Microsoft または PS で始まらないモジュールを取得し、 **Helpinfouri** プロパティの値を設定します。これにより、モジュールの更新されたヘルプファイルの検索場所を PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-187">A pipeline operator (`|`) sends the modules to the `Where-Object` cmdlet, which gets modules whose names do not begin with Microsoft or PS, and have a value for the **HelpInfoURI** property, which tells PowerShell where to find updated help files for the module.</span></span> <span data-ttu-id="3ab3c-188">比較ステートメントは、 **and** 論理演算子によって結合されます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-188">The comparison statements are connected by the **And** logical operator.</span></span>

<span data-ttu-id="3ab3c-189">この例は、スクリプト ブロックのコマンド形式を使用しています。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-189">The example uses the script block command format.</span></span> <span data-ttu-id="3ab3c-190">論理演算子 ( **and** や **Or** など) は、スクリプトブロックでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-190">Logical operators, such as **And** and **Or** , are valid only in script blocks.</span></span> <span data-ttu-id="3ab3c-191">コマンドの比較ステートメント形式で使用することはできません `Where-Object` 。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-191">You cannot use them in the comparison statement format of a `Where-Object` command.</span></span>

- <span data-ttu-id="3ab3c-192">PowerShell の論理演算子の詳細については、「 [about_Logical_Operators](./About/about_logical_operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-192">For more information about PowerShell logical operators, see [about_Logical_Operators](./About/about_logical_operators.md).</span></span>
- <span data-ttu-id="3ab3c-193">更新可能なヘルプ機能の詳細については、「 [about_Updatable_Help](./About/about_Updatable_Help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-193">For more information about the Updatable Help feature, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>

## <span data-ttu-id="3ab3c-194">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3ab3c-194">PARAMETERS</span></span>

### <span data-ttu-id="3ab3c-195">-CContains</span><span class="sxs-lookup"><span data-stu-id="3ab3c-195">-CContains</span></span>

<span data-ttu-id="3ab3c-196">オブジェクトのプロパティ値が指定した値と完全に一致する場合に、このコマンドレットがコレクションからオブジェクトを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-196">Indicates that this cmdlet gets objects from a collection if the property value of the object is an exact match for the specified value.</span></span> <span data-ttu-id="3ab3c-197">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-197">This operation is case-sensitive.</span></span>

<span data-ttu-id="3ab3c-198">例: `Get-Process | where ProcessName -CContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="3ab3c-198">For example: `Get-Process | where ProcessName -CContains "svchost"`</span></span>

<span data-ttu-id="3ab3c-199">**Ccontains** は値のコレクションを参照し、指定された値と完全に一致する項目がコレクションに格納されている場合は true になります。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-199">**CContains** refers to a collection of values and is true if the collection contains an item that is an exact match for the specified value.</span></span> <span data-ttu-id="3ab3c-200">入力が単一のオブジェクトの場合、PowerShell はそれを1つのオブジェクトのコレクションに変換します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-200">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="3ab3c-201">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-201">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-202">-CEQ</span><span class="sxs-lookup"><span data-stu-id="3ab3c-202">-CEQ</span></span>

<span data-ttu-id="3ab3c-203">プロパティ値が指定した値と同じ場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-203">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>
<span data-ttu-id="3ab3c-204">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-204">This operation is case-sensitive.</span></span>

<span data-ttu-id="3ab3c-205">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-205">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-206">-CGE</span><span class="sxs-lookup"><span data-stu-id="3ab3c-206">-CGE</span></span>

<span data-ttu-id="3ab3c-207">プロパティ値が指定した値以上の場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-207">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span> <span data-ttu-id="3ab3c-208">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-208">This operation is case-sensitive.</span></span>

<span data-ttu-id="3ab3c-209">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-209">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-210">-CGT</span><span class="sxs-lookup"><span data-stu-id="3ab3c-210">-CGT</span></span>

<span data-ttu-id="3ab3c-211">プロパティ値が指定した値よりも大きい場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-211">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>
<span data-ttu-id="3ab3c-212">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-212">This operation is case-sensitive.</span></span>

<span data-ttu-id="3ab3c-213">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-213">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-214">-CIn</span><span class="sxs-lookup"><span data-stu-id="3ab3c-214">-CIn</span></span>

<span data-ttu-id="3ab3c-215">プロパティ値に指定した値が含まれている場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-215">Indicates that this cmdlet gets objects if the property value includes the specified value.</span></span> <span data-ttu-id="3ab3c-216">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-216">This operation is case-sensitive.</span></span>

<span data-ttu-id="3ab3c-217">例: `Get-Process | where -Value "svchost" -CIn ProcessName`</span><span class="sxs-lookup"><span data-stu-id="3ab3c-217">For example: `Get-Process | where -Value "svchost" -CIn ProcessName`</span></span>

<span data-ttu-id="3ab3c-218">**CIn** は **ccontains** に似ていますが、プロパティと値の位置が逆になる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-218">**CIn** resembles **CContains** , except that the property and value positions are reversed.</span></span> <span data-ttu-id="3ab3c-219">たとえば、次のステートメントはどちらも true です。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-219">For example, the following statements are both true.</span></span>

`"abc", "def" -CContains "abc"`

`"abc" -CIn "abc", "def"`

<span data-ttu-id="3ab3c-220">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-220">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-221">-CLE</span><span class="sxs-lookup"><span data-stu-id="3ab3c-221">-CLE</span></span>

<span data-ttu-id="3ab3c-222">プロパティ値が指定した値以下の場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-222">Indicates that this cmdlet gets objects if the property value is less-than or equal to the specified value.</span></span> <span data-ttu-id="3ab3c-223">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-223">This operation is case-sensitive.</span></span>

<span data-ttu-id="3ab3c-224">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-224">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-225">-CLike</span><span class="sxs-lookup"><span data-stu-id="3ab3c-225">-CLike</span></span>

<span data-ttu-id="3ab3c-226">プロパティ値がワイルドカード文字を含む値と一致する場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-226">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span> <span data-ttu-id="3ab3c-227">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-227">This operation is case-sensitive.</span></span>

<span data-ttu-id="3ab3c-228">例: `Get-Process | where ProcessName -CLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="3ab3c-228">For example: `Get-Process | where ProcessName -CLike "*host"`</span></span>

<span data-ttu-id="3ab3c-229">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-229">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-230">-CLT</span><span class="sxs-lookup"><span data-stu-id="3ab3c-230">-CLT</span></span>

<span data-ttu-id="3ab3c-231">プロパティ値が指定した値より小さい場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-231">Indicates that this cmdlet gets objects if the property value is less-than the specified value.</span></span> <span data-ttu-id="3ab3c-232">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-232">This operation is case-sensitive.</span></span>

<span data-ttu-id="3ab3c-233">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-233">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-234">-CMatch</span><span class="sxs-lookup"><span data-stu-id="3ab3c-234">-CMatch</span></span>

<span data-ttu-id="3ab3c-235">プロパティ値が指定した正規表現に一致する場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-235">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="3ab3c-236">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-236">This operation is case-sensitive.</span></span> <span data-ttu-id="3ab3c-237">入力がスカラーの場合は、一致した値が自動変数に保存され `$Matches` ます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-237">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="3ab3c-238">例: `Get-Process | where ProcessName -CMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="3ab3c-238">For example: `Get-Process | where ProcessName -CMatch "Shell"`</span></span>

<span data-ttu-id="3ab3c-239">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-239">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-240">-CNE</span><span class="sxs-lookup"><span data-stu-id="3ab3c-240">-CNE</span></span>

<span data-ttu-id="3ab3c-241">プロパティ値が指定した値と異なる場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-241">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>
<span data-ttu-id="3ab3c-242">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-242">This operation is case-sensitive.</span></span>

<span data-ttu-id="3ab3c-243">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-243">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-244">-CNotContains</span><span class="sxs-lookup"><span data-stu-id="3ab3c-244">-CNotContains</span></span>

<span data-ttu-id="3ab3c-245">オブジェクトのプロパティ値が指定した値と完全に一致しない場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-245">Indicates that this cmdlet gets objects if the property value of the object is not an exact match for the specified value.</span></span> <span data-ttu-id="3ab3c-246">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-246">This operation is case-sensitive.</span></span>

<span data-ttu-id="3ab3c-247">例: `Get-Process | where ProcessName -CNotContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="3ab3c-247">For example: `Get-Process | where ProcessName -CNotContains "svchost"`</span></span>

<span data-ttu-id="3ab3c-248">**Notcontains** と **cnotcontains** は値のコレクションを参照し、指定された値と完全に一致する項目がコレクションに含まれていない場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-248">**NotContains** and **CNotContains** refer to a collection of values and are true when the collection does not contains any items that are an exact match for the specified value.</span></span> <span data-ttu-id="3ab3c-249">入力が単一のオブジェクトの場合、PowerShell はそれを1つのオブジェクトのコレクションに変換します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-249">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="3ab3c-250">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-250">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-251">-CNotIn</span><span class="sxs-lookup"><span data-stu-id="3ab3c-251">-CNotIn</span></span>

<span data-ttu-id="3ab3c-252">プロパティ値が指定した値と完全に一致しない場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-252">Indicates that this cmdlet gets objects if the property value is not an exact match for the specified value.</span></span> <span data-ttu-id="3ab3c-253">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-253">This operation is case-sensitive.</span></span>

<span data-ttu-id="3ab3c-254">例: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="3ab3c-254">For example: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span></span>

<span data-ttu-id="3ab3c-255">**Notin** および **cnotin** 演算子は、プロパティと値の位置が逆になる点を除い **て、Notin** および **cnotin** と似ています。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-255">**NotIn** and **CNotIn** operators resemble **NotContains** and **CNotContains** , except that the property and value positions are reversed.</span></span> <span data-ttu-id="3ab3c-256">たとえば、次のステートメントは true です。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-256">For example, the following statements are true.</span></span>

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

### <span data-ttu-id="3ab3c-257">-CNotLike</span><span class="sxs-lookup"><span data-stu-id="3ab3c-257">-CNotLike</span></span>

<span data-ttu-id="3ab3c-258">プロパティ値がワイルドカード文字を含む値と一致しない場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-258">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span> <span data-ttu-id="3ab3c-259">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-259">This operation is case-sensitive.</span></span>

<span data-ttu-id="3ab3c-260">例: `Get-Process | where ProcessName -CNotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="3ab3c-260">For example: `Get-Process | where ProcessName -CNotLike "*host"`</span></span>

<span data-ttu-id="3ab3c-261">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-261">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-262">-CNotMatch</span><span class="sxs-lookup"><span data-stu-id="3ab3c-262">-CNotMatch</span></span>

<span data-ttu-id="3ab3c-263">プロパティ値が指定した正規表現と一致しない場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-263">Indicates that this cmdlet gets objects if the property value does not match the specified regular expression.</span></span> <span data-ttu-id="3ab3c-264">この操作では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-264">This operation is case-sensitive.</span></span> <span data-ttu-id="3ab3c-265">入力がスカラーの場合は、一致した値が自動変数に保存され `$Matches` ます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-265">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="3ab3c-266">例: `Get-Process | where ProcessName -CNotMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="3ab3c-266">For example: `Get-Process | where ProcessName -CNotMatch "Shell"`</span></span>

<span data-ttu-id="3ab3c-267">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-267">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-268">-Contains</span><span class="sxs-lookup"><span data-stu-id="3ab3c-268">-Contains</span></span>

<span data-ttu-id="3ab3c-269">オブジェクトのプロパティ値の項目が指定した値と完全に一致する場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-269">Indicates that this cmdlet gets objects if any item in the property value of the object is an exact match for the specified value.</span></span>

<span data-ttu-id="3ab3c-270">例: `Get-Process | where ProcessName -Contains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="3ab3c-270">For example: `Get-Process | where ProcessName -Contains "Svchost"`</span></span>

<span data-ttu-id="3ab3c-271">プロパティ値に1つのオブジェクトが含まれている場合、PowerShell はそれを1つのオブジェクトのコレクションに変換します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-271">If the property value contains a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="3ab3c-272">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-272">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-273">-EQ</span><span class="sxs-lookup"><span data-stu-id="3ab3c-273">-EQ</span></span>

<span data-ttu-id="3ab3c-274">プロパティ値が指定した値と同じ場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-274">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>

<span data-ttu-id="3ab3c-275">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-275">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-276">-FilterScript</span><span class="sxs-lookup"><span data-stu-id="3ab3c-276">-FilterScript</span></span>

<span data-ttu-id="3ab3c-277">オブジェクトをフィルター処理するために使用するスクリプト ブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-277">Specifies the script block that is used to filter the objects.</span></span> <span data-ttu-id="3ab3c-278">スクリプトブロックを中かっこ () で囲み `{}` ます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-278">Enclose the script block in braces (`{}`).</span></span>

<span data-ttu-id="3ab3c-279">パラメーター名 **Filterscript** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-279">The parameter name, **FilterScript** , is optional.</span></span>

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

### <span data-ttu-id="3ab3c-280">-GE</span><span class="sxs-lookup"><span data-stu-id="3ab3c-280">-GE</span></span>

<span data-ttu-id="3ab3c-281">プロパティ値が指定した値以上の場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-281">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span>

<span data-ttu-id="3ab3c-282">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-282">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-283">-GT</span><span class="sxs-lookup"><span data-stu-id="3ab3c-283">-GT</span></span>

<span data-ttu-id="3ab3c-284">プロパティ値が指定した値よりも大きい場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-284">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>

<span data-ttu-id="3ab3c-285">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-285">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-286">-In</span><span class="sxs-lookup"><span data-stu-id="3ab3c-286">-In</span></span>

<span data-ttu-id="3ab3c-287">プロパティ値が指定した値と一致する場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-287">Indicates that this cmdlet gets objects if the property value matches any of the specified values.</span></span>
<span data-ttu-id="3ab3c-288">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-288">For example:</span></span>

`Get-Process | where -Property ProcessName -in -Value "Svchost", "TaskHost", "WsmProvHost"`

<span data-ttu-id="3ab3c-289">**Value** パラメーターの値が単一のオブジェクトの場合、PowerShell はそれを1つのオブジェクトのコレクションに変換します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-289">If the value of the **Value** parameter is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="3ab3c-290">オブジェクトのプロパティ値が配列の場合、PowerShell は参照の等価性を使用して一致を判定します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-290">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="3ab3c-291">`Where-Object`**Property** パラメーターの値と **値** の値がオブジェクトの同じインスタンスである場合にのみ、オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-291">`Where-Object` returns the object only if the value of the **Property** parameter and any value of **Value** are the same instance of an object.</span></span>

<span data-ttu-id="3ab3c-292">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-292">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-293">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3ab3c-293">-InputObject</span></span>

<span data-ttu-id="3ab3c-294">フィルター処理されるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-294">Specifies the objects to be filtered.</span></span> <span data-ttu-id="3ab3c-295">パイプを使用してオブジェクトをにパイプすることもでき `Where-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-295">You can also pipe the objects to `Where-Object`.</span></span>

<span data-ttu-id="3ab3c-296">で **inputobject** パラメーターを使用すると、 `Where-Object` コマンドの結果をにパイプするのではなく、 `Where-Object` **inputobject** 値が1つのオブジェクトとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-296">When you use the **InputObject** parameter with `Where-Object`, instead of piping command results to `Where-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="3ab3c-297">これは、値が、などのコマンドの結果であるコレクションである場合にも当てはまり `-InputObject (Get-Process)` ます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-297">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span> <span data-ttu-id="3ab3c-298">**InputObject** は配列またはオブジェクトのコレクションから個々のプロパティを返すことができないため、を使用し `Where-Object` て、定義されたプロパティに特定の値を持つオブジェクトのコレクションをフィルター処理する場合は、 `Where-Object` このトピックの例に示すように、パイプラインでを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-298">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that, if you use `Where-Object` to filter a collection of objects for those objects that have specific values in defined properties, you use `Where-Object` in the pipeline, as shown in the examples in this topic.</span></span>

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

### <span data-ttu-id="3ab3c-299">-が</span><span class="sxs-lookup"><span data-stu-id="3ab3c-299">-Is</span></span>

<span data-ttu-id="3ab3c-300">プロパティ値が指定された .NET 型のインスタンスの場合に、このコマンドレットがオブジェクトを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-300">Indicates that this cmdlet gets objects if the property value is an instance of the specified .NET type.</span></span> <span data-ttu-id="3ab3c-301">型名を角かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-301">Enclose the type name in square brackets.</span></span>

<span data-ttu-id="3ab3c-302">たとえば、`Get-Process | where StartTime -Is [DateTime]` のように指定します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-302">For example, `Get-Process | where StartTime -Is [DateTime]`</span></span>

<span data-ttu-id="3ab3c-303">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-303">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-304">-IsNot</span><span class="sxs-lookup"><span data-stu-id="3ab3c-304">-IsNot</span></span>

<span data-ttu-id="3ab3c-305">プロパティ値が指定した .NET 型のインスタンスでない場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-305">Indicates that this cmdlet gets objects if the property value is not an instance of the specified .NET type.</span></span>

<span data-ttu-id="3ab3c-306">たとえば、`Get-Process | where StartTime -IsNot [DateTime]` のように指定します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-306">For example, `Get-Process | where StartTime -IsNot [DateTime]`</span></span>

<span data-ttu-id="3ab3c-307">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-307">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-308">-LE</span><span class="sxs-lookup"><span data-stu-id="3ab3c-308">-LE</span></span>

<span data-ttu-id="3ab3c-309">プロパティ値が指定した値以下の場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-309">Indicates that this cmdlet gets objects if the property value is less than or equal to the specified value.</span></span>

<span data-ttu-id="3ab3c-310">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-310">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-311">-Like</span><span class="sxs-lookup"><span data-stu-id="3ab3c-311">-Like</span></span>

<span data-ttu-id="3ab3c-312">プロパティ値がワイルドカード文字を含む値と一致する場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-312">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span>

<span data-ttu-id="3ab3c-313">例: `Get-Process | where ProcessName -Like "*host"`</span><span class="sxs-lookup"><span data-stu-id="3ab3c-313">For example: `Get-Process | where ProcessName -Like "*host"`</span></span>

<span data-ttu-id="3ab3c-314">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-314">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-315">-LT</span><span class="sxs-lookup"><span data-stu-id="3ab3c-315">-LT</span></span>

<span data-ttu-id="3ab3c-316">プロパティ値が指定した値よりも小さい場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-316">Indicates that this cmdlet gets objects if the property value is less than the specified value.</span></span>

<span data-ttu-id="3ab3c-317">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-317">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-318">-一致</span><span class="sxs-lookup"><span data-stu-id="3ab3c-318">-Match</span></span>

<span data-ttu-id="3ab3c-319">プロパティ値が指定した正規表現に一致する場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-319">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="3ab3c-320">入力がスカラーの場合は、一致した値が自動変数に保存され `$Matches` ます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-320">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="3ab3c-321">例: `Get-Process | where ProcessName -Match "shell"`</span><span class="sxs-lookup"><span data-stu-id="3ab3c-321">For example: `Get-Process | where ProcessName -Match "shell"`</span></span>

<span data-ttu-id="3ab3c-322">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-322">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-323">-NE</span><span class="sxs-lookup"><span data-stu-id="3ab3c-323">-NE</span></span>

<span data-ttu-id="3ab3c-324">プロパティ値が指定した値と異なる場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-324">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>

<span data-ttu-id="3ab3c-325">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-325">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-326">-Not</span><span class="sxs-lookup"><span data-stu-id="3ab3c-326">-Not</span></span>

<span data-ttu-id="3ab3c-327">プロパティが存在しない場合、または値が null または false の場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-327">Indicates that this cmdlet gets objects if the property does not exist or has a value of null or false.</span></span>

<span data-ttu-id="3ab3c-328">例: `Get-Service | where -Not "DependentServices"`</span><span class="sxs-lookup"><span data-stu-id="3ab3c-328">For example: `Get-Service | where -Not "DependentServices"`</span></span>

<span data-ttu-id="3ab3c-329">このパラメーターは、Windows PowerShell 6.1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-329">This parameter was introduced in Windows PowerShell 6.1.</span></span>

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

### <span data-ttu-id="3ab3c-330">-NotContains</span><span class="sxs-lookup"><span data-stu-id="3ab3c-330">-NotContains</span></span>

<span data-ttu-id="3ab3c-331">プロパティ値の項目が指定した値と完全に一致しない場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-331">Indicates that this cmdlet gets objects if none of the items in the property value is an exact match for the specified value.</span></span>

<span data-ttu-id="3ab3c-332">例: `Get-Process | where ProcessName -NotContains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="3ab3c-332">For example: `Get-Process | where ProcessName -NotContains "Svchost"`</span></span>

<span data-ttu-id="3ab3c-333">**Notcontains** は値のコレクションを参照し、指定された値と完全に一致する項目がコレクションに含まれていない場合は true になります。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-333">**NotContains** refers to a collection of values and is true if the collection does not contain any items that are an exact match for the specified value.</span></span> <span data-ttu-id="3ab3c-334">入力が単一のオブジェクトの場合、PowerShell はそれを1つのオブジェクトのコレクションに変換します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-334">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="3ab3c-335">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-335">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-336">-NotIn</span><span class="sxs-lookup"><span data-stu-id="3ab3c-336">-NotIn</span></span>

<span data-ttu-id="3ab3c-337">プロパティ値が指定した値と完全に一致しない場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-337">Indicates that this cmdlet gets objects if the property value is not an exact match for any of the specified values.</span></span>

<span data-ttu-id="3ab3c-338">例: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="3ab3c-338">For example: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span></span>

<span data-ttu-id="3ab3c-339">**Value** の値が単一のオブジェクトの場合、PowerShell はそれを1つのオブジェクトのコレクションに変換します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-339">If the value of **Value** is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="3ab3c-340">オブジェクトのプロパティ値が配列の場合、PowerShell は参照の等価性を使用して一致を判定します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-340">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="3ab3c-341">`Where-Object`**プロパティ** の値と **値** の値がオブジェクトの同じインスタンスでない場合にのみ、オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-341">`Where-Object` returns the object only if the value of **Property** and any value of **Value** are not the same instance of an object.</span></span>

<span data-ttu-id="3ab3c-342">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-342">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-343">-NotLike</span><span class="sxs-lookup"><span data-stu-id="3ab3c-343">-NotLike</span></span>

<span data-ttu-id="3ab3c-344">プロパティ値がワイルドカード文字を含む値と一致しない場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-344">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span>

<span data-ttu-id="3ab3c-345">例: `Get-Process | where ProcessName -NotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="3ab3c-345">For example: `Get-Process | where ProcessName -NotLike "*host"`</span></span>

<span data-ttu-id="3ab3c-346">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-346">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-347">-NotMatch</span><span class="sxs-lookup"><span data-stu-id="3ab3c-347">-NotMatch</span></span>

<span data-ttu-id="3ab3c-348">プロパティ値が指定した正規表現と一致しない場合に、このコマンドレットによってオブジェクトが取得されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-348">Indicates that this cmdlet gets objects when the property value does not match the specified regular expression.</span></span> <span data-ttu-id="3ab3c-349">入力がスカラーの場合は、一致した値が自動変数に保存され `$Matches` ます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-349">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="3ab3c-350">例: `Get-Process | where ProcessName -NotMatch "PowerShell"`</span><span class="sxs-lookup"><span data-stu-id="3ab3c-350">For example: `Get-Process | where ProcessName -NotMatch "PowerShell"`</span></span>

<span data-ttu-id="3ab3c-351">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-351">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3ab3c-352">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="3ab3c-352">-Property</span></span>

<span data-ttu-id="3ab3c-353">オブジェクトのプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-353">Specifies the name of an object property.</span></span> <span data-ttu-id="3ab3c-354">パラメーター名 ( **Property** ) は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-354">The parameter name, **Property** , is optional.</span></span>

<span data-ttu-id="3ab3c-355">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-355">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: EqualSet, CaseSensitiveNotLikeSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, CaseSensitiveGreaterOrEqualSet, LessOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet, Not
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3ab3c-356">-Value</span><span class="sxs-lookup"><span data-stu-id="3ab3c-356">-Value</span></span>

<span data-ttu-id="3ab3c-357">プロパティ値を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-357">Specifies a property value.</span></span> <span data-ttu-id="3ab3c-358">パラメーター名 ( **Value** ) は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-358">The parameter name, **Value** , is optional.</span></span> <span data-ttu-id="3ab3c-359">このパラメーターでは、次の比較パラメーターと共にワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-359">This parameter accepts wildcard characters when used with the following comparison parameters:</span></span>

- <span data-ttu-id="3ab3c-360">**CLike**</span><span class="sxs-lookup"><span data-stu-id="3ab3c-360">**CLike**</span></span>
- <span data-ttu-id="3ab3c-361">**CNotLike**</span><span class="sxs-lookup"><span data-stu-id="3ab3c-361">**CNotLike**</span></span>
- <span data-ttu-id="3ab3c-362">**Like**</span><span class="sxs-lookup"><span data-stu-id="3ab3c-362">**Like**</span></span>
- <span data-ttu-id="3ab3c-363">**NotLike**</span><span class="sxs-lookup"><span data-stu-id="3ab3c-363">**NotLike**</span></span>

<span data-ttu-id="3ab3c-364">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-364">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Object
Parameter Sets: EqualSet, CaseSensitiveGreaterOrEqualSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, LessOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, CaseSensitiveNotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="3ab3c-365">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="3ab3c-365">CommonParameters</span></span>

<span data-ttu-id="3ab3c-366">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-366">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3ab3c-367">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-367">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3ab3c-368">入力</span><span class="sxs-lookup"><span data-stu-id="3ab3c-368">INPUTS</span></span>

### <span data-ttu-id="3ab3c-369">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="3ab3c-369">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="3ab3c-370">パイプを使用してオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-370">You can pipe the objects to this cmdlet.</span></span>

## <span data-ttu-id="3ab3c-371">出力</span><span class="sxs-lookup"><span data-stu-id="3ab3c-371">OUTPUTS</span></span>

### <span data-ttu-id="3ab3c-372">Object</span><span class="sxs-lookup"><span data-stu-id="3ab3c-372">Object</span></span>

<span data-ttu-id="3ab3c-373">このコマンドレットは、入力オブジェクトセットから選択された項目を返します。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-373">This cmdlet returns selected items from the input object set.</span></span>

## <span data-ttu-id="3ab3c-374">注</span><span class="sxs-lookup"><span data-stu-id="3ab3c-374">NOTES</span></span>

<span data-ttu-id="3ab3c-375">Windows PowerShell 4.0 以降では `Where` 、 `ForEach` コレクションで使用するためのメソッドとメソッドが追加されました。</span><span class="sxs-lookup"><span data-stu-id="3ab3c-375">Starting in Windows PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span>

<span data-ttu-id="3ab3c-376">これらの新しいメソッドの詳細については、こちらを参照してください [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="3ab3c-376">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

## <span data-ttu-id="3ab3c-377">関連リンク</span><span class="sxs-lookup"><span data-stu-id="3ab3c-377">RELATED LINKS</span></span>

[<span data-ttu-id="3ab3c-378">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="3ab3c-378">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="3ab3c-379">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="3ab3c-379">ForEach-Object</span></span>](ForEach-Object.md)

[<span data-ttu-id="3ab3c-380">Group-Object</span><span class="sxs-lookup"><span data-stu-id="3ab3c-380">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="3ab3c-381">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="3ab3c-381">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="3ab3c-382">New-Object</span><span class="sxs-lookup"><span data-stu-id="3ab3c-382">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="3ab3c-383">Select-Object</span><span class="sxs-lookup"><span data-stu-id="3ab3c-383">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="3ab3c-384">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="3ab3c-384">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="3ab3c-385">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="3ab3c-385">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)