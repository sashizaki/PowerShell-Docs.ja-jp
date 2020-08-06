---
title: ListEntry for ListControl (Format) の EntrySelectedBy 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: d6ab1c08dd353da74d1a7d27c569d2fa86e083c3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774118"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="64d60-102">ListControl の ListEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="64d60-102">EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="64d60-103">このリストビュー定義を使用する .NET 型、またはこの定義を使用するために存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="64d60-103">Defines the .NET types that use this list view definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="64d60-104">ほとんどの場合、リストビューに必要な定義は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="64d60-104">In most cases only one definition is needed for a list view.</span></span> <span data-ttu-id="64d60-105">ただし、同じリストビューを使用して異なるオブジェクトの異なるデータを表示する場合は、リストビューに複数の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="64d60-105">However, you can provide multiple definitions for the list view if you want to use the same list view to display different data for different objects.</span></span>

<span data-ttu-id="64d60-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (Format) ListEntries 要素の ListControl (format) ListEntry 要素の ListEntry for ListControl (Format) の要素を ListEntry for ListControl (format) に渡します。</span><span class="sxs-lookup"><span data-stu-id="64d60-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntry for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="64d60-107">構文</span><span class="sxs-lookup"><span data-stu-id="64d60-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="64d60-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="64d60-108">Attributes and Elements</span></span>

<span data-ttu-id="64d60-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `EntrySelectedBy` ます。</span><span class="sxs-lookup"><span data-stu-id="64d60-109">The following sections describe the attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="64d60-110">属性</span><span class="sxs-lookup"><span data-stu-id="64d60-110">Attributes</span></span>

<span data-ttu-id="64d60-111">なし。</span><span class="sxs-lookup"><span data-stu-id="64d60-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="64d60-112">子要素</span><span class="sxs-lookup"><span data-stu-id="64d60-112">Child Elements</span></span>

|<span data-ttu-id="64d60-113">要素</span><span class="sxs-lookup"><span data-stu-id="64d60-113">Element</span></span>|<span data-ttu-id="64d60-114">説明</span><span class="sxs-lookup"><span data-stu-id="64d60-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="64d60-115">ListControl (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="64d60-115">SelectionCondition Element for EntrySelectedBy for ListControl  (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="64d60-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="64d60-116">Optional element.</span></span><br /><br /> <span data-ttu-id="64d60-117">このリストビュー定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="64d60-117">Defines the condition that must exist for this list view definition to be used.</span></span>|
|[<span data-ttu-id="64d60-118">ListControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="64d60-118">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="64d60-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="64d60-119">Optional element.</span></span><br /><br /> <span data-ttu-id="64d60-120">このリストビュー定義を使用する一連の .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="64d60-120">Specifies a set of .NET types that use this list view definition.</span></span>|
|[<span data-ttu-id="64d60-121">ListControl の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="64d60-121">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="64d60-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="64d60-122">Optional element.</span></span><br /><br /> <span data-ttu-id="64d60-123">このリストビュー定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="64d60-123">Specifies a .NET type that uses this list view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="64d60-124">親要素</span><span class="sxs-lookup"><span data-stu-id="64d60-124">Parent Elements</span></span>

|<span data-ttu-id="64d60-125">要素</span><span class="sxs-lookup"><span data-stu-id="64d60-125">Element</span></span>|<span data-ttu-id="64d60-126">説明</span><span class="sxs-lookup"><span data-stu-id="64d60-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="64d60-127">ListControl の ListEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="64d60-127">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="64d60-128">リストの行をどのように表示するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="64d60-128">Defines how the rows of the list are displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="64d60-129">解説</span><span class="sxs-lookup"><span data-stu-id="64d60-129">Remarks</span></span>

<span data-ttu-id="64d60-130">リストビュー定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64d60-130">You must specify at least one type, selection set, or selection condition for a list view definition.</span></span> <span data-ttu-id="64d60-131">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="64d60-131">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="64d60-132">選択条件は、オブジェクトが特定のプロパティを持っている場合や、特定のプロパティ値またはスクリプトがに評価される場合など、使用する定義のために存在する必要がある条件を定義するために使用され `true` ます。</span><span class="sxs-lookup"><span data-stu-id="64d60-132">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="64d60-133">選択条件の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64d60-133">For more information about selection conditions, see [Defining Conditions for when Data is displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="64d60-134">リストビューのコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64d60-134">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="64d60-135">例</span><span class="sxs-lookup"><span data-stu-id="64d60-135">Example</span></span>

<span data-ttu-id="64d60-136">次の例は、.NET 型名を使用してリストビューのオブジェクトを定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="64d60-136">The following example shows how to define the objects for a list view using their .NET type name.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="64d60-137">参照</span><span class="sxs-lookup"><span data-stu-id="64d60-137">See Also</span></span>

[<span data-ttu-id="64d60-138">ListControl の ListEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="64d60-138">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="64d60-139">ListControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="64d60-139">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="64d60-140">ListControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="64d60-140">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="64d60-141">ListControl の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="64d60-141">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="64d60-142">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="64d60-142">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="64d60-143">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="64d60-143">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="64d60-144">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="64d60-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
