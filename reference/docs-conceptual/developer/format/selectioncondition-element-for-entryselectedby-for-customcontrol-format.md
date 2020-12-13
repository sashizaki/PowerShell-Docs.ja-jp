---
ms.date: 09/13/2016
ms.topic: reference
title: CustomControl の EntrySelectedBy の SelectionCondition 要素 (書式)
description: CustomControl の EntrySelectedBy の SelectionCondition 要素 (書式)
ms.openlocfilehash: 6d4cc5a2d5fef0445d586e320b3729d3a7044063
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649774"
---
# <a name="selectioncondition-element-for-entryselectedby-for-customcontrol-format"></a><span data-ttu-id="855f9-103">CustomControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="855f9-103">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span></span>

<span data-ttu-id="855f9-104">コントロール定義を使用するために存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="855f9-104">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="855f9-105">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="855f9-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="855f9-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビューの CustomControl 要素 (format) CustomControl for view (format) の CustomEntries の CustomControl for view (format) カスタムエントリ要素の for ビュー (形式)) に対して CustomEntry for CustomControl for View (format) エントリの EntrySelectedBy 要素を指定して、CustomControl for View (Format) の EntrySelectedBy の SelectionCondition 要素を表示します。</span><span class="sxs-lookup"><span data-stu-id="855f9-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) EntrySelectedBy Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="855f9-107">構文</span><span class="sxs-lookup"><span data-stu-id="855f9-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="855f9-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="855f9-108">Attributes and Elements</span></span>

<span data-ttu-id="855f9-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="855f9-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="855f9-110">属性</span><span class="sxs-lookup"><span data-stu-id="855f9-110">Attributes</span></span>

<span data-ttu-id="855f9-111">なし。</span><span class="sxs-lookup"><span data-stu-id="855f9-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="855f9-112">子要素</span><span class="sxs-lookup"><span data-stu-id="855f9-112">Child Elements</span></span>

|<span data-ttu-id="855f9-113">要素</span><span class="sxs-lookup"><span data-stu-id="855f9-113">Element</span></span>|<span data-ttu-id="855f9-114">説明</span><span class="sxs-lookup"><span data-stu-id="855f9-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="855f9-115">View の CustomControl の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="855f9-115">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="855f9-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="855f9-116">Optional element.</span></span><br /><br /> <span data-ttu-id="855f9-117">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="855f9-117">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="855f9-118">View の CustomControl の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="855f9-118">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="855f9-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="855f9-119">Optional element.</span></span><br /><br /> <span data-ttu-id="855f9-120">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="855f9-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="855f9-121">View (Format) のカスタムコントロールの SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="855f9-121">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="855f9-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="855f9-122">Optional element.</span></span><br /><br /> <span data-ttu-id="855f9-123">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="855f9-123">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="855f9-124">View の CustomControl の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="855f9-124">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="855f9-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="855f9-125">Optional element.</span></span><br /><br /> <span data-ttu-id="855f9-126">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="855f9-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="855f9-127">親要素</span><span class="sxs-lookup"><span data-stu-id="855f9-127">Parent Elements</span></span>

|<span data-ttu-id="855f9-128">要素</span><span class="sxs-lookup"><span data-stu-id="855f9-128">Element</span></span>|<span data-ttu-id="855f9-129">説明</span><span class="sxs-lookup"><span data-stu-id="855f9-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="855f9-130">View の CustomControl の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="855f9-130">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="855f9-131">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="855f9-131">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="855f9-132">解説</span><span class="sxs-lookup"><span data-stu-id="855f9-132">Remarks</span></span>

<span data-ttu-id="855f9-133">選択条件を定義する場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="855f9-133">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="855f9-134">選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="855f9-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="855f9-135">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="855f9-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="855f9-136">選択条件の使用方法の詳細については、「 [データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="855f9-136">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="855f9-137">参照</span><span class="sxs-lookup"><span data-stu-id="855f9-137">See Also</span></span>

[<span data-ttu-id="855f9-138">View の CustomControl の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="855f9-138">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="855f9-139">View の CustomControl の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="855f9-139">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="855f9-140">View (Format) のカスタムコントロールの SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="855f9-140">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="855f9-141">View の CustomControl の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="855f9-141">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="855f9-142">View の CustomControl の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="855f9-142">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="855f9-143">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="855f9-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
