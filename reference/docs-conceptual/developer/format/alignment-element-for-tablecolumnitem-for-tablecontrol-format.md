---
title: TableControl (Format) の TableColumnItem の Alignment 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b07a53df-64f1-49b0-8cea-c993b3f1f76b
caps.latest.revision: 10
ms.openlocfilehash: 1bc936b94ee6fd6239e9e3c4afcdb8f14fbe36eb
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369081"
---
# <a name="alignment-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="8ddf6-102">TableControl の TableColumnItem の Alignment 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8ddf6-102">Alignment Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="8ddf6-103">行の列のデータをどのように表示するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="8ddf6-103">Defines how the data in a column of the row is displayed.</span></span>

<span data-ttu-id="8ddf6-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) TableColumnItems Element (format) TableColumnItem Element (Format)TableColumnItem の Alignment 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="8ddf6-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) Alignment Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8ddf6-105">構文</span><span class="sxs-lookup"><span data-stu-id="8ddf6-105">Syntax</span></span>

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8ddf6-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="8ddf6-106">Attributes and Elements</span></span>

<span data-ttu-id="8ddf6-107">次のセクションでは、`Alignment` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ddf6-107">The following sections describe the attributes, child elements, and parent element of the `Alignment` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8ddf6-108">属性</span><span class="sxs-lookup"><span data-stu-id="8ddf6-108">Attributes</span></span>

<span data-ttu-id="8ddf6-109">なし。</span><span class="sxs-lookup"><span data-stu-id="8ddf6-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8ddf6-110">子要素</span><span class="sxs-lookup"><span data-stu-id="8ddf6-110">Child Elements</span></span>

<span data-ttu-id="8ddf6-111">なし。</span><span class="sxs-lookup"><span data-stu-id="8ddf6-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8ddf6-112">親要素</span><span class="sxs-lookup"><span data-stu-id="8ddf6-112">Parent Elements</span></span>

|<span data-ttu-id="8ddf6-113">要素</span><span class="sxs-lookup"><span data-stu-id="8ddf6-113">Element</span></span>|<span data-ttu-id="8ddf6-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="8ddf6-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8ddf6-115">TableColumnItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="8ddf6-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="8ddf6-116">テーブルの列のデータのラベル、幅、および配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="8ddf6-116">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8ddf6-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="8ddf6-117">Text Value</span></span>

<span data-ttu-id="8ddf6-118">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ddf6-118">Specify one of the following values.</span></span> <span data-ttu-id="8ddf6-119">(これらの値は大文字と小文字が区別されません)。</span><span class="sxs-lookup"><span data-stu-id="8ddf6-119">(These values are not case-sensitive.)</span></span>

<span data-ttu-id="8ddf6-120">列に表示されているデータを左にシフトします。</span><span class="sxs-lookup"><span data-stu-id="8ddf6-120">Left Shifts the data displayed in the column to the left.</span></span> <span data-ttu-id="8ddf6-121">(この要素が指定されていない場合の既定値です)。</span><span class="sxs-lookup"><span data-stu-id="8ddf6-121">(This is the default if this element is not specified.)</span></span>

<span data-ttu-id="8ddf6-122">列に表示されているデータを右にシフトします。</span><span class="sxs-lookup"><span data-stu-id="8ddf6-122">Right Shifts the data displayed in the column to the right.</span></span>

<span data-ttu-id="8ddf6-123">中央には、列に表示されるデータが中央に配置されます。</span><span class="sxs-lookup"><span data-stu-id="8ddf6-123">Center Centers the data displayed in the column.</span></span>

## <a name="remarks"></a><span data-ttu-id="8ddf6-124">コメント</span><span class="sxs-lookup"><span data-stu-id="8ddf6-124">Remarks</span></span>

<span data-ttu-id="8ddf6-125">テーブルビューのコンポーネントの詳細については、「[テーブルビュー](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ddf6-125">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8ddf6-126">参照</span><span class="sxs-lookup"><span data-stu-id="8ddf6-126">See Also</span></span>

[<span data-ttu-id="8ddf6-127">テーブルビュー</span><span class="sxs-lookup"><span data-stu-id="8ddf6-127">Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="8ddf6-128">TableColumnItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="8ddf6-128">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)
