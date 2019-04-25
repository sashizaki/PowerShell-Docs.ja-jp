---
title: TableControl (形式) の TableRowEntry EntrySelectedBy 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49623fcf-1238-4d20-a7ce-238d47d9d565
caps.latest.revision: 15
ms.openlocfilehash: 9302bfed0324773cb98d698acdcf608f34ee19c1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066160"
---
# <a name="entryselectedby-element-for-tablerowentry--for-tablecontrol-format"></a><span data-ttu-id="a1255-102">TableControl の TableRowEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a1255-102">EntrySelectedBy Element for TableRowEntry  for TableControl (Format)</span></span>

<span data-ttu-id="a1255-103">この定義のテーブル ビューまたは条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="a1255-103">Defines the .NET types that use this definition of the table view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="a1255-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素 (形式) TableRowEntry 要素 (形式) EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a1255-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a1255-105">構文</span><span class="sxs-lookup"><span data-stu-id="a1255-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a1255-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a1255-106">Attributes and Elements</span></span>

<span data-ttu-id="a1255-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`EntrySelectedBy`要素。</span><span class="sxs-lookup"><span data-stu-id="a1255-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a1255-108">属性</span><span class="sxs-lookup"><span data-stu-id="a1255-108">Attributes</span></span>

<span data-ttu-id="a1255-109">なし。</span><span class="sxs-lookup"><span data-stu-id="a1255-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a1255-110">子要素</span><span class="sxs-lookup"><span data-stu-id="a1255-110">Child Elements</span></span>

|<span data-ttu-id="a1255-111">要素</span><span class="sxs-lookup"><span data-stu-id="a1255-111">Element</span></span>|<span data-ttu-id="a1255-112">説明</span><span class="sxs-lookup"><span data-stu-id="a1255-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a1255-113">TableControl (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="a1255-113">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="a1255-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a1255-114">Optional element.</span></span><br /><br /> <span data-ttu-id="a1255-115">このテーブルのビュー定義に使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="a1255-115">Defines the condition that must exist for this table view definition to be used.</span></span>|
|[<span data-ttu-id="a1255-116">TableControl (形式) の EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="a1255-116">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="a1255-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a1255-117">Optional element.</span></span><br /><br /> <span data-ttu-id="a1255-118">このテーブルのビュー定義を使用して .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1255-118">Specifies a set of .NET types that use this table view definition.</span></span>|
|[<span data-ttu-id="a1255-119">TableControl (形式) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="a1255-119">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="a1255-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a1255-120">Optional element.</span></span><br /><br /> <span data-ttu-id="a1255-121">このテーブルのビュー定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1255-121">Specifies a .NET type that uses this table view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a1255-122">親要素</span><span class="sxs-lookup"><span data-stu-id="a1255-122">Parent Elements</span></span>

|<span data-ttu-id="a1255-123">要素</span><span class="sxs-lookup"><span data-stu-id="a1255-123">Element</span></span>|<span data-ttu-id="a1255-124">説明</span><span class="sxs-lookup"><span data-stu-id="a1255-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a1255-125">TableControl (形式) の TableRowEntry 要素</span><span class="sxs-lookup"><span data-stu-id="a1255-125">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="a1255-126">テーブルの行に表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="a1255-126">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a1255-127">コメント</span><span class="sxs-lookup"><span data-stu-id="a1255-127">Remarks</span></span>

<span data-ttu-id="a1255-128">少なくとも 1 つの型、選択範囲のセット、またはテーブル ビューの定義の選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1255-128">You must specify at least one type, selection set, or selection condition for a table view definition.</span></span> <span data-ttu-id="a1255-129">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="a1255-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="a1255-130">選択条件を使用して、定義オブジェクトに特定のプロパティがある場合など、使用するのに必要な条件を定義または特定のプロパティの値またはスクリプトに評価される`true`します。</span><span class="sxs-lookup"><span data-stu-id="a1255-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="a1255-131">選択条件の詳細については、次を参照してください。[とビューのエントリの定義の条件またはアイテムが使用されて](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="a1255-131">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="a1255-132">テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="a1255-132">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a1255-133">例</span><span class="sxs-lookup"><span data-stu-id="a1255-133">Example</span></span>

<span data-ttu-id="a1255-134">次の例は、`TableRowEntry`要素のプロパティを表示するために使用される、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a1255-134">The following example shows a `TableRowEntry` element that is used to display the properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a1255-135">参照</span><span class="sxs-lookup"><span data-stu-id="a1255-135">See Also</span></span>

[<span data-ttu-id="a1255-136">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="a1255-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="a1255-137">TableControl (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="a1255-137">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="a1255-138">TableControl (形式) の EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="a1255-138">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="a1255-139">TableControl (形式) の TableRowEntry 要素</span><span class="sxs-lookup"><span data-stu-id="a1255-139">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="a1255-140">TableControl (形式) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="a1255-140">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="a1255-141">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="a1255-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
