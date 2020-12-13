---
ms.date: 09/13/2016
ms.topic: reference
title: WideControl の WideItem 要素 (書式)
description: WideControl の WideItem 要素 (書式)
ms.openlocfilehash: b9c416bbe3befcd689b8a2c0b72a8ff1301b9659
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647807"
---
# <a name="wideitem-element-for-widecontrol-format"></a><span data-ttu-id="41369-103">WideControl の WideItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="41369-103">WideItem Element for WideControl (Format)</span></span>

<span data-ttu-id="41369-104">値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="41369-104">Defines the property or script whose value is displayed.</span></span>

<span data-ttu-id="41369-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (Format) WideEntries Element (format) WideEntry Element (format) WideItem Element (Format)</span><span class="sxs-lookup"><span data-stu-id="41369-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="41369-106">構文</span><span class="sxs-lookup"><span data-stu-id="41369-106">Syntax</span></span>

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="41369-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="41369-107">Attributes and Elements</span></span>

<span data-ttu-id="41369-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `WideItem` ます。</span><span class="sxs-lookup"><span data-stu-id="41369-108">The following sections describe the attributes, child elements, and the parent element of the `WideItem` element.</span></span> <span data-ttu-id="41369-109">`FormatString` 要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="41369-109">The `FormatString` element is optional.</span></span> <span data-ttu-id="41369-110">ただし、要素または要素を指定する必要があり `PropertyName` `ScriptBlock` ますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="41369-110">However, you must specify a `PropertyName` or `ScriptBlock` element, but you cannot specify both.</span></span>

### <a name="attributes"></a><span data-ttu-id="41369-111">属性</span><span class="sxs-lookup"><span data-stu-id="41369-111">Attributes</span></span>

<span data-ttu-id="41369-112">なし。</span><span class="sxs-lookup"><span data-stu-id="41369-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="41369-113">子要素</span><span class="sxs-lookup"><span data-stu-id="41369-113">Child Elements</span></span>

|<span data-ttu-id="41369-114">要素</span><span class="sxs-lookup"><span data-stu-id="41369-114">Element</span></span>|<span data-ttu-id="41369-115">説明</span><span class="sxs-lookup"><span data-stu-id="41369-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="41369-116">WideControl の WideItem の FormatString 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="41369-116">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="41369-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="41369-117">Optional element.</span></span><br /><br /> <span data-ttu-id="41369-118">プロパティまたはスクリプトの値をビューに表示する方法を定義する形式パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="41369-118">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>|
|[<span data-ttu-id="41369-119">WideItem の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="41369-119">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="41369-120">ワイドビューに表示される値を持つオブジェクトのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="41369-120">Specifies the property of the object whose value is displayed in the wide view.</span></span>|
|[<span data-ttu-id="41369-121">WideItem の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="41369-121">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="41369-122">ワイドビューに値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="41369-122">Specifies the script whose value is displayed in the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="41369-123">親要素</span><span class="sxs-lookup"><span data-stu-id="41369-123">Parent Elements</span></span>

|<span data-ttu-id="41369-124">要素</span><span class="sxs-lookup"><span data-stu-id="41369-124">Element</span></span>|<span data-ttu-id="41369-125">説明</span><span class="sxs-lookup"><span data-stu-id="41369-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="41369-126">WideEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="41369-126">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="41369-127">ワイドビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="41369-127">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="41369-128">解説</span><span class="sxs-lookup"><span data-stu-id="41369-128">Remarks</span></span>

<span data-ttu-id="41369-129">ワイドビューのコンポーネントの詳細については、「 [Wide ビュー](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41369-129">For more information about the components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="41369-130">例</span><span class="sxs-lookup"><span data-stu-id="41369-130">Example</span></span>

<span data-ttu-id="41369-131">次の例は、 `WideEntry` 1 つの要素を定義する要素を示して `WideItem` います。</span><span class="sxs-lookup"><span data-stu-id="41369-131">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="41369-132">要素は、 `WideItem` ビューに値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="41369-132">The `WideItem` element defines the property or script whose value is displayed in the view.</span></span>

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

<span data-ttu-id="41369-133">ワイドビューの完全な例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41369-133">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="41369-134">参照</span><span class="sxs-lookup"><span data-stu-id="41369-134">See Also</span></span>

[<span data-ttu-id="41369-135">WideControl の WideItem の FormatString 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="41369-135">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="41369-136">WideItem の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="41369-136">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="41369-137">WideItem の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="41369-137">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="41369-138">WideEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="41369-138">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="41369-139">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="41369-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
