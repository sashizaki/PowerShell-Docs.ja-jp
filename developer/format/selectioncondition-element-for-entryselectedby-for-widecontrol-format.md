---
title: WideControl (形式) の EntrySelectedBy SelectionCondition 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7a9f086-b1ca-4400-9be7-9ec1ec8880f3
caps.latest.revision: 11
ms.openlocfilehash: f20679e3392b99a049c075f24c7712262bab08e1
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854118"
---
# <a name="selectioncondition-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="3fbd6-102">WideControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3fbd6-102">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="3fbd6-103">この定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-103">Defines the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="3fbd6-104">ワイド エントリの定義に指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-104">There is no limit to the number of selection conditions that can be specified for a wide entry definition.</span></span>

<span data-ttu-id="3fbd6-105">構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式) EntrySelectedBy 要素の WideEntry (形式) SelectionCondition 要素EntrySelectedBy WideEntry (形式) の</span><span class="sxs-lookup"><span data-stu-id="3fbd6-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3fbd6-106">構文</span><span class="sxs-lookup"><span data-stu-id="3fbd6-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3fbd6-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="3fbd6-107">Attributes and Elements</span></span>

<span data-ttu-id="3fbd6-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionCondition`要素。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="3fbd6-109">1 つを指定する必要があります`PropertyName`または`ScriptBlock`要素。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-109">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="3fbd6-110">`SelectionSetName`と`TypeName`要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-110">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="3fbd6-111">要素のいずれかのいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-111">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3fbd6-112">属性</span><span class="sxs-lookup"><span data-stu-id="3fbd6-112">Attributes</span></span>

<span data-ttu-id="3fbd6-113">なし。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3fbd6-114">子要素</span><span class="sxs-lookup"><span data-stu-id="3fbd6-114">Child Elements</span></span>

|<span data-ttu-id="3fbd6-115">要素</span><span class="sxs-lookup"><span data-stu-id="3fbd6-115">Element</span></span>|<span data-ttu-id="3fbd6-116">説明</span><span class="sxs-lookup"><span data-stu-id="3fbd6-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3fbd6-117">SelectionCondition EntrySelectedBy WideEntry (形式) のための PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="3fbd6-117">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="3fbd6-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-118">Optional element.</span></span><br /><br /> <span data-ttu-id="3fbd6-119">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-119">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="3fbd6-120">SelectionCondition EntrySelectedBy WideEntry (形式) のためのスクリプト ブロックの要素</span><span class="sxs-lookup"><span data-stu-id="3fbd6-120">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="3fbd6-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-121">Optional element.</span></span><br /><br /> <span data-ttu-id="3fbd6-122">条件をトリガーするスクリプト ブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-122">Specifies the script block that triggers the condition.</span></span>|
|[<span data-ttu-id="3fbd6-123">EntrySelectedBy WideEntry (形式) 用の SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3fbd6-123">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="3fbd6-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-124">Optional element.</span></span><br /><br /> <span data-ttu-id="3fbd6-125">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-125">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="3fbd6-126">SelectionCondition EntrySelectedBy WideEntry (形式) のための TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="3fbd6-126">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="3fbd6-127">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-127">Optional element.</span></span><br /><br /> <span data-ttu-id="3fbd6-128">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-128">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3fbd6-129">親要素</span><span class="sxs-lookup"><span data-stu-id="3fbd6-129">Parent Elements</span></span>

|<span data-ttu-id="3fbd6-130">要素</span><span class="sxs-lookup"><span data-stu-id="3fbd6-130">Element</span></span>|<span data-ttu-id="3fbd6-131">説明</span><span class="sxs-lookup"><span data-stu-id="3fbd6-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3fbd6-132">WideEntry (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="3fbd6-132">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="3fbd6-133">このワイド エントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-133">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3fbd6-134">コメント</span><span class="sxs-lookup"><span data-stu-id="3fbd6-134">Remarks</span></span>

<span data-ttu-id="3fbd6-135">少なくとも 1 つの型名、選択範囲のセット、または選択条件が定義されている各ワイド エントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-135">Each wide entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="3fbd6-136">選択条件を定義している場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-136">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="3fbd6-137">選択条件では、少なくとも 1 つのプロパティ名またはスクリプト ブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-137">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="3fbd6-138">選択条件が .NET 型の任意の数を指定するか、選択範囲を設定するが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-138">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="3fbd6-139">選択条件を使用する方法の詳細については、次を参照してください。[とビューのエントリの定義の条件またはアイテムが使用されて](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-139">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="3fbd6-140">ワイド ビューの他のコンポーネントに関する詳細については、次を参照してください。[ワイド ビューを作成する](./creating-a-wide-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-140">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3fbd6-141">参照</span><span class="sxs-lookup"><span data-stu-id="3fbd6-141">See Also</span></span>

[<span data-ttu-id="3fbd6-142">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="3fbd6-142">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="3fbd6-143">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="3fbd6-143">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="3fbd6-144">WideEntry (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="3fbd6-144">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="3fbd6-145">SelectionCondition EntrySelectedBy WideEntry (形式) のための PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="3fbd6-145">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="3fbd6-146">SelectionCondition EntrySelectedBy WideEntry (形式) のためのスクリプト ブロックの要素</span><span class="sxs-lookup"><span data-stu-id="3fbd6-146">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="3fbd6-147">EntrySelectedBy WideEntry (形式) 用の SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="3fbd6-147">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="3fbd6-148">SelectionCondition EntrySelectedBy WideEntry (形式) のための TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="3fbd6-148">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="3fbd6-149">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="3fbd6-149">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
