---
title: ビュー (形式) の controls 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bd82666-447f-40fe-bd87-c8b182522f4f
caps.latest.revision: 14
ms.openlocfilehash: 477b8b54c8edd2fa0e6939041d04322d861197c9
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066803"
---
# <a name="controls-element-for-view-format"></a><span data-ttu-id="844d7-102">View の Controls 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="844d7-102">Controls Element for View (Format)</span></span>

<span data-ttu-id="844d7-103">特定のビューで使用できるビュー コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="844d7-103">Defines the view controls that can be used by a specific view.</span></span>

<span data-ttu-id="844d7-104">ビュー (形式) の構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) の Controls 要素</span><span class="sxs-lookup"><span data-stu-id="844d7-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="844d7-105">構文</span><span class="sxs-lookup"><span data-stu-id="844d7-105">Syntax</span></span>

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="844d7-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="844d7-106">Attributes and Elements</span></span>

<span data-ttu-id="844d7-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`Controls`要素。</span><span class="sxs-lookup"><span data-stu-id="844d7-107">The following sections describe the attributes, child elements, and parent elements of the `Controls` element.</span></span> <span data-ttu-id="844d7-108">この要素は、少なくとも 1 つの子要素をいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="844d7-108">This element must have at least one child element.</span></span> <span data-ttu-id="844d7-109">子要素の最大数がないもは順序が重要です。</span><span class="sxs-lookup"><span data-stu-id="844d7-109">There is no maximum number of child elements, nor is their order significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="844d7-110">属性</span><span class="sxs-lookup"><span data-stu-id="844d7-110">Attributes</span></span>

<span data-ttu-id="844d7-111">なし。</span><span class="sxs-lookup"><span data-stu-id="844d7-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="844d7-112">子要素</span><span class="sxs-lookup"><span data-stu-id="844d7-112">Child Elements</span></span>

|<span data-ttu-id="844d7-113">要素</span><span class="sxs-lookup"><span data-stu-id="844d7-113">Element</span></span>|<span data-ttu-id="844d7-114">説明</span><span class="sxs-lookup"><span data-stu-id="844d7-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="844d7-115">コントロールが表示されます (形式) のコントロール要素</span><span class="sxs-lookup"><span data-stu-id="844d7-115">Control Element for Controls for View (Format)</span></span>](./control-element-for-controls-for-view-format.md)|<span data-ttu-id="844d7-116">ビューで使用できるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="844d7-116">Defines a control that can be used by the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="844d7-117">親要素</span><span class="sxs-lookup"><span data-stu-id="844d7-117">Parent Elements</span></span>

|<span data-ttu-id="844d7-118">要素</span><span class="sxs-lookup"><span data-stu-id="844d7-118">Element</span></span>|<span data-ttu-id="844d7-119">説明</span><span class="sxs-lookup"><span data-stu-id="844d7-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="844d7-120">ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="844d7-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="844d7-121">1 つまたは複数の .NET オブジェクトのメンバーを表示するために使用するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="844d7-121">Defines a view that is used to display the members of one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="844d7-122">コメント</span><span class="sxs-lookup"><span data-stu-id="844d7-122">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="844d7-123">参照</span><span class="sxs-lookup"><span data-stu-id="844d7-123">See Also</span></span>

[<span data-ttu-id="844d7-124">コントロール要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="844d7-124">Control Element (Format)</span></span>](./control-element-for-controls-for-view-format.md)

[<span data-ttu-id="844d7-125">ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="844d7-125">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="844d7-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="844d7-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
