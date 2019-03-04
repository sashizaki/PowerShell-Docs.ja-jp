---
title: 数量パラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c0bd8a9-1749-4885-ab24-38c0a4d9f2cb
caps.latest.revision: 6
ms.openlocfilehash: 7a3efc60fcc8729d833f6de070016cfd08cc9b88
ms.sourcegitcommit: ce46e5098786e19d521b4bf948ff62d2b90bc53e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2019
ms.locfileid: "57251372"
---
# <a name="quantity-parameters"></a><span data-ttu-id="8d3ed-102">数量のパラメーター</span><span class="sxs-lookup"><span data-stu-id="8d3ed-102">Quantity Parameters</span></span>

<span data-ttu-id="8d3ed-103">次の表は、推奨される名前と数量のパラメーターの機能を示します。</span><span class="sxs-lookup"><span data-stu-id="8d3ed-103">The following table lists the recommended names and functionality for quantity parameters.</span></span>

|<span data-ttu-id="8d3ed-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8d3ed-104">Parameter</span></span>|<span data-ttu-id="8d3ed-105">機能</span><span class="sxs-lookup"><span data-stu-id="8d3ed-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="8d3ed-106">**すべての**</span><span class="sxs-lookup"><span data-stu-id="8d3ed-106">**All**</span></span><br><span data-ttu-id="8d3ed-107">データの種類:ブール型</span><span class="sxs-lookup"><span data-stu-id="8d3ed-107">Data type: Boolean</span></span>|<span data-ttu-id="8d3ed-108">このパラメーターを実装できるように`true`リソースの既定のサブセットではなくすべてのリソースが左右されることを示します。</span><span class="sxs-lookup"><span data-stu-id="8d3ed-108">Implement this parameter so that `true` indicates that all resources should be acted upon instead of a default subset of resources.</span></span> <span data-ttu-id="8d3ed-109">このパラメーターを実装できるように`false`リソースのサブセットを示します。</span><span class="sxs-lookup"><span data-stu-id="8d3ed-109">Implement this parameter so that `false` indicates a subset of the resources.</span></span>|
|<span data-ttu-id="8d3ed-110">**割り当て**</span><span class="sxs-lookup"><span data-stu-id="8d3ed-110">**Allocation**</span></span><br><span data-ttu-id="8d3ed-111">データの種類:Int32</span><span class="sxs-lookup"><span data-stu-id="8d3ed-111">Data type: Int32</span></span>|<span data-ttu-id="8d3ed-112">ユーザーが割り当てる項目の数を指定できるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="8d3ed-112">Implement this parameter so that the user can specify the number of items to allocate.</span></span>|
|<span data-ttu-id="8d3ed-113">**BlockCount**</span><span class="sxs-lookup"><span data-stu-id="8d3ed-113">**BlockCount**</span></span><br><span data-ttu-id="8d3ed-114">データの種類:Int64</span><span class="sxs-lookup"><span data-stu-id="8d3ed-114">Data type: Int64</span></span>|<span data-ttu-id="8d3ed-115">このパラメーターを実装するは、ユーザーは、ブロックの数を指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8d3ed-115">Implement this parameter so that the user can specify the block count.</span></span>|
|<span data-ttu-id="8d3ed-116">**カウント**</span><span class="sxs-lookup"><span data-stu-id="8d3ed-116">**Count**</span></span><br><span data-ttu-id="8d3ed-117">データの種類:Int64</span><span class="sxs-lookup"><span data-stu-id="8d3ed-117">Data type: Int64</span></span>|<span data-ttu-id="8d3ed-118">このパラメーターを実装するは、ユーザーが数を指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8d3ed-118">Implement this parameter so that the user can specify the count.</span></span>|
|<span data-ttu-id="8d3ed-119">**スコープ**</span><span class="sxs-lookup"><span data-stu-id="8d3ed-119">**Scope**</span></span><br><span data-ttu-id="8d3ed-120">データの種類:キーワード</span><span class="sxs-lookup"><span data-stu-id="8d3ed-120">Data type: Keyword</span></span>|<span data-ttu-id="8d3ed-121">ユーザーが操作するスコープを指定できるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="8d3ed-121">Implement this parameter so that the user can specify the scope to operate on.</span></span>|

## <a name="see-also"></a><span data-ttu-id="8d3ed-122">参照</span><span class="sxs-lookup"><span data-stu-id="8d3ed-122">See Also</span></span>

[<span data-ttu-id="8d3ed-123">コマンドレットのパラメーター</span><span class="sxs-lookup"><span data-stu-id="8d3ed-123">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="8d3ed-124">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="8d3ed-124">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="8d3ed-125">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="8d3ed-125">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
