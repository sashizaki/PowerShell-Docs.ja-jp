---
description: PowerShell でコマンドパラメーターを操作する方法について説明します。
Locale: en-US
ms.date: 02/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parameters?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parameters
ms.openlocfilehash: c9d7ab62c13a7cafcf93103f9a70f6575d5dd7b8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602425"
---
# <a name="about-parameters"></a><span data-ttu-id="34ad0-103">パラメーターについて</span><span class="sxs-lookup"><span data-stu-id="34ad0-103">About Parameters</span></span>

## <a name="short-description"></a><span data-ttu-id="34ad0-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="34ad0-104">Short description</span></span>
<span data-ttu-id="34ad0-105">PowerShell でコマンドパラメーターを操作する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="34ad0-105">Describes how to work with command parameters in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="34ad0-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="34ad0-106">Long description</span></span>

<span data-ttu-id="34ad0-107">コマンドレット、関数、スクリプトなど、ほとんどの PowerShell コマンドは、ユーザーがオプションを選択したり入力を指定したりできるように、パラメーターに依存しています。</span><span class="sxs-lookup"><span data-stu-id="34ad0-107">Most PowerShell commands, such as cmdlets, functions, and scripts, rely on parameters to allow users to select options or provide input.</span></span> <span data-ttu-id="34ad0-108">パラメーターはコマンド名に従い、次の形式になります。</span><span class="sxs-lookup"><span data-stu-id="34ad0-108">The parameters follow the command name and have the following form:</span></span>

```
-<parameter_name> <parameter_value>
-<parameter_name>:<parameter_value>
```

<span data-ttu-id="34ad0-109">パラメーターの名前の前にはハイフン (-) が付きます。これは、ハイフンの後に続く単語がパラメーター名であることを PowerShell に通知します。</span><span class="sxs-lookup"><span data-stu-id="34ad0-109">The name of the parameter is preceded by a hyphen (-), which signals to PowerShell that the word following the hyphen is a parameter name.</span></span> <span data-ttu-id="34ad0-110">パラメーターの名前と値は、スペースまたはコロンで区切ることができます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-110">The parameter name and value can be separated by a space or a colon character.</span></span> <span data-ttu-id="34ad0-111">パラメーターには、パラメーター値を必要としないものと受け入れないものがあります。</span><span class="sxs-lookup"><span data-stu-id="34ad0-111">Some parameters do not require or accept a parameter value.</span></span> <span data-ttu-id="34ad0-112">その他のパラメーターには値が必要ですが、コマンドでパラメーター名を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="34ad0-112">Other parameters require a value, but do not require the parameter name in the command.</span></span>

<span data-ttu-id="34ad0-113">パラメーターの種類と要件は異なります。</span><span class="sxs-lookup"><span data-stu-id="34ad0-113">The type of parameters and the requirements for those parameters vary.</span></span> <span data-ttu-id="34ad0-114">コマンドのパラメーターに関する情報を検索するには、コマンドレットを使用し `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-114">To find information about the parameters of a command, use the `Get-Help` cmdlet.</span></span> <span data-ttu-id="34ad0-115">たとえば、コマンドレットのパラメーターに関する情報を検索するには、次のように `Get-ChildItem` 入力します。</span><span class="sxs-lookup"><span data-stu-id="34ad0-115">For example, to find information about the parameters of the `Get-ChildItem` cmdlet, type:</span></span>

```powershell
Get-Help Get-ChildItem
```

<span data-ttu-id="34ad0-116">スクリプトのパラメーターに関する情報を検索するには、スクリプトファイルへの完全なパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="34ad0-116">To find information about the parameters of a script, use the full path to the script file.</span></span> <span data-ttu-id="34ad0-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="34ad0-117">For example:</span></span>

```powershell
Get-Help $home\Documents\Scripts\Get-Function.ps1
```

<span data-ttu-id="34ad0-118">コマンドレットは、コマンド `Get-Help` の説明、コマンドの構文、パラメーターに関する情報、コマンドでパラメーターを使用する方法を示す例など、コマンドに関するさまざまな詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="34ad0-118">The `Get-Help` cmdlet returns various details about the command, including a description, the command syntax, information about the parameters, and examples showing how to use the parameters in a command.</span></span>

<span data-ttu-id="34ad0-119">また、コマンドレットの Parameter パラメーターを使用し `Get-Help` て、特定のパラメーターに関する情報を検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-119">You can also use the Parameter parameter of the `Get-Help` cmdlet to find information about a particular parameter.</span></span> <span data-ttu-id="34ad0-120">または、 **parameter** パラメーターをワイルドカード文字 () 値と共に使用して `*` 、コマンドのすべてのパラメーターに関する情報を検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-120">Or, you can use the **Parameter** parameter with the wildcard character ( `*` ) value to find information about all parameters of the command.</span></span> <span data-ttu-id="34ad0-121">たとえば、次のコマンドは、コマンドレットのすべてのパラメーターに関する情報を取得し `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-121">For example, the following command gets information about all parameters of the `Get-Member` cmdlet:</span></span>

```powershell
Get-Help Get-Member -Parameter *
```

### <a name="default-parameter-values"></a><span data-ttu-id="34ad0-122">既定のパラメーター値</span><span class="sxs-lookup"><span data-stu-id="34ad0-122">Default parameter values</span></span>

<span data-ttu-id="34ad0-123">省略可能なパラメーターには既定値があります。これは、コマンドでパラメーターが指定されていない場合に使用される値です。</span><span class="sxs-lookup"><span data-stu-id="34ad0-123">Optional parameters have a default value, which is the value that is used or assumed when the parameter is not specified in the command.</span></span>

<span data-ttu-id="34ad0-124">たとえば、多くのコマンドレットの **ComputerName** パラメーターの既定値は、ローカルコンピューターの名前です。</span><span class="sxs-lookup"><span data-stu-id="34ad0-124">For example, the default value of the **ComputerName** parameter of many cmdlets is the name of the local computer.</span></span> <span data-ttu-id="34ad0-125">このため、 **ComputerName** パラメーターが指定されていない場合、コマンドではローカルコンピューター名が使用されます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-125">As a result, the local computer name is used in the command unless the **ComputerName** parameter is specified.</span></span>

<span data-ttu-id="34ad0-126">既定のパラメーター値を確認するには、コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="34ad0-126">To find the default parameter value, see help topic for the cmdlet.</span></span> <span data-ttu-id="34ad0-127">パラメーターの説明には、既定値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad0-127">The parameter description should include the default value.</span></span>

<span data-ttu-id="34ad0-128">また、コマンドレットまたは高度な関数の任意のパラメーターに対して、カスタムの既定値を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-128">You can also set a custom default value for any parameter of a cmdlet or advanced function.</span></span> <span data-ttu-id="34ad0-129">カスタムの既定値の設定の詳細については、「 [about_Parameters_Default_Values](about_Parameters_Default_Values.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34ad0-129">For information about setting custom default values, see [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span></span>

### <a name="parameter-attribute-table"></a><span data-ttu-id="34ad0-130">パラメーター属性テーブル</span><span class="sxs-lookup"><span data-stu-id="34ad0-130">Parameter attribute table</span></span>

<span data-ttu-id="34ad0-131">コマンドレットの **Full**、 **parameter**、または **Online** パラメーターを使用すると `Get-Help` 、パラメーター `Get-Help` の詳細情報を含むパラメーター属性テーブルがによって表示されます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-131">When you use the **Full**, **Parameter**, or **Online** parameters of the `Get-Help` cmdlet, `Get-Help` displays a parameter attribute table with detailed information about the parameter.</span></span>

<span data-ttu-id="34ad0-132">この情報には、パラメーターを使用するために必要な詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="34ad0-132">This information includes the details you need to know to use the parameter.</span></span>
<span data-ttu-id="34ad0-133">たとえば、コマンドレットのヘルプトピックには、 `Get-ChildItem` Path パラメーターに関する次の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="34ad0-133">For example, the help topic for the `Get-ChildItem` cmdlet includes the following details about its Path parameter:</span></span>

```
-path <string[]>
    Specifies a path of one or more locations. Wildcard characters are
    permitted. The default location is the current directory (.).

Required?                    false
Position?                    0
Default value                Current directory
Accept pipeline input?       true (ByValue, ByPropertyName)
Accept wildcard characters?  true
```

<span data-ttu-id="34ad0-134">パラメーター情報には、パラメーターの構文、パラメーターの説明、およびパラメーターの属性が含まれます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-134">The parameter information includes the parameter syntax, a description of the parameter, and the parameter attributes.</span></span> <span data-ttu-id="34ad0-135">以下のセクションでは、パラメーターの属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="34ad0-135">The following sections describe the parameter attributes.</span></span>

#### <a name="parameter-required"></a><span data-ttu-id="34ad0-136">パラメーターが必要です</span><span class="sxs-lookup"><span data-stu-id="34ad0-136">Parameter Required</span></span>

<span data-ttu-id="34ad0-137">この設定は、パラメーターが必須かどうか、つまり、このコマンドレットを使用するすべてのコマンドにこのパラメーターを含める必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="34ad0-137">This setting indicates whether the parameter is mandatory, that is, whether all commands that use this cmdlet must include this parameter.</span></span> <span data-ttu-id="34ad0-138">この値が **True** で、パラメーターがコマンドにない場合、PowerShell はパラメーターの値を入力するように求めます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-138">When the value is **True** and the parameter is missing from the command, PowerShell prompts you for a value for the parameter.</span></span>

#### <a name="parameter-position"></a><span data-ttu-id="34ad0-139">パラメーターの位置</span><span class="sxs-lookup"><span data-stu-id="34ad0-139">Parameter Position</span></span>

<span data-ttu-id="34ad0-140">`Position`設定が正の整数に設定されている場合、パラメーター名は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="34ad0-140">If the `Position` setting is set to a positive integer, the parameter name is not required.</span></span> <span data-ttu-id="34ad0-141">この型のパラメーターは、位置指定パラメーターと呼ばれます。この数値は、他の位置指定パラメーターとの関係でパラメーターを表示する必要がある位置を示します。</span><span class="sxs-lookup"><span data-stu-id="34ad0-141">This type of parameter is referred to as a positional parameter, and the number indicates the position in which the parameter must appear in relation to other positional parameters.</span></span> <span data-ttu-id="34ad0-142">名前付きパラメーターは、コマンドレット名の後の任意の位置に表示できます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-142">A named parameter can be listed in any position after the cmdlet name.</span></span> <span data-ttu-id="34ad0-143">位置指定パラメーターのパラメーター名を指定した場合、パラメーターはコマンドレット名の後の任意の位置に一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-143">If you include the parameter name for a positional parameter, the parameter can be listed in any position after the cmdlet name.</span></span>

<span data-ttu-id="34ad0-144">たとえば、 `Get-ChildItem` コマンドレットには Path パラメーターと Exclude パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="34ad0-144">For example, the `Get-ChildItem` cmdlet has Path and Exclude parameters.</span></span> <span data-ttu-id="34ad0-145">`Position`**パス** の設定は **0** であり、これは位置指定パラメーターであることを意味します。</span><span class="sxs-lookup"><span data-stu-id="34ad0-145">The `Position` setting for **Path** is **0**, which means that it is a positional parameter.</span></span> <span data-ttu-id="34ad0-146">`Position` **Exclude** の設定には **という名前が付け** られます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-146">The `Position` setting for **Exclude** is **named**.</span></span>

<span data-ttu-id="34ad0-147">これは、 **Path** ではパラメーター名を必要としないことを意味しますが、パラメーター値はコマンドの最初のパラメーター値または無名のパラメーター値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad0-147">This means that **Path** does not require the parameter name, but its parameter value must be the first or only unnamed parameter value in the command.</span></span>
<span data-ttu-id="34ad0-148">ただし、Exclude パラメーターは名前付きパラメーターであるため、コマンド内の任意の位置に配置できます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-148">However, because the Exclude parameter is a named parameter, you can place it in any position in the command.</span></span>

<span data-ttu-id="34ad0-149">`Position`これら2つのパラメーターの設定の結果として、次のコマンドのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-149">As a result of the `Position` settings for these two parameters, you can use any of the following commands:</span></span>

```powershell
Get-ChildItem -Path c:\techdocs -Exclude *.ppt
Get-ChildItem c:\techdocs -Exclude *.ppt
Get-ChildItem -Exclude *.ppt -Path c:\techdocs
Get-ChildItem -Exclude *.ppt c:\techdocs
```

<span data-ttu-id="34ad0-150">パラメーター名を含めずに別の位置指定パラメーターを追加する場合、そのパラメーターは、設定で指定された順序で配置される必要があり `Position` ます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-150">If you were to include another positional parameter without including the parameter name, that parameter must be placed in the order specified by the `Position` setting.</span></span>

#### <a name="parameter-type"></a><span data-ttu-id="34ad0-151">パラメーターの型</span><span class="sxs-lookup"><span data-stu-id="34ad0-151">Parameter Type</span></span>

<span data-ttu-id="34ad0-152">この設定では、パラメーター値の Microsoft .NET Framework 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="34ad0-152">This setting specifies the Microsoft .NET Framework type of the parameter value.</span></span> <span data-ttu-id="34ad0-153">たとえば、型が **Int32** の場合、パラメーター値は整数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad0-153">For example, if the type is **Int32**, the parameter value must be an integer.</span></span> <span data-ttu-id="34ad0-154">型が string の場合、パラメーター値は文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad0-154">If the type is string, the parameter value must be a character string.</span></span> <span data-ttu-id="34ad0-155">文字列に空白が含まれている場合は、値を引用符で囲む必要があります。または、スペースの前にエスケープ文字 (') を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad0-155">If the string contains spaces, the value must be enclosed in quotation marks, or the spaces must be preceded by the escape character ( \` ).</span></span>

#### <a name="default-value"></a><span data-ttu-id="34ad0-156">既定値</span><span class="sxs-lookup"><span data-stu-id="34ad0-156">Default Value</span></span>

<span data-ttu-id="34ad0-157">この設定では、他の値が指定されていない場合に、パラメーターが想定する値を指定します。</span><span class="sxs-lookup"><span data-stu-id="34ad0-157">This setting specifies the value that the parameter will assume if no other value is provided.</span></span> <span data-ttu-id="34ad0-158">たとえば、Path パラメーターの既定値は、多くの場合、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="34ad0-158">For example, the default value of the Path parameter is often the current directory.</span></span> <span data-ttu-id="34ad0-159">必須のパラメーターに既定値を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="34ad0-159">Required parameters never have a default value.</span></span>
<span data-ttu-id="34ad0-160">省略可能なパラメーターの多くでは、パラメーターが使用されていない場合は効果がないため、既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="34ad0-160">For many optional parameters, there is no default because the parameter has no effect if it is not used.</span></span>

#### <a name="accepts-multiple-values"></a><span data-ttu-id="34ad0-161">複数の値を受け取る</span><span class="sxs-lookup"><span data-stu-id="34ad0-161">Accepts Multiple Values</span></span>

<span data-ttu-id="34ad0-162">この設定は、パラメーターが複数のパラメーター値を受け入れるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="34ad0-162">This setting indicates whether a parameter accepts multiple parameter values.</span></span>
<span data-ttu-id="34ad0-163">パラメーターが複数の値を受け取る場合は、コマンドのパラメーターの値としてコンマ区切りのリストを入力するか、コンマ区切りのリスト (配列) を変数に保存してから、その変数をパラメーター値として指定します。</span><span class="sxs-lookup"><span data-stu-id="34ad0-163">When a parameter accepts multiple values, you can type a comma-separated list as the value of the parameter in the command, or save a comma-separated list (an array) in a variable, and then specify the variable as the parameter value.</span></span>

<span data-ttu-id="34ad0-164">たとえば、コマンドレットの ServiceName パラメーターには、複数の値を指定 `Get-Service` できます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-164">For example, the ServiceName parameter of the `Get-Service` cmdlet accepts multiple values.</span></span> <span data-ttu-id="34ad0-165">次のコマンドは両方とも有効です。</span><span class="sxs-lookup"><span data-stu-id="34ad0-165">The following commands are both valid:</span></span>

```powershell
Get-Service -servicename winrm, netlogon
```

```powershell
$s = "winrm", "netlogon"
Get-Service -servicename $s
```

#### <a name="accepts-pipeline-input"></a><span data-ttu-id="34ad0-166">パイプライン入力の受け入れ</span><span class="sxs-lookup"><span data-stu-id="34ad0-166">Accepts Pipeline Input</span></span>

<span data-ttu-id="34ad0-167">この設定は、パイプライン演算子 () を使用して、パラメーターに値を送信できるかどうかを示し `|` ます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-167">This setting indicates whether you can use the pipeline operator ( `|` ) to send a value to the parameter.</span></span>

```
Value                    Description
-----                    -----------
False                    Indicates that you cannot pipe a value to the
                         parameter.

True (by Value)          Indicates that you can pipe any value to the
                         parameter, just so the value has the .NET
                         Framework type specified for the parameter or the
                         value can be converted to the specified .NET
                         Framework type.
```

<span data-ttu-id="34ad0-168">パラメーターが "True (値渡し)" の場合、PowerShell は他のメソッドがコマンドを解釈する前に、パイプされた値をそのパラメーターに関連付けようとします。</span><span class="sxs-lookup"><span data-stu-id="34ad0-168">When a parameter is "True (by Value)", PowerShell tries to associate any piped values with that parameter before it tries other methods to interpret the command.</span></span>

```
True (by Property Name)  Indicates that you can pipe a value to the
                         parameter, but the .NET Framework type of the
                         parameter must include a property with the same
                         name as the parameter.
```

<span data-ttu-id="34ad0-169">たとえば、値 **に name という名前** のプロパティがある場合にのみ、値を **名前** パラメーターにパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-169">For example, you can pipe a value to a **Name** parameter only when the value has a property called **Name**.</span></span>

> [!NOTE]
> <span data-ttu-id="34ad0-170">パイプラインの入力 () または () を受け入れる型指定されたパラメーター `by Value` `by PropertyName` では、パラメーターで **遅延バインディング** スクリプトブロックを使用できます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-170">A typed parameter that accepts pipeline input (`by Value`) or (`by PropertyName`) enables use of **delay-bind** script blocks on the parameter.</span></span>
>
> <span data-ttu-id="34ad0-171">**遅延バインド** スクリプトブロックは、 **parameterbinding** 中に自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-171">The **delay-bind** script block is run automatically during **ParameterBinding**.</span></span> <span data-ttu-id="34ad0-172">結果は、パラメーターにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-172">The result is bound to the parameter.</span></span> <span data-ttu-id="34ad0-173">遅延バインディングは、型または型として定義されたパラメーターに対しては機能し **ません** `ScriptBlock` `System.Object` 。スクリプトブロックは呼び出さ **ず** に渡されます。</span><span class="sxs-lookup"><span data-stu-id="34ad0-173">Delay binding does **not** work for parameters defined as type `ScriptBlock` or `System.Object`, the script block is passed through **without** being invoked.</span></span>
>
> <span data-ttu-id="34ad0-174">**遅延バインドの** スクリプトブロックについては、「about_Script_Blocks」を参照 [してください。](about_Script_Blocks.md)</span><span class="sxs-lookup"><span data-stu-id="34ad0-174">You can read about **delay-bind** script blocks here [about_Script_Blocks.md](about_Script_Blocks.md)</span></span>

#### <a name="accepts-wildcard-characters"></a><span data-ttu-id="34ad0-175">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="34ad0-175">Accepts Wildcard Characters</span></span>

<span data-ttu-id="34ad0-176">この設定では、パラメーターの値にワイルドカード文字を含めることができるかどうかを示します。これにより、ターゲットコンテナー内の複数の既存の項目とパラメーター値を照合できるようになります。</span><span class="sxs-lookup"><span data-stu-id="34ad0-176">This setting indicates whether the parameter's value can contain wildcard characters so that the parameter value can be matched to more than one existing item in the target container.</span></span>

#### <a name="common-parameters"></a><span data-ttu-id="34ad0-177">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="34ad0-177">Common Parameters</span></span>

<span data-ttu-id="34ad0-178">共通パラメーターは、任意のコマンドレットで使用できるパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="34ad0-178">Common parameters are parameters that you can use with any cmdlet.</span></span> <span data-ttu-id="34ad0-179">共通パラメーターの詳細については、「 [about_CommonParameters](about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34ad0-179">For more information about common parameters, see [about_CommonParameters](about_CommonParameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="34ad0-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="34ad0-180">See also</span></span>

[<span data-ttu-id="34ad0-181">about_Command_syntax</span><span class="sxs-lookup"><span data-stu-id="34ad0-181">about_Command_syntax</span></span>](about_Command_syntax.md)

[<span data-ttu-id="34ad0-182">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="34ad0-182">about_Comment_Based_Help</span></span>](about_Comment_Based_Help.md)

[<span data-ttu-id="34ad0-183">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="34ad0-183">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="34ad0-184">about_Parameters_Default_Values</span><span class="sxs-lookup"><span data-stu-id="34ad0-184">about_Parameters_Default_Values</span></span>](about_Parameters_Default_Values.md)

[<span data-ttu-id="34ad0-185">about_Pipelines</span><span class="sxs-lookup"><span data-stu-id="34ad0-185">about_Pipelines</span></span>](about_Pipelines.md)

[<span data-ttu-id="34ad0-186">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="34ad0-186">about_Wildcards</span></span>](about_Wildcards.md)

