---
ms.date: 09/13/2016
ms.topic: reference
title: TableControl の TableRowEntry の EntrySelectedBy 要素 (書式)
description: TableControl の TableRowEntry の EntrySelectedBy 要素 (書式)
ms.openlocfilehash: 1b7fc60b6fa9864b66e9edfebb3e4a86e287f3f8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645894"
---
# <a name="entryselectedby-element-for-tablerowentry--for-tablecontrol-format"></a><span data-ttu-id="7f006-103">TableControl の TableRowEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7f006-103">EntrySelectedBy Element for TableRowEntry  for TableControl (Format)</span></span>

<span data-ttu-id="7f006-104">テーブルビューのこの定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="7f006-104">Defines the .NET types that use this definition of the table view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="7f006-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) 要素 (format) のエントリ</span><span class="sxs-lookup"><span data-stu-id="7f006-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7f006-106">構文</span><span class="sxs-lookup"><span data-stu-id="7f006-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7f006-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7f006-107">Attributes and Elements</span></span>

<span data-ttu-id="7f006-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `EntrySelectedBy` ます。</span><span class="sxs-lookup"><span data-stu-id="7f006-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7f006-109">属性</span><span class="sxs-lookup"><span data-stu-id="7f006-109">Attributes</span></span>

<span data-ttu-id="7f006-110">なし。</span><span class="sxs-lookup"><span data-stu-id="7f006-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7f006-111">子要素</span><span class="sxs-lookup"><span data-stu-id="7f006-111">Child Elements</span></span>

|<span data-ttu-id="7f006-112">要素</span><span class="sxs-lookup"><span data-stu-id="7f006-112">Element</span></span>|<span data-ttu-id="7f006-113">説明</span><span class="sxs-lookup"><span data-stu-id="7f006-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7f006-114">TableControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7f006-114">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="7f006-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="7f006-115">Optional element.</span></span><br /><br /> <span data-ttu-id="7f006-116">このテーブルビュー定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="7f006-116">Defines the condition that must exist for this table view definition to be used.</span></span>|
|[<span data-ttu-id="7f006-117">TableControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7f006-117">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="7f006-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="7f006-118">Optional element.</span></span><br /><br /> <span data-ttu-id="7f006-119">このテーブルビュー定義を使用する一連の .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="7f006-119">Specifies a set of .NET types that use this table view definition.</span></span>|
|[<span data-ttu-id="7f006-120">TableControl の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7f006-120">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="7f006-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="7f006-121">Optional element.</span></span><br /><br /> <span data-ttu-id="7f006-122">このテーブルビュー定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="7f006-122">Specifies a .NET type that uses this table view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7f006-123">親要素</span><span class="sxs-lookup"><span data-stu-id="7f006-123">Parent Elements</span></span>

|<span data-ttu-id="7f006-124">要素</span><span class="sxs-lookup"><span data-stu-id="7f006-124">Element</span></span>|<span data-ttu-id="7f006-125">説明</span><span class="sxs-lookup"><span data-stu-id="7f006-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7f006-126">TableControl (Format) の TableRowEntry 要素</span><span class="sxs-lookup"><span data-stu-id="7f006-126">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="7f006-127">テーブルの行に表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="7f006-127">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7f006-128">解説</span><span class="sxs-lookup"><span data-stu-id="7f006-128">Remarks</span></span>

<span data-ttu-id="7f006-129">テーブルビュー定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f006-129">You must specify at least one type, selection set, or selection condition for a table view definition.</span></span> <span data-ttu-id="7f006-130">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="7f006-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="7f006-131">選択条件は、オブジェクトが特定のプロパティを持っている場合や、特定のプロパティ値またはスクリプトがに評価される場合など、使用する定義のために存在する必要がある条件を定義するために使用され `true` ます。</span><span class="sxs-lookup"><span data-stu-id="7f006-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="7f006-132">選択条件の詳細については、「 [ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f006-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="7f006-133">テーブルビューのコンポーネントの詳細については、「 [テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f006-133">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="7f006-134">例</span><span class="sxs-lookup"><span data-stu-id="7f006-134">Example</span></span>

<span data-ttu-id="7f006-135">次の例は、 `TableRowEntry` system.object オブジェクトのプロパティを表示するために使用[](/dotnet/api/System.Diagnostics.Process)される要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="7f006-135">The following example shows a `TableRowEntry` element that is used to display the properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </EntrySelectedBy>
  <TableColumnItems>
    <TableColumnItem>
      <PropertyName>PropertyForFirstColumn</PropertyName>
    </TableColumnItem>
    <TableColumnItem>
      <PropertyName>PropertyForSecondColumn</PropertyName>
    </TableColumnItem>
  </TableColumnItems>
</TableRowEntry>
```

## <a name="see-also"></a><span data-ttu-id="7f006-136">参照</span><span class="sxs-lookup"><span data-stu-id="7f006-136">See Also</span></span>

[<span data-ttu-id="7f006-137">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="7f006-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="7f006-138">TableControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7f006-138">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="7f006-139">TableControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7f006-139">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="7f006-140">TableControl (Format) の TableRowEntry 要素</span><span class="sxs-lookup"><span data-stu-id="7f006-140">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="7f006-141">TableControl の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7f006-141">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="7f006-142">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="7f006-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
