---
title: ListControl (Format) の EntrySelectedBy の SelectionCondition 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7649d5d0-2b56-49b5-a670-dde46caca343
caps.latest.revision: 11
ms.openlocfilehash: 7150b29ad84dfb587215ee3e64c356adbd5a6305
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74417542"
---
# <a name="selectioncondition-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="137bb-102">ListControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="137bb-102">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="137bb-103">リストビューのこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="137bb-103">Defines the condition that must exist to use this definition of the list view.</span></span> <span data-ttu-id="137bb-104">リスト定義に指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="137bb-104">There is no limit to the number of selection conditions that can be specified for a list definition.</span></span>

<span data-ttu-id="137bb-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (形式) ListEntries Element (format) ListEntry Element (format) ListEntry (Format) SelectionCondition 要素のエントリListEntry の EntrySelectedBy (形式)</span><span class="sxs-lookup"><span data-stu-id="137bb-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="137bb-106">構文</span><span class="sxs-lookup"><span data-stu-id="137bb-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="137bb-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="137bb-107">Attributes and Elements</span></span>

<span data-ttu-id="137bb-108">次のセクションでは、`SelectionCondition` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="137bb-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="137bb-109">属性</span><span class="sxs-lookup"><span data-stu-id="137bb-109">Attributes</span></span>

<span data-ttu-id="137bb-110">なし。</span><span class="sxs-lookup"><span data-stu-id="137bb-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="137bb-111">子要素</span><span class="sxs-lookup"><span data-stu-id="137bb-111">Child Elements</span></span>

|<span data-ttu-id="137bb-112">要素</span><span class="sxs-lookup"><span data-stu-id="137bb-112">Element</span></span>|<span data-ttu-id="137bb-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="137bb-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="137bb-114">ListEntry (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="137bb-114">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="137bb-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="137bb-115">Optional element.</span></span><br /><br /> <span data-ttu-id="137bb-116">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="137bb-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="137bb-117">ListEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="137bb-117">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="137bb-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="137bb-118">Optional element.</span></span><br /><br /> <span data-ttu-id="137bb-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="137bb-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="137bb-120">EntrySelectedBy for ListEntry (Format) の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="137bb-120">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)|<span data-ttu-id="137bb-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="137bb-121">Optional element.</span></span><br /><br /> <span data-ttu-id="137bb-122">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="137bb-122">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="137bb-123">ListEntry (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="137bb-123">TypeName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="137bb-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="137bb-124">Optional element.</span></span><br /><br /> <span data-ttu-id="137bb-125">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="137bb-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="137bb-126">親要素</span><span class="sxs-lookup"><span data-stu-id="137bb-126">Parent Elements</span></span>

|<span data-ttu-id="137bb-127">要素</span><span class="sxs-lookup"><span data-stu-id="137bb-127">Element</span></span>|<span data-ttu-id="137bb-128">[説明]</span><span class="sxs-lookup"><span data-stu-id="137bb-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="137bb-129">TableRowEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="137bb-129">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="137bb-130">このテーブルエントリを使用する .NET 型、またはこのエントリを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="137bb-130">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="137bb-131">コメント</span><span class="sxs-lookup"><span data-stu-id="137bb-131">Remarks</span></span>

<span data-ttu-id="137bb-132">選択条件を定義する場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="137bb-132">lWhen you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="137bb-133">選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="137bb-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="137bb-134">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="137bb-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="137bb-135">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="137bb-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="137bb-136">リストビューのその他のコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="137bb-136">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="137bb-137">参照</span><span class="sxs-lookup"><span data-stu-id="137bb-137">See Also</span></span>

[<span data-ttu-id="137bb-138">リストビューの作成</span><span class="sxs-lookup"><span data-stu-id="137bb-138">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="137bb-139">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="137bb-139">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="137bb-140">ListEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="137bb-140">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="137bb-141">ListEntry (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="137bb-141">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="137bb-142">ListEntry (Format) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="137bb-142">TypeName Element for EntrySelectedBy for ListEntry (Format)</span></span>](/powershell/scripting/developer/format/typename-element-for-entryselectedby-for-listcontrol-format)

[<span data-ttu-id="137bb-143">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="137bb-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
