---
title: TableControl (形式) の EntrySelectedBy SelectionCondition 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 912f3e63-e4d5-41ce-8710-6dfd8c885dc2
caps.latest.revision: 12
ms.openlocfilehash: 2faca6021dc26878869bdd2d35bc4ffc64d0fe7b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861238"
---
# <a name="selectioncondition-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="dd799-102">TableControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="dd799-102">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="dd799-103">テーブル ビューのこの定義に使用する必要があります条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="dd799-103">Defines the condition that must exist to use for this definition of the table view.</span></span> <span data-ttu-id="dd799-104">テーブルの定義に指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="dd799-104">There is no limit to the number of selection conditions that can be specified for a table definition.</span></span>

<span data-ttu-id="dd799-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素 (形式) TableRowEntry 要素 (形式) EntrySelectedBy 要素を TableRowEntry (形式)TableRowEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="dd799-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dd799-106">構文</span><span class="sxs-lookup"><span data-stu-id="dd799-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dd799-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="dd799-107">Attributes and Elements</span></span>

<span data-ttu-id="dd799-108">次のセクションでは、属性、子要素、および SelectionCondition 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd799-108">The following sections describe attributes, child elements, and the parent element of the SelectionCondition element.</span></span>

### <a name="attributes"></a><span data-ttu-id="dd799-109">属性</span><span class="sxs-lookup"><span data-stu-id="dd799-109">Attributes</span></span>

<span data-ttu-id="dd799-110">なし。</span><span class="sxs-lookup"><span data-stu-id="dd799-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dd799-111">子要素</span><span class="sxs-lookup"><span data-stu-id="dd799-111">Child Elements</span></span>

|<span data-ttu-id="dd799-112">要素</span><span class="sxs-lookup"><span data-stu-id="dd799-112">Element</span></span>|<span data-ttu-id="dd799-113">説明</span><span class="sxs-lookup"><span data-stu-id="dd799-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dd799-114">SelectionCondition EntrySelectedBy TableRowEntry (形式) のための PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="dd799-114">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)|<span data-ttu-id="dd799-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="dd799-115">Optional element.</span></span><br /><br /> <span data-ttu-id="dd799-116">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="dd799-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="dd799-117">SelectionCondition EntrySelectedBy TableRowEntry (形式) のためのスクリプト ブロックの要素</span><span class="sxs-lookup"><span data-stu-id="dd799-117">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="dd799-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="dd799-118">Optional element.</span></span><br /><br /> <span data-ttu-id="dd799-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="dd799-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="dd799-120">EntrySelectedBy TableRowEntry (形式) 用の SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="dd799-120">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="dd799-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="dd799-121">Optional element.</span></span><br /><br /> <span data-ttu-id="dd799-122">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="dd799-122">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="dd799-123">SelectionCondition EntrySelectedBy TableRowEntry (形式) のための TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="dd799-123">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="dd799-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="dd799-124">Optional element.</span></span><br /><br /> <span data-ttu-id="dd799-125">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd799-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="dd799-126">親要素</span><span class="sxs-lookup"><span data-stu-id="dd799-126">Parent Elements</span></span>

|<span data-ttu-id="dd799-127">要素</span><span class="sxs-lookup"><span data-stu-id="dd799-127">Element</span></span>|<span data-ttu-id="dd799-128">説明</span><span class="sxs-lookup"><span data-stu-id="dd799-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dd799-129">TableRowEntry (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="dd799-129">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="dd799-130">このテーブルのエントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="dd799-130">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="dd799-131">コメント</span><span class="sxs-lookup"><span data-stu-id="dd799-131">Remarks</span></span>

<span data-ttu-id="dd799-132">リストの各エントリに少なくとも 1 つの型名、選択範囲のセット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd799-132">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="dd799-133">選択条件を定義している場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="dd799-133">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="dd799-134">選択条件では、少なくとも 1 つのプロパティ名またはスクリプト ブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="dd799-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="dd799-135">選択条件が .NET 型の任意の数を指定するか、選択範囲を設定するが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="dd799-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="dd799-136">選択条件を使用する方法の詳細については、次を参照してください。[とビューのエントリの定義の条件またはアイテムが使用されて](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="dd799-136">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="dd799-137">テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="dd799-137">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dd799-138">参照</span><span class="sxs-lookup"><span data-stu-id="dd799-138">See Also</span></span>

[<span data-ttu-id="dd799-139">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd799-139">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="dd799-140">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="dd799-140">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="dd799-141">EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="dd799-141">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="dd799-142">SelectionCondition EntrySelectedBy TableRowEntry (形式) のための PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="dd799-142">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="dd799-143">SelectionCondition EntrySelectedBy TableRowEntry (形式) のためのスクリプト ブロックの要素</span><span class="sxs-lookup"><span data-stu-id="dd799-143">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="dd799-144">EntrySelectedBy TableRowEntry (形式) 用の SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="dd799-144">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="dd799-145">SelectionCondition EntrySelectedBy TableRowEntry (形式) のための TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="dd799-145">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="dd799-146">Windows PowerShell の書式設定の書き込みとファイルの種類</span><span class="sxs-lookup"><span data-stu-id="dd799-146">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
