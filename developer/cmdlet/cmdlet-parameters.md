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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853848"
---
# <a name="cmdlet-parameters"></a><span data-ttu-id="016d5-102">コマンドレットのパラメーター</span><span class="sxs-lookup"><span data-stu-id="016d5-102">Cmdlet Parameters</span></span>

<span data-ttu-id="016d5-103">コマンドレットのパラメーターは、コマンドレットの入力を受け付けることを許可するメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="016d5-103">Cmdlet parameters provide the mechanism that allows a cmdlet to accept input.</span></span> <span data-ttu-id="016d5-104">パラメーターは、コマンドラインから直接、または、引数、パイプラインを介してコマンドレットに渡されたオブジェクトからの入力を受け付けることができます (とも呼ばれます*値*) これらのパラメーターをコマンドレットが受け取る入力を指定できますが、方法コマンドレットは、アクション、およびパイプラインにコマンドレットが返すデータを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="016d5-104">Parameters can accept input directly from the command line, or from objects passed to the cmdlet through the pipeline, The arguments (also known as *values*) of these parameters can specify the input that the cmdlet accepts, how the cmdlet should perform its actions, and the data that the cmdlet returns to the pipeline.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="016d5-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="016d5-105">In This Section</span></span>

<span data-ttu-id="016d5-106">[パラメーターとしてプロパティを宣言する](./declaring-properties-as-parameters.md)コマンドレットのパラメーターを宣言する前に理解する必要があります、基本的な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="016d5-106">[Declaring Properties as Parameters](./declaring-properties-as-parameters.md) Provides basic information you must understand before you declare the parameters of a cmdlet.</span></span>

<span data-ttu-id="016d5-107">[コマンドレットのパラメーターの型](./types-of-cmdlet-parameters.md)コマンドレットで宣言するパラメーターのさまざまな種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="016d5-107">[Types of Cmdlet Parameters](./types-of-cmdlet-parameters.md) Describes the different types of parameters that you can declare in cmdlets.</span></span>

<span data-ttu-id="016d5-108">[コマンドレットのパラメーター名と機能のガイドライン](./standard-cmdlet-parameter-names-and-types.md)で、名前のデータ型、および標準のパラメーターの機能をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="016d5-108">[Cmdlet Parameter Name and Functionality Guidelines](./standard-cmdlet-parameter-names-and-types.md) Discuses the names, recommended data type, and functionality of standard parameters.</span></span>

<span data-ttu-id="016d5-109">[パラメーター エイリアス](./parameter-aliases.md)パラメーターを定義できるエイリアスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="016d5-109">[Parameter Aliases](./parameter-aliases.md) Discusses the aliases that you can define for parameters.</span></span>

<span data-ttu-id="016d5-110">[一般的なパラメーター名](./common-parameter-names.md)このトピックでは、Windows PowerShell コマンドレットを追加しますパラメーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="016d5-110">[Common Parameter Names](./common-parameter-names.md) This topic describes the parameters that Windows PowerShell adds to cmdlets.</span></span>

<span data-ttu-id="016d5-111">[コマンドレットのパラメーター設定](./cmdlet-parameter-sets.md)パラメーター セットを使用するさまざまなシナリオのさまざまなアクションを実行できる 1 つのコマンドレットを記述する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="016d5-111">[Cmdlet Parameter Sets](./cmdlet-parameter-sets.md) Discusses how parameter sets enable you to write a single cmdlet that can perform different actions for different scenarios.</span></span>

<span data-ttu-id="016d5-112">[コマンドレットの動的パラメーター](./cmdlet-dynamic-parameters.md)は特別な条件下で、ユーザーに使用できるパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="016d5-112">[Cmdlet Dynamic Parameters](./cmdlet-dynamic-parameters.md) Discusses parameters that are available to the user under special conditions.</span></span>

<span data-ttu-id="016d5-113">[コマンドレットのパラメーターにワイルドカード文字をサポートしている](./supporting-wildcard-characters-in-cmdlet-parameters.md)リソースのグループに対して実行されるコマンドレットをデザインするときに、ワイルドカード文字のサポートを提供する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="016d5-113">[Supporting Wildcard Characters in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md) Describes how to provide support for wildcard characters when you design a cmdlet that will be run against a group of resources.</span></span>

<span data-ttu-id="016d5-114">[パラメーターの入力を検証する](./validating-parameter-input.md)Windows PowerShell コマンドレットのパラメーターに渡される引数を検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="016d5-114">[Validating Parameter Input](./validating-parameter-input.md) Describes how Windows PowerShell validates the arguments passed to cmdlet parameters.</span></span>

<span data-ttu-id="016d5-115">[入力フィルター パラメーター](./input-filter-parameters.md)について説明します、 `Filter`、 `Include`、および`Exclude`パラメーターをコマンドレットに影響を与える入力オブジェクトのセットをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="016d5-115">[Input Filter Parameters](./input-filter-parameters.md) Discusses the `Filter`, `Include`, and `Exclude` parameters that filter the set of input objects that the cmdlet affects.</span></span>

## <a name="related-sections"></a><span data-ttu-id="016d5-116">関連セクション</span><span class="sxs-lookup"><span data-stu-id="016d5-116">Related Sections</span></span>

[<span data-ttu-id="016d5-117">パラメーターの入力を検証する方法</span><span class="sxs-lookup"><span data-stu-id="016d5-117">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

## <a name="see-also"></a><span data-ttu-id="016d5-118">参照</span><span class="sxs-lookup"><span data-stu-id="016d5-118">See Also</span></span>

[<span data-ttu-id="016d5-119">パラメーター属性の宣言</span><span class="sxs-lookup"><span data-stu-id="016d5-119">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="016d5-120">Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="016d5-120">Windows PowerShell Cmdlets</span></span>](./cmdlet-overview.md)
