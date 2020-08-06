---
title: GroupBy (Format) の CustomEntry の EntrySelectedBy 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 75a0f42e7722b54791a873200a35c8fcbbd665b1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774135"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a><span data-ttu-id="bfb8e-102">GroupBy の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bfb8e-102">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="bfb8e-103">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="bfb8e-103">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="bfb8e-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bfb8e-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="bfb8e-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素を表示 (format) の CustomControl 要素を使用して、groupby (形式) の CustomControl の CustomControl の groupby (format) の CustomEntry 要素を使用して CustomEntry for GroupBy (形式)</span><span class="sxs-lookup"><span data-stu-id="bfb8e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bfb8e-106">構文</span><span class="sxs-lookup"><span data-stu-id="bfb8e-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bfb8e-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bfb8e-107">Attributes and Elements</span></span>

<span data-ttu-id="bfb8e-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `EntrySelectedBy` ます。</span><span class="sxs-lookup"><span data-stu-id="bfb8e-108">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="bfb8e-109">定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfb8e-109">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="bfb8e-110">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="bfb8e-110">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="bfb8e-111">属性</span><span class="sxs-lookup"><span data-stu-id="bfb8e-111">Attributes</span></span>

<span data-ttu-id="bfb8e-112">なし。</span><span class="sxs-lookup"><span data-stu-id="bfb8e-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bfb8e-113">子要素</span><span class="sxs-lookup"><span data-stu-id="bfb8e-113">Child Elements</span></span>

|<span data-ttu-id="bfb8e-114">要素</span><span class="sxs-lookup"><span data-stu-id="bfb8e-114">Element</span></span>|<span data-ttu-id="bfb8e-115">説明</span><span class="sxs-lookup"><span data-stu-id="bfb8e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bfb8e-116">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bfb8e-116">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="bfb8e-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="bfb8e-117">Optional element.</span></span><br /><br /> <span data-ttu-id="bfb8e-118">この定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="bfb8e-118">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="bfb8e-119">GroupBy の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bfb8e-119">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="bfb8e-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="bfb8e-120">Optional element.</span></span><br /><br /> <span data-ttu-id="bfb8e-121">コントロールのこの定義を使用する .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="bfb8e-121">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="bfb8e-122">GroupBy の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bfb8e-122">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="bfb8e-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="bfb8e-123">Optional element.</span></span><br /><br /> <span data-ttu-id="bfb8e-124">コントロールのこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfb8e-124">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bfb8e-125">親要素</span><span class="sxs-lookup"><span data-stu-id="bfb8e-125">Parent Elements</span></span>

|<span data-ttu-id="bfb8e-126">要素</span><span class="sxs-lookup"><span data-stu-id="bfb8e-126">Element</span></span>|<span data-ttu-id="bfb8e-127">説明</span><span class="sxs-lookup"><span data-stu-id="bfb8e-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bfb8e-128">GroupBy の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bfb8e-128">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="bfb8e-129">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="bfb8e-129">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bfb8e-130">解説</span><span class="sxs-lookup"><span data-stu-id="bfb8e-130">Remarks</span></span>

<span data-ttu-id="bfb8e-131">選択条件は、オブジェクトが特定のプロパティを持っている場合や、特定のプロパティ値またはスクリプトがに評価された場合など、使用する定義のために存在する必要がある条件を定義するために使用され `true` ます。</span><span class="sxs-lookup"><span data-stu-id="bfb8e-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="bfb8e-132">選択条件の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfb8e-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bfb8e-133">参照</span><span class="sxs-lookup"><span data-stu-id="bfb8e-133">See Also</span></span>

[<span data-ttu-id="bfb8e-134">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bfb8e-134">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="bfb8e-135">GroupBy の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bfb8e-135">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="bfb8e-136">GroupBy の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bfb8e-136">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="bfb8e-137">View の Controls の CustomEntries の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bfb8e-137">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="bfb8e-138">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="bfb8e-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
