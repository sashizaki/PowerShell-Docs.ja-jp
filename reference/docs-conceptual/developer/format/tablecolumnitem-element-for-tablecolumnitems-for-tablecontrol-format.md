---
ms.date: 09/13/2016
ms.topic: reference
title: TableControl の TableColumnItems の TableColumnItem 要素 (書式)
description: TableControl の TableColumnItems の TableColumnItem 要素 (書式)
ms.openlocfilehash: 8ef5158c9bb9f074d5c58190d4d3b20c10c83744
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659856"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a><span data-ttu-id="8dc80-103">TableControl の TableColumnItems の TableColumnItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8dc80-103">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

<span data-ttu-id="8dc80-104">行の列に値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="8dc80-104">Defines the property or script whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="8dc80-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries 要素の tablecontrol (format) TableRowEntry 要素の TableRowEntries for tablecontrol (format) TableColumnItems 要素 for TableControlEntry for tablecontrol (format) TableColumnItem for TableControl (format) TableColumnItems 要素</span><span class="sxs-lookup"><span data-stu-id="8dc80-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format) TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8dc80-106">構文</span><span class="sxs-lookup"><span data-stu-id="8dc80-106">Syntax</span></span>

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <FormatString>FormatPattern</FormatString>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8dc80-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8dc80-107">Attributes and Elements</span></span>

<span data-ttu-id="8dc80-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `TableColumnItem` ます。</span><span class="sxs-lookup"><span data-stu-id="8dc80-108">The following sections describe the attributes, child elements, and parent element of the `TableColumnItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8dc80-109">属性</span><span class="sxs-lookup"><span data-stu-id="8dc80-109">Attributes</span></span>

<span data-ttu-id="8dc80-110">なし。</span><span class="sxs-lookup"><span data-stu-id="8dc80-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8dc80-111">子要素</span><span class="sxs-lookup"><span data-stu-id="8dc80-111">Child Elements</span></span>

|<span data-ttu-id="8dc80-112">要素</span><span class="sxs-lookup"><span data-stu-id="8dc80-112">Element</span></span>|<span data-ttu-id="8dc80-113">説明</span><span class="sxs-lookup"><span data-stu-id="8dc80-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8dc80-114">TableControl の TableColumnItem の Alignment 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8dc80-114">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="8dc80-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="8dc80-115">Optional element.</span></span><br /><br /> <span data-ttu-id="8dc80-116">行の列のデータをどのように表示するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="8dc80-116">Defines how the data in a column of the row is displayed.</span></span>|
|[<span data-ttu-id="8dc80-117">TableControl の TableColumnItem の FormatString 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8dc80-117">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="8dc80-118">行の列のデータの書式設定に使用する形式パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="8dc80-118">Specifies a format pattern that is used to format the data in the column of the row.</span></span>|
|[<span data-ttu-id="8dc80-119">TableControl の TableColumnItem の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8dc80-119">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="8dc80-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="8dc80-120">Optional element.</span></span><br /><br /> <span data-ttu-id="8dc80-121">値が表示されるプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8dc80-121">Specifies the name of the property whose value is displayed.</span></span>|
|[<span data-ttu-id="8dc80-122">TableControl の TableColumnItem の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8dc80-122">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="8dc80-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="8dc80-123">Optional element.</span></span><br /><br /> <span data-ttu-id="8dc80-124">行の列に値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="8dc80-124">Specifies the script whose value is displayed in the column of a row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8dc80-125">親要素</span><span class="sxs-lookup"><span data-stu-id="8dc80-125">Parent Elements</span></span>

|<span data-ttu-id="8dc80-126">要素</span><span class="sxs-lookup"><span data-stu-id="8dc80-126">Element</span></span>|<span data-ttu-id="8dc80-127">説明</span><span class="sxs-lookup"><span data-stu-id="8dc80-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8dc80-128">TableControl (Format) の TableControlEntry の TableColumnItems 要素</span><span class="sxs-lookup"><span data-stu-id="8dc80-128">TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="8dc80-129">値が行内に表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="8dc80-129">Defines the properties or scripts whose values are displayed in the row.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8dc80-130">解説</span><span class="sxs-lookup"><span data-stu-id="8dc80-130">Remarks</span></span>

<span data-ttu-id="8dc80-131">行の各列に、オブジェクトまたはスクリプトのプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8dc80-131">You can specify a property of an object or a script in each column of the row.</span></span> <span data-ttu-id="8dc80-132">子要素が指定されていない場合、項目はプレースホルダーであり、データは表示されません。</span><span class="sxs-lookup"><span data-stu-id="8dc80-132">If no child elements are specified, the item is a placeholder, and no data is displayed.</span></span>

<span data-ttu-id="8dc80-133">テーブルビューのコンポーネントの詳細については、「 [テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8dc80-133">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="8dc80-134">例</span><span class="sxs-lookup"><span data-stu-id="8dc80-134">Example</span></span>

<span data-ttu-id="8dc80-135">この例は、 `TableColumnItem` `Status` system.object オブジェクトのプロパティの値を表示する要素[](/dotnet/api/System.Diagnostics.Process)を示しています。</span><span class="sxs-lookup"><span data-stu-id="8dc80-135">This example shows a `TableColumnItem` element that displays the value of the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="8dc80-136">参照</span><span class="sxs-lookup"><span data-stu-id="8dc80-136">See Also</span></span>

[<span data-ttu-id="8dc80-137">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="8dc80-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="8dc80-138">TableControl の TableColumnItem の Alignment 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8dc80-138">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="8dc80-139">TableColumnItems 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="8dc80-139">TableColumnItems Element (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="8dc80-140">TableControl の TableColumnItem の FormatString 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8dc80-140">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="8dc80-141">TableControl の TableColumnItem の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8dc80-141">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="8dc80-142">TableControl の TableColumnItem の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8dc80-142">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="8dc80-143">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="8dc80-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
