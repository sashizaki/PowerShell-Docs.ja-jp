---
description: PowerShell で関数を作成して使用する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 2/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions
ms.openlocfilehash: 2e1a94659b3a0b8368b0b2611f470a0e676edd55
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391461"
---
# <a name="about-functions"></a><span data-ttu-id="e4cfe-104">Functions について</span><span class="sxs-lookup"><span data-stu-id="e4cfe-104">About Functions</span></span>

## <a name="short-description"></a><span data-ttu-id="e4cfe-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="e4cfe-105">Short description</span></span>

<span data-ttu-id="e4cfe-106">PowerShell で関数を作成して使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-106">Describes how to create and use functions in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="e4cfe-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="e4cfe-107">Long description</span></span>

<span data-ttu-id="e4cfe-108">関数とは、割り当てた名前を持つ PowerShell ステートメントの一覧です。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-108">A function is a list of PowerShell statements that has a name that you assign.</span></span> <span data-ttu-id="e4cfe-109">関数を実行するときは、関数名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-109">When you run a function, you type the function name.</span></span> <span data-ttu-id="e4cfe-110">リスト内のステートメントは、コマンドプロンプトで入力した場合と同じように実行されます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-110">The statements in the list run as if you had typed them at the command prompt.</span></span>

<span data-ttu-id="e4cfe-111">関数は、次のような単純なものにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-111">Functions can be as simple as:</span></span>

```powershell
function Get-PowerShellProcess { Get-Process PowerShell }
```

<span data-ttu-id="e4cfe-112">関数は、コマンドレットまたはアプリケーションプログラムと同じように複雑にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-112">A function can also be as complex as a cmdlet or an application program.</span></span>

<span data-ttu-id="e4cfe-113">コマンドレットと同様に、関数はパラメーターを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-113">Like cmdlets, functions can have parameters.</span></span> <span data-ttu-id="e4cfe-114">パラメーターには、名前付き、位置指定、スイッチ、または動的パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-114">The parameters can be named, positional, switch, or dynamic parameters.</span></span> <span data-ttu-id="e4cfe-115">関数のパラメーターは、コマンドラインまたはパイプラインから読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-115">Function parameters can be read from the command line or from the pipeline.</span></span>

<span data-ttu-id="e4cfe-116">関数は、表示、変数への代入、または他の関数やコマンドレットに渡すことができる値を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-116">Functions can return values that can be displayed, assigned to variables, or passed to other functions or cmdlets.</span></span> <span data-ttu-id="e4cfe-117">キーワードを使用して戻り値を指定することもでき `return` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-117">You can also specify a return value using the `return` keyword.</span></span> <span data-ttu-id="e4cfe-118">キーワードは、 `return` 関数から返される他の出力には影響しません。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-118">The `return` keyword does not affect or suppress other output returned from your function.</span></span> <span data-ttu-id="e4cfe-119">ただし、 `return` キーワードはその行の関数を終了します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-119">However, the `return` keyword exits the function at that line.</span></span> <span data-ttu-id="e4cfe-120">詳細については、「 [about_Return](about_Return.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-120">For more information, see [about_Return](about_Return.md).</span></span>

<span data-ttu-id="e4cfe-121">関数のステートメントリストには、キーワード、、およびを使用して、さまざまな種類のステートメントリストを含めることができ `Begin` `Process` `End` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-121">The function's statement list can contain different types of statement lists with the keywords `Begin`, `Process`, and `End`.</span></span> <span data-ttu-id="e4cfe-122">これらのステートメントでは、パイプラインからの入力の処理方法が異なります。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-122">These statement lists handle input from the pipeline differently.</span></span>

<span data-ttu-id="e4cfe-123">フィルターは、キーワードを使用する特別な種類の関数です `Filter` 。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-123">A filter is a special kind of function that uses the `Filter` keyword.</span></span>

<span data-ttu-id="e4cfe-124">関数は、コマンドレットのように機能することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-124">Functions can also act like cmdlets.</span></span> <span data-ttu-id="e4cfe-125">プログラミングを使用せずに、コマンドレットと同じように動作する関数を作成でき `C#` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-125">You can create a function that works just like a cmdlet without using `C#` programming.</span></span> <span data-ttu-id="e4cfe-126">詳細については、「 [about_Functions_Advanced](about_Functions_Advanced.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-126">For more information, see [about_Functions_Advanced](about_Functions_Advanced.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="e4cfe-127">構文</span><span class="sxs-lookup"><span data-stu-id="e4cfe-127">Syntax</span></span>

<span data-ttu-id="e4cfe-128">関数の構文を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-128">The following is the syntax for a function:</span></span>

```
function [<scope:>]<name> [([type]$parameter1[,[type]$parameter2])]
{
  param([type]$parameter1 [,[type]$parameter2])
  dynamicparam {<statement list>}
  begin {<statement list>}
  process {<statement list>}
  end {<statement list>}
}
```

<span data-ttu-id="e4cfe-129">関数には、次の項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-129">A function includes the following items:</span></span>

- <span data-ttu-id="e4cfe-130">`Function`キーワード</span><span class="sxs-lookup"><span data-stu-id="e4cfe-130">A `Function` keyword</span></span>
- <span data-ttu-id="e4cfe-131">スコープ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="e4cfe-131">A scope (optional)</span></span>
- <span data-ttu-id="e4cfe-132">選択した名前</span><span class="sxs-lookup"><span data-stu-id="e4cfe-132">A name that you select</span></span>
- <span data-ttu-id="e4cfe-133">任意の数の名前付きパラメーター (省略可能)</span><span class="sxs-lookup"><span data-stu-id="e4cfe-133">Any number of named parameters (optional)</span></span>
- <span data-ttu-id="e4cfe-134">中かっこで囲まれた1つ以上の PowerShell コマンド `{}`</span><span class="sxs-lookup"><span data-stu-id="e4cfe-134">One or more PowerShell commands enclosed in braces `{}`</span></span>

<span data-ttu-id="e4cfe-135">`Dynamicparam`関数のキーワードと動的パラメーターの詳細については、「 [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-135">For more information about the `Dynamicparam` keyword and dynamic parameters in functions, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

## <a name="simple-functions"></a><span data-ttu-id="e4cfe-136">単純な関数</span><span class="sxs-lookup"><span data-stu-id="e4cfe-136">Simple Functions</span></span>

<span data-ttu-id="e4cfe-137">関数は、役に立つために複雑である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-137">Functions do not have to be complicated to be useful.</span></span> <span data-ttu-id="e4cfe-138">最も単純な関数の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-138">The simplest functions have the following format:</span></span>

```
function <function-name> {statements}
```

<span data-ttu-id="e4cfe-139">たとえば、次の関数は、[管理者として実行] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-139">For example, the following function starts PowerShell with the Run as Administrator option.</span></span>

```powershell
function Start-PSAdmin {Start-Process PowerShell -Verb RunAs}
```

<span data-ttu-id="e4cfe-140">関数を使用するには、次のように入力します。 `Start-PSAdmin`</span><span class="sxs-lookup"><span data-stu-id="e4cfe-140">To use the function, type: `Start-PSAdmin`</span></span>

<span data-ttu-id="e4cfe-141">関数にステートメントを追加するには、各ステートメントを別の行に入力するか、セミコロンを使用し `;` てステートメントを区切ります。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-141">To add statements to the function, type each statement on a separate line, or use a semi-colon `;` to separate the statements.</span></span>

<span data-ttu-id="e4cfe-142">たとえば、次の関数は、 `.jpg` 開始日以降に変更された、現在のユーザーのディレクトリにあるすべてのファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-142">For example, the following function finds all `.jpg` files in the current user's directories that were changed after the start date.</span></span>

```powershell
function Get-NewPix
{
  $start = Get-Date -Month 1 -Day 1 -Year 2010
  $allpix = Get-ChildItem -Path $env:UserProfile\*.jpg -Recurse
  $allpix | Where-Object {$_.LastWriteTime -gt $Start}
}
```

<span data-ttu-id="e4cfe-143">便利な小さい関数のツールボックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-143">You can create a toolbox of useful small functions.</span></span> <span data-ttu-id="e4cfe-144">これらの関数を PowerShell プロファイルに追加します。詳細については、このトピックの「 [about_Profiles](about_Profiles.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-144">Add these functions to your PowerShell profile, as described in [about_Profiles](about_Profiles.md) and later in this topic.</span></span>

## <a name="function-names"></a><span data-ttu-id="e4cfe-145">関数名</span><span class="sxs-lookup"><span data-stu-id="e4cfe-145">Function Names</span></span>

<span data-ttu-id="e4cfe-146">関数には任意の名前を割り当てることができますが、他のユーザーと共有する関数は、すべての PowerShell コマンドに対して設定されている名前付け規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-146">You can assign any name to a function, but functions that you share with others should follow the naming rules that have been established for all PowerShell commands.</span></span>

<span data-ttu-id="e4cfe-147">関数名は、動詞と名詞のペアで構成されている必要があります。動詞は、関数が実行するアクションを識別し、名詞は、コマンドレットがアクションを実行する項目を識別します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-147">Functions names should consist of a verb-noun pair in which the verb identifies the action that the function performs and the noun identifies the item on which the cmdlet performs its action.</span></span>

<span data-ttu-id="e4cfe-148">関数は、すべての PowerShell コマンドに対して承認された標準動詞を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-148">Functions should use the standard verbs that have been approved for all PowerShell commands.</span></span> <span data-ttu-id="e4cfe-149">これらの動詞を使用すると、コマンド名を簡単かつ一貫性のあるものにし、ユーザーが理解しやすいものにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-149">These verbs help us to keep our command names simple, consistent, and easy for users to understand.</span></span>

<span data-ttu-id="e4cfe-150">標準の PowerShell 動詞の詳細については、「Microsoft Docs での承認された [動詞](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-150">For more information about the standard PowerShell verbs, see [Approved Verbs](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands) in the Microsoft Docs.</span></span>

## <a name="functions-with-parameters"></a><span data-ttu-id="e4cfe-151">パラメーターを持つ関数</span><span class="sxs-lookup"><span data-stu-id="e4cfe-151">Functions with Parameters</span></span>

<span data-ttu-id="e4cfe-152">パラメーターには、名前付きパラメーター、位置指定パラメーター、スイッチパラメーター、動的パラメーターなどの関数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-152">You can use parameters with functions, including named parameters, positional parameters, switch parameters, and dynamic parameters.</span></span> <span data-ttu-id="e4cfe-153">関数の動的パラメーターの詳細については、「 [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-153">For more information about dynamic parameters in functions, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

### <a name="named-parameters"></a><span data-ttu-id="e4cfe-154">名前付きパラメーター</span><span class="sxs-lookup"><span data-stu-id="e4cfe-154">Named Parameters</span></span>

<span data-ttu-id="e4cfe-155">任意の数の名前付きパラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-155">You can define any number of named parameters.</span></span> <span data-ttu-id="e4cfe-156">このトピックで後述するように、名前付きパラメーターの既定値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-156">You can include a default value for named parameters, as described later in this topic.</span></span>

<span data-ttu-id="e4cfe-157">`Param`次のサンプル構文に示すように、キーワードを使用して、中かっこ内にパラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-157">You can define parameters inside the braces using the `Param` keyword, as shown in the following sample syntax:</span></span>

```
function <name> {
  param ([type]$parameter1[,[type]$parameter2])
  <statement list>
}
```

<span data-ttu-id="e4cfe-158">`Param`次のサンプル構文に示すように、キーワードを使用せずに、中かっこの外側にパラメーターを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-158">You can also define parameters outside the braces without the `Param` keyword, as shown in the following sample syntax:</span></span>

```powershell
function <name> [([type]$parameter1[,[type]$parameter2])] {
  <statement list>
}
```

<span data-ttu-id="e4cfe-159">この代替構文の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-159">Below is an example of this alternative syntax.</span></span>

```powershell
Function Add-Numbers($one, $two) {
    $one + $two
}
```

<span data-ttu-id="e4cfe-160">最初の方法をお勧めしますが、この2つの方法に違いはありません。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-160">While the first method is preferred, there is no difference between these two methods.</span></span>

<span data-ttu-id="e4cfe-161">関数を実行すると、パラメーターに指定した値が、パラメーター名を含む変数に代入されます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-161">When you run the function, the value you supply for a parameter is assigned to a variable that contains the parameter name.</span></span> <span data-ttu-id="e4cfe-162">この変数の値は、関数で使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-162">The value of that variable can be used in the function.</span></span>

<span data-ttu-id="e4cfe-163">次の例は、という関数を示して `Get-SmallFiles` います。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-163">The following example is a function called `Get-SmallFiles`.</span></span> <span data-ttu-id="e4cfe-164">この関数には `$Size` パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-164">This function has a `$Size` parameter.</span></span> <span data-ttu-id="e4cfe-165">関数は、パラメーターの値よりも小さいすべてのファイルを表示 `$Size` し、ディレクトリを除外します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-165">The function displays all the files that are smaller than the value of the `$Size` parameter, and it excludes directories:</span></span>

```powershell
function Get-SmallFiles {
  Param($Size)
  Get-ChildItem $HOME | Where-Object {
    $_.Length -lt $Size -and !$_.PSIsContainer
  }
}
```

<span data-ttu-id="e4cfe-166">関数では、 `$Size` パラメーターに定義されている名前である変数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-166">In the function, you can use the `$Size` variable, which is the name defined for the parameter.</span></span>

<span data-ttu-id="e4cfe-167">この関数を使用するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-167">To use this function, type the following command:</span></span>

```powershell
Get-SmallFiles -Size 50
```

<span data-ttu-id="e4cfe-168">パラメーター名を指定せずに名前付きパラメーターの値を入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-168">You can also enter a value for a named parameter without the parameter name.</span></span>
<span data-ttu-id="e4cfe-169">たとえば、次のコマンドでは、 **Size** パラメーターに名前を付けたコマンドと同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-169">For example, the following command gives the same result as a command that names the **Size** parameter:</span></span>

```powershell
Get-SmallFiles 50
```

<span data-ttu-id="e4cfe-170">パラメーターの既定値を定義するには、次の例に示すように、等号とパラメーター名の後に値を入力し `Get-SmallFiles` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-170">To define a default value for a parameter, type an equal sign and the value after the parameter name, as shown in the following variation of the `Get-SmallFiles` example:</span></span>

```powershell
function Get-SmallFiles ($Size = 100) {
  Get-ChildItem $HOME | Where-Object {
    $_.Length -lt $Size -and !$_.PSIsContainer
  }
}
```

<span data-ttu-id="e4cfe-171">`Get-SmallFiles`値を指定せずにを入力すると、関数は100をに割り当て `$size` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-171">If you type `Get-SmallFiles` without a value, the function assigns 100 to `$size`.</span></span> <span data-ttu-id="e4cfe-172">値を指定した場合、関数はその値を使用します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-172">If you provide a value, the function uses that value.</span></span>

<span data-ttu-id="e4cfe-173">必要に応じて、パラメーターの既定値を説明する簡単なヘルプ文字列を指定できます。これには、パラメーターの説明に **psdefaultvalue** 属性を追加し、 **Psdefaultvalue** の **help** プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-173">Optionally, you can provide a brief help string that describes the default value of your parameter, by adding the **PSDefaultValue** attribute to the description of your parameter, and specifying the **Help** property of **PSDefaultValue**.</span></span> <span data-ttu-id="e4cfe-174">関数の **Size** パラメーターの既定値 (100) を説明するヘルプ文字列を指定するには `Get-SmallFiles` 、次の例に示すように **psdefaultvalue** 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-174">To provide a help string that describes the default value (100) of the **Size** parameter in the `Get-SmallFiles` function, add the **PSDefaultValue** attribute as shown in the following example.</span></span>

```powershell
function Get-SmallFiles {
  param (
      [PSDefaultValue(Help = '100')]
      $Size = 100
  )
}
```

<span data-ttu-id="e4cfe-175">**Psdefaultvalue** 属性クラスの詳細については、「 [Psdefaultvalue 属性のメンバー](/dotnet/api/system.management.automation.psdefaultvalueattribute)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-175">For more information about the **PSDefaultValue** attribute class, see [PSDefaultValue Attribute Members](/dotnet/api/system.management.automation.psdefaultvalueattribute).</span></span>

### <a name="positional-parameters"></a><span data-ttu-id="e4cfe-176">位置指定パラメーター</span><span class="sxs-lookup"><span data-stu-id="e4cfe-176">Positional Parameters</span></span>

<span data-ttu-id="e4cfe-177">位置指定パラメーターは、パラメーター名のないパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-177">A positional parameter is a parameter without a parameter name.</span></span> <span data-ttu-id="e4cfe-178">PowerShell では、パラメーター値の順序を使用して、各パラメーター値を関数のパラメーターに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-178">PowerShell uses the parameter value order to associate each parameter value with a parameter in the function.</span></span>

<span data-ttu-id="e4cfe-179">位置指定パラメーターを使用する場合は、関数名の後に1つ以上の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-179">When you use positional parameters, type one or more values after the function name.</span></span> <span data-ttu-id="e4cfe-180">位置指定パラメーターの値は配列変数に代入され `$args` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-180">Positional parameter values are assigned to the `$args` array variable.</span></span>
<span data-ttu-id="e4cfe-181">関数名の後の値は、配列内の最初の位置に割り当てられ `$args` `$args[0]` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-181">The value that follows the function name is assigned to the first position in the `$args` array, `$args[0]`.</span></span>

<span data-ttu-id="e4cfe-182">次の関数は、指定したファイル `Get-Extension` `.txt` 名にファイル名拡張子を追加します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-182">The following `Get-Extension` function adds the `.txt` file name extension to a file name that you supply:</span></span>

```powershell
function Get-Extension {
  $name = $args[0] + ".txt"
  $name
}
```

```powershell
Get-Extension myTextFile
```

```Output
myTextFile.txt
```

### <a name="switch-parameters"></a><span data-ttu-id="e4cfe-183">スイッチパラメーター</span><span class="sxs-lookup"><span data-stu-id="e4cfe-183">Switch Parameters</span></span>

<span data-ttu-id="e4cfe-184">スイッチは、値を必要としないパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-184">A switch is a parameter that does not require a value.</span></span> <span data-ttu-id="e4cfe-185">代わりに、関数名の後にスイッチパラメーターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-185">Instead, you type the function name followed by the name of the switch parameter.</span></span>

<span data-ttu-id="e4cfe-186">スイッチパラメーターを定義するには、 `[switch]` 次の例に示すように、パラメーター名の前に型を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-186">To define a switch parameter, specify the type `[switch]` before the parameter name, as shown in the following example:</span></span>

```powershell
function Switch-Item {
  param ([switch]$on)
  if ($on) { "Switch on" }
  else { "Switch off" }
}
```

<span data-ttu-id="e4cfe-187">`On`関数名の後に switch パラメーターを入力すると、関数は "switch on" を表示します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-187">When you type the `On` switch parameter after the function name, the function displays "Switch on".</span></span> <span data-ttu-id="e4cfe-188">スイッチパラメーターを指定しない場合は、"Switch off" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-188">Without the switch parameter, it displays "Switch off".</span></span>

```powershell
Switch-Item -on
```

```Output
Switch on
```

```powershell
Switch-Item
```

```Output
Switch off
```

<span data-ttu-id="e4cfe-189">次の例に示すように、関数を実行するときに、スイッチに **ブール** 値を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-189">You can also assign a **Boolean** value to a switch when you run the function, as shown in the following example:</span></span>

```powershell
Switch-Item -on:$true
```

```Output
Switch on
```

```powershell
Switch-Item -on:$false
```

```Output
Switch off
```

## <a name="using-splatting-to-represent-command-parameters"></a><span data-ttu-id="e4cfe-190">スプラッティングを使用してコマンドパラメーターを表す</span><span class="sxs-lookup"><span data-stu-id="e4cfe-190">Using Splatting to Represent Command Parameters</span></span>

<span data-ttu-id="e4cfe-191">スプラッティングを使用して、コマンドのパラメーターを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-191">You can use splatting to represent the parameters of a command.</span></span> <span data-ttu-id="e4cfe-192">この機能は、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-192">This feature is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="e4cfe-193">この手法は、セッションでコマンドを呼び出す関数で使用します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-193">Use this technique in functions that call commands in the session.</span></span> <span data-ttu-id="e4cfe-194">コマンドパラメーターを宣言または列挙したり、コマンドパラメーターが変更されたときに関数を変更したりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-194">You do not need to declare or enumerate the command parameters, or change the function when command parameters change.</span></span>

<span data-ttu-id="e4cfe-195">次のサンプル関数は、 `Get-Command` コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-195">The following sample function calls the `Get-Command` cmdlet.</span></span> <span data-ttu-id="e4cfe-196">このコマンドは、を使用して `@Args` のパラメーターを表し `Get-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-196">The command uses `@Args` to represent the parameters of `Get-Command`.</span></span>

```powershell
function Get-MyCommand { Get-Command @Args }
```

<span data-ttu-id="e4cfe-197">関数を呼び出すときに、のすべてのパラメーターを使用でき `Get-Command` `Get-MyCommand` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-197">You can use all of the parameters of `Get-Command` when you call the `Get-MyCommand` function.</span></span> <span data-ttu-id="e4cfe-198">パラメーターとパラメーター値は、を使用してコマンドに渡され `@Args` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-198">The parameters and parameter values are passed to the command using `@Args`.</span></span>

```powershell
Get-MyCommand -Name Get-ChildItem
```

```Output
CommandType     Name                ModuleName
-----------     ----                ----------
Cmdlet          Get-ChildItem       Microsoft.PowerShell.Management
```

<span data-ttu-id="e4cfe-199">この `@Args` 機能は `$Args` 自動パラメーターを使用します。これは、宣言されていないコマンドレットパラメーターと残りの引数の値を表します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-199">The `@Args` feature uses the `$Args` automatic parameter, which represents undeclared cmdlet parameters and values from remaining arguments.</span></span>

<span data-ttu-id="e4cfe-200">スプラッティングの詳細については、「 [about_Splatting](about_Splatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-200">For more information about splatting, see [about_Splatting](about_Splatting.md).</span></span>

## <a name="piping-objects-to-functions"></a><span data-ttu-id="e4cfe-201">オブジェクトを関数にパイプする</span><span class="sxs-lookup"><span data-stu-id="e4cfe-201">Piping Objects to Functions</span></span>

<span data-ttu-id="e4cfe-202">すべての関数は、パイプラインからの入力を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-202">Any function can take input from the pipeline.</span></span> <span data-ttu-id="e4cfe-203">、、およびキーワードを使用して、関数がパイプラインからの入力を処理する方法を制御でき `Begin` `Process` `End` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-203">You can control how a function processes input from the pipeline using `Begin`, `Process`, and `End` keywords.</span></span> <span data-ttu-id="e4cfe-204">次のサンプル構文は、3つのキーワードを示しています。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-204">The following sample syntax shows the three keywords:</span></span>

```
function <name> {
  begin {<statement list>}
  process {<statement list>}
  end {<statement list>}
}
```

<span data-ttu-id="e4cfe-205">`Begin`ステートメントリストは、関数の先頭で1回だけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-205">The `Begin` statement list runs one time only, at the beginning of the function.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4cfe-206">関数で、、またはブロックが定義されている場合は、 `Begin` `Process` `End` すべてのコードがそのブロック内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-206">If your function defines a `Begin`, `Process` or `End` block, all of your code must reside inside those blocks.</span></span> <span data-ttu-id="e4cfe-207">ブロックの *いずれか* が定義されている場合、ブロックの外側ではコードが認識されません。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-207">No code will be recognized outside the blocks if *any* of the blocks are defined.</span></span>

<span data-ttu-id="e4cfe-208">ステートメントの一覧は、 `Process` パイプライン内の各オブジェクトに対して1回実行されます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-208">The `Process` statement list runs one time for each object in the pipeline.</span></span>
<span data-ttu-id="e4cfe-209">`Process`ブロックが実行されている間、各パイプラインオブジェクトは、一度に1つのパイプラインオブジェクトに対して自動変数に割り当てられ `$_` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-209">While the `Process` block is running, each pipeline object is assigned to the `$_` automatic variable, one pipeline object at a time.</span></span>

<span data-ttu-id="e4cfe-210">関数がパイプライン内のすべてのオブジェクトを受け取ると、 `End` ステートメントの一覧が1回だけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-210">After the function receives all the objects in the pipeline, the `End` statement list runs one time.</span></span> <span data-ttu-id="e4cfe-211">、、またはキーワードが使用されていない場合は、 `Begin` `Process` `End` すべてのステートメントがステートメントリストと同様に扱われ `End` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-211">If no `Begin`, `Process`, or `End` keywords are used, all the statements are treated like an `End` statement list.</span></span>

<span data-ttu-id="e4cfe-212">次の関数では、キーワードを使用し `Process` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-212">The following function uses the `Process` keyword.</span></span> <span data-ttu-id="e4cfe-213">この関数は、パイプラインの例を表示します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-213">The function displays examples from the pipeline:</span></span>

```powershell
function Get-Pipeline
{
  process {"The value is: $_"}
}
```

<span data-ttu-id="e4cfe-214">この関数を示すには、次の例に示すように、コンマで区切られた数値のリストを入力します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-214">To demonstrate this function, enter an list of numbers separated by commas, as shown in the following example:</span></span>

```powershell
1,2,4 | Get-Pipeline
```

```Output
The value is: 1
The value is: 2
The value is: 4
```

<span data-ttu-id="e4cfe-215">パイプラインで関数を使用すると、関数にパイプされたオブジェクトが自動変数に割り当てられ `$input` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-215">When you use a function in a pipeline, the objects piped to the function are assigned to the `$input` automatic variable.</span></span> <span data-ttu-id="e4cfe-216">関数は、 `Begin` オブジェクトがパイプラインから取得される前に、キーワードを使用してステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-216">The function runs statements with the `Begin` keyword before any objects come from the pipeline.</span></span> <span data-ttu-id="e4cfe-217">関数は、 `End` すべてのオブジェクトがパイプラインから受信された後、キーワードを使用してステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-217">The function runs statements with the `End` keyword after all the objects have been received from the pipeline.</span></span>

<span data-ttu-id="e4cfe-218">次の例は、 `$input` キーワードとキーワードを使用した自動変数を示して `Begin` `End` います。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-218">The following example shows the `$input` automatic variable with `Begin` and `End` keywords.</span></span>

```powershell
function Get-PipelineBeginEnd
{
  begin {"Begin: The input is $input"}
  end {"End:   The input is $input" }
}
```

<span data-ttu-id="e4cfe-219">パイプラインを使用してこの関数を実行すると、次の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-219">If this function is run by using the pipeline, it displays the following results:</span></span>

```powershell
1,2,4 | Get-PipelineBeginEnd
```

```Output
Begin: The input is
End:   The input is 1 2 4
```

<span data-ttu-id="e4cfe-220">ステートメントの実行時に、この `Begin` 関数にはパイプラインからの入力がありません。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-220">When the `Begin` statement runs, the function does not have the input from the pipeline.</span></span> <span data-ttu-id="e4cfe-221">ステートメントは、 `End` 関数の値がの後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-221">The `End` statement runs after the function has the values.</span></span>

<span data-ttu-id="e4cfe-222">関数にキーワードがある場合 `Process` 、内の各オブジェクト `$input` はから削除され、 `$input` に割り当てられ `$_` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-222">If the function has a `Process` keyword, each object in `$input` is removed from `$input` and assigned to `$_`.</span></span> <span data-ttu-id="e4cfe-223">次の例には、ステートメントの一覧があり `Process` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-223">The following example has a `Process` statement list:</span></span>

```powershell
function Get-PipelineInput
{
  process {"Processing:  $_ " }
  end {"End:   The input is: $input" }
}
```

<span data-ttu-id="e4cfe-224">この例では、関数にパイプ処理された各オブジェクトが、ステートメントリストに送信され `Process` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-224">In this example, each object that is piped to the function is sent to the `Process` statement list.</span></span> <span data-ttu-id="e4cfe-225">ステートメントは、 `Process` 各オブジェクトに対して一度に1つずつ実行されます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-225">The `Process` statements run on each object, one object at a time.</span></span> <span data-ttu-id="e4cfe-226">`$input`関数がキーワードに達した場合、自動変数は空になり `End` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-226">The `$input` automatic variable is empty when the function reaches the `End` keyword.</span></span>

```powershell
1,2,4 | Get-PipelineInput
```

```Output
Processing:  1
Processing:  2
Processing:  4
End:   The input is:
```

<span data-ttu-id="e4cfe-227">詳細については、「[列挙子の使用](about_Automatic_Variables.md#using-enumerators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-227">For more information, see [Using Enumerators](about_Automatic_Variables.md#using-enumerators)</span></span>

## <a name="filters"></a><span data-ttu-id="e4cfe-228">フィルター</span><span class="sxs-lookup"><span data-stu-id="e4cfe-228">Filters</span></span>

<span data-ttu-id="e4cfe-229">フィルターは、パイプライン内の各オブジェクトに対して実行される関数の一種です。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-229">A filter is a type of function that runs on each object in the pipeline.</span></span> <span data-ttu-id="e4cfe-230">フィルターは、ブロック内のすべてのステートメントを含む関数に似て `Process` います。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-230">A filter resembles a function with all its statements in a `Process` block.</span></span>

<span data-ttu-id="e4cfe-231">フィルターの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-231">The syntax of a filter is as follows:</span></span>

```
filter [<scope:>]<name> {<statement list>}
```

<span data-ttu-id="e4cfe-232">次のフィルターは、パイプラインからログエントリを受け取り、エントリ全体を表示するか、エントリのメッセージ部分のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-232">The following filter takes log entries from the pipeline and then displays either the whole entry or only the message portion of the entry:</span></span>

```powershell
filter Get-ErrorLog ([switch]$message)
{
  if ($message) { Out-Host -InputObject $_.Message }
  else { $_ }
}
```

## <a name="function-scope"></a><span data-ttu-id="e4cfe-233">関数のスコープ</span><span class="sxs-lookup"><span data-stu-id="e4cfe-233">Function Scope</span></span>

<span data-ttu-id="e4cfe-234">関数は、それが作成されたスコープ内に存在します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-234">A function exists in the scope in which it was created.</span></span>

<span data-ttu-id="e4cfe-235">関数がスクリプトの一部である場合、関数はそのスクリプト内のステートメントで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-235">If a function is part of a script, the function is available to statements within that script.</span></span> <span data-ttu-id="e4cfe-236">既定では、スクリプト内の関数はコマンドプロンプトでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-236">By default, a function in a script is not available at the command prompt.</span></span>

<span data-ttu-id="e4cfe-237">関数のスコープを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-237">You can specify the scope of a function.</span></span> <span data-ttu-id="e4cfe-238">たとえば、次の例では、関数がグローバルスコープに追加されます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-238">For example, the function is added to the global scope in the following example:</span></span>

```powershell
function global:Get-DependentSvs {
  Get-Service | Where-Object {$_.DependentServices}
}
```

<span data-ttu-id="e4cfe-239">関数がグローバルスコープ内にある場合は、スクリプト、関数、およびコマンドラインで関数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-239">When a function is in the global scope, you can use the function in scripts, in functions, and at the command line.</span></span>

<span data-ttu-id="e4cfe-240">関数は、通常、スコープを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-240">Functions normally create a scope.</span></span> <span data-ttu-id="e4cfe-241">変数などの関数で作成されたアイテムは、関数スコープにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-241">The items created in a function, such as variables, exist only in the function scope.</span></span>

<span data-ttu-id="e4cfe-242">PowerShell のスコープの詳細については、「 [about_Scopes](about_Scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-242">For more information about scope in PowerShell, see [about_Scopes](about_Scopes.md).</span></span>

## <a name="finding-and-managing-functions-using-the-function-drive"></a><span data-ttu-id="e4cfe-243">関数を使用した関数の検索と管理: ドライブ</span><span class="sxs-lookup"><span data-stu-id="e4cfe-243">Finding and Managing Functions Using the Function: Drive</span></span>

<span data-ttu-id="e4cfe-244">PowerShell のすべての関数とフィルターは、自動的にドライブに格納され `Function:` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-244">All the functions and filters in PowerShell are automatically stored in the `Function:` drive.</span></span> <span data-ttu-id="e4cfe-245">このドライブは、PowerShell **関数** プロバイダーによって公開されています。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-245">This drive is exposed by the PowerShell **Function** provider.</span></span>

<span data-ttu-id="e4cfe-246">ドライブを参照するとき `Function:` は、コンピューターのまたはドライブを参照する場合と同様に、 **関数** の後にコロンを入力し `C` `D` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-246">When referring to the `Function:` drive, type a colon after **Function** , just as you would do when referencing the `C` or `D` drive of a computer.</span></span>

<span data-ttu-id="e4cfe-247">次のコマンドは、PowerShell の現在のセッションのすべての関数を表示します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-247">The following command displays all the functions in the current session of PowerShell:</span></span>

```powershell
Get-ChildItem function:
```

<span data-ttu-id="e4cfe-248">関数内のコマンドは、関数の definition プロパティにスクリプトブロックとして格納されます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-248">The commands in the function are stored as a script block in the definition property of the function.</span></span> <span data-ttu-id="e4cfe-249">たとえば、PowerShell に付属する Help 関数のコマンドを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-249">For example, to display the commands in the Help function that comes with PowerShell, type:</span></span>

```powershell
(Get-ChildItem function:help).Definition
```

<span data-ttu-id="e4cfe-250">次の構文を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-250">You can also use the following syntax.</span></span>

```powershell
$function:help
```

<span data-ttu-id="e4cfe-251">ドライブの詳細については `Function:` 、 **関数** プロバイダーのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-251">For more information about the `Function:` drive, see the help topic for the **Function** provider.</span></span> <span data-ttu-id="e4cfe-252">「`Get-Help Function`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-252">Type `Get-Help Function`.</span></span>

## <a name="reusing-functions-in-new-sessions"></a><span data-ttu-id="e4cfe-253">新しいセッションでの関数の再利用</span><span class="sxs-lookup"><span data-stu-id="e4cfe-253">Reusing Functions in New Sessions</span></span>

<span data-ttu-id="e4cfe-254">PowerShell コマンドプロンプトで関数を入力すると、関数が現在のセッションの一部になります。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-254">When you type a function at the PowerShell command prompt, the function becomes part of the current session.</span></span> <span data-ttu-id="e4cfe-255">セッションが終了するまで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-255">It is available until the session ends.</span></span>

<span data-ttu-id="e4cfe-256">すべての PowerShell セッションで関数を使用するには、関数を PowerShell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-256">To use your function in all PowerShell sessions, add the function to your PowerShell profile.</span></span> <span data-ttu-id="e4cfe-257">プロファイルの詳細については、「[about_Profiles](about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-257">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="e4cfe-258">また、関数を PowerShell スクリプトファイルに保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-258">You can also save your function in a PowerShell script file.</span></span> <span data-ttu-id="e4cfe-259">テキストファイルに関数を入力し、ファイル名拡張子を付けてファイルを保存し `.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-259">Type your function in a text file, and then save the file with the `.ps1` file name extension.</span></span>

## <a name="writing-help-for-functions"></a><span data-ttu-id="e4cfe-260">関数のヘルプの記述</span><span class="sxs-lookup"><span data-stu-id="e4cfe-260">Writing Help for Functions</span></span>

<span data-ttu-id="e4cfe-261">`Get-Help`コマンドレットは、コマンドレット、プロバイダー、およびスクリプトに加えて、関数のヘルプを取得します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-261">The `Get-Help` cmdlet gets help for functions, as well as for cmdlets, providers, and scripts.</span></span> <span data-ttu-id="e4cfe-262">関数のヘルプを表示するには、 `Get-Help` 関数名の後に「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-262">To get help for a function, type `Get-Help` followed by the function name.</span></span>

<span data-ttu-id="e4cfe-263">たとえば、関数のヘルプを表示するには、次のように `Get-MyDisks` 入力します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-263">For example, to get help for the `Get-MyDisks` function, type:</span></span>

```powershell
Get-Help Get-MyDisks
```

<span data-ttu-id="e4cfe-264">関数のヘルプは、次の2つの方法のいずれかを使用して記述できます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-264">You can write help for a function by using either of the two following methods:</span></span>

- <span data-ttu-id="e4cfe-265">関数のヘルプの Comment-Based</span><span class="sxs-lookup"><span data-stu-id="e4cfe-265">Comment-Based Help for Functions</span></span>

  <span data-ttu-id="e4cfe-266">コメントに特殊なキーワードを使用して、ヘルプトピックを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-266">Create a help topic by using special keywords in the comments.</span></span> <span data-ttu-id="e4cfe-267">関数のコメントベースのヘルプを作成するには、関数本体の先頭または末尾にコメントを配置するか、関数キーワードの前の行に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-267">To create comment-based help for a function, the comments must be placed at the beginning or end of the function body or on the lines preceding the function keyword.</span></span> <span data-ttu-id="e4cfe-268">コメントベースのヘルプの詳細については、「 [about_Comment_Based_Help](about_Comment_Based_Help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-268">For more information about comment-based help, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span>

- <span data-ttu-id="e4cfe-269">関数のヘルプの XML-Based</span><span class="sxs-lookup"><span data-stu-id="e4cfe-269">XML-Based Help for Functions</span></span>

  <span data-ttu-id="e4cfe-270">コマンドレットに対して通常作成される型など、XML ベースのヘルプトピックを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-270">Create an XML-based help topic, such as the type that is typically created for cmdlets.</span></span> <span data-ttu-id="e4cfe-271">ヘルプトピックを複数の言語にローカライズする場合は、XML ベースのヘルプが必要です。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-271">XML-based help is required if you are localizing help topics into multiple languages.</span></span>

  <span data-ttu-id="e4cfe-272">関数を XML ベースのヘルプトピックに関連付けるには、 `.ExternalHelp` コメントベースのヘルプキーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-272">To associate the function with the XML-based help topic, use the `.ExternalHelp` comment-based help keyword.</span></span> <span data-ttu-id="e4cfe-273">このキーワードがない場合、は `Get-Help` 関数のヘルプトピックを見つけることができず、関数に対してを呼び出すと、 `Get-Help` 自動生成されたヘルプだけが返されます。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-273">Without this keyword, `Get-Help` cannot find the function help topic and calls to `Get-Help` for the function return only auto-generated help.</span></span>

  <span data-ttu-id="e4cfe-274">キーワードの詳細については `ExternalHelp` 、「 [about_Comment_Based_Help](about_Comment_Based_Help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-274">For more information about the `ExternalHelp` keyword, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span> <span data-ttu-id="e4cfe-275">XML ベースのヘルプの詳細については、「 [How To Write Cmdlet help](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4cfe-275">For more information about XML-based help, see [How to Write Cmdlet Help](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span></span>

## <a name="see-also"></a><span data-ttu-id="e4cfe-276">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4cfe-276">See also</span></span>

[<span data-ttu-id="e4cfe-277">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="e4cfe-277">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="e4cfe-278">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="e4cfe-278">about_Comment_Based_Help</span></span>](about_Comment_Based_Help.md)

[<span data-ttu-id="e4cfe-279">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="e4cfe-279">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="e4cfe-280">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="e4cfe-280">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="e4cfe-281">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="e4cfe-281">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="e4cfe-282">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="e4cfe-282">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="e4cfe-283">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="e4cfe-283">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

[<span data-ttu-id="e4cfe-284">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="e4cfe-284">about_Parameters</span></span>](about_Parameters.md)

[<span data-ttu-id="e4cfe-285">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="e4cfe-285">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="e4cfe-286">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="e4cfe-286">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="e4cfe-287">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="e4cfe-287">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="e4cfe-288">about_Function_provider</span><span class="sxs-lookup"><span data-stu-id="e4cfe-288">about_Function_provider</span></span>](about_Function_provider.md)
