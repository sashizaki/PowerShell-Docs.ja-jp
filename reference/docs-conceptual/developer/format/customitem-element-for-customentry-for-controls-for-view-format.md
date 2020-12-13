---
ms.date: 09/13/2016
ms.topic: reference
title: View の Controls の CustomEntry の CustomItem 要素 (書式)
description: View の Controls の CustomEntry の CustomItem 要素 (書式)
ms.openlocfilehash: 67bff97c27cfedf046b17eea438efcd66ae2ee4a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666758"
---
# <a name="customitem-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="50532-103">View の Controls の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="50532-103">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="50532-104">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="50532-104">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="50532-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="50532-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="50532-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビューのコントロール要素 (format) コントロールの要素 (書式) コントロールのコントロール要素 (format) のコントロール要素 (形式)) の CustomEntries 要素を使用して、CustomControl for view (format) の CustomEntry 要素を使用して、ビュー (Format) のコントロールのためのビュー (format) Customentries 要素を表示します。</span><span class="sxs-lookup"><span data-stu-id="50532-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="50532-107">構文</span><span class="sxs-lookup"><span data-stu-id="50532-107">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...<Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="50532-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="50532-108">Attributes and Elements</span></span>

<span data-ttu-id="50532-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomItem` ます。</span><span class="sxs-lookup"><span data-stu-id="50532-109">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="50532-110">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50532-110">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="50532-111">属性</span><span class="sxs-lookup"><span data-stu-id="50532-111">Attributes</span></span>

<span data-ttu-id="50532-112">なし。</span><span class="sxs-lookup"><span data-stu-id="50532-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="50532-113">子要素</span><span class="sxs-lookup"><span data-stu-id="50532-113">Child Elements</span></span>

|<span data-ttu-id="50532-114">要素</span><span class="sxs-lookup"><span data-stu-id="50532-114">Element</span></span>|<span data-ttu-id="50532-115">説明</span><span class="sxs-lookup"><span data-stu-id="50532-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="50532-116">View の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="50532-116">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="50532-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="50532-117">Optional element.</span></span><br /><br /> <span data-ttu-id="50532-118">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="50532-118">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="50532-119">View の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="50532-119">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="50532-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="50532-120">Optional element.</span></span><br /><br /> <span data-ttu-id="50532-121">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="50532-121">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="50532-122">View の Controls の CustomItem の NewLine 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="50532-122">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="50532-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="50532-123">Optional element.</span></span><br /><br /> <span data-ttu-id="50532-124">コントロールの表示に空白行を追加します。</span><span class="sxs-lookup"><span data-stu-id="50532-124">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="50532-125">View の Controls の CustomItem の Text 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="50532-125">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="50532-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="50532-126">Optional element.</span></span><br /><br /> <span data-ttu-id="50532-127">かっこや角かっこなどのテキストをコントロールの表示に追加します。</span><span class="sxs-lookup"><span data-stu-id="50532-127">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="50532-128">親要素</span><span class="sxs-lookup"><span data-stu-id="50532-128">Parent Elements</span></span>

|<span data-ttu-id="50532-129">要素</span><span class="sxs-lookup"><span data-stu-id="50532-129">Element</span></span>|<span data-ttu-id="50532-130">説明</span><span class="sxs-lookup"><span data-stu-id="50532-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="50532-131">View の Controls の CustomEntries の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="50532-131">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="50532-132">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="50532-132">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="50532-133">解説</span><span class="sxs-lookup"><span data-stu-id="50532-133">Remarks</span></span>

<span data-ttu-id="50532-134">要素の子要素を指定する場合 `CustomItem` は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="50532-134">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="50532-135">子要素は、、、、およびの順に追加する必要があり `ExpressionBinding` `NewLine` `Text` `Frame` ます。</span><span class="sxs-lookup"><span data-stu-id="50532-135">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="50532-136">指定できるシーケンスの数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="50532-136">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="50532-137">各シーケンスには、使用できる要素の数に上限がありません `ExpressionBinding` 。</span><span class="sxs-lookup"><span data-stu-id="50532-137">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="50532-138">参照</span><span class="sxs-lookup"><span data-stu-id="50532-138">See Also</span></span>

[<span data-ttu-id="50532-139">View の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="50532-139">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="50532-140">View の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="50532-140">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="50532-141">View の Controls の CustomItem の NewLine 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="50532-141">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="50532-142">View の Controls の CustomItem の Text 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="50532-142">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="50532-143">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="50532-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
