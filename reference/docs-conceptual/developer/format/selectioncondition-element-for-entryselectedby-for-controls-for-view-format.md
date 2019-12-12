---
title: ビュー (Format) のコントロールに対する EntrySelectedBy の SelectionCondition 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2623407e-fa10-4d27-a804-204f6d50ef22
caps.latest.revision: 6
ms.openlocfilehash: ea15e647a9dd7a7064718a0c536c4a3178d62d95
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362051"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="c4ed8-102">View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c4ed8-102">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="c4ed8-103">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="c4ed8-103">Defines a condition that must exist for the control definition to be used.</span></span> <span data-ttu-id="c4ed8-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4ed8-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="c4ed8-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素ビュー用のコントロールの CustomControl (書式) の CustomEntry 要素のコントロール用のカスタムエントリのためのコントロールのためのコントロールのためのコントロールのためのコントロールのための、ビューのコントロールの EntrySelectedBy の SelectionCondition 要素を表示するためのコントロール (形式</span><span class="sxs-lookup"><span data-stu-id="c4ed8-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c4ed8-106">構文</span><span class="sxs-lookup"><span data-stu-id="c4ed8-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c4ed8-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="c4ed8-107">Attributes and Elements</span></span>

<span data-ttu-id="c4ed8-108">次のセクションでは、`SelectionCondition` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4ed8-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c4ed8-109">属性</span><span class="sxs-lookup"><span data-stu-id="c4ed8-109">Attributes</span></span>

<span data-ttu-id="c4ed8-110">なし。</span><span class="sxs-lookup"><span data-stu-id="c4ed8-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c4ed8-111">子要素</span><span class="sxs-lookup"><span data-stu-id="c4ed8-111">Child Elements</span></span>

|<span data-ttu-id="c4ed8-112">要素</span><span class="sxs-lookup"><span data-stu-id="c4ed8-112">Element</span></span>|<span data-ttu-id="c4ed8-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="c4ed8-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c4ed8-114">ビューのコントロールの SelectionCondition の PropertyName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c4ed8-114">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="c4ed8-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c4ed8-115">Optional element.</span></span><br /><br /> <span data-ttu-id="c4ed8-116">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4ed8-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="c4ed8-117">ビューのコントロールの SelectionCondition の ScriptBlock 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c4ed8-117">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="c4ed8-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c4ed8-118">Optional element.</span></span><br /><br /> <span data-ttu-id="c4ed8-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4ed8-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="c4ed8-120">ビューのコントロール (Format) の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="c4ed8-120">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="c4ed8-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c4ed8-121">Optional element.</span></span><br /><br /> <span data-ttu-id="c4ed8-122">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4ed8-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="c4ed8-123">ビューのコントロールの SelectionCondition の TypeName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c4ed8-123">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="c4ed8-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c4ed8-124">Optional element.</span></span><br /><br /> <span data-ttu-id="c4ed8-125">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="c4ed8-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c4ed8-126">親要素</span><span class="sxs-lookup"><span data-stu-id="c4ed8-126">Parent Elements</span></span>

|<span data-ttu-id="c4ed8-127">要素</span><span class="sxs-lookup"><span data-stu-id="c4ed8-127">Element</span></span>|<span data-ttu-id="c4ed8-128">[説明]</span><span class="sxs-lookup"><span data-stu-id="c4ed8-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c4ed8-129">ビューのコントロールに対する CustomEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c4ed8-129">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="c4ed8-130">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="c4ed8-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c4ed8-131">コメント</span><span class="sxs-lookup"><span data-stu-id="c4ed8-131">Remarks</span></span>

<span data-ttu-id="c4ed8-132">選択条件を定義する場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c4ed8-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="c4ed8-133">選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c4ed8-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="c4ed8-134">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c4ed8-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="c4ed8-135">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4ed8-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c4ed8-136">参照</span><span class="sxs-lookup"><span data-stu-id="c4ed8-136">See Also</span></span>

[<span data-ttu-id="c4ed8-137">ビューのコントロールの SelectionCondition の PropertyName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c4ed8-137">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="c4ed8-138">ビューのコントロールの SelectionCondition の ScriptBlock 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c4ed8-138">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="c4ed8-139">ビューのコントロール (Format) の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="c4ed8-139">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="c4ed8-140">ビューのコントロールの SelectionCondition の TypeName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c4ed8-140">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="c4ed8-141">ビューのコントロールに対する CustomEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c4ed8-141">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="c4ed8-142">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="c4ed8-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
