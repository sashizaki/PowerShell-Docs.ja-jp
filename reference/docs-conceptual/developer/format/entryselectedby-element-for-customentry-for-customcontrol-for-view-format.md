---
title: CustomEntry for CustomControl for View (Format) の EntrySelectedBy 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4d4900cefb0d499397fc9dff7e037ce0a541f72f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783689"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="a8f96-102">View の CustomControl の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a8f96-102">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="a8f96-103">このカスタムエントリを使用する .NET 型、またはこのエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="a8f96-103">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>

<span data-ttu-id="a8f96-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) CustomControl 要素 (形式) の CustomEntries for CustomControl for view (format) の CustomEntry 要素を使用して、CustomEntry for ビューの EntrySelectedBy 要素を表示 (形式) します。</span><span class="sxs-lookup"><span data-stu-id="a8f96-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a8f96-105">構文</span><span class="sxs-lookup"><span data-stu-id="a8f96-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a8f96-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a8f96-106">Attributes and Elements</span></span>

<span data-ttu-id="a8f96-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `EntrySelectedBy` ます。</span><span class="sxs-lookup"><span data-stu-id="a8f96-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a8f96-108">属性</span><span class="sxs-lookup"><span data-stu-id="a8f96-108">Attributes</span></span>

<span data-ttu-id="a8f96-109">なし。</span><span class="sxs-lookup"><span data-stu-id="a8f96-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a8f96-110">子要素</span><span class="sxs-lookup"><span data-stu-id="a8f96-110">Child Elements</span></span>

|<span data-ttu-id="a8f96-111">要素</span><span class="sxs-lookup"><span data-stu-id="a8f96-111">Element</span></span>|<span data-ttu-id="a8f96-112">説明</span><span class="sxs-lookup"><span data-stu-id="a8f96-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a8f96-113">CustomEntry (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="a8f96-113">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="a8f96-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a8f96-114">Optional element.</span></span><br /><br /> <span data-ttu-id="a8f96-115">この定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="a8f96-115">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="a8f96-116">CustomEntry (形式) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="a8f96-116">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|<span data-ttu-id="a8f96-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a8f96-117">Optional element.</span></span><br /><br /> <span data-ttu-id="a8f96-118">コントロールビューのこの定義を使用する .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8f96-118">Specifies a set of .NET types that use this definition of the control view.</span></span>|
|[<span data-ttu-id="a8f96-119">CustomEntry (形式) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="a8f96-119">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="a8f96-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a8f96-120">Optional element.</span></span><br /><br /> <span data-ttu-id="a8f96-121">コントロールビューのこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8f96-121">Specifies a .NET type that uses this definition of the control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a8f96-122">親要素</span><span class="sxs-lookup"><span data-stu-id="a8f96-122">Parent Elements</span></span>

|<span data-ttu-id="a8f96-123">要素</span><span class="sxs-lookup"><span data-stu-id="a8f96-123">Element</span></span>|<span data-ttu-id="a8f96-124">説明</span><span class="sxs-lookup"><span data-stu-id="a8f96-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a8f96-125">View (Format) の CustomEntries の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="a8f96-125">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="a8f96-126">特定の .NET オブジェクトで使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="a8f96-126">Defines the controls used by specific .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a8f96-127">解説</span><span class="sxs-lookup"><span data-stu-id="a8f96-127">Remarks</span></span>

<span data-ttu-id="a8f96-128">エントリの種類、選択セット、または選択条件を少なくとも1つ指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8f96-128">You must specify at least one type, selection set, or selection condition for an entry.</span></span> <span data-ttu-id="a8f96-129">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="a8f96-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="a8f96-130">選択条件は、オブジェクトに特定のプロパティがある場合や、特定のプロパティ値またはスクリプトがに評価される場合など、エントリの使用に必要な条件を定義するために使用し `true` ます。</span><span class="sxs-lookup"><span data-stu-id="a8f96-130">Selection conditions are used to define a condition that must exist for the entry to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="a8f96-131">選択条件の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8f96-131">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="a8f96-132">カスタムコントロールビューのコンポーネントの詳細については、「[カスタムコントロールビュー](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8f96-132">For more information about the components of a custom control view, see [Custom Control View](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a8f96-133">参照</span><span class="sxs-lookup"><span data-stu-id="a8f96-133">See Also</span></span>

[<span data-ttu-id="a8f96-134">CustomEntry (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="a8f96-134">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="a8f96-135">CustomEntry (形式) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="a8f96-135">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a8f96-136">CustomEntry (形式) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="a8f96-136">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a8f96-137">View (Format) の CustomEntries の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="a8f96-137">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a8f96-138">カスタムコントロールビュー</span><span class="sxs-lookup"><span data-stu-id="a8f96-138">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="a8f96-139">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="a8f96-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
