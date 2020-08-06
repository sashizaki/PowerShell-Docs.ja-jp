---
title: WideEntry の EntrySelectedBy 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: ba0a776839c39d753d12859335388c5326639fd4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774084"
---
# <a name="entryselectedby-element-for-wideentry-format"></a><span data-ttu-id="69528-102">WideEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="69528-102">EntrySelectedBy Element for WideEntry (Format)</span></span>

<span data-ttu-id="69528-103">ワイドビューのこの定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="69528-103">Defines the .NET types that use this definition of the wide view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="69528-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideEntry (Format) の要素 (format)</span><span class="sxs-lookup"><span data-stu-id="69528-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="69528-105">構文</span><span class="sxs-lookup"><span data-stu-id="69528-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="69528-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="69528-106">Attributes and Elements</span></span>

<span data-ttu-id="69528-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `EntrySelectedBy` ます。</span><span class="sxs-lookup"><span data-stu-id="69528-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="69528-108">属性</span><span class="sxs-lookup"><span data-stu-id="69528-108">Attributes</span></span>

<span data-ttu-id="69528-109">なし。</span><span class="sxs-lookup"><span data-stu-id="69528-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="69528-110">子要素</span><span class="sxs-lookup"><span data-stu-id="69528-110">Child Elements</span></span>

|<span data-ttu-id="69528-111">要素</span><span class="sxs-lookup"><span data-stu-id="69528-111">Element</span></span>|<span data-ttu-id="69528-112">説明</span><span class="sxs-lookup"><span data-stu-id="69528-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="69528-113">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="69528-113">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="69528-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="69528-114">Optional element.</span></span><br /><br /> <span data-ttu-id="69528-115">このワイドビュー定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="69528-115">Defines the condition that must exist for this wide view definition to be used.</span></span>|
|[<span data-ttu-id="69528-116">WideEntry (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="69528-116">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="69528-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="69528-117">Optional element.</span></span><br /><br /> <span data-ttu-id="69528-118">このワイドビュー定義を使用する一連の .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="69528-118">Specifies a set of .NET types that use this wide view definition.</span></span>|
|[<span data-ttu-id="69528-119">WideEntry の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="69528-119">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="69528-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="69528-120">Optional element.</span></span><br /><br /> <span data-ttu-id="69528-121">このワイドビュー定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="69528-121">Specifies a .NET type that uses this wide view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="69528-122">親要素</span><span class="sxs-lookup"><span data-stu-id="69528-122">Parent Elements</span></span>

|<span data-ttu-id="69528-123">要素</span><span class="sxs-lookup"><span data-stu-id="69528-123">Element</span></span>|<span data-ttu-id="69528-124">説明</span><span class="sxs-lookup"><span data-stu-id="69528-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="69528-125">WideEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="69528-125">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="69528-126">ワイドビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="69528-126">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="69528-127">解説</span><span class="sxs-lookup"><span data-stu-id="69528-127">Remarks</span></span>

<span data-ttu-id="69528-128">ワイドビュー定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69528-128">You must specify at least one type, selection set, or selection condition for a wide view definition.</span></span> <span data-ttu-id="69528-129">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="69528-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="69528-130">選択条件は、オブジェクトに特定のプロパティがある場合や、特定のプロパティ値またはスクリプト値がに評価される場合など、使用する定義のために存在する必要がある条件を定義するために使用され `true` ます。</span><span class="sxs-lookup"><span data-stu-id="69528-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script value evaluates to `true`.</span></span> <span data-ttu-id="69528-131">選択条件の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69528-131">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="69528-132">ワイドビューのその他のコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69528-132">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="69528-133">参照</span><span class="sxs-lookup"><span data-stu-id="69528-133">See Also</span></span>

[<span data-ttu-id="69528-134">WideEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="69528-134">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="69528-135">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="69528-135">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="69528-136">WideEntry (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="69528-136">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="69528-137">WideEntry の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="69528-137">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="69528-138">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="69528-138">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="69528-139">データの表示条件を定義する</span><span class="sxs-lookup"><span data-stu-id="69528-139">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="69528-140">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="69528-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
