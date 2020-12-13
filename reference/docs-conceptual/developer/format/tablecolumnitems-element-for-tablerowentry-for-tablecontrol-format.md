---
ms.date: 09/13/2016
ms.topic: reference
title: TableControl の TableRowEntry の TableColumnItems 要素 (書式)
description: TableControl の TableRowEntry の TableColumnItems 要素 (書式)
ms.openlocfilehash: 4d600a366d2be1c453f05b301bdf575351dd51c1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667761"
---
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a><span data-ttu-id="0791a-103">TableControl の TableRowEntry の TableColumnItems 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0791a-103">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>

<span data-ttu-id="0791a-104">値が行内に表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="0791a-104">Defines the properties or scripts whose values are displayed in a row.</span></span>

<span data-ttu-id="0791a-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries 要素の tablecontrol (format) TableRowEntry 要素の TableRowEntries for TableControl (Format) TableColumnItems Element for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="0791a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0791a-106">構文</span><span class="sxs-lookup"><span data-stu-id="0791a-106">Syntax</span></span>

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0791a-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0791a-107">Attributes and Elements</span></span>

<span data-ttu-id="0791a-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `TableColumnItems` ます。</span><span class="sxs-lookup"><span data-stu-id="0791a-108">The following sections describe the attributes, child elements, and parent element of the `TableColumnItems` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0791a-109">属性</span><span class="sxs-lookup"><span data-stu-id="0791a-109">Attributes</span></span>

<span data-ttu-id="0791a-110">なし。</span><span class="sxs-lookup"><span data-stu-id="0791a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0791a-111">子要素</span><span class="sxs-lookup"><span data-stu-id="0791a-111">Child Elements</span></span>

|<span data-ttu-id="0791a-112">要素</span><span class="sxs-lookup"><span data-stu-id="0791a-112">Element</span></span>|<span data-ttu-id="0791a-113">説明</span><span class="sxs-lookup"><span data-stu-id="0791a-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0791a-114">TableControl の TableColumnItems の TableColumnItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0791a-114">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="0791a-115">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="0791a-115">Required element.</span></span><br /><br /> <span data-ttu-id="0791a-116">行の列に値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="0791a-116">Defines the property or script whose value is displayed in a column of the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0791a-117">親要素</span><span class="sxs-lookup"><span data-stu-id="0791a-117">Parent Elements</span></span>

|<span data-ttu-id="0791a-118">要素</span><span class="sxs-lookup"><span data-stu-id="0791a-118">Element</span></span>|<span data-ttu-id="0791a-119">説明</span><span class="sxs-lookup"><span data-stu-id="0791a-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0791a-120">TableControl の TableRowEntries の TableRowEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0791a-120">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="0791a-121">テーブルの行に表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="0791a-121">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0791a-122">解説</span><span class="sxs-lookup"><span data-stu-id="0791a-122">Remarks</span></span>

<span data-ttu-id="0791a-123">`TableColumnItem`行の各列には要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="0791a-123">A `TableColumnItem` element is required for each column of the row.</span></span> <span data-ttu-id="0791a-124">最初のエントリは最初の列に、2番目の列には2番目のエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0791a-124">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

<span data-ttu-id="0791a-125">テーブルビューのコンポーネントの詳細については、「 [テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0791a-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="0791a-126">例</span><span class="sxs-lookup"><span data-stu-id="0791a-126">Example</span></span>

<span data-ttu-id="0791a-127">次の例は、 `TableColumnItems` system.object オブジェクトの3つのプロパティ[](/dotnet/api/System.Diagnostics.Process)を定義する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="0791a-127">The following example shows a `TableColumnItems` element that defines three properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItems>
  <TableColumnItem>
    <PropertyName>Status</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>Name</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>DisplayName</PropertyName>
  </TableColumnItem>
</TableColumnItems>

```

## <a name="see-also"></a><span data-ttu-id="0791a-128">参照</span><span class="sxs-lookup"><span data-stu-id="0791a-128">See Also</span></span>

[<span data-ttu-id="0791a-129">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="0791a-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="0791a-130">TableColumnItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="0791a-130">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="0791a-131">TableRowEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="0791a-131">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="0791a-132">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="0791a-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
