---
ms.date: 09/13/2016
ms.topic: reference
title: EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)
description: EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)
ms.openlocfilehash: 3ecf7fde99b9ee66a153eea416792f351ff62af3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647915"
---
# <a name="selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="d4132-103">EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d4132-103">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="d4132-104">この定義のコレクションオブジェクトを展開するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="d4132-104">Defines the condition that must exist to expand the collection objects of this definition.</span></span>

<span data-ttu-id="d4132-105">Configuration 要素 (Format) DefaultSettings Element (format) 列挙 able膨張要素 (format) 列挙 able膨張拡張要素 (format) EntrySelectedBy (format) の Entryselectedby の SelectionCondition 要素を列挙します。</span><span class="sxs-lookup"><span data-stu-id="d4132-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d4132-106">構文</span><span class="sxs-lookup"><span data-stu-id="d4132-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d4132-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d4132-107">Attributes and Elements</span></span>

<span data-ttu-id="d4132-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="d4132-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="d4132-109">1つまたは複数の要素を指定する必要があり `PropertyName` `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="d4132-109">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="d4132-110">`SelectionSetName`要素と `TypeName` 要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d4132-110">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="d4132-111">いずれかの要素を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d4132-111">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d4132-112">属性</span><span class="sxs-lookup"><span data-stu-id="d4132-112">Attributes</span></span>

<span data-ttu-id="d4132-113">なし。</span><span class="sxs-lookup"><span data-stu-id="d4132-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d4132-114">子要素</span><span class="sxs-lookup"><span data-stu-id="d4132-114">Child Elements</span></span>

|<span data-ttu-id="d4132-115">要素</span><span class="sxs-lookup"><span data-stu-id="d4132-115">Element</span></span>|<span data-ttu-id="d4132-116">説明</span><span class="sxs-lookup"><span data-stu-id="d4132-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d4132-117">EnumerableExpansion の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d4132-117">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="d4132-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d4132-118">Optional element.</span></span><br /><br /> <span data-ttu-id="d4132-119">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4132-119">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="d4132-120">EnumerableExpansion の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d4132-120">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="d4132-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d4132-121">Optional element.</span></span><br /><br /> <span data-ttu-id="d4132-122">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4132-122">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="d4132-123">EnumerableExpansion の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d4132-123">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="d4132-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d4132-124">Optional element.</span></span><br /><br /> <span data-ttu-id="d4132-125">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4132-125">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="d4132-126">EnumerableExpansion の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d4132-126">TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="d4132-127">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d4132-127">Optional element.</span></span><br /><br /> <span data-ttu-id="d4132-128">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4132-128">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d4132-129">親要素</span><span class="sxs-lookup"><span data-stu-id="d4132-129">Parent Elements</span></span>

|<span data-ttu-id="d4132-130">要素</span><span class="sxs-lookup"><span data-stu-id="d4132-130">Element</span></span>|<span data-ttu-id="d4132-131">説明</span><span class="sxs-lookup"><span data-stu-id="d4132-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d4132-132">EnumerableExpansion の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d4132-132">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="d4132-133">この定義によって展開される .NET コレクションオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="d4132-133">Defines which .NET collection objects are expanded by this definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d4132-134">解説</span><span class="sxs-lookup"><span data-stu-id="d4132-134">Remarks</span></span>

<span data-ttu-id="d4132-135">各定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4132-135">Each definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="d4132-136">選択条件を定義する場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d4132-136">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="d4132-137">選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d4132-137">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="d4132-138">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d4132-138">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="d4132-139">選択条件の使用方法の詳細については、「 [データの Diplaying の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4132-139">For more information about how to use selection conditions, see [Defining Conditions for Diplaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="d4132-140">ワイドビューのその他のコンポーネントの詳細については、「 [Wide ビュー](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4132-140">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d4132-141">参照</span><span class="sxs-lookup"><span data-stu-id="d4132-141">See Also</span></span>

[<span data-ttu-id="d4132-142">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="d4132-142">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="d4132-143">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="d4132-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
