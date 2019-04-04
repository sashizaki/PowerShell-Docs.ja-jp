---
title: EnumerableExpansion (形式) の要素を EntrySelectedBy |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3af6aff8-4c2d-4f08-9bb1-e1f3ed3e583e
caps.latest.revision: 11
ms.openlocfilehash: 6a371bdbb85d07730c32931a4a79ee40856ce298
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855588"
---
# <a name="entryselectedby-element-for-enumerableexpansion-format"></a><span data-ttu-id="60b34-102">EnumerableExpansion の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="60b34-102">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="60b34-103">この定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="60b34-103">Defines the .NET types that use this definition or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="60b34-104">構成要素 (形式) DefaultSettings 要素 (形式) EnumerableExpansions 要素 (形式) EnumerableExpansion 要素 (形式) EntrySelectedBy 要素の EnumerableExpansion (形式)</span><span class="sxs-lookup"><span data-stu-id="60b34-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="60b34-105">構文</span><span class="sxs-lookup"><span data-stu-id="60b34-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="60b34-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="60b34-106">Attributes and Elements</span></span>

<span data-ttu-id="60b34-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`EntrySelectedBy`要素。</span><span class="sxs-lookup"><span data-stu-id="60b34-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="60b34-108">属性</span><span class="sxs-lookup"><span data-stu-id="60b34-108">Attributes</span></span>

<span data-ttu-id="60b34-109">なし。</span><span class="sxs-lookup"><span data-stu-id="60b34-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="60b34-110">子要素</span><span class="sxs-lookup"><span data-stu-id="60b34-110">Child Elements</span></span>

|<span data-ttu-id="60b34-111">要素</span><span class="sxs-lookup"><span data-stu-id="60b34-111">Element</span></span>|<span data-ttu-id="60b34-112">説明</span><span class="sxs-lookup"><span data-stu-id="60b34-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="60b34-113">EnumerableExpansion (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="60b34-113">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="60b34-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="60b34-114">Optional element.</span></span><br /><br /> <span data-ttu-id="60b34-115">この定義のコレクション オブジェクトの展開に必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="60b34-115">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|
|[<span data-ttu-id="60b34-116">EnumerableExpansion (形式) の EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="60b34-116">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="60b34-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="60b34-117">Optional element.</span></span><br /><br /> <span data-ttu-id="60b34-118">この定義のコレクション オブジェクトを展開する方法を使用する .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="60b34-118">Specifies a set of .NET types that use this definition of how collection objects are expanded.</span></span>|
|[<span data-ttu-id="60b34-119">EntrySelectedBy EnumerableExpansion (形式) 用の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="60b34-119">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="60b34-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="60b34-120">Optional element.</span></span><br /><br /> <span data-ttu-id="60b34-121">この定義のコレクション オブジェクトを展開する方法を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="60b34-121">Specifies a .NET type that uses this definition of how collection objects are expanded.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="60b34-122">親要素</span><span class="sxs-lookup"><span data-stu-id="60b34-122">Parent Elements</span></span>

|<span data-ttu-id="60b34-123">要素</span><span class="sxs-lookup"><span data-stu-id="60b34-123">Element</span></span>|<span data-ttu-id="60b34-124">説明</span><span class="sxs-lookup"><span data-stu-id="60b34-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="60b34-125">EnumerableExpansion 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="60b34-125">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="60b34-126">ビューに表示されているときに、オブジェクトが展開されます、特定の .NET コレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="60b34-126">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="60b34-127">コメント</span><span class="sxs-lookup"><span data-stu-id="60b34-127">Remarks</span></span>

<span data-ttu-id="60b34-128">少なくとも 1 つの型、選択範囲のセット、または定義のエントリの選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60b34-128">You must specify at least one type, selection set, or selection condition for a definition entry.</span></span> <span data-ttu-id="60b34-129">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="60b34-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="60b34-130">選択条件を使用して、定義オブジェクトに特定のプロパティがある場合など、使用するのに必要な条件を定義または特定のプロパティの値またはスクリプトに評価される`true`します。</span><span class="sxs-lookup"><span data-stu-id="60b34-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="60b34-131">選択条件の詳細については、[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60b34-131">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="60b34-132">参照</span><span class="sxs-lookup"><span data-stu-id="60b34-132">See Also</span></span>

[<span data-ttu-id="60b34-133">データを表示するための条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="60b34-133">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="60b34-134">EnumerableExpansion 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="60b34-134">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)

[<span data-ttu-id="60b34-135">EnumerableExpansion (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="60b34-135">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="60b34-136">EnumerableExpansion (形式) の EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="60b34-136">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="60b34-137">EntrySelectedBy EnumerableExpansion (形式) 用の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="60b34-137">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="60b34-138">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="60b34-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
