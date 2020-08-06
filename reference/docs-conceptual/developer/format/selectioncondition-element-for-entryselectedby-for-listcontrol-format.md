---
title: ListControl (Format) の EntrySelectedBy の SelectionCondition 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 29626b181f21d168e1ebf973e01afeb411d9ef54
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772775"
---
# <a name="selectioncondition-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="c31b6-102">ListControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c31b6-102">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="c31b6-103">リストビューのこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="c31b6-103">Defines the condition that must exist to use this definition of the list view.</span></span> <span data-ttu-id="c31b6-104">リスト定義に指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="c31b6-104">There is no limit to the number of selection conditions that can be specified for a list definition.</span></span>

<span data-ttu-id="c31b6-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries Element (format) ListEntry Element (format) ListEntry (Format) の SelectionCondition 要素 for ListEntry (Format) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="c31b6-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c31b6-106">構文</span><span class="sxs-lookup"><span data-stu-id="c31b6-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c31b6-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c31b6-107">Attributes and Elements</span></span>

<span data-ttu-id="c31b6-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="c31b6-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c31b6-109">属性</span><span class="sxs-lookup"><span data-stu-id="c31b6-109">Attributes</span></span>

<span data-ttu-id="c31b6-110">なし。</span><span class="sxs-lookup"><span data-stu-id="c31b6-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c31b6-111">子要素</span><span class="sxs-lookup"><span data-stu-id="c31b6-111">Child Elements</span></span>

|<span data-ttu-id="c31b6-112">要素</span><span class="sxs-lookup"><span data-stu-id="c31b6-112">Element</span></span>|<span data-ttu-id="c31b6-113">説明</span><span class="sxs-lookup"><span data-stu-id="c31b6-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c31b6-114">ListEntry (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="c31b6-114">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="c31b6-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c31b6-115">Optional element.</span></span><br /><br /> <span data-ttu-id="c31b6-116">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="c31b6-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="c31b6-117">ListEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="c31b6-117">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="c31b6-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c31b6-118">Optional element.</span></span><br /><br /> <span data-ttu-id="c31b6-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c31b6-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="c31b6-120">ListEntry の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c31b6-120">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)|<span data-ttu-id="c31b6-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c31b6-121">Optional element.</span></span><br /><br /> <span data-ttu-id="c31b6-122">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="c31b6-122">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="c31b6-123">ListEntry (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="c31b6-123">TypeName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="c31b6-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c31b6-124">Optional element.</span></span><br /><br /> <span data-ttu-id="c31b6-125">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="c31b6-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c31b6-126">親要素</span><span class="sxs-lookup"><span data-stu-id="c31b6-126">Parent Elements</span></span>

|<span data-ttu-id="c31b6-127">要素</span><span class="sxs-lookup"><span data-stu-id="c31b6-127">Element</span></span>|<span data-ttu-id="c31b6-128">説明</span><span class="sxs-lookup"><span data-stu-id="c31b6-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c31b6-129">TableRowEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c31b6-129">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="c31b6-130">このテーブルエントリを使用する .NET 型、またはこのエントリを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="c31b6-130">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c31b6-131">解説</span><span class="sxs-lookup"><span data-stu-id="c31b6-131">Remarks</span></span>

<span data-ttu-id="c31b6-132">選択条件を定義する場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c31b6-132">lWhen you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="c31b6-133">選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c31b6-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="c31b6-134">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c31b6-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="c31b6-135">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c31b6-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="c31b6-136">リストビューのその他のコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c31b6-136">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c31b6-137">参照</span><span class="sxs-lookup"><span data-stu-id="c31b6-137">See Also</span></span>

[<span data-ttu-id="c31b6-138">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="c31b6-138">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="c31b6-139">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="c31b6-139">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="c31b6-140">ListEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c31b6-140">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="c31b6-141">ListEntry (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="c31b6-141">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="c31b6-142">ListEntry (Format) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="c31b6-142">TypeName Element for EntrySelectedBy for ListEntry (Format)</span></span>](/powershell/scripting/developer/format/typename-element-for-entryselectedby-for-listcontrol-format)

[<span data-ttu-id="c31b6-143">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="c31b6-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
