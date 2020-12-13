---
ms.date: 09/13/2016
ms.topic: reference
title: TableControl の TableRowEntries の TableRowEntry 要素 (書式)
description: TableControl の TableRowEntries の TableRowEntry 要素 (書式)
ms.openlocfilehash: 60d64b7c14b40e87825ada36e19f52a66fe8b6cb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659769"
---
# <a name="tablerowentry-element-for-tablerowentries-for-tablecontrol-format"></a><span data-ttu-id="669ab-103">TableControl の TableRowEntries の TableRowEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="669ab-103">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>

<span data-ttu-id="669ab-104">テーブルの行に表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="669ab-104">Defines the data that is displayed in a row of the table.</span></span>

<span data-ttu-id="669ab-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries の TableControl (format) TableRowEntry 要素の TableRowEntries for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="669ab-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="669ab-106">構文</span><span class="sxs-lookup"><span data-stu-id="669ab-106">Syntax</span></span>

```xml
<TableRowEntry>
  <Wrap/>
  <EntrySelectedBy>...</EntrySelectedBy>
  <TableColumnItems>...</TableColumnItems>
</TableRowEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="669ab-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="669ab-107">Attributes and Elements</span></span>

<span data-ttu-id="669ab-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `TableRowEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="669ab-108">The following sections describe attributes, child elements, and parent element of the `TableRowEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="669ab-109">属性</span><span class="sxs-lookup"><span data-stu-id="669ab-109">Attributes</span></span>

<span data-ttu-id="669ab-110">なし。</span><span class="sxs-lookup"><span data-stu-id="669ab-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="669ab-111">子要素</span><span class="sxs-lookup"><span data-stu-id="669ab-111">Child Elements</span></span>

|<span data-ttu-id="669ab-112">要素</span><span class="sxs-lookup"><span data-stu-id="669ab-112">Element</span></span>|<span data-ttu-id="669ab-113">説明</span><span class="sxs-lookup"><span data-stu-id="669ab-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="669ab-114">TableControl (Format) の TableRowEntry の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="669ab-114">EntrySelectedBy Element for TableRowEntry for TableControl (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="669ab-115">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="669ab-115">Required element.</span></span><br /><br /> <span data-ttu-id="669ab-116">プロパティ値が行内に表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="669ab-116">Defines the objects whose property values are displayed in the row.</span></span>|
|[<span data-ttu-id="669ab-117">TableControl の TableRowEntry の TableColumnItems 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="669ab-117">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="669ab-118">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="669ab-118">Required element.</span></span><br /><br /> <span data-ttu-id="669ab-119">値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="669ab-119">Defines the properties or scripts whose values are displayed.</span></span>|
|[<span data-ttu-id="669ab-120">TableControl (Format) の TableRowEntry の Wrap 要素</span><span class="sxs-lookup"><span data-stu-id="669ab-120">Wrap Element for TableRowEntry for TableControl (Format)</span></span>](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="669ab-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="669ab-121">Optional element.</span></span><br /><br /> <span data-ttu-id="669ab-122">列幅を超えるテキストを次の行に表示するように指定します。</span><span class="sxs-lookup"><span data-stu-id="669ab-122">Specifies that text that exceeds the column width is displayed on the next line.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="669ab-123">親要素</span><span class="sxs-lookup"><span data-stu-id="669ab-123">Parent Elements</span></span>

|<span data-ttu-id="669ab-124">要素</span><span class="sxs-lookup"><span data-stu-id="669ab-124">Element</span></span>|<span data-ttu-id="669ab-125">説明</span><span class="sxs-lookup"><span data-stu-id="669ab-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="669ab-126">TableControl の TableRowEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="669ab-126">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)|<span data-ttu-id="669ab-127">テーブルの行を定義します。</span><span class="sxs-lookup"><span data-stu-id="669ab-127">Defines the rows of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="669ab-128">解説</span><span class="sxs-lookup"><span data-stu-id="669ab-128">Remarks</span></span>

<span data-ttu-id="669ab-129">1つ `TableColumnItems` の要素と1つの `EntrySelectedBy` 要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="669ab-129">One `TableColumnItems` element and one `EntrySelectedBy` element must be specified.</span></span>

<span data-ttu-id="669ab-130">テーブルビューのコンポーネントの詳細については、「 [テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="669ab-130">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="669ab-131">例</span><span class="sxs-lookup"><span data-stu-id="669ab-131">Example</span></span>

<span data-ttu-id="669ab-132">次の例は、system.string `TableRowEntry` オブジェクトの2つのプロパティの値を表示する行を[](/dotnet/api/System.Diagnostics.Process)定義する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="669ab-132">The following example shows a `TableRowEntry` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </EntrySelectedBy>
  <TableColumnItems>
    <TableColumnItem>
      <PropertyName> Property for first column</PropertyName>
    </TableColumnItem>
    <TableColumnItem>
      <PropertyName> Property for second column</PropertyName>
    </TableColumnItem>
  </TableColumnItems>
</TableRowEntry>
```

## <a name="see-also"></a><span data-ttu-id="669ab-133">参照</span><span class="sxs-lookup"><span data-stu-id="669ab-133">See Also</span></span>

[<span data-ttu-id="669ab-134">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="669ab-134">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="669ab-135">TableControl (Format) の TableRowEntry の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="669ab-135">EntrySelectedBy Element for TableRowEntry for TableControl (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="669ab-136">TableControl の TableRowEntry の TableColumnItems 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="669ab-136">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="669ab-137">TableControl の TableRowEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="669ab-137">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)

[<span data-ttu-id="669ab-138">TableControl (Format) の TableRowEntry の Wrap 要素</span><span class="sxs-lookup"><span data-stu-id="669ab-138">Wrap Element for TableRowEntry for TableControl (Format)</span></span>](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="669ab-139">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="669ab-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
