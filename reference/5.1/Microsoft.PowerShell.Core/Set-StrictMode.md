---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-strictmode?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-StrictMode
ms.openlocfilehash: e44cad2bab6c81de67cdd0902af5172438efa19e
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388503"
---
# <span data-ttu-id="4dc55-103">Set-StrictMode</span><span class="sxs-lookup"><span data-stu-id="4dc55-103">Set-StrictMode</span></span>

## <span data-ttu-id="4dc55-104">概要</span><span class="sxs-lookup"><span data-stu-id="4dc55-104">SYNOPSIS</span></span>
<span data-ttu-id="4dc55-105">式、スクリプト、およびスクリプト ブロックでのコーディング規則を確立し、適用します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-105">Establishes and enforces coding rules in expressions, scripts, and script blocks.</span></span>

## <span data-ttu-id="4dc55-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4dc55-106">SYNTAX</span></span>

### <span data-ttu-id="4dc55-107">Version (既定値)</span><span class="sxs-lookup"><span data-stu-id="4dc55-107">Version (Default)</span></span>

```
Set-StrictMode -Version <Version> [<CommonParameters>]
```

### <span data-ttu-id="4dc55-108">オフ</span><span class="sxs-lookup"><span data-stu-id="4dc55-108">Off</span></span>

```
Set-StrictMode [-Off] [<CommonParameters>]
```

## <span data-ttu-id="4dc55-109">Description</span><span class="sxs-lookup"><span data-stu-id="4dc55-109">DESCRIPTION</span></span>

<span data-ttu-id="4dc55-110">`Set-StrictMode`このコマンドレットは、現在のスコープとすべての子スコープの厳格モードを構成し、オンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="4dc55-110">The `Set-StrictMode` cmdlet configures strict mode for the current scope and all child scopes, and turns it on and off.</span></span> <span data-ttu-id="4dc55-111">Strict モードがオンの場合、式、スクリプト、またはスクリプトブロックの内容が基本的なベストプラクティスのコーディング規則に違反すると、PowerShell によって終了エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="4dc55-111">When strict mode is on, PowerShell generates a terminating error when the content of an expression, script, or script block violates basic best-practice coding rules.</span></span>

<span data-ttu-id="4dc55-112">**バージョン** パラメーターを使用して、適用するコーディング規則を決定します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-112">Use the **Version** parameter to determine which coding rules are enforced.</span></span>

<span data-ttu-id="4dc55-113">`Set-PSDebug -Strict` コマンドレットは、グローバルスコープに対して strict モードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4dc55-113">`Set-PSDebug -Strict` cmdlet turns on strict mode for the global scope.</span></span> <span data-ttu-id="4dc55-114">`Set-StrictMode` は、現在のスコープとその子スコープにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-114">`Set-StrictMode` affects only the current scope and its child scopes.</span></span> <span data-ttu-id="4dc55-115">このため、スクリプトまたは関数で使用して、グローバルスコープから継承された設定をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="4dc55-115">Therefore, you can use it in a script or function to override the setting inherited from the global scope.</span></span>

<span data-ttu-id="4dc55-116">`Set-StrictMode`がオフの場合、PowerShell には次の動作があります。</span><span class="sxs-lookup"><span data-stu-id="4dc55-116">When `Set-StrictMode` is off, PowerShell has the following behaviors:</span></span>

- <span data-ttu-id="4dc55-117">初期化されていない変数は `$Null` 、型に応じて 0 (ゼロ) またはの値を持つと見なされます。</span><span class="sxs-lookup"><span data-stu-id="4dc55-117">Uninitialized variables are assumed to have a value of 0 (zero) or `$Null`, depending on type</span></span>
- <span data-ttu-id="4dc55-118">存在しないプロパティへの参照はを返します `$Null`</span><span class="sxs-lookup"><span data-stu-id="4dc55-118">References to non-existent properties return `$Null`</span></span>
- <span data-ttu-id="4dc55-119">不適切な関数構文の結果は、エラー条件によって異なります。</span><span class="sxs-lookup"><span data-stu-id="4dc55-119">Results of improper function syntax vary with the error conditions</span></span>
- <span data-ttu-id="4dc55-120">配列内の無効なインデックスを使用して値を取得しようとすると、が返されます。 `$Null`</span><span class="sxs-lookup"><span data-stu-id="4dc55-120">Attempting to retrieve a value using an invalid index in an array returns `$Null`</span></span>

## <span data-ttu-id="4dc55-121">例</span><span class="sxs-lookup"><span data-stu-id="4dc55-121">EXAMPLES</span></span>

### <span data-ttu-id="4dc55-122">例 1: strict モードをバージョン1.0 として有効にする</span><span class="sxs-lookup"><span data-stu-id="4dc55-122">Example 1: Turn on strict mode as version 1.0</span></span>

```powershell
# Strict mode is off by default.
$a -gt 5
```

```Output
False
```

```powershell
Set-StrictMode -Version 1.0
$a -gt 5
```

```Output
The variable $a cannot be retrieved because it has not been set yet.

At line:1 char:3
+ $a <<<<  -gt 5
+ CategoryInfo          : InvalidOperation: (a:Token) [], RuntimeException
+ FullyQualifiedErrorId : VariableIsUndefined
```

<span data-ttu-id="4dc55-123">Strict モードがバージョン1.0 に設定されている場合、初期化されていない変数を参照しようとすると失敗します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-123">With strict mode set to version 1.0, attempts to reference variables that are not initialized fail.</span></span>

### <span data-ttu-id="4dc55-124">例 2: strict モードをバージョン2.0 として有効にする</span><span class="sxs-lookup"><span data-stu-id="4dc55-124">Example 2: Turn on strict mode as version 2.0</span></span>

```powershell
# Strict mode is off by default.
function add ($a, $b) {
    '$a = ' + $a
    '$b = ' + $b
    '$a+$b = ' + ($a + $b)
}
add 3 4
```

```Output
$a = 3
$b = 4
$a+$b = 7
```

```powershell
add(3,4)
```

```Output
$a = 3 4
$b =
$a+$b = 3 4
```

```powershell
Set-StrictMode -Version 2.0
add(3,4)
```

```Output
The function or command was called like a method. Parameters should be separated by spaces,
as described in 'Get-Help about_Parameter.'
At line:1 char:4
+ add <<<< (3,4)
+ CategoryInfo          : InvalidOperation: (:) [], RuntimeException
+ FullyQualifiedErrorId : StrictModeFunctionCallWithParens
```

```powershell
Set-StrictMode -Off
$string = "This is a string."
$null -eq $string.Month
```

```Output
True
```

```powershell
Set-StrictMode -Version 2.0
$string = "This is a string."
$null -eq $string.Month
```

```Output
Property 'Month' cannot be found on this object; make sure it exists.
At line:1 char:9
+ $string. <<<< month
+ CategoryInfo          : InvalidOperation: (.:OperatorToken) [], RuntimeException
+ FullyQualifiedErrorId : PropertyNotFoundStrict
```

<span data-ttu-id="4dc55-125">このコマンドは、の厳格モードをオンにし、バージョン2.0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-125">This command turns strict mode on and sets it to version 2.0.</span></span> <span data-ttu-id="4dc55-126">その結果、関数呼び出しにかっことコンマを使用しているか、初期化されていない変数または存在しないプロパティを参照するメソッド構文を使用すると、PowerShell はエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-126">As a result, PowerShell returns an error if you use method syntax, which uses parentheses and commas, for a function call or reference uninitialized variables or non-existent properties.</span></span>

<span data-ttu-id="4dc55-127">サンプル出力は、バージョン 2.0 strict モードの効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="4dc55-127">The sample output shows the effect of version 2.0 strict mode.</span></span>

<span data-ttu-id="4dc55-128">バージョン 2.0 の厳格モードを使用しない場合、値 "(3,4)" は、何も追加されない 1 つの配列オブジェクトとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="4dc55-128">Without version 2.0 strict mode, the "(3,4)" value is interpreted as a single array object to which nothing is added.</span></span> <span data-ttu-id="4dc55-129">バージョン 2.0 strict モードを使用すると、2つの値を送信するための正しくない構文として正しく解釈されます。</span><span class="sxs-lookup"><span data-stu-id="4dc55-129">By using version 2.0 strict mode, it is correctly interpreted as faulty syntax for submitting two values.</span></span>

<span data-ttu-id="4dc55-130">バージョン2.0 を使用しない場合、文字列の存在しない **Month** プロパティへの参照はのみを返し `$Null` ます。</span><span class="sxs-lookup"><span data-stu-id="4dc55-130">Without version 2.0, the reference to the non-existent **Month** property of a string returns only `$Null`.</span></span> <span data-ttu-id="4dc55-131">バージョン2.0 を使用すると、参照エラーとして正しく解釈されます。</span><span class="sxs-lookup"><span data-stu-id="4dc55-131">By using version 2.0, it is interpreted correctly as a reference error.</span></span>

### <span data-ttu-id="4dc55-132">例 3: strict モードをバージョン3.0 として有効にする</span><span class="sxs-lookup"><span data-stu-id="4dc55-132">Example 3: Turn on strict mode as version 3.0</span></span>

<span data-ttu-id="4dc55-133">Strict モードが **Off** に設定されている場合、無効または範囲外のインデックスの結果は null 値を返します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-133">With strict mode set to **Off** , invalid or out of bounds indexes result return null values.</span></span>

```powershell
# Strict mode is off by default.
$a = @(1)
$null -eq $a[2]
$null -eq $a['abc']
```

```Output
True
True
```

```powershell
Set-StrictMode -Version 3
$a = @(1)
$null -eq $a[2]
$null -eq $a['abc']
```

```Output
Index was outside the bounds of the array.
At line:1 char:1
+ $null -eq $a[2]
+ ~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (:) [], IndexOutOfRangeException
    + FullyQualifiedErrorId : System.IndexOutOfRangeException

Cannot convert value "abc" to type "System.Int32". Error: "Input string was not in a correct format."
At line:1 char:1
+ $null -eq $a['abc']
+ ~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [], RuntimeException
    + FullyQualifiedErrorId : InvalidCastFromStringToInteger
```

<span data-ttu-id="4dc55-134">Strict モードがバージョン3以上に設定されている場合、インデックスが無効または範囲外の場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-134">With strict mode set to version 3 or higher, invalid or out of bounds indexes result in errors.</span></span>

## <span data-ttu-id="4dc55-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4dc55-135">PARAMETERS</span></span>

### <span data-ttu-id="4dc55-136">-Off</span><span class="sxs-lookup"><span data-stu-id="4dc55-136">-Off</span></span>

<span data-ttu-id="4dc55-137">このコマンドレットが、現在のスコープとすべての子スコープの厳格モードをオフにすることを示します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-137">Indicates that this cmdlet turns strict mode off for the current scope and all child scopes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Off
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dc55-138">-Version</span><span class="sxs-lookup"><span data-stu-id="4dc55-138">-Version</span></span>

<span data-ttu-id="4dc55-139">厳格モードでエラーとなる条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-139">Specifies the conditions that cause an error in strict mode.</span></span> <span data-ttu-id="4dc55-140">このパラメーターは、任意の有効な PowerShell バージョン番号を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4dc55-140">This parameter accepts any valid PowerShell version number.</span></span> <span data-ttu-id="4dc55-141">3より大きい数値は、 **最新** のものとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="4dc55-141">Any number higher than 3 is treated as **Latest**.</span></span>

<span data-ttu-id="4dc55-142">このパラメーターの有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4dc55-142">The effective values for this parameter are:</span></span>

- <span data-ttu-id="4dc55-143">1.0</span><span class="sxs-lookup"><span data-stu-id="4dc55-143">1.0</span></span>
  - <span data-ttu-id="4dc55-144">初期化されていない変数への参照を禁止します (文字列の初期化されていない変数を除く)</span><span class="sxs-lookup"><span data-stu-id="4dc55-144">Prohibits references to uninitialized variables, except for uninitialized variables in strings.</span></span>
- <span data-ttu-id="4dc55-145">2.0</span><span class="sxs-lookup"><span data-stu-id="4dc55-145">2.0</span></span>
  - <span data-ttu-id="4dc55-146">初期化されていない変数への参照を禁止します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-146">Prohibits references to uninitialized variables.</span></span> <span data-ttu-id="4dc55-147">これには、初期化されていない変数が文字列に含まれます。</span><span class="sxs-lookup"><span data-stu-id="4dc55-147">This includes uninitialized variables in strings.</span></span>
  - <span data-ttu-id="4dc55-148">オブジェクトの存在しないプロパティへの参照を禁止します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-148">Prohibits references to non-existent properties of an object.</span></span>
  - <span data-ttu-id="4dc55-149">メソッドを呼び出すための構文を使用する関数呼び出しを禁止します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-149">Prohibits function calls that use the syntax for calling methods.</span></span>
- <span data-ttu-id="4dc55-150">3.0</span><span class="sxs-lookup"><span data-stu-id="4dc55-150">3.0</span></span>
  - <span data-ttu-id="4dc55-151">初期化されていない変数への参照を禁止します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-151">Prohibits references to uninitialized variables.</span></span> <span data-ttu-id="4dc55-152">これには、初期化されていない変数が文字列に含まれます。</span><span class="sxs-lookup"><span data-stu-id="4dc55-152">This includes uninitialized variables in strings.</span></span>
  - <span data-ttu-id="4dc55-153">オブジェクトの存在しないプロパティへの参照を禁止します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-153">Prohibits references to non-existent properties of an object.</span></span>
  - <span data-ttu-id="4dc55-154">メソッドを呼び出すための構文を使用する関数呼び出しを禁止します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-154">Prohibits function calls that use the syntax for calling methods.</span></span>
  - <span data-ttu-id="4dc55-155">範囲外または解決できない配列インデックスを禁止します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-155">Prohibit out of bounds or unresolvable array indexes.</span></span>
- <span data-ttu-id="4dc55-156">最新</span><span class="sxs-lookup"><span data-stu-id="4dc55-156">Latest</span></span>
  - <span data-ttu-id="4dc55-157">使用可能な最新バージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-157">Selects the latest version available.</span></span> <span data-ttu-id="4dc55-158">最新バージョンは最も厳格です。</span><span class="sxs-lookup"><span data-stu-id="4dc55-158">The latest version is the most strict.</span></span> <span data-ttu-id="4dc55-159">新しいバージョンを PowerShell に追加した場合でも、スクリプトが使用可能な最も厳格なバージョンを使用するようにするには、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-159">Use this value to make sure that scripts use the strictest available version, even when new versions are added to PowerShell.</span></span>

> [!CAUTION]
> <span data-ttu-id="4dc55-160">スクリプトで **最新\*\*\*\*バージョン** を使用します。</span><span class="sxs-lookup"><span data-stu-id="4dc55-160">Using a **Version** of **Latest** in scripts.</span></span> <span data-ttu-id="4dc55-161">**最新** のの意味は、PowerShell の新しいリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4dc55-161">The meaning of **Latest** can change in new releases of PowerShell.</span></span> <span data-ttu-id="4dc55-162">そのため、を使用する古いバージョンの PowerShell 用に記述 `Set-StrictMode -Version Latest` されたスクリプトには、新しいバージョンの powershell で実行するときに、より制限の厳しい規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="4dc55-162">Therefore, a script written for an older version of PowerShell that uses `Set-StrictMode -Version Latest` is subject to more restrictive rules when run in a newer version of PowerShell.</span></span>

```yaml
Type: System.Version
Parameter Sets: Version
Aliases: v

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dc55-163">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4dc55-163">CommonParameters</span></span>

<span data-ttu-id="4dc55-164">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="4dc55-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4dc55-165">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dc55-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4dc55-166">入力</span><span class="sxs-lookup"><span data-stu-id="4dc55-166">INPUTS</span></span>

### <span data-ttu-id="4dc55-167">なし</span><span class="sxs-lookup"><span data-stu-id="4dc55-167">None</span></span>

<span data-ttu-id="4dc55-168">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="4dc55-168">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="4dc55-169">出力</span><span class="sxs-lookup"><span data-stu-id="4dc55-169">OUTPUTS</span></span>

### <span data-ttu-id="4dc55-170">なし</span><span class="sxs-lookup"><span data-stu-id="4dc55-170">None</span></span>

<span data-ttu-id="4dc55-171">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="4dc55-171">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="4dc55-172">注</span><span class="sxs-lookup"><span data-stu-id="4dc55-172">NOTES</span></span>

<span data-ttu-id="4dc55-173">`Set-StrictMode` は、その子スコープに設定されているスコープ内でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="4dc55-173">`Set-StrictMode` is effective only in the scope in which it is set and in its child scopes.</span></span> <span data-ttu-id="4dc55-174">PowerShell のスコープの詳細については、「 [about_Scopes](about/about_Scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dc55-174">For more information about scopes in PowerShell, see [about_Scopes](about/about_Scopes.md).</span></span>

## <span data-ttu-id="4dc55-175">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4dc55-175">RELATED LINKS</span></span>

[<span data-ttu-id="4dc55-176">Set-PSDebug</span><span class="sxs-lookup"><span data-stu-id="4dc55-176">Set-PSDebug</span></span>](Set-PSDebug.md)
