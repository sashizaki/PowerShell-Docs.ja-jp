---
title: 列挙 Able膨張 (Format) の EntrySelectedBy 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3af6aff8-4c2d-4f08-9bb1-e1f3ed3e583e
caps.latest.revision: 11
ms.openlocfilehash: 6a371bdbb85d07730c32931a4a79ee40856ce298
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368801"
---
# <a name="entryselectedby-element-for-enumerableexpansion-format"></a><span data-ttu-id="93cde-102">EnumerableExpansion の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="93cde-102">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="93cde-103">この定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="93cde-103">Defines the .NET types that use this definition or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="93cde-104">Configuration 要素 (Format) DefaultSettings 要素 (format) の列挙 Able膨張要素 (format) 列挙 Able膨張の要素 (形式) には、列挙 Able拡張 (Format) の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="93cde-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="93cde-105">構文</span><span class="sxs-lookup"><span data-stu-id="93cde-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="93cde-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="93cde-106">Attributes and Elements</span></span>

<span data-ttu-id="93cde-107">次のセクションでは、属性、子要素、`EntrySelectedBy` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="93cde-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="93cde-108">属性</span><span class="sxs-lookup"><span data-stu-id="93cde-108">Attributes</span></span>

<span data-ttu-id="93cde-109">なし。</span><span class="sxs-lookup"><span data-stu-id="93cde-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="93cde-110">子要素</span><span class="sxs-lookup"><span data-stu-id="93cde-110">Child Elements</span></span>

|<span data-ttu-id="93cde-111">要素</span><span class="sxs-lookup"><span data-stu-id="93cde-111">Element</span></span>|<span data-ttu-id="93cde-112">[説明]</span><span class="sxs-lookup"><span data-stu-id="93cde-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="93cde-113">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="93cde-113">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="93cde-114">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="93cde-114">Optional element.</span></span><br /><br /> <span data-ttu-id="93cde-115">この定義のコレクションオブジェクトを展開するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="93cde-115">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|
|[<span data-ttu-id="93cde-116">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="93cde-116">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="93cde-117">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="93cde-117">Optional element.</span></span><br /><br /> <span data-ttu-id="93cde-118">コレクションオブジェクトの展開方法のこの定義を使用する一連の .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="93cde-118">Specifies a set of .NET types that use this definition of how collection objects are expanded.</span></span>|
|[<span data-ttu-id="93cde-119">列挙型展開の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="93cde-119">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="93cde-120">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="93cde-120">Optional element.</span></span><br /><br /> <span data-ttu-id="93cde-121">コレクションオブジェクトの展開方法のこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="93cde-121">Specifies a .NET type that uses this definition of how collection objects are expanded.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="93cde-122">親要素</span><span class="sxs-lookup"><span data-stu-id="93cde-122">Parent Elements</span></span>

|<span data-ttu-id="93cde-123">要素</span><span class="sxs-lookup"><span data-stu-id="93cde-123">Element</span></span>|<span data-ttu-id="93cde-124">[説明]</span><span class="sxs-lookup"><span data-stu-id="93cde-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="93cde-125">列挙 Able展開要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="93cde-125">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="93cde-126">特定の .NET コレクションオブジェクトをビューに表示するときに展開する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="93cde-126">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="93cde-127">コメント</span><span class="sxs-lookup"><span data-stu-id="93cde-127">Remarks</span></span>

<span data-ttu-id="93cde-128">定義エントリには、少なくとも1つの種類、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93cde-128">You must specify at least one type, selection set, or selection condition for a definition entry.</span></span> <span data-ttu-id="93cde-129">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="93cde-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="93cde-130">選択条件は、オブジェクトに特定のプロパティがある場合や、特定のプロパティ値またはスクリプトが `true` に評価される場合など、使用する定義のために存在する必要がある条件を定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="93cde-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="93cde-131">選択条件の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93cde-131">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="93cde-132">参照</span><span class="sxs-lookup"><span data-stu-id="93cde-132">See Also</span></span>

[<span data-ttu-id="93cde-133">データを表示するための条件の定義</span><span class="sxs-lookup"><span data-stu-id="93cde-133">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="93cde-134">列挙 Able展開要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="93cde-134">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)

[<span data-ttu-id="93cde-135">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="93cde-135">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="93cde-136">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="93cde-136">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="93cde-137">列挙型展開の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="93cde-137">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="93cde-138">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="93cde-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
