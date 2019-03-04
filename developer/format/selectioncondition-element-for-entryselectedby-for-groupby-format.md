---
title: GroupBy (形式) の EntrySelectedBy SelectionCondition 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dc2093a-dc54-42c4-ada3-c8d089ba1e8e
caps.latest.revision: 6
ms.openlocfilehash: a6738a7c4c934b2d6a16695a711f7c6c80afdd2d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855168"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="a8075-102">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a8075-102">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="a8075-103">コントロールの定義が使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="a8075-103">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="a8075-104">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a8075-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="a8075-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) の EntrySelectedBy の GroupBy (形式) SelectionCondition 要素 CustomEntry の GroupBy (形式) EntrySelectedBy 要素にカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="a8075-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a8075-106">構文</span><span class="sxs-lookup"><span data-stu-id="a8075-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a8075-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="a8075-107">Attributes and Elements</span></span>

<span data-ttu-id="a8075-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionCondition`要素。</span><span class="sxs-lookup"><span data-stu-id="a8075-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a8075-109">属性</span><span class="sxs-lookup"><span data-stu-id="a8075-109">Attributes</span></span>

<span data-ttu-id="a8075-110">なし。</span><span class="sxs-lookup"><span data-stu-id="a8075-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a8075-111">子要素</span><span class="sxs-lookup"><span data-stu-id="a8075-111">Child Elements</span></span>

|<span data-ttu-id="a8075-112">要素</span><span class="sxs-lookup"><span data-stu-id="a8075-112">Element</span></span>|<span data-ttu-id="a8075-113">説明</span><span class="sxs-lookup"><span data-stu-id="a8075-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a8075-114">GroupBy (形式) の SelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="a8075-114">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="a8075-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a8075-115">Optional element.</span></span><br /><br /> <span data-ttu-id="a8075-116">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8075-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="a8075-117">GroupBy (形式) の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="a8075-117">ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="a8075-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a8075-118">Optional element.</span></span><br /><br /> <span data-ttu-id="a8075-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8075-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="a8075-120">GroupBy (形式) の SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="a8075-120">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="a8075-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a8075-121">Optional element.</span></span><br /><br /> <span data-ttu-id="a8075-122">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8075-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="a8075-123">GroupBy (形式) の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="a8075-123">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="a8075-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a8075-124">Optional element.</span></span><br /><br /> <span data-ttu-id="a8075-125">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8075-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a8075-126">親要素</span><span class="sxs-lookup"><span data-stu-id="a8075-126">Parent Elements</span></span>

|<span data-ttu-id="a8075-127">要素</span><span class="sxs-lookup"><span data-stu-id="a8075-127">Element</span></span>|<span data-ttu-id="a8075-128">説明</span><span class="sxs-lookup"><span data-stu-id="a8075-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a8075-129">GroupBy (形式) の CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="a8075-129">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="a8075-130">このコントロールの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="a8075-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a8075-131">コメント</span><span class="sxs-lookup"><span data-stu-id="a8075-131">Remarks</span></span>

<span data-ttu-id="a8075-132">選択条件を定義している場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="a8075-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="a8075-133">選択条件では、少なくとも 1 つのプロパティ名またはスクリプト ブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a8075-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="a8075-134">選択条件が .NET 型の任意の数を指定するか、選択範囲を設定するが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a8075-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="a8075-135">選択条件を使用する方法の詳細については、次を参照してください。[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="a8075-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a8075-136">参照</span><span class="sxs-lookup"><span data-stu-id="a8075-136">See Also</span></span>

[<span data-ttu-id="a8075-137">ビュー (形式) のカスタム コントロールの SelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="a8075-137">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a8075-138">ビュー (形式) のカスタム コントロールの SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="a8075-138">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a8075-139">ビュー (形式) 用のカスタム コントロールの SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="a8075-139">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a8075-140">GroupBy (形式) の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="a8075-140">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="a8075-141">GroupBy (形式) の CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="a8075-141">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="a8075-142">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="a8075-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
