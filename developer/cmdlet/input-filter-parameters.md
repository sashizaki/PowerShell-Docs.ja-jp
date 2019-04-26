---
title: 入力フィルター パラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e45929d1-bbb4-4dc6-892f-f9eacdb1c84c
caps.latest.revision: 8
ms.openlocfilehash: 553878c34e74129f9876cca25a5393cb0d53445a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067690"
---
# <a name="input-filter-parameters"></a><span data-ttu-id="38da3-102">入力フィルターのパラメーター</span><span class="sxs-lookup"><span data-stu-id="38da3-102">Input Filter Parameters</span></span>

<span data-ttu-id="38da3-103">コマンドレットを定義できます`Filter`、 `Include`、および`Exclude`パラメーターをコマンドレットに影響を与える入力オブジェクトのセットをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="38da3-103">A cmdlet can define `Filter`, `Include`, and `Exclude` parameters that filter the set of input objects that the cmdlet affects.</span></span>

<span data-ttu-id="38da3-104">通常、入力オブジェクトのセットがで指定された、 `InputObject`、 `Path`、または`Name`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="38da3-104">Typically, the set of input objects is specified by an `InputObject`, `Path`, or `Name` parameter.</span></span> <span data-ttu-id="38da3-105">たとえば、コマンドレットが持つことができます、`Path`をワイルドカード文字、および入力オブジェクトには、各パス ポイントを使用して複数のパスを受け取るパラメーター。</span><span class="sxs-lookup"><span data-stu-id="38da3-105">For example, a cmdlet can have a `Path` parameter that accepts multiple paths by using wildcard characters, and each path points to an input object.</span></span> <span data-ttu-id="38da3-106">、一緒に使用、 `Filter`、 `Include`、および`Exclude`パラメーターをさらには、コマンドレットの動作が呼び出されるたびにパスを修飾します。</span><span class="sxs-lookup"><span data-stu-id="38da3-106">Used together, the `Filter`, `Include`, and `Exclude` parameters further qualify the paths the cmdlet works on each time it is invoked.</span></span>

## <a name="include-and-exclude-parameters"></a><span data-ttu-id="38da3-107">パラメーターを含めたり除外したり</span><span class="sxs-lookup"><span data-stu-id="38da3-107">Include and Exclude Parameters</span></span>

<span data-ttu-id="38da3-108">`Include`と`Exclude`パラメーターが含まれるか、コマンドレットに渡された入力オブジェクトのセットから除外するオブジェクトを識別します。</span><span class="sxs-lookup"><span data-stu-id="38da3-108">The `Include` and `Exclude` parameters identify the objects that are included or excluded from the set of input objects passed to the cmdlet.</span></span> <span data-ttu-id="38da3-109">フィルターは、標準のワイルドカードの言語で表現できる場合は、これらのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="38da3-109">Use these parameters when the filter can be expressed in the standard wildcard language.</span></span> <span data-ttu-id="38da3-110">(ワイルドカード文字の詳細については、次を参照してください[コマンドレットのパラメーターにワイルドカードをサポートしている](./supporting-wildcard-characters-in-cmdlet-parameters.md)。)。`Include`パラメーターに名前を持つ包含フィルターに一致するすべてのオブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="38da3-110">(For more information about wildcard characters, see [Supporting Wildcards in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md).) The `Include` parameter includes all the objects whose names match the inclusion filter.</span></span> <span data-ttu-id="38da3-111">`Exclude`パラメーターに名前を持つフィルターに一致するすべてのオブジェクトが除外されます。</span><span class="sxs-lookup"><span data-stu-id="38da3-111">The `Exclude` parameter excludes all the objects whose names match the filter.</span></span>

## <a name="filter-parameter"></a><span data-ttu-id="38da3-112">パラメーターをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="38da3-112">Filter Parameter</span></span>

<span data-ttu-id="38da3-113">`Filter`パラメーターは、標準のワイルドカードの言語で表記されていないフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="38da3-113">The `Filter` parameter specifies a filter that is not expressed in the standard wildcard language.</span></span> <span data-ttu-id="38da3-114">たとえば、Active Directory サービス インターフェイス (ADSI) または SQL のフィルターがを介してコマンドレットに渡すことができます、`Filter`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="38da3-114">For example, Active Directory Service Interfaces (ADSI) or SQL filters might be passed to the cmdlet through its `Filter` parameter.</span></span> <span data-ttu-id="38da3-115">Windows PowerShell によって提供される、コマンドレットでは、これらのフィルターは、コマンドレットを使用してデータ ストアにアクセスする Windows PowerShell プロバイダーによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="38da3-115">In the cmdlets provided by Windows PowerShell, these filters are specified by the Windows PowerShell providers that use the cmdlet to access a data store.</span></span> <span data-ttu-id="38da3-116">通常、各プロバイダーは、独自のフィルターを定義します。</span><span class="sxs-lookup"><span data-stu-id="38da3-116">Each provider typically defines its own filter.</span></span>

## <a name="filtering-if-no-set-of-input-objects-is-specified"></a><span data-ttu-id="38da3-117">入力オブジェクトのセットが指定されていない場合にフィルター処理</span><span class="sxs-lookup"><span data-stu-id="38da3-117">Filtering If No Set of Input Objects Is Specified</span></span>

<span data-ttu-id="38da3-118">通常入力オブジェクトのセットが指定されていない場合これをすべてのオブジェクトに対してフィルター処理することを意味します。</span><span class="sxs-lookup"><span data-stu-id="38da3-118">If no set of input objects is specified, this typically means to filter against all objects.</span></span> <span data-ttu-id="38da3-119">詳細については、次を参照してください。[Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)します。</span><span class="sxs-lookup"><span data-stu-id="38da3-119">For more information, see[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process).</span></span>

## <a name="see-also"></a><span data-ttu-id="38da3-120">参照</span><span class="sxs-lookup"><span data-stu-id="38da3-120">See Also</span></span>

[<span data-ttu-id="38da3-121">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="38da3-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)