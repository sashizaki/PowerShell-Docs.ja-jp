---
title: GroupBy (形式) の CustomEntry EntrySelectedBy 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a317d482-73cc-4c98-a002-1357fa879cd7
caps.latest.revision: 7
ms.openlocfilehash: cf1a80e845c38d97d71f26eba63c38a550958b79
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862818"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a><span data-ttu-id="3f278-102">GroupBy の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3f278-102">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="3f278-103">このコントロールの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="3f278-103">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="3f278-104">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f278-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="3f278-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) の CustomEntry の GroupBy (形式) EntrySelectedBy 要素にカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="3f278-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3f278-106">構文</span><span class="sxs-lookup"><span data-stu-id="3f278-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3f278-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="3f278-107">Attributes and Elements</span></span>

<span data-ttu-id="3f278-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`EntrySelectedBy`要素。</span><span class="sxs-lookup"><span data-stu-id="3f278-108">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="3f278-109">少なくとも 1 つの型、選択範囲のセット、または定義の選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f278-109">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="3f278-110">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="3f278-110">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="3f278-111">属性</span><span class="sxs-lookup"><span data-stu-id="3f278-111">Attributes</span></span>

<span data-ttu-id="3f278-112">なし。</span><span class="sxs-lookup"><span data-stu-id="3f278-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3f278-113">子要素</span><span class="sxs-lookup"><span data-stu-id="3f278-113">Child Elements</span></span>

|<span data-ttu-id="3f278-114">要素</span><span class="sxs-lookup"><span data-stu-id="3f278-114">Element</span></span>|<span data-ttu-id="3f278-115">説明</span><span class="sxs-lookup"><span data-stu-id="3f278-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3f278-116">GroupBy (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="3f278-116">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="3f278-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="3f278-117">Optional element.</span></span><br /><br /> <span data-ttu-id="3f278-118">この定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="3f278-118">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="3f278-119">GroupBy (形式) の EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3f278-119">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="3f278-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="3f278-120">Optional element.</span></span><br /><br /> <span data-ttu-id="3f278-121">このコントロールの定義を使用して .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f278-121">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="3f278-122">GroupBy (形式) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="3f278-122">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="3f278-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="3f278-123">Optional element.</span></span><br /><br /> <span data-ttu-id="3f278-124">このコントロールの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f278-124">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3f278-125">親要素</span><span class="sxs-lookup"><span data-stu-id="3f278-125">Parent Elements</span></span>

|<span data-ttu-id="3f278-126">要素</span><span class="sxs-lookup"><span data-stu-id="3f278-126">Element</span></span>|<span data-ttu-id="3f278-127">説明</span><span class="sxs-lookup"><span data-stu-id="3f278-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3f278-128">GroupBy (形式) のカスタム コントロールの CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="3f278-128">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="3f278-129">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="3f278-129">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3f278-130">コメント</span><span class="sxs-lookup"><span data-stu-id="3f278-130">Remarks</span></span>

<span data-ttu-id="3f278-131">選択条件を使用して、使用する定義のオブジェクトに特定のプロパティがある場合などときや、特定のプロパティ値の条件が存在する必要がありますを定義またはスクリプトを評価する`true`します。</span><span class="sxs-lookup"><span data-stu-id="3f278-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="3f278-132">選択条件の詳細については、[とビューのエントリの定義の条件またはアイテムが使用されて](./defining-conditions-for-displaying-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f278-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3f278-133">参照</span><span class="sxs-lookup"><span data-stu-id="3f278-133">See Also</span></span>

[<span data-ttu-id="3f278-134">GroupBy (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="3f278-134">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="3f278-135">GroupBy (形式) の EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3f278-135">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="3f278-136">GroupBy (形式) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="3f278-136">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="3f278-137">コントロールが表示されます (形式) の CustomEntries CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="3f278-137">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="3f278-138">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="3f278-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
