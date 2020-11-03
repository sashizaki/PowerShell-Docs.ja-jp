---
description: スクリプトブロックとは何かを定義し、PowerShell プログラミング言語でスクリプトブロックを使用する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_script_blocks?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Script_Blocks
ms.openlocfilehash: 28bc5377e1787ddb646480eacc219c5bbb63dc37
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223904"
---
# <a name="about-script-blocks"></a><span data-ttu-id="c8abb-104">スクリプトブロックについて</span><span class="sxs-lookup"><span data-stu-id="c8abb-104">About Script Blocks</span></span>

## <a name="short-description"></a><span data-ttu-id="c8abb-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="c8abb-105">Short description</span></span>

<span data-ttu-id="c8abb-106">スクリプトブロックとは何かを定義し、PowerShell プログラミング言語でスクリプトブロックを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8abb-106">Defines what a script block is and explains how to use script blocks in the PowerShell programming language.</span></span>

## <a name="long-description"></a><span data-ttu-id="c8abb-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="c8abb-107">Long description</span></span>

<span data-ttu-id="c8abb-108">PowerShell プログラミング言語では、スクリプトブロックは1つの単位として使用できるステートメントまたは式のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="c8abb-108">In the PowerShell programming language, a script block is a collection of statements or expressions that can be used as a single unit.</span></span>
<span data-ttu-id="c8abb-109">スクリプト ブロックは引数を受け取り、値を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="c8abb-109">A script block can accept arguments and return values.</span></span>

<span data-ttu-id="c8abb-110">構文的には、次の構文に示すように、スクリプトブロックは中かっこで囲まれたステートメントリストです。</span><span class="sxs-lookup"><span data-stu-id="c8abb-110">Syntactically, a script block is a statement list in braces, as shown in the following syntax:</span></span>

```
{<statement list>}
```

<span data-ttu-id="c8abb-111">スクリプトブロックは、スクリプトブロック内のすべてのコマンドの出力を、単一のオブジェクトまたは配列として返します。</span><span class="sxs-lookup"><span data-stu-id="c8abb-111">A script block returns the output of all the commands in the script block, either as a single object or as an array.</span></span>

<span data-ttu-id="c8abb-112">キーワードを使用して戻り値を指定することもでき `return` ます。</span><span class="sxs-lookup"><span data-stu-id="c8abb-112">You can also specify a return value using the `return` keyword.</span></span> <span data-ttu-id="c8abb-113">キーワードは、 `return` スクリプトブロックから返された他の出力には影響しません。</span><span class="sxs-lookup"><span data-stu-id="c8abb-113">The `return` keyword does not affect or suppress other output returned from your script block.</span></span> <span data-ttu-id="c8abb-114">ただし、キーワードは、 `return` その行のスクリプトブロックを終了します。</span><span class="sxs-lookup"><span data-stu-id="c8abb-114">However, the `return` keyword exits the script block at that line.</span></span> <span data-ttu-id="c8abb-115">詳細については、「 [about_Return](about_Return.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8abb-115">For more information, see [about_Return](about_Return.md).</span></span>

<span data-ttu-id="c8abb-116">関数と同様に、スクリプトブロックにはパラメーターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c8abb-116">Like functions, a script block can include parameters.</span></span> <span data-ttu-id="c8abb-117">次の構文に示すように、Param キーワードを使用して名前付きパラメーターを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c8abb-117">Use the Param keyword to assign named parameters, as shown in the following syntax:</span></span>

```
{
Param([type]$Parameter1 [,[type]$Parameter2])
<statement list>
}
```

> [!NOTE]
> <span data-ttu-id="c8abb-118">スクリプトブロックでは、関数とは異なり、中かっこの外側でパラメーターを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c8abb-118">In a script block, unlike a function, you cannot specify parameters outside the braces.</span></span>

<span data-ttu-id="c8abb-119">関数と同様に、スクリプトブロックには、、、、およびの各キーワードを含めることができ `DynamicParam` `Begin` `Process` `End` ます。</span><span class="sxs-lookup"><span data-stu-id="c8abb-119">Like functions, script blocks can include the `DynamicParam`, `Begin`, `Process`, and `End` keywords.</span></span> <span data-ttu-id="c8abb-120">詳細については、「 [about_Functions](about_Functions.md) 」および「 [about_Functions_Advanced](about_Functions_Advanced.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8abb-120">For more information, see [about_Functions](about_Functions.md) and [about_Functions_Advanced](about_Functions_Advanced.md).</span></span>

## <a name="using-script-blocks"></a><span data-ttu-id="c8abb-121">スクリプトブロックの使用</span><span class="sxs-lookup"><span data-stu-id="c8abb-121">Using Script Blocks</span></span>

<span data-ttu-id="c8abb-122">スクリプトブロックは、Microsoft .NET Framework 型のインスタンス `System.Management.Automation.ScriptBlock` です。</span><span class="sxs-lookup"><span data-stu-id="c8abb-122">A script block is an instance of a Microsoft .NET Framework type `System.Management.Automation.ScriptBlock`.</span></span> <span data-ttu-id="c8abb-123">コマンドには、スクリプトブロックのパラメーター値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c8abb-123">Commands can have script block parameter values.</span></span> <span data-ttu-id="c8abb-124">たとえば、コマンドレットには、次の `Invoke-Command` `ScriptBlock` 例に示すように、スクリプトブロックの値を受け取るパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="c8abb-124">For example, the `Invoke-Command` cmdlet has a `ScriptBlock` parameter that takes a script block value, as shown in this example:</span></span>

```powershell
Invoke-Command -ScriptBlock { Get-Process }
```

```Output
Handles  NPM(K)    PM(K)     WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----     ----- -----   ------     -- -----------
999          28    39100     45020   262    15.88   1844 communicator
721          28    32696     36536   222    20.84   4028 explorer
...
```

<span data-ttu-id="c8abb-125">`Invoke-Command` また、パラメーターブロックを含むスクリプトブロックを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="c8abb-125">`Invoke-Command` can also execute script blocks that have parameter blocks.</span></span>
<span data-ttu-id="c8abb-126">パラメーターは、 **ArgumentList** パラメーターを使用して位置によって割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c8abb-126">Parameters are assigned by position using the **ArgumentList** parameter.</span></span>

```powershell
Invoke-Command -ScriptBlock { param($p1, $p2)
"p1: $p1"
"p2: $p2"
} -ArgumentList "First", "Second"
```

```Output
p1: First
p2: Second
```

<span data-ttu-id="c8abb-127">前の例のスクリプトブロックでは、キーワードを使用し `param` て、パラメーターとを作成して `$p1` `$p2` います。</span><span class="sxs-lookup"><span data-stu-id="c8abb-127">The script block in the preceding example uses the `param` keyword to create a parameters `$p1` and `$p2`.</span></span> <span data-ttu-id="c8abb-128">"First" という文字列は最初のパラメーター () にバインドされ、 `$p1` "Second" は () にバインドされ `$p2` ます。</span><span class="sxs-lookup"><span data-stu-id="c8abb-128">The string "First" is bound to the first parameter (`$p1`) and "Second" is bound to (`$p2`).</span></span>

<span data-ttu-id="c8abb-129">**ArgumentList** の動作の詳細については、「 [about_Splatting](about_Splatting.md#splatting-with-arrays)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8abb-129">For more information about the behavior of **ArgumentList** , see [about_Splatting](about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="c8abb-130">変数を使用して、スクリプトブロックを格納および実行することができます。</span><span class="sxs-lookup"><span data-stu-id="c8abb-130">You can use variables to store and execute script blocks.</span></span> <span data-ttu-id="c8abb-131">次の例では、スクリプトブロックを変数に格納し、に渡し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="c8abb-131">The example below stores a script block in a variable and passes it to `Invoke-Command`.</span></span>

```powershell
$a = { Get-Service BITS }
Invoke-Command -ScriptBlock $a
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  BITS               Background Intelligent Transfer Ser...
```

<span data-ttu-id="c8abb-132">呼び出し演算子は、変数に格納されているスクリプトブロックを実行するもう1つの方法です。</span><span class="sxs-lookup"><span data-stu-id="c8abb-132">The call operator is another way to execute script blocks stored in a variable.</span></span>
<span data-ttu-id="c8abb-133">と同様 `Invoke-Command` に、呼び出し演算子は、子スコープでスクリプトブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="c8abb-133">Like `Invoke-Command`, the call operator executes the script block in a child scope.</span></span> <span data-ttu-id="c8abb-134">呼び出し演算子を使用すると、スクリプトブロックでパラメーターを簡単に使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c8abb-134">The call operator can make it easier for you to use parameters with your script blocks.</span></span>

```powershell
$a ={ param($p1, $p2)
"p1: $p1"
"p2: $p2"
}
&$a -p2 "First" -p1 "Second"
```

```Output
p1: Second
p2: First
```

<span data-ttu-id="c8abb-135">割り当てを使用して、スクリプトブロックの出力を変数に格納できます。</span><span class="sxs-lookup"><span data-stu-id="c8abb-135">You can store the output from your script blocks in a variable using assignment.</span></span>

```
PS>  $a = { 1 + 1}
PS>  $b = &$a
PS>  $b
2
```

```
PS>  $a = { 1 + 1}
PS>  $b = Invoke-Command $a
PS>  $b
2
```

<span data-ttu-id="c8abb-136">呼び出し演算子の詳細については、「 [about_Operators](about_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8abb-136">For more information about the call operator, see [about_Operators](about_Operators.md).</span></span>

## <a name="using-delay-bind-script-blocks-with-parameters"></a><span data-ttu-id="c8abb-137">遅延バインドスクリプトブロックをパラメーターと共に使用する</span><span class="sxs-lookup"><span data-stu-id="c8abb-137">Using delay-bind script blocks with parameters</span></span>

<span data-ttu-id="c8abb-138">パイプラインの入力 () または () を受け入れる型指定されたパラメーター `by Value` `by PropertyName` では、パラメーターで **遅延バインディング** スクリプトブロックを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c8abb-138">A typed parameter that accepts pipeline input (`by Value`) or (`by PropertyName`) enables use of **delay-bind** script blocks on the parameter.</span></span>
<span data-ttu-id="c8abb-139">**遅延バインド** スクリプトブロック内では、パイプライン変数を使用してパイプされた in オブジェクトを参照でき `$_` ます。</span><span class="sxs-lookup"><span data-stu-id="c8abb-139">Within the **delay-bind** script block, you can reference the piped in object using the pipeline variable `$_`.</span></span>

```powershell
# Renames config.log to old_config.log
dir config.log | Rename-Item -NewName {"old_" + $_.Name}
```

<span data-ttu-id="c8abb-140">より複雑なコマンドレットでは、遅延バインドスクリプトブロックを使用すると、パイプを使用してパイプを使用して他のパラメーターを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="c8abb-140">In more complex cmdlets, delay-bind script blocks allow the reuse of one piped in object to populate other parameters.</span></span>

<span data-ttu-id="c8abb-141">遅延をパラメーターとして **バインド** するスクリプトブロックに関する注意事項:</span><span class="sxs-lookup"><span data-stu-id="c8abb-141">Notes on **delay-bind** script blocks as parameters:</span></span>

- <span data-ttu-id="c8abb-142">**遅延バインド** スクリプトブロックで使用するパラメーター名は、明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8abb-142">You must explicitly specify any parameter names you use with **delay-bind** script blocks.</span></span>
- <span data-ttu-id="c8abb-143">パラメーターを型指定することはできません。また、パラメーターの型をまたはにすることはできません `[scriptblock]` `[object]` 。</span><span class="sxs-lookup"><span data-stu-id="c8abb-143">The parameter must not be untyped, and the parameter's type cannot be `[scriptblock]` or `[object]`.</span></span>
- <span data-ttu-id="c8abb-144">パイプライン入力を指定せずに **遅延バインディング** スクリプトブロックを使用すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c8abb-144">You receive an error if you use a **delay-bind** script block without providing pipeline input.</span></span>

  ```powershell
  Rename-Item -NewName {$_.Name + ".old"}
  ```

  ```Output
  Rename-Item : Cannot evaluate parameter 'NewName' because its argument is
  specified as a script block and there is no input. A script block cannot
  be evaluated without input.
  At line:1 char:23
  +  Rename-Item -NewName {$_.Name + ".old"}
  +                       ~~~~~~~~~~~~~~~~~~
      + CategoryInfo          : MetadataError: (:) [Rename-Item],
        ParameterBindingException
      + FullyQualifiedErrorId : ScriptBlockArgumentNoInput,
        Microsoft.PowerShell.Commands.RenameItemCommand
  ```

## <a name="see-also"></a><span data-ttu-id="c8abb-145">参照</span><span class="sxs-lookup"><span data-stu-id="c8abb-145">See Also</span></span>

[<span data-ttu-id="c8abb-146">about_Functions</span><span class="sxs-lookup"><span data-stu-id="c8abb-146">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="c8abb-147">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="c8abb-147">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="c8abb-148">about_Operators</span><span class="sxs-lookup"><span data-stu-id="c8abb-148">about_Operators</span></span>](about_Operators.md)

