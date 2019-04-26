---
title: パラメーター属性の宣言 |Microsoft Docs
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
ms.openlocfilehash: a3488d5fb3f7eb3df28d0242d6c39d07145a3c8d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067554"
---
# <a name="parameter-attribute-declaration"></a><span data-ttu-id="eb7ba-102">パラメーター属性の宣言</span><span class="sxs-lookup"><span data-stu-id="eb7ba-102">Parameter Attribute Declaration</span></span>

<span data-ttu-id="eb7ba-103">パラメーター属性では、コマンドレット パラメーターとして、コマンドレット クラスのパブリック プロパティを識別します。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-103">The Parameter attribute identifies a public property of the cmdlet class as a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="eb7ba-104">構文</span><span class="sxs-lookup"><span data-stu-id="eb7ba-104">Syntax</span></span>

```csharp
[Parameter()]
[Parameter(Named Parameters...)]
```

#### <a name="parameters"></a><span data-ttu-id="eb7ba-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eb7ba-105">Parameters</span></span>

<span data-ttu-id="eb7ba-106">`Mandatory` ([System.Boolean](/dotnet/api/System.Boolean)) という名前のパラメーター (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-106">`Mandatory` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="eb7ba-107">`True` コマンドレットのパラメーターが必要なことを示します。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-107">`True` indicates the cmdlet parameter is required.</span></span> <span data-ttu-id="eb7ba-108">コマンドレットが呼び出されたときに必要なパラメーターが指定されていない場合、Windows PowerShell には、パラメーター値をユーザーが求められます。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-108">If a required parameter is not provided when the cmdlet is invoked, Windows PowerShell prompts the user for a parameter value.</span></span> <span data-ttu-id="eb7ba-109">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-109">The default is `false`.</span></span>

<span data-ttu-id="eb7ba-110">`ParameterSetName` ([System.String](/dotnet/api/System.String)) という名前のパラメーター (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-110">`ParameterSetName` ([System.String](/dotnet/api/System.String)) Optional named parameter.</span></span> <span data-ttu-id="eb7ba-111">パラメーターの設定をこのコマンドレットのパラメーターが属していることを指定します。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-111">Specifies the parameter set that this cmdlet parameter belongs to.</span></span> <span data-ttu-id="eb7ba-112">パラメーター セットが指定されていない場合、パラメーターは、すべてのパラメーター セットに属しています。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-112">If no parameter set is specified, the parameter belongs to all parameter sets.</span></span>

<span data-ttu-id="eb7ba-113">`Position` ([System.Integer](/dotnet/api/System.Integer)) という名前のパラメーター (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-113">`Position` ([System.Integer](/dotnet/api/System.Integer)) Optional named parameter.</span></span> <span data-ttu-id="eb7ba-114">Windows PowerShell コマンド内でパラメーターの位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-114">Specifies the position of the parameter within a Windows PowerShell command.</span></span>

<span data-ttu-id="eb7ba-115">`ValueFromPipeline` ([System.Boolean](/dotnet/api/System.Boolean)) という名前のパラメーター (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-115">`ValueFromPipeline` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="eb7ba-116">`True` コマンドレットのパラメーターが、パイプライン オブジェクトから値を受け取ることを示します。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-116">`True` indicates that the cmdlet parameter takes its value from a pipeline object.</span></span> <span data-ttu-id="eb7ba-117">コマンドレットが、完全にアクセスする場合にこのキーワードを指定するだけでなく、オブジェクトのプロパティのオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-117">Specify this keyword if the cmdlet accesses the complete object, not just a property of the object.</span></span> <span data-ttu-id="eb7ba-118">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-118">The default is `false`.</span></span>

<span data-ttu-id="eb7ba-119">`ValueFromPipelineByPropertyName` ([System.Boolean](/dotnet/api/System.Boolean)) という名前のパラメーター (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-119">`ValueFromPipelineByPropertyName` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="eb7ba-120">`True` コマンドレットのパラメーターが同じ名前またはこのパラメーターと同じエイリアスのいずれかのあるパイプライン オブジェクトのプロパティから値を受け取ることを示します。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-120">`True` indicates that the cmdlet parameter takes its value from a property of a pipeline object that has either the same name or the same alias as this parameter.</span></span> <span data-ttu-id="eb7ba-121">たとえば、次のコマンドレットがある、`Name`パラメーターと、パイプライン オブジェクトがあります、`Name`プロパティ、値の`Name`に割り当てられているプロパティ、`Name`コマンドレットのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-121">For example, if the cmdlet has a `Name` parameter and the pipeline object also has a `Name` property, the value of the `Name` property is assigned to the `Name` parameter of the cmdlet.</span></span> <span data-ttu-id="eb7ba-122">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-122">The default is `false`.</span></span>

<span data-ttu-id="eb7ba-123">`ValueFromRemainingArguments` ([System.Boolean](/dotnet/api/System.Boolean)) という名前のパラメーター (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-123">`ValueFromRemainingArguments` ([System.Boolean](/dotnet/api/System.Boolean)) Optional named parameter.</span></span> <span data-ttu-id="eb7ba-124">`True` コマンドレット パラメーターをコマンドレットに渡されるすべての残りの引数を受け入れることを示します。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-124">`True` indicates that the cmdlet parameter accepts all remaining arguments that are passed to the cmdlet.</span></span> <span data-ttu-id="eb7ba-125">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-125">The default is `false`.</span></span>

<span data-ttu-id="eb7ba-126">`HelpMessage` 名前付きパラメーターを省略可能です。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-126">`HelpMessage` Optional named parameter.</span></span> <span data-ttu-id="eb7ba-127">パラメーターの短い説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-127">Specifies a short description of the parameter.</span></span> <span data-ttu-id="eb7ba-128">Windows PowerShell では、コマンドレットが実行され、必須のパラメーターが指定されていないときに、このメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-128">Windows PowerShell displays this message when a cmdlet is run and a mandatory parameter is not specified.</span></span>

<span data-ttu-id="eb7ba-129">`HelpMessageBaseName` 名前付きパラメーターを省略可能です。リソース識別子が存在する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-129">`HelpMessageBaseName` Optional named parameter.Specifies the location where resource identifiers reside.</span></span> <span data-ttu-id="eb7ba-130">たとえば、このパラメーターは、ローカライズするヘルプ メッセージを含むリソース アセンブリを指定できます。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-130">For example, this parameter could specify a resource assembly that contains Help messages that you want to localize.</span></span>

<span data-ttu-id="eb7ba-131">`HelpMessageResourceId` 名前付きパラメーターを省略可能です。ヘルプ メッセージのリソース識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-131">`HelpMessageResourceId` Optional named parameter.Specifies the resource identifier for a Help message.</span></span>

## <a name="remarks"></a><span data-ttu-id="eb7ba-132">コメント</span><span class="sxs-lookup"><span data-stu-id="eb7ba-132">Remarks</span></span>

- <span data-ttu-id="eb7ba-133">この属性を宣言する方法の詳細については、次を参照してください。[コマンドレット パラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)します。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-133">For more information about how to declare this attribute, see [How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).</span></span>

- <span data-ttu-id="eb7ba-134">コマンドレットは、任意の数のパラメーターを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-134">A cmdlet can have any number of parameters.</span></span> <span data-ttu-id="eb7ba-135">ただし、ユーザー エクスペリエンスを向上させるには、パラメーターの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-135">However, for a better user experience, limit the number of parameters.</span></span>

- <span data-ttu-id="eb7ba-136">パブリックの非静的フィールドまたはプロパティでは、パラメーターを宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-136">Parameters must be declared on public non-static fields or properties.</span></span> <span data-ttu-id="eb7ba-137">プロパティでは、パラメーターを宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-137">Parameters should be declared on properties.</span></span> <span data-ttu-id="eb7ba-138">プロパティには、パブリック set アクセサーと場合、`ValueFromPipeline`または`ValueFromPipelineByPropertyName`キーワードを指定すると、プロパティは、public の get アクセサーをいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-138">The property must have a public set accessor, and if the `ValueFromPipeline` or `ValueFromPipelineByPropertyName` keyword is specified, the property must have a public get accessor.</span></span>

- <span data-ttu-id="eb7ba-139">位置指定パラメーターを指定する場合は、5 未満に設定するパラメーターの位置指定パラメーターの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-139">When you specify positional parameters,  limit the number of positional parameters in a parameter set to less than five.</span></span> <span data-ttu-id="eb7ba-140">また、位置指定パラメーターは、連続している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-140">And, positional parameters do not have to be contiguous.</span></span> <span data-ttu-id="eb7ba-141">5、100、および 250 の位置は、同じを位置 0、1、および 2 として機能します。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-141">Positions 5, 100, and 250 work the same as positions 0, 1, and 2.</span></span>

- <span data-ttu-id="eb7ba-142">ときに、`Position`キーワードが指定されていない、コマンドレット パラメーターは、名前で参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-142">When the `Position` keyword is not specified, the cmdlet parameter must be referenced by its name.</span></span>

- <span data-ttu-id="eb7ba-143">パラメーター セットを使用すると、次に注意してください。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-143">When you use parameter sets, note the following:</span></span>

    - <span data-ttu-id="eb7ba-144">各パラメーターのセットには、少なくとも 1 つの一意のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-144">Each parameter set must have at least one unique parameter.</span></span> <span data-ttu-id="eb7ba-145">適切なコマンドレットのデザインでは、この一意のパラメーターも必須にするか可能な場合を示します。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-145">Good cmdlet design indicates this unique parameter should also be mandatory if possible.</span></span> <span data-ttu-id="eb7ba-146">場合は、コマンドレットがパラメーターなしで動作するように設計、一意のパラメーターを必須にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-146">If your cmdlet is designed to be run without parameters, the unique parameter cannot be mandatory.</span></span>

    - <span data-ttu-id="eb7ba-147">パラメーター セットは同じ位置に 1 つ以上の位置指定パラメーターを含めることがない必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-147">No parameter set should contain more than one positional parameter with the same position.</span></span>

    - <span data-ttu-id="eb7ba-148">パラメーター セットで 1 つだけのパラメーターを宣言する必要があります`ValueFromPipeline = true`します。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-148">Only one parameter in a parameter set should declare `ValueFromPipeline = true`.</span></span> <span data-ttu-id="eb7ba-149">複数のパラメーターを定義できます`ValueFromPipelineByPropertyName = true`します。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-149">Multiple parameters can define `ValueFromPipelineByPropertyName = true`.</span></span>

    - <span data-ttu-id="eb7ba-150">複数のパラメーターを定義できます`ValueFromPipelineByPropertyName = true`します。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-150">Multiple parameters can define `ValueFromPipelineByPropertyName = true`.</span></span>

- <span data-ttu-id="eb7ba-151">パラメーター名に関するガイドラインの詳細については、次を参照してください。[コマンドレットのパラメーター名](standard-cmdlet-parameter-names-and-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-151">For more information about the guidelines for parameter names, see [Cmdlet Parameter Names](standard-cmdlet-parameter-names-and-types.md).</span></span>

- <span data-ttu-id="eb7ba-152">パラメーター属性が定義した、 [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)クラス。</span><span class="sxs-lookup"><span data-stu-id="eb7ba-152">The parameter attribute is defined by the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb7ba-153">参照</span><span class="sxs-lookup"><span data-stu-id="eb7ba-153">See Also</span></span>

[<span data-ttu-id="eb7ba-154">System.Management.Automation.Parameterattribute</span><span class="sxs-lookup"><span data-stu-id="eb7ba-154">System.Management.Automation.Parameterattribute</span></span>](/dotnet/api/System.Management.Automation.ParameterAttribute)

[<span data-ttu-id="eb7ba-155">コマンドレットのパラメーター名</span><span class="sxs-lookup"><span data-stu-id="eb7ba-155">Cmdlet Parameter Names</span></span>](standard-cmdlet-parameter-names-and-types.md)

[<span data-ttu-id="eb7ba-156">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="eb7ba-156">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
