---
ms.date: 09/13/2016
ms.topic: reference
title: WideEntry の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)
description: WideEntry の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)
ms.openlocfilehash: c6466e3ac6e1f194df9172468d26448f9630da6a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655012"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="46584-103">WideEntry の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="46584-103">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="46584-104">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="46584-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="46584-105">このセット内のいずれかの型が存在する場合、条件が満たされ、このワイドビューの定義を使用してオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="46584-105">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the wide view.</span></span>

<span data-ttu-id="46584-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideEntry (Format) Element (format) EntrySelectedBy for WideEntry (format) SelectionSetName Element for entryselectedby on WideEntry (format) の SelectionCondition の selectioncondition 要素</span><span class="sxs-lookup"><span data-stu-id="46584-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="46584-107">構文</span><span class="sxs-lookup"><span data-stu-id="46584-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="46584-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="46584-108">Attributes and Elements</span></span>

<span data-ttu-id="46584-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="46584-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="46584-110">属性</span><span class="sxs-lookup"><span data-stu-id="46584-110">Attributes</span></span>

<span data-ttu-id="46584-111">なし。</span><span class="sxs-lookup"><span data-stu-id="46584-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="46584-112">子要素</span><span class="sxs-lookup"><span data-stu-id="46584-112">Child Elements</span></span>

<span data-ttu-id="46584-113">なし。</span><span class="sxs-lookup"><span data-stu-id="46584-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="46584-114">親要素</span><span class="sxs-lookup"><span data-stu-id="46584-114">Parent Elements</span></span>

|<span data-ttu-id="46584-115">要素</span><span class="sxs-lookup"><span data-stu-id="46584-115">Element</span></span>|<span data-ttu-id="46584-116">説明</span><span class="sxs-lookup"><span data-stu-id="46584-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="46584-117">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="46584-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="46584-118">この定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="46584-118">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="46584-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="46584-119">Text Value</span></span>

<span data-ttu-id="46584-120">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="46584-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="46584-121">解説</span><span class="sxs-lookup"><span data-stu-id="46584-121">Remarks</span></span>

<span data-ttu-id="46584-122">選択条件では、選択セットまたは .NET 型を指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="46584-122">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="46584-123">選択条件の使用方法の詳細については、「 [データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46584-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="46584-124">選択セットは、書式設定ファイルによって定義される任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="46584-124">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="46584-125">選択セットの作成と参照の詳細については、「 [オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46584-125">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="46584-126">ワイドビューのその他のコンポーネントの詳細については、「 [ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46584-126">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="46584-127">参照</span><span class="sxs-lookup"><span data-stu-id="46584-127">See Also</span></span>

[<span data-ttu-id="46584-128">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="46584-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="46584-129">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="46584-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="46584-130">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="46584-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="46584-131">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="46584-131">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="46584-132">WideEntry (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="46584-132">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="46584-133">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="46584-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
