---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-expression?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Expression
ms.openlocfilehash: d8f7df3a4c7197b6cf62eecc0b0b314d9668de90
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209699"
---
# <span data-ttu-id="2ffd7-103">Invoke-Expression</span><span class="sxs-lookup"><span data-stu-id="2ffd7-103">Invoke-Expression</span></span>

## <span data-ttu-id="2ffd7-104">概要</span><span class="sxs-lookup"><span data-stu-id="2ffd7-104">SYNOPSIS</span></span>
<span data-ttu-id="2ffd7-105">ローカル コンピューター上でコマンドまたは式を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-105">Runs commands or expressions on the local computer.</span></span>

## <span data-ttu-id="2ffd7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2ffd7-106">SYNTAX</span></span>

```
Invoke-Expression [-Command] <String> [<CommonParameters>]
```

## <span data-ttu-id="2ffd7-107">Description</span><span class="sxs-lookup"><span data-stu-id="2ffd7-107">DESCRIPTION</span></span>

<span data-ttu-id="2ffd7-108">`Invoke-Expression`コマンドレットは、指定された文字列をコマンドとして評価または実行し、式またはコマンドの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-108">The `Invoke-Expression` cmdlet evaluates or runs a specified string as a command and returns the results of the expression or command.</span></span> <span data-ttu-id="2ffd7-109">を指定しない場合 `Invoke-Expression` 、コマンドラインで送信された文字列は変更されずに返されます。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-109">Without `Invoke-Expression`, a string submitted at the command line is returned (echoed) unchanged.</span></span>

<span data-ttu-id="2ffd7-110">式は評価され、現在のスコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-110">Expressions are evaluated and run in the current scope.</span></span> <span data-ttu-id="2ffd7-111">詳細については、「 [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-111">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="2ffd7-112">スクリプトでコマンドレットを使用する場合は、十分な注意が必要 `Invoke-Expression` です。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-112">Take reasonable precautions when using the `Invoke-Expression` cmdlet in scripts.</span></span> <span data-ttu-id="2ffd7-113">を使用してユーザーが入力したコマンドを実行する場合は、コマンドを実行する `Invoke-Expression` 前に実行するのが安全であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-113">When using `Invoke-Expression` to run a command that the user enters, verify that the command is safe to run before running it.</span></span> <span data-ttu-id="2ffd7-114">一般的には、自由な入力を許可するのではなく、定義済みの入力オプションを使用してスクリプトを設計することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-114">In general, it is best to design your script with predefined input options, rather than allowing freeform input.</span></span>

## <span data-ttu-id="2ffd7-115">例</span><span class="sxs-lookup"><span data-stu-id="2ffd7-115">EXAMPLES</span></span>

### <span data-ttu-id="2ffd7-116">例 1: 式を評価する</span><span class="sxs-lookup"><span data-stu-id="2ffd7-116">Example 1: Evaluate an expression</span></span>

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

<span data-ttu-id="2ffd7-117">この例では、を使用して `Invoke-Expression` 式を評価する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-117">This example demonstrates the use of `Invoke-Expression` to evaluate an expression.</span></span> <span data-ttu-id="2ffd7-118">を指定しない `Invoke-Expression` 場合、式は印刷されますが、評価されません。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-118">Without `Invoke-Expression`, the expression is printed, but not evaluated.</span></span>

<span data-ttu-id="2ffd7-119">最初のコマンドは、 `Get-Process` 変数に (文字列) の値を割り当て `$Command` ます。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-119">The first command assigns a value of `Get-Process` (a string) to the `$Command` variable.</span></span>

<span data-ttu-id="2ffd7-120">2 番目のコマンドは、コマンド ラインで変数名を入力した場合の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-120">The second command shows the effect of typing the variable name at the command line.</span></span> <span data-ttu-id="2ffd7-121">PowerShell は文字列をエコーします。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-121">PowerShell echoes the string.</span></span>

<span data-ttu-id="2ffd7-122">3番目のコマンドは、を使用し `Invoke-Expression` て文字列を評価します。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-122">The third command uses `Invoke-Expression` to evaluate the string.</span></span>

### <span data-ttu-id="2ffd7-123">例 2: ローカルコンピューターでスクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="2ffd7-123">Example 2: Run a script on the local computer</span></span>

```powershell
Invoke-Expression -Command "C:\ps-test\testscript.ps1"
"C:\ps-test\testscript.ps1" | Invoke-Expression
```

<span data-ttu-id="2ffd7-124">これらのコマンドは、を使用し `Invoke-Expression` て、ローカルコンピューター上でスクリプト (TestScript.ps1) を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-124">These commands use `Invoke-Expression` to run a script, TestScript.ps1, on the local computer.</span></span> <span data-ttu-id="2ffd7-125">2 つのコマンドは同等です。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-125">The two commands are equivalent.</span></span> <span data-ttu-id="2ffd7-126">最初のコマンドでは、 **command** パラメーターを使用して、実行するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-126">The first uses the **Command** parameter to specify the command to run.</span></span>
<span data-ttu-id="2ffd7-127">2番目のコマンドは、パイプライン演算子 () を使用し `|` て、コマンド文字列をに送信し `Invoke-Expression` ます。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-127">The second uses a pipeline operator (`|`) to send the command string to `Invoke-Expression`.</span></span>

### <span data-ttu-id="2ffd7-128">例 3: 変数でコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="2ffd7-128">Example 3: Run a command in a variable</span></span>

```powershell
$Command = 'Get-Process | where {$_.cpu -gt 1000}'
Invoke-Expression $Command
```

<span data-ttu-id="2ffd7-129">この例では、変数に保存されているコマンド文字列を実行し `$Command` ます。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-129">This example runs a command string that is saved in the `$Command` variable.</span></span>

<span data-ttu-id="2ffd7-130">コマンド文字列は、現在のオブジェクトを表す変数 () が含まれているため、単一引用符で囲まれてい `$_` ます。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-130">The command string is enclosed in single quotation marks because it includes a variable, `$_`, which represents the current object.</span></span> <span data-ttu-id="2ffd7-131">二重引用符で囲まれている場合は、変数 `$_` に保存される前に、変数がその値に置き換えられ `$Command` ます。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-131">If it were enclosed in double quotation marks, the `$_` variable would be replaced by its value before it was saved in the `$Command` variable.</span></span>

### <span data-ttu-id="2ffd7-132">例 4: コマンドレットのヘルプ例を取得して実行する</span><span class="sxs-lookup"><span data-stu-id="2ffd7-132">Example 4: Get and run a cmdlet Help example</span></span>

```powershell
$Cmdlet_name = "Get-EventLog"
$Example_number = 1
$Example_code = (Get-Help $Cmdlet_name).examples.example[($Example_number-1)].code
Invoke-Expression $Example_code
```

<span data-ttu-id="2ffd7-133">このコマンドは、コマンドレットのヘルプトピックの最初の例を取得して実行し `Get-EventLog` ます。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-133">This command retrieves and runs the first example in the `Get-EventLog` cmdlet Help topic.</span></span>

<span data-ttu-id="2ffd7-134">別のコマンドレットの例を実行するには、変数の値 `$Cmdlet_name` をコマンドレットの名前に変更します。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-134">To run an example of a different cmdlet, change the value of the `$Cmdlet_name` variable to the name of the cmdlet.</span></span> <span data-ttu-id="2ffd7-135">また、変数を、 `$Example_number` 実行するサンプル番号に変更します。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-135">And, change the `$Example_number` variable to the example number you want to run.</span></span> <span data-ttu-id="2ffd7-136">例の番号が有効でない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-136">The command fails if the example number is not valid.</span></span>

## <span data-ttu-id="2ffd7-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2ffd7-137">PARAMETERS</span></span>

### <span data-ttu-id="2ffd7-138">-Command</span><span class="sxs-lookup"><span data-stu-id="2ffd7-138">-Command</span></span>

<span data-ttu-id="2ffd7-139">実行するコマンドまたは式を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-139">Specifies the command or expression to run.</span></span> <span data-ttu-id="2ffd7-140">コマンドまたは式を入力するか、コマンドまたは式を含む変数を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-140">Type the command or expression or enter a variable that contains the command or expression.</span></span> <span data-ttu-id="2ffd7-141">**Command** パラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-141">The **Command** parameter is required.</span></span>

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

### <span data-ttu-id="2ffd7-142">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2ffd7-142">CommonParameters</span></span>

<span data-ttu-id="2ffd7-143">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2ffd7-144">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-144">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="2ffd7-145">入力</span><span class="sxs-lookup"><span data-stu-id="2ffd7-145">INPUTS</span></span>

### <span data-ttu-id="2ffd7-146">System.string または PSObject</span><span class="sxs-lookup"><span data-stu-id="2ffd7-146">System.String or PSObject</span></span>

<span data-ttu-id="2ffd7-147">パイプを使用して、コマンドを表すオブジェクトをにパイプすることができ `Invoke-Expression` ます。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-147">You can pipe an object that represents the command to `Invoke-Expression`.</span></span>
<span data-ttu-id="2ffd7-148">`$Input`コマンド内の入力オブジェクトを表すには、自動変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-148">Use the `$Input` automatic variable to represent the input objects in the command.</span></span>

## <span data-ttu-id="2ffd7-149">出力</span><span class="sxs-lookup"><span data-stu-id="2ffd7-149">OUTPUTS</span></span>

### <span data-ttu-id="2ffd7-150">PSObject</span><span class="sxs-lookup"><span data-stu-id="2ffd7-150">PSObject</span></span>

<span data-ttu-id="2ffd7-151">呼び出されたコマンド ( **command** パラメーターの値) によって生成される出力を返します。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-151">Returns the output that is generated by the invoked command (the value of the **Command** parameter).</span></span>

## <span data-ttu-id="2ffd7-152">注</span><span class="sxs-lookup"><span data-stu-id="2ffd7-152">NOTES</span></span>

<span data-ttu-id="2ffd7-153">ほとんどの場合、PowerShell の call 演算子を使用して式を呼び出し、同じ結果を達成します。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-153">In most cases, you invoke expressions using PowerShell's call operator and achieve the same results.</span></span>
<span data-ttu-id="2ffd7-154">呼び出し演算子は安全な方法です。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-154">The call operator is a safer method.</span></span> <span data-ttu-id="2ffd7-155">詳細については、「 [about_Operators](../microsoft.powershell.core/about/about_operators.md#call-operator-)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ffd7-155">For more information, see [about_Operators](../microsoft.powershell.core/about/about_operators.md#call-operator-).</span></span>

## <span data-ttu-id="2ffd7-156">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2ffd7-156">RELATED LINKS</span></span>

[<span data-ttu-id="2ffd7-157">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="2ffd7-157">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="2ffd7-158">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="2ffd7-158">about_Scopes</span></span>](../Microsoft.PowerShell.Core/About/about_Scopes.md)
