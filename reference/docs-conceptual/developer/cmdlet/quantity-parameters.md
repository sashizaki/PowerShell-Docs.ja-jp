---
title: Quantity パラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c0bd8a9-1749-4885-ab24-38c0a4d9f2cb
caps.latest.revision: 6
ms.openlocfilehash: 7a3efc60fcc8729d833f6de070016cfd08cc9b88
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369561"
---
# <a name="quantity-parameters"></a><span data-ttu-id="92dce-102">数量のパラメーター</span><span class="sxs-lookup"><span data-stu-id="92dce-102">Quantity Parameters</span></span>

<span data-ttu-id="92dce-103">次の表に、quantity パラメーターの推奨される名前と機能を示します。</span><span class="sxs-lookup"><span data-stu-id="92dce-103">The following table lists the recommended names and functionality for quantity parameters.</span></span>

|<span data-ttu-id="92dce-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="92dce-104">Parameter</span></span>|<span data-ttu-id="92dce-105">機能</span><span class="sxs-lookup"><span data-stu-id="92dce-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="92dce-106">**All**</span><span class="sxs-lookup"><span data-stu-id="92dce-106">**All**</span></span><br><span data-ttu-id="92dce-107">データ型: ブール値</span><span class="sxs-lookup"><span data-stu-id="92dce-107">Data type: Boolean</span></span>|<span data-ttu-id="92dce-108">このパラメーターは、リソースの既定のサブセットではなく、すべてのリソースを処理する必要があることを `true` に示すために実装します。</span><span class="sxs-lookup"><span data-stu-id="92dce-108">Implement this parameter so that `true` indicates that all resources should be acted upon instead of a default subset of resources.</span></span> <span data-ttu-id="92dce-109">`false` がリソースのサブセットを示すように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="92dce-109">Implement this parameter so that `false` indicates a subset of the resources.</span></span>|
|<span data-ttu-id="92dce-110">**Allocation**</span><span class="sxs-lookup"><span data-stu-id="92dce-110">**Allocation**</span></span><br><span data-ttu-id="92dce-111">データ型: Int32</span><span class="sxs-lookup"><span data-stu-id="92dce-111">Data type: Int32</span></span>|<span data-ttu-id="92dce-112">割り当てられる項目の数をユーザーが指定できるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="92dce-112">Implement this parameter so that the user can specify the number of items to allocate.</span></span>|
|<span data-ttu-id="92dce-113">**ブロック数**</span><span class="sxs-lookup"><span data-stu-id="92dce-113">**BlockCount**</span></span><br><span data-ttu-id="92dce-114">データ型: Int64</span><span class="sxs-lookup"><span data-stu-id="92dce-114">Data type: Int64</span></span>|<span data-ttu-id="92dce-115">ユーザーがブロックカウントを指定できるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="92dce-115">Implement this parameter so that the user can specify the block count.</span></span>|
|<span data-ttu-id="92dce-116">**Count**</span><span class="sxs-lookup"><span data-stu-id="92dce-116">**Count**</span></span><br><span data-ttu-id="92dce-117">データ型: Int64</span><span class="sxs-lookup"><span data-stu-id="92dce-117">Data type: Int64</span></span>|<span data-ttu-id="92dce-118">ユーザーがカウントを指定できるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="92dce-118">Implement this parameter so that the user can specify the count.</span></span>|
|<span data-ttu-id="92dce-119">**Scope**</span><span class="sxs-lookup"><span data-stu-id="92dce-119">**Scope**</span></span><br><span data-ttu-id="92dce-120">データ型: キーワード</span><span class="sxs-lookup"><span data-stu-id="92dce-120">Data type: Keyword</span></span>|<span data-ttu-id="92dce-121">操作するスコープをユーザーが指定できるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="92dce-121">Implement this parameter so that the user can specify the scope to operate on.</span></span>|

## <a name="see-also"></a><span data-ttu-id="92dce-122">参照</span><span class="sxs-lookup"><span data-stu-id="92dce-122">See Also</span></span>

[<span data-ttu-id="92dce-123">コマンドレットのパラメーター</span><span class="sxs-lookup"><span data-stu-id="92dce-123">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="92dce-124">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="92dce-124">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="92dce-125">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="92dce-125">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
