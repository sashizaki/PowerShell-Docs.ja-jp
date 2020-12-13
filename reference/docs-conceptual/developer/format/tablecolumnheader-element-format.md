---
ms.date: 09/13/2016
ms.topic: reference
title: TableColumnHeader 要素 (書式)
description: TableColumnHeader 要素 (書式)
ms.openlocfilehash: 30368512875b7c5c4cf3c686f3d09540dea1bd26
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651520"
---
# <a name="tablecolumnheader-element-format"></a><span data-ttu-id="8b224-103">TableColumnHeader 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8b224-103">TableColumnHeader Element (Format)</span></span>

<span data-ttu-id="8b224-104">ラベル、列の幅、およびテーブルの列のラベルの配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="8b224-104">Defines the label, the width of the column, and the alignment of the label for a column of the table.</span></span>

<span data-ttu-id="8b224-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素 tablecontrol (format) の TableHeaders の TableColumnHeader 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="8b224-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8b224-106">構文</span><span class="sxs-lookup"><span data-stu-id="8b224-106">Syntax</span></span>

```xml
<TableColumnHeader>
  <Label>DisplayedLabel</Label>
  <Width>NumberOfCharacters</Width>
  <Alignment>Left, Right, or Centered</Alignment>
</TableColumnHeader>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8b224-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8b224-107">Attributes and Elements</span></span>

<span data-ttu-id="8b224-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `TableColumnHeader` ます。</span><span class="sxs-lookup"><span data-stu-id="8b224-108">The following sections describe attributes, child elements, and the parent element of the `TableColumnHeader` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8b224-109">属性</span><span class="sxs-lookup"><span data-stu-id="8b224-109">Attributes</span></span>

<span data-ttu-id="8b224-110">なし。</span><span class="sxs-lookup"><span data-stu-id="8b224-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8b224-111">子要素</span><span class="sxs-lookup"><span data-stu-id="8b224-111">Child Elements</span></span>

|<span data-ttu-id="8b224-112">要素</span><span class="sxs-lookup"><span data-stu-id="8b224-112">Element</span></span>|<span data-ttu-id="8b224-113">説明</span><span class="sxs-lookup"><span data-stu-id="8b224-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8b224-114">TableControl (Format) の TableColumnHeader の Label 要素</span><span class="sxs-lookup"><span data-stu-id="8b224-114">Label Element For TableColumnHeader for TableControl (Format)</span></span>](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="8b224-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="8b224-115">Optional element.</span></span><br /><br /> <span data-ttu-id="8b224-116">列の上部に表示されるラベルを定義します。</span><span class="sxs-lookup"><span data-stu-id="8b224-116">Defines the label that is displayed at the top of the column.</span></span> <span data-ttu-id="8b224-117">ラベルが指定されていない場合は、行に表示される値を持つプロパティの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8b224-117">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>|
|[<span data-ttu-id="8b224-118">TableControl の TableColumnHeader の Width 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8b224-118">Width Element for TableColumnHeader for TableControl (Format)</span></span>](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="8b224-119">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="8b224-119">Required element.</span></span><br /><br /> <span data-ttu-id="8b224-120">列の幅 (文字数) を指定します。</span><span class="sxs-lookup"><span data-stu-id="8b224-120">Specifies the width (in characters) of the column.</span></span>|
|[<span data-ttu-id="8b224-121">TableControl の TableColumnHeader の Alignment 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8b224-121">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="8b224-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="8b224-122">Optional element.</span></span><br /><br /> <span data-ttu-id="8b224-123">列のラベルを表示する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="8b224-123">Specifies how the label of the column is displayed.</span></span> <span data-ttu-id="8b224-124">アラインメントが指定されていない場合、ラベルは左揃えで配置されます。</span><span class="sxs-lookup"><span data-stu-id="8b224-124">If no alignment is specified, the label is aligned on the left.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8b224-125">親要素</span><span class="sxs-lookup"><span data-stu-id="8b224-125">Parent Elements</span></span>

|<span data-ttu-id="8b224-126">要素</span><span class="sxs-lookup"><span data-stu-id="8b224-126">Element</span></span>|<span data-ttu-id="8b224-127">説明</span><span class="sxs-lookup"><span data-stu-id="8b224-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8b224-128">TableHeaders 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="8b224-128">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="8b224-129">テーブルビューの列を定義します。</span><span class="sxs-lookup"><span data-stu-id="8b224-129">Defines the columns of a table view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8b224-130">解説</span><span class="sxs-lookup"><span data-stu-id="8b224-130">Remarks</span></span>

<span data-ttu-id="8b224-131">テーブルの列ごとにヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="8b224-131">Specify a header for each column of the table.</span></span> <span data-ttu-id="8b224-132">列は、要素が定義されている順序で表示され `TableColumnHeader` ます。</span><span class="sxs-lookup"><span data-stu-id="8b224-132">The columns are displayed in the order in which the `TableColumnHeader` elements are defined.</span></span>

<span data-ttu-id="8b224-133">テーブルには、要素と同じ数の要素が含まれている必要があり `TableColumnHeader` `TableRowEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="8b224-133">A table must have the same number of `TableColumnHeader` elements as `TableRowEntry` elements.</span></span> <span data-ttu-id="8b224-134">列ヘッダーは、テーブルの上部のテキストの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="8b224-134">The column header defines how the text at the top of the table is displayed.</span></span> <span data-ttu-id="8b224-135">行のエントリによって、テーブルの行に表示されるデータが定義されます。</span><span class="sxs-lookup"><span data-stu-id="8b224-135">The row entries define what data is displayed in the rows of the table.</span></span>

<span data-ttu-id="8b224-136">テーブルビューのコンポーネントの詳細については、「 [テーブルビュー](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b224-136">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="8b224-137">例</span><span class="sxs-lookup"><span data-stu-id="8b224-137">Example</span></span>

<span data-ttu-id="8b224-138">次の例は、2つの `TableColumnHeader` 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="8b224-138">The following example shows two `TableColumnHeader` elements.</span></span> <span data-ttu-id="8b224-139">最初の要素は、ラベルが "Column 1" で、幅が16文字で、ラベルが左揃えである列を定義します。</span><span class="sxs-lookup"><span data-stu-id="8b224-139">The first element defines a column whose label is "Column 1", has a width of 16 characters, and whose label is aligned on the left.</span></span> <span data-ttu-id="8b224-140">2番目の要素は、ラベルが "Column 2" で、幅が10文字で、列のラベルが中央にある列を定義します。</span><span class="sxs-lookup"><span data-stu-id="8b224-140">The second element defines a column whose label is "Column 2", has a width of 10 characters, and whose label is centered in the column.</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>
    <Label>Column 1</Label)
    <Width>16</Width>
    <Alignment>Left</Alignment>
  </TableColumnHeader>
    <TableColumnHeader>
    <Label>Column 2</Label)
    <Width>10</Width>
    <Alignment>Centered</Alignment>
  </TableColumnHeader>
</TableHeaders>
```

## <a name="see-also"></a><span data-ttu-id="8b224-141">参照</span><span class="sxs-lookup"><span data-stu-id="8b224-141">See Also</span></span>

[<span data-ttu-id="8b224-142">TableControl の TableColumnHeader の Alignment 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8b224-142">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="8b224-143">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="8b224-143">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="8b224-144">TableControl の TableColumnHeader の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8b224-144">Label Element for TableColumnHeader for TableControl (Format)</span></span>](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="8b224-145">TableControl の TableHeaders 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="8b224-145">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="8b224-146">TableColumnHeader for TableControl 要素の幅 (形式)</span><span class="sxs-lookup"><span data-stu-id="8b224-146">Width for TableColumnHeader for TableControl Element (Format)</span></span>](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="8b224-147">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="8b224-147">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
