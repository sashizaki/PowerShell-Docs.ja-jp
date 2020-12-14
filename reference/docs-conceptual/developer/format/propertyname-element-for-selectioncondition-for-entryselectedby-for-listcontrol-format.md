---
ms.date: 09/13/2016
ms.topic: reference
title: ListControl の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)
description: ListControl の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)
ms.openlocfilehash: 1e318e3a29f07b157b9ae7343ba08759db8efbb5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665823"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="90c09-103">ListControl の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="90c09-103">PropertyName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="90c09-104">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="90c09-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="90c09-105">このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、リストエントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="90c09-105">When this property is present or when it evaluates to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="90c09-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries Element (format) ListEntry Element (format) ListEntry (format) の SelectionCondition 要素を ListEntry (Format) の selectioncondition 要素に指定します。 EntrySelectedBy on ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="90c09-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="90c09-107">構文</span><span class="sxs-lookup"><span data-stu-id="90c09-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="90c09-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="90c09-108">Attributes and Elements</span></span>

<span data-ttu-id="90c09-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="90c09-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="90c09-110">属性</span><span class="sxs-lookup"><span data-stu-id="90c09-110">Attributes</span></span>

<span data-ttu-id="90c09-111">なし。</span><span class="sxs-lookup"><span data-stu-id="90c09-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="90c09-112">子要素</span><span class="sxs-lookup"><span data-stu-id="90c09-112">Child Elements</span></span>

<span data-ttu-id="90c09-113">なし。</span><span class="sxs-lookup"><span data-stu-id="90c09-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="90c09-114">親要素</span><span class="sxs-lookup"><span data-stu-id="90c09-114">Parent Elements</span></span>

|<span data-ttu-id="90c09-115">要素</span><span class="sxs-lookup"><span data-stu-id="90c09-115">Element</span></span>|<span data-ttu-id="90c09-116">説明</span><span class="sxs-lookup"><span data-stu-id="90c09-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="90c09-117">ListEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="90c09-117">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="90c09-118">このリストエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="90c09-118">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="90c09-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="90c09-119">Text Value</span></span>

<span data-ttu-id="90c09-120">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="90c09-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="90c09-121">解説</span><span class="sxs-lookup"><span data-stu-id="90c09-121">Remarks</span></span>

<span data-ttu-id="90c09-122">選択条件では、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="90c09-122">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="90c09-123">選択条件の使用方法の詳細については、「 [ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c09-123">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="90c09-124">リストビューのその他のコンポーネントの詳細については、「 [リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c09-124">For more information about other components of a list view, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="90c09-125">参照</span><span class="sxs-lookup"><span data-stu-id="90c09-125">See Also</span></span>

[<span data-ttu-id="90c09-126">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="90c09-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="90c09-127">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="90c09-127">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="90c09-128">ListEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="90c09-128">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="90c09-129">ListEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="90c09-129">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="90c09-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="90c09-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
