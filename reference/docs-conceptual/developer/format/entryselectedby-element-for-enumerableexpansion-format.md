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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368801"
---
# <a name="entryselectedby-element-for-enumerableexpansion-format"></a><span data-ttu-id="ac656-102">EnumerableExpansion の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ac656-102">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="ac656-103">この定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="ac656-103">Defines the .NET types that use this definition or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="ac656-104">Configuration 要素 (Format) DefaultSettings 要素 (format) の列挙 Able膨張要素 (format) 列挙 Able膨張の要素 (形式) には、列挙 Able拡張 (Format) の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac656-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ac656-105">構文</span><span class="sxs-lookup"><span data-stu-id="ac656-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ac656-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="ac656-106">Attributes and Elements</span></span>

<span data-ttu-id="ac656-107">次のセクションでは、`EntrySelectedBy` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac656-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ac656-108">属性</span><span class="sxs-lookup"><span data-stu-id="ac656-108">Attributes</span></span>

<span data-ttu-id="ac656-109">なし。</span><span class="sxs-lookup"><span data-stu-id="ac656-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ac656-110">子要素</span><span class="sxs-lookup"><span data-stu-id="ac656-110">Child Elements</span></span>

|<span data-ttu-id="ac656-111">要素</span><span class="sxs-lookup"><span data-stu-id="ac656-111">Element</span></span>|<span data-ttu-id="ac656-112">[説明]</span><span class="sxs-lookup"><span data-stu-id="ac656-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ac656-113">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="ac656-113">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="ac656-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="ac656-114">Optional element.</span></span><br /><br /> <span data-ttu-id="ac656-115">この定義のコレクションオブジェクトを展開するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="ac656-115">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|
|[<span data-ttu-id="ac656-116">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="ac656-116">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="ac656-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="ac656-117">Optional element.</span></span><br /><br /> <span data-ttu-id="ac656-118">コレクションオブジェクトの展開方法のこの定義を使用する一連の .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac656-118">Specifies a set of .NET types that use this definition of how collection objects are expanded.</span></span>|
|[<span data-ttu-id="ac656-119">列挙型展開の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="ac656-119">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="ac656-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="ac656-120">Optional element.</span></span><br /><br /> <span data-ttu-id="ac656-121">コレクションオブジェクトの展開方法のこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac656-121">Specifies a .NET type that uses this definition of how collection objects are expanded.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ac656-122">親要素</span><span class="sxs-lookup"><span data-stu-id="ac656-122">Parent Elements</span></span>

|<span data-ttu-id="ac656-123">要素</span><span class="sxs-lookup"><span data-stu-id="ac656-123">Element</span></span>|<span data-ttu-id="ac656-124">[説明]</span><span class="sxs-lookup"><span data-stu-id="ac656-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ac656-125">列挙 Able展開要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ac656-125">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="ac656-126">特定の .NET コレクションオブジェクトをビューに表示するときに展開する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="ac656-126">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ac656-127">コメント</span><span class="sxs-lookup"><span data-stu-id="ac656-127">Remarks</span></span>

<span data-ttu-id="ac656-128">定義エントリには、少なくとも1つの種類、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac656-128">You must specify at least one type, selection set, or selection condition for a definition entry.</span></span> <span data-ttu-id="ac656-129">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="ac656-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="ac656-130">選択条件を使用して、オブジェクトに特定のプロパティがある場合や、特定のプロパティ値またはスクリプトが `true`として評価される場合など、使用する定義に存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="ac656-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="ac656-131">選択条件の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac656-131">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ac656-132">参照</span><span class="sxs-lookup"><span data-stu-id="ac656-132">See Also</span></span>

[<span data-ttu-id="ac656-133">データを表示するための条件の定義</span><span class="sxs-lookup"><span data-stu-id="ac656-133">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="ac656-134">列挙 Able展開要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ac656-134">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)

[<span data-ttu-id="ac656-135">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="ac656-135">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="ac656-136">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="ac656-136">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="ac656-137">列挙型展開の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="ac656-137">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="ac656-138">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="ac656-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
