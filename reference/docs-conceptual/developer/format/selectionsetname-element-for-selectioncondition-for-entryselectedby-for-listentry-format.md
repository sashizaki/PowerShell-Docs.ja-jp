---
ms.date: 09/13/2016
ms.topic: reference
title: ListEntry の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)
description: ListEntry の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)
ms.openlocfilehash: f3193799e67706eb07f0fe1c2cd42cce83f7af57
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651542"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format"></a><span data-ttu-id="f7eb2-103">ListEntry の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f7eb2-103">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

<span data-ttu-id="f7eb2-104">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7eb2-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="f7eb2-105">このセット内のいずれかの型が存在する場合、条件が満たされ、リストビューのこの定義を使用してオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7eb2-105">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the list view.</span></span>

<span data-ttu-id="f7eb2-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries Element (format) ListEntry Element (format) ListEntry (format) の SelectionCondition 要素を ListEntry (Format) SelectionSetName 要素の entryselectedby for ListEntry (Format) の SelectionCondition に指定します。</span><span class="sxs-lookup"><span data-stu-id="f7eb2-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f7eb2-107">構文</span><span class="sxs-lookup"><span data-stu-id="f7eb2-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f7eb2-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f7eb2-108">Attributes and Elements</span></span>

<span data-ttu-id="f7eb2-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="f7eb2-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f7eb2-110">属性</span><span class="sxs-lookup"><span data-stu-id="f7eb2-110">Attributes</span></span>

<span data-ttu-id="f7eb2-111">なし。</span><span class="sxs-lookup"><span data-stu-id="f7eb2-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f7eb2-112">子要素</span><span class="sxs-lookup"><span data-stu-id="f7eb2-112">Child Elements</span></span>

<span data-ttu-id="f7eb2-113">なし。</span><span class="sxs-lookup"><span data-stu-id="f7eb2-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f7eb2-114">親要素</span><span class="sxs-lookup"><span data-stu-id="f7eb2-114">Parent Elements</span></span>

|<span data-ttu-id="f7eb2-115">要素</span><span class="sxs-lookup"><span data-stu-id="f7eb2-115">Element</span></span>|<span data-ttu-id="f7eb2-116">説明</span><span class="sxs-lookup"><span data-stu-id="f7eb2-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f7eb2-117">ListEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="f7eb2-117">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="f7eb2-118">リストビューのこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="f7eb2-118">Defines the condition that must exist to use this definition of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f7eb2-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="f7eb2-119">Text Value</span></span>

<span data-ttu-id="f7eb2-120">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7eb2-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="f7eb2-121">解説</span><span class="sxs-lookup"><span data-stu-id="f7eb2-121">Remarks</span></span>

<span data-ttu-id="f7eb2-122">選択条件では、選択セットまたは .NET 型を指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f7eb2-122">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="f7eb2-123">選択条件の使用方法の詳細については、「 [データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7eb2-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="f7eb2-124">選択セットは、書式設定ファイルによって定義される任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="f7eb2-124">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="f7eb2-125">選択セットの作成と参照の詳細については、「 [オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7eb2-125">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="f7eb2-126">リストビューのその他のコンポーネントの詳細については、「 [リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7eb2-126">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f7eb2-127">参照</span><span class="sxs-lookup"><span data-stu-id="f7eb2-127">See Also</span></span>

[<span data-ttu-id="f7eb2-128">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="f7eb2-128">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="f7eb2-129">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="f7eb2-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="f7eb2-130">ListEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="f7eb2-130">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="f7eb2-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="f7eb2-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
