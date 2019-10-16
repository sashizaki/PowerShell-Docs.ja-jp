---
title: ListControl (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71c3f1f6-6fe2-42f1-8260-6974d3871748
caps.latest.revision: 11
ms.openlocfilehash: 7d526372cf80327b3fb9b79b6e83429c57780183
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362291"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="4b598-102">ListControl の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4b598-102">PropertyName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="4b598-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="4b598-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="4b598-104">このプロパティが存在する場合、または `true` と評価された場合、条件が満たされ、リストエントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="4b598-104">When this property is present or when it evaluates to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="4b598-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (形式) ListEntries Element (format) ListEntry Element (format) ListEntry (Format) SelectionCondition 要素のエントリEntryselectedby for ListEntry (Format) PropertyName Element for EntrySelectedBy for ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="4b598-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4b598-106">構文</span><span class="sxs-lookup"><span data-stu-id="4b598-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4b598-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="4b598-107">Attributes and Elements</span></span>

<span data-ttu-id="4b598-108">次のセクションでは、属性、子要素、`PropertyName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b598-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4b598-109">属性</span><span class="sxs-lookup"><span data-stu-id="4b598-109">Attributes</span></span>

<span data-ttu-id="4b598-110">なし。</span><span class="sxs-lookup"><span data-stu-id="4b598-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4b598-111">子要素</span><span class="sxs-lookup"><span data-stu-id="4b598-111">Child Elements</span></span>

<span data-ttu-id="4b598-112">なし。</span><span class="sxs-lookup"><span data-stu-id="4b598-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4b598-113">親要素</span><span class="sxs-lookup"><span data-stu-id="4b598-113">Parent Elements</span></span>

|<span data-ttu-id="4b598-114">要素</span><span class="sxs-lookup"><span data-stu-id="4b598-114">Element</span></span>|<span data-ttu-id="4b598-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="4b598-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4b598-116">ListEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="4b598-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="4b598-117">このリストエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="4b598-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4b598-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="4b598-118">Text Value</span></span>

<span data-ttu-id="4b598-119">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4b598-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="4b598-120">コメント</span><span class="sxs-lookup"><span data-stu-id="4b598-120">Remarks</span></span>

<span data-ttu-id="4b598-121">選択条件では、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="4b598-121">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="4b598-122">選択条件の使用方法の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b598-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="4b598-123">リストビューのその他のコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b598-123">For more information about other components of a list view, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4b598-124">参照</span><span class="sxs-lookup"><span data-stu-id="4b598-124">See Also</span></span>

[<span data-ttu-id="4b598-125">リストビューの作成</span><span class="sxs-lookup"><span data-stu-id="4b598-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="4b598-126">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="4b598-126">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="4b598-127">ListEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="4b598-127">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="4b598-128">ListEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="4b598-128">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="4b598-129">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="4b598-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
