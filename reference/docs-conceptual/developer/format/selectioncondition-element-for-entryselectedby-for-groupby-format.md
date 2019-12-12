---
title: GroupBy (Format) の EntrySelectedBy の SelectionCondition 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dc2093a-dc54-42c4-ada3-c8d089ba1e8e
caps.latest.revision: 6
ms.openlocfilehash: a6738a7c4c934b2d6a16695a711f7c6c80afdd2d
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368431"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="2ab69-102">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2ab69-102">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="2ab69-103">コントロール定義を使用するために存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="2ab69-103">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="2ab69-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2ab69-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="2ab69-105">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素Groupby (format) の CustomControl の Entryselectedby for groupby (format) の Selectionselectedby 要素の EntrySelectedBy GroupBy (形式) の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="2ab69-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2ab69-106">構文</span><span class="sxs-lookup"><span data-stu-id="2ab69-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2ab69-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="2ab69-107">Attributes and Elements</span></span>

<span data-ttu-id="2ab69-108">次のセクションでは、`SelectionCondition` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ab69-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2ab69-109">属性</span><span class="sxs-lookup"><span data-stu-id="2ab69-109">Attributes</span></span>

<span data-ttu-id="2ab69-110">なし。</span><span class="sxs-lookup"><span data-stu-id="2ab69-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2ab69-111">子要素</span><span class="sxs-lookup"><span data-stu-id="2ab69-111">Child Elements</span></span>

|<span data-ttu-id="2ab69-112">要素</span><span class="sxs-lookup"><span data-stu-id="2ab69-112">Element</span></span>|<span data-ttu-id="2ab69-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="2ab69-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2ab69-114">GroupBy (Format) の SelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="2ab69-114">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="2ab69-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2ab69-115">Optional element.</span></span><br /><br /> <span data-ttu-id="2ab69-116">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="2ab69-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="2ab69-117">GroupBy (Format) の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="2ab69-117">ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="2ab69-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2ab69-118">Optional element.</span></span><br /><br /> <span data-ttu-id="2ab69-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="2ab69-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="2ab69-120">GroupBy (Format) の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="2ab69-120">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="2ab69-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2ab69-121">Optional element.</span></span><br /><br /> <span data-ttu-id="2ab69-122">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="2ab69-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="2ab69-123">GroupBy (Format) の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="2ab69-123">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="2ab69-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2ab69-124">Optional element.</span></span><br /><br /> <span data-ttu-id="2ab69-125">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ab69-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2ab69-126">親要素</span><span class="sxs-lookup"><span data-stu-id="2ab69-126">Parent Elements</span></span>

|<span data-ttu-id="2ab69-127">要素</span><span class="sxs-lookup"><span data-stu-id="2ab69-127">Element</span></span>|<span data-ttu-id="2ab69-128">[説明]</span><span class="sxs-lookup"><span data-stu-id="2ab69-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2ab69-129">GroupBy の CustomEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="2ab69-129">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="2ab69-130">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="2ab69-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2ab69-131">コメント</span><span class="sxs-lookup"><span data-stu-id="2ab69-131">Remarks</span></span>

<span data-ttu-id="2ab69-132">選択条件を定義する場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="2ab69-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="2ab69-133">選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="2ab69-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="2ab69-134">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="2ab69-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="2ab69-135">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ab69-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2ab69-136">参照</span><span class="sxs-lookup"><span data-stu-id="2ab69-136">See Also</span></span>

[<span data-ttu-id="2ab69-137">CustomControl for ビュー (Format) の SelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="2ab69-137">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="2ab69-138">CustomControl for ビュー (Format) の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="2ab69-138">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="2ab69-139">View (Format) のカスタムコントロールの SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="2ab69-139">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="2ab69-140">GroupBy (Format) の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="2ab69-140">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="2ab69-141">GroupBy の CustomEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="2ab69-141">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="2ab69-142">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="2ab69-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
