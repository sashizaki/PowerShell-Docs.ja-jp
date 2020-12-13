---
ms.date: 09/13/2016
ms.topic: reference
title: ListControl の ListEntry の EntrySelectedBy 要素 (書式)
description: ListControl の ListEntry の EntrySelectedBy 要素 (書式)
ms.openlocfilehash: 1981c8fae65f494504d6cdd9f59337d555350b07
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652289"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="4fbff-103">ListControl の ListEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4fbff-103">EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="4fbff-104">このリストビュー定義を使用する .NET 型、またはこの定義を使用するために存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="4fbff-104">Defines the .NET types that use this list view definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="4fbff-105">ほとんどの場合、リストビューに必要な定義は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="4fbff-105">In most cases only one definition is needed for a list view.</span></span> <span data-ttu-id="4fbff-106">ただし、同じリストビューを使用して異なるオブジェクトの異なるデータを表示する場合は、リストビューに複数の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4fbff-106">However, you can provide multiple definitions for the list view if you want to use the same list view to display different data for different objects.</span></span>

<span data-ttu-id="4fbff-107">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (Format) ListEntries 要素の ListControl (format) ListEntry 要素の ListEntry for ListControl (Format) の要素を ListEntry for ListControl (format) に渡します。</span><span class="sxs-lookup"><span data-stu-id="4fbff-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntry for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4fbff-108">構文</span><span class="sxs-lookup"><span data-stu-id="4fbff-108">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4fbff-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4fbff-109">Attributes and Elements</span></span>

<span data-ttu-id="4fbff-110">次のセクションでは、要素の属性、子要素、および親要素について説明し `EntrySelectedBy` ます。</span><span class="sxs-lookup"><span data-stu-id="4fbff-110">The following sections describe the attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4fbff-111">属性</span><span class="sxs-lookup"><span data-stu-id="4fbff-111">Attributes</span></span>

<span data-ttu-id="4fbff-112">なし。</span><span class="sxs-lookup"><span data-stu-id="4fbff-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4fbff-113">子要素</span><span class="sxs-lookup"><span data-stu-id="4fbff-113">Child Elements</span></span>

|<span data-ttu-id="4fbff-114">要素</span><span class="sxs-lookup"><span data-stu-id="4fbff-114">Element</span></span>|<span data-ttu-id="4fbff-115">説明</span><span class="sxs-lookup"><span data-stu-id="4fbff-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4fbff-116">ListControl (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="4fbff-116">SelectionCondition Element for EntrySelectedBy for ListControl  (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="4fbff-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4fbff-117">Optional element.</span></span><br /><br /> <span data-ttu-id="4fbff-118">このリストビュー定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="4fbff-118">Defines the condition that must exist for this list view definition to be used.</span></span>|
|[<span data-ttu-id="4fbff-119">ListControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4fbff-119">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="4fbff-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4fbff-120">Optional element.</span></span><br /><br /> <span data-ttu-id="4fbff-121">このリストビュー定義を使用する一連の .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="4fbff-121">Specifies a set of .NET types that use this list view definition.</span></span>|
|[<span data-ttu-id="4fbff-122">ListControl の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4fbff-122">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="4fbff-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4fbff-123">Optional element.</span></span><br /><br /> <span data-ttu-id="4fbff-124">このリストビュー定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="4fbff-124">Specifies a .NET type that uses this list view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4fbff-125">親要素</span><span class="sxs-lookup"><span data-stu-id="4fbff-125">Parent Elements</span></span>

|<span data-ttu-id="4fbff-126">要素</span><span class="sxs-lookup"><span data-stu-id="4fbff-126">Element</span></span>|<span data-ttu-id="4fbff-127">説明</span><span class="sxs-lookup"><span data-stu-id="4fbff-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4fbff-128">ListControl の ListEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4fbff-128">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="4fbff-129">リストの行をどのように表示するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="4fbff-129">Defines how the rows of the list are displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4fbff-130">解説</span><span class="sxs-lookup"><span data-stu-id="4fbff-130">Remarks</span></span>

<span data-ttu-id="4fbff-131">リストビュー定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fbff-131">You must specify at least one type, selection set, or selection condition for a list view definition.</span></span> <span data-ttu-id="4fbff-132">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="4fbff-132">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="4fbff-133">選択条件は、オブジェクトが特定のプロパティを持っている場合や、特定のプロパティ値またはスクリプトがに評価される場合など、使用する定義のために存在する必要がある条件を定義するために使用され `true` ます。</span><span class="sxs-lookup"><span data-stu-id="4fbff-133">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="4fbff-134">選択条件の詳細については、「 [データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fbff-134">For more information about selection conditions, see [Defining Conditions for when Data is displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="4fbff-135">リストビューのコンポーネントの詳細については、「 [リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fbff-135">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="4fbff-136">例</span><span class="sxs-lookup"><span data-stu-id="4fbff-136">Example</span></span>

<span data-ttu-id="4fbff-137">次の例は、.NET 型名を使用してリストビューのオブジェクトを定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4fbff-137">The following example shows how to define the objects for a list view using their .NET type name.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="4fbff-138">参照</span><span class="sxs-lookup"><span data-stu-id="4fbff-138">See Also</span></span>

[<span data-ttu-id="4fbff-139">ListControl の ListEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4fbff-139">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="4fbff-140">ListControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4fbff-140">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="4fbff-141">ListControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4fbff-141">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="4fbff-142">ListControl の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4fbff-142">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="4fbff-143">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="4fbff-143">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="4fbff-144">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="4fbff-144">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="4fbff-145">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="4fbff-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
