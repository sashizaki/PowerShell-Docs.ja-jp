---
title: コマンドレットのパラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- optional parameters [PowerShell SDK]
- aliases [PowerShell SDK]
- parameter sets [PowerShell SDK]
- parameters [PowerShell SDK]
- mandatory parameters [PowerShell SDK]
- positional parameters [PowerShell SDK]
- cmdlets [PowerShell SDK], parameters
ms.assetid: 3f1cca5f-5b95-4bce-94a6-a22db1aefd47
caps.latest.revision: 23
ms.openlocfilehash: 914a10907bcf980eed8d7e2f819c382fe6b341ad
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365931"
---
# <a name="cmdlet-parameters"></a><span data-ttu-id="77d8c-102">コマンドレットのパラメーター</span><span class="sxs-lookup"><span data-stu-id="77d8c-102">Cmdlet Parameters</span></span>

<span data-ttu-id="77d8c-103">コマンドレットのパラメーターは、コマンドレットが入力を受け入れることができるメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="77d8c-103">Cmdlet parameters provide the mechanism that allows a cmdlet to accept input.</span></span> <span data-ttu-id="77d8c-104">パラメーターでは、コマンドラインから直接入力を受け取ることも、パイプラインを介してコマンドレットに渡されたオブジェクトから入力を受け入れることもできます。これらのパラメーターの引数 (*値*とも呼ばれます) は、コマンドレットが受け入れる入力を指定できます。アクションと、このコマンドレットによってパイプラインに返されるデータ。</span><span class="sxs-lookup"><span data-stu-id="77d8c-104">Parameters can accept input directly from the command line, or from objects passed to the cmdlet through the pipeline, The arguments (also known as *values*) of these parameters can specify the input that the cmdlet accepts, how the cmdlet should perform its actions, and the data that the cmdlet returns to the pipeline.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="77d8c-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="77d8c-105">In This Section</span></span>

<span data-ttu-id="77d8c-106">[パラメーターとしてのプロパティの宣言](./declaring-properties-as-parameters.md)コマンドレットのパラメーターを宣言する前に理解しておく必要がある基本情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="77d8c-106">[Declaring Properties as Parameters](./declaring-properties-as-parameters.md) Provides basic information you must understand before you declare the parameters of a cmdlet.</span></span>

<span data-ttu-id="77d8c-107">[コマンドレットパラメーターの型](./types-of-cmdlet-parameters.md)コマンドレットで宣言できるさまざまな種類のパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="77d8c-107">[Types of Cmdlet Parameters](./types-of-cmdlet-parameters.md) Describes the different types of parameters that you can declare in cmdlets.</span></span>

<span data-ttu-id="77d8c-108">[コマンドレットのパラメーター名と機能のガイドライン](./standard-cmdlet-parameter-names-and-types.md)Discuses は、標準パラメーターの名前、推奨されるデータ型、および機能を入力します。</span><span class="sxs-lookup"><span data-stu-id="77d8c-108">[Cmdlet Parameter Name and Functionality Guidelines](./standard-cmdlet-parameter-names-and-types.md) Discuses the names, recommended data type, and functionality of standard parameters.</span></span>

<span data-ttu-id="77d8c-109">[パラメーターの別名](./parameter-aliases.md)パラメーターに対して定義できるエイリアスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="77d8c-109">[Parameter Aliases](./parameter-aliases.md) Discusses the aliases that you can define for parameters.</span></span>

<span data-ttu-id="77d8c-110">[共通パラメーター名](./common-parameter-names.md)このトピックでは、Windows PowerShell によってコマンドレットに追加されるパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="77d8c-110">[Common Parameter Names](./common-parameter-names.md) This topic describes the parameters that Windows PowerShell adds to cmdlets.</span></span>

<span data-ttu-id="77d8c-111">[コマンドレットのパラメーターセット](./cmdlet-parameter-sets.md)パラメーターセットを使用して、さまざまなシナリオでさまざまなアクションを実行できる単一のコマンドレットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="77d8c-111">[Cmdlet Parameter Sets](./cmdlet-parameter-sets.md) Discusses how parameter sets enable you to write a single cmdlet that can perform different actions for different scenarios.</span></span>

<span data-ttu-id="77d8c-112">[コマンドレット動的パラメーター](./cmdlet-dynamic-parameters.md)特別な条件下でユーザーが使用できるパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="77d8c-112">[Cmdlet Dynamic Parameters](./cmdlet-dynamic-parameters.md) Discusses parameters that are available to the user under special conditions.</span></span>

<span data-ttu-id="77d8c-113">[コマンドレットパラメーターでのワイルドカード文字のサポート](./supporting-wildcard-characters-in-cmdlet-parameters.md)リソースグループに対して実行されるコマンドレットを設計するときに、ワイルドカード文字のサポートを提供する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="77d8c-113">[Supporting Wildcard Characters in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md) Describes how to provide support for wildcard characters when you design a cmdlet that will be run against a group of resources.</span></span>

<span data-ttu-id="77d8c-114">[パラメーター入力の検証](./validating-parameter-input.md)コマンドレットパラメーターに渡された引数を Windows PowerShell が検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="77d8c-114">[Validating Parameter Input](./validating-parameter-input.md) Describes how Windows PowerShell validates the arguments passed to cmdlet parameters.</span></span>

<span data-ttu-id="77d8c-115">[入力フィルターパラメーター](./input-filter-parameters.md)コマンドレットによって影響を与える入力オブジェクトのセットをフィルター処理する、`Filter`、@no__t 2、および `Exclude` のパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="77d8c-115">[Input Filter Parameters](./input-filter-parameters.md) Discusses the `Filter`, `Include`, and `Exclude` parameters that filter the set of input objects that the cmdlet affects.</span></span>

## <a name="related-sections"></a><span data-ttu-id="77d8c-116">関連セクション</span><span class="sxs-lookup"><span data-stu-id="77d8c-116">Related Sections</span></span>

[<span data-ttu-id="77d8c-117">パラメーター入力を検証する方法</span><span class="sxs-lookup"><span data-stu-id="77d8c-117">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

## <a name="see-also"></a><span data-ttu-id="77d8c-118">参照</span><span class="sxs-lookup"><span data-stu-id="77d8c-118">See Also</span></span>

[<span data-ttu-id="77d8c-119">パラメーター属性の宣言</span><span class="sxs-lookup"><span data-stu-id="77d8c-119">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="77d8c-120">Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="77d8c-120">Windows PowerShell Cmdlets</span></span>](./cmdlet-overview.md)
