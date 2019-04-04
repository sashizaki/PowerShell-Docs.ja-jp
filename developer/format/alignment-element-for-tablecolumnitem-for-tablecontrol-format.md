---
title: TableColumnItem TableControl (形式) の要素の配置 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b07a53df-64f1-49b0-8cea-c993b3f1f76b
caps.latest.revision: 10
ms.openlocfilehash: 1bc936b94ee6fd6239e9e3c4afcdb8f14fbe36eb
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858208"
---
# <a name="alignment-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="461cb-102">TableControl の TableColumnItem の Alignment 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="461cb-102">Alignment Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="461cb-103">行の列のデータを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="461cb-103">Defines how the data in a column of the row is displayed.</span></span>

<span data-ttu-id="461cb-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素 (形式) TableRowEntry 要素 (形式) TableColumnItems 要素 (形式) TableColumnItem 要素 (形式)TableColumnItem (形式) の要素を配置</span><span class="sxs-lookup"><span data-stu-id="461cb-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) Alignment Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="461cb-105">構文</span><span class="sxs-lookup"><span data-stu-id="461cb-105">Syntax</span></span>

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="461cb-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="461cb-106">Attributes and Elements</span></span>

<span data-ttu-id="461cb-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`Alignment`要素。</span><span class="sxs-lookup"><span data-stu-id="461cb-107">The following sections describe the attributes, child elements, and parent element of the `Alignment` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="461cb-108">属性</span><span class="sxs-lookup"><span data-stu-id="461cb-108">Attributes</span></span>

<span data-ttu-id="461cb-109">なし。</span><span class="sxs-lookup"><span data-stu-id="461cb-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="461cb-110">子要素</span><span class="sxs-lookup"><span data-stu-id="461cb-110">Child Elements</span></span>

<span data-ttu-id="461cb-111">なし。</span><span class="sxs-lookup"><span data-stu-id="461cb-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="461cb-112">親要素</span><span class="sxs-lookup"><span data-stu-id="461cb-112">Parent Elements</span></span>

|<span data-ttu-id="461cb-113">要素</span><span class="sxs-lookup"><span data-stu-id="461cb-113">Element</span></span>|<span data-ttu-id="461cb-114">説明</span><span class="sxs-lookup"><span data-stu-id="461cb-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="461cb-115">TableColumnItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="461cb-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="461cb-116">ラベル、幅、およびテーブルの列のデータのアラインメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="461cb-116">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="461cb-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="461cb-117">Text Value</span></span>

<span data-ttu-id="461cb-118">次の値のいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="461cb-118">Specify one of the following values.</span></span> <span data-ttu-id="461cb-119">(これらの値小文字は区別されません) です。</span><span class="sxs-lookup"><span data-stu-id="461cb-119">(These values are not case-sensitive.)</span></span>

<span data-ttu-id="461cb-120">左シフト、左側の列にデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="461cb-120">Left Shifts the data displayed in the column to the left.</span></span> <span data-ttu-id="461cb-121">(これは既定のこの要素が指定されていない場合) です。</span><span class="sxs-lookup"><span data-stu-id="461cb-121">(This is the default if this element is not specified.)</span></span>

<span data-ttu-id="461cb-122">右シフトの右側の列に表示されるデータ。</span><span class="sxs-lookup"><span data-stu-id="461cb-122">Right Shifts the data displayed in the column to the right.</span></span>

<span data-ttu-id="461cb-123">中央揃えの列に表示されるデータ。</span><span class="sxs-lookup"><span data-stu-id="461cb-123">Center Centers the data displayed in the column.</span></span>

## <a name="remarks"></a><span data-ttu-id="461cb-124">コメント</span><span class="sxs-lookup"><span data-stu-id="461cb-124">Remarks</span></span>

<span data-ttu-id="461cb-125">テーブル ビューのコンポーネントに関する詳細については、[テーブル ビュー](./creating-a-table-view.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="461cb-125">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="461cb-126">参照</span><span class="sxs-lookup"><span data-stu-id="461cb-126">See Also</span></span>

[<span data-ttu-id="461cb-127">テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="461cb-127">Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="461cb-128">TableColumnItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="461cb-128">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)
