---
ms.date: 09/13/2016
ms.topic: reference
title: TableControl の TableColumnItem の Alignment 要素 (書式)
description: TableControl の TableColumnItem の Alignment 要素 (書式)
ms.openlocfilehash: d2bb81ff894cad44e16212891faffd22ee627383
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646120"
---
# <a name="alignment-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="cb323-103">TableControl の TableColumnItem の Alignment 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cb323-103">Alignment Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="cb323-104">行の列のデータをどのように表示するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="cb323-104">Defines how the data in a column of the row is displayed.</span></span>

<span data-ttu-id="cb323-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) TableColumnItems Element (format) TableColumnItem Element (format) Element (format) Element (format) Alignment 要素 TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="cb323-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) Alignment Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cb323-106">構文</span><span class="sxs-lookup"><span data-stu-id="cb323-106">Syntax</span></span>

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cb323-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cb323-107">Attributes and Elements</span></span>

<span data-ttu-id="cb323-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `Alignment` ます。</span><span class="sxs-lookup"><span data-stu-id="cb323-108">The following sections describe the attributes, child elements, and parent element of the `Alignment` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cb323-109">属性</span><span class="sxs-lookup"><span data-stu-id="cb323-109">Attributes</span></span>

<span data-ttu-id="cb323-110">なし。</span><span class="sxs-lookup"><span data-stu-id="cb323-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cb323-111">子要素</span><span class="sxs-lookup"><span data-stu-id="cb323-111">Child Elements</span></span>

<span data-ttu-id="cb323-112">なし。</span><span class="sxs-lookup"><span data-stu-id="cb323-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cb323-113">親要素</span><span class="sxs-lookup"><span data-stu-id="cb323-113">Parent Elements</span></span>

|<span data-ttu-id="cb323-114">要素</span><span class="sxs-lookup"><span data-stu-id="cb323-114">Element</span></span>|<span data-ttu-id="cb323-115">説明</span><span class="sxs-lookup"><span data-stu-id="cb323-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cb323-116">TableColumnItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="cb323-116">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="cb323-117">テーブルの列のデータのラベル、幅、および配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="cb323-117">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="cb323-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="cb323-118">Text Value</span></span>

<span data-ttu-id="cb323-119">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="cb323-119">Specify one of the following values.</span></span> <span data-ttu-id="cb323-120">(これらの値は大文字と小文字が区別されません)。</span><span class="sxs-lookup"><span data-stu-id="cb323-120">(These values are not case-sensitive.)</span></span>

<span data-ttu-id="cb323-121">列に表示されているデータを左にシフトします。</span><span class="sxs-lookup"><span data-stu-id="cb323-121">Left Shifts the data displayed in the column to the left.</span></span> <span data-ttu-id="cb323-122">(この要素が指定されていない場合の既定値です)。</span><span class="sxs-lookup"><span data-stu-id="cb323-122">(This is the default if this element is not specified.)</span></span>

<span data-ttu-id="cb323-123">列に表示されているデータを右にシフトします。</span><span class="sxs-lookup"><span data-stu-id="cb323-123">Right Shifts the data displayed in the column to the right.</span></span>

<span data-ttu-id="cb323-124">中央には、列に表示されるデータが中央に配置されます。</span><span class="sxs-lookup"><span data-stu-id="cb323-124">Center Centers the data displayed in the column.</span></span>

## <a name="remarks"></a><span data-ttu-id="cb323-125">解説</span><span class="sxs-lookup"><span data-stu-id="cb323-125">Remarks</span></span>

<span data-ttu-id="cb323-126">テーブルビューのコンポーネントの詳細については、「 [テーブルビュー](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb323-126">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cb323-127">参照</span><span class="sxs-lookup"><span data-stu-id="cb323-127">See Also</span></span>

[<span data-ttu-id="cb323-128">テーブルビュー</span><span class="sxs-lookup"><span data-stu-id="cb323-128">Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="cb323-129">TableColumnItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="cb323-129">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)
