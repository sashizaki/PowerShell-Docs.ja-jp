---
title: CustomEntry for Controls for Controls の CustomItem 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: bb8124242496f192717127f201674bc1428e5de0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785865"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="e4fe3-102">Configuration の Controls の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e4fe3-102">CustomItem Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="e4fe3-103">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="e4fe3-103">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="e4fe3-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e4fe3-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="e4fe3-105">Configuration 要素 (Format) コントロールの構成 (format) コントロールの要素の構成 (形式) の CustomControl 要素の構成のためのコントロールの構成 (形式) の CustomEntries 要素を構成するための CustomControl の構成 (形式) の Custommentry 要素を構成するための CustomEntry の構成 (形式) Customentries 要素</span><span class="sxs-lookup"><span data-stu-id="e4fe3-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration</span></span>

## <a name="syntax"></a><span data-ttu-id="e4fe3-106">構文</span><span class="sxs-lookup"><span data-stu-id="e4fe3-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e4fe3-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e4fe3-107">Attributes and Elements</span></span>

<span data-ttu-id="e4fe3-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomItem` ます。</span><span class="sxs-lookup"><span data-stu-id="e4fe3-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="e4fe3-109">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4fe3-109">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="e4fe3-110">属性</span><span class="sxs-lookup"><span data-stu-id="e4fe3-110">Attributes</span></span>

<span data-ttu-id="e4fe3-111">なし。</span><span class="sxs-lookup"><span data-stu-id="e4fe3-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e4fe3-112">子要素</span><span class="sxs-lookup"><span data-stu-id="e4fe3-112">Child Elements</span></span>

|<span data-ttu-id="e4fe3-113">要素</span><span class="sxs-lookup"><span data-stu-id="e4fe3-113">Element</span></span>|<span data-ttu-id="e4fe3-114">説明</span><span class="sxs-lookup"><span data-stu-id="e4fe3-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e4fe3-115">Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e4fe3-115">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="e4fe3-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e4fe3-116">Optional element.</span></span><br /><br /> <span data-ttu-id="e4fe3-117">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="e4fe3-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="e4fe3-118">Configuration の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e4fe3-118">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="e4fe3-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e4fe3-119">Optional element.</span></span><br /><br /> <span data-ttu-id="e4fe3-120">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="e4fe3-120">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="e4fe3-121">Configuration の Controls の CustomItem の NewLine 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e4fe3-121">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="e4fe3-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e4fe3-122">Optional element.</span></span><br /><br /> <span data-ttu-id="e4fe3-123">コントロールの表示に空白行を追加します。</span><span class="sxs-lookup"><span data-stu-id="e4fe3-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="e4fe3-124">Configuration の Controls の CustomItem の Text 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e4fe3-124">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="e4fe3-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e4fe3-125">Optional element.</span></span><br /><br /> <span data-ttu-id="e4fe3-126">かっこや角かっこなどのテキストをコントロールの表示に追加します。</span><span class="sxs-lookup"><span data-stu-id="e4fe3-126">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e4fe3-127">親要素</span><span class="sxs-lookup"><span data-stu-id="e4fe3-127">Parent Elements</span></span>

|<span data-ttu-id="e4fe3-128">要素</span><span class="sxs-lookup"><span data-stu-id="e4fe3-128">Element</span></span>|<span data-ttu-id="e4fe3-129">説明</span><span class="sxs-lookup"><span data-stu-id="e4fe3-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e4fe3-130">Configuration の Controls の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e4fe3-130">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="e4fe3-131">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="e4fe3-131">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e4fe3-132">解説</span><span class="sxs-lookup"><span data-stu-id="e4fe3-132">Remarks</span></span>

<span data-ttu-id="e4fe3-133">要素の子要素を指定する場合 `CustomItem` は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e4fe3-133">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="e4fe3-134">子要素は、、、、およびの順に追加する必要があり `ExpressionBinding` `NewLine` `Text` `Frame` ます。</span><span class="sxs-lookup"><span data-stu-id="e4fe3-134">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="e4fe3-135">指定できるシーケンスの数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="e4fe3-135">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="e4fe3-136">各シーケンスには、使用できる要素の数に上限がありません `ExpressionBinding` 。</span><span class="sxs-lookup"><span data-stu-id="e4fe3-136">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4fe3-137">参照</span><span class="sxs-lookup"><span data-stu-id="e4fe3-137">See Also</span></span>

[<span data-ttu-id="e4fe3-138">Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e4fe3-138">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="e4fe3-139">Configuration の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e4fe3-139">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="e4fe3-140">Configuration の Controls の CustomItem の NewLine 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e4fe3-140">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="e4fe3-141">Configuration の Controls の CustomItem の Text 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e4fe3-141">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="e4fe3-142">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="e4fe3-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
