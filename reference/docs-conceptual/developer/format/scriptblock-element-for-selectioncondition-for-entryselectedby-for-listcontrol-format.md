---
title: ListControl (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a1adad7-e864-4892-9d26-a6476a9698d2
caps.latest.revision: 7
ms.openlocfilehash: b65d953169f6daf15fb617ce4d0303cf4cb584ee
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368591"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="7711d-102">ListControl の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7711d-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="7711d-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7711d-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="7711d-104">このスクリプトが `true` に評価されると、条件が満たされ、リストエントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="7711d-104">When this script is evaluated to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="7711d-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (形式) ListEntries Element (format) ListEntry Element (format) ListEntry (Format) SelectionCondition 要素のエントリEntryselectedby for ListEntry (Format) の SelectionCondition に使用する EntrySelectedBy for ListEntry (Format) ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="7711d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7711d-106">構文</span><span class="sxs-lookup"><span data-stu-id="7711d-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7711d-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="7711d-107">Attributes and Elements</span></span>

<span data-ttu-id="7711d-108">次のセクションでは、属性、子要素、`ScriptBlock` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7711d-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7711d-109">属性</span><span class="sxs-lookup"><span data-stu-id="7711d-109">Attributes</span></span>

<span data-ttu-id="7711d-110">なし。</span><span class="sxs-lookup"><span data-stu-id="7711d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7711d-111">子要素</span><span class="sxs-lookup"><span data-stu-id="7711d-111">Child Elements</span></span>

<span data-ttu-id="7711d-112">なし。</span><span class="sxs-lookup"><span data-stu-id="7711d-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7711d-113">親要素</span><span class="sxs-lookup"><span data-stu-id="7711d-113">Parent Elements</span></span>

|<span data-ttu-id="7711d-114">要素</span><span class="sxs-lookup"><span data-stu-id="7711d-114">Element</span></span>|<span data-ttu-id="7711d-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="7711d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7711d-116">ListEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="7711d-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="7711d-117">このリストエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="7711d-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7711d-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="7711d-118">Text Value</span></span>

<span data-ttu-id="7711d-119">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7711d-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="7711d-120">コメント</span><span class="sxs-lookup"><span data-stu-id="7711d-120">Remarks</span></span>

<span data-ttu-id="7711d-121">選択条件には、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="7711d-121">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="7711d-122">(選択条件を使用する方法の詳細については、「[ビューエントリまたはアイテムが使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="7711d-122">(For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).)</span></span>

<span data-ttu-id="7711d-123">リストビューのその他のコンポーネントの詳細については、「[リストビュー](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7711d-123">For more information about the other components of a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7711d-124">参照</span><span class="sxs-lookup"><span data-stu-id="7711d-124">See Also</span></span>

[<span data-ttu-id="7711d-125">ListEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="7711d-125">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="7711d-126">ListEntry (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="7711d-126">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="7711d-127">ListEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="7711d-127">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="7711d-128">リストビュー</span><span class="sxs-lookup"><span data-stu-id="7711d-128">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="7711d-129">ビューエントリまたはアイテムが使用される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="7711d-129">Defining Conditions for when a View Entry or Item is Used</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="7711d-130">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="7711d-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)