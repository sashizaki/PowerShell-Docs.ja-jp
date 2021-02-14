---
ms.date: 09/13/2016
ms.topic: reference
title: パラメーター属性の宣言
description: パラメーター属性の宣言
ms.openlocfilehash: 24a49406b1493a7f8c23bca798ddb3e73a901111
ms.sourcegitcommit: 77f6225ab0c8ea9faa1fe46b2ea15c178ec170e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2021
ms.locfileid: "100500231"
---
# <a name="parameter-attribute-declaration"></a><span data-ttu-id="67628-103">パラメーター属性の宣言</span><span class="sxs-lookup"><span data-stu-id="67628-103">Parameter Attribute Declaration</span></span>

<span data-ttu-id="67628-104">Parameter 属性は、コマンドレットパラメーターとしてコマンドレットクラスのパブリックプロパティを識別します。</span><span class="sxs-lookup"><span data-stu-id="67628-104">The Parameter attribute identifies a public property of the cmdlet class as a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="67628-105">構文</span><span class="sxs-lookup"><span data-stu-id="67628-105">Syntax</span></span>

```csharp
[Parameter()]
[Parameter(Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="67628-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="67628-106">Parameters</span></span>

<span data-ttu-id="67628-107">`Mandatory` ([System.string) 省略](/dotnet/api/System.Boolean)可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="67628-107">`Mandatory` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="67628-108">`True` コマンドレットパラメーターが必要であることを示します。</span><span class="sxs-lookup"><span data-stu-id="67628-108">`True` indicates the cmdlet parameter is required.</span></span> <span data-ttu-id="67628-109">コマンドレットが呼び出されたときに必要なパラメーターが指定されていない場合、Windows PowerShell はユーザーにパラメーター値の入力を求めます。</span><span class="sxs-lookup"><span data-stu-id="67628-109">If a required parameter is not provided when the cmdlet is invoked, Windows PowerShell prompts the user for a parameter value.</span></span> <span data-ttu-id="67628-110">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="67628-110">The default is `false`.</span></span>

<span data-ttu-id="67628-111">`ParameterSetName` ([System.string](/dotnet/api/System.String)) 省略可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="67628-111">`ParameterSetName` ([System.String](/dotnet/api/System.String)) Optional named parameter.</span></span> <span data-ttu-id="67628-112">このコマンドレットパラメーターが属するパラメーターセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="67628-112">Specifies the parameter set that this cmdlet parameter belongs to.</span></span> <span data-ttu-id="67628-113">パラメーターセットが指定されていない場合、パラメーターはすべてのパラメーターセットに属します。</span><span class="sxs-lookup"><span data-stu-id="67628-113">If no parameter set is specified, the parameter belongs to all parameter sets.</span></span>

<span data-ttu-id="67628-114">`Position` ([System.string](/dotnet/api/System.Int32)) 省略可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="67628-114">`Position` ([System.Int32](/dotnet/api/System.Int32)) Optional named parameter.</span></span> <span data-ttu-id="67628-115">Windows PowerShell コマンド内のパラメーターの位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="67628-115">Specifies the position of the parameter within a Windows PowerShell command.</span></span>

<span data-ttu-id="67628-116">`ValueFromPipeline` ([System.string) 省略](/dotnet/api/System.Boolean)可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="67628-116">`ValueFromPipeline` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="67628-117">`True` コマンドレットパラメーターがパイプラインオブジェクトからの値を受け取ることを示します。</span><span class="sxs-lookup"><span data-stu-id="67628-117">`True` indicates that the cmdlet parameter takes its value from a pipeline object.</span></span> <span data-ttu-id="67628-118">コマンドレットがオブジェクトのプロパティだけでなく、完全なオブジェクトにアクセスする場合は、このキーワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="67628-118">Specify this keyword if the cmdlet accesses the complete object, not just a property of the object.</span></span> <span data-ttu-id="67628-119">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="67628-119">The default is `false`.</span></span>

<span data-ttu-id="67628-120">`ValueFromPipelineByPropertyName` ([System.string) 省略](/dotnet/api/System.Boolean)可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="67628-120">`ValueFromPipelineByPropertyName` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="67628-121">`True` コマンドレットパラメーターが、このパラメーターと同じ名前または別名を持つパイプラインオブジェクトのプロパティから値を取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="67628-121">`True` indicates that the cmdlet parameter takes its value from a property of a pipeline object that has either the same name or the same alias as this parameter.</span></span> <span data-ttu-id="67628-122">たとえば、コマンドレットにパラメーターがあり、パイプラインオブジェクトにもプロパティがある場合、 `Name` `Name` プロパティの値 `Name` は `Name` コマンドレットのパラメーターに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="67628-122">For example, if the cmdlet has a `Name` parameter and the pipeline object also has a `Name` property, the value of the `Name` property is assigned to the `Name` parameter of the cmdlet.</span></span> <span data-ttu-id="67628-123">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="67628-123">The default is `false`.</span></span>

<span data-ttu-id="67628-124">`ValueFromRemainingArguments` ([System.string) 省略](/dotnet/api/System.Boolean)可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="67628-124">`ValueFromRemainingArguments` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="67628-125">`True` コマンドレットパラメーターが、コマンドレットに渡される残りのすべての引数を受け入れることを示します。</span><span class="sxs-lookup"><span data-stu-id="67628-125">`True` indicates that the cmdlet parameter accepts all remaining arguments that are passed to the cmdlet.</span></span> <span data-ttu-id="67628-126">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="67628-126">The default is `false`.</span></span>

<span data-ttu-id="67628-127">`HelpMessage` 省略可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="67628-127">`HelpMessage` Optional named parameter.</span></span> <span data-ttu-id="67628-128">パラメーターの短い説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="67628-128">Specifies a short description of the parameter.</span></span> <span data-ttu-id="67628-129">コマンドレットが実行され、必須パラメーターが指定されていない場合、Windows PowerShell はこのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="67628-129">Windows PowerShell displays this message when a cmdlet is run and a mandatory parameter is not specified.</span></span>

<span data-ttu-id="67628-130">`HelpMessageBaseName` 省略可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="67628-130">`HelpMessageBaseName` Optional named parameter.</span></span> <span data-ttu-id="67628-131">リソース識別子が存在する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="67628-131">Specifies the location where resource identifiers reside.</span></span> <span data-ttu-id="67628-132">たとえば、このパラメーターは、ローカライズするヘルプメッセージを含むリソースアセンブリを指定できます。</span><span class="sxs-lookup"><span data-stu-id="67628-132">For example, this parameter could specify a resource assembly that contains Help messages that you want to localize.</span></span>

<span data-ttu-id="67628-133">`HelpMessageResourceId` 省略可能な名前付きパラメーター。ヘルプメッセージのリソース識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="67628-133">`HelpMessageResourceId` Optional named parameter.Specifies the resource identifier for a Help message.</span></span>

## <a name="remarks"></a><span data-ttu-id="67628-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="67628-134">Remarks</span></span>

- <span data-ttu-id="67628-135">この属性を宣言する方法の詳細については、「 [コマンドレットのパラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67628-135">For more information about how to declare this attribute, see [How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).</span></span>

- <span data-ttu-id="67628-136">コマンドレットには、任意の数のパラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="67628-136">A cmdlet can have any number of parameters.</span></span> <span data-ttu-id="67628-137">ただし、ユーザーエクスペリエンスを向上させるには、パラメーターの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="67628-137">However, for a better user experience, limit the number of parameters.</span></span>

- <span data-ttu-id="67628-138">パラメーターは、静的なパブリックでないフィールドまたはプロパティで宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67628-138">Parameters must be declared on public non-static fields or properties.</span></span> <span data-ttu-id="67628-139">パラメーターは、プロパティで宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67628-139">Parameters should be declared on properties.</span></span> <span data-ttu-id="67628-140">プロパティはパブリック set アクセサーを持つ必要があり、 `ValueFromPipeline` または `ValueFromPipelineByPropertyName` キーワードが指定されている場合、プロパティはパブリック get アクセサーを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="67628-140">The property must have a public set accessor, and if the `ValueFromPipeline` or `ValueFromPipelineByPropertyName` keyword is specified, the property must have a public get accessor.</span></span>

- <span data-ttu-id="67628-141">位置指定パラメーターを指定する場合は、パラメーターに設定されている位置指定パラメーターの数を5未満に制限します。</span><span class="sxs-lookup"><span data-stu-id="67628-141">When you specify positional parameters,  limit the number of positional parameters in a parameter set to less than five.</span></span> <span data-ttu-id="67628-142">また、位置指定パラメーターは連続している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="67628-142">And, positional parameters do not have to be contiguous.</span></span> <span data-ttu-id="67628-143">位置5、100、および250は、位置0、1、および2と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="67628-143">Positions 5, 100, and 250 work the same as positions 0, 1, and 2.</span></span>

- <span data-ttu-id="67628-144">`Position`キーワードが指定されていない場合は、コマンドレットパラメーターを名前で参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67628-144">When the `Position` keyword is not specified, the cmdlet parameter must be referenced by its name.</span></span>

- <span data-ttu-id="67628-145">パラメーターセットを使用する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="67628-145">When you use parameter sets, note the following:</span></span>

  - <span data-ttu-id="67628-146">各パラメーターセットには、少なくとも1つの一意のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="67628-146">Each parameter set must have at least one unique parameter.</span></span> <span data-ttu-id="67628-147">コマンドレットの設計が適切であることは、可能であれば、この一意のパラメーターも必須であることを示します。</span><span class="sxs-lookup"><span data-stu-id="67628-147">Good cmdlet design indicates this unique parameter should also be mandatory if possible.</span></span> <span data-ttu-id="67628-148">コマンドレットをパラメーターなしで実行するように設計されている場合、unique パラメーターを必須にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="67628-148">If your cmdlet is designed to be run without parameters, the unique parameter cannot be mandatory.</span></span>

  - <span data-ttu-id="67628-149">パラメーターセットには、同じ位置に複数の位置パラメーターを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="67628-149">No parameter set should contain more than one positional parameter with the same position.</span></span>

  - <span data-ttu-id="67628-150">パラメーターセット内の1つのパラメーターだけがを宣言する必要があり `ValueFromPipeline = true` ます。</span><span class="sxs-lookup"><span data-stu-id="67628-150">Only one parameter in a parameter set should declare `ValueFromPipeline = true`.</span></span>

  - <span data-ttu-id="67628-151">複数のパラメーターでを定義でき `ValueFromPipelineByPropertyName = true` ます。</span><span class="sxs-lookup"><span data-stu-id="67628-151">Multiple parameters can define `ValueFromPipelineByPropertyName = true`.</span></span>

- <span data-ttu-id="67628-152">パラメーター名のガイドラインの詳細については、「 [コマンドレットパラメーター名](standard-cmdlet-parameter-names-and-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67628-152">For more information about the guidelines for parameter names, see [Cmdlet Parameter Names](standard-cmdlet-parameter-names-and-types.md).</span></span>

- <span data-ttu-id="67628-153">Parameter 属性は、system.servicemodel [属性](/dotnet/api/System.Management.Automation.ParameterAttribute) クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="67628-153">The parameter attribute is defined by the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="67628-154">参照</span><span class="sxs-lookup"><span data-stu-id="67628-154">See Also</span></span>

[<span data-ttu-id="67628-155">System.string. Parameterattribute</span><span class="sxs-lookup"><span data-stu-id="67628-155">System.Management.Automation.Parameterattribute</span></span>](/dotnet/api/System.Management.Automation.ParameterAttribute)

[<span data-ttu-id="67628-156">コマンドレットのパラメーター名</span><span class="sxs-lookup"><span data-stu-id="67628-156">Cmdlet Parameter Names</span></span>](standard-cmdlet-parameter-names-and-types.md)

[<span data-ttu-id="67628-157">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="67628-157">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
