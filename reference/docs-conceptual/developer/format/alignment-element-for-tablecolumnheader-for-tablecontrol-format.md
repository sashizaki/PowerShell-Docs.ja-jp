---
ms.date: 09/13/2016
ms.topic: reference
title: TableControl の TableColumnHeader の Alignment 要素 (書式)
description: TableControl の TableColumnHeader の Alignment 要素 (書式)
ms.openlocfilehash: cf8b90c12c28951283b5870186e2c88d427318a5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666826"
---
# <a name="alignment-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="138ae-103">TableControl の TableColumnHeader の Alignment 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="138ae-103">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="138ae-104">列ヘッダー内のデータを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="138ae-104">Defines how the data in a column header is displayed.</span></span>

<span data-ttu-id="138ae-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素 (format) TableColumnHeader Element (format) Alignment 要素 (format)</span><span class="sxs-lookup"><span data-stu-id="138ae-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element (Format) TableColumnHeader Element (Format) Alignment Element for TableColumnHeader (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="138ae-106">構文</span><span class="sxs-lookup"><span data-stu-id="138ae-106">Syntax</span></span>

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="138ae-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="138ae-107">Attributes and Elements</span></span>

<span data-ttu-id="138ae-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `Alignment` ます。</span><span class="sxs-lookup"><span data-stu-id="138ae-108">The following sections describe the attributes, child elements, and parent element of the `Alignment` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="138ae-109">属性</span><span class="sxs-lookup"><span data-stu-id="138ae-109">Attributes</span></span>

<span data-ttu-id="138ae-110">なし。</span><span class="sxs-lookup"><span data-stu-id="138ae-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="138ae-111">子要素</span><span class="sxs-lookup"><span data-stu-id="138ae-111">Child Elements</span></span>

<span data-ttu-id="138ae-112">なし。</span><span class="sxs-lookup"><span data-stu-id="138ae-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="138ae-113">親要素</span><span class="sxs-lookup"><span data-stu-id="138ae-113">Parent Elements</span></span>

|<span data-ttu-id="138ae-114">要素</span><span class="sxs-lookup"><span data-stu-id="138ae-114">Element</span></span>|<span data-ttu-id="138ae-115">説明</span><span class="sxs-lookup"><span data-stu-id="138ae-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="138ae-116">TableColumnHeader 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="138ae-116">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="138ae-117">テーブルの列のデータのラベル、幅、および配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="138ae-117">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="138ae-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="138ae-118">Text Value</span></span>

<span data-ttu-id="138ae-119">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="138ae-119">Specify one of the following values.</span></span> <span data-ttu-id="138ae-120">これらの値では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="138ae-120">These values are not case-sensitive.</span></span>

<span data-ttu-id="138ae-121">左揃えこの要素が指定されていない場合は、左側の列に表示されるデータが既定値になります。</span><span class="sxs-lookup"><span data-stu-id="138ae-121">Left Aligns the data displayed in the column on the left This is the default if this element is not specified.</span></span>

<span data-ttu-id="138ae-122">右側の列に表示されるデータを右揃えにします。</span><span class="sxs-lookup"><span data-stu-id="138ae-122">Right Aligns the data displayed in the column on the right.</span></span>

<span data-ttu-id="138ae-123">中央には、列に表示されるデータが中央に配置されます。</span><span class="sxs-lookup"><span data-stu-id="138ae-123">Center Centers the data displayed in the column.</span></span>

## <a name="remarks"></a><span data-ttu-id="138ae-124">解説</span><span class="sxs-lookup"><span data-stu-id="138ae-124">Remarks</span></span>

<span data-ttu-id="138ae-125">テーブルビューのコンポーネントの詳細については、「 [テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="138ae-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="138ae-126">例</span><span class="sxs-lookup"><span data-stu-id="138ae-126">Example</span></span>

<span data-ttu-id="138ae-127">この例では、 `TableColumnHeader` データが左側に揃えられている要素を示します。</span><span class="sxs-lookup"><span data-stu-id="138ae-127">This example shows a `TableColumnHeader` element whose data is aligned on the left.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="138ae-128">参照</span><span class="sxs-lookup"><span data-stu-id="138ae-128">See Also</span></span>

[<span data-ttu-id="138ae-129">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="138ae-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="138ae-130">TableColumnHeader 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="138ae-130">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="138ae-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="138ae-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
