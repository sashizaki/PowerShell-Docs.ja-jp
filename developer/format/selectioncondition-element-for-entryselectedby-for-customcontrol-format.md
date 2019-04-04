---
title: カスタム コントロール (形式) の EntrySelectedBy SelectionCondition 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 231e9c6d-09ec-4e68-80ee-0c8f7fe1b9f5
caps.latest.revision: 7
ms.openlocfilehash: 49e2c0cf09dfa55b535effcd431e980daf12fac3
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858828"
---
# <a name="selectioncondition-element-for-entryselectedby-for-customcontrol-format"></a><span data-ttu-id="44e85-102">CustomControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="44e85-102">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span></span>

<span data-ttu-id="44e85-103">コントロールの定義が使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="44e85-103">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="44e85-104">この要素は、カスタム コントロールのビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="44e85-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="44e85-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素の表示 (カスタム コントロールの CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールのビュー (形式) CustomEntries 要素CustomEntry CustomEntry EntrySelectedBy ビュー (形式) のカスタム コントロール用のビュー (形式) SelectionCondition 要素のカスタム コントロール用のビュー (形式) EntrySelectedBy 要素のカスタム コントロール用の形式) CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="44e85-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) EntrySelectedBy Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="44e85-106">構文</span><span class="sxs-lookup"><span data-stu-id="44e85-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="44e85-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="44e85-107">Attributes and Elements</span></span>

<span data-ttu-id="44e85-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionCondition`要素。</span><span class="sxs-lookup"><span data-stu-id="44e85-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="44e85-109">属性</span><span class="sxs-lookup"><span data-stu-id="44e85-109">Attributes</span></span>

<span data-ttu-id="44e85-110">なし。</span><span class="sxs-lookup"><span data-stu-id="44e85-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="44e85-111">子要素</span><span class="sxs-lookup"><span data-stu-id="44e85-111">Child Elements</span></span>

|<span data-ttu-id="44e85-112">要素</span><span class="sxs-lookup"><span data-stu-id="44e85-112">Element</span></span>|<span data-ttu-id="44e85-113">説明</span><span class="sxs-lookup"><span data-stu-id="44e85-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="44e85-114">ビュー (形式) のカスタム コントロールの SelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="44e85-114">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="44e85-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="44e85-115">Optional element.</span></span><br /><br /> <span data-ttu-id="44e85-116">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="44e85-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="44e85-117">ビュー (形式) のカスタム コントロールの SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="44e85-117">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="44e85-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="44e85-118">Optional element.</span></span><br /><br /> <span data-ttu-id="44e85-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="44e85-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="44e85-120">ビュー (形式) 用のカスタム コントロールの SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="44e85-120">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="44e85-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="44e85-121">Optional element.</span></span><br /><br /> <span data-ttu-id="44e85-122">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="44e85-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="44e85-123">ビュー (形式) のカスタム コントロールの SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="44e85-123">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="44e85-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="44e85-124">Optional element.</span></span><br /><br /> <span data-ttu-id="44e85-125">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="44e85-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="44e85-126">親要素</span><span class="sxs-lookup"><span data-stu-id="44e85-126">Parent Elements</span></span>

|<span data-ttu-id="44e85-127">要素</span><span class="sxs-lookup"><span data-stu-id="44e85-127">Element</span></span>|<span data-ttu-id="44e85-128">説明</span><span class="sxs-lookup"><span data-stu-id="44e85-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="44e85-129">ビュー (形式) のカスタム コントロールの CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="44e85-129">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="44e85-130">このコントロールの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="44e85-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="44e85-131">コメント</span><span class="sxs-lookup"><span data-stu-id="44e85-131">Remarks</span></span>

<span data-ttu-id="44e85-132">選択条件を定義している場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="44e85-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="44e85-133">選択条件では、少なくとも 1 つのプロパティ名またはスクリプト ブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="44e85-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="44e85-134">選択条件が .NET 型の任意の数を指定するか、選択範囲を設定するが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="44e85-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="44e85-135">選択条件を使用する方法の詳細については、[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44e85-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="44e85-136">参照</span><span class="sxs-lookup"><span data-stu-id="44e85-136">See Also</span></span>

[<span data-ttu-id="44e85-137">ビュー (形式) のカスタム コントロールの SelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="44e85-137">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="44e85-138">ビュー (形式) のカスタム コントロールの SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="44e85-138">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="44e85-139">ビュー (形式) 用のカスタム コントロールの SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="44e85-139">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="44e85-140">ビュー (形式) のカスタム コントロールの SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="44e85-140">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="44e85-141">ビュー (形式) のカスタム コントロールの CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="44e85-141">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="44e85-142">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="44e85-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
