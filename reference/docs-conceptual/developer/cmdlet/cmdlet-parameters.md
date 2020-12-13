---
ms.date: 09/13/2016
ms.topic: reference
title: コマンドレットのパラメーター
description: コマンドレットのパラメーター
ms.openlocfilehash: 1ab495cb674f6b2cd769c3f64d899aec67704216
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668271"
---
# <a name="cmdlet-parameters"></a><span data-ttu-id="7ba06-103">コマンドレットのパラメーター</span><span class="sxs-lookup"><span data-stu-id="7ba06-103">Cmdlet Parameters</span></span>

<span data-ttu-id="7ba06-104">コマンドレットのパラメーターは、コマンドレットが入力を受け入れることができるメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="7ba06-104">Cmdlet parameters provide the mechanism that allows a cmdlet to accept input.</span></span> <span data-ttu-id="7ba06-105">パラメーターでは、コマンドラインから直接入力を受け取ることも、パイプラインを介してコマンドレットに渡されたオブジェクトから入力を受け入れることもできます。また、これらのパラメーターの引数 ( *値* とも呼ばれます) は、コマンドレットが受け入れる入力、コマンドレットがアクションを実行する方法、コマンドレットがパイプラインに返すデータを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7ba06-105">Parameters can accept input directly from the command line, or from objects passed to the cmdlet through the pipeline, The arguments (also known as *values*) of these parameters can specify the input that the cmdlet accepts, how the cmdlet should perform its actions, and the data that the cmdlet returns to the pipeline.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7ba06-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7ba06-106">In This Section</span></span>

<span data-ttu-id="7ba06-107">[パラメーターとしてのプロパティの宣言](./declaring-properties-as-parameters.md) コマンドレットのパラメーターを宣言する前に理解しておく必要がある基本情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ba06-107">[Declaring Properties as Parameters](./declaring-properties-as-parameters.md) Provides basic information you must understand before you declare the parameters of a cmdlet.</span></span>

<span data-ttu-id="7ba06-108">[コマンドレットパラメーターの型](./types-of-cmdlet-parameters.md) コマンドレットで宣言できるさまざまな種類のパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7ba06-108">[Types of Cmdlet Parameters](./types-of-cmdlet-parameters.md) Describes the different types of parameters that you can declare in cmdlets.</span></span>

<span data-ttu-id="7ba06-109">[コマンドレットのパラメーター名と機能のガイドライン](./standard-cmdlet-parameter-names-and-types.md) 標準パラメーターの名前、推奨されるデータ型、および機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ba06-109">[Cmdlet Parameter Name and Functionality Guidelines](./standard-cmdlet-parameter-names-and-types.md) Discusses the names, recommended data type, and functionality of standard parameters.</span></span>

<span data-ttu-id="7ba06-110">[パラメーターの別名](./parameter-aliases.md) パラメーターに対して定義できるエイリアスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7ba06-110">[Parameter Aliases](./parameter-aliases.md) Discusses the aliases that you can define for parameters.</span></span>

<span data-ttu-id="7ba06-111">[共通パラメーター名](./common-parameter-names.md) このトピックでは、Windows PowerShell によってコマンドレットに追加されるパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7ba06-111">[Common Parameter Names](./common-parameter-names.md) This topic describes the parameters that Windows PowerShell adds to cmdlets.</span></span>

<span data-ttu-id="7ba06-112">[コマンドレットのパラメーターセット](./cmdlet-parameter-sets.md) パラメーターセットを使用して、さまざまなシナリオでさまざまなアクションを実行できる単一のコマンドレットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ba06-112">[Cmdlet Parameter Sets](./cmdlet-parameter-sets.md) Discusses how parameter sets enable you to write a single cmdlet that can perform different actions for different scenarios.</span></span>

<span data-ttu-id="7ba06-113">[コマンドレット動的パラメーター](./cmdlet-dynamic-parameters.md) 特別な条件下でユーザーが使用できるパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7ba06-113">[Cmdlet Dynamic Parameters](./cmdlet-dynamic-parameters.md) Discusses parameters that are available to the user under special conditions.</span></span>

<span data-ttu-id="7ba06-114">[コマンドレットパラメーターでのワイルドカード文字のサポート](./supporting-wildcard-characters-in-cmdlet-parameters.md) リソースグループに対して実行されるコマンドレットを設計するときに、ワイルドカード文字のサポートを提供する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ba06-114">[Supporting Wildcard Characters in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md) Describes how to provide support for wildcard characters when you design a cmdlet that will be run against a group of resources.</span></span>

<span data-ttu-id="7ba06-115">[パラメーター入力の検証](./validating-parameter-input.md) コマンドレットパラメーターに渡された引数を Windows PowerShell が検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ba06-115">[Validating Parameter Input](./validating-parameter-input.md) Describes how Windows PowerShell validates the arguments passed to cmdlet parameters.</span></span>

<span data-ttu-id="7ba06-116">[入力フィルターパラメーター](./input-filter-parameters.md) コマンドレットによって `Filter` `Include` 影響を `Exclude` 与える入力オブジェクトのセットをフィルター処理する、、、およびの各パラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7ba06-116">[Input Filter Parameters](./input-filter-parameters.md) Discusses the `Filter`, `Include`, and `Exclude` parameters that filter the set of input objects that the cmdlet affects.</span></span>

## <a name="related-sections"></a><span data-ttu-id="7ba06-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ba06-117">Related Sections</span></span>

[<span data-ttu-id="7ba06-118">パラメーター入力を検証する方法</span><span class="sxs-lookup"><span data-stu-id="7ba06-118">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

## <a name="see-also"></a><span data-ttu-id="7ba06-119">参照</span><span class="sxs-lookup"><span data-stu-id="7ba06-119">See Also</span></span>

[<span data-ttu-id="7ba06-120">パラメーター属性の宣言</span><span class="sxs-lookup"><span data-stu-id="7ba06-120">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="7ba06-121">Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="7ba06-121">Windows PowerShell Cmdlets</span></span>](./cmdlet-overview.md)
