---
title: WideControl の WideEntries 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 74383b288c945008c1d7b5119363a166c04802ae
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785049"
---
# <a name="wideentries-element-for-widecontrol-format"></a><span data-ttu-id="4cdf9-102">WideControl の WideEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4cdf9-102">WideEntries Element for WideControl (Format)</span></span>

<span data-ttu-id="4cdf9-103">ワイドビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="4cdf9-103">Provides the definitions of the wide view.</span></span> <span data-ttu-id="4cdf9-104">ワイドビューでは、1つまたは複数の定義を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cdf9-104">The wide view must specify one or more definitions.</span></span>

<span data-ttu-id="4cdf9-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl 要素 (format) WideEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="4cdf9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4cdf9-106">構文</span><span class="sxs-lookup"><span data-stu-id="4cdf9-106">Syntax</span></span>

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="4cdf9-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4cdf9-107">Attributes and Elements</span></span>

<span data-ttu-id="4cdf9-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `WideEntries` ます。</span><span class="sxs-lookup"><span data-stu-id="4cdf9-108">The following sections describe the attributes, child elements, and parent element of the `WideEntries` element.</span></span> <span data-ttu-id="4cdf9-109">少なくとも1つの子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cdf9-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="4cdf9-110">属性</span><span class="sxs-lookup"><span data-stu-id="4cdf9-110">Attributes</span></span>

<span data-ttu-id="4cdf9-111">なし。</span><span class="sxs-lookup"><span data-stu-id="4cdf9-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4cdf9-112">子要素</span><span class="sxs-lookup"><span data-stu-id="4cdf9-112">Child Elements</span></span>

|<span data-ttu-id="4cdf9-113">要素</span><span class="sxs-lookup"><span data-stu-id="4cdf9-113">Element</span></span>|<span data-ttu-id="4cdf9-114">説明</span><span class="sxs-lookup"><span data-stu-id="4cdf9-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4cdf9-115">WideEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="4cdf9-115">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="4cdf9-116">ワイドビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="4cdf9-116">Provides a definition of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4cdf9-117">親要素</span><span class="sxs-lookup"><span data-stu-id="4cdf9-117">Parent Elements</span></span>

|<span data-ttu-id="4cdf9-118">要素</span><span class="sxs-lookup"><span data-stu-id="4cdf9-118">Element</span></span>|<span data-ttu-id="4cdf9-119">説明</span><span class="sxs-lookup"><span data-stu-id="4cdf9-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4cdf9-120">WideControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4cdf9-120">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="4cdf9-121">ビューのワイド (単一値) リスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="4cdf9-121">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4cdf9-122">解説</span><span class="sxs-lookup"><span data-stu-id="4cdf9-122">Remarks</span></span>

<span data-ttu-id="4cdf9-123">ワイドビューは、オブジェクトごとに1つのプロパティ値またはスクリプト値を表示するリスト形式です。</span><span class="sxs-lookup"><span data-stu-id="4cdf9-123">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="4cdf9-124">ワイドビューのコンポーネントの詳細については、「[ワイドビューコンポーネント](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cdf9-124">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="4cdf9-125">例</span><span class="sxs-lookup"><span data-stu-id="4cdf9-125">Example</span></span>

<span data-ttu-id="4cdf9-126">次の例は、 `WideEntries` 1 つの要素を定義する要素を示して `WideEntry` います。</span><span class="sxs-lookup"><span data-stu-id="4cdf9-126">The following example shows a `WideEntries` element that defines a single `WideEntry` element.</span></span> <span data-ttu-id="4cdf9-127">要素には、 `WideEntry` `WideItem` ビューに表示されるプロパティまたはスクリプトの値を定義する1つの要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4cdf9-127">The `WideEntry` element contains a single `WideItem` element that defines what property or script value is displayed in the view.</span></span>

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="4cdf9-128">ワイドビューの完全な例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cdf9-128">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4cdf9-129">参照</span><span class="sxs-lookup"><span data-stu-id="4cdf9-129">See Also</span></span>

[<span data-ttu-id="4cdf9-130">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="4cdf9-130">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="4cdf9-131">WideControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4cdf9-131">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="4cdf9-132">WideEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="4cdf9-132">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="4cdf9-133">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="4cdf9-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
