---
title: Parameter 属性宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, Parameter
- Parameter attribute, described
- Parameter attribute
ms.assetid: 08433d0b-169b-42c8-9335-2881d9034698
caps.latest.revision: 13
ms.openlocfilehash: 81b1ed95669f51ba554f6f99031d098e239f02e0
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365361"
---
# <a name="parameter-attribute-declaration"></a><span data-ttu-id="19179-102">パラメーター属性の宣言</span><span class="sxs-lookup"><span data-stu-id="19179-102">Parameter Attribute Declaration</span></span>

<span data-ttu-id="19179-103">Parameter 属性は、コマンドレットパラメーターとしてコマンドレットクラスのパブリックプロパティを識別します。</span><span class="sxs-lookup"><span data-stu-id="19179-103">The Parameter attribute identifies a public property of the cmdlet class as a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="19179-104">構文</span><span class="sxs-lookup"><span data-stu-id="19179-104">Syntax</span></span>

```csharp
[Parameter()]
[Parameter(Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="19179-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19179-105">Parameters</span></span>

<span data-ttu-id="19179-106">`Mandatory` ([system.string](/dotnet/api/System.Boolean)) 省略可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="19179-106">`Mandatory` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="19179-107">`True` は、コマンドレットパラメーターが必要であることを示します。</span><span class="sxs-lookup"><span data-stu-id="19179-107">`True` indicates the cmdlet parameter is required.</span></span> <span data-ttu-id="19179-108">コマンドレットが呼び出されたときに必要なパラメーターが指定されていない場合、Windows PowerShell はユーザーにパラメーター値の入力を求めます。</span><span class="sxs-lookup"><span data-stu-id="19179-108">If a required parameter is not provided when the cmdlet is invoked, Windows PowerShell prompts the user for a parameter value.</span></span> <span data-ttu-id="19179-109">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="19179-109">The default is `false`.</span></span>

<span data-ttu-id="19179-110">`ParameterSetName` ([system.string](/dotnet/api/System.String)) 省略可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="19179-110">`ParameterSetName` ([System.String](/dotnet/api/System.String)) Optional named parameter.</span></span> <span data-ttu-id="19179-111">このコマンドレットパラメーターが属するパラメーターセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="19179-111">Specifies the parameter set that this cmdlet parameter belongs to.</span></span> <span data-ttu-id="19179-112">パラメーターセットが指定されていない場合、パラメーターはすべてのパラメーターセットに属します。</span><span class="sxs-lookup"><span data-stu-id="19179-112">If no parameter set is specified, the parameter belongs to all parameter sets.</span></span>

<span data-ttu-id="19179-113">`Position` ([system.string) 省略](/dotnet/api/System.Int32)可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="19179-113">`Position` ([System.Int32](/dotnet/api/System.Int32)) Optional named parameter.</span></span> <span data-ttu-id="19179-114">Windows PowerShell コマンド内のパラメーターの位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="19179-114">Specifies the position of the parameter within a Windows PowerShell command.</span></span>

<span data-ttu-id="19179-115">`ValueFromPipeline` ([system.string](/dotnet/api/System.Boolean)) 省略可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="19179-115">`ValueFromPipeline` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="19179-116">`True` は、コマンドレットパラメーターがパイプラインオブジェクトからの値を受け取ることを示します。</span><span class="sxs-lookup"><span data-stu-id="19179-116">`True` indicates that the cmdlet parameter takes its value from a pipeline object.</span></span> <span data-ttu-id="19179-117">コマンドレットがオブジェクトのプロパティだけでなく、完全なオブジェクトにアクセスする場合は、このキーワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="19179-117">Specify this keyword if the cmdlet accesses the complete object, not just a property of the object.</span></span> <span data-ttu-id="19179-118">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="19179-118">The default is `false`.</span></span>

<span data-ttu-id="19179-119">`ValueFromPipelineByPropertyName` ([system.string](/dotnet/api/System.Boolean)) 省略可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="19179-119">`ValueFromPipelineByPropertyName` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="19179-120">`True` は、コマンドレットパラメーターが、このパラメーターと同じ名前または別名を持つパイプラインオブジェクトのプロパティから値を受け取ることを示します。</span><span class="sxs-lookup"><span data-stu-id="19179-120">`True` indicates that the cmdlet parameter takes its value from a property of a pipeline object that has either the same name or the same alias as this parameter.</span></span> <span data-ttu-id="19179-121">たとえば、コマンドレットに `Name` パラメーターがあり、パイプラインオブジェクトにも `Name` プロパティがある場合、`Name` プロパティの値は、コマンドレットの `Name` パラメーターに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="19179-121">For example, if the cmdlet has a `Name` parameter and the pipeline object also has a `Name` property, the value of the `Name` property is assigned to the `Name` parameter of the cmdlet.</span></span> <span data-ttu-id="19179-122">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="19179-122">The default is `false`.</span></span>

<span data-ttu-id="19179-123">`ValueFromRemainingArguments` ([system.string](/dotnet/api/System.Boolean)) 省略可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="19179-123">`ValueFromRemainingArguments` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="19179-124">`True` は、コマンドレットパラメーターが、コマンドレットに渡される残りのすべての引数を受け入れることを示します。</span><span class="sxs-lookup"><span data-stu-id="19179-124">`True` indicates that the cmdlet parameter accepts all remaining arguments that are passed to the cmdlet.</span></span> <span data-ttu-id="19179-125">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="19179-125">The default is `false`.</span></span>

<span data-ttu-id="19179-126">省略可能な名前付きパラメーター `HelpMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="19179-126">`HelpMessage` Optional named parameter.</span></span> <span data-ttu-id="19179-127">パラメーターの短い説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="19179-127">Specifies a short description of the parameter.</span></span> <span data-ttu-id="19179-128">コマンドレットが実行され、必須パラメーターが指定されていない場合、Windows PowerShell はこのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="19179-128">Windows PowerShell displays this message when a cmdlet is run and a mandatory parameter is not specified.</span></span>

<span data-ttu-id="19179-129">省略可能な名前付きパラメーター `HelpMessageBaseName` ます。リソース識別子が存在する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="19179-129">`HelpMessageBaseName` Optional named parameter.Specifies the location where resource identifiers reside.</span></span> <span data-ttu-id="19179-130">たとえば、このパラメーターは、ローカライズするヘルプメッセージを含むリソースアセンブリを指定できます。</span><span class="sxs-lookup"><span data-stu-id="19179-130">For example, this parameter could specify a resource assembly that contains Help messages that you want to localize.</span></span>

<span data-ttu-id="19179-131">省略可能な名前付きパラメーター `HelpMessageResourceId` ます。ヘルプメッセージのリソース識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="19179-131">`HelpMessageResourceId` Optional named parameter.Specifies the resource identifier for a Help message.</span></span>

## <a name="remarks"></a><span data-ttu-id="19179-132">コメント</span><span class="sxs-lookup"><span data-stu-id="19179-132">Remarks</span></span>

- <span data-ttu-id="19179-133">この属性を宣言する方法の詳細については、「[コマンドレットのパラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19179-133">For more information about how to declare this attribute, see [How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).</span></span>

- <span data-ttu-id="19179-134">コマンドレットには、任意の数のパラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="19179-134">A cmdlet can have any number of parameters.</span></span> <span data-ttu-id="19179-135">ただし、ユーザーエクスペリエンスを向上させるには、パラメーターの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="19179-135">However, for a better user experience, limit the number of parameters.</span></span>

- <span data-ttu-id="19179-136">パラメーターは、静的なパブリックでないフィールドまたはプロパティで宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19179-136">Parameters must be declared on public non-static fields or properties.</span></span> <span data-ttu-id="19179-137">パラメーターは、プロパティで宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19179-137">Parameters should be declared on properties.</span></span> <span data-ttu-id="19179-138">プロパティは、パブリック set アクセサーを持つ必要があります。また、`ValueFromPipeline` または `ValueFromPipelineByPropertyName` キーワードが指定されている場合、プロパティはパブリック get アクセサーを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="19179-138">The property must have a public set accessor, and if the `ValueFromPipeline` or `ValueFromPipelineByPropertyName` keyword is specified, the property must have a public get accessor.</span></span>

- <span data-ttu-id="19179-139">位置指定パラメーターを指定する場合は、パラメーターに設定されている位置指定パラメーターの数を5未満に制限します。</span><span class="sxs-lookup"><span data-stu-id="19179-139">When you specify positional parameters,  limit the number of positional parameters in a parameter set to less than five.</span></span> <span data-ttu-id="19179-140">また、位置指定パラメーターは連続している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="19179-140">And, positional parameters do not have to be contiguous.</span></span> <span data-ttu-id="19179-141">位置5、100、および250は、位置0、1、および2と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="19179-141">Positions 5, 100, and 250 work the same as positions 0, 1, and 2.</span></span>

- <span data-ttu-id="19179-142">`Position` キーワードが指定されていない場合は、コマンドレットパラメーターを名前で参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19179-142">When the `Position` keyword is not specified, the cmdlet parameter must be referenced by its name.</span></span>

- <span data-ttu-id="19179-143">パラメーターセットを使用する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="19179-143">When you use parameter sets, note the following:</span></span>

    - <span data-ttu-id="19179-144">各パラメーターセットには、少なくとも1つの一意のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="19179-144">Each parameter set must have at least one unique parameter.</span></span> <span data-ttu-id="19179-145">コマンドレットの設計が適切であることは、可能であれば、この一意のパラメーターも必須であることを示します。</span><span class="sxs-lookup"><span data-stu-id="19179-145">Good cmdlet design indicates this unique parameter should also be mandatory if possible.</span></span> <span data-ttu-id="19179-146">コマンドレットをパラメーターなしで実行するように設計されている場合、unique パラメーターを必須にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="19179-146">If your cmdlet is designed to be run without parameters, the unique parameter cannot be mandatory.</span></span>

    - <span data-ttu-id="19179-147">パラメーターセットには、同じ位置に複数の位置パラメーターを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="19179-147">No parameter set should contain more than one positional parameter with the same position.</span></span>

    - <span data-ttu-id="19179-148">パラメーターセット内の1つのパラメーターのみが `ValueFromPipeline = true`を宣言しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="19179-148">Only one parameter in a parameter set should declare `ValueFromPipeline = true`.</span></span> <span data-ttu-id="19179-149">複数のパラメーターで `ValueFromPipelineByPropertyName = true`を定義できます。</span><span class="sxs-lookup"><span data-stu-id="19179-149">Multiple parameters can define `ValueFromPipelineByPropertyName = true`.</span></span>

    - <span data-ttu-id="19179-150">複数のパラメーターで `ValueFromPipelineByPropertyName = true`を定義できます。</span><span class="sxs-lookup"><span data-stu-id="19179-150">Multiple parameters can define `ValueFromPipelineByPropertyName = true`.</span></span>

- <span data-ttu-id="19179-151">パラメーター名のガイドラインの詳細については、「[コマンドレットパラメーター名](standard-cmdlet-parameter-names-and-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19179-151">For more information about the guidelines for parameter names, see [Cmdlet Parameter Names](standard-cmdlet-parameter-names-and-types.md).</span></span>

- <span data-ttu-id="19179-152">Parameter 属性は、system.servicemodel[属性](/dotnet/api/System.Management.Automation.ParameterAttribute)クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="19179-152">The parameter attribute is defined by the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="19179-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="19179-153">See Also</span></span>

[<span data-ttu-id="19179-154">System.string. Parameterattribute</span><span class="sxs-lookup"><span data-stu-id="19179-154">System.Management.Automation.Parameterattribute</span></span>](/dotnet/api/System.Management.Automation.ParameterAttribute)

[<span data-ttu-id="19179-155">コマンドレットのパラメーター名</span><span class="sxs-lookup"><span data-stu-id="19179-155">Cmdlet Parameter Names</span></span>](standard-cmdlet-parameter-names-and-types.md)

[<span data-ttu-id="19179-156">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="19179-156">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
