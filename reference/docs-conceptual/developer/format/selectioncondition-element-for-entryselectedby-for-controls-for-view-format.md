---
ms.date: 09/13/2016
ms.topic: reference
title: View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)
description: View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)
ms.openlocfilehash: 16b048e73195b3d6168724714ff223851dc1b20b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664852"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="8f3bc-103">View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8f3bc-103">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="8f3bc-104">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="8f3bc-104">Defines a condition that must exist for the control definition to be used.</span></span> <span data-ttu-id="8f3bc-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f3bc-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="8f3bc-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールのコントロールに対して、ビューのコントロールの要素 (形式) コントロール要素 (format) コントロールの要素 (書式) を制御するためのコントロール要素 (書式) の CustomControl 要素 (形式) に対して、コントロールの CustomControl view (format) CustomEntry 要素を使用して、ビュー (format) のコントロールに対して、参照 (format) の項目を表示するためのコントロールの参照 (format) SelectionCondition 要素を表示するためのコントロールに対して、EntrySelectedBy を使用します。</span><span class="sxs-lookup"><span data-stu-id="8f3bc-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8f3bc-107">構文</span><span class="sxs-lookup"><span data-stu-id="8f3bc-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8f3bc-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8f3bc-108">Attributes and Elements</span></span>

<span data-ttu-id="8f3bc-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="8f3bc-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8f3bc-110">属性</span><span class="sxs-lookup"><span data-stu-id="8f3bc-110">Attributes</span></span>

<span data-ttu-id="8f3bc-111">なし。</span><span class="sxs-lookup"><span data-stu-id="8f3bc-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8f3bc-112">子要素</span><span class="sxs-lookup"><span data-stu-id="8f3bc-112">Child Elements</span></span>

|<span data-ttu-id="8f3bc-113">要素</span><span class="sxs-lookup"><span data-stu-id="8f3bc-113">Element</span></span>|<span data-ttu-id="8f3bc-114">説明</span><span class="sxs-lookup"><span data-stu-id="8f3bc-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8f3bc-115">View の Controls の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8f3bc-115">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="8f3bc-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="8f3bc-116">Optional element.</span></span><br /><br /> <span data-ttu-id="8f3bc-117">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="8f3bc-117">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="8f3bc-118">View の Controls の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8f3bc-118">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="8f3bc-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="8f3bc-119">Optional element.</span></span><br /><br /> <span data-ttu-id="8f3bc-120">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="8f3bc-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="8f3bc-121">View の Controls の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8f3bc-121">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="8f3bc-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="8f3bc-122">Optional element.</span></span><br /><br /> <span data-ttu-id="8f3bc-123">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="8f3bc-123">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="8f3bc-124">View の Controls の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8f3bc-124">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="8f3bc-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="8f3bc-125">Optional element.</span></span><br /><br /> <span data-ttu-id="8f3bc-126">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f3bc-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8f3bc-127">親要素</span><span class="sxs-lookup"><span data-stu-id="8f3bc-127">Parent Elements</span></span>

|<span data-ttu-id="8f3bc-128">要素</span><span class="sxs-lookup"><span data-stu-id="8f3bc-128">Element</span></span>|<span data-ttu-id="8f3bc-129">説明</span><span class="sxs-lookup"><span data-stu-id="8f3bc-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8f3bc-130">View の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8f3bc-130">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="8f3bc-131">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="8f3bc-131">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8f3bc-132">解説</span><span class="sxs-lookup"><span data-stu-id="8f3bc-132">Remarks</span></span>

<span data-ttu-id="8f3bc-133">選択条件を定義する場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="8f3bc-133">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="8f3bc-134">選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="8f3bc-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="8f3bc-135">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="8f3bc-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="8f3bc-136">選択条件の使用方法の詳細については、「 [データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f3bc-136">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8f3bc-137">参照</span><span class="sxs-lookup"><span data-stu-id="8f3bc-137">See Also</span></span>

[<span data-ttu-id="8f3bc-138">View の Controls の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8f3bc-138">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="8f3bc-139">View の Controls の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8f3bc-139">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="8f3bc-140">View の Controls の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8f3bc-140">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="8f3bc-141">View の Controls の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8f3bc-141">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="8f3bc-142">View の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8f3bc-142">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="8f3bc-143">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="8f3bc-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
