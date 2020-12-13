---
ms.date: 09/13/2016
ms.topic: reference
title: WideEntry の EntrySelectedBy 要素 (書式)
description: WideEntry の EntrySelectedBy 要素 (書式)
ms.openlocfilehash: 246a1967300ab0551f376c4799deac275068308c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660239"
---
# <a name="entryselectedby-element-for-wideentry-format"></a><span data-ttu-id="6ee35-103">WideEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6ee35-103">EntrySelectedBy Element for WideEntry (Format)</span></span>

<span data-ttu-id="6ee35-104">ワイドビューのこの定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="6ee35-104">Defines the .NET types that use this definition of the wide view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="6ee35-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideEntry (Format) の要素 (format)</span><span class="sxs-lookup"><span data-stu-id="6ee35-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6ee35-106">構文</span><span class="sxs-lookup"><span data-stu-id="6ee35-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6ee35-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6ee35-107">Attributes and Elements</span></span>

<span data-ttu-id="6ee35-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `EntrySelectedBy` ます。</span><span class="sxs-lookup"><span data-stu-id="6ee35-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6ee35-109">属性</span><span class="sxs-lookup"><span data-stu-id="6ee35-109">Attributes</span></span>

<span data-ttu-id="6ee35-110">なし。</span><span class="sxs-lookup"><span data-stu-id="6ee35-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6ee35-111">子要素</span><span class="sxs-lookup"><span data-stu-id="6ee35-111">Child Elements</span></span>

|<span data-ttu-id="6ee35-112">要素</span><span class="sxs-lookup"><span data-stu-id="6ee35-112">Element</span></span>|<span data-ttu-id="6ee35-113">説明</span><span class="sxs-lookup"><span data-stu-id="6ee35-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6ee35-114">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="6ee35-114">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="6ee35-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="6ee35-115">Optional element.</span></span><br /><br /> <span data-ttu-id="6ee35-116">このワイドビュー定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="6ee35-116">Defines the condition that must exist for this wide view definition to be used.</span></span>|
|[<span data-ttu-id="6ee35-117">WideEntry (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="6ee35-117">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="6ee35-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="6ee35-118">Optional element.</span></span><br /><br /> <span data-ttu-id="6ee35-119">このワイドビュー定義を使用する一連の .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="6ee35-119">Specifies a set of .NET types that use this wide view definition.</span></span>|
|[<span data-ttu-id="6ee35-120">WideEntry の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6ee35-120">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="6ee35-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="6ee35-121">Optional element.</span></span><br /><br /> <span data-ttu-id="6ee35-122">このワイドビュー定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="6ee35-122">Specifies a .NET type that uses this wide view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6ee35-123">親要素</span><span class="sxs-lookup"><span data-stu-id="6ee35-123">Parent Elements</span></span>

|<span data-ttu-id="6ee35-124">要素</span><span class="sxs-lookup"><span data-stu-id="6ee35-124">Element</span></span>|<span data-ttu-id="6ee35-125">説明</span><span class="sxs-lookup"><span data-stu-id="6ee35-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6ee35-126">WideEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="6ee35-126">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="6ee35-127">ワイドビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="6ee35-127">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6ee35-128">解説</span><span class="sxs-lookup"><span data-stu-id="6ee35-128">Remarks</span></span>

<span data-ttu-id="6ee35-129">ワイドビュー定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ee35-129">You must specify at least one type, selection set, or selection condition for a wide view definition.</span></span> <span data-ttu-id="6ee35-130">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="6ee35-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="6ee35-131">選択条件は、オブジェクトに特定のプロパティがある場合や、特定のプロパティ値またはスクリプト値がに評価される場合など、使用する定義のために存在する必要がある条件を定義するために使用され `true` ます。</span><span class="sxs-lookup"><span data-stu-id="6ee35-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script value evaluates to `true`.</span></span> <span data-ttu-id="6ee35-132">選択条件の詳細については、「 [データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ee35-132">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="6ee35-133">ワイドビューのその他のコンポーネントの詳細については、「 [ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ee35-133">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6ee35-134">参照</span><span class="sxs-lookup"><span data-stu-id="6ee35-134">See Also</span></span>

[<span data-ttu-id="6ee35-135">WideEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="6ee35-135">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="6ee35-136">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="6ee35-136">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="6ee35-137">WideEntry (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="6ee35-137">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="6ee35-138">WideEntry の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6ee35-138">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="6ee35-139">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="6ee35-139">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="6ee35-140">データの表示条件を定義する</span><span class="sxs-lookup"><span data-stu-id="6ee35-140">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="6ee35-141">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="6ee35-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
