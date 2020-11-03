---
description: PowerShell で使用される構文図について説明します。
keywords: powershell,コマンドレット
ms.date: 06/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_command_syntax?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Command_Syntax
ms.openlocfilehash: 33692eebab41e20bd85eb447cc66f1ff592977ef
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221763"
---
# <a name="about-command-syntax"></a><span data-ttu-id="457b1-104">コマンド構文について</span><span class="sxs-lookup"><span data-stu-id="457b1-104">About Command Syntax</span></span>

## <a name="short-description"></a><span data-ttu-id="457b1-105">概要</span><span class="sxs-lookup"><span data-stu-id="457b1-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="457b1-106">PowerShell で使用される構文図について説明します。</span><span class="sxs-lookup"><span data-stu-id="457b1-106">Describes the syntax diagrams that are used in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="457b1-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="457b1-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="457b1-108">[Get-help](xref:Microsoft.PowerShell.Core.Get-Help)および[get Command](xref:Microsoft.PowerShell.Core.Get-Command)コマンドレットは、コマンドを正しく構築するのに役立つ構文図を表示します。</span><span class="sxs-lookup"><span data-stu-id="457b1-108">The [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) and [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command) cmdlets display syntax diagrams to help you construct commands correctly.</span></span> <span data-ttu-id="457b1-109">このトピックでは、構文図を解釈する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="457b1-109">This topic explains how to interpret the syntax diagrams.</span></span>

## <a name="syntax-diagrams"></a><span data-ttu-id="457b1-110">構文図</span><span class="sxs-lookup"><span data-stu-id="457b1-110">SYNTAX DIAGRAMS</span></span>

<span data-ttu-id="457b1-111">コマンド構文図の各段落は、有効な形式のコマンドを表しています。</span><span class="sxs-lookup"><span data-stu-id="457b1-111">Each paragraph in a command syntax diagram represents a valid form of the command.</span></span>

<span data-ttu-id="457b1-112">コマンドを構築するには、左から右の構文図に従います。</span><span class="sxs-lookup"><span data-stu-id="457b1-112">To construct a command, follow the syntax diagram from left to right.</span></span> <span data-ttu-id="457b1-113">省略可能なパラメーターの中から選択し、プレースホルダーの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="457b1-113">Select from among the optional parameters and provide values for the placeholders.</span></span>

<span data-ttu-id="457b1-114">PowerShell では、構文図に次の表記を使用します。</span><span class="sxs-lookup"><span data-stu-id="457b1-114">PowerShell uses the following notation for syntax diagrams.</span></span>

```powershell
<command-name> -<Required Parameter Name> <Required Parameter Value>
[-<Optional Parameter Name> <Optional Parameter Value>]
[-<Optional Switch Parameters>]
[-<Optional Parameter Name>] <Required Parameter Value>
```

<span data-ttu-id="457b1-115">次に、 [新しいエイリアス](xref:Microsoft.PowerShell.Utility.New-Alias) のコマンドレットの構文を示します。</span><span class="sxs-lookup"><span data-stu-id="457b1-115">The following is the syntax for the [New-Alias](xref:Microsoft.PowerShell.Utility.New-Alias) cmdlet.</span></span>

```powershell
New-Alias [-Name] <string> [-Value] <string> [-Description <string>]
[-Force] [-Option {None | ReadOnly | Constant | Private | AllScope}]
[-PassThru] [-Scope <string>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

<span data-ttu-id="457b1-116">構文は読みやすくするために大文字で表記されますが、PowerShell では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="457b1-116">The syntax is capitalized for readability, but PowerShell is case-insensitive.</span></span>

<span data-ttu-id="457b1-117">構文ダイアグラムには、次の要素があります。</span><span class="sxs-lookup"><span data-stu-id="457b1-117">The syntax diagram has the following elements.</span></span>

## <a name="command-name"></a><span data-ttu-id="457b1-118">[コマンド名]</span><span class="sxs-lookup"><span data-stu-id="457b1-118">Command name</span></span>

<span data-ttu-id="457b1-119">コマンドは、のように、常にコマンド名で始まり `New-Alias` ます。</span><span class="sxs-lookup"><span data-stu-id="457b1-119">Commands always begin with a command name, such as `New-Alias`.</span></span> <span data-ttu-id="457b1-120">コマンド名またはそのエイリアス (たとえば、の "gcm") を入力し `Get-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="457b1-120">Type the command name or its alias, such a "gcm" for `Get-Command`.</span></span>

## <a name="parameters"></a><span data-ttu-id="457b1-121">パラメーター</span><span class="sxs-lookup"><span data-stu-id="457b1-121">Parameters</span></span>

<span data-ttu-id="457b1-122">コマンドのパラメーターは、コマンドの動作を決定するオプションです。</span><span class="sxs-lookup"><span data-stu-id="457b1-122">The parameters of a command are options that determine what the command does.</span></span>
<span data-ttu-id="457b1-123">一部のパラメーターは、"値" を受け取ります。これは、コマンドに対するユーザー入力です。</span><span class="sxs-lookup"><span data-stu-id="457b1-123">Some parameters take a "value" which is user input to the command.</span></span>

<span data-ttu-id="457b1-124">たとえば、コマンドには `Get-Help` **name** パラメーターがあり、ヘルプを表示するトピックの名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="457b1-124">For example, the `Get-Help` command has a **Name** parameter that lets you specify the name of the topic for which help is displayed.</span></span> <span data-ttu-id="457b1-125">トピック名は、 **name** パラメーターの値です。</span><span class="sxs-lookup"><span data-stu-id="457b1-125">The topic name is the value of the **Name** parameter.</span></span>

<span data-ttu-id="457b1-126">PowerShell コマンドでは、パラメーター名は常にハイフンで始まります。</span><span class="sxs-lookup"><span data-stu-id="457b1-126">In a PowerShell command, parameter names always begin with a hyphen.</span></span>
<span data-ttu-id="457b1-127">ハイフンは、コマンド内の項目がパラメーター名であることを PowerShell に伝えます。</span><span class="sxs-lookup"><span data-stu-id="457b1-127">The hyphen tells PowerShell that the item in the command is a parameter name.</span></span>

<span data-ttu-id="457b1-128">たとえば、の Name パラメーターを使用するに `New-Alias` は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="457b1-128">For example, to use the Name parameter of `New-Alias`, you type the following:</span></span>

```powershell
-Name
```

<span data-ttu-id="457b1-129">パラメーターには、必須またはオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="457b1-129">Parameters can be mandatory or optional.</span></span> <span data-ttu-id="457b1-130">構文図では、省略可能な項目が角かっこで囲まれてい `[ ]` ます。</span><span class="sxs-lookup"><span data-stu-id="457b1-130">In a syntax diagram, optional items are enclosed in brackets `[ ]`.</span></span>

<span data-ttu-id="457b1-131">パラメーターの詳細については、「 [about_Parameters](about_Parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="457b1-131">For more information about parameters, see [about_Parameters](about_Parameters.md).</span></span>

## <a name="parameter-values"></a><span data-ttu-id="457b1-132">パラメーター値</span><span class="sxs-lookup"><span data-stu-id="457b1-132">Parameter Values</span></span>

<span data-ttu-id="457b1-133">パラメーター値は、パラメーターが受け取る入力です。</span><span class="sxs-lookup"><span data-stu-id="457b1-133">A parameter value is the input that the parameter takes.</span></span> <span data-ttu-id="457b1-134">Windows PowerShell は Microsoft .NET Framework に基づいているため、パラメーター値は、.NET 型によって構文図で表現されます。</span><span class="sxs-lookup"><span data-stu-id="457b1-134">Because Windows PowerShell is based on the Microsoft .NET Framework, parameter values are represented in the syntax diagram by their .NET type.</span></span>

<span data-ttu-id="457b1-135">たとえば、の Name パラメーターは、 `Get-Help` "string" 値を受け取ります。これは、1つの単語または引用符で囲まれた複数の単語などのテキスト文字列です。</span><span class="sxs-lookup"><span data-stu-id="457b1-135">For example, the Name parameter of `Get-Help` takes a "String" value, which is a text string, such as a single word or multiple words enclosed in quotation marks.</span></span>

```powershell
[-Name] <string>
```

<span data-ttu-id="457b1-136">パラメーター値の .NET 型は、 `< >` 値のプレースホルダーであり、コマンドで入力するリテラルではないことを示すために山かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="457b1-136">The .NET type of a parameter value is enclosed in angle brackets `< >` to indicate that it is placeholder for a value and not a literal that you type in a command.</span></span>

<span data-ttu-id="457b1-137">パラメーターを使用するには、.NET 型のプレースホルダーを、指定された .NET 型のオブジェクトに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="457b1-137">To use the parameter, replace the .NET type placeholder with an object that has the specified .NET type.</span></span>

<span data-ttu-id="457b1-138">たとえば、 **Name** パラメーターを使用するには、「-Name」に続けて、次のような文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="457b1-138">For example, to use the **Name** parameter, type "-Name" followed by a string, such as the following:</span></span>

```powershell
-Name MyAlias
```

## <a name="parameters-with-no-values"></a><span data-ttu-id="457b1-139">値のないパラメーター</span><span class="sxs-lookup"><span data-stu-id="457b1-139">Parameters with no values</span></span>

<span data-ttu-id="457b1-140">一部のパラメーターは入力を受け付けないため、パラメーター値を持ちません。</span><span class="sxs-lookup"><span data-stu-id="457b1-140">Some parameters do not accept input, so they do not have a parameter value.</span></span>
<span data-ttu-id="457b1-141">値のないパラメーターは、スイッチのオン/オフのように機能するため、"スイッチパラメーター" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="457b1-141">Parameters without values are called "switch parameters" because they work like on/off switches.</span></span> <span data-ttu-id="457b1-142">これらのコマンドを使用するか ()、コマンドからそれらを省略します (オフ)。</span><span class="sxs-lookup"><span data-stu-id="457b1-142">You include them (on) or you omit them (off) from a command.</span></span>

<span data-ttu-id="457b1-143">スイッチパラメーターを使用するには、パラメーター名の前にハイフンを入力するだけです。</span><span class="sxs-lookup"><span data-stu-id="457b1-143">To use a switch parameter, just type the parameter name, preceded by a hyphen.</span></span>

<span data-ttu-id="457b1-144">たとえば、コマンドレットの **WhatIf** パラメーターを使用するに `New-Alias` は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="457b1-144">For example, to use the **WhatIf** parameter of the `New-Alias` cmdlet, type the following:</span></span>

```powershell
-WhatIf
```

## <a name="parameter-sets"></a><span data-ttu-id="457b1-145">パラメーターセット</span><span class="sxs-lookup"><span data-stu-id="457b1-145">Parameter Sets</span></span>

<span data-ttu-id="457b1-146">コマンドのパラメーターは、[パラメーターセット] に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="457b1-146">The parameters of a command are listed in parameter sets.</span></span> <span data-ttu-id="457b1-147">パラメーターセットは、構文図の段落のようになります。</span><span class="sxs-lookup"><span data-stu-id="457b1-147">Parameter sets look like the paragraphs of a syntax diagram.</span></span>

<span data-ttu-id="457b1-148">`New-Alias`コマンドレットには1つのパラメーターセットがありますが、多くのコマンドレットには複数のパラメーターセットがあります。</span><span class="sxs-lookup"><span data-stu-id="457b1-148">The `New-Alias` cmdlet has one parameter set, but many cmdlets have multiple parameter sets.</span></span> <span data-ttu-id="457b1-149">コマンドレットのパラメーターの中には、パラメーターセットに固有のものや、複数のパラメーターセットに含まれるものがあります。</span><span class="sxs-lookup"><span data-stu-id="457b1-149">Some of the cmdlet parameters are unique to a parameter set, and others appear in multiple parameter sets.</span></span> <span data-ttu-id="457b1-150">各パラメーターセットは、有効なコマンドの形式を表します。</span><span class="sxs-lookup"><span data-stu-id="457b1-150">Each parameter set represents the format of a valid command.</span></span> <span data-ttu-id="457b1-151">パラメーターセットには、コマンドで一緒に使用できるパラメーターだけが含まれています。</span><span class="sxs-lookup"><span data-stu-id="457b1-151">A parameter set includes only parameters that can be used together in a command.</span></span> <span data-ttu-id="457b1-152">パラメーターを同じコマンド内で使用できない場合は、個別のパラメーターセットに含まれます。</span><span class="sxs-lookup"><span data-stu-id="457b1-152">If parameters cannot be used in the same command, they appear in separate parameter sets.</span></span>

<span data-ttu-id="457b1-153">たとえば、 [Get Random](xref:Microsoft.PowerShell.Utility.Get-Random) コマンドレットには、次のパラメーターセットがあります。</span><span class="sxs-lookup"><span data-stu-id="457b1-153">For example, the [Get-Random](xref:Microsoft.PowerShell.Utility.Get-Random) cmdlet has the following parameter sets:</span></span>

```powershell
Get-Random [[-Maximum] <Object>] [-Minimum <Object>] [-SetSeed <int>]
[<CommonParameters>]

Get-Random [-InputObject] <Object[]> [-Count <int>] [-SetSeed <int>]
[<CommonParameters>]
```

<span data-ttu-id="457b1-154">乱数を返す最初のパラメーターセットには、 **最小** 値と **最大値** のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="457b1-154">The first parameter set, which returns a random number, has the **Minimum** and **Maximum** parameters.</span></span> <span data-ttu-id="457b1-155">2番目のパラメーターセットは、オブジェクトのセットからランダムに選択されたオブジェクトを返し、 **InputObject** パラメーターと **Count** パラメーターを含みます。</span><span class="sxs-lookup"><span data-stu-id="457b1-155">The second parameter set, which returns a randomly selected object from a set of objects, includes the **InputObject** and **Count** parameters.</span></span> <span data-ttu-id="457b1-156">どちらのパラメーターセットにも **Setseed** パラメーターと共通パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="457b1-156">Both parameter sets have the **SetSeed** parameter and the common parameters.</span></span>

<span data-ttu-id="457b1-157">これらのパラメーターセットは、同じコマンドで **InputObject** および **count** パラメーターを使用できることを示していますが、同じコマンドで **Maximum** パラメーターと **count** パラメーターを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="457b1-157">These parameter sets indicate that you can use the **InputObject** and **Count** parameters in the same command, but you cannot use the **Maximum** and **Count** parameters in the same command.</span></span>

<span data-ttu-id="457b1-158">パラメーターセットのパラメーターを使用して、使用するパラメーターセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="457b1-158">You indicate which parameter set you want to use by using the parameters in that parameter set.</span></span>

<span data-ttu-id="457b1-159">ただし、すべてのコマンドレットには、既定のパラメーターセットもあります。</span><span class="sxs-lookup"><span data-stu-id="457b1-159">However, every cmdlet also has a default parameter set.</span></span> <span data-ttu-id="457b1-160">パラメーターセットに固有のパラメーターを指定しない場合は、既定のパラメーターセットが使用されます。</span><span class="sxs-lookup"><span data-stu-id="457b1-160">The default parameter set is used when you do not specify parameters that are unique to a parameter set.</span></span> <span data-ttu-id="457b1-161">たとえば、パラメーターを指定せずにを使用する場合、 `Get-Random` Windows PowerShell は **number** パラメーターセットを使用していると想定し、乱数を返します。</span><span class="sxs-lookup"><span data-stu-id="457b1-161">For example, if you use `Get-Random` without parameters, Windows PowerShell assumes that you are using the **Number** parameter set and it returns a random number.</span></span>

<span data-ttu-id="457b1-162">各パラメーターセットでは、パラメーターが位置の順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="457b1-162">In each parameter set, the parameters appear in position order.</span></span> <span data-ttu-id="457b1-163">コマンド内のパラメーターの順序は、省略可能なパラメーター名を省略した場合にのみ重要です。</span><span class="sxs-lookup"><span data-stu-id="457b1-163">The order of parameters in a command matters only when you omit the optional parameter names.</span></span> <span data-ttu-id="457b1-164">パラメーター名を省略すると、PowerShell では、位置と型によってパラメーターに値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="457b1-164">When parameter names are omitted, PowerShell assigns values to parameters by position and type.</span></span> <span data-ttu-id="457b1-165">パラメーターの位置の詳細については、「」を参照してください `about_Parameters` 。</span><span class="sxs-lookup"><span data-stu-id="457b1-165">For more information about parameter position, see `about_Parameters`.</span></span>

## <a name="symbols-in-syntax-diagrams"></a><span data-ttu-id="457b1-166">構文図のシンボル</span><span class="sxs-lookup"><span data-stu-id="457b1-166">Symbols in Syntax Diagrams</span></span>

<span data-ttu-id="457b1-167">構文ダイアグラムには、コマンド名、コマンドパラメーター、およびパラメーター値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="457b1-167">The syntax diagram lists the command name, the command parameters, and the parameter values.</span></span> <span data-ttu-id="457b1-168">また、シンボルを使用して、有効なコマンドを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="457b1-168">It also uses symbols to show how to construct a valid command.</span></span>

<span data-ttu-id="457b1-169">構文ダイアグラムでは、次の記号が使用されます。</span><span class="sxs-lookup"><span data-stu-id="457b1-169">The syntax diagrams use the following symbols:</span></span>

- <span data-ttu-id="457b1-170">ハイフンは、 `-` パラメーター名を示します。</span><span class="sxs-lookup"><span data-stu-id="457b1-170">A hyphen `-` indicates a parameter name.</span></span> <span data-ttu-id="457b1-171">コマンドで、構文図に示すように、スペースを含めずに、パラメーター名の直前にハイフンを入力します。</span><span class="sxs-lookup"><span data-stu-id="457b1-171">In a command, type the hyphen immediately before the parameter name with no intervening spaces, as shown in the syntax diagram.</span></span>

  <span data-ttu-id="457b1-172">たとえば、の **Name** パラメーターを使用するには `New-Alias` 、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="457b1-172">For example, to use the **Name** parameter of `New-Alias`, type:</span></span>

  ```powershell
  -Name
  ```

- <span data-ttu-id="457b1-173">山かっこは `<>` 、プレースホルダーテキストを示します。</span><span class="sxs-lookup"><span data-stu-id="457b1-173">Angle brackets `<>` indicate placeholder text.</span></span> <span data-ttu-id="457b1-174">コマンドで山かっこやプレースホルダーテキストを入力することはできません。</span><span class="sxs-lookup"><span data-stu-id="457b1-174">You do not type the angle brackets or the placeholder text in a command.</span></span> <span data-ttu-id="457b1-175">代わりに、それが記述されている項目に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="457b1-175">Instead, you replace it with the item that it describes.</span></span>

  <span data-ttu-id="457b1-176">山かっこは、パラメーターの値の .NET 型を識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="457b1-176">Angle brackets are used to identify the .NET type of the value that a parameter takes.</span></span> <span data-ttu-id="457b1-177">たとえば、コマンドレットの **Name** パラメーターを使用するに `New-Alias` は、を `<string>` 1 つの単語または引用符で囲まれた単語のグループである文字列に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="457b1-177">For example, to use the **Name** parameter of the `New-Alias` cmdlet, you replace the `<string>` with a string, which is a single word or a group of words that are enclosed in quotation marks.</span></span>

- <span data-ttu-id="457b1-178">角かっこは `[ ]` 省略可能な項目を示します。</span><span class="sxs-lookup"><span data-stu-id="457b1-178">Brackets `[ ]` indicate optional items.</span></span> <span data-ttu-id="457b1-179">パラメーターとその値は省略可能です。また、必須パラメーターの名前は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="457b1-179">A parameter and its value can be optional, or the name of a required parameter can be optional.</span></span>

  <span data-ttu-id="457b1-180">たとえば、の **Description** パラメーター `New-Alias` とその値は、両方とも省略可能であるため、角かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="457b1-180">For example, the **Description** parameter of `New-Alias` and its value are enclosed in brackets because they are both optional.</span></span>

  ```powershell
  [-Description <string>]
  ```

  <span data-ttu-id="457b1-181">また、角かっこは、Name パラメーターの値が必須であることを示してい `<string>` ますが、パラメーター名 "name" は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="457b1-181">The brackets also indicate that the Name parameter value `<string>` is required, but the parameter name, "Name", is optional.</span></span>

  ```powershell
  [-Name] <string>
  ```

- <span data-ttu-id="457b1-182">.NET 型に右および左の角かっこが追加された場合、 `[]` その型の1つまたは複数の値をパラメーターが受け入れることができることを示します。</span><span class="sxs-lookup"><span data-stu-id="457b1-182">A right and left bracket `[]` appended to a .NET type indicates that the parameter can accept one or multiple values of that type.</span></span> <span data-ttu-id="457b1-183">コンマ区切りのリストで、値を入力します。</span><span class="sxs-lookup"><span data-stu-id="457b1-183">Enter the values in a comma-separated list.</span></span>

  <span data-ttu-id="457b1-184">たとえば、コマンドレットの **name** パラメーターには `New-Alias` 1 つの文字列しか使用できませんが、 [Get Process](xref:Microsoft.PowerShell.Management.Get-Process)の **name** パラメーターは、1つまたは複数の文字列を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="457b1-184">For example, the **Name** parameter of the `New-Alias` cmdlet takes only one string, but the **Name** parameter of [Get-Process](xref:Microsoft.PowerShell.Management.Get-Process) can take one or many strings.</span></span>

  ```powershell
  New-Alias [-Name] <string>

  New-Alias -Name MyAlias
  ```

  ```powershell
  Get-Process [-Name] <string[]>

  Get-Process -Name Explorer, Winlogon, Services
  ```

- <span data-ttu-id="457b1-185">中かっこ `{}` は、パラメーターの有効な値のセットである "列挙型" を示します。</span><span class="sxs-lookup"><span data-stu-id="457b1-185">Braces `{}` indicate an "enumeration," which is a set of valid values for a parameter.</span></span>

  <span data-ttu-id="457b1-186">中かっこ内の値は、縦棒で区切られ `|` ます。</span><span class="sxs-lookup"><span data-stu-id="457b1-186">The values in the braces are separated by vertical bars `|`.</span></span> <span data-ttu-id="457b1-187">これらのバーは "排他的" または "選択" を示します。つまり、中かっこ内に一覧表示される値のセットから1つの値のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="457b1-187">These bars indicate an "exclusive OR" choice, meaning that you can choose only one value from the set of values that are listed inside the braces.</span></span>

  <span data-ttu-id="457b1-188">たとえば、コマンドレットの構文には、 `New-Alias` **Option** パラメーターの次の値の列挙が含まれています。</span><span class="sxs-lookup"><span data-stu-id="457b1-188">For example, the syntax for the `New-Alias` cmdlet includes the following value enumeration for the **Option** parameter:</span></span>

  ```powershell
  -Option {None | ReadOnly | Constant | Private | AllScope}
  ```

  <span data-ttu-id="457b1-189">中かっこと縦棒は、"ReadOnly" や "AllScope" など、 **オプション** パラメーターに対して一覧表示されているいずれかの値を選択できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="457b1-189">The braces and vertical bars indicate that you can choose any one of the listed values for the **Option** parameter, such as "ReadOnly" or "AllScope".</span></span>

  ```powershell
  -Option ReadOnly
  ```

## <a name="optional-items"></a><span data-ttu-id="457b1-190">オプションの項目</span><span class="sxs-lookup"><span data-stu-id="457b1-190">Optional Items</span></span>

<span data-ttu-id="457b1-191">省略可能な項目は角かっこで `[]` 囲みます。</span><span class="sxs-lookup"><span data-stu-id="457b1-191">Brackets `[]` surround optional items.</span></span> <span data-ttu-id="457b1-192">たとえば、 `New-Alias` コマンドレットの構文の説明では、 **Scope** パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="457b1-192">For example, in the `New-Alias` cmdlet syntax description, the **Scope** parameter is optional.</span></span> <span data-ttu-id="457b1-193">この構文では、パラメーター名と型を囲む角かっこで示されています。</span><span class="sxs-lookup"><span data-stu-id="457b1-193">This is indicated in the syntax by the brackets around the parameter name and type:</span></span>

```powershell
[-Scope <string>]
```

<span data-ttu-id="457b1-194">次の例はどちらも、コマンドレットの正しい使用法です `New-Alias` 。</span><span class="sxs-lookup"><span data-stu-id="457b1-194">Both the following examples are correct uses of the `New-Alias` cmdlet:</span></span>

```powershell
New-Alias -Name utd -Value Update-TypeData
New-Alias -Name utd -Value Update-TypeData -Scope Global
```

<span data-ttu-id="457b1-195">パラメーターの値が必要な場合でも、パラメーター名を省略可能にすることができます。</span><span class="sxs-lookup"><span data-stu-id="457b1-195">A parameter name can be optional even if the value for that parameter is required.</span></span> <span data-ttu-id="457b1-196">この構文では、コマンドレットの例のように、パラメーターの型ではなく、パラメーター名を囲む角かっこで囲まれてい `New-Alias` ます。</span><span class="sxs-lookup"><span data-stu-id="457b1-196">This is indicated in the syntax by the brackets around the parameter name but not the parameter type, as in this example from the `New-Alias` cmdlet:</span></span>

```powershell
[-Name] <string> [-Value] <string>
```

<span data-ttu-id="457b1-197">次のコマンドでは、コマンドレットを正しく使用し `New-Alias` ます。</span><span class="sxs-lookup"><span data-stu-id="457b1-197">The following commands correctly use the `New-Alias` cmdlet.</span></span> <span data-ttu-id="457b1-198">コマンドを実行すると、同じ結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="457b1-198">The commands produce the same result.</span></span>

```powershell
New-Alias -Name utd -Value Update-TypeData
New-Alias -Name utd Update-TypeData
New-Alias utd -Value Update-TypeData
New-Alias utd Update-TypeData
```

<span data-ttu-id="457b1-199">パラメーター名が型指定されたステートメントに含まれていない場合、Windows PowerShell は引数の位置を使用して、パラメーターに値を割り当てようとします。</span><span class="sxs-lookup"><span data-stu-id="457b1-199">If the parameter name is not included in the statement as typed, Windows PowerShell tries to use the position of the arguments to assign the values to parameters.</span></span>

<span data-ttu-id="457b1-200">次の例は完全ではありません。</span><span class="sxs-lookup"><span data-stu-id="457b1-200">The following example is not complete:</span></span>

```powershell
New-Alias utd
```

<span data-ttu-id="457b1-201">このコマンドレットでは、 **名前** と **値** の両方のパラメーターの値が必要です。</span><span class="sxs-lookup"><span data-stu-id="457b1-201">This cmdlet requires values for both the **Name** and **Value** parameters.</span></span>

<span data-ttu-id="457b1-202">構文の例では、.NET Framework 型に名前を付けてキャストする際にも角かっこが使用されます。</span><span class="sxs-lookup"><span data-stu-id="457b1-202">In syntax examples, brackets are also used in naming and casting to .NET Framework types.</span></span> <span data-ttu-id="457b1-203">このコンテキストでは、角かっこは要素が省略可能であることを示していません。</span><span class="sxs-lookup"><span data-stu-id="457b1-203">In this context, brackets do not indicate an element is optional.</span></span>

## <a name="see-also"></a><span data-ttu-id="457b1-204">関連項目</span><span class="sxs-lookup"><span data-stu-id="457b1-204">SEE ALSO</span></span>

- [<span data-ttu-id="457b1-205">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="457b1-205">about_Parameters</span></span>](about_Parameters.md)
- [<span data-ttu-id="457b1-206">Get-Command</span><span class="sxs-lookup"><span data-stu-id="457b1-206">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)
- [<span data-ttu-id="457b1-207">Get-Help</span><span class="sxs-lookup"><span data-stu-id="457b1-207">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)
