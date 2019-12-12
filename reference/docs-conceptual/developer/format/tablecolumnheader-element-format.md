---
title: TableColumnHeader 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49ff3062-6396-4aa8-919b-3fd3ac60899a
caps.latest.revision: 19
ms.openlocfilehash: d3ad7fa563def17d43ce4dc64d155b65b650521f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361851"
---
# <a name="tablecolumnheader-element-format"></a><span data-ttu-id="c8f47-102">TableColumnHeader 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c8f47-102">TableColumnHeader Element (Format)</span></span>

<span data-ttu-id="c8f47-103">ラベル、列の幅、およびテーブルの列のラベルの配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="c8f47-103">Defines the label, the width of the column, and the alignment of the label for a column of the table.</span></span>

<span data-ttu-id="c8f47-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素 tablecontrol (format) の TableHeaders の TableColumnHeader 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c8f47-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c8f47-105">構文</span><span class="sxs-lookup"><span data-stu-id="c8f47-105">Syntax</span></span>

```xml
<TableColumnHeader>
  <Label>DisplayedLabel</Label>
  <Width>NumberOfCharacters</Width>
  <Alignment>Left, Right, or Centered</Alignment>
</TableColumnHeader>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c8f47-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="c8f47-106">Attributes and Elements</span></span>

<span data-ttu-id="c8f47-107">次のセクションでは、`TableColumnHeader` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8f47-107">The following sections describe attributes, child elements, and the parent element of the `TableColumnHeader` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c8f47-108">属性</span><span class="sxs-lookup"><span data-stu-id="c8f47-108">Attributes</span></span>

<span data-ttu-id="c8f47-109">なし。</span><span class="sxs-lookup"><span data-stu-id="c8f47-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c8f47-110">子要素</span><span class="sxs-lookup"><span data-stu-id="c8f47-110">Child Elements</span></span>

|<span data-ttu-id="c8f47-111">要素</span><span class="sxs-lookup"><span data-stu-id="c8f47-111">Element</span></span>|<span data-ttu-id="c8f47-112">[説明]</span><span class="sxs-lookup"><span data-stu-id="c8f47-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c8f47-113">TableControl (Format) の TableColumnHeader の Label 要素</span><span class="sxs-lookup"><span data-stu-id="c8f47-113">Label Element For TableColumnHeader for TableControl (Format)</span></span>](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="c8f47-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c8f47-114">Optional element.</span></span><br /><br /> <span data-ttu-id="c8f47-115">列の上部に表示されるラベルを定義します。</span><span class="sxs-lookup"><span data-stu-id="c8f47-115">Defines the label that is displayed at the top of the column.</span></span> <span data-ttu-id="c8f47-116">ラベルが指定されていない場合は、行に表示される値を持つプロパティの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8f47-116">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>|
|[<span data-ttu-id="c8f47-117">TableControl の TableColumnHeader の Width 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c8f47-117">Width Element for TableColumnHeader for TableControl (Format)</span></span>](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="c8f47-118">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="c8f47-118">Required element.</span></span><br /><br /> <span data-ttu-id="c8f47-119">列の幅 (文字数) を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8f47-119">Specifies the width (in characters) of the column.</span></span>|
|[<span data-ttu-id="c8f47-120">TableControl (Format) の TableColumnHeader の Alignment 要素</span><span class="sxs-lookup"><span data-stu-id="c8f47-120">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="c8f47-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c8f47-121">Optional element.</span></span><br /><br /> <span data-ttu-id="c8f47-122">列のラベルを表示する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8f47-122">Specifies how the label of the column is displayed.</span></span> <span data-ttu-id="c8f47-123">アラインメントが指定されていない場合、ラベルは左揃えで配置されます。</span><span class="sxs-lookup"><span data-stu-id="c8f47-123">If no alignment is specified, the label is aligned on the left.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c8f47-124">親要素</span><span class="sxs-lookup"><span data-stu-id="c8f47-124">Parent Elements</span></span>

|<span data-ttu-id="c8f47-125">要素</span><span class="sxs-lookup"><span data-stu-id="c8f47-125">Element</span></span>|<span data-ttu-id="c8f47-126">[説明]</span><span class="sxs-lookup"><span data-stu-id="c8f47-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c8f47-127">TableHeaders 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c8f47-127">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="c8f47-128">テーブルビューの列を定義します。</span><span class="sxs-lookup"><span data-stu-id="c8f47-128">Defines the columns of a table view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c8f47-129">コメント</span><span class="sxs-lookup"><span data-stu-id="c8f47-129">Remarks</span></span>

<span data-ttu-id="c8f47-130">テーブルの列ごとにヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8f47-130">Specify a header for each column of the table.</span></span> <span data-ttu-id="c8f47-131">列は `TableColumnHeader` の要素が定義されている順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8f47-131">The columns are displayed in the order in which the `TableColumnHeader` elements are defined.</span></span>

<span data-ttu-id="c8f47-132">テーブルの `TableColumnHeader` 要素の数は、`TableRowEntry` 要素と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8f47-132">A table must have the same number of `TableColumnHeader` elements as `TableRowEntry` elements.</span></span> <span data-ttu-id="c8f47-133">列ヘッダーは、テーブルの上部のテキストの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="c8f47-133">The column header defines how the text at the top of the table is displayed.</span></span> <span data-ttu-id="c8f47-134">行のエントリによって、テーブルの行に表示されるデータが定義されます。</span><span class="sxs-lookup"><span data-stu-id="c8f47-134">The row entries define what data is displayed in the rows of the table.</span></span>

<span data-ttu-id="c8f47-135">テーブルビューのコンポーネントの詳細については、「[テーブルビュー](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f47-135">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="c8f47-136">例</span><span class="sxs-lookup"><span data-stu-id="c8f47-136">Example</span></span>

<span data-ttu-id="c8f47-137">次の例は、2つの `TableColumnHeader` 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="c8f47-137">The following example shows two `TableColumnHeader` elements.</span></span> <span data-ttu-id="c8f47-138">最初の要素は、ラベルが "Column 1" で、幅が16文字で、ラベルが左揃えである列を定義します。</span><span class="sxs-lookup"><span data-stu-id="c8f47-138">The first element defines a column whose label is "Column 1", has a width of 16 characters, and whose label is aligned on the left.</span></span> <span data-ttu-id="c8f47-139">2番目の要素は、ラベルが "Column 2" で、幅が10文字で、列のラベルが中央にある列を定義します。</span><span class="sxs-lookup"><span data-stu-id="c8f47-139">The second element defines a column whose label is "Column 2", has a width of 10 characters, and whose label is centered in the column.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c8f47-140">参照</span><span class="sxs-lookup"><span data-stu-id="c8f47-140">See Also</span></span>

[<span data-ttu-id="c8f47-141">TableControl (Format) の TableColumnHeader の Alignment 要素</span><span class="sxs-lookup"><span data-stu-id="c8f47-141">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="c8f47-142">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="c8f47-142">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="c8f47-143">TableControl (Format) の TableColumnHeader の Label 要素</span><span class="sxs-lookup"><span data-stu-id="c8f47-143">Label Element for TableColumnHeader for TableControl (Format)</span></span>](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="c8f47-144">TableControl の TableHeaders 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c8f47-144">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="c8f47-145">TableColumnHeader for TableControl 要素の幅 (形式)</span><span class="sxs-lookup"><span data-stu-id="c8f47-145">Width for TableColumnHeader for TableControl Element (Format)</span></span>](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="c8f47-146">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="c8f47-146">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
