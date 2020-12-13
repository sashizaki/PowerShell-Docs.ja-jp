---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)
description: GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)
ms.openlocfilehash: 14c293b6bc6d6accc201de35be9219349079801d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664743"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="06d71-103">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="06d71-103">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="06d71-104">コントロール定義を使用するために存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="06d71-104">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="06d71-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="06d71-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="06d71-106">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) の GroupBy 要素を使用して、groupby (形式) の CustomControl 要素の CustomControl の CustomControl for groupby (形式) の CustomEntry 要素の for groupby (format) の CustomEntry 要素を使用して、groupby (形式) のエントリを指定します。</span><span class="sxs-lookup"><span data-stu-id="06d71-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="06d71-107">構文</span><span class="sxs-lookup"><span data-stu-id="06d71-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="06d71-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="06d71-108">Attributes and Elements</span></span>

<span data-ttu-id="06d71-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="06d71-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="06d71-110">属性</span><span class="sxs-lookup"><span data-stu-id="06d71-110">Attributes</span></span>

<span data-ttu-id="06d71-111">なし。</span><span class="sxs-lookup"><span data-stu-id="06d71-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="06d71-112">子要素</span><span class="sxs-lookup"><span data-stu-id="06d71-112">Child Elements</span></span>

|<span data-ttu-id="06d71-113">要素</span><span class="sxs-lookup"><span data-stu-id="06d71-113">Element</span></span>|<span data-ttu-id="06d71-114">説明</span><span class="sxs-lookup"><span data-stu-id="06d71-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="06d71-115">GroupBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="06d71-115">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="06d71-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="06d71-116">Optional element.</span></span><br /><br /> <span data-ttu-id="06d71-117">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="06d71-117">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="06d71-118">GroupBy (Format) の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="06d71-118">ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="06d71-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="06d71-119">Optional element.</span></span><br /><br /> <span data-ttu-id="06d71-120">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="06d71-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="06d71-121">GroupBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="06d71-121">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="06d71-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="06d71-122">Optional element.</span></span><br /><br /> <span data-ttu-id="06d71-123">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="06d71-123">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="06d71-124">GroupBy (Format) の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="06d71-124">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="06d71-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="06d71-125">Optional element.</span></span><br /><br /> <span data-ttu-id="06d71-126">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="06d71-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="06d71-127">親要素</span><span class="sxs-lookup"><span data-stu-id="06d71-127">Parent Elements</span></span>

|<span data-ttu-id="06d71-128">要素</span><span class="sxs-lookup"><span data-stu-id="06d71-128">Element</span></span>|<span data-ttu-id="06d71-129">説明</span><span class="sxs-lookup"><span data-stu-id="06d71-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="06d71-130">GroupBy の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="06d71-130">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="06d71-131">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="06d71-131">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="06d71-132">解説</span><span class="sxs-lookup"><span data-stu-id="06d71-132">Remarks</span></span>

<span data-ttu-id="06d71-133">選択条件を定義する場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="06d71-133">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="06d71-134">選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="06d71-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="06d71-135">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="06d71-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="06d71-136">選択条件の使用方法の詳細については、「 [データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06d71-136">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="06d71-137">参照</span><span class="sxs-lookup"><span data-stu-id="06d71-137">See Also</span></span>

[<span data-ttu-id="06d71-138">View の CustomControl の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="06d71-138">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="06d71-139">View の CustomControl の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="06d71-139">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="06d71-140">View (Format) のカスタムコントロールの SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="06d71-140">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="06d71-141">GroupBy (Format) の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="06d71-141">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="06d71-142">GroupBy の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="06d71-142">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="06d71-143">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="06d71-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
