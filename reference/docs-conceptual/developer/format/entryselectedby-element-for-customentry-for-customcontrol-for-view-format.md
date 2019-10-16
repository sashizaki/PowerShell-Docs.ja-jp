---
title: CustomEntry for CustomControl for View (Format) の EntrySelectedBy 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7828b45b-eabf-4432-b127-131b4ef0c800
caps.latest.revision: 8
ms.openlocfilehash: e7176f9f6ef67116ea7c07a46797fb0ba84f915d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368781"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="a0f0c-102">View の CustomControl の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a0f0c-102">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="a0f0c-103">このカスタムエントリを使用する .NET 型、またはこのエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="a0f0c-103">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>

<span data-ttu-id="a0f0c-104">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素の CustomControl for view (format) EntrySelectedBy 要素 for view (Format) EntrySelectedByCustomEntry for ビューの要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a0f0c-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a0f0c-105">構文</span><span class="sxs-lookup"><span data-stu-id="a0f0c-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a0f0c-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="a0f0c-106">Attributes and Elements</span></span>

<span data-ttu-id="a0f0c-107">次のセクションでは、属性、子要素、`EntrySelectedBy` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0f0c-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a0f0c-108">属性</span><span class="sxs-lookup"><span data-stu-id="a0f0c-108">Attributes</span></span>

<span data-ttu-id="a0f0c-109">なし。</span><span class="sxs-lookup"><span data-stu-id="a0f0c-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a0f0c-110">子要素</span><span class="sxs-lookup"><span data-stu-id="a0f0c-110">Child Elements</span></span>

|<span data-ttu-id="a0f0c-111">要素</span><span class="sxs-lookup"><span data-stu-id="a0f0c-111">Element</span></span>|<span data-ttu-id="a0f0c-112">[説明]</span><span class="sxs-lookup"><span data-stu-id="a0f0c-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a0f0c-113">CustomEntry (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="a0f0c-113">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="a0f0c-114">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="a0f0c-114">Optional element.</span></span><br /><br /> <span data-ttu-id="a0f0c-115">この定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="a0f0c-115">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="a0f0c-116">CustomEntry (形式) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="a0f0c-116">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|<span data-ttu-id="a0f0c-117">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="a0f0c-117">Optional element.</span></span><br /><br /> <span data-ttu-id="a0f0c-118">コントロールビューのこの定義を使用する .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="a0f0c-118">Specifies a set of .NET types that use this definition of the control view.</span></span>|
|[<span data-ttu-id="a0f0c-119">CustomEntry (形式) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="a0f0c-119">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="a0f0c-120">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="a0f0c-120">Optional element.</span></span><br /><br /> <span data-ttu-id="a0f0c-121">コントロールビューのこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="a0f0c-121">Specifies a .NET type that uses this definition of the control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a0f0c-122">親要素</span><span class="sxs-lookup"><span data-stu-id="a0f0c-122">Parent Elements</span></span>

|<span data-ttu-id="a0f0c-123">要素</span><span class="sxs-lookup"><span data-stu-id="a0f0c-123">Element</span></span>|<span data-ttu-id="a0f0c-124">[説明]</span><span class="sxs-lookup"><span data-stu-id="a0f0c-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a0f0c-125">View (Format) の CustomEntries の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="a0f0c-125">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="a0f0c-126">特定の .NET オブジェクトで使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="a0f0c-126">Defines the controls used by specific .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a0f0c-127">コメント</span><span class="sxs-lookup"><span data-stu-id="a0f0c-127">Remarks</span></span>

<span data-ttu-id="a0f0c-128">エントリの種類、選択セット、または選択条件を少なくとも1つ指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0f0c-128">You must specify at least one type, selection set, or selection condition for an entry.</span></span> <span data-ttu-id="a0f0c-129">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="a0f0c-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="a0f0c-130">選択条件は、オブジェクトに特定のプロパティがある場合や、特定のプロパティ値またはスクリプトが `true` に評価される場合など、エントリを使用するために存在する必要がある条件を定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0f0c-130">Selection conditions are used to define a condition that must exist for the entry to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="a0f0c-131">選択条件の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0f0c-131">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="a0f0c-132">カスタムコントロールビューのコンポーネントの詳細については、「[カスタムコントロールビュー](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0f0c-132">For more information about the components of a custom control view, see [Custom Control View](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a0f0c-133">参照</span><span class="sxs-lookup"><span data-stu-id="a0f0c-133">See Also</span></span>

[<span data-ttu-id="a0f0c-134">CustomEntry (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="a0f0c-134">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="a0f0c-135">CustomEntry (形式) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="a0f0c-135">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a0f0c-136">CustomEntry (形式) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="a0f0c-136">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a0f0c-137">View (Format) の CustomEntries の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="a0f0c-137">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a0f0c-138">カスタムコントロールビュー</span><span class="sxs-lookup"><span data-stu-id="a0f0c-138">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="a0f0c-139">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="a0f0c-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
