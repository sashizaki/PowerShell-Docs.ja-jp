---
ms.date: 09/13/2016
ms.topic: reference
title: 数量のパラメーター
description: 数量のパラメーター
ms.openlocfilehash: 3f7c23eec34a709b1f2d59f611c93909b20f4124
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650299"
---
# <a name="quantity-parameters"></a><span data-ttu-id="183b1-103">数量のパラメーター</span><span class="sxs-lookup"><span data-stu-id="183b1-103">Quantity Parameters</span></span>

<span data-ttu-id="183b1-104">次の表に、quantity パラメーターの推奨される名前と機能を示します。</span><span class="sxs-lookup"><span data-stu-id="183b1-104">The following table lists the recommended names and functionality for quantity parameters.</span></span>

|<span data-ttu-id="183b1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="183b1-105">Parameter</span></span>|<span data-ttu-id="183b1-106">機能</span><span class="sxs-lookup"><span data-stu-id="183b1-106">Functionality</span></span>|
|---|---|
|<span data-ttu-id="183b1-107">**すべて**</span><span class="sxs-lookup"><span data-stu-id="183b1-107">**All**</span></span><br><span data-ttu-id="183b1-108">データ型: ブール値</span><span class="sxs-lookup"><span data-stu-id="183b1-108">Data type: Boolean</span></span>|<span data-ttu-id="183b1-109">このパラメーターは、 `true` リソースの既定のサブセットではなく、すべてのリソースを処理する必要があることを示すために実装します。</span><span class="sxs-lookup"><span data-stu-id="183b1-109">Implement this parameter so that `true` indicates that all resources should be acted upon instead of a default subset of resources.</span></span> <span data-ttu-id="183b1-110">リソースのサブセットを示すように、このパラメーターを実装 `false` します。</span><span class="sxs-lookup"><span data-stu-id="183b1-110">Implement this parameter so that `false` indicates a subset of the resources.</span></span>|
|<span data-ttu-id="183b1-111">**Allocation**</span><span class="sxs-lookup"><span data-stu-id="183b1-111">**Allocation**</span></span><br><span data-ttu-id="183b1-112">データ型: Int32</span><span class="sxs-lookup"><span data-stu-id="183b1-112">Data type: Int32</span></span>|<span data-ttu-id="183b1-113">割り当てられる項目の数をユーザーが指定できるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="183b1-113">Implement this parameter so that the user can specify the number of items to allocate.</span></span>|
|<span data-ttu-id="183b1-114">**ブロック数**</span><span class="sxs-lookup"><span data-stu-id="183b1-114">**BlockCount**</span></span><br><span data-ttu-id="183b1-115">データ型: Int64</span><span class="sxs-lookup"><span data-stu-id="183b1-115">Data type: Int64</span></span>|<span data-ttu-id="183b1-116">ユーザーがブロックカウントを指定できるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="183b1-116">Implement this parameter so that the user can specify the block count.</span></span>|
|<span data-ttu-id="183b1-117">**Count**</span><span class="sxs-lookup"><span data-stu-id="183b1-117">**Count**</span></span><br><span data-ttu-id="183b1-118">データ型: Int64</span><span class="sxs-lookup"><span data-stu-id="183b1-118">Data type: Int64</span></span>|<span data-ttu-id="183b1-119">ユーザーがカウントを指定できるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="183b1-119">Implement this parameter so that the user can specify the count.</span></span>|
|<span data-ttu-id="183b1-120">**スコープ**</span><span class="sxs-lookup"><span data-stu-id="183b1-120">**Scope**</span></span><br><span data-ttu-id="183b1-121">データ型: キーワード</span><span class="sxs-lookup"><span data-stu-id="183b1-121">Data type: Keyword</span></span>|<span data-ttu-id="183b1-122">操作するスコープをユーザーが指定できるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="183b1-122">Implement this parameter so that the user can specify the scope to operate on.</span></span>|

## <a name="see-also"></a><span data-ttu-id="183b1-123">参照</span><span class="sxs-lookup"><span data-stu-id="183b1-123">See Also</span></span>

[<span data-ttu-id="183b1-124">コマンドレットのパラメーター</span><span class="sxs-lookup"><span data-stu-id="183b1-124">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="183b1-125">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="183b1-125">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="183b1-126">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="183b1-126">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
