---
title: ListEntry for ListControl (Format) の EntrySelectedBy 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f7a74e9-764d-46ce-ab8e-8b9314ce1659
caps.latest.revision: 12
ms.openlocfilehash: 442565d25f60ae8e04501f3f9ffba35d486fbc8a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363831"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="7bff8-102">ListControl の ListEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7bff8-102">EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="7bff8-103">このリストビュー定義を使用する .NET 型、またはこの定義を使用するために存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="7bff8-103">Defines the .NET types that use this list view definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="7bff8-104">ほとんどの場合、リストビューに必要な定義は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="7bff8-104">In most cases only one definition is needed for a list view.</span></span> <span data-ttu-id="7bff8-105">ただし、同じリストビューを使用して異なるオブジェクトの異なるデータを表示する場合は、リストビューに複数の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7bff8-105">However, you can provide multiple definitions for the list view if you want to use the same list view to display different data for different objects.</span></span>

<span data-ttu-id="7bff8-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (Format) の ListControl (format) ListEntry 要素の ListEntry for ListControl (Format) エントリの要素の ListEntries 要素ListEntry for ListControl (形式)</span><span class="sxs-lookup"><span data-stu-id="7bff8-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntry for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7bff8-107">構文</span><span class="sxs-lookup"><span data-stu-id="7bff8-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7bff8-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="7bff8-108">Attributes and Elements</span></span>

<span data-ttu-id="7bff8-109">次のセクションでは、`EntrySelectedBy` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7bff8-109">The following sections describe the attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7bff8-110">属性</span><span class="sxs-lookup"><span data-stu-id="7bff8-110">Attributes</span></span>

<span data-ttu-id="7bff8-111">なし。</span><span class="sxs-lookup"><span data-stu-id="7bff8-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7bff8-112">子要素</span><span class="sxs-lookup"><span data-stu-id="7bff8-112">Child Elements</span></span>

|<span data-ttu-id="7bff8-113">要素</span><span class="sxs-lookup"><span data-stu-id="7bff8-113">Element</span></span>|<span data-ttu-id="7bff8-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="7bff8-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7bff8-115">ListControl (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="7bff8-115">SelectionCondition Element for EntrySelectedBy for ListControl  (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="7bff8-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="7bff8-116">Optional element.</span></span><br /><br /> <span data-ttu-id="7bff8-117">このリストビュー定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="7bff8-117">Defines the condition that must exist for this list view definition to be used.</span></span>|
|[<span data-ttu-id="7bff8-118">ListControl (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="7bff8-118">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="7bff8-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="7bff8-119">Optional element.</span></span><br /><br /> <span data-ttu-id="7bff8-120">このリストビュー定義を使用する一連の .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="7bff8-120">Specifies a set of .NET types that use this list view definition.</span></span>|
|[<span data-ttu-id="7bff8-121">ListControl (Format) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="7bff8-121">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="7bff8-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="7bff8-122">Optional element.</span></span><br /><br /> <span data-ttu-id="7bff8-123">このリストビュー定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="7bff8-123">Specifies a .NET type that uses this list view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7bff8-124">親要素</span><span class="sxs-lookup"><span data-stu-id="7bff8-124">Parent Elements</span></span>

|<span data-ttu-id="7bff8-125">要素</span><span class="sxs-lookup"><span data-stu-id="7bff8-125">Element</span></span>|<span data-ttu-id="7bff8-126">[説明]</span><span class="sxs-lookup"><span data-stu-id="7bff8-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7bff8-127">ListControl の ListEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7bff8-127">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="7bff8-128">リストの行をどのように表示するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="7bff8-128">Defines how the rows of the list are displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7bff8-129">コメント</span><span class="sxs-lookup"><span data-stu-id="7bff8-129">Remarks</span></span>

<span data-ttu-id="7bff8-130">リストビュー定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bff8-130">You must specify at least one type, selection set, or selection condition for a list view definition.</span></span> <span data-ttu-id="7bff8-131">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="7bff8-131">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="7bff8-132">選択条件を使用して、オブジェクトに特定のプロパティがある場合や、特定のプロパティ値またはスクリプトが `true`として評価される場合など、使用する定義に存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="7bff8-132">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="7bff8-133">選択条件の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bff8-133">For more information about selection conditions, see [Defining Conditions for when Data is displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="7bff8-134">リストビューのコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bff8-134">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="7bff8-135">例</span><span class="sxs-lookup"><span data-stu-id="7bff8-135">Example</span></span>

<span data-ttu-id="7bff8-136">次の例は、.NET 型名を使用してリストビューのオブジェクトを定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7bff8-136">The following example shows how to define the objects for a list view using their .NET type name.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="7bff8-137">参照</span><span class="sxs-lookup"><span data-stu-id="7bff8-137">See Also</span></span>

[<span data-ttu-id="7bff8-138">ListControl の ListEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7bff8-138">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="7bff8-139">ListControl (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="7bff8-139">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="7bff8-140">ListControl (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="7bff8-140">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="7bff8-141">ListControl (Format) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="7bff8-141">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="7bff8-142">リストビューの作成</span><span class="sxs-lookup"><span data-stu-id="7bff8-142">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="7bff8-143">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="7bff8-143">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="7bff8-144">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="7bff8-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
