---
title: GroupBy (Format) の CustomEntry の EntrySelectedBy 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a317d482-73cc-4c98-a002-1357fa879cd7
caps.latest.revision: 7
ms.openlocfilehash: cf1a80e845c38d97d71f26eba63c38a550958b79
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363861"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a><span data-ttu-id="4b5e2-102">GroupBy の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4b5e2-102">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="4b5e2-103">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="4b5e2-103">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="4b5e2-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4b5e2-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="4b5e2-105">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素Groupby (format) の CustomControl には、GroupBy (形式) の CustomEntry の要素のエントリがあります。</span><span class="sxs-lookup"><span data-stu-id="4b5e2-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4b5e2-106">構文</span><span class="sxs-lookup"><span data-stu-id="4b5e2-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4b5e2-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="4b5e2-107">Attributes and Elements</span></span>

<span data-ttu-id="4b5e2-108">次のセクションでは、`EntrySelectedBy` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b5e2-108">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="4b5e2-109">定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b5e2-109">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="4b5e2-110">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="4b5e2-110">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="4b5e2-111">属性</span><span class="sxs-lookup"><span data-stu-id="4b5e2-111">Attributes</span></span>

<span data-ttu-id="4b5e2-112">なし。</span><span class="sxs-lookup"><span data-stu-id="4b5e2-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4b5e2-113">子要素</span><span class="sxs-lookup"><span data-stu-id="4b5e2-113">Child Elements</span></span>

|<span data-ttu-id="4b5e2-114">要素</span><span class="sxs-lookup"><span data-stu-id="4b5e2-114">Element</span></span>|<span data-ttu-id="4b5e2-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="4b5e2-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4b5e2-116">GroupBy (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="4b5e2-116">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="4b5e2-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4b5e2-117">Optional element.</span></span><br /><br /> <span data-ttu-id="4b5e2-118">この定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="4b5e2-118">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="4b5e2-119">GroupBy (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="4b5e2-119">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="4b5e2-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4b5e2-120">Optional element.</span></span><br /><br /> <span data-ttu-id="4b5e2-121">コントロールのこの定義を使用する .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="4b5e2-121">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="4b5e2-122">GroupBy (Format) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="4b5e2-122">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="4b5e2-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4b5e2-123">Optional element.</span></span><br /><br /> <span data-ttu-id="4b5e2-124">コントロールのこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="4b5e2-124">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4b5e2-125">親要素</span><span class="sxs-lookup"><span data-stu-id="4b5e2-125">Parent Elements</span></span>

|<span data-ttu-id="4b5e2-126">要素</span><span class="sxs-lookup"><span data-stu-id="4b5e2-126">Element</span></span>|<span data-ttu-id="4b5e2-127">[説明]</span><span class="sxs-lookup"><span data-stu-id="4b5e2-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4b5e2-128">GroupBy (Format) の CustomControl の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="4b5e2-128">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="4b5e2-129">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="4b5e2-129">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4b5e2-130">コメント</span><span class="sxs-lookup"><span data-stu-id="4b5e2-130">Remarks</span></span>

<span data-ttu-id="4b5e2-131">選択条件を使用して、オブジェクトに特定のプロパティがある場合や、特定のプロパティ値またはスクリプトが `true`に評価される場合など、使用する定義に必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="4b5e2-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="4b5e2-132">選択条件の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b5e2-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4b5e2-133">参照</span><span class="sxs-lookup"><span data-stu-id="4b5e2-133">See Also</span></span>

[<span data-ttu-id="4b5e2-134">GroupBy (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="4b5e2-134">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="4b5e2-135">GroupBy (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="4b5e2-135">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="4b5e2-136">GroupBy (Format) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="4b5e2-136">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="4b5e2-137">ビューのコントロール (Format) の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="4b5e2-137">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="4b5e2-138">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="4b5e2-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
