---
title: ビュー (Format) のコントロールに対する EntrySelectedBy の SelectionCondition 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1c14b2638249bdbfe25f7a96e917d66ea10ed239
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787582"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="21626-102">View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="21626-102">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="21626-103">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="21626-103">Defines a condition that must exist for the control definition to be used.</span></span> <span data-ttu-id="21626-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="21626-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="21626-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールのコントロールに対して、ビューのコントロールの要素 (形式) コントロール要素 (format) コントロールの要素 (書式) を制御するためのコントロール要素 (書式) の CustomControl 要素 (形式) に対して、コントロールの CustomControl view (format) CustomEntry 要素を使用して、ビュー (format) のコントロールに対して、参照 (format) の項目を表示するためのコントロールの参照 (format) SelectionCondition 要素を表示するためのコントロールに対して、EntrySelectedBy を使用します。</span><span class="sxs-lookup"><span data-stu-id="21626-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="21626-106">構文</span><span class="sxs-lookup"><span data-stu-id="21626-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="21626-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="21626-107">Attributes and Elements</span></span>

<span data-ttu-id="21626-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="21626-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="21626-109">属性</span><span class="sxs-lookup"><span data-stu-id="21626-109">Attributes</span></span>

<span data-ttu-id="21626-110">なし。</span><span class="sxs-lookup"><span data-stu-id="21626-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="21626-111">子要素</span><span class="sxs-lookup"><span data-stu-id="21626-111">Child Elements</span></span>

|<span data-ttu-id="21626-112">要素</span><span class="sxs-lookup"><span data-stu-id="21626-112">Element</span></span>|<span data-ttu-id="21626-113">説明</span><span class="sxs-lookup"><span data-stu-id="21626-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="21626-114">View の Controls の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="21626-114">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="21626-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="21626-115">Optional element.</span></span><br /><br /> <span data-ttu-id="21626-116">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="21626-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="21626-117">View の Controls の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="21626-117">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="21626-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="21626-118">Optional element.</span></span><br /><br /> <span data-ttu-id="21626-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="21626-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="21626-120">View の Controls の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="21626-120">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="21626-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="21626-121">Optional element.</span></span><br /><br /> <span data-ttu-id="21626-122">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="21626-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="21626-123">View の Controls の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="21626-123">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="21626-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="21626-124">Optional element.</span></span><br /><br /> <span data-ttu-id="21626-125">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="21626-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="21626-126">親要素</span><span class="sxs-lookup"><span data-stu-id="21626-126">Parent Elements</span></span>

|<span data-ttu-id="21626-127">要素</span><span class="sxs-lookup"><span data-stu-id="21626-127">Element</span></span>|<span data-ttu-id="21626-128">説明</span><span class="sxs-lookup"><span data-stu-id="21626-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="21626-129">View の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="21626-129">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="21626-130">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="21626-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="21626-131">解説</span><span class="sxs-lookup"><span data-stu-id="21626-131">Remarks</span></span>

<span data-ttu-id="21626-132">選択条件を定義する場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="21626-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="21626-133">選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="21626-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="21626-134">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="21626-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="21626-135">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21626-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="21626-136">参照</span><span class="sxs-lookup"><span data-stu-id="21626-136">See Also</span></span>

[<span data-ttu-id="21626-137">View の Controls の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="21626-137">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="21626-138">View の Controls の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="21626-138">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="21626-139">View の Controls の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="21626-139">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="21626-140">View の Controls の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="21626-140">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="21626-141">View の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="21626-141">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="21626-142">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="21626-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
