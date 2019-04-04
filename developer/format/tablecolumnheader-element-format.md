---
title: TableColumnHeader 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49ff3062-6396-4aa8-919b-3fd3ac60899a
caps.latest.revision: 19
ms.openlocfilehash: d3ad7fa563def17d43ce4dc64d155b65b650521f
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057877"
---
# <a name="tablecolumnheader-element-format"></a><span data-ttu-id="867ab-102">TableColumnHeader 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="867ab-102">TableColumnHeader Element (Format)</span></span>

<span data-ttu-id="867ab-103">ラベル、列の幅と、テーブルの列のラベルの配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="867ab-103">Defines the label, the width of the column, and the alignment of the label for a column of the table.</span></span>

<span data-ttu-id="867ab-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableHeaders 要素の要素に TableControl (形式) TableColumnHeader TableHeaders TableControl (形式) 用の</span><span class="sxs-lookup"><span data-stu-id="867ab-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="867ab-105">構文</span><span class="sxs-lookup"><span data-stu-id="867ab-105">Syntax</span></span>

```xml
<TableColumnHeader>
  <Label>DisplayedLabel</Label>
  <Width>NumberOfCharacters</Width>
  <Alignment>Left, Right, or Centered</Alignment>
</TableColumnHeader>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="867ab-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="867ab-106">Attributes and Elements</span></span>

<span data-ttu-id="867ab-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`TableColumnHeader`要素。</span><span class="sxs-lookup"><span data-stu-id="867ab-107">The following sections describe attributes, child elements, and the parent element of the `TableColumnHeader` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="867ab-108">属性</span><span class="sxs-lookup"><span data-stu-id="867ab-108">Attributes</span></span>

<span data-ttu-id="867ab-109">なし。</span><span class="sxs-lookup"><span data-stu-id="867ab-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="867ab-110">子要素</span><span class="sxs-lookup"><span data-stu-id="867ab-110">Child Elements</span></span>

|<span data-ttu-id="867ab-111">要素</span><span class="sxs-lookup"><span data-stu-id="867ab-111">Element</span></span>|<span data-ttu-id="867ab-112">説明</span><span class="sxs-lookup"><span data-stu-id="867ab-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="867ab-113">TableControl (形式) の TableColumnHeader label 要素</span><span class="sxs-lookup"><span data-stu-id="867ab-113">Label Element For TableColumnHeader for TableControl (Format)</span></span>](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="867ab-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="867ab-114">Optional element.</span></span><br /><br /> <span data-ttu-id="867ab-115">列の上部に表示されるラベルを定義します。</span><span class="sxs-lookup"><span data-stu-id="867ab-115">Defines the label that is displayed at the top of the column.</span></span> <span data-ttu-id="867ab-116">ラベルが指定されていない場合は、行の値を持つが表示されるプロパティの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="867ab-116">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>|
|[<span data-ttu-id="867ab-117">TableControl (形式) の TableColumnHeader 幅要素</span><span class="sxs-lookup"><span data-stu-id="867ab-117">Width Element for TableColumnHeader for TableControl (Format)</span></span>](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="867ab-118">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="867ab-118">Required element.</span></span><br /><br /> <span data-ttu-id="867ab-119">(文字) で、列の幅を指定します。</span><span class="sxs-lookup"><span data-stu-id="867ab-119">Specifies the width (in characters) of the column.</span></span>|
|[<span data-ttu-id="867ab-120">TableControl (形式) の TableColumnHeader の alignment 要素</span><span class="sxs-lookup"><span data-stu-id="867ab-120">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="867ab-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="867ab-121">Optional element.</span></span><br /><br /> <span data-ttu-id="867ab-122">列のラベルを表示する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="867ab-122">Specifies how the label of the column is displayed.</span></span> <span data-ttu-id="867ab-123">配置が指定されていない場合、ラベルを左側に配置します。</span><span class="sxs-lookup"><span data-stu-id="867ab-123">If no alignment is specified, the label is aligned on the left.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="867ab-124">親要素</span><span class="sxs-lookup"><span data-stu-id="867ab-124">Parent Elements</span></span>

|<span data-ttu-id="867ab-125">要素</span><span class="sxs-lookup"><span data-stu-id="867ab-125">Element</span></span>|<span data-ttu-id="867ab-126">説明</span><span class="sxs-lookup"><span data-stu-id="867ab-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="867ab-127">TableHeaders 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="867ab-127">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="867ab-128">テーブル ビューの列を定義します。</span><span class="sxs-lookup"><span data-stu-id="867ab-128">Defines the columns of a table view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="867ab-129">コメント</span><span class="sxs-lookup"><span data-stu-id="867ab-129">Remarks</span></span>

<span data-ttu-id="867ab-130">テーブルの各列のヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="867ab-130">Specify a header for each column of the table.</span></span> <span data-ttu-id="867ab-131">列が順番に表示されます、`TableColumnHeader`要素が定義されます。</span><span class="sxs-lookup"><span data-stu-id="867ab-131">The columns are displayed in the order in which the `TableColumnHeader` elements are defined.</span></span>

<span data-ttu-id="867ab-132">テーブルには、同じ数の必要があります`TableColumnHeader`要素として`TableRowEntry`要素。</span><span class="sxs-lookup"><span data-stu-id="867ab-132">A table must have the same number of `TableColumnHeader` elements as `TableRowEntry` elements.</span></span> <span data-ttu-id="867ab-133">列ヘッダーは、テーブルの上部にあるテキストを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="867ab-133">The column header defines how the text at the top of the table is displayed.</span></span> <span data-ttu-id="867ab-134">行のエントリでは、テーブルの行で表示するデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="867ab-134">The row entries define what data is displayed in the rows of the table.</span></span>

<span data-ttu-id="867ab-135">テーブル ビューのコンポーネントに関する詳細については、[テーブル ビュー](./creating-a-table-view.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="867ab-135">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="867ab-136">例</span><span class="sxs-lookup"><span data-stu-id="867ab-136">Example</span></span>

<span data-ttu-id="867ab-137">次の例では 2 つ`TableColumnHeader`要素。</span><span class="sxs-lookup"><span data-stu-id="867ab-137">The following example shows two `TableColumnHeader` elements.</span></span> <span data-ttu-id="867ab-138">最初の要素は、左側にあるラベルを配置し、ラベルは"Column 1"が 16 文字の幅を持つ列を定義します。</span><span class="sxs-lookup"><span data-stu-id="867ab-138">The first element defines a column whose label is "Column 1", has a width of 16 characters, and whose label is aligned on the left.</span></span> <span data-ttu-id="867ab-139">2 番目の要素は、ラベルが、列の中央に配置し、ラベルは"Column 2"が 10 文字の幅を持つ列を定義します。</span><span class="sxs-lookup"><span data-stu-id="867ab-139">The second element defines a column whose label is "Column 2", has a width of 10 characters, and whose label is centered in the column.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="867ab-140">参照</span><span class="sxs-lookup"><span data-stu-id="867ab-140">See Also</span></span>

[<span data-ttu-id="867ab-141">TableControl (形式) の TableColumnHeader の alignment 要素</span><span class="sxs-lookup"><span data-stu-id="867ab-141">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="867ab-142">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="867ab-142">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="867ab-143">TableControl (形式) の TableColumnHeader label 要素</span><span class="sxs-lookup"><span data-stu-id="867ab-143">Label Element for TableColumnHeader for TableControl (Format)</span></span>](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="867ab-144">TableControl (形式) の TableHeaders 要素</span><span class="sxs-lookup"><span data-stu-id="867ab-144">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="867ab-145">TableControl 要素 (形式) の TableColumnHeader の幅</span><span class="sxs-lookup"><span data-stu-id="867ab-145">Width for TableColumnHeader for TableControl Element (Format)</span></span>](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="867ab-146">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="867ab-146">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
