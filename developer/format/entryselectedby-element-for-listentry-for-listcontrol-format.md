---
title: ListControl (形式) の ListEntry EntrySelectedBy 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f7a74e9-764d-46ce-ab8e-8b9314ce1659
caps.latest.revision: 12
ms.openlocfilehash: 442565d25f60ae8e04501f3f9ffba35d486fbc8a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066194"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="e209a-102">ListControl の ListEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e209a-102">EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="e209a-103">このリスト ビューの定義を使用する .NET 型または条件を使用するには、この定義が存在する必要がありますを定義します。</span><span class="sxs-lookup"><span data-stu-id="e209a-103">Defines the .NET types that use this list view definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="e209a-104">ほとんどの場合は、リスト ビューの 1 つだけ定義が必要です。</span><span class="sxs-lookup"><span data-stu-id="e209a-104">In most cases only one definition is needed for a list view.</span></span> <span data-ttu-id="e209a-105">ただし、さまざまなオブジェクトのさまざまなデータを表示する同じリスト ビューを使用する場合は、リスト ビューの複数の定義を提供できます。</span><span class="sxs-lookup"><span data-stu-id="e209a-105">However, you can provide multiple definitions for the list view if you want to use the same list view to display different data for different objects.</span></span>

<span data-ttu-id="e209a-106">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素の要素に ListControl (形式) ListEntry ListEntry の ListControl (形式) EntrySelectedBy 要素のListEntry ListControl (形式) の</span><span class="sxs-lookup"><span data-stu-id="e209a-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntry for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e209a-107">構文</span><span class="sxs-lookup"><span data-stu-id="e209a-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e209a-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e209a-108">Attributes and Elements</span></span>

<span data-ttu-id="e209a-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`EntrySelectedBy`要素。</span><span class="sxs-lookup"><span data-stu-id="e209a-109">The following sections describe the attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e209a-110">属性</span><span class="sxs-lookup"><span data-stu-id="e209a-110">Attributes</span></span>

<span data-ttu-id="e209a-111">なし。</span><span class="sxs-lookup"><span data-stu-id="e209a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e209a-112">子要素</span><span class="sxs-lookup"><span data-stu-id="e209a-112">Child Elements</span></span>

|<span data-ttu-id="e209a-113">要素</span><span class="sxs-lookup"><span data-stu-id="e209a-113">Element</span></span>|<span data-ttu-id="e209a-114">説明</span><span class="sxs-lookup"><span data-stu-id="e209a-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e209a-115">ListControl (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="e209a-115">SelectionCondition Element for EntrySelectedBy for ListControl  (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="e209a-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e209a-116">Optional element.</span></span><br /><br /> <span data-ttu-id="e209a-117">このリスト ビューの定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="e209a-117">Defines the condition that must exist for this list view definition to be used.</span></span>|
|[<span data-ttu-id="e209a-118">ListControl (形式) の EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="e209a-118">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="e209a-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e209a-119">Optional element.</span></span><br /><br /> <span data-ttu-id="e209a-120">このリスト ビューの定義を使用して .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="e209a-120">Specifies a set of .NET types that use this list view definition.</span></span>|
|[<span data-ttu-id="e209a-121">EntrySelectedBy ListControl (形式) 用の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="e209a-121">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="e209a-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e209a-122">Optional element.</span></span><br /><br /> <span data-ttu-id="e209a-123">このリスト ビューの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="e209a-123">Specifies a .NET type that uses this list view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e209a-124">親要素</span><span class="sxs-lookup"><span data-stu-id="e209a-124">Parent Elements</span></span>

|<span data-ttu-id="e209a-125">要素</span><span class="sxs-lookup"><span data-stu-id="e209a-125">Element</span></span>|<span data-ttu-id="e209a-126">説明</span><span class="sxs-lookup"><span data-stu-id="e209a-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e209a-127">ListControl (形式) の ListEntry 要素</span><span class="sxs-lookup"><span data-stu-id="e209a-127">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="e209a-128">一覧の行を表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="e209a-128">Defines how the rows of the list are displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e209a-129">コメント</span><span class="sxs-lookup"><span data-stu-id="e209a-129">Remarks</span></span>

<span data-ttu-id="e209a-130">少なくとも 1 つの型、選択範囲のセット、またはリスト ビューの定義の選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e209a-130">You must specify at least one type, selection set, or selection condition for a list view definition.</span></span> <span data-ttu-id="e209a-131">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="e209a-131">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="e209a-132">選択条件を使用して、定義オブジェクトに特定のプロパティがある場合など、使用するのに必要な条件を定義または特定のプロパティの値またはスクリプトに評価される`true`します。</span><span class="sxs-lookup"><span data-stu-id="e209a-132">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="e209a-133">選択条件の詳細については、次を参照してください。[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="e209a-133">For more information about selection conditions, see [Defining Conditions for when Data is displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="e209a-134">リスト ビューのコンポーネントに関する詳細については、次を参照してください。[リスト ビューを作成する](./creating-a-list-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="e209a-134">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e209a-135">例</span><span class="sxs-lookup"><span data-stu-id="e209a-135">Example</span></span>

<span data-ttu-id="e209a-136">次の例では、その .NET 型名を使用してリスト ビューのオブジェクトを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e209a-136">The following example shows how to define the objects for a list view using their .NET type name.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="e209a-137">参照</span><span class="sxs-lookup"><span data-stu-id="e209a-137">See Also</span></span>

[<span data-ttu-id="e209a-138">ListControl (形式) の ListEntry 要素</span><span class="sxs-lookup"><span data-stu-id="e209a-138">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="e209a-139">ListControl (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="e209a-139">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="e209a-140">ListControl (形式) の EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="e209a-140">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="e209a-141">EntrySelectedBy ListControl (形式) 用の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="e209a-141">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="e209a-142">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="e209a-142">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="e209a-143">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="e209a-143">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="e209a-144">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="e209a-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
