---
ms.date: 09/13/2016
ms.topic: reference
title: WideControl の WideEntry 要素 (書式)
description: WideControl の WideEntry 要素 (書式)
ms.openlocfilehash: 3faaf767d11914792effd6765beed956a502c642
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664555"
---
# <a name="wideentry-element-for-widecontrol-format"></a><span data-ttu-id="ce8e0-103">WideControl の WideEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ce8e0-103">WideEntry Element for WideControl (Format)</span></span>

<span data-ttu-id="ce8e0-104">ワイドビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="ce8e0-104">Provides a definition of the wide view.</span></span>

<span data-ttu-id="ce8e0-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (Format)</span><span class="sxs-lookup"><span data-stu-id="ce8e0-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ce8e0-106">構文</span><span class="sxs-lookup"><span data-stu-id="ce8e0-106">Syntax</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ce8e0-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ce8e0-107">Attributes and Elements</span></span>

<span data-ttu-id="ce8e0-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `WideEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="ce8e0-108">The following sections describe the attributes, child elements, and the parent element of the `WideEntry` element.</span></span> <span data-ttu-id="ce8e0-109">1つの子要素を指定する必要があり `WideItem` ます。</span><span class="sxs-lookup"><span data-stu-id="ce8e0-109">You must specify a single `WideItem` child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ce8e0-110">属性</span><span class="sxs-lookup"><span data-stu-id="ce8e0-110">Attributes</span></span>

<span data-ttu-id="ce8e0-111">なし。</span><span class="sxs-lookup"><span data-stu-id="ce8e0-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ce8e0-112">子要素</span><span class="sxs-lookup"><span data-stu-id="ce8e0-112">Child Elements</span></span>

|<span data-ttu-id="ce8e0-113">要素</span><span class="sxs-lookup"><span data-stu-id="ce8e0-113">Element</span></span>|<span data-ttu-id="ce8e0-114">説明</span><span class="sxs-lookup"><span data-stu-id="ce8e0-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ce8e0-115">WideEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ce8e0-115">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="ce8e0-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="ce8e0-116">Optional element.</span></span><br /><br /> <span data-ttu-id="ce8e0-117">このワイドエントリ定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="ce8e0-117">Defines the .NET types that use this wide entry definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="ce8e0-118">WideItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ce8e0-118">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="ce8e0-119">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="ce8e0-119">Required element.</span></span><br /><br /> <span data-ttu-id="ce8e0-120">値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="ce8e0-120">Defines the property or script whose value is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ce8e0-121">親要素</span><span class="sxs-lookup"><span data-stu-id="ce8e0-121">Parent Elements</span></span>

|<span data-ttu-id="ce8e0-122">要素</span><span class="sxs-lookup"><span data-stu-id="ce8e0-122">Element</span></span>|<span data-ttu-id="ce8e0-123">説明</span><span class="sxs-lookup"><span data-stu-id="ce8e0-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ce8e0-124">WideEntries 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ce8e0-124">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="ce8e0-125">ワイドビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="ce8e0-125">Provides the definitions of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ce8e0-126">解説</span><span class="sxs-lookup"><span data-stu-id="ce8e0-126">Remarks</span></span>

<span data-ttu-id="ce8e0-127">ワイドビューは、オブジェクトごとに1つのプロパティ値またはスクリプト値を表示するリスト形式です。</span><span class="sxs-lookup"><span data-stu-id="ce8e0-127">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="ce8e0-128">他の種類のビューとは異なり、各ビュー定義に指定できる項目要素は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="ce8e0-128">Unlike other types of views, you can specify only one item element for each view definition.</span></span> <span data-ttu-id="ce8e0-129">ワイドビューのその他のコンポーネントの詳細については、「 [ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce8e0-129">For more information about the other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ce8e0-130">例</span><span class="sxs-lookup"><span data-stu-id="ce8e0-130">Example</span></span>

<span data-ttu-id="ce8e0-131">次の例は、 `WideEntry` 1 つの要素を定義する要素を示して `WideItem` います。</span><span class="sxs-lookup"><span data-stu-id="ce8e0-131">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="ce8e0-132">要素は、 `WideItem` ビューに値が表示されるプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="ce8e0-132">The `WideItem` element defines the property whose value is displayed in the view.</span></span>

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

<span data-ttu-id="ce8e0-133">ワイドビューの完全な例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce8e0-133">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ce8e0-134">参照</span><span class="sxs-lookup"><span data-stu-id="ce8e0-134">See Also</span></span>

[<span data-ttu-id="ce8e0-135">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="ce8e0-135">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="ce8e0-136">WideEntry の SelectionCondition 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ce8e0-136">SelectionCondition Element for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="ce8e0-137">WideEntry の SelectionSetName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ce8e0-137">SelectionSetName Element for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="ce8e0-138">WideEntry の TypeName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ce8e0-138">TypeName Element for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="ce8e0-139">WideEntries 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ce8e0-139">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="ce8e0-140">WideItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ce8e0-140">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="ce8e0-141">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="ce8e0-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
