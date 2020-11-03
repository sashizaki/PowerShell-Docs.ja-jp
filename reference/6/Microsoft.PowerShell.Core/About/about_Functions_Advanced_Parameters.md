---
description: 高度な関数にパラメーターを追加する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced_parameters?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced_Parameters
ms.openlocfilehash: 1d33fcd6ccb665ceae1db91783542385fd49b9cc
ms.sourcegitcommit: 3b1779890f828130a9d73aebf17ebffae511728f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "93225256"
---
# <a name="about-functions-advanced-parameters"></a><span data-ttu-id="47bf0-104">関数の詳細パラメーターの概要</span><span class="sxs-lookup"><span data-stu-id="47bf0-104">About Functions Advanced Parameters</span></span>

## <a name="short-description"></a><span data-ttu-id="47bf0-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="47bf0-105">Short description</span></span>

<span data-ttu-id="47bf0-106">高度な関数にパラメーターを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-106">Explains how to add parameters to advanced functions.</span></span>

## <a name="long-description"></a><span data-ttu-id="47bf0-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="47bf0-107">Long description</span></span>

<span data-ttu-id="47bf0-108">記述する高度な関数にパラメーターを追加し、パラメーターの属性と引数を使用して、ユーザーがパラメーターを使用して送信するパラメーターの値を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-108">You can add parameters to the advanced functions that you write, and use parameter attributes and arguments to limit the parameter values that function users submit with the parameter.</span></span>

<span data-ttu-id="47bf0-109">関数に追加するパラメーターは、PowerShell がすべてのコマンドレットと高度な関数に自動的に追加する共通パラメーターに加えて、ユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-109">The parameters that you add to your function are available to users in addition to the common parameters that PowerShell adds automatically to all cmdlets and advanced functions.</span></span> <span data-ttu-id="47bf0-110">PowerShell の共通パラメーターの詳細については、「 [about_CommonParameters](about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47bf0-110">For more information about the PowerShell common parameters, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="47bf0-111">PowerShell 3.0 以降では、スプラッティングをと共に使用して、コマンドのパラメーターを表すことができ `@Args` ます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-111">Beginning in PowerShell 3.0, you can use splatting with `@Args` to represent the parameters in a command.</span></span> <span data-ttu-id="47bf0-112">スプラッティングは、単純関数と高度な関数で有効です。</span><span class="sxs-lookup"><span data-stu-id="47bf0-112">Splatting is valid on simple and advanced functions.</span></span> <span data-ttu-id="47bf0-113">詳細については、「 [about_Functions](about_Functions.md) 」および「 [about_Splatting](about_Splatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47bf0-113">For more information, see [about_Functions](about_Functions.md) and [about_Splatting](about_Splatting.md).</span></span>

## <a name="type-conversion-of-parameter-values"></a><span data-ttu-id="47bf0-114">パラメーター値の型変換</span><span class="sxs-lookup"><span data-stu-id="47bf0-114">Type conversion of parameter values</span></span>

<span data-ttu-id="47bf0-115">異なる型を想定するパラメーターの引数として文字列を指定すると、PowerShell は文字列をパラメーターのターゲット型に暗黙的に変換します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-115">When you supply strings as arguments to parameters that expect a different type, PowerShell implicitly converts the strings to the parameter target type.</span></span>
<span data-ttu-id="47bf0-116">高度な関数は、カルチャに依存しないパラメーター値の解析を実行します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-116">Advanced functions perform culture-invariant parsing of parameter values.</span></span>

<span data-ttu-id="47bf0-117">これに対し、カルチャに依存した変換は、コンパイル済みのコマンドレットのパラメーターバインド中に実行されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-117">By contrast, a culture-sensitive conversion is performed during parameter binding for compiled cmdlets.</span></span>

<span data-ttu-id="47bf0-118">この例では、パラメーターを受け取るコマンドレットとスクリプト関数を作成し `[datetime]` ます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-118">In this example, we create a cmdlet and a script function that take a `[datetime]` parameter.</span></span> <span data-ttu-id="47bf0-119">現在のカルチャはドイツ語の設定を使用するように変更されています。</span><span class="sxs-lookup"><span data-stu-id="47bf0-119">The current culture is changed to use German settings.</span></span>
<span data-ttu-id="47bf0-120">ドイツ語形式の日付がパラメーターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-120">A German-formatted date is passed to the parameter.</span></span>

```powershell
# Create a cmdlet that accepts a [datetime] argument.
Add-Type @'
  using System;
  using System.Management.Automation;
  [Cmdlet("Get", "Date_Cmdlet")]
  public class GetFooCmdlet : Cmdlet {

    [Parameter(Position=0)]
    public DateTime Date { get; set; }

    protected override void ProcessRecord() {
      WriteObject(Date);
    }
  }
'@ -PassThru | % Assembly | Import-Module

[cultureinfo]::CurrentCulture = 'de-DE'
$dateStr = '19-06-2018'

Get-Date_Cmdlet $dateStr
```

```Output
Dienstag, 19. Juni 2018 00:00:00
```

<span data-ttu-id="47bf0-121">上記のように、コマンドレットでは、カルチャに依存した解析を使用して文字列を変換します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-121">As shown above, cmdlets use culture-sensitive parsing to convert the string.</span></span>

```powershell
# Define an equivalent function.
function Get-Date_Func {
  param(
    [DateTime] $Date
  )
  process {
    $Date
  }
}

[cultureinfo]::CurrentCulture = 'de-DE'

# This German-format date string doesn't work with the invariant culture.
# E.g., [datetime] '19-06-2018' breaks.
$dateStr = '19-06-2018'

Get-Date_Func $dateStr
```

<span data-ttu-id="47bf0-122">高度な関数では、カルチャに依存しない解析が使用されるため、次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-122">Advanced functions use culture-invariant parsing, which results in the following error.</span></span>

```Output
Get-Date_Func : Cannot process argument transformation on parameter 'Date'. Cannot convert
 value "19-06-2018" to type "System.DateTime". Error: "String was not recognized as a valid
 DateTime."
At line:13 char:15
+ Get-Date_Func $dateStr
+               ~~~~~~~~
    + CategoryInfo          : InvalidData: (:) [Get-Date_Func], ParameterBindingArgumentTransformationException
    + FullyQualifiedErrorId : ParameterArgumentTransformationError,Get-Date_Func
```

## <a name="static-parameters"></a><span data-ttu-id="47bf0-123">静的パラメーター</span><span class="sxs-lookup"><span data-stu-id="47bf0-123">Static parameters</span></span>

<span data-ttu-id="47bf0-124">静的パラメーターは、関数で常に使用できるパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="47bf0-124">Static parameters are parameters that are always available in the function.</span></span>
<span data-ttu-id="47bf0-125">PowerShell コマンドレットとスクリプトのほとんどのパラメーターは静的パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="47bf0-125">Most parameters in PowerShell cmdlets and scripts are static parameters.</span></span>

<span data-ttu-id="47bf0-126">次の例は、次の特性を持つ **ComputerName** パラメーターの宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="47bf0-126">The following example shows the declaration of a **ComputerName** parameter that has the following characteristics:</span></span>

- <span data-ttu-id="47bf0-127">必須です (必須)。</span><span class="sxs-lookup"><span data-stu-id="47bf0-127">It's mandatory (required).</span></span>
- <span data-ttu-id="47bf0-128">パイプラインからの入力を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-128">It takes input from the pipeline.</span></span>
- <span data-ttu-id="47bf0-129">文字列の配列を入力として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-129">It takes an array of strings as input.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipeline=$true)]
    [String[]]
    $ComputerName
)
```

## <a name="attributes-of-parameters"></a><span data-ttu-id="47bf0-130">パラメーターの属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-130">Attributes of parameters</span></span>

<span data-ttu-id="47bf0-131">ここでは、関数のパラメーターに追加できる属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-131">This section describes the attributes that you can add to function parameters.</span></span>

<span data-ttu-id="47bf0-132">すべての属性は省略できます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-132">All attributes are optional.</span></span> <span data-ttu-id="47bf0-133">ただし、この属性を省略 **した場合** 、高度な関数として認識されるようにするには、関数に **パラメーター** 属性を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-133">However, if you omit the **CmdletBinding** attribute, then to be recognized as an advanced function, the function must include the **Parameter** attribute.</span></span>

<span data-ttu-id="47bf0-134">各パラメーター宣言には、1つまたは複数の属性を追加できます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-134">You can add one or multiple attributes in each parameter declaration.</span></span> <span data-ttu-id="47bf0-135">パラメーター宣言に追加できる属性の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="47bf0-135">There's no limit to the number of attributes that you can add to a parameter declaration.</span></span>

### <a name="parameter-attribute"></a><span data-ttu-id="47bf0-136">パラメーター属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-136">Parameter attribute</span></span>

<span data-ttu-id="47bf0-137">**パラメーター** 属性は、関数パラメーターの属性を宣言するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-137">The **Parameter** attribute is used to declare the attributes of function parameters.</span></span>

<span data-ttu-id="47bf0-138">**Parameter** 属性は省略可能です。関数のどのパラメーターにも属性が必要ない場合は、省略できます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-138">The **Parameter** attribute is optional, and you can omit it if none of the parameters of your functions need attributes.</span></span> <span data-ttu-id="47bf0-139">しかし、単純な関数ではなく、高度な関数として認識されるようにするには、関数には、"属性 **" 属性また** は " **Parameter** " 属性またはその両方を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-139">But, to be recognized as an advanced function, rather than a simple function, a function must have either the **CmdletBinding** attribute or the **Parameter** attribute, or both.</span></span>

<span data-ttu-id="47bf0-140">Parameter **属性に** は、パラメーターが必須か省略可能かなど、パラメーターの特性を定義する引数があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-140">The **Parameter** attribute has arguments that define the characteristics of the parameter, such as whether the parameter is mandatory or optional.</span></span>

<span data-ttu-id="47bf0-141">**パラメーター** 属性、引数、および引数値を宣言するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-141">Use the following syntax to declare the **Parameter** attribute, an argument, and an argument value.</span></span> <span data-ttu-id="47bf0-142">引数とその値を囲むかっこは、余分なスペースを含まない **パラメーター** の後に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-142">The parentheses that enclose the argument and its value must follow **Parameter** with no intervening space.</span></span>

```powershell
Param(
    [Parameter(Argument=value)]
    $ParameterName
)
```

<span data-ttu-id="47bf0-143">かっこ内で引数を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-143">Use commas to separate arguments within the parentheses.</span></span> <span data-ttu-id="47bf0-144">**パラメーター** 属性の2つの引数を宣言するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-144">Use the following syntax to declare two arguments of the **Parameter** attribute.</span></span>

```powershell
Param(
    [Parameter(Argument1=value1,
    Argument2=value2)]
)
```

<span data-ttu-id="47bf0-145">**Parameter 属性から** 省略した場合、 **parameter** 属性のブール型引数の既定値は **False** になります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-145">The boolean argument types of the **Parameter** attribute default to **False** when omitted from the **Parameter** attribute.</span></span> <span data-ttu-id="47bf0-146">引数の値をに設定し `$true` ます。または、引数を名前で一覧表示するだけです。</span><span class="sxs-lookup"><span data-stu-id="47bf0-146">Set the argument value to `$true` or just list the argument by name.</span></span> <span data-ttu-id="47bf0-147">たとえば、次の **パラメーター** 属性は同等です。</span><span class="sxs-lookup"><span data-stu-id="47bf0-147">For example, the following **Parameter** attributes are equivalent.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
)

# Boolean arguments can be defined using this shorthand syntax

Param(
    [Parameter(Mandatory)]
)
```

<span data-ttu-id="47bf0-148">引数を指定せずに **パラメーター** 属性を使用する場合、 **この属性を** 使用する代わりに、属性名の後に続くかっこが必要になります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-148">If you use the **Parameter** attribute without arguments, as an alternative to using the **CmdletBinding** attribute, the parentheses that follow the attribute name are still required.</span></span>

```powershell
Param(
    [Parameter()]
    $ParameterName
)
```

#### <a name="mandatory-argument"></a><span data-ttu-id="47bf0-149">必須の引数</span><span class="sxs-lookup"><span data-stu-id="47bf0-149">Mandatory argument</span></span>

<span data-ttu-id="47bf0-150">引数は、 `Mandatory` パラメーターが必須であることを示します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-150">The `Mandatory` argument indicates that the parameter is required.</span></span> <span data-ttu-id="47bf0-151">この引数が指定されていない場合、パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="47bf0-151">If this argument isn't specified, the parameter is optional.</span></span>

<span data-ttu-id="47bf0-152">次の例では、 **ComputerName** パラメーターを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="47bf0-152">The following example declares the **ComputerName** parameter.</span></span> <span data-ttu-id="47bf0-153">引数を使用して `Mandatory` 、パラメーターを必須にします。</span><span class="sxs-lookup"><span data-stu-id="47bf0-153">It uses the `Mandatory` argument to make the parameter mandatory.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [String[]]
    $ComputerName
)
```

#### <a name="position-argument"></a><span data-ttu-id="47bf0-154">Position 引数</span><span class="sxs-lookup"><span data-stu-id="47bf0-154">Position argument</span></span>

<span data-ttu-id="47bf0-155">引数は、パラメーター `Position` がコマンドで使用されるときにパラメーター名が必要かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-155">The `Position` argument determines whether the parameter name is required when the parameter is used in a command.</span></span> <span data-ttu-id="47bf0-156">パラメーターの宣言に引数が含まれている場合 `Position` 、パラメーター名を省略することができ、名前のないパラメーター値は、コマンド内の名前のないパラメーター値のリストの位置 (順序) によって PowerShell によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-156">When a parameter declaration includes the `Position` argument, the parameter name can be omitted and PowerShell identifies the unnamed parameter value by its position, or order, in the list of unnamed parameter values in the command.</span></span>

<span data-ttu-id="47bf0-157">引数が `Position` 指定されていない場合、パラメーター名またはパラメーター名の別名または省略形は、パラメーターがコマンドで使用されるたびに、パラメーター値の前に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-157">If the `Position` argument isn't specified, the parameter name, or a parameter name alias or abbreviation, must precede the parameter value whenever the parameter is used in a command.</span></span>

<span data-ttu-id="47bf0-158">既定では、すべての関数のパラメーターは位置指定です。</span><span class="sxs-lookup"><span data-stu-id="47bf0-158">By default, all function parameters are positional.</span></span> <span data-ttu-id="47bf0-159">PowerShell では、パラメーターが関数内で宣言されている順序で、パラメーターに位置番号が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-159">PowerShell assigns position numbers to parameters in the order in which the parameters are declared in the function.</span></span> <span data-ttu-id="47bf0-160">この機能を無効にするには、[ `PositionalBinding` 属性] の **CmdletBinding** 引数の値をに設定 `$False` します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-160">To disable this feature, set the value of the `PositionalBinding` argument of the **CmdletBinding** attribute to `$False`.</span></span> <span data-ttu-id="47bf0-161">引数は、 `Position` 属性の引数の値よりも優先され `PositionalBinding` ます。 **CmdletBinding**</span><span class="sxs-lookup"><span data-stu-id="47bf0-161">The `Position` argument takes precedence over the value of the `PositionalBinding` argument of the **CmdletBinding** attribute.</span></span> <span data-ttu-id="47bf0-162">詳細については、「about_Functions_CmdletBindingAttribute」を参照してください `PositionalBinding` 。 [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)</span><span class="sxs-lookup"><span data-stu-id="47bf0-162">For more information, see `PositionalBinding` in [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span></span>

<span data-ttu-id="47bf0-163">引数の値 `Position` は整数として指定されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-163">The value of the `Position` argument is specified as an integer.</span></span> <span data-ttu-id="47bf0-164">Position 値 **0** はコマンド内の最初の位置を表し、position 値 **1** はコマンドの2番目の位置を表します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-164">A position value of **0** represents the first position in the command, a position value of **1** represents the second position in the command, and so on.</span></span>

<span data-ttu-id="47bf0-165">関数に位置指定パラメーターがない場合、PowerShell では、パラメーターが宣言されている順序に基づいて各パラメーターに位置が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-165">If a function has no positional parameters, PowerShell assigns positions to each parameter based on the order in which the parameters are declared.</span></span>
<span data-ttu-id="47bf0-166">ただし、ベストプラクティスとして、この割り当てに依存しないでください。</span><span class="sxs-lookup"><span data-stu-id="47bf0-166">However, as a best practice, don't rely on this assignment.</span></span> <span data-ttu-id="47bf0-167">パラメーターを位置指定にする場合は、引数を使用し `Position` ます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-167">When you want parameters to be positional, use the `Position` argument.</span></span>

<span data-ttu-id="47bf0-168">次の例では、 **ComputerName** パラメーターを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="47bf0-168">The following example declares the **ComputerName** parameter.</span></span> <span data-ttu-id="47bf0-169">この例では、 `Position` 値が **0** の引数を使用しています。</span><span class="sxs-lookup"><span data-stu-id="47bf0-169">It uses the `Position` argument with a value of **0**.</span></span> <span data-ttu-id="47bf0-170">結果として、コマンドからを省略した場合、 `-ComputerName` その値は、コマンドの最初のパラメーター値または無名のパラメーター値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-170">As a result, when `-ComputerName` is omitted from command, its value must be the first or only unnamed parameter value in the command.</span></span>

```powershell
Param(
    [Parameter(Position=0)]
    [String[]]
    $ComputerName
)
```

#### <a name="parametersetname-argument"></a><span data-ttu-id="47bf0-171">ParameterSetName 引数</span><span class="sxs-lookup"><span data-stu-id="47bf0-171">ParameterSetName argument</span></span>

<span data-ttu-id="47bf0-172">引数は、 `ParameterSetName` パラメーターが属するパラメーターセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-172">The `ParameterSetName` argument specifies the parameter set to which a parameter belongs.</span></span> <span data-ttu-id="47bf0-173">パラメーターセットが指定されていない場合、パラメーターは、関数によって定義されたすべてのパラメーターセットに属します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-173">If no parameter set is specified, the parameter belongs to all the parameter sets defined by the function.</span></span> <span data-ttu-id="47bf0-174">したがって、一意にするには、各パラメーターセットに、他のパラメーターセットのメンバーではないパラメーターが少なくとも1つ必要です。</span><span class="sxs-lookup"><span data-stu-id="47bf0-174">Therefore, to be unique, each parameter set must have at least one parameter that isn't a member of any other parameter set.</span></span>

> [!NOTE]
> <span data-ttu-id="47bf0-175">コマンドレットまたは関数の場合、32パラメーターセットの制限があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-175">For a cmdlet or function, there is a limit of 32 parameter sets.</span></span>

<span data-ttu-id="47bf0-176">次の例では、パラメーターセット内の **ComputerName** パラメーター `Computer` 、パラメーターセットの **UserName** パラメーター、 `User` および両方のパラメーターセットの **概要** パラメーターを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="47bf0-176">The following example declares a **ComputerName** parameter in the `Computer` parameter set, a **UserName** parameter in the `User` parameter set, and a **Summary** parameter in both parameter sets.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ParameterSetName="Computer")]
    [String[]]
    $ComputerName,

    [Parameter(Mandatory=$true,
    ParameterSetName="User")]
    [String[]]
    $UserName,

    [Parameter(Mandatory=$false)]
    [Switch]
    $Summary
)
```

<span data-ttu-id="47bf0-177">各引数に指定できる値は1つだけで `ParameterSetName` 、 `ParameterSetName` 各 **パラメーター** 属性には1つの引数のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-177">You can specify only one `ParameterSetName` value in each argument and only one `ParameterSetName` argument in each **Parameter** attribute.</span></span> <span data-ttu-id="47bf0-178">パラメーターが複数のパラメーターセットに含まれていることを示すには、 **パラメーター属性を追加し** ます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-178">To indicate that a parameter appears in more than one parameter set, add additional **Parameter** attributes.</span></span>

<span data-ttu-id="47bf0-179">次の例では、およびパラメーターセットに **Summary** パラメーターを明示的に追加し `Computer` `User` ます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-179">The following example explicitly adds the **Summary** parameter to the `Computer` and `User` parameter sets.</span></span> <span data-ttu-id="47bf0-180">パラメーターセットでは **Summary** パラメーターを省略 `Computer` でき、パラメーターセットでは必須です `User` 。</span><span class="sxs-lookup"><span data-stu-id="47bf0-180">The **Summary** parameter is optional in the `Computer` parameter set and mandatory in the `User` parameter set.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ParameterSetName="Computer")]
    [String[]]
    $ComputerName,

    [Parameter(Mandatory=$true,
    ParameterSetName="User")]
    [String[]]
    $UserName,

    [Parameter(Mandatory=$false, ParameterSetName="Computer")]
    [Parameter(Mandatory=$true, ParameterSetName="User")]
    [Switch]
    $Summary
)
```

<span data-ttu-id="47bf0-181">パラメーターセットの詳細については、「 [パラメーターセットについ](about_parameter_sets.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47bf0-181">For more information about parameter sets, see [About Parameter Sets](about_parameter_sets.md).</span></span>

#### <a name="valuefrompipeline-argument"></a><span data-ttu-id="47bf0-182">ValueFromPipeline 引数</span><span class="sxs-lookup"><span data-stu-id="47bf0-182">ValueFromPipeline argument</span></span>

<span data-ttu-id="47bf0-183">引数は、 `ValueFromPipeline` パラメーターがパイプラインオブジェクトからの入力を受け入れることを示します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-183">The `ValueFromPipeline` argument indicates that the parameter accepts input from a pipeline object.</span></span> <span data-ttu-id="47bf0-184">オブジェクトのプロパティだけでなく、関数がオブジェクト全体を受け入れる場合は、この引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-184">Specify this argument if the function accepts the entire object, not just a property of the object.</span></span>

<span data-ttu-id="47bf0-185">次の例では、必須の **ComputerName** パラメーターを宣言し、パイプラインから関数に渡されたオブジェクトを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-185">The following example declares a **ComputerName** parameter that's mandatory and accepts an object that's passed to the function from the pipeline.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipeline=$true)]
    [String[]]
    $ComputerName
)
```

#### <a name="valuefrompipelinebypropertyname-argument"></a><span data-ttu-id="47bf0-186">ValueFromPipelineByPropertyName 引数</span><span class="sxs-lookup"><span data-stu-id="47bf0-186">ValueFromPipelineByPropertyName argument</span></span>

<span data-ttu-id="47bf0-187">引数は、 `ValueFromPipelineByPropertyName` パラメーターがパイプラインオブジェクトのプロパティからの入力を受け入れることを示します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-187">The `ValueFromPipelineByPropertyName` argument indicates that the parameter accepts input from a property of a pipeline object.</span></span> <span data-ttu-id="47bf0-188">オブジェクトプロパティには、パラメーターと同じ名前またはエイリアスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-188">The object property must have the same name or alias as the parameter.</span></span>

<span data-ttu-id="47bf0-189">たとえば、関数に **computername** パラメーターがあり、パイプされたオブジェクトに **computername** プロパティがある場合、 **computername** プロパティの値は関数の **computername** パラメーターに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-189">For example, if the function has a **ComputerName** parameter, and the piped object has a **ComputerName** property, the value of the **ComputerName** property is assigned to the function's **ComputerName** parameter.</span></span>

<span data-ttu-id="47bf0-190">次の例では、必須の **computername** パラメーターを宣言し、パイプラインを介して関数に渡されるオブジェクトの **computername** プロパティからの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-190">The following example declares a **ComputerName** parameter that's mandatory and accepts input from the object's **ComputerName** property that's passed to the function through the pipeline.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipelineByPropertyName=$true)]
    [String[]]
    $ComputerName
)
```

> [!NOTE]
> <span data-ttu-id="47bf0-191">パイプラインの入力 () または () を受け入れる型指定されたパラメーター `by Value` `by PropertyName` では、パラメーターで _遅延バインディング_ スクリプトブロックを使用できます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-191">A typed parameter that accepts pipeline input (`by Value`) or (`by PropertyName`) enables use of _delay-bind_ script blocks on the parameter.</span></span>
>
> <span data-ttu-id="47bf0-192">_遅延バインド_ スクリプトブロックは、 **parameterbinding** 中に自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-192">The _delay-bind_ script block is run automatically during **ParameterBinding**.</span></span> <span data-ttu-id="47bf0-193">結果は、パラメーターにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-193">The result is bound to the parameter.</span></span> <span data-ttu-id="47bf0-194">遅延バインディングは、型または型として定義されたパラメーターに対しては機能しません `ScriptBlock` `System.Object` 。</span><span class="sxs-lookup"><span data-stu-id="47bf0-194">Delay binding does not work for parameters defined as type `ScriptBlock` or `System.Object`.</span></span> <span data-ttu-id="47bf0-195">スクリプトブロックは呼び出され _ず_ に渡されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-195">The script block is passed through _without_ being invoked.</span></span>
>
> <span data-ttu-id="47bf0-196">_遅延バインドの_ スクリプトブロックについては、「 [about_Script_Blocks](about_Script_Blocks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47bf0-196">You can read about _delay-bind_ script blocks here [about_Script_Blocks.md](about_Script_Blocks.md).</span></span>

#### <a name="valuefromremainingarguments-argument"></a><span data-ttu-id="47bf0-197">ValueFromRemainingArguments 引数</span><span class="sxs-lookup"><span data-stu-id="47bf0-197">ValueFromRemainingArguments argument</span></span>

<span data-ttu-id="47bf0-198">引数は、 `ValueFromRemainingArguments` パラメーターが、関数の他のパラメーターに割り当てられていないコマンド内のすべてのパラメーターの値を受け入れることを示します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-198">The `ValueFromRemainingArguments` argument indicates that the parameter accepts all the parameter's values in the command that aren't assigned to other parameters of the function.</span></span>

<span data-ttu-id="47bf0-199">次の例では、必須の **値** パラメーターと、その関数に送信される残りのすべてのパラメーター値を受け入れる **残り** のパラメーターを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="47bf0-199">The following example declares a **Value** parameter that's mandatory and a **Remaining** parameter that accepts all the remaining parameter values that are submitted to the function.</span></span>

```powershell
function Test-Remainder
{
     param(
         [string]
         [Parameter(Mandatory = $true, Position=0)]
         $Value,
         [string[]]
         [Parameter(Position=1, ValueFromRemainingArguments)]
         $Remaining)
     "Found $($Remaining.Count) elements"
     for ($i = 0; $i -lt $Remaining.Count; $i++)
     {
        "${i}: $($Remaining[$i])"
     }
}
Test-Remainder first one,two
```

```Output
Found 2 elements
0: one
1: two
```

> [!NOTE]
> <span data-ttu-id="47bf0-200">PowerShell 6.2 より前では、 **ValueFromRemainingArguments** コレクションはインデックス **0** の1つのエンティティとして結合されていました。</span><span class="sxs-lookup"><span data-stu-id="47bf0-200">Prior to PowerShell 6.2, the **ValueFromRemainingArguments** collection was joined as single entity under index **0**.</span></span>

#### <a name="helpmessage-argument"></a><span data-ttu-id="47bf0-201">HelpMessage 引数</span><span class="sxs-lookup"><span data-stu-id="47bf0-201">HelpMessage argument</span></span>

<span data-ttu-id="47bf0-202">引数は、 `HelpMessage` パラメーターまたはその値の簡単な説明を含む文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-202">The `HelpMessage` argument specifies a string that contains a brief description of the parameter or its value.</span></span> <span data-ttu-id="47bf0-203">PowerShell では、コマンドに必須のパラメーター値が指定されていない場合に表示されるプロンプトに、このメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-203">PowerShell displays this message in the prompt that appears when a mandatory parameter value is missing from a command.</span></span> <span data-ttu-id="47bf0-204">この引数は、省略可能なパラメーターには影響しません。</span><span class="sxs-lookup"><span data-stu-id="47bf0-204">This argument has no effect on optional parameters.</span></span>

<span data-ttu-id="47bf0-205">次の例では、必須の **ComputerName** パラメーターと、必要なパラメーター値を説明するヘルプメッセージを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="47bf0-205">The following example declares a mandatory **ComputerName** parameter and a help message that explains the expected parameter value.</span></span>

<span data-ttu-id="47bf0-206">関数に他の [コメントベースのヘルプ](./about_comment_based_help.md) 構文 (など) がない場合は、 `.SYNOPSIS` このメッセージも出力に表示さ `Get-Help` れます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-206">If there is no other [comment-based help](./about_comment_based_help.md) syntax for the function (for example, `.SYNOPSIS`) then this message also shows up in `Get-Help` output.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    HelpMessage="Enter one or more computer names separated by commas.")]
    [String[]]
    $ComputerName
)
```

### <a name="alias-attribute"></a><span data-ttu-id="47bf0-207">Alias 属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-207">Alias attribute</span></span>

<span data-ttu-id="47bf0-208">**Alias** 属性は、パラメーターの代替名を確立します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-208">The **Alias** attribute establishes an alternate name for the parameter.</span></span>
<span data-ttu-id="47bf0-209">パラメーターに割り当てることができるエイリアスの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="47bf0-209">There's no limit to the number of aliases that you can assign to a parameter.</span></span>

<span data-ttu-id="47bf0-210">次の例は、 **CN** および **MachineName** エイリアスを必須の **ComputerName** パラメーターに追加するパラメーター宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="47bf0-210">The following example shows a parameter declaration that adds the **CN** and **MachineName** aliases to the mandatory **ComputerName** parameter.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [Alias("CN","MachineName")]
    [String[]]
    $ComputerName
)
```

### <a name="supportswildcards-attribute"></a><span data-ttu-id="47bf0-211">SupportsWildcards 属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-211">SupportsWildcards attribute</span></span>

<span data-ttu-id="47bf0-212">**SupportsWildcards** 属性は、パラメーターがワイルドカード値を受け入れることを示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-212">The **SupportsWildcards** attribute is used to indicate that the parameter accepts wildcard values.</span></span> <span data-ttu-id="47bf0-213">次の例は、ワイルドカード値をサポートする必須の **パス** パラメーターのパラメーター宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="47bf0-213">The following example shows a parameter declaration for a mandatory **Path** parameter that supports wildcard values.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [SupportsWildcards()]
    [String[]]
    $Path
)
```

<span data-ttu-id="47bf0-214">この属性を使用しても、ワイルドカードのサポートは自動的に有効になりません。</span><span class="sxs-lookup"><span data-stu-id="47bf0-214">Using this attribute does not automatically enable wildcard support.</span></span> <span data-ttu-id="47bf0-215">コマンドレットの開発者は、ワイルドカード入力を処理するコードを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-215">The cmdlet developer must implement the code to handle the wildcard input.</span></span> <span data-ttu-id="47bf0-216">サポートされているワイルドカードは、基になる API または PowerShell プロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-216">The wildcards supported can vary according to the underlying API or PowerShell provider.</span></span> <span data-ttu-id="47bf0-217">詳細については、「 [about_Wildcards](about_Wildcards.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47bf0-217">For more information, see [about_Wildcards](about_Wildcards.md).</span></span>

### <a name="parameter-and-variable-validation-attributes"></a><span data-ttu-id="47bf0-218">パラメーターと変数の検証属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-218">Parameter and variable validation attributes</span></span>

<span data-ttu-id="47bf0-219">検証属性は、ユーザーが高度な関数を呼び出したときに送信されるパラメーター値をテストするように PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-219">Validation attributes direct PowerShell to test the parameter values that users submit when they call the advanced function.</span></span> <span data-ttu-id="47bf0-220">パラメーター値がテストに失敗した場合は、エラーが生成され、関数は呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="47bf0-220">If the parameter values fail the test, an error is generated and the function isn't called.</span></span> <span data-ttu-id="47bf0-221">パラメーターの検証は、指定された入力にのみ適用され、既定値のようなその他の値は検証されません。</span><span class="sxs-lookup"><span data-stu-id="47bf0-221">Parameter validation is only applied to the input provided and any other values like default values are not validated.</span></span>

<span data-ttu-id="47bf0-222">また、検証属性を使用して、ユーザーが変数に指定できる値を制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-222">You can also use the validation attributes to restrict the values that users can specify for variables.</span></span> <span data-ttu-id="47bf0-223">検証属性と共に型コンバーターを使用する場合は、属性の前に型コンバーターを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-223">When you use a type converter along with a validation attribute, the type converter has to be defined before the attribute.</span></span>

```powershell
[int32][AllowNull()] $number = 7
```

### <a name="allownull-validation-attribute"></a><span data-ttu-id="47bf0-224">AllowNull 検証属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-224">AllowNull validation attribute</span></span>

<span data-ttu-id="47bf0-225">**Allownull** 属性では、必須パラメーターの値をにすることができ `$null` ます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-225">The **AllowNull** attribute allows the value of a mandatory parameter to be `$null`.</span></span> <span data-ttu-id="47bf0-226">次の例では、 **null** 値を持つことができる Hashtable **computerinfo** パラメーターを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="47bf0-226">The following example declares a hashtable **ComputerInfo** parameter that can have a **null** value.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowNull()]
    [hashtable]
    $ComputerInfo
)
```

> [!NOTE]
> <span data-ttu-id="47bf0-227">型コンバーターが string に設定されている場合、文字列型は null 値を受け入れないため、 **Allownull** 属性は機能しません。</span><span class="sxs-lookup"><span data-stu-id="47bf0-227">The **AllowNull** attribute doesn't work if the type converter is set to string as the string type will not accept a null value.</span></span> <span data-ttu-id="47bf0-228">このシナリオでは、 **AllowEmptyString** 属性を使用できます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-228">You can use the **AllowEmptyString** attribute for this scenario.</span></span>

### <a name="allowemptystring-validation-attribute"></a><span data-ttu-id="47bf0-229">AllowEmptyString validation 属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-229">AllowEmptyString validation attribute</span></span>

<span data-ttu-id="47bf0-230">**AllowEmptyString** 属性を使用すると、必須パラメーターの値を空の文字列 () にすることができ `""` ます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-230">The **AllowEmptyString** attribute allows the value of a mandatory parameter to be an empty string (`""`).</span></span> <span data-ttu-id="47bf0-231">次の例では、空の文字列値を持つことができる **ComputerName** パラメーターを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="47bf0-231">The following example declares a **ComputerName** parameter that can have an empty string value.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowEmptyString()]
    [String]
    $ComputerName
)
```

### <a name="allowemptycollection-validation-attribute"></a><span data-ttu-id="47bf0-232">AllowEmptyCollection 検証属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-232">AllowEmptyCollection validation attribute</span></span>

<span data-ttu-id="47bf0-233">**Allowemptycollection** 属性を使用すると、必須パラメーターの値を空のコレクションにすることができ `@()` ます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-233">The **AllowEmptyCollection** attribute allows the value of a mandatory parameter to be an empty collection `@()`.</span></span> <span data-ttu-id="47bf0-234">次の例では、空のコレクション値を持つことができる **ComputerName** パラメーターを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="47bf0-234">The following example declares a **ComputerName** parameter that can have an empty collection value.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowEmptyCollection()]
    [String[]]
    $ComputerName
)
```

### <a name="validatecount-validation-attribute"></a><span data-ttu-id="47bf0-235">ValidateCount 検証属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-235">ValidateCount validation attribute</span></span>

<span data-ttu-id="47bf0-236">**Validatecount** 属性では、パラメーターで許容されるパラメーター値の最小数と最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-236">The **ValidateCount** attribute specifies the minimum and maximum number of parameter values that a parameter accepts.</span></span> <span data-ttu-id="47bf0-237">PowerShell では、関数を呼び出すコマンド内のパラメーター値の数がその範囲外の場合、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-237">PowerShell generates an error if the number of parameter values in the command that calls the function is outside that range.</span></span>

<span data-ttu-id="47bf0-238">次のパラメーター宣言では、1 ~ 5 個のパラメーター値を受け取る **ComputerName** パラメーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-238">The following parameter declaration creates a **ComputerName** parameter that takes one to five parameter values.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateCount(1,5)]
    [String[]]
    $ComputerName
)
```

### <a name="validatelength-validation-attribute"></a><span data-ttu-id="47bf0-239">ValidateLength validation 属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-239">ValidateLength validation attribute</span></span>

<span data-ttu-id="47bf0-240">**ValidateLength** 属性は、パラメーターまたは変数値の文字の最小数と最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-240">The **ValidateLength** attribute specifies the minimum and maximum number of characters in a parameter or variable value.</span></span> <span data-ttu-id="47bf0-241">パラメーターまたは変数に指定された値の長さが範囲外の場合、PowerShell ではエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-241">PowerShell generates an error if the length of a value specified for a parameter or a variable is outside of the range.</span></span>

<span data-ttu-id="47bf0-242">次の例では、各コンピューター名は 1 ~ 10 文字である必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-242">In the following example, each computer name must have one to ten characters.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateLength(1,10)]
    [String[]]
    $ComputerName
)
```

<span data-ttu-id="47bf0-243">次の例では、変数の値は、 `$number` 長さが1文字以上、最大で10文字である必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-243">In the following example, the value of the variable `$number` must be a minimum of one character in length, and a maximum of ten characters.</span></span>

```powershell
[Int32][ValidateLength(1,10)]$number = '01'
```

> [!NOTE]
> <span data-ttu-id="47bf0-244">この例では、の値 `01` が単一引用符で囲まれています。</span><span class="sxs-lookup"><span data-stu-id="47bf0-244">In this example, the value of `01` is wrapped in single quotes.</span></span> <span data-ttu-id="47bf0-245">**ValidateLength** 属性では、引用符で囲まずに数値を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="47bf0-245">The **ValidateLength** attribute won't accept a number without being wrapped in quotes.</span></span>

### <a name="validatepattern-validation-attribute"></a><span data-ttu-id="47bf0-246">ValidatePattern 検証属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-246">ValidatePattern validation attribute</span></span>

<span data-ttu-id="47bf0-247">**Validatepattern** 属性は、パラメーターまたは変数値と比較される正規表現を指定します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-247">The **ValidatePattern** attribute specifies a regular expression that's compared to the parameter or variable value.</span></span> <span data-ttu-id="47bf0-248">値が正規表現パターンに一致しない場合、PowerShell ではエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-248">PowerShell generates an error if the value doesn't match the regular expression pattern.</span></span>

<span data-ttu-id="47bf0-249">次の例では、パラメーター値に4桁の数字を含める必要があり、各桁には 0 ~ 9 の数値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-249">In the following example, the parameter value must contain a four-digit number, and each digit must be a number zero to nine.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidatePattern("[0-9][0-9][0-9][0-9]")]
    [String[]]
    $ComputerName
)
```

<span data-ttu-id="47bf0-250">次の例では、変数の値は4桁の数字にする `$number` 必要があり、各桁には 0 ~ 9 の数値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-250">In the following example, the value of the variable `$number` must be exactly a four-digit number, and each digit must be a number zero to nine.</span></span>

```powershell
[Int32][ValidatePattern("^[0-9][0-9][0-9][0-9]$")]$number = 1111
```

### <a name="validaterange-validation-attribute"></a><span data-ttu-id="47bf0-251">ValidateRange validation 属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-251">ValidateRange validation attribute</span></span>

<span data-ttu-id="47bf0-252">**ValidateRange** 属性は、各パラメーターまたは変数値の数値範囲または **Validaterangekind** 列挙値を指定します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-252">The **ValidateRange** attribute specifies a numeric range or a **ValidateRangeKind** enum value for each parameter or variable value.</span></span>
<span data-ttu-id="47bf0-253">値が範囲外の場合、PowerShell はエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-253">PowerShell generates an error if any value is outside that range.</span></span>

<span data-ttu-id="47bf0-254">**Validaterangekind** 列挙型では、次の値が許可されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-254">The **ValidateRangeKind** enum allows for the following values:</span></span>

- <span data-ttu-id="47bf0-255">**正** -0 より大きい数値。</span><span class="sxs-lookup"><span data-stu-id="47bf0-255">**Positive** - A number greater than zero.</span></span>
- <span data-ttu-id="47bf0-256">**負** -0 未満の数値。</span><span class="sxs-lookup"><span data-stu-id="47bf0-256">**Negative** - A number less than zero.</span></span>
- <span data-ttu-id="47bf0-257">**非正** -0 以下の数値。</span><span class="sxs-lookup"><span data-stu-id="47bf0-257">**NonPositive** - A number less than or equal to zero.</span></span>
- <span data-ttu-id="47bf0-258">**負** でない-0 以上の数値。</span><span class="sxs-lookup"><span data-stu-id="47bf0-258">**NonNegative** - A number greater than or equal to zero.</span></span>

<span data-ttu-id="47bf0-259">次の例では、 **Attempts** パラメーターの値を0から10までの範囲で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-259">In the following example, the value of the **Attempts** parameter must be between zero and ten.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateRange(0,10)]
    [Int]
    $Attempts
)
```

<span data-ttu-id="47bf0-260">次の例では、変数の値を `$number` 0 から10までの範囲で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-260">In the following example, the value of the variable `$number` must be between zero and ten.</span></span>

```powershell
[Int32][ValidateRange(0,10)]$number = 5
```

<span data-ttu-id="47bf0-261">次の例では、変数の値 `$number` が0より大きい必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-261">In the following example, the value of the variable `$number` must be greater than zero.</span></span>

```powershell
[Int32][ValidateRange("Positive")]$number = 1
```

### <a name="validatescript-validation-attribute"></a><span data-ttu-id="47bf0-262">ValidateScript validation 属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-262">ValidateScript validation attribute</span></span>

<span data-ttu-id="47bf0-263">**ValidateScript** 属性は、パラメーターまたは変数値の検証に使用されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-263">The **ValidateScript** attribute specifies a script that is used to validate a parameter or variable value.</span></span> <span data-ttu-id="47bf0-264">PowerShell は、値をスクリプトにパイプし、スクリプトがを返すか、 `$false` またはスクリプトが例外をスローした場合にエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-264">PowerShell pipes the value to the script, and generates an error if the script returns `$false` or if the script throws an exception.</span></span>

<span data-ttu-id="47bf0-265">**ValidateScript** 属性を使用すると、検証されている値が変数にマップされ `$_` ます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-265">When you use the **ValidateScript** attribute, the value that's being validated is mapped to the `$_` variable.</span></span> <span data-ttu-id="47bf0-266">変数を使用し `$_` て、スクリプト内の値を参照できます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-266">You can use the `$_` variable to refer to the value in the script.</span></span>

<span data-ttu-id="47bf0-267">次の例では、 **Eventdate** パラメーターの値が現在の日付以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-267">In the following example, the value of the **EventDate** parameter must be greater than or equal to the current date.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateScript({$_ -ge (Get-Date)})]
    [DateTime]
    $EventDate
)
```

<span data-ttu-id="47bf0-268">次の例では、変数の値 `$date` が現在の日付と時刻以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-268">In the following example, the value of the variable `$date` must be greater than or equal to the current date and time.</span></span>

```powershell
[DateTime][ValidateScript({$_ -ge (Get-Date)})]$date = (Get-Date)
```

> [!NOTE]
> <span data-ttu-id="47bf0-269">**ValidateScript** を使用する場合は、パラメーターに値を渡すことはできません `$null` 。</span><span class="sxs-lookup"><span data-stu-id="47bf0-269">If you use **ValidateScript** , you cannot pass a `$null` value to the parameter.</span></span> <span data-ttu-id="47bf0-270">Null 値を渡すと、 **ValidateScript** は引数を検証できません。</span><span class="sxs-lookup"><span data-stu-id="47bf0-270">When you pass a null value **ValidateScript** can't validate the argument.</span></span>

### <a name="validateset-attribute"></a><span data-ttu-id="47bf0-271">ValidateSet 属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-271">ValidateSet attribute</span></span>

<span data-ttu-id="47bf0-272">**Validateset** 属性では、パラメーターまたは変数に有効な値のセットを指定し、タブ補完を有効にします。</span><span class="sxs-lookup"><span data-stu-id="47bf0-272">The **ValidateSet** attribute specifies a set of valid values for a parameter or variable and enables tab completion.</span></span> <span data-ttu-id="47bf0-273">パラメーターまたは変数値がセット内の値と一致しない場合、PowerShell ではエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-273">PowerShell generates an error if a parameter or variable value doesn't match a value in the set.</span></span> <span data-ttu-id="47bf0-274">次の例では、 **Detail** パラメーターの値には、Low、Average、または High のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-274">In the following example, the value of the **Detail** parameter can only be Low, Average, or High.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateSet("Low", "Average", "High")]
    [String[]]
    $Detail
)
```

<span data-ttu-id="47bf0-275">次の例では、変数の値は、 `$flavor` チョコレート、Strawberry、またはバニラのいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-275">In the following example, the value of the variable `$flavor` must be either Chocolate, Strawberry, or Vanilla.</span></span>

```powershell
[ValidateSet("Chocolate", "Strawberry", "Vanilla")]
[String]$flavor = "Strawberry"
```

<span data-ttu-id="47bf0-276">検証は、スクリプト内でもその変数が割り当てられるたびに行われます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-276">The validation occurs whenever that variable is assigned even within the script.</span></span> <span data-ttu-id="47bf0-277">たとえば、次の例では、実行時にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-277">For example, the following results in an error at runtime:</span></span>

```powershell
Param(
    [ValidateSet("hello", "world")]
    [String]$Message
)

$Message = "bye"
```

#### <a name="dynamic-validateset-values"></a><span data-ttu-id="47bf0-278">動的 validateSet 値</span><span class="sxs-lookup"><span data-stu-id="47bf0-278">Dynamic validateSet values</span></span>

<span data-ttu-id="47bf0-279">**クラス** を使用して、実行時に **validateset** の値を動的に生成できます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-279">You can use a **Class** to dynamically generate the values for **ValidateSet** at runtime.</span></span> <span data-ttu-id="47bf0-280">次の例では、変数の有効な値が、 `$Sound` 使用可能なサウンドファイルの3つのファイルシステムパスをチェックする **soundnames** という名前の **クラス** を使用して生成されています。</span><span class="sxs-lookup"><span data-stu-id="47bf0-280">In the following example, the valid values for the variable `$Sound` are generated via a **Class** named **SoundNames** that checks three filesystem paths for available sound files:</span></span>

```powershell
Class SoundNames : System.Management.Automation.IValidateSetValuesGenerator {
    [String[]] GetValidValues() {
        $SoundPaths = '/System/Library/Sounds/',
            '/Library/Sounds','~/Library/Sounds'
        $SoundNames = ForEach ($SoundPath in $SoundPaths) {
            If (Test-Path $SoundPath) {
                (Get-ChildItem $SoundPath).BaseName
            }
        }
        return [String[]] $SoundNames
    }
}
```

<span data-ttu-id="47bf0-281">クラスは、次のように `[SoundNames]` 動的な **validateset** 値として実装されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-281">The `[SoundNames]` class is then implemented as a dynamic **ValidateSet** value as follows:</span></span>

```powershell
Param(
    [ValidateSet([SoundNames])]
    [String]$Sound
)
```

### <a name="validatenotnull-validation-attribute"></a><span data-ttu-id="47bf0-282">ValidateNotNull 検証属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-282">ValidateNotNull validation attribute</span></span>

<span data-ttu-id="47bf0-283">**Validatenotnull** 属性は、パラメーター値をにすることができないことを指定し `$null` ます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-283">The **ValidateNotNull** attribute specifies that the parameter value can't be `$null`.</span></span> <span data-ttu-id="47bf0-284">パラメーター値がの場合、PowerShell ではエラーが生成され `$null` ます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-284">PowerShell generates an error if the parameter value is `$null`.</span></span>

<span data-ttu-id="47bf0-285">**Validatenotnull** 属性は、パラメーターが省略可能で、型が定義されていない場合、または **オブジェクト** などの null 値を暗黙的に変換できない型コンバーターを持つ場合に使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="47bf0-285">The **ValidateNotNull** attribute is designed to be used when the parameter is optional and the type is undefined or has a type converter that can't implicitly convert a null value like **object**.</span></span> <span data-ttu-id="47bf0-286">**文字列** などの null 値を暗黙的に変換する型を指定した場合、 **validatenotnull** 属性を使用していても null 値は空の文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-286">If you specify a type that that will implicitly convert a null value such as a **string** , the null value is converted to an empty string even when using the **ValidateNotNull** attribute.</span></span> <span data-ttu-id="47bf0-287">このシナリオでは、 **Validatenotnullorempty** を使用します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-287">For this scenario use the **ValidateNotNullOrEmpty**</span></span>

<span data-ttu-id="47bf0-288">次の例では、 **ID** パラメーターの値をにすることはできません `$null` 。</span><span class="sxs-lookup"><span data-stu-id="47bf0-288">In the following example, the value of the **ID** parameter can't be `$null`.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$false)]
    [ValidateNotNull()]
    $ID
)
```

### <a name="validatenotnullorempty-validation-attribute"></a><span data-ttu-id="47bf0-289">ValidateNotNullOrEmpty 検証属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-289">ValidateNotNullOrEmpty validation attribute</span></span>

<span data-ttu-id="47bf0-290">**Validatenotnullorempty** 属性は、パラメーター値をにすることができず、 `$null` 空の文字列 () にすることができないことを指定し `""` ます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-290">The **ValidateNotNullOrEmpty** attribute specifies that the parameter value can't be `$null` and can't be an empty string (`""`).</span></span> <span data-ttu-id="47bf0-291">パラメーターが関数呼び出しで使用されていても、その値が `$null` 、空の文字列 ( `""` )、または空の配列の場合、PowerShell ではエラーが生成され `@()` ます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-291">PowerShell generates an error if the parameter is used in a function call, but its value is `$null`, an empty string (`""`), or an empty array `@()`.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateNotNullOrEmpty()]
    [String[]]
    $UserName
)
```

### <a name="validatedrive-validation-attribute"></a><span data-ttu-id="47bf0-292">ValidateDrive 検証属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-292">ValidateDrive validation attribute</span></span>

<span data-ttu-id="47bf0-293">**Validatedrive** 属性は、パラメーター値がパスを表す必要があることを指定します。これは、許可されるドライブのみを指します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-293">The **ValidateDrive** attribute specifies that the parameter value must represent the path, that's referring to allowed drives only.</span></span> <span data-ttu-id="47bf0-294">パラメーター値が許可されている以外のドライブを参照している場合、PowerShell はエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-294">PowerShell generates an error if the parameter value refers to drives other than the allowed.</span></span> <span data-ttu-id="47bf0-295">ドライブ自体を除き、パスの存在は検証されません。</span><span class="sxs-lookup"><span data-stu-id="47bf0-295">Existence of the path, except for the drive itself, isn't verified.</span></span>

<span data-ttu-id="47bf0-296">相対パスを使用する場合は、現在のドライブがドライブの一覧に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-296">If you use relative path, the current drive must be in the allowed drive list.</span></span>

```powershell
Param(
    [ValidateDrive("C", "D", "Variable", "Function")]
    [String]$Path
)
```

### <a name="validateuserdrive-validation-attribute"></a><span data-ttu-id="47bf0-297">ValidateUserDrive 検証属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-297">ValidateUserDrive validation attribute</span></span>

<span data-ttu-id="47bf0-298">**Validateuserdrive** 属性は、パラメーター値がドライブを参照するパスを表す必要があることを指定し `User` ます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-298">The **ValidateUserDrive** attribute specifies that the parameter value must represent the path, that is referring to `User` drive.</span></span> <span data-ttu-id="47bf0-299">パスが別のドライブを参照している場合は、PowerShell によってエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-299">PowerShell generates an error if the path refers to a different drive.</span></span> <span data-ttu-id="47bf0-300">検証属性は、パスのドライブ部分が存在するかどうかのみをテストします。</span><span class="sxs-lookup"><span data-stu-id="47bf0-300">The validation attribute only tests for the existence of the drive portion of the path.</span></span>

<span data-ttu-id="47bf0-301">相対パスを使用する場合は、現在のドライブがである必要があり `User` ます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-301">If you use relative path, the current drive must be `User`.</span></span>

```powershell
function Test-UserDrivePath{
    [OutputType([bool])]
    Param(
      [Parameter(Mandatory=, Position=0)][ValidateUserDrive()][String]$Path
      )
    $True
}

Test-UserDrivePath -Path C:\
```

```Output
Test-UserDrivePath: Cannot validate argument on parameter 'Path'. The path
argument drive C does not belong to the set of approved drives: User.
Supply a path argument with an approved drive.
```

```powershell
Test-UserDrivePath -Path 'User:\A_folder_that_does_not_exist'
```

```Output
Test-UserDrivePath: Cannot validate argument on parameter 'Path'. Cannot
find drive. A drive with the name 'User' does not exist.
```

<span data-ttu-id="47bf0-302">ドライブは、 `User` 十分な管理 (JEA) セッション構成でのみ定義できます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-302">You can define `User` drive in Just Enough Administration (JEA) session configurations.</span></span> <span data-ttu-id="47bf0-303">この例では、User: ドライブを作成します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-303">For this example, we create the User: drive.</span></span>

```powershell
New-PSDrive -Name 'User' -PSProvider FileSystem -Root $env:HOMEPATH
```

```Output
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
User               75.76         24.24 FileSystem    C:\Users\ExampleUser

```powershell
Test-UserDrivePath -Path 'User:\A_folder_that_does_not_exist'
```

```Output
True
```

### <a name="validatetrusteddata-validation-attribute"></a><span data-ttu-id="47bf0-304">ValidateTrustedData validation 属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-304">ValidateTrustedData validation attribute</span></span>

<span data-ttu-id="47bf0-305">この属性は、PowerShell 6.1.1 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="47bf0-305">This attribute was added in PowerShell 6.1.1.</span></span>

<span data-ttu-id="47bf0-306">現時点では、属性は PowerShell 自体によって内部的に使用され、外部での使用を目的としたものではありません。</span><span class="sxs-lookup"><span data-stu-id="47bf0-306">At this time, the attribute is used internally by PowerShell itself and is not intended for external usage.</span></span>

## <a name="dynamic-parameters"></a><span data-ttu-id="47bf0-307">動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="47bf0-307">Dynamic parameters</span></span>

<span data-ttu-id="47bf0-308">動的パラメーターとは、特定の条件下でのみ使用可能なコマンドレット、関数、またはスクリプトのパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="47bf0-308">Dynamic parameters are parameters of a cmdlet, function, or script that are available only under certain conditions.</span></span>

<span data-ttu-id="47bf0-309">たとえば、いくつかのプロバイダーコマンドレットには、プロバイダードライブまたはプロバイダードライブの特定のパスでコマンドレットが使用されている場合にのみ使用可能なパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-309">For example, several provider cmdlets have parameters that are available only when the cmdlet is used in the provider drive, or in a particular path of the provider drive.</span></span> <span data-ttu-id="47bf0-310">たとえば、 **Encoding** パラメーターは `Add-Content` 、 `Get-Content` `Set-Content` ファイルシステムドライブで使用されている場合にのみ、、、およびコマンドレットで使用できます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-310">For example, the **Encoding** parameter is available on the `Add-Content`, `Get-Content`, and `Set-Content` cmdlets only when it's used in a file system drive.</span></span>

<span data-ttu-id="47bf0-311">また、関数コマンドで別のパラメーターが使用されている場合、または別のパラメーターに特定の値が含まれている場合にのみ表示されるパラメーターを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-311">You can also create a parameter that appears only when another parameter is used in the function command or when another parameter has a certain value.</span></span>

<span data-ttu-id="47bf0-312">動的パラメーターは役に立つ場合がありますが、ユーザーが検出するのが困難な場合があるため、必要な場合にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="47bf0-312">Dynamic parameters can be useful, but use them only when necessary, because they can be difficult for users to discover.</span></span> <span data-ttu-id="47bf0-313">動的パラメーターを検索するには、ユーザーがプロバイダーのパスに存在しているか、コマンドレットの **ArgumentList** パラメーターを使用している `Get-Command` か、の **path** パラメーターを使用している必要があり `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-313">To find a dynamic parameter, the user must be in the provider path, use the **ArgumentList** parameter of the `Get-Command` cmdlet, or use the **Path** parameter of `Get-Help`.</span></span>

<span data-ttu-id="47bf0-314">関数またはスクリプトの動的パラメーターを作成するには、キーワードを使用し `DynamicParam` ます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-314">To create a dynamic parameter for a function or script, use the `DynamicParam` keyword.</span></span>

<span data-ttu-id="47bf0-315">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="47bf0-315">The syntax is as follows:</span></span>

`DynamicParam {<statement-list>}`

<span data-ttu-id="47bf0-316">[ステートメント] ボックスの一覧で、ステートメントを使用して、 `If` 関数でパラメーターを使用できる条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-316">In the statement list, use an `If` statement to specify the conditions under which the parameter is available in the function.</span></span>

<span data-ttu-id="47bf0-317">コマンドレットを使用して、 `New-Object` パラメーターを表す system.string オブジェクトを作成し、その名前を **System.Management.Automation.RuntimeDefinedParameter** 指定します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-317">Use the `New-Object` cmdlet to create a **System.Management.Automation.RuntimeDefinedParameter** object to represent the parameter and specify its name.</span></span>

<span data-ttu-id="47bf0-318">コマンドを使用し `New-Object` て、パラメーターの **System.Management.Automation.ParameterAttribute** 属性を表すための system.object オブジェクトを作成できます。たとえば、 **必須** 、 **位置** 、 **valuefrompipeline** 、パラメーターセットなどです。</span><span class="sxs-lookup"><span data-stu-id="47bf0-318">You can use a `New-Object` command to create a **System.Management.Automation.ParameterAttribute** object to represent attributes of the parameter, such as **Mandatory** , **Position** , or **ValueFromPipeline** or its parameter set.</span></span>

<span data-ttu-id="47bf0-319">次の例では、 **Name** と **Path** という名前の標準パラメーターと、 **sjc-dp1** という名前の省略可能な動的パラメーターを使用したサンプル関数を示します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-319">The following example shows a sample function with standard parameters named **Name** and **Path** , and an optional dynamic parameter named **DP1**.</span></span> <span data-ttu-id="47bf0-320">**Sjc-dp1** パラメーターはパラメーターセットにあり、 `PSet1` の型を持ち `Int32` ます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-320">The **DP1** parameter is in the `PSet1` parameter set and has a type of `Int32`.</span></span>
<span data-ttu-id="47bf0-321">**Sjc-dp1** パラメーターは、 `Get-Sample` **Path** パラメーターの値がで始まっている場合にのみ、関数で使用でき `HKLM:` ます。これは、レジストリドライブで使用されていることを示し `HKEY_LOCAL_MACHINE` ます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-321">The **DP1** parameter is available in the `Get-Sample` function only when the value of the **Path** parameter starts with `HKLM:`, indicating that it's being used in the `HKEY_LOCAL_MACHINE` registry drive.</span></span>

```powershell
function Get-Sample {
  [CmdletBinding()]
  Param([String]$Name, [String]$Path)

  DynamicParam
  {
    if ($Path.StartsWith("HKLM:"))
    {
      $attributes = New-Object -Type `
        System.Management.Automation.ParameterAttribute
      $attributes.ParameterSetName = "PSet1"
      $attributes.Mandatory = $false
      $attributeCollection = New-Object `
        -Type System.Collections.ObjectModel.Collection[System.Attribute]
      $attributeCollection.Add($attributes)

      $dynParam1 = New-Object -Type `
        System.Management.Automation.RuntimeDefinedParameter("DP1", [Int32],
          $attributeCollection)

      $paramDictionary = New-Object `
        -Type System.Management.Automation.RuntimeDefinedParameterDictionary
      $paramDictionary.Add("DP1", $dynParam1)
      return $paramDictionary
    }
  }
}
```

<span data-ttu-id="47bf0-322">詳細については、「 [Runtimeのパラメーター](/dotnet/api/system.management.automation.runtimedefinedparameter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47bf0-322">For more information, see [RuntimeDefinedParameter](/dotnet/api/system.management.automation.runtimedefinedparameter).</span></span>

## <a name="switch-parameters"></a><span data-ttu-id="47bf0-323">スイッチ パラメーター</span><span class="sxs-lookup"><span data-stu-id="47bf0-323">Switch parameters</span></span>

<span data-ttu-id="47bf0-324">スイッチパラメーターはパラメーター値のないパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="47bf0-324">Switch parameters are parameters with no parameter value.</span></span> <span data-ttu-id="47bf0-325">これらは、使用されている場合にのみ有効になり、効果は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="47bf0-325">They're effective only when they're used and have only one effect.</span></span>

<span data-ttu-id="47bf0-326">たとえば、 **powershell.exe** の **noprofile** パラメーターはスイッチパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="47bf0-326">For example, the **NoProfile** parameter of **powershell.exe** is a switch parameter.</span></span>

<span data-ttu-id="47bf0-327">関数でスイッチパラメーターを作成するには、 `Switch` パラメーター定義で型を指定します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-327">To create a switch parameter in a function, specify the `Switch` type in the parameter definition.</span></span>

<span data-ttu-id="47bf0-328">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-328">For example:</span></span>

```powershell
Param([Switch]<ParameterName>)
```

<span data-ttu-id="47bf0-329">または、別のメソッドを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-329">Or, you can use an another method:</span></span>

```powershell
Param(
    [Parameter(Mandatory=$false)]
    [Switch]
    $<ParameterName>
)
```

<span data-ttu-id="47bf0-330">スイッチパラメーターは簡単に使用でき、より複雑な構文を持つブール型パラメーターよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-330">Switch parameters are easy to use and are preferred over Boolean parameters, which have a more difficult syntax.</span></span>

<span data-ttu-id="47bf0-331">たとえば、スイッチパラメーターを使用する場合、ユーザーはコマンドでパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-331">For example, to use a switch parameter, the user types the parameter in the command.</span></span>

`-IncludeAll`

<span data-ttu-id="47bf0-332">ブール型パラメーターを使用するには、ユーザーがパラメーターとブール値を入力します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-332">To use a Boolean parameter, the user types the parameter and a Boolean value.</span></span>

`-IncludeAll:$true`

<span data-ttu-id="47bf0-333">スイッチパラメーターを作成するときは、パラメーター名を慎重に選択してください。</span><span class="sxs-lookup"><span data-stu-id="47bf0-333">When creating switch parameters, choose the parameter name carefully.</span></span> <span data-ttu-id="47bf0-334">パラメーター名は、パラメーターの効果をユーザーに伝えるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="47bf0-334">Be sure that the parameter name communicates the effect of the parameter to the user.</span></span>
<span data-ttu-id="47bf0-335">値が必要であると考えられる **フィルター** や **最大** 値など、あいまいな用語を使用しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="47bf0-335">Avoid ambiguous terms, such as **Filter** or **Maximum** that might imply a value is required.</span></span>

## <a name="argumentcompleter-attribute"></a><span data-ttu-id="47bf0-336">ArgumentCompleter 属性</span><span class="sxs-lookup"><span data-stu-id="47bf0-336">ArgumentCompleter attribute</span></span>

<span data-ttu-id="47bf0-337">**ArgumentCompleter** 属性を使用すると、特定のパラメーターにタブ補完の値を追加できます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-337">The **ArgumentCompleter** attribute allows you to add tab completion values to a specific parameter.</span></span> <span data-ttu-id="47bf0-338">タブ補完が必要な各パラメーターに対して、 **ArgumentCompleter** 属性を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-338">An **ArgumentCompleter** attribute must be defined for each parameter that needs tab completion.</span></span> <span data-ttu-id="47bf0-339">**Dynamicparameters** と同様に、使用可能な値は、ユーザーがパラメーター名の後に <kbd>tab キー</kbd>を押したときに実行時に計算されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-339">Similar to **DynamicParameters** , the available values are calculated at runtime when the user presses <kbd>Tab</kbd> after the parameter name.</span></span>

<span data-ttu-id="47bf0-340">**ArgumentCompleter** 属性を追加するには、値を決定するスクリプトブロックを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-340">To add an **ArgumentCompleter** attribute, you need to define a script block that determines the values.</span></span> <span data-ttu-id="47bf0-341">スクリプトブロックは、次のパラメーターを以下の順序で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-341">The script block must take the following parameters in the order specified below.</span></span> <span data-ttu-id="47bf0-342">パラメーターの名前は、値が位置に指定されている場合には問題になりません。</span><span class="sxs-lookup"><span data-stu-id="47bf0-342">The parameter's names don't matter as the values are provided positionally.</span></span>

<span data-ttu-id="47bf0-343">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="47bf0-343">The syntax is as follows:</span></span>

```powershell
Param(
    [Parameter(Mandatory)]
    [ArgumentCompleter({
        param ( $commandName,
                $parameterName,
                $wordToComplete,
                $commandAst,
                $fakeBoundParameters )
        # Perform calculation of tab completed values here.
    })]
)
```

### <a name="argumentcompleter-script-block"></a><span data-ttu-id="47bf0-344">ArgumentCompleter スクリプトブロック</span><span class="sxs-lookup"><span data-stu-id="47bf0-344">ArgumentCompleter script block</span></span>

<span data-ttu-id="47bf0-345">スクリプトブロックのパラメーターは、次の値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-345">The script block parameters are set to the following values:</span></span>

- <span data-ttu-id="47bf0-346">`$commandName` (位置 0)-このパラメーターには、スクリプトブロックがタブ補完を提供するコマンドの名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-346">`$commandName` (Position 0) - This parameter is set to the name of the command for which the script block is providing tab completion.</span></span>
- <span data-ttu-id="47bf0-347">`$parameterName` (位置 1)-このパラメーターは、値にタブ補完が必要なパラメーターに設定されています。</span><span class="sxs-lookup"><span data-stu-id="47bf0-347">`$parameterName` (Position 1) - This parameter is set to the parameter whose value requires tab completion.</span></span>
- <span data-ttu-id="47bf0-348">`$wordToComplete` (位置 2)-このパラメーターは、 <kbd>Tab キー</kbd>を押す前にユーザーが指定した値に設定されます。スクリプトブロックは、この値を使用してタブ補完の値を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-348">`$wordToComplete` (Position 2) - This parameter is set to value the user has provided before they pressed <kbd>Tab</kbd>. Your script block should use this value to determine tab completion values.</span></span>
- <span data-ttu-id="47bf0-349">`$commandAst` (位置 3)-このパラメーターは、現在の入力行の抽象構文ツリー (AST) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-349">`$commandAst` (Position 3) - This parameter is set to the Abstract Syntax Tree (AST) for the current input line.</span></span> <span data-ttu-id="47bf0-350">詳細については、「 [Ast クラス](/dotnet/api/system.management.automation.language.ast)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47bf0-350">For more information, see [Ast Class](/dotnet/api/system.management.automation.language.ast).</span></span>
- <span data-ttu-id="47bf0-351">`$fakeBoundParameters` (位置 4)-このパラメーターは、 `$PSBoundParameters` ユーザーが <kbd>Tab キー</kbd>を押した前に、コマンドレットのを含むハッシュテーブルに設定されます。詳細については、「 [about_Automatic_Variables](about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47bf0-351">`$fakeBoundParameters` (Position 4) - This parameter is set to a hashtable containing the `$PSBoundParameters` for the cmdlet, before the user pressed <kbd>Tab</kbd>. For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="47bf0-352">**ArgumentCompleter** スクリプトブロックは `ForEach-Object` 、、 `Where-Object` 、またはその他の適切なメソッドなどのパイプラインを使用して値のロールアウトを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bf0-352">The **ArgumentCompleter** script block must unroll the values using the pipeline, such as `ForEach-Object`, `Where-Object`, or another suitable method.</span></span>
<span data-ttu-id="47bf0-353">値の配列を返すと、PowerShell は配列全体を **1 つ** のタブ補完値として扱います。</span><span class="sxs-lookup"><span data-stu-id="47bf0-353">Returning an array of values causes PowerShell to treat the entire array as **one** tab completion value.</span></span>

<span data-ttu-id="47bf0-354">次の例では、 **値** パラメーターにタブ補完機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="47bf0-354">The following example adds tab completion to the **Value** parameter.</span></span> <span data-ttu-id="47bf0-355">**Value** パラメーターのみを指定した場合は、 **値** に対して使用可能なすべての値 (引数) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-355">If only the **Value** parameter is specified, all possible values, or arguments, for **Value** are displayed.</span></span> <span data-ttu-id="47bf0-356">**Type** パラメーターが指定されている場合、 **Value** パラメーターにはその型の有効な値のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="47bf0-356">When the **Type** parameter is specified, the **Value** parameter only displays the possible values for that type.</span></span>

<span data-ttu-id="47bf0-357">さらに、演算子は、 `-like` ユーザーが次のコマンドを入力して <kbd>タブ</kbd> 補完を使用する場合に、 **Apple** のみが返されるようにします。</span><span class="sxs-lookup"><span data-stu-id="47bf0-357">In addition, the `-like` operator ensures that if the user types the following command and uses <kbd>Tab</kbd> completion, only **Apple** is returned.</span></span>

`Test-ArgumentCompleter -Type Fruits -Value A`

```powershell
function Test-ArgumentCompleter {
[CmdletBinding()]
 param (
        [Parameter(Mandatory=$true)]
        [ValidateSet('Fruits', 'Vegetables')]
        $Type,
        [Parameter(Mandatory=$true)]
        [ArgumentCompleter( {
            param ( $commandName,
                    $parameterName,
                    $wordToComplete,
                    $commandAst,
                    $fakeBoundParameters )

            $possibleValues = @{
                Fruits = @('Apple', 'Orange', 'Banana')
                Vegetables = @('Tomato', 'Squash', 'Corn')
            }
            if ($fakeBoundParameters.ContainsKey('Type'))
            {
                $possibleValues[$fakeBoundParameters.Type] | Where-Object {
                    $_ -like "$wordToComplete*"
                }
            }
            else
            {
                $possibleValues.Values | ForEach-Object {$_}
            }
        } )]
        $Value
      )
}
```

## <a name="see-also"></a><span data-ttu-id="47bf0-358">関連項目</span><span class="sxs-lookup"><span data-stu-id="47bf0-358">See also</span></span>

[<span data-ttu-id="47bf0-359">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="47bf0-359">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="47bf0-360">about_Functions</span><span class="sxs-lookup"><span data-stu-id="47bf0-360">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="47bf0-361">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="47bf0-361">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="47bf0-362">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="47bf0-362">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="47bf0-363">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="47bf0-363">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="47bf0-364">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="47bf0-364">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)
