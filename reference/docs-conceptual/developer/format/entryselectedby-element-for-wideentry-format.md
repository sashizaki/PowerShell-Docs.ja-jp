---
title: WideEntry の EntrySelectedBy 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e0c98933-b7a5-4205-b811-06c0b0bf8988
caps.latest.revision: 9
ms.openlocfilehash: 54c7c261a23075721cd7bce75e530150dc0e0212
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363331"
---
# <a name="entryselectedby-element-for-wideentry-format"></a><span data-ttu-id="a0647-102">WideEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a0647-102">EntrySelectedBy Element for WideEntry (Format)</span></span>

<span data-ttu-id="a0647-103">ワイドビューのこの定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="a0647-103">Defines the .NET types that use this definition of the wide view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="a0647-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideEntry (Format) の要素 (format)</span><span class="sxs-lookup"><span data-stu-id="a0647-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a0647-105">構文</span><span class="sxs-lookup"><span data-stu-id="a0647-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a0647-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="a0647-106">Attributes and Elements</span></span>

<span data-ttu-id="a0647-107">次のセクションでは、`EntrySelectedBy` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0647-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a0647-108">属性</span><span class="sxs-lookup"><span data-stu-id="a0647-108">Attributes</span></span>

<span data-ttu-id="a0647-109">なし。</span><span class="sxs-lookup"><span data-stu-id="a0647-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a0647-110">子要素</span><span class="sxs-lookup"><span data-stu-id="a0647-110">Child Elements</span></span>

|<span data-ttu-id="a0647-111">要素</span><span class="sxs-lookup"><span data-stu-id="a0647-111">Element</span></span>|<span data-ttu-id="a0647-112">[説明]</span><span class="sxs-lookup"><span data-stu-id="a0647-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a0647-113">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="a0647-113">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="a0647-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a0647-114">Optional element.</span></span><br /><br /> <span data-ttu-id="a0647-115">このワイドビュー定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="a0647-115">Defines the condition that must exist for this wide view definition to be used.</span></span>|
|[<span data-ttu-id="a0647-116">WideEntry (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="a0647-116">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="a0647-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a0647-117">Optional element.</span></span><br /><br /> <span data-ttu-id="a0647-118">このワイドビュー定義を使用する一連の .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="a0647-118">Specifies a set of .NET types that use this wide view definition.</span></span>|
|[<span data-ttu-id="a0647-119">WideEntry (Format) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="a0647-119">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="a0647-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a0647-120">Optional element.</span></span><br /><br /> <span data-ttu-id="a0647-121">このワイドビュー定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="a0647-121">Specifies a .NET type that uses this wide view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a0647-122">親要素</span><span class="sxs-lookup"><span data-stu-id="a0647-122">Parent Elements</span></span>

|<span data-ttu-id="a0647-123">要素</span><span class="sxs-lookup"><span data-stu-id="a0647-123">Element</span></span>|<span data-ttu-id="a0647-124">[説明]</span><span class="sxs-lookup"><span data-stu-id="a0647-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a0647-125">WideEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="a0647-125">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="a0647-126">ワイドビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="a0647-126">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a0647-127">コメント</span><span class="sxs-lookup"><span data-stu-id="a0647-127">Remarks</span></span>

<span data-ttu-id="a0647-128">ワイドビュー定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0647-128">You must specify at least one type, selection set, or selection condition for a wide view definition.</span></span> <span data-ttu-id="a0647-129">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="a0647-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="a0647-130">選択条件は、オブジェクトに特定のプロパティがある場合や、特定のプロパティ値またはスクリプト値が `true`に評価される場合など、使用する定義のために存在する必要がある条件を定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0647-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script value evaluates to `true`.</span></span> <span data-ttu-id="a0647-131">選択条件の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0647-131">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="a0647-132">ワイドビューのその他のコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0647-132">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a0647-133">参照</span><span class="sxs-lookup"><span data-stu-id="a0647-133">See Also</span></span>

[<span data-ttu-id="a0647-134">WideEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="a0647-134">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="a0647-135">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="a0647-135">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="a0647-136">WideEntry (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="a0647-136">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="a0647-137">WideEntry (Format) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="a0647-137">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="a0647-138">ワイドビューの作成</span><span class="sxs-lookup"><span data-stu-id="a0647-138">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="a0647-139">データを表示するための条件の定義</span><span class="sxs-lookup"><span data-stu-id="a0647-139">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="a0647-140">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="a0647-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
