---
ms.date: 09/13/2016
ms.topic: reference
title: EnumerableExpansion の EntrySelectedBy 要素 (書式)
description: EnumerableExpansion の EntrySelectedBy 要素 (書式)
ms.openlocfilehash: 8b2fff2d0b14d0622d0be2c5af3a95194c733a73
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652322"
---
# <a name="entryselectedby-element-for-enumerableexpansion-format"></a><span data-ttu-id="65946-103">EnumerableExpansion の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="65946-103">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="65946-104">この定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="65946-104">Defines the .NET types that use this definition or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="65946-105">Configuration 要素 (Format) DefaultSettings 要素 (format) の列挙 Able膨張要素 (format) 列挙 Able膨張の要素 (形式) には、列挙 Able拡張 (Format) の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="65946-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="65946-106">構文</span><span class="sxs-lookup"><span data-stu-id="65946-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="65946-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="65946-107">Attributes and Elements</span></span>

<span data-ttu-id="65946-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `EntrySelectedBy` ます。</span><span class="sxs-lookup"><span data-stu-id="65946-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="65946-109">属性</span><span class="sxs-lookup"><span data-stu-id="65946-109">Attributes</span></span>

<span data-ttu-id="65946-110">なし。</span><span class="sxs-lookup"><span data-stu-id="65946-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="65946-111">子要素</span><span class="sxs-lookup"><span data-stu-id="65946-111">Child Elements</span></span>

|<span data-ttu-id="65946-112">要素</span><span class="sxs-lookup"><span data-stu-id="65946-112">Element</span></span>|<span data-ttu-id="65946-113">説明</span><span class="sxs-lookup"><span data-stu-id="65946-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="65946-114">EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="65946-114">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="65946-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="65946-115">Optional element.</span></span><br /><br /> <span data-ttu-id="65946-116">この定義のコレクションオブジェクトを展開するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="65946-116">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|
|[<span data-ttu-id="65946-117">EnumerableExpansion の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="65946-117">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="65946-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="65946-118">Optional element.</span></span><br /><br /> <span data-ttu-id="65946-119">コレクションオブジェクトの展開方法のこの定義を使用する一連の .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="65946-119">Specifies a set of .NET types that use this definition of how collection objects are expanded.</span></span>|
|[<span data-ttu-id="65946-120">EnumerableExpansion の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="65946-120">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="65946-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="65946-121">Optional element.</span></span><br /><br /> <span data-ttu-id="65946-122">コレクションオブジェクトの展開方法のこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="65946-122">Specifies a .NET type that uses this definition of how collection objects are expanded.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="65946-123">親要素</span><span class="sxs-lookup"><span data-stu-id="65946-123">Parent Elements</span></span>

|<span data-ttu-id="65946-124">要素</span><span class="sxs-lookup"><span data-stu-id="65946-124">Element</span></span>|<span data-ttu-id="65946-125">説明</span><span class="sxs-lookup"><span data-stu-id="65946-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="65946-126">EnumerableExpansion 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="65946-126">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="65946-127">特定の .NET コレクションオブジェクトをビューに表示するときに展開する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="65946-127">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="65946-128">解説</span><span class="sxs-lookup"><span data-stu-id="65946-128">Remarks</span></span>

<span data-ttu-id="65946-129">定義エントリには、少なくとも1つの種類、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65946-129">You must specify at least one type, selection set, or selection condition for a definition entry.</span></span> <span data-ttu-id="65946-130">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="65946-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="65946-131">選択条件は、オブジェクトが特定のプロパティを持っている場合や、特定のプロパティ値またはスクリプトがに評価される場合など、使用する定義のために存在する必要がある条件を定義するために使用され `true` ます。</span><span class="sxs-lookup"><span data-stu-id="65946-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="65946-132">選択条件の詳細については、「 [データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65946-132">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="65946-133">参照</span><span class="sxs-lookup"><span data-stu-id="65946-133">See Also</span></span>

[<span data-ttu-id="65946-134">データの表示条件を定義する</span><span class="sxs-lookup"><span data-stu-id="65946-134">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="65946-135">EnumerableExpansion 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="65946-135">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)

[<span data-ttu-id="65946-136">EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="65946-136">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="65946-137">EnumerableExpansion の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="65946-137">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="65946-138">EnumerableExpansion の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="65946-138">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="65946-139">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="65946-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
