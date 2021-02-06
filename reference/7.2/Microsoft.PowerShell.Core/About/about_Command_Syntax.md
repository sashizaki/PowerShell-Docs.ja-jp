---
description: PowerShell で使用される構文図について説明します。
ms.date: 06/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_command_syntax?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Command_Syntax
ms.openlocfilehash: 8182cc856de0813f0828400bcef7170a6e165c51
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602398"
---
# <a name="about-command-syntax"></a><span data-ttu-id="106c4-103">コマンド構文について</span><span class="sxs-lookup"><span data-stu-id="106c4-103">About Command Syntax</span></span>

## <a name="short-description"></a><span data-ttu-id="106c4-104">概要</span><span class="sxs-lookup"><span data-stu-id="106c4-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="106c4-105">PowerShell で使用される構文図について説明します。</span><span class="sxs-lookup"><span data-stu-id="106c4-105">Describes the syntax diagrams that are used in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="106c4-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="106c4-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="106c4-107">[Get-help](xref:Microsoft.PowerShell.Core.Get-Help)および[get Command](xref:Microsoft.PowerShell.Core.Get-Command)コマンドレットは、コマンドを正しく構築するのに役立つ構文図を表示します。</span><span class="sxs-lookup"><span data-stu-id="106c4-107">The [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) and [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command) cmdlets display syntax diagrams to help you construct commands correctly.</span></span> <span data-ttu-id="106c4-108">このトピックでは、構文図を解釈する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="106c4-108">This topic explains how to interpret the syntax diagrams.</span></span>

## <a name="syntax-diagrams"></a><span data-ttu-id="106c4-109">構文図</span><span class="sxs-lookup"><span data-stu-id="106c4-109">SYNTAX DIAGRAMS</span></span>

<span data-ttu-id="106c4-110">コマンド構文図の各段落は、有効な形式のコマンドを表しています。</span><span class="sxs-lookup"><span data-stu-id="106c4-110">Each paragraph in a command syntax diagram represents a valid form of the command.</span></span>

<span data-ttu-id="106c4-111">コマンドを構築するには、左から右の構文図に従います。</span><span class="sxs-lookup"><span data-stu-id="106c4-111">To construct a command, follow the syntax diagram from left to right.</span></span> <span data-ttu-id="106c4-112">省略可能なパラメーターの中から選択し、プレースホルダーの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="106c4-112">Select from among the optional parameters and provide values for the placeholders.</span></span>

<span data-ttu-id="106c4-113">PowerShell では、構文図に次の表記を使用します。</span><span class="sxs-lookup"><span data-stu-id="106c4-113">PowerShell uses the following notation for syntax diagrams.</span></span>

```powershell
<command-name> -<Required Parameter Name> <Required Parameter Value>
[-<Optional Parameter Name> <Optional Parameter Value>]
[-<Optional Switch Parameters>]
[-<Optional Parameter Name>] <Required Parameter Value>
```

<span data-ttu-id="106c4-114">次に、 [新しいエイリアス](xref:Microsoft.PowerShell.Utility.New-Alias) のコマンドレットの構文を示します。</span><span class="sxs-lookup"><span data-stu-id="106c4-114">The following is the syntax for the [New-Alias](xref:Microsoft.PowerShell.Utility.New-Alias) cmdlet.</span></span>

```powershell
New-Alias [-Name] <string> [-Value] <string> [-Description <string>]
[-Force] [-Option {None | ReadOnly | Constant | Private | AllScope}]
[-PassThru] [-Scope <string>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

<span data-ttu-id="106c4-115">構文は読みやすくするために大文字で表記されますが、PowerShell では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="106c4-115">The syntax is capitalized for readability, but PowerShell is case-insensitive.</span></span>

<span data-ttu-id="106c4-116">構文ダイアグラムには、次の要素があります。</span><span class="sxs-lookup"><span data-stu-id="106c4-116">The syntax diagram has the following elements.</span></span>

## <a name="command-name"></a><span data-ttu-id="106c4-117">[コマンド名]</span><span class="sxs-lookup"><span data-stu-id="106c4-117">Command name</span></span>

<span data-ttu-id="106c4-118">コマンドは、のように、常にコマンド名で始まり `New-Alias` ます。</span><span class="sxs-lookup"><span data-stu-id="106c4-118">Commands always begin with a command name, such as `New-Alias`.</span></span> <span data-ttu-id="106c4-119">コマンド名またはそのエイリアス (たとえば、の "gcm") を入力し `Get-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="106c4-119">Type the command name or its alias, such a "gcm" for `Get-Command`.</span></span>

## <a name="parameters"></a><span data-ttu-id="106c4-120">パラメーター</span><span class="sxs-lookup"><span data-stu-id="106c4-120">Parameters</span></span>

<span data-ttu-id="106c4-121">コマンドのパラメーターは、コマンドの動作を決定するオプションです。</span><span class="sxs-lookup"><span data-stu-id="106c4-121">The parameters of a command are options that determine what the command does.</span></span>
<span data-ttu-id="106c4-122">一部のパラメーターは、"値" を受け取ります。これは、コマンドに対するユーザー入力です。</span><span class="sxs-lookup"><span data-stu-id="106c4-122">Some parameters take a "value" which is user input to the command.</span></span>

<span data-ttu-id="106c4-123">たとえば、コマンドには `Get-Help` **name** パラメーターがあり、ヘルプを表示するトピックの名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="106c4-123">For example, the `Get-Help` command has a **Name** parameter that lets you specify the name of the topic for which help is displayed.</span></span> <span data-ttu-id="106c4-124">トピック名は、 **name** パラメーターの値です。</span><span class="sxs-lookup"><span data-stu-id="106c4-124">The topic name is the value of the **Name** parameter.</span></span>

<span data-ttu-id="106c4-125">PowerShell コマンドでは、パラメーター名は常にハイフンで始まります。</span><span class="sxs-lookup"><span data-stu-id="106c4-125">In a PowerShell command, parameter names always begin with a hyphen.</span></span>
<span data-ttu-id="106c4-126">ハイフンは、コマンド内の項目がパラメーター名であることを PowerShell に伝えます。</span><span class="sxs-lookup"><span data-stu-id="106c4-126">The hyphen tells PowerShell that the item in the command is a parameter name.</span></span>

<span data-ttu-id="106c4-127">たとえば、の Name パラメーターを使用するに `New-Alias` は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="106c4-127">For example, to use the Name parameter of `New-Alias`, you type the following:</span></span>

```powershell
-Name
```

<span data-ttu-id="106c4-128">パラメーターには、必須またはオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="106c4-128">Parameters can be mandatory or optional.</span></span> <span data-ttu-id="106c4-129">構文図では、省略可能な項目が角かっこで囲まれてい `[ ]` ます。</span><span class="sxs-lookup"><span data-stu-id="106c4-129">In a syntax diagram, optional items are enclosed in brackets `[ ]`.</span></span>

<span data-ttu-id="106c4-130">パラメーターの詳細については、「 [about_Parameters](about_Parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="106c4-130">For more information about parameters, see [about_Parameters](about_Parameters.md).</span></span>

## <a name="parameter-values"></a><span data-ttu-id="106c4-131">パラメーター値</span><span class="sxs-lookup"><span data-stu-id="106c4-131">Parameter Values</span></span>

<span data-ttu-id="106c4-132">パラメーター値は、パラメーターが受け取る入力です。</span><span class="sxs-lookup"><span data-stu-id="106c4-132">A parameter value is the input that the parameter takes.</span></span> <span data-ttu-id="106c4-133">Windows PowerShell は Microsoft .NET Framework に基づいているため、パラメーター値は、.NET 型によって構文図で表現されます。</span><span class="sxs-lookup"><span data-stu-id="106c4-133">Because Windows PowerShell is based on the Microsoft .NET Framework, parameter values are represented in the syntax diagram by their .NET type.</span></span>

<span data-ttu-id="106c4-134">たとえば、の Name パラメーターは、 `Get-Help` "string" 値を受け取ります。これは、1つの単語または引用符で囲まれた複数の単語などのテキスト文字列です。</span><span class="sxs-lookup"><span data-stu-id="106c4-134">For example, the Name parameter of `Get-Help` takes a "String" value, which is a text string, such as a single word or multiple words enclosed in quotation marks.</span></span>

```powershell
[-Name] <string>
```

<span data-ttu-id="106c4-135">パラメーター値の .NET 型は、 `< >` 値のプレースホルダーであり、コマンドで入力するリテラルではないことを示すために山かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="106c4-135">The .NET type of a parameter value is enclosed in angle brackets `< >` to indicate that it is placeholder for a value and not a literal that you type in a command.</span></span>

<span data-ttu-id="106c4-136">パラメーターを使用するには、.NET 型のプレースホルダーを、指定された .NET 型のオブジェクトに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="106c4-136">To use the parameter, replace the .NET type placeholder with an object that has the specified .NET type.</span></span>

<span data-ttu-id="106c4-137">たとえば、 **Name** パラメーターを使用するには、「-Name」に続けて、次のような文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="106c4-137">For example, to use the **Name** parameter, type "-Name" followed by a string, such as the following:</span></span>

```powershell
-Name MyAlias
```

## <a name="parameters-with-no-values"></a><span data-ttu-id="106c4-138">値のないパラメーター</span><span class="sxs-lookup"><span data-stu-id="106c4-138">Parameters with no values</span></span>

<span data-ttu-id="106c4-139">一部のパラメーターは入力を受け付けないため、パラメーター値を持ちません。</span><span class="sxs-lookup"><span data-stu-id="106c4-139">Some parameters do not accept input, so they do not have a parameter value.</span></span>
<span data-ttu-id="106c4-140">値のないパラメーターは、スイッチのオン/オフのように機能するため、"スイッチパラメーター" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="106c4-140">Parameters without values are called "switch parameters" because they work like on/off switches.</span></span> <span data-ttu-id="106c4-141">これらのコマンドを使用するか ()、コマンドからそれらを省略します (オフ)。</span><span class="sxs-lookup"><span data-stu-id="106c4-141">You include them (on) or you omit them (off) from a command.</span></span>

<span data-ttu-id="106c4-142">スイッチパラメーターを使用するには、パラメーター名の前にハイフンを入力するだけです。</span><span class="sxs-lookup"><span data-stu-id="106c4-142">To use a switch parameter, just type the parameter name, preceded by a hyphen.</span></span>

<span data-ttu-id="106c4-143">たとえば、コマンドレットの **WhatIf** パラメーターを使用するに `New-Alias` は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="106c4-143">For example, to use the **WhatIf** parameter of the `New-Alias` cmdlet, type the following:</span></span>

```powershell
-WhatIf
```

## <a name="parameter-sets"></a><span data-ttu-id="106c4-144">パラメーターセット</span><span class="sxs-lookup"><span data-stu-id="106c4-144">Parameter Sets</span></span>

<span data-ttu-id="106c4-145">コマンドのパラメーターは、[パラメーターセット] に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="106c4-145">The parameters of a command are listed in parameter sets.</span></span> <span data-ttu-id="106c4-146">パラメーターセットは、構文図の段落のようになります。</span><span class="sxs-lookup"><span data-stu-id="106c4-146">Parameter sets look like the paragraphs of a syntax diagram.</span></span>

<span data-ttu-id="106c4-147">`New-Alias`コマンドレットには1つのパラメーターセットがありますが、多くのコマンドレットには複数のパラメーターセットがあります。</span><span class="sxs-lookup"><span data-stu-id="106c4-147">The `New-Alias` cmdlet has one parameter set, but many cmdlets have multiple parameter sets.</span></span> <span data-ttu-id="106c4-148">コマンドレットのパラメーターの中には、パラメーターセットに固有のものや、複数のパラメーターセットに含まれるものがあります。</span><span class="sxs-lookup"><span data-stu-id="106c4-148">Some of the cmdlet parameters are unique to a parameter set, and others appear in multiple parameter sets.</span></span> <span data-ttu-id="106c4-149">各パラメーターセットは、有効なコマンドの形式を表します。</span><span class="sxs-lookup"><span data-stu-id="106c4-149">Each parameter set represents the format of a valid command.</span></span> <span data-ttu-id="106c4-150">パラメーターセットには、コマンドで一緒に使用できるパラメーターだけが含まれています。</span><span class="sxs-lookup"><span data-stu-id="106c4-150">A parameter set includes only parameters that can be used together in a command.</span></span> <span data-ttu-id="106c4-151">パラメーターを同じコマンド内で使用できない場合は、個別のパラメーターセットに含まれます。</span><span class="sxs-lookup"><span data-stu-id="106c4-151">If parameters cannot be used in the same command, they appear in separate parameter sets.</span></span>

<span data-ttu-id="106c4-152">たとえば、 [Get Random](xref:Microsoft.PowerShell.Utility.Get-Random) コマンドレットには、次のパラメーターセットがあります。</span><span class="sxs-lookup"><span data-stu-id="106c4-152">For example, the [Get-Random](xref:Microsoft.PowerShell.Utility.Get-Random) cmdlet has the following parameter sets:</span></span>

```powershell
Get-Random [[-Maximum] <Object>] [-Minimum <Object>] [-SetSeed <int>]
[<CommonParameters>]

Get-Random [-InputObject] <Object[]> [-Count <int>] [-SetSeed <int>]
[<CommonParameters>]
```

<span data-ttu-id="106c4-153">乱数を返す最初のパラメーターセットには、 **最小** 値と **最大値** のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="106c4-153">The first parameter set, which returns a random number, has the **Minimum** and **Maximum** parameters.</span></span> <span data-ttu-id="106c4-154">2番目のパラメーターセットは、オブジェクトのセットからランダムに選択されたオブジェクトを返し、 **InputObject** パラメーターと **Count** パラメーターを含みます。</span><span class="sxs-lookup"><span data-stu-id="106c4-154">The second parameter set, which returns a randomly selected object from a set of objects, includes the **InputObject** and **Count** parameters.</span></span> <span data-ttu-id="106c4-155">どちらのパラメーターセットにも **Setseed** パラメーターと共通パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="106c4-155">Both parameter sets have the **SetSeed** parameter and the common parameters.</span></span>

<span data-ttu-id="106c4-156">これらのパラメーターセットは、同じコマンドで **InputObject** および **count** パラメーターを使用できることを示していますが、同じコマンドで **Maximum** パラメーターと **count** パラメーターを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="106c4-156">These parameter sets indicate that you can use the **InputObject** and **Count** parameters in the same command, but you cannot use the **Maximum** and **Count** parameters in the same command.</span></span>

<span data-ttu-id="106c4-157">パラメーターセットのパラメーターを使用して、使用するパラメーターセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="106c4-157">You indicate which parameter set you want to use by using the parameters in that parameter set.</span></span>

<span data-ttu-id="106c4-158">ただし、すべてのコマンドレットには、既定のパラメーターセットもあります。</span><span class="sxs-lookup"><span data-stu-id="106c4-158">However, every cmdlet also has a default parameter set.</span></span> <span data-ttu-id="106c4-159">パラメーターセットに固有のパラメーターを指定しない場合は、既定のパラメーターセットが使用されます。</span><span class="sxs-lookup"><span data-stu-id="106c4-159">The default parameter set is used when you do not specify parameters that are unique to a parameter set.</span></span> <span data-ttu-id="106c4-160">たとえば、パラメーターを指定せずにを使用する場合、 `Get-Random` Windows PowerShell は **number** パラメーターセットを使用していると想定し、乱数を返します。</span><span class="sxs-lookup"><span data-stu-id="106c4-160">For example, if you use `Get-Random` without parameters, Windows PowerShell assumes that you are using the **Number** parameter set and it returns a random number.</span></span>

<span data-ttu-id="106c4-161">各パラメーターセットでは、パラメーターが位置の順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="106c4-161">In each parameter set, the parameters appear in position order.</span></span> <span data-ttu-id="106c4-162">コマンド内のパラメーターの順序は、省略可能なパラメーター名を省略した場合にのみ重要です。</span><span class="sxs-lookup"><span data-stu-id="106c4-162">The order of parameters in a command matters only when you omit the optional parameter names.</span></span> <span data-ttu-id="106c4-163">パラメーター名を省略すると、PowerShell では、位置と型によってパラメーターに値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="106c4-163">When parameter names are omitted, PowerShell assigns values to parameters by position and type.</span></span> <span data-ttu-id="106c4-164">パラメーターの位置の詳細については、「」を参照してください `about_Parameters` 。</span><span class="sxs-lookup"><span data-stu-id="106c4-164">For more information about parameter position, see `about_Parameters`.</span></span>

## <a name="symbols-in-syntax-diagrams"></a><span data-ttu-id="106c4-165">構文図のシンボル</span><span class="sxs-lookup"><span data-stu-id="106c4-165">Symbols in Syntax Diagrams</span></span>

<span data-ttu-id="106c4-166">構文ダイアグラムには、コマンド名、コマンドパラメーター、およびパラメーター値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="106c4-166">The syntax diagram lists the command name, the command parameters, and the parameter values.</span></span> <span data-ttu-id="106c4-167">また、シンボルを使用して、有効なコマンドを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="106c4-167">It also uses symbols to show how to construct a valid command.</span></span>

<span data-ttu-id="106c4-168">構文ダイアグラムでは、次の記号が使用されます。</span><span class="sxs-lookup"><span data-stu-id="106c4-168">The syntax diagrams use the following symbols:</span></span>

- <span data-ttu-id="106c4-169">ハイフンは、 `-` パラメーター名を示します。</span><span class="sxs-lookup"><span data-stu-id="106c4-169">A hyphen `-` indicates a parameter name.</span></span> <span data-ttu-id="106c4-170">コマンドで、構文図に示すように、スペースを含めずに、パラメーター名の直前にハイフンを入力します。</span><span class="sxs-lookup"><span data-stu-id="106c4-170">In a command, type the hyphen immediately before the parameter name with no intervening spaces, as shown in the syntax diagram.</span></span>

  <span data-ttu-id="106c4-171">たとえば、の **Name** パラメーターを使用するには `New-Alias` 、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="106c4-171">For example, to use the **Name** parameter of `New-Alias`, type:</span></span>

  ```powershell
  -Name
  ```

- <span data-ttu-id="106c4-172">山かっこは `<>` 、プレースホルダーテキストを示します。</span><span class="sxs-lookup"><span data-stu-id="106c4-172">Angle brackets `<>` indicate placeholder text.</span></span> <span data-ttu-id="106c4-173">コマンドで山かっこやプレースホルダーテキストを入力することはできません。</span><span class="sxs-lookup"><span data-stu-id="106c4-173">You do not type the angle brackets or the placeholder text in a command.</span></span> <span data-ttu-id="106c4-174">代わりに、それが記述されている項目に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="106c4-174">Instead, you replace it with the item that it describes.</span></span>

  <span data-ttu-id="106c4-175">山かっこは、パラメーターの値の .NET 型を識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="106c4-175">Angle brackets are used to identify the .NET type of the value that a parameter takes.</span></span> <span data-ttu-id="106c4-176">たとえば、コマンドレットの **Name** パラメーターを使用するに `New-Alias` は、を `<string>` 1 つの単語または引用符で囲まれた単語のグループである文字列に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="106c4-176">For example, to use the **Name** parameter of the `New-Alias` cmdlet, you replace the `<string>` with a string, which is a single word or a group of words that are enclosed in quotation marks.</span></span>

- <span data-ttu-id="106c4-177">角かっこは `[ ]` 省略可能な項目を示します。</span><span class="sxs-lookup"><span data-stu-id="106c4-177">Brackets `[ ]` indicate optional items.</span></span> <span data-ttu-id="106c4-178">パラメーターとその値は省略可能です。また、必須パラメーターの名前は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="106c4-178">A parameter and its value can be optional, or the name of a required parameter can be optional.</span></span>

  <span data-ttu-id="106c4-179">たとえば、の **Description** パラメーター `New-Alias` とその値は、両方とも省略可能であるため、角かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="106c4-179">For example, the **Description** parameter of `New-Alias` and its value are enclosed in brackets because they are both optional.</span></span>

  ```powershell
  [-Description <string>]
  ```

  <span data-ttu-id="106c4-180">また、角かっこは、Name パラメーターの値が必須であることを示してい `<string>` ますが、パラメーター名 "name" は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="106c4-180">The brackets also indicate that the Name parameter value `<string>` is required, but the parameter name, "Name", is optional.</span></span>

  ```powershell
  [-Name] <string>
  ```

- <span data-ttu-id="106c4-181">.NET 型に右および左の角かっこが追加された場合、 `[]` その型の1つまたは複数の値をパラメーターが受け入れることができることを示します。</span><span class="sxs-lookup"><span data-stu-id="106c4-181">A right and left bracket `[]` appended to a .NET type indicates that the parameter can accept one or multiple values of that type.</span></span> <span data-ttu-id="106c4-182">コンマ区切りのリストで、値を入力します。</span><span class="sxs-lookup"><span data-stu-id="106c4-182">Enter the values in a comma-separated list.</span></span>

  <span data-ttu-id="106c4-183">たとえば、コマンドレットの **name** パラメーターには `New-Alias` 1 つの文字列しか使用できませんが、 [Get Process](xref:Microsoft.PowerShell.Management.Get-Process)の **name** パラメーターは、1つまたは複数の文字列を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="106c4-183">For example, the **Name** parameter of the `New-Alias` cmdlet takes only one string, but the **Name** parameter of [Get-Process](xref:Microsoft.PowerShell.Management.Get-Process) can take one or many strings.</span></span>

  ```powershell
  New-Alias [-Name] <string>

  New-Alias -Name MyAlias
  ```

  ```powershell
  Get-Process [-Name] <string[]>

  Get-Process -Name Explorer, Winlogon, Services
  ```

- <span data-ttu-id="106c4-184">中かっこ `{}` は、パラメーターの有効な値のセットである "列挙型" を示します。</span><span class="sxs-lookup"><span data-stu-id="106c4-184">Braces `{}` indicate an "enumeration," which is a set of valid values for a parameter.</span></span>

  <span data-ttu-id="106c4-185">中かっこ内の値は、縦棒で区切られ `|` ます。</span><span class="sxs-lookup"><span data-stu-id="106c4-185">The values in the braces are separated by vertical bars `|`.</span></span> <span data-ttu-id="106c4-186">これらのバーは "排他的" または "選択" を示します。つまり、中かっこ内に一覧表示される値のセットから1つの値のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="106c4-186">These bars indicate an "exclusive OR" choice, meaning that you can choose only one value from the set of values that are listed inside the braces.</span></span>

  <span data-ttu-id="106c4-187">たとえば、コマンドレットの構文には、 `New-Alias` **Option** パラメーターの次の値の列挙が含まれています。</span><span class="sxs-lookup"><span data-stu-id="106c4-187">For example, the syntax for the `New-Alias` cmdlet includes the following value enumeration for the **Option** parameter:</span></span>

  ```powershell
  -Option {None | ReadOnly | Constant | Private | AllScope}
  ```

  <span data-ttu-id="106c4-188">中かっこと縦棒は、"ReadOnly" や "AllScope" など、 **オプション** パラメーターに対して一覧表示されているいずれかの値を選択できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="106c4-188">The braces and vertical bars indicate that you can choose any one of the listed values for the **Option** parameter, such as "ReadOnly" or "AllScope".</span></span>

  ```powershell
  -Option ReadOnly
  ```

## <a name="optional-items"></a><span data-ttu-id="106c4-189">オプションの項目</span><span class="sxs-lookup"><span data-stu-id="106c4-189">Optional Items</span></span>

<span data-ttu-id="106c4-190">省略可能な項目は角かっこで `[]` 囲みます。</span><span class="sxs-lookup"><span data-stu-id="106c4-190">Brackets `[]` surround optional items.</span></span> <span data-ttu-id="106c4-191">たとえば、 `New-Alias` コマンドレットの構文の説明では、 **Scope** パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="106c4-191">For example, in the `New-Alias` cmdlet syntax description, the **Scope** parameter is optional.</span></span> <span data-ttu-id="106c4-192">この構文では、パラメーター名と型を囲む角かっこで示されています。</span><span class="sxs-lookup"><span data-stu-id="106c4-192">This is indicated in the syntax by the brackets around the parameter name and type:</span></span>

```powershell
[-Scope <string>]
```

<span data-ttu-id="106c4-193">次の例はどちらも、コマンドレットの正しい使用法です `New-Alias` 。</span><span class="sxs-lookup"><span data-stu-id="106c4-193">Both the following examples are correct uses of the `New-Alias` cmdlet:</span></span>

```powershell
New-Alias -Name utd -Value Update-TypeData
New-Alias -Name utd -Value Update-TypeData -Scope Global
```

<span data-ttu-id="106c4-194">パラメーターの値が必要な場合でも、パラメーター名を省略可能にすることができます。</span><span class="sxs-lookup"><span data-stu-id="106c4-194">A parameter name can be optional even if the value for that parameter is required.</span></span> <span data-ttu-id="106c4-195">この構文では、コマンドレットの例のように、パラメーターの型ではなく、パラメーター名を囲む角かっこで囲まれてい `New-Alias` ます。</span><span class="sxs-lookup"><span data-stu-id="106c4-195">This is indicated in the syntax by the brackets around the parameter name but not the parameter type, as in this example from the `New-Alias` cmdlet:</span></span>

```powershell
[-Name] <string> [-Value] <string>
```

<span data-ttu-id="106c4-196">次のコマンドでは、コマンドレットを正しく使用し `New-Alias` ます。</span><span class="sxs-lookup"><span data-stu-id="106c4-196">The following commands correctly use the `New-Alias` cmdlet.</span></span> <span data-ttu-id="106c4-197">コマンドを実行すると、同じ結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="106c4-197">The commands produce the same result.</span></span>

```powershell
New-Alias -Name utd -Value Update-TypeData
New-Alias -Name utd Update-TypeData
New-Alias utd -Value Update-TypeData
New-Alias utd Update-TypeData
```

<span data-ttu-id="106c4-198">パラメーター名が型指定されたステートメントに含まれていない場合、Windows PowerShell は引数の位置を使用して、パラメーターに値を割り当てようとします。</span><span class="sxs-lookup"><span data-stu-id="106c4-198">If the parameter name is not included in the statement as typed, Windows PowerShell tries to use the position of the arguments to assign the values to parameters.</span></span>

<span data-ttu-id="106c4-199">次の例は完全ではありません。</span><span class="sxs-lookup"><span data-stu-id="106c4-199">The following example is not complete:</span></span>

```powershell
New-Alias utd
```

<span data-ttu-id="106c4-200">このコマンドレットでは、 **名前** と **値** の両方のパラメーターの値が必要です。</span><span class="sxs-lookup"><span data-stu-id="106c4-200">This cmdlet requires values for both the **Name** and **Value** parameters.</span></span>

<span data-ttu-id="106c4-201">構文の例では、.NET Framework 型に名前を付けてキャストする際にも角かっこが使用されます。</span><span class="sxs-lookup"><span data-stu-id="106c4-201">In syntax examples, brackets are also used in naming and casting to .NET Framework types.</span></span> <span data-ttu-id="106c4-202">このコンテキストでは、角かっこは要素が省略可能であることを示していません。</span><span class="sxs-lookup"><span data-stu-id="106c4-202">In this context, brackets do not indicate an element is optional.</span></span>

## <a name="see-also"></a><span data-ttu-id="106c4-203">関連項目</span><span class="sxs-lookup"><span data-stu-id="106c4-203">SEE ALSO</span></span>

- [<span data-ttu-id="106c4-204">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="106c4-204">about_Parameters</span></span>](about_Parameters.md)
- [<span data-ttu-id="106c4-205">Get-Command</span><span class="sxs-lookup"><span data-stu-id="106c4-205">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)
- [<span data-ttu-id="106c4-206">Get-Help</span><span class="sxs-lookup"><span data-stu-id="106c4-206">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)

