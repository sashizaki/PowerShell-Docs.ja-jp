---
title: Quantity パラメーター |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7ff6562380bb6336b08879b31d8d9fed47bfb6a7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781819"
---
# <a name="quantity-parameters"></a><span data-ttu-id="212fa-102">数量のパラメーター</span><span class="sxs-lookup"><span data-stu-id="212fa-102">Quantity Parameters</span></span>

<span data-ttu-id="212fa-103">次の表に、quantity パラメーターの推奨される名前と機能を示します。</span><span class="sxs-lookup"><span data-stu-id="212fa-103">The following table lists the recommended names and functionality for quantity parameters.</span></span>

|<span data-ttu-id="212fa-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="212fa-104">Parameter</span></span>|<span data-ttu-id="212fa-105">機能</span><span class="sxs-lookup"><span data-stu-id="212fa-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="212fa-106">**すべて**</span><span class="sxs-lookup"><span data-stu-id="212fa-106">**All**</span></span><br><span data-ttu-id="212fa-107">データ型: ブール値</span><span class="sxs-lookup"><span data-stu-id="212fa-107">Data type: Boolean</span></span>|<span data-ttu-id="212fa-108">このパラメーターは、 `true` リソースの既定のサブセットではなく、すべてのリソースを処理する必要があることを示すために実装します。</span><span class="sxs-lookup"><span data-stu-id="212fa-108">Implement this parameter so that `true` indicates that all resources should be acted upon instead of a default subset of resources.</span></span> <span data-ttu-id="212fa-109">リソースのサブセットを示すように、このパラメーターを実装 `false` します。</span><span class="sxs-lookup"><span data-stu-id="212fa-109">Implement this parameter so that `false` indicates a subset of the resources.</span></span>|
|<span data-ttu-id="212fa-110">**Allocation**</span><span class="sxs-lookup"><span data-stu-id="212fa-110">**Allocation**</span></span><br><span data-ttu-id="212fa-111">データ型: Int32</span><span class="sxs-lookup"><span data-stu-id="212fa-111">Data type: Int32</span></span>|<span data-ttu-id="212fa-112">割り当てられる項目の数をユーザーが指定できるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="212fa-112">Implement this parameter so that the user can specify the number of items to allocate.</span></span>|
|<span data-ttu-id="212fa-113">**ブロック数**</span><span class="sxs-lookup"><span data-stu-id="212fa-113">**BlockCount**</span></span><br><span data-ttu-id="212fa-114">データ型: Int64</span><span class="sxs-lookup"><span data-stu-id="212fa-114">Data type: Int64</span></span>|<span data-ttu-id="212fa-115">ユーザーがブロックカウントを指定できるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="212fa-115">Implement this parameter so that the user can specify the block count.</span></span>|
|<span data-ttu-id="212fa-116">**Count**</span><span class="sxs-lookup"><span data-stu-id="212fa-116">**Count**</span></span><br><span data-ttu-id="212fa-117">データ型: Int64</span><span class="sxs-lookup"><span data-stu-id="212fa-117">Data type: Int64</span></span>|<span data-ttu-id="212fa-118">ユーザーがカウントを指定できるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="212fa-118">Implement this parameter so that the user can specify the count.</span></span>|
|<span data-ttu-id="212fa-119">**スコープ**</span><span class="sxs-lookup"><span data-stu-id="212fa-119">**Scope**</span></span><br><span data-ttu-id="212fa-120">データ型: キーワード</span><span class="sxs-lookup"><span data-stu-id="212fa-120">Data type: Keyword</span></span>|<span data-ttu-id="212fa-121">操作するスコープをユーザーが指定できるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="212fa-121">Implement this parameter so that the user can specify the scope to operate on.</span></span>|

## <a name="see-also"></a><span data-ttu-id="212fa-122">参照</span><span class="sxs-lookup"><span data-stu-id="212fa-122">See Also</span></span>

[<span data-ttu-id="212fa-123">コマンドレットのパラメーター</span><span class="sxs-lookup"><span data-stu-id="212fa-123">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="212fa-124">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="212fa-124">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="212fa-125">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="212fa-125">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
