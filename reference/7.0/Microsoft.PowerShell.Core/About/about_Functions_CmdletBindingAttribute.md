---
description: 関数をコンパイル済みのコマンドレットのように機能させるための属性について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_CmdletBindingAttribute
ms.openlocfilehash: 816bee647702fca4a2b9196491b2525f0338ab31
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222288"
---
# <a name="about-functions-cmdletbindingattribute"></a><span data-ttu-id="a34fc-104">関数のバージョン情報の属性</span><span class="sxs-lookup"><span data-stu-id="a34fc-104">About Functions CmdletBindingAttribute</span></span>

## <a name="short-description"></a><span data-ttu-id="a34fc-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="a34fc-105">Short description</span></span>
<span data-ttu-id="a34fc-106">関数をコンパイル済みのコマンドレットのように機能させるための属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="a34fc-106">Describes the attribute that makes a function work like a compiled cmdlet.</span></span>

## <a name="long-description"></a><span data-ttu-id="a34fc-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="a34fc-107">Long description</span></span>

<span data-ttu-id="a34fc-108">`CmdletBinding`属性は、C# で記述されたコンパイル済みコマンドレットのように動作する関数の属性です。</span><span class="sxs-lookup"><span data-stu-id="a34fc-108">The `CmdletBinding` attribute is an attribute of functions that makes them operate like compiled cmdlets written in C#.</span></span> <span data-ttu-id="a34fc-109">コマンドレットの機能へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="a34fc-109">It provides access to the features of cmdlets.</span></span>

<span data-ttu-id="a34fc-110">PowerShell は、コンパイルされた `CmdletBinding` コマンドレットのパラメーターをバインドするのと同じ方法で、属性を持つ関数のパラメーターをバインドします。</span><span class="sxs-lookup"><span data-stu-id="a34fc-110">PowerShell binds the parameters of functions that have the `CmdletBinding` attribute in the same way that it binds the parameters of compiled cmdlets.</span></span> <span data-ttu-id="a34fc-111">`$PSCmdlet`属性を持つ関数では自動変数を使用できますが、 `CmdletBinding` 変数は使用でき `$Args` ません。</span><span class="sxs-lookup"><span data-stu-id="a34fc-111">The `$PSCmdlet` automatic variable is available to functions with the `CmdletBinding` attribute, but the `$Args` variable is not available.</span></span>

<span data-ttu-id="a34fc-112">属性を持つ関数では `CmdletBinding` 、位置パラメーターが一致しない不明なパラメーターおよび位置指定引数によって、パラメーターのバインドが失敗します。</span><span class="sxs-lookup"><span data-stu-id="a34fc-112">In functions that have the `CmdletBinding` attribute, unknown parameters and positional arguments that have no matching positional parameters cause parameter binding to fail.</span></span>

> [!NOTE]
> <span data-ttu-id="a34fc-113">コンパイルされたコマンドレットは required 属性を使用し `Cmdlet` `CmdletBinding` ます。これは、このトピックで説明されている属性に似ています。</span><span class="sxs-lookup"><span data-stu-id="a34fc-113">Compiled cmdlets use the required `Cmdlet` attribute, which is similar to the `CmdletBinding` attribute that is described in this topic.</span></span>

## <a name="syntax"></a><span data-ttu-id="a34fc-114">構文</span><span class="sxs-lookup"><span data-stu-id="a34fc-114">Syntax</span></span>

<span data-ttu-id="a34fc-115">次の例は、属性のすべての省略可能な引数を指定する関数の形式を示して `CmdletBinding` います。</span><span class="sxs-lookup"><span data-stu-id="a34fc-115">The following example shows the format of a function that specifies all the optional arguments of the `CmdletBinding` attribute.</span></span> <span data-ttu-id="a34fc-116">各引数の簡単な説明を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a34fc-116">A brief description of each argument follows this example.</span></span>

```powershell
{
    [CmdletBinding(ConfirmImpact=<String>,
    DefaultParameterSetName=<String>,
    HelpURI=<URI>,
    SupportsPaging=<Boolean>,
    SupportsShouldProcess=<Boolean>,
    PositionalBinding=<Boolean>)]

    Param ($Parameter1)
    Begin{}
    Process{}
    End{}
}
```

## <a name="confirmimpact"></a><span data-ttu-id="a34fc-117">ConfirmImpact</span><span class="sxs-lookup"><span data-stu-id="a34fc-117">ConfirmImpact</span></span>

<span data-ttu-id="a34fc-118">**Confirmimpact** **引数は、メソッドの** 呼び出しによって関数のアクションを確認するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="a34fc-118">The **ConfirmImpact** argument specifies when the action of the function should be confirmed by a call to the **ShouldProcess** method.</span></span> <span data-ttu-id="a34fc-119">値を指定する **メソッドを** 呼び出すと、 **confirmimpact** 引数がユーザー設定変数の値以上の場合にのみ、確認プロンプトが表示され `$ConfirmPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="a34fc-119">The call to the **ShouldProcess** method displays a confirmation prompt only when the **ConfirmImpact** argument is equal to or greater than the value of the `$ConfirmPreference` preference variable.</span></span> <span data-ttu-id="a34fc-120">(引数の既定値は **Medium** です)。この引数は、 **supports指定** の引数も指定されている場合にのみ指定します。</span><span class="sxs-lookup"><span data-stu-id="a34fc-120">(The default value of the argument is **Medium**.) Specify this argument only when the **SupportsShouldProcess** argument is also specified.</span></span>

<span data-ttu-id="a34fc-121">確認要求の詳細については、「 [確認の要求](/powershell/scripting/developer/cmdlet/requesting-confirmation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a34fc-121">For more information about confirmation requests, see [Requesting Confirmation](/powershell/scripting/developer/cmdlet/requesting-confirmation).</span></span>

## <a name="defaultparametersetname"></a><span data-ttu-id="a34fc-122">DefaultParameterSetName</span><span class="sxs-lookup"><span data-stu-id="a34fc-122">DefaultParameterSetName</span></span>

<span data-ttu-id="a34fc-123">**DefaultParameterSetName** 引数には、使用するパラメーターセットを決定できない場合に PowerShell が使用するパラメーターセットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a34fc-123">The **DefaultParameterSetName** argument specifies the name of the parameter set that PowerShell will attempt to use when it cannot determine which parameter set to use.</span></span> <span data-ttu-id="a34fc-124">この問題を回避するには、各パラメーターの unique パラメーターに必須パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="a34fc-124">You can avoid this issue by making the unique parameter of each parameter set a mandatory parameter.</span></span>

## <a name="helpuri"></a><span data-ttu-id="a34fc-125">HelpURI</span><span class="sxs-lookup"><span data-stu-id="a34fc-125">HelpURI</span></span>

<span data-ttu-id="a34fc-126">この **引数は、関数** について説明するヘルプトピックのオンラインバージョンのインターネットアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a34fc-126">The **HelpURI** argument specifies the internet address of the online version of the help topic that describes the function.</span></span> <span data-ttu-id="a34fc-127">パラメーターの値は **、"** http" または "https" で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a34fc-127">The value of the **HelpURI** argument must begin with "http" or "https".</span></span>

<span data-ttu-id="a34fc-128">パラメーター **の値は、** 関数に対してを返す **commandinfo** オブジェクト **のプロパティの** 値に使用され `Get-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="a34fc-128">The **HelpURI** argument value is used for the value of the **HelpURI** property of the **CommandInfo** object that `Get-Command` returns for the function.</span></span>

<span data-ttu-id="a34fc-129">ただし、ヘルプファイルがコンピューターにインストールされていて、ヘルプファイルの [関連 **リンク** ] セクションの最初のリンクの値が uri である場合、またはコメントベースのヘルプの最初のディレクティブの値が uri である場合は、 `.Link` ヘルプファイル内の uri が **HelpUri** 関数のすべてのプロパティの値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="a34fc-129">However, when help files are installed on the computer and the value of the first link in the **RelatedLinks** section of the help file is a URI, or the value of the first `.Link` directive in comment-based help is a URI, the URI in the help file is used as the value of the **HelpUri** property of the function.</span></span>

<span data-ttu-id="a34fc-130">コマンドレットでは、 `Get-Help` コマンドで **HelpURI** の **online** パラメーターが指定されている場合に、関数ヘルプトピックのオンラインバージョンを検索するために、の値を使用し `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="a34fc-130">The `Get-Help` cmdlet uses the value of the **HelpURI** property to locate the online version of the function help topic when the **Online** parameter of `Get-Help` is specified in a command.</span></span>

## <a name="supportspaging"></a><span data-ttu-id="a34fc-131">SupportsPaging</span><span class="sxs-lookup"><span data-stu-id="a34fc-131">SupportsPaging</span></span>

<span data-ttu-id="a34fc-132">**Supportspaging** 引数は、関数に **First** 、 **Skip** 、および **includetotalcount** パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="a34fc-132">The **SupportsPaging** argument adds the **First** , **Skip** , and **IncludeTotalCount** parameters to the function.</span></span> <span data-ttu-id="a34fc-133">これらのパラメーターを使用すると、ユーザーは非常に大きな結果セットから出力を選択できます。</span><span class="sxs-lookup"><span data-stu-id="a34fc-133">These parameters allow users to select output from a very large result set.</span></span> <span data-ttu-id="a34fc-134">この引数は、SQL データベースなどのデータ選択をサポートする大規模なデータストアからデータを返すコマンドレットと関数用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="a34fc-134">This argument is designed for cmdlets and functions that return data from large data stores that support data selection, such as an SQL database.</span></span>

<span data-ttu-id="a34fc-135">この引数は、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a34fc-135">This argument was introduced in Windows PowerShell 3.0.</span></span>

- <span data-ttu-id="a34fc-136">**First** : 最初の ' n ' 個のオブジェクトのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="a34fc-136">**First** : Gets only the first 'n' objects.</span></span>
- <span data-ttu-id="a34fc-137">**Skip** : 最初の ' n ' 個のオブジェクトを無視し、残りのオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="a34fc-137">**Skip** :  Ignores the first 'n' objects and then gets the remaining objects.</span></span>
- <span data-ttu-id="a34fc-138">**Includetotalcount** : データセット内のオブジェクト (整数) の後にオブジェクトの数を報告します。</span><span class="sxs-lookup"><span data-stu-id="a34fc-138">**IncludeTotalCount** : Reports the number of objects in the data set (an integer) followed by the objects.</span></span> <span data-ttu-id="a34fc-139">コマンドレットが合計数を判別できない場合は、"Unknown total count" を返します。</span><span class="sxs-lookup"><span data-stu-id="a34fc-139">If the cmdlet cannot determine the total count, it returns "Unknown total count".</span></span>

<span data-ttu-id="a34fc-140">PowerShell には **Newtotalcount** が含まれています。これは、返される合計数の値を取得するヘルパーメソッドで、合計数の値の推定精度を含みます。</span><span class="sxs-lookup"><span data-stu-id="a34fc-140">PowerShell includes **NewTotalCount** , a helper method that gets the total count value to return and includes an estimate of the accuracy of the total count value.</span></span>

<span data-ttu-id="a34fc-141">次のサンプル関数は、ページングパラメーターのサポートを高度な関数に追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a34fc-141">The following sample function shows how to add support for the paging parameters to an advanced function.</span></span>

```powershell
function Get-Numbers {
    [CmdletBinding(SupportsPaging = $true)]
    param()

    $FirstNumber = [Math]::Min($PSCmdlet.PagingParameters.Skip, 100)
    $LastNumber = [Math]::Min($PSCmdlet.PagingParameters.First +
      $FirstNumber - 1, 100)

    if ($PSCmdlet.PagingParameters.IncludeTotalCount) {
        $TotalCountAccuracy = 1.0
        $TotalCount = $PSCmdlet.PagingParameters.NewTotalCount(100,
          $TotalCountAccuracy)
        Write-Output $TotalCount
    }
    $FirstNumber .. $LastNumber | Write-Output
}
```

## <a name="supportsshouldprocess"></a><span data-ttu-id="a34fc-142">SupportsShouldProcess</span><span class="sxs-lookup"><span data-stu-id="a34fc-142">SupportsShouldProcess</span></span>

<span data-ttu-id="a34fc-143">**Supports指定処理** 引数は、 **Confirm** パラメーターと **WhatIf** パラメーターを関数に追加します。</span><span class="sxs-lookup"><span data-stu-id="a34fc-143">The **SupportsShouldProcess** argument adds **Confirm** and **WhatIf** parameters to the function.</span></span> <span data-ttu-id="a34fc-144">**Confirm** パラメーターは、パイプライン内の各オブジェクトに対してコマンドを実行する前に、ユーザーにプロンプトを表示します。</span><span class="sxs-lookup"><span data-stu-id="a34fc-144">The **Confirm** parameter prompts the user before it runs the command on each object in the pipeline.</span></span> <span data-ttu-id="a34fc-145">**WhatIf** パラメーターは、コマンドを実行するのではなく、コマンドによって実行される変更を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="a34fc-145">The **WhatIf** parameter lists the changes that the command would make, instead of running the command.</span></span>

## <a name="positionalbinding"></a><span data-ttu-id="a34fc-146">PositionalBinding</span><span class="sxs-lookup"><span data-stu-id="a34fc-146">PositionalBinding</span></span>

<span data-ttu-id="a34fc-147">**Positionalbinding** 引数は、関数内のパラメーターが既定で位置指定されているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="a34fc-147">The **PositionalBinding** argument determines whether parameters in the function are positional by default.</span></span> <span data-ttu-id="a34fc-148">既定値は `$True` です。</span><span class="sxs-lookup"><span data-stu-id="a34fc-148">The default value is `$True`.</span></span> <span data-ttu-id="a34fc-149">位置指定バインドを無効にするには、 **Positionalbinding** 引数を値と共に使用し `$False` ます。</span><span class="sxs-lookup"><span data-stu-id="a34fc-149">You can use the **PositionalBinding** argument with a value of `$False` to disable positional binding.</span></span>

<span data-ttu-id="a34fc-150">**Positionalbinding** 引数は、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a34fc-150">The **PositionalBinding** argument is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="a34fc-151">パラメーターが位置指定の場合、パラメーター名は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a34fc-151">When parameters are positional, the parameter name is optional.</span></span>
<span data-ttu-id="a34fc-152">PowerShell では、関数コマンド内の名前のないパラメーター値の順序や位置に従って、名前のないパラメーター値が関数パラメーターに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="a34fc-152">PowerShell associates unnamed parameter values with the function parameters according to the order or position of the unnamed parameter values in the function command.</span></span>

<span data-ttu-id="a34fc-153">パラメーターが位置指定されていない場合 ("名前付き" の場合)、コマンドにパラメーター名 (または名前の省略形または別名) が必要です。</span><span class="sxs-lookup"><span data-stu-id="a34fc-153">When parameters are not positional (they are "named"), the parameter name (or an abbreviation or alias of the name) is required in the command.</span></span>

<span data-ttu-id="a34fc-154">**Positionalbinding** がの場合 `$True` 、関数のパラメーターは既定で位置指定されます。</span><span class="sxs-lookup"><span data-stu-id="a34fc-154">When **PositionalBinding** is `$True`, function parameters are positional by default.</span></span> <span data-ttu-id="a34fc-155">PowerShell では、関数内で宣言されている順序で、パラメーターに位置番号が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="a34fc-155">PowerShell assigns position number to the parameters in the order in which they are declared in the function.</span></span>

<span data-ttu-id="a34fc-156">**Positionalbinding** がの場合 `$False` 、関数のパラメーターは既定では位置指定されません。</span><span class="sxs-lookup"><span data-stu-id="a34fc-156">When **PositionalBinding** is `$False`, function parameters are not positional by default.</span></span> <span data-ttu-id="a34fc-157">**パラメーター属性の** **Position** 引数がパラメーターで宣言されている場合を除き、パラメーターを関数で使用するときは、パラメーター名 (または別名または省略形) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a34fc-157">Unless the **Position** argument of the **Parameter** attribute is declared on the parameter, the parameter name (or an alias or abbreviation) must be included when the parameter is used in a function.</span></span>

<span data-ttu-id="a34fc-158">**Parameter** 属性の **Position** 引数は、 **positionalbinding** の既定値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="a34fc-158">The **Position** argument of the **Parameter** attribute takes precedence over the **PositionalBinding** default value.</span></span> <span data-ttu-id="a34fc-159">**Position** 引数を使用して、パラメーターの位置の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a34fc-159">You can use the **Position** argument to specify a position value for a parameter.</span></span> <span data-ttu-id="a34fc-160">**Position** 引数の詳細については、「 [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a34fc-160">For more information about the **Position** argument, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

## <a name="notes"></a><span data-ttu-id="a34fc-161">メモ</span><span class="sxs-lookup"><span data-stu-id="a34fc-161">Notes</span></span>

<span data-ttu-id="a34fc-162">**SupportsTransactions** 引数は、高度な関数ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a34fc-162">The **SupportsTransactions** argument is not supported in advanced functions.</span></span>

## <a name="keywords"></a><span data-ttu-id="a34fc-163">Keywords</span><span class="sxs-lookup"><span data-stu-id="a34fc-163">Keywords</span></span>

<span data-ttu-id="a34fc-164">about_Functions_CmdletBinding_Attribute</span><span class="sxs-lookup"><span data-stu-id="a34fc-164">about_Functions_CmdletBinding_Attribute</span></span>

## <a name="see-also"></a><span data-ttu-id="a34fc-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="a34fc-165">See also</span></span>

[<span data-ttu-id="a34fc-166">about_Functions</span><span class="sxs-lookup"><span data-stu-id="a34fc-166">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="a34fc-167">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="a34fc-167">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="a34fc-168">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="a34fc-168">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="a34fc-169">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="a34fc-169">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="a34fc-170">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="a34fc-170">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)
