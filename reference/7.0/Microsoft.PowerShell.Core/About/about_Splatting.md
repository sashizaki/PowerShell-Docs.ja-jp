---
description: スプラッティングを使用して PowerShell のコマンドにパラメーターを渡す方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_splatting?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Splatting
ms.openlocfilehash: 6918f6699f9da8a24b1284a06a5bb5b4454ca0d7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220544"
---
# <a name="about-splatting"></a><span data-ttu-id="bd631-104">スプラッティングについて</span><span class="sxs-lookup"><span data-stu-id="bd631-104">About Splatting</span></span>

## <a name="short-description"></a><span data-ttu-id="bd631-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="bd631-105">Short description</span></span>

<span data-ttu-id="bd631-106">スプラッティングを使用して PowerShell のコマンドにパラメーターを渡す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bd631-106">Describes how to use splatting to pass parameters to commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="bd631-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="bd631-107">Long description</span></span>

<span data-ttu-id="bd631-108">スプラッティングは、パラメーター値のコレクションを1つの単位としてコマンドに渡す方法です。</span><span class="sxs-lookup"><span data-stu-id="bd631-108">Splatting is a method of passing a collection of parameter values to a command as a unit.</span></span> <span data-ttu-id="bd631-109">PowerShell は、コマンドパラメーターを使用して、コレクション内の各値を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="bd631-109">PowerShell associates each value in the collection with a command parameter.</span></span> <span data-ttu-id="bd631-110">Splatted パラメーターの値は、標準の変数と同じように、名前付きのスプラッティング変数に格納されますが、ドル記号 () ではなくアットマーク () で始まり `@` `$` ます。</span><span class="sxs-lookup"><span data-stu-id="bd631-110">Splatted parameter values are stored in named splatting variables, which look like standard variables, but begin with an At symbol (`@`) instead of a dollar sign (`$`).</span></span> <span data-ttu-id="bd631-111">At 記号は、単一の値ではなく、値のコレクションを渡すことを PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="bd631-111">The At symbol tells PowerShell that you are passing a collection of values, instead of a single value.</span></span>

<span data-ttu-id="bd631-112">スプラッティングを使用すると、コマンドが短く、読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="bd631-112">Splatting makes your commands shorter and easier to read.</span></span> <span data-ttu-id="bd631-113">さまざまなコマンド呼び出しでスプラッティング値を再利用し、スプラッティングを使用して、 `$PSBoundParameters` 自動変数から他のスクリプトや関数にパラメーター値を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="bd631-113">You can reuse the splatting values in different command calls and use splatting to pass parameter values from the `$PSBoundParameters` automatic variable to other scripts and functions.</span></span>

<span data-ttu-id="bd631-114">Windows PowerShell 3.0 以降では、スプラッティングを使用してコマンドのすべてのパラメーターを表すこともできます。</span><span class="sxs-lookup"><span data-stu-id="bd631-114">Beginning in Windows PowerShell 3.0, you can also use splatting to represent all parameters of a command.</span></span>

## <a name="syntax"></a><span data-ttu-id="bd631-115">構文</span><span class="sxs-lookup"><span data-stu-id="bd631-115">Syntax</span></span>

```
<CommandName> <optional parameters> @<HashTable> <optional parameters>
<CommandName> <optional parameters> @<Array> <optional parameters>
```

<span data-ttu-id="bd631-116">パラメーター名を必要としない、位置指定パラメーターのパラメーター値を指定するには、配列構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd631-116">To provide parameter values for positional parameters, in which parameter names are not required, use the array syntax.</span></span> <span data-ttu-id="bd631-117">パラメーターの名前と値のペアを指定するには、ハッシュテーブルの構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd631-117">To provide parameter name and value pairs, use the hash table syntax.</span></span> <span data-ttu-id="bd631-118">Splatted の値は、パラメーターリスト内の任意の場所に配置できます。</span><span class="sxs-lookup"><span data-stu-id="bd631-118">The splatted value can appear anywhere in the parameter list.</span></span>

<span data-ttu-id="bd631-119">スプラッティングの場合、すべてのパラメーターを渡すためにハッシュテーブルまたは配列を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bd631-119">When splatting, you do not need to use a hash table or an array to pass all parameters.</span></span> <span data-ttu-id="bd631-120">スプラッティングを使用していくつかのパラメーターを渡し、位置またはパラメーター名で他のパラメーターを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="bd631-120">You may pass some parameters by using splatting and pass others by position or by parameter name.</span></span> <span data-ttu-id="bd631-121">また、複数のオブジェクトを1つのコマンドで記号して、各パラメーターに対して複数の値を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="bd631-121">Also, you can splat multiple objects in a single command so you don't pass more than one value for each parameter.</span></span>

## <a name="splatting-with-hash-tables"></a><span data-ttu-id="bd631-122">スプラッティングとハッシュテーブル</span><span class="sxs-lookup"><span data-stu-id="bd631-122">Splatting with hash tables</span></span>

<span data-ttu-id="bd631-123">ハッシュテーブルを使用して、パラメーターの名前と値のペアを記号します。</span><span class="sxs-lookup"><span data-stu-id="bd631-123">Use a hash table to splat parameter name and value pairs.</span></span> <span data-ttu-id="bd631-124">この形式は、位置指定パラメーターやスイッチパラメーターなど、すべてのパラメーターの型に対して使用できます。</span><span class="sxs-lookup"><span data-stu-id="bd631-124">You can use this format for all parameter types, including positional and switch parameters.</span></span>
<span data-ttu-id="bd631-125">位置指定パラメーターは名前で割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd631-125">Positional parameters must be assigned by name.</span></span>

<span data-ttu-id="bd631-126">次の例では、 `Copy-Item` Test.txt ファイルを同じディレクトリ内の Test2.txt ファイルにコピーする2つのコマンドを比較します。</span><span class="sxs-lookup"><span data-stu-id="bd631-126">The following examples compare two `Copy-Item` commands that copy the Test.txt file to the Test2.txt file in the same directory.</span></span>

<span data-ttu-id="bd631-127">最初の例では、パラメーター名が含まれている従来の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd631-127">The first example uses the traditional format in which parameter names are included.</span></span>

```powershell
Copy-Item -Path "test.txt" -Destination "test2.txt" -WhatIf
```

<span data-ttu-id="bd631-128">2番目の例では、ハッシュテーブルスプラッティングを使用します。</span><span class="sxs-lookup"><span data-stu-id="bd631-128">The second example uses hash table splatting.</span></span> <span data-ttu-id="bd631-129">最初のコマンドは、パラメーター名とパラメーター値のペアのハッシュテーブルを作成し、変数に格納し `$HashArguments` ます。</span><span class="sxs-lookup"><span data-stu-id="bd631-129">The first command creates a hash table of parameter-name and parameter-value pairs and stores it in the `$HashArguments` variable.</span></span> <span data-ttu-id="bd631-130">2番目のコマンドは、 `$HashArguments` スプラッティングを使用してコマンド内の変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd631-130">The second command uses the `$HashArguments` variable in a command with splatting.</span></span> <span data-ttu-id="bd631-131">At 記号 () は、 `@HashArguments` コマンドのドル記号 () に代わるもの `$HashArguments` です。</span><span class="sxs-lookup"><span data-stu-id="bd631-131">The At symbol (`@HashArguments`) replaces the dollar sign (`$HashArguments`) in the command.</span></span>

<span data-ttu-id="bd631-132">**WhatIf** スイッチパラメーターの値を指定するには、 `$True` またはを使用 `$False` します。</span><span class="sxs-lookup"><span data-stu-id="bd631-132">To provide a value for the **WhatIf** switch parameter, use `$True` or `$False`.</span></span>

```powershell
$HashArguments = @{
  Path = "test.txt"
  Destination = "test2.txt"
  WhatIf = $true
}
Copy-Item @HashArguments
```

> [!NOTE]
> <span data-ttu-id="bd631-133">最初のコマンドでは、アットマーク ( `@` ) は splatted 値ではなくハッシュテーブルを示します。</span><span class="sxs-lookup"><span data-stu-id="bd631-133">In the first command, the At symbol (`@`) indicates a hash table, not a splatted value.</span></span> <span data-ttu-id="bd631-134">PowerShell のハッシュテーブルの構文は次のとおりです。 `@{<name>=<value>; <name>=<value>; ...}`</span><span class="sxs-lookup"><span data-stu-id="bd631-134">The syntax for hash tables in PowerShell is: `@{<name>=<value>; <name>=<value>; ...}`</span></span>

## <a name="splatting-with-arrays"></a><span data-ttu-id="bd631-135">配列を使用したスプラッティング</span><span class="sxs-lookup"><span data-stu-id="bd631-135">Splatting with arrays</span></span>

<span data-ttu-id="bd631-136">配列を使用して、パラメーター名を必要としない位置指定パラメーターの値を記号します。</span><span class="sxs-lookup"><span data-stu-id="bd631-136">Use an array to splat values for positional parameters, which do not require parameter names.</span></span> <span data-ttu-id="bd631-137">値は、配列内の位置番号の順序で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd631-137">The values must be in position-number order in the array.</span></span>

<span data-ttu-id="bd631-138">次の例では、 `Copy-Item` Test.txt ファイルを同じディレクトリ内の Test2.txt ファイルにコピーする2つのコマンドを比較します。</span><span class="sxs-lookup"><span data-stu-id="bd631-138">The following examples compare two `Copy-Item` commands that copy the Test.txt file to the Test2.txt file in the same directory.</span></span>

<span data-ttu-id="bd631-139">最初の例では、パラメーター名が省略されている従来の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd631-139">The first example uses the traditional format in which parameter names are omitted.</span></span> <span data-ttu-id="bd631-140">パラメーター値は、コマンドの位置の順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd631-140">The parameter values appear in position order in the command.</span></span>

```powershell
Copy-Item "test.txt" "test2.txt" -WhatIf
```

<span data-ttu-id="bd631-141">2番目の例では、配列スプラッティングを使用します。</span><span class="sxs-lookup"><span data-stu-id="bd631-141">The second example uses array splatting.</span></span> <span data-ttu-id="bd631-142">最初のコマンドは、パラメーター値の配列を作成し、変数に格納し `$ArrayArguments` ます。</span><span class="sxs-lookup"><span data-stu-id="bd631-142">The first command creates an array of the parameter values and stores it in the `$ArrayArguments` variable.</span></span> <span data-ttu-id="bd631-143">値は、配列内の位置の順序になっています。</span><span class="sxs-lookup"><span data-stu-id="bd631-143">The values are in position order in the array.</span></span> <span data-ttu-id="bd631-144">2番目のコマンドは、 `$ArrayArguments` スプラッティングのコマンドで変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd631-144">The second command uses the `$ArrayArguments` variable in a command in splatting.</span></span> <span data-ttu-id="bd631-145">At 記号 () は、 `@ArrayArguments` コマンドのドル記号 () に代わるもの `$ArrayArguments` です。</span><span class="sxs-lookup"><span data-stu-id="bd631-145">The At symbol (`@ArrayArguments`) replaces the dollar sign (`$ArrayArguments`) in the command.</span></span>

```powershell
$ArrayArguments = "test.txt", "test2.txt"
Copy-Item @ArrayArguments -WhatIf
```

### <a name="using-the-argumentlist-parameter"></a><span data-ttu-id="bd631-146">ArgumentList パラメーターの使用</span><span class="sxs-lookup"><span data-stu-id="bd631-146">Using the ArgumentList parameter</span></span>

<span data-ttu-id="bd631-147">いくつかのコマンドレットには、コマンドレットによって実行されるスクリプトブロックにパラメーター値を渡すために使用される **ArgumentList** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="bd631-147">Several cmdlets have an **ArgumentList** parameter that is used to pass parameter values to a script block that is executed by the cmdlet.</span></span> <span data-ttu-id="bd631-148">**ArgumentList** パラメーターは、スクリプトブロックに渡される値の配列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="bd631-148">The **ArgumentList** parameter takes an array of values that is passed to the script block.</span></span> <span data-ttu-id="bd631-149">PowerShell は、実際には配列スプラッティングを使用して、値をスクリプトブロックのパラメーターにバインドします。</span><span class="sxs-lookup"><span data-stu-id="bd631-149">PowerShell is effectively using array splatting to bind the values to the parameters of the script block.</span></span> <span data-ttu-id="bd631-150">**ArgumentList** を使用する場合、1つのパラメーターにバインドされた単一のオブジェクトとして配列を渡す必要がある場合は、配列を別の配列の唯一の要素としてラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd631-150">When using **ArgumentList** , if you need to pass an array as a single object bound to a single parameter, you must wrap the array as the only element of another array.</span></span>

<span data-ttu-id="bd631-151">次の例には、文字列の配列である1つのパラメーターを受け取るスクリプトブロックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bd631-151">The following example has a script block that takes a single parameter that is an array of strings.</span></span>

```powershell
$array = 'Hello', 'World!'
Invoke-Command -ScriptBlock {
  param([string[]]$words) $words -join ' '
  } -ArgumentList $array
```

<span data-ttu-id="bd631-152">この例では、の最初の項目だけ `$array` がスクリプトブロックに渡されます。</span><span class="sxs-lookup"><span data-stu-id="bd631-152">In this example, only the first item in `$array` is passed to the script block.</span></span>

```Output
Hello
```

```powershell
$array = 'Hello', 'World!'
Invoke-Command -ScriptBlock {
  param([string[]]$words) $words -join ' '
} -ArgumentList (,$array)
````

<span data-ttu-id="bd631-153">この例では、配列 `$array` 全体が単一のオブジェクトとしてスクリプトブロックに渡されるように、が配列にラップされています。</span><span class="sxs-lookup"><span data-stu-id="bd631-153">In this example, `$array` is wrapped in an array so that the entire array is passed to the script block as a single object.</span></span>

```Output
Hello World!
```

## <a name="examples"></a><span data-ttu-id="bd631-154">例</span><span class="sxs-lookup"><span data-stu-id="bd631-154">Examples</span></span>

<span data-ttu-id="bd631-155">この例では、さまざまなコマンドで splatted 値を再利用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bd631-155">This example shows how to reuse splatted values in different commands.</span></span> <span data-ttu-id="bd631-156">この例のコマンドは、コマンドレットを使用して、 `Write-Host` ホストプログラムコンソールにメッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="bd631-156">The commands in this example use the `Write-Host` cmdlet to write messages to the host program console.</span></span> <span data-ttu-id="bd631-157">スプラッティングを使用して、前景色と背景色を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd631-157">It uses splatting to specify the foreground and background colors.</span></span>

<span data-ttu-id="bd631-158">すべてのコマンドの色を変更するには、変数の値を変更するだけ `$Colors` です。</span><span class="sxs-lookup"><span data-stu-id="bd631-158">To change the colors of all commands, just change the value of the `$Colors` variable.</span></span>

<span data-ttu-id="bd631-159">最初のコマンドは、パラメーター名と値のハッシュテーブルを作成し、そのハッシュテーブルを変数に格納し `$Colors` ます。</span><span class="sxs-lookup"><span data-stu-id="bd631-159">The first command creates a hash table of parameter names and values and stores the hash table in the `$Colors` variable.</span></span>

```powershell
$Colors = @{ForegroundColor = "black"; BackgroundColor = "white"}
```

<span data-ttu-id="bd631-160">2番目と3番目のコマンドは、 `$Colors` コマンドでスプラッティングの変数を使用し `Write-Host` ます。</span><span class="sxs-lookup"><span data-stu-id="bd631-160">The second and third commands use the `$Colors` variable for splatting in a `Write-Host` command.</span></span> <span data-ttu-id="bd631-161">を使用するには `$Colors variable` 、ドル記号 ( `$Colors` ) をアットマーク () に置き換え `@Colors` ます。</span><span class="sxs-lookup"><span data-stu-id="bd631-161">To use the `$Colors variable`, replace the dollar sign (`$Colors`) with an At symbol (`@Colors`).</span></span>

```powershell
#Write a message with the colors in $Colors
Write-Host "This is a test." @Colors

#Write second message with same colors. The position of splatted
#hash table does not matter.
Write-Host @Colors "This is another test."
```

<span data-ttu-id="bd631-162">この例では、スプラッティングと自動変数を使用して、他のコマンドにパラメーターを転送する方法を示し `$PSBoundParameters` ます。</span><span class="sxs-lookup"><span data-stu-id="bd631-162">This example shows how to forward their parameters to other commands by using splatting and the `$PSBoundParameters` automatic variable.</span></span>

<span data-ttu-id="bd631-163">`$PSBoundParameters`自動変数は、スクリプトまたは関数の実行時に使用されるすべてのパラメーター名と値を含むディクショナリオブジェクト (system.string) です。</span><span class="sxs-lookup"><span data-stu-id="bd631-163">The `$PSBoundParameters` automatic variable is a dictionary object (System.Collections.Generic.Dictionary) that contains all the parameter names and values that are used when a script or function is run.</span></span>

<span data-ttu-id="bd631-164">次の例では、変数を使用して、 `$PSBoundParameters` スクリプトまたは関数に渡されたパラメーター値を関数から `Test2` 関数に転送し `Test1` ます。</span><span class="sxs-lookup"><span data-stu-id="bd631-164">In the following example, we use the `$PSBoundParameters` variable to forward the parameters values passed to a script or function from `Test2` function to the `Test1` function.</span></span> <span data-ttu-id="bd631-165">から関数を呼び出すと、 `Test1` `Test2` スプラッティングが使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd631-165">Both calls to the `Test1` function from `Test2` use splatting.</span></span>

```powershell
function Test1
{
    param($a, $b, $c)

    $a
    $b
    $c
}

function Test2
{
    param($a, $b, $c)

    #Call the Test1 function with $a, $b, and $c.
    Test1 @PsBoundParameters

    #Call the Test1 function with $b and $c, but not with $a
    $LimitedParameters = $PSBoundParameters
    $LimitedParameters.Remove("a") | Out-Null
    Test1 @LimitedParameters
}
```

```Output
Test2 -a 1 -b 2 -c 3
1
2
3
2
3
```

## <a name="splatting-command-parameters"></a><span data-ttu-id="bd631-166">スプラッティングコマンドのパラメーター</span><span class="sxs-lookup"><span data-stu-id="bd631-166">Splatting command parameters</span></span>

<span data-ttu-id="bd631-167">スプラッティングを使用して、コマンドのパラメーターを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="bd631-167">You can use splatting to represent the parameters of a command.</span></span> <span data-ttu-id="bd631-168">この手法は、プロキシ関数、つまり別のコマンドを呼び出す関数を作成するときに便利です。</span><span class="sxs-lookup"><span data-stu-id="bd631-168">This technique is useful when you are creating a proxy function, that is, a function that calls another command.</span></span> <span data-ttu-id="bd631-169">この機能は、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="bd631-169">This feature is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="bd631-170">コマンドのパラメーターを記号するには、 `@Args` を使用してコマンドパラメーターを表します。</span><span class="sxs-lookup"><span data-stu-id="bd631-170">To splat the parameters of a command, use `@Args` to represent the command parameters.</span></span> <span data-ttu-id="bd631-171">この手法は、コマンドパラメーターを列挙するよりも簡単です。呼び出されたコマンドのパラメーターが変更された場合でも、リビジョンなしで動作します。</span><span class="sxs-lookup"><span data-stu-id="bd631-171">This technique is easier than enumerating command parameters and it works without revision even if the parameters of the called command change.</span></span>

<span data-ttu-id="bd631-172">この機能は、 `$Args` 割り当てられていないすべてのパラメーター値を含む自動変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd631-172">The feature uses the `$Args` automatic variable, which contains all unassigned parameter values.</span></span>

<span data-ttu-id="bd631-173">たとえば、次の関数は、 `Get-Process` コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="bd631-173">For example, the following function calls the `Get-Process` cmdlet.</span></span> <span data-ttu-id="bd631-174">この関数では、は、 `@Args` コマンドレットのすべてのパラメーターを表し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="bd631-174">In this function, `@Args` represents all the parameters of the `Get-Process` cmdlet.</span></span>

```powershell
function Get-MyProcess { Get-Process @Args }
```

<span data-ttu-id="bd631-175">関数を使用すると、 `Get-MyProcess` 次のコマンドに示すように、割り当てられていないすべてのパラメーターとパラメーター値がに渡され `@Args` ます。</span><span class="sxs-lookup"><span data-stu-id="bd631-175">When you use the `Get-MyProcess` function, all unassigned parameters and parameter values are passed to `@Args`, as shown in the following commands.</span></span>

```powershell
Get-MyProcess -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    463      46   225484     237196   719    15.86   3228 powershell
```

```powershell
Get-MyProcess -Name PowerShell_Ise -FileVersionInfo
```

```Output
ProductVersion   FileVersion      FileName
--------------   -----------      --------
6.2.9200.16384   6.2.9200.1638... C:\Windows\system32\WindowsPowerShell\...
```

<span data-ttu-id="bd631-176">`@Args`パラメーターを明示的に宣言した関数でを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bd631-176">You can use `@Args` in a function that has explicitly declared parameters.</span></span> <span data-ttu-id="bd631-177">関数内で複数回使用できますが、 `@Args` 次の例に示すように、入力したすべてのパラメーターがのすべてのインスタンスに渡されます。</span><span class="sxs-lookup"><span data-stu-id="bd631-177">You can use it more than once in a function, but all parameters that you enter are passed to all instances of `@Args`, as shown in the following example.</span></span>

```powershell
function Get-MyCommand
{
    Param ([switch]$P, [switch]$C)
    if ($P) { Get-Process @Args }
    if ($C) { Get-Command @Args }
}

Get-MyCommand -P -C -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
408      28    75568      83176   620     1.33   1692 powershell

Path               : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.e
Extension          : .exe
Definition         : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.e
Visibility         : Public
OutputType         : {System.String}
Name               : powershell.exe
CommandType        : Application
ModuleName         :
Module             :
RemotingCapability : PowerShell
Parameters         :
ParameterSets      :
HelpUri            :
FileVersionInfo    : File:             C:\Windows\System32\WindowsPowerShell
                     \v1.0\powershell.exe
                     InternalName:     POWERSHELL
                     OriginalFilename: PowerShell.EXE.MUI
                     FileVersion:      10.0.14393.0 (rs1_release.160715-1616
                     FileDescription:  Windows PowerShell
                     Product:          Microsoft Windows Operating System
                     ProductVersion:   10.0.14393.0
                     Debug:            False
                     Patched:          False
                     PreRelease:       False
                     PrivateBuild:     False
                     SpecialBuild:     False
                     Language:         English (United States)
```

## <a name="notes"></a><span data-ttu-id="bd631-178">メモ</span><span class="sxs-lookup"><span data-stu-id="bd631-178">Notes</span></span>

<span data-ttu-id="bd631-179">構成 **属性またはパラメーター属性を使用** して関数を高度な関数に **Parameter** すると、 `$args` 自動変数は関数で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="bd631-179">If you make a function into an advanced function by using either the **CmdletBinding** or **Parameter** attributes, the `$args` automatic variable is no longer available in the function.</span></span> <span data-ttu-id="bd631-180">高度な関数には、明示的なパラメーター定義が必要です。</span><span class="sxs-lookup"><span data-stu-id="bd631-180">Advanced functions require explicit parameter definition.</span></span>

<span data-ttu-id="bd631-181">PowerShell Desired State Configuration (DSC) は、スプラッティングを使用するように設計されていません。</span><span class="sxs-lookup"><span data-stu-id="bd631-181">PowerShell Desired State Configuration (DSC) was not designed to use splatting.</span></span>
<span data-ttu-id="bd631-182">スプラッティングを使用して、DSC リソースに値を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="bd631-182">You cannot use splatting to pass values into a DSC resource.</span></span> <span data-ttu-id="bd631-183">詳細については、「 [スプラッティング DSC リソース](https://gaelcolas.com/2017/11/05/pseudo-splatting-dsc-resources/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd631-183">For more information, see Gael Colas' article [Pseudo-Splatting DSC Resources](https://gaelcolas.com/2017/11/05/pseudo-splatting-dsc-resources/).</span></span>

## <a name="see-also"></a><span data-ttu-id="bd631-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd631-184">See also</span></span>

[<span data-ttu-id="bd631-185">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="bd631-185">about_Arrays</span></span>](about_Arrays.md)

[<span data-ttu-id="bd631-186">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="bd631-186">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="bd631-187">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="bd631-187">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="bd631-188">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="bd631-188">about_Parameters</span></span>](about_Parameters.md)
