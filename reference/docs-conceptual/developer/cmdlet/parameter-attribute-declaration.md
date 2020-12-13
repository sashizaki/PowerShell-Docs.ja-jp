---
ms.date: 09/13/2016
ms.topic: reference
title: パラメーター属性の宣言
description: パラメーター属性の宣言
ms.openlocfilehash: bab48a94cb4b1e8501fb79c2f3ef71393fa2ee68
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650346"
---
# <a name="parameter-attribute-declaration"></a><span data-ttu-id="c8b79-103">パラメーター属性の宣言</span><span class="sxs-lookup"><span data-stu-id="c8b79-103">Parameter Attribute Declaration</span></span>

<span data-ttu-id="c8b79-104">Parameter 属性は、コマンドレットパラメーターとしてコマンドレットクラスのパブリックプロパティを識別します。</span><span class="sxs-lookup"><span data-stu-id="c8b79-104">The Parameter attribute identifies a public property of the cmdlet class as a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="c8b79-105">構文</span><span class="sxs-lookup"><span data-stu-id="c8b79-105">Syntax</span></span>

```csharp
[Parameter()]
[Parameter(Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="c8b79-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c8b79-106">Parameters</span></span>

<span data-ttu-id="c8b79-107">`Mandatory` ([System.string) 省略](/dotnet/api/System.Boolean)可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="c8b79-107">`Mandatory` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="c8b79-108">`True` コマンドレットパラメーターが必要であることを示します。</span><span class="sxs-lookup"><span data-stu-id="c8b79-108">`True` indicates the cmdlet parameter is required.</span></span> <span data-ttu-id="c8b79-109">コマンドレットが呼び出されたときに必要なパラメーターが指定されていない場合、Windows PowerShell はユーザーにパラメーター値の入力を求めます。</span><span class="sxs-lookup"><span data-stu-id="c8b79-109">If a required parameter is not provided when the cmdlet is invoked, Windows PowerShell prompts the user for a parameter value.</span></span> <span data-ttu-id="c8b79-110">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="c8b79-110">The default is `false`.</span></span>

<span data-ttu-id="c8b79-111">`ParameterSetName` ([System.string](/dotnet/api/System.String)) 省略可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="c8b79-111">`ParameterSetName` ([System.String](/dotnet/api/System.String)) Optional named parameter.</span></span> <span data-ttu-id="c8b79-112">このコマンドレットパラメーターが属するパラメーターセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8b79-112">Specifies the parameter set that this cmdlet parameter belongs to.</span></span> <span data-ttu-id="c8b79-113">パラメーターセットが指定されていない場合、パラメーターはすべてのパラメーターセットに属します。</span><span class="sxs-lookup"><span data-stu-id="c8b79-113">If no parameter set is specified, the parameter belongs to all parameter sets.</span></span>

<span data-ttu-id="c8b79-114">`Position` ([System.string](/dotnet/api/System.Int32)) 省略可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="c8b79-114">`Position` ([System.Int32](/dotnet/api/System.Int32)) Optional named parameter.</span></span> <span data-ttu-id="c8b79-115">Windows PowerShell コマンド内のパラメーターの位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8b79-115">Specifies the position of the parameter within a Windows PowerShell command.</span></span>

<span data-ttu-id="c8b79-116">`ValueFromPipeline` ([System.string) 省略](/dotnet/api/System.Boolean)可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="c8b79-116">`ValueFromPipeline` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="c8b79-117">`True` コマンドレットパラメーターがパイプラインオブジェクトからの値を受け取ることを示します。</span><span class="sxs-lookup"><span data-stu-id="c8b79-117">`True` indicates that the cmdlet parameter takes its value from a pipeline object.</span></span> <span data-ttu-id="c8b79-118">コマンドレットがオブジェクトのプロパティだけでなく、完全なオブジェクトにアクセスする場合は、このキーワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8b79-118">Specify this keyword if the cmdlet accesses the complete object, not just a property of the object.</span></span> <span data-ttu-id="c8b79-119">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="c8b79-119">The default is `false`.</span></span>

<span data-ttu-id="c8b79-120">`ValueFromPipelineByPropertyName` ([System.string) 省略](/dotnet/api/System.Boolean)可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="c8b79-120">`ValueFromPipelineByPropertyName` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="c8b79-121">`True` コマンドレットパラメーターが、このパラメーターと同じ名前または別名を持つパイプラインオブジェクトのプロパティから値を取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="c8b79-121">`True` indicates that the cmdlet parameter takes its value from a property of a pipeline object that has either the same name or the same alias as this parameter.</span></span> <span data-ttu-id="c8b79-122">たとえば、コマンドレットにパラメーターがあり、パイプラインオブジェクトにもプロパティがある場合、 `Name` `Name` プロパティの値 `Name` は `Name` コマンドレットのパラメーターに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c8b79-122">For example, if the cmdlet has a `Name` parameter and the pipeline object also has a `Name` property, the value of the `Name` property is assigned to the `Name` parameter of the cmdlet.</span></span> <span data-ttu-id="c8b79-123">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="c8b79-123">The default is `false`.</span></span>

<span data-ttu-id="c8b79-124">`ValueFromRemainingArguments` ([System.string) 省略](/dotnet/api/System.Boolean)可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="c8b79-124">`ValueFromRemainingArguments` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="c8b79-125">`True` コマンドレットパラメーターが、コマンドレットに渡される残りのすべての引数を受け入れることを示します。</span><span class="sxs-lookup"><span data-stu-id="c8b79-125">`True` indicates that the cmdlet parameter accepts all remaining arguments that are passed to the cmdlet.</span></span> <span data-ttu-id="c8b79-126">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="c8b79-126">The default is `false`.</span></span>

<span data-ttu-id="c8b79-127">`HelpMessage` 省略可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="c8b79-127">`HelpMessage` Optional named parameter.</span></span> <span data-ttu-id="c8b79-128">パラメーターの短い説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8b79-128">Specifies a short description of the parameter.</span></span> <span data-ttu-id="c8b79-129">コマンドレットが実行され、必須パラメーターが指定されていない場合、Windows PowerShell はこのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="c8b79-129">Windows PowerShell displays this message when a cmdlet is run and a mandatory parameter is not specified.</span></span>

<span data-ttu-id="c8b79-130">`HelpMessageBaseName` 省略可能な名前付きパラメーター。リソース識別子が存在する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8b79-130">`HelpMessageBaseName` Optional named parameter.Specifies the location where resource identifiers reside.</span></span> <span data-ttu-id="c8b79-131">たとえば、このパラメーターは、ローカライズするヘルプメッセージを含むリソースアセンブリを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c8b79-131">For example, this parameter could specify a resource assembly that contains Help messages that you want to localize.</span></span>

<span data-ttu-id="c8b79-132">`HelpMessageResourceId` 省略可能な名前付きパラメーター。ヘルプメッセージのリソース識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8b79-132">`HelpMessageResourceId` Optional named parameter.Specifies the resource identifier for a Help message.</span></span>

## <a name="remarks"></a><span data-ttu-id="c8b79-133">解説</span><span class="sxs-lookup"><span data-stu-id="c8b79-133">Remarks</span></span>

- <span data-ttu-id="c8b79-134">この属性を宣言する方法の詳細については、「 [コマンドレットのパラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8b79-134">For more information about how to declare this attribute, see [How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).</span></span>

- <span data-ttu-id="c8b79-135">コマンドレットには、任意の数のパラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c8b79-135">A cmdlet can have any number of parameters.</span></span> <span data-ttu-id="c8b79-136">ただし、ユーザーエクスペリエンスを向上させるには、パラメーターの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="c8b79-136">However, for a better user experience, limit the number of parameters.</span></span>

- <span data-ttu-id="c8b79-137">パラメーターは、静的なパブリックでないフィールドまたはプロパティで宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8b79-137">Parameters must be declared on public non-static fields or properties.</span></span> <span data-ttu-id="c8b79-138">パラメーターは、プロパティで宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8b79-138">Parameters should be declared on properties.</span></span> <span data-ttu-id="c8b79-139">プロパティはパブリック set アクセサーを持つ必要があり、 `ValueFromPipeline` または `ValueFromPipelineByPropertyName` キーワードが指定されている場合、プロパティはパブリック get アクセサーを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8b79-139">The property must have a public set accessor, and if the `ValueFromPipeline` or `ValueFromPipelineByPropertyName` keyword is specified, the property must have a public get accessor.</span></span>

- <span data-ttu-id="c8b79-140">位置指定パラメーターを指定する場合は、パラメーターに設定されている位置指定パラメーターの数を5未満に制限します。</span><span class="sxs-lookup"><span data-stu-id="c8b79-140">When you specify positional parameters,  limit the number of positional parameters in a parameter set to less than five.</span></span> <span data-ttu-id="c8b79-141">また、位置指定パラメーターは連続している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c8b79-141">And, positional parameters do not have to be contiguous.</span></span> <span data-ttu-id="c8b79-142">位置5、100、および250は、位置0、1、および2と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="c8b79-142">Positions 5, 100, and 250 work the same as positions 0, 1, and 2.</span></span>

- <span data-ttu-id="c8b79-143">`Position`キーワードが指定されていない場合は、コマンドレットパラメーターを名前で参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8b79-143">When the `Position` keyword is not specified, the cmdlet parameter must be referenced by its name.</span></span>

- <span data-ttu-id="c8b79-144">パラメーターセットを使用する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c8b79-144">When you use parameter sets, note the following:</span></span>

  - <span data-ttu-id="c8b79-145">各パラメーターセットには、少なくとも1つの一意のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="c8b79-145">Each parameter set must have at least one unique parameter.</span></span> <span data-ttu-id="c8b79-146">コマンドレットの設計が適切であることは、可能であれば、この一意のパラメーターも必須であることを示します。</span><span class="sxs-lookup"><span data-stu-id="c8b79-146">Good cmdlet design indicates this unique parameter should also be mandatory if possible.</span></span> <span data-ttu-id="c8b79-147">コマンドレットをパラメーターなしで実行するように設計されている場合、unique パラメーターを必須にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c8b79-147">If your cmdlet is designed to be run without parameters, the unique parameter cannot be mandatory.</span></span>

  - <span data-ttu-id="c8b79-148">パラメーターセットには、同じ位置に複数の位置パラメーターを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="c8b79-148">No parameter set should contain more than one positional parameter with the same position.</span></span>

  - <span data-ttu-id="c8b79-149">パラメーターセット内の1つのパラメーターだけがを宣言する必要があり `ValueFromPipeline = true` ます。</span><span class="sxs-lookup"><span data-stu-id="c8b79-149">Only one parameter in a parameter set should declare `ValueFromPipeline = true`.</span></span> <span data-ttu-id="c8b79-150">複数のパラメーターでを定義でき `ValueFromPipelineByPropertyName = true` ます。</span><span class="sxs-lookup"><span data-stu-id="c8b79-150">Multiple parameters can define `ValueFromPipelineByPropertyName = true`.</span></span>

  - <span data-ttu-id="c8b79-151">複数のパラメーターでを定義でき `ValueFromPipelineByPropertyName = true` ます。</span><span class="sxs-lookup"><span data-stu-id="c8b79-151">Multiple parameters can define `ValueFromPipelineByPropertyName = true`.</span></span>

- <span data-ttu-id="c8b79-152">パラメーター名のガイドラインの詳細については、「 [コマンドレットパラメーター名](standard-cmdlet-parameter-names-and-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8b79-152">For more information about the guidelines for parameter names, see [Cmdlet Parameter Names](standard-cmdlet-parameter-names-and-types.md).</span></span>

- <span data-ttu-id="c8b79-153">Parameter 属性は、system.servicemodel [属性](/dotnet/api/System.Management.Automation.ParameterAttribute) クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="c8b79-153">The parameter attribute is defined by the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8b79-154">参照</span><span class="sxs-lookup"><span data-stu-id="c8b79-154">See Also</span></span>

[<span data-ttu-id="c8b79-155">System.string. Parameterattribute</span><span class="sxs-lookup"><span data-stu-id="c8b79-155">System.Management.Automation.Parameterattribute</span></span>](/dotnet/api/System.Management.Automation.ParameterAttribute)

[<span data-ttu-id="c8b79-156">コマンドレットのパラメーター名</span><span class="sxs-lookup"><span data-stu-id="c8b79-156">Cmdlet Parameter Names</span></span>](standard-cmdlet-parameter-names-and-types.md)

[<span data-ttu-id="c8b79-157">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="c8b79-157">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
