---
title: 入力フィルターパラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e45929d1-bbb4-4dc6-892f-f9eacdb1c84c
caps.latest.revision: 8
ms.openlocfilehash: 7a1582031d27f78bad069f5539408312ccabb3f2
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83563870"
---
# <a name="input-filter-parameters"></a><span data-ttu-id="082ee-102">入力フィルターのパラメーター</span><span class="sxs-lookup"><span data-stu-id="082ee-102">Input Filter Parameters</span></span>

<span data-ttu-id="082ee-103">コマンドレットでは `Filter` 、 `Include` `Exclude` コマンドレットが影響する入力オブジェクトのセットをフィルター処理する、、およびパラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="082ee-103">A cmdlet can define `Filter`, `Include`, and `Exclude` parameters that filter the set of input objects that the cmdlet affects.</span></span>

<span data-ttu-id="082ee-104">通常、入力オブジェクトのセットは `InputObject` 、、 `Path` 、またはパラメーターによって指定され `Name` ます。</span><span class="sxs-lookup"><span data-stu-id="082ee-104">Typically, the set of input objects is specified by an `InputObject`, `Path`, or `Name` parameter.</span></span> <span data-ttu-id="082ee-105">たとえば、コマンドレットは、ワイルドカード文字を使用して複数のパスを受け取るパラメーターを持つことができ、 `Path` 各パスは入力オブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="082ee-105">For example, a cmdlet can have a `Path` parameter that accepts multiple paths by using wildcard characters, and each path points to an input object.</span></span> <span data-ttu-id="082ee-106">、、およびの `Filter` `Include` 各パラメーターは、コマンドレットが呼び出されるたび `Exclude` に機能するパスをさらに修飾します。</span><span class="sxs-lookup"><span data-stu-id="082ee-106">Used together, the `Filter`, `Include`, and `Exclude` parameters further qualify the paths the cmdlet works on each time it is invoked.</span></span>

## <a name="include-and-exclude-parameters"></a><span data-ttu-id="082ee-107">Include パラメーターと Exclude パラメーター</span><span class="sxs-lookup"><span data-stu-id="082ee-107">Include and Exclude Parameters</span></span>

<span data-ttu-id="082ee-108">`Include`パラメーターと `Exclude` パラメーターは、コマンドレットに渡された入力オブジェクトのセットに含まれる、または除外されるオブジェクトを識別します。</span><span class="sxs-lookup"><span data-stu-id="082ee-108">The `Include` and `Exclude` parameters identify the objects that are included or excluded from the set of input objects passed to the cmdlet.</span></span> <span data-ttu-id="082ee-109">フィルターを標準のワイルドカード言語で表現できる場合は、これらのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="082ee-109">Use these parameters when the filter can be expressed in the standard wildcard language.</span></span> <span data-ttu-id="082ee-110">(ワイルドカード文字の詳細については、「[コマンドレットパラメーターでのワイルドカードのサポート](./supporting-wildcard-characters-in-cmdlet-parameters.md)」を参照してください)。パラメーターには、 `Include` 包含フィルターに一致する名前を持つすべてのオブジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="082ee-110">(For more information about wildcard characters, see [Supporting Wildcards in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md).) The `Include` parameter includes all the objects whose names match the inclusion filter.</span></span> <span data-ttu-id="082ee-111">パラメーターには、 `Exclude` フィルターに一致する名前を持つすべてのオブジェクトが除外されます。</span><span class="sxs-lookup"><span data-stu-id="082ee-111">The `Exclude` parameter excludes all the objects whose names match the filter.</span></span>

## <a name="filter-parameter"></a><span data-ttu-id="082ee-112">フィルターパラメーター</span><span class="sxs-lookup"><span data-stu-id="082ee-112">Filter Parameter</span></span>

<span data-ttu-id="082ee-113">パラメーターは、 `Filter` 標準のワイルドカード言語で表されないフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="082ee-113">The `Filter` parameter specifies a filter that is not expressed in the standard wildcard language.</span></span> <span data-ttu-id="082ee-114">たとえば、パラメーターを使用して、Active Directory サービスインターフェイス (ADSI) または SQL フィルターをコマンドレットに渡すことができ `Filter` ます。</span><span class="sxs-lookup"><span data-stu-id="082ee-114">For example, Active Directory Service Interfaces (ADSI) or SQL filters might be passed to the cmdlet through its `Filter` parameter.</span></span> <span data-ttu-id="082ee-115">Windows PowerShell によって提供されるコマンドレットでは、これらのフィルターは、コマンドレットを使用してデータストアにアクセスする Windows PowerShell プロバイダーによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="082ee-115">In the cmdlets provided by Windows PowerShell, these filters are specified by the Windows PowerShell providers that use the cmdlet to access a data store.</span></span> <span data-ttu-id="082ee-116">各プロバイダーは、通常、独自のフィルターを定義します。</span><span class="sxs-lookup"><span data-stu-id="082ee-116">Each provider typically defines its own filter.</span></span>

## <a name="filtering-if-no-set-of-input-objects-is-specified"></a><span data-ttu-id="082ee-117">入力オブジェクトのセットが指定されていない場合のフィルター処理</span><span class="sxs-lookup"><span data-stu-id="082ee-117">Filtering If No Set of Input Objects Is Specified</span></span>

<span data-ttu-id="082ee-118">入力オブジェクトのセットが指定されていない場合、これは通常、すべてのオブジェクトに対してフィルター処理を行うことを意味します。</span><span class="sxs-lookup"><span data-stu-id="082ee-118">If no set of input objects is specified, this typically means to filter against all objects.</span></span> <span data-ttu-id="082ee-119">詳細については、「[Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="082ee-119">For more information, see[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process).</span></span>

## <a name="see-also"></a><span data-ttu-id="082ee-120">参照</span><span class="sxs-lookup"><span data-stu-id="082ee-120">See Also</span></span>

[<span data-ttu-id="082ee-121">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="082ee-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
