---
ms.date: 09/13/2016
ms.topic: reference
title: ListControl の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)
description: ListControl の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)
ms.openlocfilehash: ec7691358d0ff3758411317a349221e1704a1895
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659914"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="49837-103">ListControl の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="49837-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="49837-104">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="49837-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="49837-105">このスクリプトがに評価されると、 `true` 条件が満たされ、リストエントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="49837-105">When this script is evaluated to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="49837-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries Element (format) ListEntry Element (format) ListEntry (format) の SelectionCondition 要素を ListEntry (Format) の selectioncondition for entryselectedby on ListEntry (Format) 用に指定します。</span><span class="sxs-lookup"><span data-stu-id="49837-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="49837-107">構文</span><span class="sxs-lookup"><span data-stu-id="49837-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="49837-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="49837-108">Attributes and Elements</span></span>

<span data-ttu-id="49837-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="49837-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="49837-110">属性</span><span class="sxs-lookup"><span data-stu-id="49837-110">Attributes</span></span>

<span data-ttu-id="49837-111">なし。</span><span class="sxs-lookup"><span data-stu-id="49837-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="49837-112">子要素</span><span class="sxs-lookup"><span data-stu-id="49837-112">Child Elements</span></span>

<span data-ttu-id="49837-113">なし。</span><span class="sxs-lookup"><span data-stu-id="49837-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="49837-114">親要素</span><span class="sxs-lookup"><span data-stu-id="49837-114">Parent Elements</span></span>

|<span data-ttu-id="49837-115">要素</span><span class="sxs-lookup"><span data-stu-id="49837-115">Element</span></span>|<span data-ttu-id="49837-116">説明</span><span class="sxs-lookup"><span data-stu-id="49837-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="49837-117">ListEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="49837-117">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="49837-118">このリストエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="49837-118">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="49837-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="49837-119">Text Value</span></span>

<span data-ttu-id="49837-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="49837-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="49837-121">解説</span><span class="sxs-lookup"><span data-stu-id="49837-121">Remarks</span></span>

<span data-ttu-id="49837-122">選択条件には、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="49837-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="49837-123">(選択条件を使用する方法の詳細については、「 [ビューエントリまたはアイテムが使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="49837-123">(For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).)</span></span>

<span data-ttu-id="49837-124">リストビューのその他のコンポーネントの詳細については、「 [リストビュー](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49837-124">For more information about the other components of a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="49837-125">参照</span><span class="sxs-lookup"><span data-stu-id="49837-125">See Also</span></span>

[<span data-ttu-id="49837-126">ListEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="49837-126">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="49837-127">ListEntry (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="49837-127">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="49837-128">ListEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="49837-128">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="49837-129">リストビュー</span><span class="sxs-lookup"><span data-stu-id="49837-129">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="49837-130">ビューエントリまたはアイテムが使用される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="49837-130">Defining Conditions for when a View Entry or Item is Used</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="49837-131">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="49837-131">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
