---
title: WideControl (Format) の EntrySelectedBy の SelectionCondition 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7a9f086-b1ca-4400-9be7-9ec1ec8880f3
caps.latest.revision: 11
ms.openlocfilehash: f20679e3392b99a049c075f24c7712262bab08e1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364781"
---
# <a name="selectioncondition-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="bef62-102">WideControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bef62-102">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="bef62-103">この定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="bef62-103">Defines the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="bef62-104">ワイドエントリの定義に指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="bef62-104">There is no limit to the number of selection conditions that can be specified for a wide entry definition.</span></span>

<span data-ttu-id="bef62-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideEntry (Format) SelectionCondition 要素の (Format) 項目の EntrySelectedBy 要素WideEntry の EntrySelectedBy (形式)</span><span class="sxs-lookup"><span data-stu-id="bef62-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bef62-106">構文</span><span class="sxs-lookup"><span data-stu-id="bef62-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bef62-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="bef62-107">Attributes and Elements</span></span>

<span data-ttu-id="bef62-108">次のセクションでは、属性、子要素、`SelectionCondition` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bef62-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="bef62-109">1つの `PropertyName` または `ScriptBlock` の要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bef62-109">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="bef62-110">@No__t-0 および `TypeName` の要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="bef62-110">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="bef62-111">いずれかの要素を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bef62-111">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bef62-112">属性</span><span class="sxs-lookup"><span data-stu-id="bef62-112">Attributes</span></span>

<span data-ttu-id="bef62-113">なし。</span><span class="sxs-lookup"><span data-stu-id="bef62-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bef62-114">子要素</span><span class="sxs-lookup"><span data-stu-id="bef62-114">Child Elements</span></span>

|<span data-ttu-id="bef62-115">要素</span><span class="sxs-lookup"><span data-stu-id="bef62-115">Element</span></span>|<span data-ttu-id="bef62-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="bef62-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bef62-117">WideEntry (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="bef62-117">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="bef62-118">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="bef62-118">Optional element.</span></span><br /><br /> <span data-ttu-id="bef62-119">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="bef62-119">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="bef62-120">WideEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="bef62-120">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="bef62-121">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="bef62-121">Optional element.</span></span><br /><br /> <span data-ttu-id="bef62-122">条件をトリガーするスクリプトブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="bef62-122">Specifies the script block that triggers the condition.</span></span>|
|[<span data-ttu-id="bef62-123">EntrySelectedBy for WideEntry (Format) の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="bef62-123">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="bef62-124">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="bef62-124">Optional element.</span></span><br /><br /> <span data-ttu-id="bef62-125">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="bef62-125">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="bef62-126">WideEntry (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="bef62-126">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="bef62-127">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="bef62-127">Optional element.</span></span><br /><br /> <span data-ttu-id="bef62-128">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="bef62-128">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bef62-129">親要素</span><span class="sxs-lookup"><span data-stu-id="bef62-129">Parent Elements</span></span>

|<span data-ttu-id="bef62-130">要素</span><span class="sxs-lookup"><span data-stu-id="bef62-130">Element</span></span>|<span data-ttu-id="bef62-131">[説明]</span><span class="sxs-lookup"><span data-stu-id="bef62-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bef62-132">WideEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bef62-132">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="bef62-133">このワイドエントリを使用する .NET 型、またはこのエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="bef62-133">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bef62-134">コメント</span><span class="sxs-lookup"><span data-stu-id="bef62-134">Remarks</span></span>

<span data-ttu-id="bef62-135">各ワイドエントリには、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bef62-135">Each wide entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="bef62-136">選択条件を定義する場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="bef62-136">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="bef62-137">選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="bef62-137">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="bef62-138">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="bef62-138">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="bef62-139">選択条件の使用方法の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bef62-139">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="bef62-140">ワイドビューのその他のコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bef62-140">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bef62-141">参照</span><span class="sxs-lookup"><span data-stu-id="bef62-141">See Also</span></span>

[<span data-ttu-id="bef62-142">ワイドビューの作成</span><span class="sxs-lookup"><span data-stu-id="bef62-142">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="bef62-143">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="bef62-143">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="bef62-144">WideEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bef62-144">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="bef62-145">WideEntry (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="bef62-145">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="bef62-146">WideEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="bef62-146">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="bef62-147">EntrySelectedBy for WideEntry (Format) の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="bef62-147">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="bef62-148">WideEntry (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="bef62-148">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="bef62-149">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="bef62-149">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
