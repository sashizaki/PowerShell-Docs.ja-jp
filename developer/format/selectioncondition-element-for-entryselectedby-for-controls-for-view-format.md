---
title: コントロールが表示されます (形式) の EntrySelectedBy SelectionCondition 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2623407e-fa10-4d27-a804-204f6d50ef22
caps.latest.revision: 6
ms.openlocfilehash: ea15e647a9dd7a7064718a0c536c4a3178d62d95
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858018"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="d5621-102">View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d5621-102">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="d5621-103">コントロールの定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="d5621-103">Defines a condition that must exist for the control definition to be used.</span></span> <span data-ttu-id="d5621-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d5621-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="d5621-105">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry EntrySelectedBy のビュー (コントロールのビュー (形式) SelectionCondition 要素のコントロールのビュー (形式) EntrySelectedBy 要素のコントロールのビュー (形式) CustomEntry 要素のコントロールのカスタム コントロール形式)</span><span class="sxs-lookup"><span data-stu-id="d5621-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d5621-106">構文</span><span class="sxs-lookup"><span data-stu-id="d5621-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d5621-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="d5621-107">Attributes and Elements</span></span>

<span data-ttu-id="d5621-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionCondition`要素。</span><span class="sxs-lookup"><span data-stu-id="d5621-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d5621-109">属性</span><span class="sxs-lookup"><span data-stu-id="d5621-109">Attributes</span></span>

<span data-ttu-id="d5621-110">なし。</span><span class="sxs-lookup"><span data-stu-id="d5621-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d5621-111">子要素</span><span class="sxs-lookup"><span data-stu-id="d5621-111">Child Elements</span></span>

|<span data-ttu-id="d5621-112">要素</span><span class="sxs-lookup"><span data-stu-id="d5621-112">Element</span></span>|<span data-ttu-id="d5621-113">説明</span><span class="sxs-lookup"><span data-stu-id="d5621-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d5621-114">コントロールが表示されます (形式) の SelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="d5621-114">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="d5621-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d5621-115">Optional element.</span></span><br /><br /> <span data-ttu-id="d5621-116">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="d5621-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="d5621-117">コントロールが表示されます (形式) の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="d5621-117">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="d5621-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d5621-118">Optional element.</span></span><br /><br /> <span data-ttu-id="d5621-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d5621-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="d5621-120">コントロールが表示されます (形式) の SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="d5621-120">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="d5621-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d5621-121">Optional element.</span></span><br /><br /> <span data-ttu-id="d5621-122">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="d5621-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="d5621-123">コントロールが表示されます (形式) の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="d5621-123">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="d5621-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d5621-124">Optional element.</span></span><br /><br /> <span data-ttu-id="d5621-125">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5621-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d5621-126">親要素</span><span class="sxs-lookup"><span data-stu-id="d5621-126">Parent Elements</span></span>

|<span data-ttu-id="d5621-127">要素</span><span class="sxs-lookup"><span data-stu-id="d5621-127">Element</span></span>|<span data-ttu-id="d5621-128">説明</span><span class="sxs-lookup"><span data-stu-id="d5621-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d5621-129">コントロールが表示されます (形式) の CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="d5621-129">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="d5621-130">このコントロールの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="d5621-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d5621-131">コメント</span><span class="sxs-lookup"><span data-stu-id="d5621-131">Remarks</span></span>

<span data-ttu-id="d5621-132">選択条件を定義している場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d5621-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="d5621-133">選択条件では、少なくとも 1 つのプロパティ名またはスクリプト ブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d5621-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="d5621-134">選択条件が .NET 型の任意の数を指定するか、選択範囲を設定するが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d5621-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="d5621-135">選択条件を使用する方法の詳細については、次を参照してください。[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="d5621-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d5621-136">参照</span><span class="sxs-lookup"><span data-stu-id="d5621-136">See Also</span></span>

[<span data-ttu-id="d5621-137">コントロールが表示されます (形式) の SelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="d5621-137">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="d5621-138">コントロールが表示されます (形式) の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="d5621-138">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="d5621-139">コントロールが表示されます (形式) の SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="d5621-139">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="d5621-140">コントロールが表示されます (形式) の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="d5621-140">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="d5621-141">コントロールが表示されます (形式) の CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="d5621-141">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="d5621-142">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="d5621-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
