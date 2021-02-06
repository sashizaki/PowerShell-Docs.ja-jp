---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-expression?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Expression
ms.openlocfilehash: 65ccc37b1c9122d54f3caf85f4546e1381558ca9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600787"
---
# <span data-ttu-id="1439c-102">Invoke-Expression</span><span class="sxs-lookup"><span data-stu-id="1439c-102">Invoke-Expression</span></span>

## <span data-ttu-id="1439c-103">概要</span><span class="sxs-lookup"><span data-stu-id="1439c-103">SYNOPSIS</span></span>
<span data-ttu-id="1439c-104">ローカル コンピューター上でコマンドまたは式を実行します。</span><span class="sxs-lookup"><span data-stu-id="1439c-104">Runs commands or expressions on the local computer.</span></span>

## <span data-ttu-id="1439c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1439c-105">SYNTAX</span></span>

```
Invoke-Expression [-Command] <String> [<CommonParameters>]
```

## <span data-ttu-id="1439c-106">Description</span><span class="sxs-lookup"><span data-stu-id="1439c-106">DESCRIPTION</span></span>

<span data-ttu-id="1439c-107">`Invoke-Expression`コマンドレットは、指定された文字列をコマンドとして評価または実行し、式またはコマンドの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="1439c-107">The `Invoke-Expression` cmdlet evaluates or runs a specified string as a command and returns the results of the expression or command.</span></span> <span data-ttu-id="1439c-108">を指定しない場合 `Invoke-Expression` 、コマンドラインで送信された文字列は変更されずに返されます。</span><span class="sxs-lookup"><span data-stu-id="1439c-108">Without `Invoke-Expression`, a string submitted at the command line is returned (echoed) unchanged.</span></span>

<span data-ttu-id="1439c-109">式は評価され、現在のスコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="1439c-109">Expressions are evaluated and run in the current scope.</span></span> <span data-ttu-id="1439c-110">詳細については、「 [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1439c-110">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="1439c-111">スクリプトでコマンドレットを使用する場合は、十分な注意が必要 `Invoke-Expression` です。</span><span class="sxs-lookup"><span data-stu-id="1439c-111">Take reasonable precautions when using the `Invoke-Expression` cmdlet in scripts.</span></span> <span data-ttu-id="1439c-112">を使用してユーザーが入力したコマンドを実行する場合は、コマンドを実行する `Invoke-Expression` 前に実行するのが安全であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1439c-112">When using `Invoke-Expression` to run a command that the user enters, verify that the command is safe to run before running it.</span></span> <span data-ttu-id="1439c-113">一般的には、自由な入力を許可するのではなく、定義済みの入力オプションを使用してスクリプトを設計することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1439c-113">In general, it is best to design your script with predefined input options, rather than allowing freeform input.</span></span>

## <span data-ttu-id="1439c-114">例</span><span class="sxs-lookup"><span data-stu-id="1439c-114">EXAMPLES</span></span>

### <span data-ttu-id="1439c-115">例 1: 式を評価する</span><span class="sxs-lookup"><span data-stu-id="1439c-115">Example 1: Evaluate an expression</span></span>

```powershell
$Command = "Get-Process"
$Command
```

```Output
Get-Process
```

```powershell
Invoke-Expression $Command
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
-------  ------    -----      ----- -----   ------     --   -----------
296       4       1572       1956    20       0.53     1348   AdtAgent
270       6       1328       800     34       0.06     2396   alg
67        2       620        484     20       0.22     716    ati2evxx
1060      15      12904      11840   74       11.48    892    CcmExec
1400      33      25280      37544   223      38.44    2564   communicator
...
```

<span data-ttu-id="1439c-116">この例では、を使用して `Invoke-Expression` 式を評価する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1439c-116">This example demonstrates the use of `Invoke-Expression` to evaluate an expression.</span></span> <span data-ttu-id="1439c-117">を指定しない `Invoke-Expression` 場合、式は印刷されますが、評価されません。</span><span class="sxs-lookup"><span data-stu-id="1439c-117">Without `Invoke-Expression`, the expression is printed, but not evaluated.</span></span>

<span data-ttu-id="1439c-118">最初のコマンドは、 `Get-Process` 変数に (文字列) の値を割り当て `$Command` ます。</span><span class="sxs-lookup"><span data-stu-id="1439c-118">The first command assigns a value of `Get-Process` (a string) to the `$Command` variable.</span></span>

<span data-ttu-id="1439c-119">2 番目のコマンドは、コマンド ラインで変数名を入力した場合の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="1439c-119">The second command shows the effect of typing the variable name at the command line.</span></span> <span data-ttu-id="1439c-120">PowerShell は文字列をエコーします。</span><span class="sxs-lookup"><span data-stu-id="1439c-120">PowerShell echoes the string.</span></span>

<span data-ttu-id="1439c-121">3番目のコマンドは、を使用し `Invoke-Expression` て文字列を評価します。</span><span class="sxs-lookup"><span data-stu-id="1439c-121">The third command uses `Invoke-Expression` to evaluate the string.</span></span>

### <span data-ttu-id="1439c-122">例 2: ローカルコンピューターでスクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="1439c-122">Example 2: Run a script on the local computer</span></span>

```powershell
Invoke-Expression -Command "C:\ps-test\testscript.ps1"
"C:\ps-test\testscript.ps1" | Invoke-Expression
```

<span data-ttu-id="1439c-123">これらのコマンドは、を使用し `Invoke-Expression` て、ローカルコンピューター上でスクリプト (TestScript.ps1) を実行します。</span><span class="sxs-lookup"><span data-stu-id="1439c-123">These commands use `Invoke-Expression` to run a script, TestScript.ps1, on the local computer.</span></span> <span data-ttu-id="1439c-124">2 つのコマンドは同等です。</span><span class="sxs-lookup"><span data-stu-id="1439c-124">The two commands are equivalent.</span></span> <span data-ttu-id="1439c-125">最初のコマンドでは、 **command** パラメーターを使用して、実行するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="1439c-125">The first uses the **Command** parameter to specify the command to run.</span></span>
<span data-ttu-id="1439c-126">2番目のコマンドは、パイプライン演算子 () を使用し `|` て、コマンド文字列をに送信し `Invoke-Expression` ます。</span><span class="sxs-lookup"><span data-stu-id="1439c-126">The second uses a pipeline operator (`|`) to send the command string to `Invoke-Expression`.</span></span>

### <span data-ttu-id="1439c-127">例 3: 変数でコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="1439c-127">Example 3: Run a command in a variable</span></span>

```powershell
$Command = 'Get-Process | where {$_.cpu -gt 1000}'
Invoke-Expression $Command
```

<span data-ttu-id="1439c-128">この例では、変数に保存されているコマンド文字列を実行し `$Command` ます。</span><span class="sxs-lookup"><span data-stu-id="1439c-128">This example runs a command string that is saved in the `$Command` variable.</span></span>

<span data-ttu-id="1439c-129">コマンド文字列は、現在のオブジェクトを表す変数 () が含まれているため、単一引用符で囲まれてい `$_` ます。</span><span class="sxs-lookup"><span data-stu-id="1439c-129">The command string is enclosed in single quotation marks because it includes a variable, `$_`, which represents the current object.</span></span> <span data-ttu-id="1439c-130">二重引用符で囲まれている場合は、変数 `$_` に保存される前に、変数がその値に置き換えられ `$Command` ます。</span><span class="sxs-lookup"><span data-stu-id="1439c-130">If it were enclosed in double quotation marks, the `$_` variable would be replaced by its value before it was saved in the `$Command` variable.</span></span>

### <span data-ttu-id="1439c-131">例 4: コマンドレットのヘルプ例を取得して実行する</span><span class="sxs-lookup"><span data-stu-id="1439c-131">Example 4: Get and run a cmdlet Help example</span></span>

```powershell
$Cmdlet_name = "Get-EventLog"
$Example_number = 1
$Example_code = (Get-Help $Cmdlet_name).examples.example[($Example_number-1)].code
Invoke-Expression $Example_code
```

<span data-ttu-id="1439c-132">このコマンドは、コマンドレットのヘルプトピックの最初の例を取得して実行し `Get-EventLog` ます。</span><span class="sxs-lookup"><span data-stu-id="1439c-132">This command retrieves and runs the first example in the `Get-EventLog` cmdlet Help topic.</span></span>

<span data-ttu-id="1439c-133">別のコマンドレットの例を実行するには、変数の値 `$Cmdlet_name` をコマンドレットの名前に変更します。</span><span class="sxs-lookup"><span data-stu-id="1439c-133">To run an example of a different cmdlet, change the value of the `$Cmdlet_name` variable to the name of the cmdlet.</span></span> <span data-ttu-id="1439c-134">また、変数を、 `$Example_number` 実行するサンプル番号に変更します。</span><span class="sxs-lookup"><span data-stu-id="1439c-134">And, change the `$Example_number` variable to the example number you want to run.</span></span> <span data-ttu-id="1439c-135">例の番号が有効でない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="1439c-135">The command fails if the example number is not valid.</span></span>

## <span data-ttu-id="1439c-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1439c-136">PARAMETERS</span></span>

### <span data-ttu-id="1439c-137">-Command</span><span class="sxs-lookup"><span data-stu-id="1439c-137">-Command</span></span>

<span data-ttu-id="1439c-138">実行するコマンドまたは式を指定します。</span><span class="sxs-lookup"><span data-stu-id="1439c-138">Specifies the command or expression to run.</span></span> <span data-ttu-id="1439c-139">コマンドまたは式を入力するか、コマンドまたは式を含む変数を入力します。</span><span class="sxs-lookup"><span data-stu-id="1439c-139">Type the command or expression or enter a variable that contains the command or expression.</span></span> <span data-ttu-id="1439c-140">**Command** パラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="1439c-140">The **Command** parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1439c-141">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="1439c-141">CommonParameters</span></span>

<span data-ttu-id="1439c-142">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="1439c-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1439c-143">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1439c-143">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="1439c-144">入力</span><span class="sxs-lookup"><span data-stu-id="1439c-144">INPUTS</span></span>

### <span data-ttu-id="1439c-145">System.string または PSObject</span><span class="sxs-lookup"><span data-stu-id="1439c-145">System.String or PSObject</span></span>

<span data-ttu-id="1439c-146">パイプを使用して、コマンドを表すオブジェクトをにパイプすることができ `Invoke-Expression` ます。</span><span class="sxs-lookup"><span data-stu-id="1439c-146">You can pipe an object that represents the command to `Invoke-Expression`.</span></span>
<span data-ttu-id="1439c-147">`$Input`コマンド内の入力オブジェクトを表すには、自動変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="1439c-147">Use the `$Input` automatic variable to represent the input objects in the command.</span></span>

## <span data-ttu-id="1439c-148">出力</span><span class="sxs-lookup"><span data-stu-id="1439c-148">OUTPUTS</span></span>

### <span data-ttu-id="1439c-149">PSObject</span><span class="sxs-lookup"><span data-stu-id="1439c-149">PSObject</span></span>

<span data-ttu-id="1439c-150">呼び出されたコマンド ( **command** パラメーターの値) によって生成される出力を返します。</span><span class="sxs-lookup"><span data-stu-id="1439c-150">Returns the output that is generated by the invoked command (the value of the **Command** parameter).</span></span>

## <span data-ttu-id="1439c-151">注</span><span class="sxs-lookup"><span data-stu-id="1439c-151">NOTES</span></span>

<span data-ttu-id="1439c-152">ほとんどの場合、PowerShell の call 演算子を使用して式を呼び出し、同じ結果を達成します。</span><span class="sxs-lookup"><span data-stu-id="1439c-152">In most cases, you invoke expressions using PowerShell's call operator and achieve the same results.</span></span>
<span data-ttu-id="1439c-153">呼び出し演算子は安全な方法です。</span><span class="sxs-lookup"><span data-stu-id="1439c-153">The call operator is a safer method.</span></span> <span data-ttu-id="1439c-154">詳細については、「 [about_Operators](../microsoft.powershell.core/about/about_operators.md#call-operator-)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1439c-154">For more information, see [about_Operators](../microsoft.powershell.core/about/about_operators.md#call-operator-).</span></span>

## <span data-ttu-id="1439c-155">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1439c-155">RELATED LINKS</span></span>

[<span data-ttu-id="1439c-156">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="1439c-156">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="1439c-157">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="1439c-157">about_Scopes</span></span>](../Microsoft.PowerShell.Core/About/about_Scopes.md)

