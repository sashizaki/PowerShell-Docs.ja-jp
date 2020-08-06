---
title: WideControl の WideItem 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6b2f7c97978c20350caeec894589c5995ae7ccc4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779898"
---
# <a name="wideitem-element-for-widecontrol-format"></a><span data-ttu-id="93b0a-102">WideControl の WideItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="93b0a-102">WideItem Element for WideControl (Format)</span></span>

<span data-ttu-id="93b0a-103">値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="93b0a-103">Defines the property or script whose value is displayed.</span></span>

<span data-ttu-id="93b0a-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (Format) WideEntries Element (format) WideEntry Element (format) WideItem Element (Format)</span><span class="sxs-lookup"><span data-stu-id="93b0a-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="93b0a-105">構文</span><span class="sxs-lookup"><span data-stu-id="93b0a-105">Syntax</span></span>

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="93b0a-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="93b0a-106">Attributes and Elements</span></span>

<span data-ttu-id="93b0a-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `WideItem` ます。</span><span class="sxs-lookup"><span data-stu-id="93b0a-107">The following sections describe the attributes, child elements, and the parent element of the `WideItem` element.</span></span> <span data-ttu-id="93b0a-108">`FormatString` 要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="93b0a-108">The `FormatString` element is optional.</span></span> <span data-ttu-id="93b0a-109">ただし、要素または要素を指定する必要があり `PropertyName` `ScriptBlock` ますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="93b0a-109">However, you must specify a `PropertyName` or `ScriptBlock` element, but you cannot specify both.</span></span>

### <a name="attributes"></a><span data-ttu-id="93b0a-110">属性</span><span class="sxs-lookup"><span data-stu-id="93b0a-110">Attributes</span></span>

<span data-ttu-id="93b0a-111">なし。</span><span class="sxs-lookup"><span data-stu-id="93b0a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="93b0a-112">子要素</span><span class="sxs-lookup"><span data-stu-id="93b0a-112">Child Elements</span></span>

|<span data-ttu-id="93b0a-113">要素</span><span class="sxs-lookup"><span data-stu-id="93b0a-113">Element</span></span>|<span data-ttu-id="93b0a-114">説明</span><span class="sxs-lookup"><span data-stu-id="93b0a-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="93b0a-115">WideControl の WideItem の FormatString 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="93b0a-115">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="93b0a-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="93b0a-116">Optional element.</span></span><br /><br /> <span data-ttu-id="93b0a-117">プロパティまたはスクリプトの値をビューに表示する方法を定義する形式パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="93b0a-117">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>|
|[<span data-ttu-id="93b0a-118">WideItem の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="93b0a-118">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="93b0a-119">ワイドビューに表示される値を持つオブジェクトのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="93b0a-119">Specifies the property of the object whose value is displayed in the wide view.</span></span>|
|[<span data-ttu-id="93b0a-120">WideItem の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="93b0a-120">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="93b0a-121">ワイドビューに値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="93b0a-121">Specifies the script whose value is displayed in the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="93b0a-122">親要素</span><span class="sxs-lookup"><span data-stu-id="93b0a-122">Parent Elements</span></span>

|<span data-ttu-id="93b0a-123">要素</span><span class="sxs-lookup"><span data-stu-id="93b0a-123">Element</span></span>|<span data-ttu-id="93b0a-124">説明</span><span class="sxs-lookup"><span data-stu-id="93b0a-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="93b0a-125">WideEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="93b0a-125">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="93b0a-126">ワイドビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="93b0a-126">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="93b0a-127">解説</span><span class="sxs-lookup"><span data-stu-id="93b0a-127">Remarks</span></span>

<span data-ttu-id="93b0a-128">ワイドビューのコンポーネントの詳細については、「 [Wide ビュー](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93b0a-128">For more information about the components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="93b0a-129">例</span><span class="sxs-lookup"><span data-stu-id="93b0a-129">Example</span></span>

<span data-ttu-id="93b0a-130">次の例は、 `WideEntry` 1 つの要素を定義する要素を示して `WideItem` います。</span><span class="sxs-lookup"><span data-stu-id="93b0a-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="93b0a-131">要素は、 `WideItem` ビューに値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="93b0a-131">The `WideItem` element defines the property or script whose value is displayed in the view.</span></span>

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

<span data-ttu-id="93b0a-132">ワイドビューの完全な例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93b0a-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="93b0a-133">参照</span><span class="sxs-lookup"><span data-stu-id="93b0a-133">See Also</span></span>

[<span data-ttu-id="93b0a-134">WideControl の WideItem の FormatString 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="93b0a-134">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="93b0a-135">WideItem の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="93b0a-135">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="93b0a-136">WideItem の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="93b0a-136">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="93b0a-137">WideEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="93b0a-137">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="93b0a-138">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="93b0a-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
