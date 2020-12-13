---
ms.date: 09/13/2016
ms.topic: reference
title: WideControl の WideEntries 要素 (書式)
description: WideControl の WideEntries 要素 (書式)
ms.openlocfilehash: 567b8acdd0d2e8d5daaef2c31b4fe4ce38c23a47
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651236"
---
# <a name="wideentries-element-for-widecontrol-format"></a><span data-ttu-id="78036-103">WideControl の WideEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="78036-103">WideEntries Element for WideControl (Format)</span></span>

<span data-ttu-id="78036-104">ワイドビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="78036-104">Provides the definitions of the wide view.</span></span> <span data-ttu-id="78036-105">ワイドビューでは、1つまたは複数の定義を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78036-105">The wide view must specify one or more definitions.</span></span>

<span data-ttu-id="78036-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl 要素 (format) WideEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="78036-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="78036-107">構文</span><span class="sxs-lookup"><span data-stu-id="78036-107">Syntax</span></span>

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="78036-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="78036-108">Attributes and Elements</span></span>

<span data-ttu-id="78036-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `WideEntries` ます。</span><span class="sxs-lookup"><span data-stu-id="78036-109">The following sections describe the attributes, child elements, and parent element of the `WideEntries` element.</span></span> <span data-ttu-id="78036-110">少なくとも1つの子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78036-110">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="78036-111">属性</span><span class="sxs-lookup"><span data-stu-id="78036-111">Attributes</span></span>

<span data-ttu-id="78036-112">なし。</span><span class="sxs-lookup"><span data-stu-id="78036-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="78036-113">子要素</span><span class="sxs-lookup"><span data-stu-id="78036-113">Child Elements</span></span>

|<span data-ttu-id="78036-114">要素</span><span class="sxs-lookup"><span data-stu-id="78036-114">Element</span></span>|<span data-ttu-id="78036-115">説明</span><span class="sxs-lookup"><span data-stu-id="78036-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="78036-116">WideEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="78036-116">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="78036-117">ワイドビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="78036-117">Provides a definition of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="78036-118">親要素</span><span class="sxs-lookup"><span data-stu-id="78036-118">Parent Elements</span></span>

|<span data-ttu-id="78036-119">要素</span><span class="sxs-lookup"><span data-stu-id="78036-119">Element</span></span>|<span data-ttu-id="78036-120">説明</span><span class="sxs-lookup"><span data-stu-id="78036-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="78036-121">WideControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="78036-121">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="78036-122">ビューのワイド (単一値) リスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="78036-122">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="78036-123">解説</span><span class="sxs-lookup"><span data-stu-id="78036-123">Remarks</span></span>

<span data-ttu-id="78036-124">ワイドビューは、オブジェクトごとに1つのプロパティ値またはスクリプト値を表示するリスト形式です。</span><span class="sxs-lookup"><span data-stu-id="78036-124">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="78036-125">ワイドビューのコンポーネントの詳細については、「 [ワイドビューコンポーネント](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78036-125">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="78036-126">例</span><span class="sxs-lookup"><span data-stu-id="78036-126">Example</span></span>

<span data-ttu-id="78036-127">次の例は、 `WideEntries` 1 つの要素を定義する要素を示して `WideEntry` います。</span><span class="sxs-lookup"><span data-stu-id="78036-127">The following example shows a `WideEntries` element that defines a single `WideEntry` element.</span></span> <span data-ttu-id="78036-128">要素には、 `WideEntry` `WideItem` ビューに表示されるプロパティまたはスクリプトの値を定義する1つの要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="78036-128">The `WideEntry` element contains a single `WideItem` element that defines what property or script value is displayed in the view.</span></span>

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="78036-129">ワイドビューの完全な例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78036-129">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="78036-130">参照</span><span class="sxs-lookup"><span data-stu-id="78036-130">See Also</span></span>

[<span data-ttu-id="78036-131">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="78036-131">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="78036-132">WideControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="78036-132">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="78036-133">WideEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="78036-133">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="78036-134">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="78036-134">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
