---
title: WideControl の WideEntry 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 13dd1f6ad7ac1e9d8d0524f0a0f18fe80ffaf8e2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780017"
---
# <a name="wideentry-element-for-widecontrol-format"></a><span data-ttu-id="ea9dc-102">WideControl の WideEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ea9dc-102">WideEntry Element for WideControl (Format)</span></span>

<span data-ttu-id="ea9dc-103">ワイドビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="ea9dc-103">Provides a definition of the wide view.</span></span>

<span data-ttu-id="ea9dc-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (Format)</span><span class="sxs-lookup"><span data-stu-id="ea9dc-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ea9dc-105">構文</span><span class="sxs-lookup"><span data-stu-id="ea9dc-105">Syntax</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ea9dc-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ea9dc-106">Attributes and Elements</span></span>

<span data-ttu-id="ea9dc-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `WideEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="ea9dc-107">The following sections describe the attributes, child elements, and the parent element of the `WideEntry` element.</span></span> <span data-ttu-id="ea9dc-108">1つの子要素を指定する必要があり `WideItem` ます。</span><span class="sxs-lookup"><span data-stu-id="ea9dc-108">You must specify a single `WideItem` child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ea9dc-109">属性</span><span class="sxs-lookup"><span data-stu-id="ea9dc-109">Attributes</span></span>

<span data-ttu-id="ea9dc-110">なし。</span><span class="sxs-lookup"><span data-stu-id="ea9dc-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ea9dc-111">子要素</span><span class="sxs-lookup"><span data-stu-id="ea9dc-111">Child Elements</span></span>

|<span data-ttu-id="ea9dc-112">要素</span><span class="sxs-lookup"><span data-stu-id="ea9dc-112">Element</span></span>|<span data-ttu-id="ea9dc-113">説明</span><span class="sxs-lookup"><span data-stu-id="ea9dc-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ea9dc-114">WideEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ea9dc-114">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="ea9dc-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="ea9dc-115">Optional element.</span></span><br /><br /> <span data-ttu-id="ea9dc-116">このワイドエントリ定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="ea9dc-116">Defines the .NET types that use this wide entry definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="ea9dc-117">WideItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ea9dc-117">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="ea9dc-118">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="ea9dc-118">Required element.</span></span><br /><br /> <span data-ttu-id="ea9dc-119">値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="ea9dc-119">Defines the property or script whose value is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ea9dc-120">親要素</span><span class="sxs-lookup"><span data-stu-id="ea9dc-120">Parent Elements</span></span>

|<span data-ttu-id="ea9dc-121">要素</span><span class="sxs-lookup"><span data-stu-id="ea9dc-121">Element</span></span>|<span data-ttu-id="ea9dc-122">説明</span><span class="sxs-lookup"><span data-stu-id="ea9dc-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ea9dc-123">WideEntries 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ea9dc-123">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="ea9dc-124">ワイドビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="ea9dc-124">Provides the definitions of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ea9dc-125">解説</span><span class="sxs-lookup"><span data-stu-id="ea9dc-125">Remarks</span></span>

<span data-ttu-id="ea9dc-126">ワイドビューは、オブジェクトごとに1つのプロパティ値またはスクリプト値を表示するリスト形式です。</span><span class="sxs-lookup"><span data-stu-id="ea9dc-126">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="ea9dc-127">他の種類のビューとは異なり、各ビュー定義に指定できる項目要素は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="ea9dc-127">Unlike other types of views, you can specify only one item element for each view definition.</span></span> <span data-ttu-id="ea9dc-128">ワイドビューのその他のコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea9dc-128">For more information about the other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ea9dc-129">例</span><span class="sxs-lookup"><span data-stu-id="ea9dc-129">Example</span></span>

<span data-ttu-id="ea9dc-130">次の例は、 `WideEntry` 1 つの要素を定義する要素を示して `WideItem` います。</span><span class="sxs-lookup"><span data-stu-id="ea9dc-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="ea9dc-131">要素は、 `WideItem` ビューに値が表示されるプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="ea9dc-131">The `WideItem` element defines the property whose value is displayed in the view.</span></span>

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

<span data-ttu-id="ea9dc-132">ワイドビューの完全な例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea9dc-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ea9dc-133">参照</span><span class="sxs-lookup"><span data-stu-id="ea9dc-133">See Also</span></span>

[<span data-ttu-id="ea9dc-134">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="ea9dc-134">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="ea9dc-135">WideEntry の SelectionCondition 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ea9dc-135">SelectionCondition Element for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="ea9dc-136">WideEntry の SelectionSetName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ea9dc-136">SelectionSetName Element for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="ea9dc-137">WideEntry の TypeName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ea9dc-137">TypeName Element for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="ea9dc-138">WideEntries 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ea9dc-138">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="ea9dc-139">WideItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ea9dc-139">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="ea9dc-140">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="ea9dc-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
