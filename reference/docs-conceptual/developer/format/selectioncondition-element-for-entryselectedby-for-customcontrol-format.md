---
title: CustomControl (Format) の EntrySelectedBy の SelectionCondition 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 231e9c6d-09ec-4e68-80ee-0c8f7fe1b9f5
caps.latest.revision: 7
ms.openlocfilehash: 49e2c0cf09dfa55b535effcd431e980daf12fac3
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368441"
---
# <a name="selectioncondition-element-for-entryselectedby-for-customcontrol-format"></a><span data-ttu-id="e986d-102">CustomControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e986d-102">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span></span>

<span data-ttu-id="e986d-103">コントロール定義を使用するために存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="e986d-103">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="e986d-104">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e986d-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="e986d-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の CustomControl 要素を表示するための CustomControl for ビュー (形式) の Custommentry 要素の CustomControl for View (Format) CustomEntry for CustomControl 用の CustomItem 要素を使用して、CustomEntry for CustomControl for view (format) の EntrySelectedBy 要素の EntrySelectedBy for CustomControl for View (format) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e986d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) EntrySelectedBy Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e986d-106">構文</span><span class="sxs-lookup"><span data-stu-id="e986d-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e986d-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="e986d-107">Attributes and Elements</span></span>

<span data-ttu-id="e986d-108">次のセクションでは、属性、子要素、`SelectionCondition` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e986d-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e986d-109">属性</span><span class="sxs-lookup"><span data-stu-id="e986d-109">Attributes</span></span>

<span data-ttu-id="e986d-110">なし。</span><span class="sxs-lookup"><span data-stu-id="e986d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e986d-111">子要素</span><span class="sxs-lookup"><span data-stu-id="e986d-111">Child Elements</span></span>

|<span data-ttu-id="e986d-112">要素</span><span class="sxs-lookup"><span data-stu-id="e986d-112">Element</span></span>|<span data-ttu-id="e986d-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="e986d-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e986d-114">CustomControl for ビュー (Format) の SelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="e986d-114">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="e986d-115">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="e986d-115">Optional element.</span></span><br /><br /> <span data-ttu-id="e986d-116">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="e986d-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="e986d-117">CustomControl for ビュー (Format) の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="e986d-117">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="e986d-118">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="e986d-118">Optional element.</span></span><br /><br /> <span data-ttu-id="e986d-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e986d-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="e986d-120">View (Format) のカスタムコントロールの SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="e986d-120">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="e986d-121">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="e986d-121">Optional element.</span></span><br /><br /> <span data-ttu-id="e986d-122">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="e986d-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="e986d-123">CustomControl for ビュー (Format) の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="e986d-123">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="e986d-124">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="e986d-124">Optional element.</span></span><br /><br /> <span data-ttu-id="e986d-125">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="e986d-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e986d-126">親要素</span><span class="sxs-lookup"><span data-stu-id="e986d-126">Parent Elements</span></span>

|<span data-ttu-id="e986d-127">要素</span><span class="sxs-lookup"><span data-stu-id="e986d-127">Element</span></span>|<span data-ttu-id="e986d-128">[説明]</span><span class="sxs-lookup"><span data-stu-id="e986d-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e986d-129">CustomEntry for CustomControl for View (Format) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="e986d-129">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="e986d-130">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="e986d-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e986d-131">コメント</span><span class="sxs-lookup"><span data-stu-id="e986d-131">Remarks</span></span>

<span data-ttu-id="e986d-132">選択条件を定義する場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e986d-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="e986d-133">選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e986d-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="e986d-134">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e986d-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="e986d-135">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e986d-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e986d-136">参照</span><span class="sxs-lookup"><span data-stu-id="e986d-136">See Also</span></span>

[<span data-ttu-id="e986d-137">CustomControl for ビュー (Format) の SelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="e986d-137">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e986d-138">CustomControl for ビュー (Format) の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="e986d-138">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e986d-139">View (Format) のカスタムコントロールの SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="e986d-139">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e986d-140">CustomControl for ビュー (Format) の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="e986d-140">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e986d-141">CustomEntry for CustomControl for View (Format) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="e986d-141">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e986d-142">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="e986d-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
