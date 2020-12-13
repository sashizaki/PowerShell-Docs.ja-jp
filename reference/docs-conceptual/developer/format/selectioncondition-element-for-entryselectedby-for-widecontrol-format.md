---
ms.date: 09/13/2016
ms.topic: reference
title: WideControl の EntrySelectedBy の SelectionCondition 要素 (書式)
description: WideControl の EntrySelectedBy の SelectionCondition 要素 (書式)
ms.openlocfilehash: 8c51ca72edc6ad174dc289c61a8987e8f9495d19
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655119"
---
# <a name="selectioncondition-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="f51d8-103">WideControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f51d8-103">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="f51d8-104">この定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="f51d8-104">Defines the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="f51d8-105">ワイドエントリの定義に指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="f51d8-105">There is no limit to the number of selection conditions that can be specified for a wide entry definition.</span></span>

<span data-ttu-id="f51d8-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideEntry (Format) の (Format) SelectionCondition 要素の EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f51d8-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f51d8-107">構文</span><span class="sxs-lookup"><span data-stu-id="f51d8-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f51d8-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f51d8-108">Attributes and Elements</span></span>

<span data-ttu-id="f51d8-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="f51d8-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="f51d8-110">1つまたは複数の要素を指定する必要があり `PropertyName` `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="f51d8-110">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="f51d8-111">`SelectionSetName`要素と `TypeName` 要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="f51d8-111">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="f51d8-112">いずれかの要素を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f51d8-112">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f51d8-113">属性</span><span class="sxs-lookup"><span data-stu-id="f51d8-113">Attributes</span></span>

<span data-ttu-id="f51d8-114">なし。</span><span class="sxs-lookup"><span data-stu-id="f51d8-114">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f51d8-115">子要素</span><span class="sxs-lookup"><span data-stu-id="f51d8-115">Child Elements</span></span>

|<span data-ttu-id="f51d8-116">要素</span><span class="sxs-lookup"><span data-stu-id="f51d8-116">Element</span></span>|<span data-ttu-id="f51d8-117">説明</span><span class="sxs-lookup"><span data-stu-id="f51d8-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f51d8-118">WideEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f51d8-118">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="f51d8-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f51d8-119">Optional element.</span></span><br /><br /> <span data-ttu-id="f51d8-120">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="f51d8-120">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="f51d8-121">WideEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="f51d8-121">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="f51d8-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f51d8-122">Optional element.</span></span><br /><br /> <span data-ttu-id="f51d8-123">条件をトリガーするスクリプトブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="f51d8-123">Specifies the script block that triggers the condition.</span></span>|
|[<span data-ttu-id="f51d8-124">WideEntry の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f51d8-124">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="f51d8-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f51d8-125">Optional element.</span></span><br /><br /> <span data-ttu-id="f51d8-126">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="f51d8-126">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="f51d8-127">WideEntry (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="f51d8-127">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="f51d8-128">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f51d8-128">Optional element.</span></span><br /><br /> <span data-ttu-id="f51d8-129">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="f51d8-129">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f51d8-130">親要素</span><span class="sxs-lookup"><span data-stu-id="f51d8-130">Parent Elements</span></span>

|<span data-ttu-id="f51d8-131">要素</span><span class="sxs-lookup"><span data-stu-id="f51d8-131">Element</span></span>|<span data-ttu-id="f51d8-132">説明</span><span class="sxs-lookup"><span data-stu-id="f51d8-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f51d8-133">WideEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f51d8-133">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="f51d8-134">このワイドエントリを使用する .NET 型、またはこのエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="f51d8-134">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f51d8-135">解説</span><span class="sxs-lookup"><span data-stu-id="f51d8-135">Remarks</span></span>

<span data-ttu-id="f51d8-136">各ワイドエントリには、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f51d8-136">Each wide entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="f51d8-137">選択条件を定義する場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f51d8-137">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="f51d8-138">選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f51d8-138">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="f51d8-139">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f51d8-139">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="f51d8-140">選択条件の使用方法の詳細については、「 [ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f51d8-140">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="f51d8-141">ワイドビューのその他のコンポーネントの詳細については、「 [ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f51d8-141">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f51d8-142">参照</span><span class="sxs-lookup"><span data-stu-id="f51d8-142">See Also</span></span>

[<span data-ttu-id="f51d8-143">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="f51d8-143">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="f51d8-144">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="f51d8-144">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="f51d8-145">WideEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f51d8-145">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="f51d8-146">WideEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f51d8-146">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="f51d8-147">WideEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="f51d8-147">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="f51d8-148">WideEntry の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f51d8-148">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="f51d8-149">WideEntry (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="f51d8-149">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="f51d8-150">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="f51d8-150">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
