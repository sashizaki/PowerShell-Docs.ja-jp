---
ms.date: 09/13/2016
ms.topic: reference
title: View の Controls の CustomEntry の EntrySelectedBy 要素 (書式)
description: View の Controls の CustomEntry の EntrySelectedBy 要素 (書式)
ms.openlocfilehash: 29b0574a95d81962fb3f72a526f89273baeea647
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660265"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="a906b-103">View の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a906b-103">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="a906b-104">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="a906b-104">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="a906b-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a906b-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="a906b-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素 (format) を使用して、ビューのコントロール (format) の CustomControl 要素のコントロール要素 view (format) の CustomControl のための Entries 要素を表示するためのコントロールのためのカスタムエントリを表示するためのコントロール (形式) の CustomEntry 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="a906b-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a906b-107">構文</span><span class="sxs-lookup"><span data-stu-id="a906b-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a906b-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a906b-108">Attributes and Elements</span></span>

<span data-ttu-id="a906b-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `EntrySelectedBy` ます。</span><span class="sxs-lookup"><span data-stu-id="a906b-109">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="a906b-110">定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a906b-110">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="a906b-111">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="a906b-111">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="a906b-112">属性</span><span class="sxs-lookup"><span data-stu-id="a906b-112">Attributes</span></span>

<span data-ttu-id="a906b-113">なし。</span><span class="sxs-lookup"><span data-stu-id="a906b-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a906b-114">子要素</span><span class="sxs-lookup"><span data-stu-id="a906b-114">Child Elements</span></span>

|<span data-ttu-id="a906b-115">要素</span><span class="sxs-lookup"><span data-stu-id="a906b-115">Element</span></span>|<span data-ttu-id="a906b-116">説明</span><span class="sxs-lookup"><span data-stu-id="a906b-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a906b-117">View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a906b-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="a906b-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a906b-118">Optional element.</span></span><br /><br /> <span data-ttu-id="a906b-119">この定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="a906b-119">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="a906b-120">View の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a906b-120">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="a906b-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a906b-121">Optional element.</span></span><br /><br /> <span data-ttu-id="a906b-122">コントロールのこの定義を使用する .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="a906b-122">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="a906b-123">View の Controls の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a906b-123">TypeName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="a906b-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a906b-124">Optional element.</span></span><br /><br /> <span data-ttu-id="a906b-125">コントロールのこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="a906b-125">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a906b-126">親要素</span><span class="sxs-lookup"><span data-stu-id="a906b-126">Parent Elements</span></span>

|<span data-ttu-id="a906b-127">要素</span><span class="sxs-lookup"><span data-stu-id="a906b-127">Element</span></span>|<span data-ttu-id="a906b-128">説明</span><span class="sxs-lookup"><span data-stu-id="a906b-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a906b-129">View の Controls の CustomEntries の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a906b-129">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="a906b-130">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="a906b-130">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a906b-131">解説</span><span class="sxs-lookup"><span data-stu-id="a906b-131">Remarks</span></span>

<span data-ttu-id="a906b-132">選択条件は、オブジェクトが特定のプロパティを持っている場合や、特定のプロパティ値またはスクリプトがに評価された場合など、使用する定義のために存在する必要がある条件を定義するために使用され `true` ます。</span><span class="sxs-lookup"><span data-stu-id="a906b-132">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="a906b-133">選択条件の詳細については、「 [ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a906b-133">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a906b-134">参照</span><span class="sxs-lookup"><span data-stu-id="a906b-134">See Also</span></span>

[<span data-ttu-id="a906b-135">View の Controls の CustomEntries の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a906b-135">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="a906b-136">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="a906b-136">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
