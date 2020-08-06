---
title: TableControl (Format) の TableRowEntry の EntrySelectedBy 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 047a10fb6b38dfa8f78a7741fd50b781d4a14b6d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787701"
---
# <a name="entryselectedby-element-for-tablerowentry--for-tablecontrol-format"></a><span data-ttu-id="24386-102">TableControl の TableRowEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="24386-102">EntrySelectedBy Element for TableRowEntry  for TableControl (Format)</span></span>

<span data-ttu-id="24386-103">テーブルビューのこの定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="24386-103">Defines the .NET types that use this definition of the table view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="24386-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) 要素 (format) のエントリ</span><span class="sxs-lookup"><span data-stu-id="24386-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="24386-105">構文</span><span class="sxs-lookup"><span data-stu-id="24386-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="24386-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="24386-106">Attributes and Elements</span></span>

<span data-ttu-id="24386-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `EntrySelectedBy` ます。</span><span class="sxs-lookup"><span data-stu-id="24386-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="24386-108">属性</span><span class="sxs-lookup"><span data-stu-id="24386-108">Attributes</span></span>

<span data-ttu-id="24386-109">なし。</span><span class="sxs-lookup"><span data-stu-id="24386-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="24386-110">子要素</span><span class="sxs-lookup"><span data-stu-id="24386-110">Child Elements</span></span>

|<span data-ttu-id="24386-111">要素</span><span class="sxs-lookup"><span data-stu-id="24386-111">Element</span></span>|<span data-ttu-id="24386-112">説明</span><span class="sxs-lookup"><span data-stu-id="24386-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="24386-113">TableControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="24386-113">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="24386-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="24386-114">Optional element.</span></span><br /><br /> <span data-ttu-id="24386-115">このテーブルビュー定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="24386-115">Defines the condition that must exist for this table view definition to be used.</span></span>|
|[<span data-ttu-id="24386-116">TableControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="24386-116">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="24386-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="24386-117">Optional element.</span></span><br /><br /> <span data-ttu-id="24386-118">このテーブルビュー定義を使用する一連の .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="24386-118">Specifies a set of .NET types that use this table view definition.</span></span>|
|[<span data-ttu-id="24386-119">TableControl の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="24386-119">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="24386-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="24386-120">Optional element.</span></span><br /><br /> <span data-ttu-id="24386-121">このテーブルビュー定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="24386-121">Specifies a .NET type that uses this table view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="24386-122">親要素</span><span class="sxs-lookup"><span data-stu-id="24386-122">Parent Elements</span></span>

|<span data-ttu-id="24386-123">要素</span><span class="sxs-lookup"><span data-stu-id="24386-123">Element</span></span>|<span data-ttu-id="24386-124">説明</span><span class="sxs-lookup"><span data-stu-id="24386-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="24386-125">TableControl (Format) の TableRowEntry 要素</span><span class="sxs-lookup"><span data-stu-id="24386-125">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="24386-126">テーブルの行に表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="24386-126">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="24386-127">解説</span><span class="sxs-lookup"><span data-stu-id="24386-127">Remarks</span></span>

<span data-ttu-id="24386-128">テーブルビュー定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24386-128">You must specify at least one type, selection set, or selection condition for a table view definition.</span></span> <span data-ttu-id="24386-129">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="24386-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="24386-130">選択条件は、オブジェクトが特定のプロパティを持っている場合や、特定のプロパティ値またはスクリプトがに評価される場合など、使用する定義のために存在する必要がある条件を定義するために使用され `true` ます。</span><span class="sxs-lookup"><span data-stu-id="24386-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="24386-131">選択条件の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24386-131">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="24386-132">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24386-132">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="24386-133">例</span><span class="sxs-lookup"><span data-stu-id="24386-133">Example</span></span>

<span data-ttu-id="24386-134">次の例は、 `TableRowEntry` system.object オブジェクトのプロパティを表示するために使用[System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)される要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="24386-134">The following example shows a `TableRowEntry` element that is used to display the properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="24386-135">参照</span><span class="sxs-lookup"><span data-stu-id="24386-135">See Also</span></span>

[<span data-ttu-id="24386-136">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="24386-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="24386-137">TableControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="24386-137">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="24386-138">TableControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="24386-138">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="24386-139">TableControl (Format) の TableRowEntry 要素</span><span class="sxs-lookup"><span data-stu-id="24386-139">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="24386-140">TableControl の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="24386-140">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="24386-141">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="24386-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
