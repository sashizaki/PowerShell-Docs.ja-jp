---
title: WideControl の WideItem 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17352fc4-ba83-4f04-86bc-f591765d85a8
caps.latest.revision: 18
ms.openlocfilehash: fa9eda3ea1028c27dbfb3eb04747af3b817c1a81
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361401"
---
# <a name="wideitem-element-for-widecontrol-format"></a><span data-ttu-id="da74d-102">WideControl の WideItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="da74d-102">WideItem Element for WideControl (Format)</span></span>

<span data-ttu-id="da74d-103">値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="da74d-103">Defines the property or script whose value is displayed.</span></span>

<span data-ttu-id="da74d-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (Format) WideEntries Element (format) WideEntry Element (format) WideItem Element (Format)</span><span class="sxs-lookup"><span data-stu-id="da74d-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="da74d-105">構文</span><span class="sxs-lookup"><span data-stu-id="da74d-105">Syntax</span></span>

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="da74d-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="da74d-106">Attributes and Elements</span></span>

<span data-ttu-id="da74d-107">次のセクションでは、`WideItem` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="da74d-107">The following sections describe the attributes, child elements, and the parent element of the `WideItem` element.</span></span> <span data-ttu-id="da74d-108">`FormatString` 要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="da74d-108">The `FormatString` element is optional.</span></span> <span data-ttu-id="da74d-109">ただし、`PropertyName` または `ScriptBlock` 要素を指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="da74d-109">However, you must specify a `PropertyName` or `ScriptBlock` element, but you cannot specify both.</span></span>

### <a name="attributes"></a><span data-ttu-id="da74d-110">属性</span><span class="sxs-lookup"><span data-stu-id="da74d-110">Attributes</span></span>

<span data-ttu-id="da74d-111">なし。</span><span class="sxs-lookup"><span data-stu-id="da74d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="da74d-112">子要素</span><span class="sxs-lookup"><span data-stu-id="da74d-112">Child Elements</span></span>

|<span data-ttu-id="da74d-113">要素</span><span class="sxs-lookup"><span data-stu-id="da74d-113">Element</span></span>|<span data-ttu-id="da74d-114">説明</span><span class="sxs-lookup"><span data-stu-id="da74d-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="da74d-115">WideControl の WideItem の FormatString 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="da74d-115">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="da74d-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="da74d-116">Optional element.</span></span><br /><br /> <span data-ttu-id="da74d-117">プロパティまたはスクリプトの値をビューに表示する方法を定義する形式パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="da74d-117">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>|
|[<span data-ttu-id="da74d-118">WideItem の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="da74d-118">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="da74d-119">ワイドビューに表示される値を持つオブジェクトのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="da74d-119">Specifies the property of the object whose value is displayed in the wide view.</span></span>|
|[<span data-ttu-id="da74d-120">WideItem の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="da74d-120">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="da74d-121">ワイドビューに値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="da74d-121">Specifies the script whose value is displayed in the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="da74d-122">親要素</span><span class="sxs-lookup"><span data-stu-id="da74d-122">Parent Elements</span></span>

|<span data-ttu-id="da74d-123">要素</span><span class="sxs-lookup"><span data-stu-id="da74d-123">Element</span></span>|<span data-ttu-id="da74d-124">説明</span><span class="sxs-lookup"><span data-stu-id="da74d-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="da74d-125">WideEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="da74d-125">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="da74d-126">ワイドビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="da74d-126">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="da74d-127">コメント</span><span class="sxs-lookup"><span data-stu-id="da74d-127">Remarks</span></span>

<span data-ttu-id="da74d-128">ワイドビューのコンポーネントの詳細については、「 [Wide ビュー](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da74d-128">For more information about the components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="da74d-129">例</span><span class="sxs-lookup"><span data-stu-id="da74d-129">Example</span></span>

<span data-ttu-id="da74d-130">次の例は、単一の `WideItem` 要素を定義する `WideEntry` 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="da74d-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="da74d-131">`WideItem` 要素は、ビューに値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="da74d-131">The `WideItem` element defines the property or script whose value is displayed in the view.</span></span>

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

<span data-ttu-id="da74d-132">ワイドビューの完全な例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da74d-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="da74d-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="da74d-133">See Also</span></span>

[<span data-ttu-id="da74d-134">WideControl の WideItem の FormatString 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="da74d-134">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="da74d-135">WideItem の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="da74d-135">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="da74d-136">WideItem の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="da74d-136">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="da74d-137">WideEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="da74d-137">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="da74d-138">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="da74d-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
