---
ms.date: 09/13/2016
ms.topic: reference
title: View の CustomControl の CustomEntry の EntrySelectedBy 要素 (書式)
description: View の CustomControl の CustomEntry の EntrySelectedBy 要素 (書式)
ms.openlocfilehash: 4821f22560f35034f90d018e5a109004f331441f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655342"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="a54f3-103">View の CustomControl の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a54f3-103">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="a54f3-104">このカスタムエントリを使用する .NET 型、またはこのエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="a54f3-104">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>

<span data-ttu-id="a54f3-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) CustomControl 要素 (形式) の CustomEntries for CustomControl for view (format) の CustomEntry 要素を使用して、CustomEntry for ビューの EntrySelectedBy 要素を表示 (形式) します。</span><span class="sxs-lookup"><span data-stu-id="a54f3-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a54f3-106">構文</span><span class="sxs-lookup"><span data-stu-id="a54f3-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a54f3-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a54f3-107">Attributes and Elements</span></span>

<span data-ttu-id="a54f3-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `EntrySelectedBy` ます。</span><span class="sxs-lookup"><span data-stu-id="a54f3-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a54f3-109">属性</span><span class="sxs-lookup"><span data-stu-id="a54f3-109">Attributes</span></span>

<span data-ttu-id="a54f3-110">なし。</span><span class="sxs-lookup"><span data-stu-id="a54f3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a54f3-111">子要素</span><span class="sxs-lookup"><span data-stu-id="a54f3-111">Child Elements</span></span>

|<span data-ttu-id="a54f3-112">要素</span><span class="sxs-lookup"><span data-stu-id="a54f3-112">Element</span></span>|<span data-ttu-id="a54f3-113">説明</span><span class="sxs-lookup"><span data-stu-id="a54f3-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a54f3-114">CustomEntry (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="a54f3-114">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="a54f3-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a54f3-115">Optional element.</span></span><br /><br /> <span data-ttu-id="a54f3-116">この定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="a54f3-116">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="a54f3-117">CustomEntry (形式) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="a54f3-117">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|<span data-ttu-id="a54f3-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a54f3-118">Optional element.</span></span><br /><br /> <span data-ttu-id="a54f3-119">コントロールビューのこの定義を使用する .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="a54f3-119">Specifies a set of .NET types that use this definition of the control view.</span></span>|
|[<span data-ttu-id="a54f3-120">CustomEntry (形式) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="a54f3-120">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="a54f3-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a54f3-121">Optional element.</span></span><br /><br /> <span data-ttu-id="a54f3-122">コントロールビューのこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="a54f3-122">Specifies a .NET type that uses this definition of the control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a54f3-123">親要素</span><span class="sxs-lookup"><span data-stu-id="a54f3-123">Parent Elements</span></span>

|<span data-ttu-id="a54f3-124">要素</span><span class="sxs-lookup"><span data-stu-id="a54f3-124">Element</span></span>|<span data-ttu-id="a54f3-125">説明</span><span class="sxs-lookup"><span data-stu-id="a54f3-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a54f3-126">View (Format) の CustomEntries の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="a54f3-126">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="a54f3-127">特定の .NET オブジェクトで使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="a54f3-127">Defines the controls used by specific .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a54f3-128">解説</span><span class="sxs-lookup"><span data-stu-id="a54f3-128">Remarks</span></span>

<span data-ttu-id="a54f3-129">エントリの種類、選択セット、または選択条件を少なくとも1つ指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a54f3-129">You must specify at least one type, selection set, or selection condition for an entry.</span></span> <span data-ttu-id="a54f3-130">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="a54f3-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="a54f3-131">選択条件は、オブジェクトに特定のプロパティがある場合や、特定のプロパティ値またはスクリプトがに評価される場合など、エントリの使用に必要な条件を定義するために使用し `true` ます。</span><span class="sxs-lookup"><span data-stu-id="a54f3-131">Selection conditions are used to define a condition that must exist for the entry to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="a54f3-132">選択条件の詳細については、「 [ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a54f3-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="a54f3-133">カスタムコントロールビューのコンポーネントの詳細については、「 [カスタムコントロールビュー](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a54f3-133">For more information about the components of a custom control view, see [Custom Control View](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a54f3-134">参照</span><span class="sxs-lookup"><span data-stu-id="a54f3-134">See Also</span></span>

[<span data-ttu-id="a54f3-135">CustomEntry (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="a54f3-135">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="a54f3-136">CustomEntry (形式) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="a54f3-136">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a54f3-137">CustomEntry (形式) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="a54f3-137">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a54f3-138">View (Format) の CustomEntries の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="a54f3-138">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a54f3-139">カスタムコントロールビュー</span><span class="sxs-lookup"><span data-stu-id="a54f3-139">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="a54f3-140">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="a54f3-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
