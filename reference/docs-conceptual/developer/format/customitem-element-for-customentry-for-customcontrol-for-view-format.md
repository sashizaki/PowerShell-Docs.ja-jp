---
ms.date: 09/13/2016
ms.topic: reference
title: View の CustomControl の CustomEntry の CustomItem 要素 (書式)
description: View の CustomControl の CustomEntry の CustomItem 要素 (書式)
ms.openlocfilehash: 9090a3ada5316ba5ddb4a9c46eee37c11982ae6e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666741"
---
# <a name="customitem-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="b0d6b-103">View の CustomControl の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b0d6b-103">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="b0d6b-104">カスタムコントロールビューとその表示方法によって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="b0d6b-104">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="b0d6b-105">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0d6b-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="b0d6b-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl 要素 (形式) CustomControl for view (format) の CustomEntries 要素のビュー (形式) の CustomEntries を指定します。この要素は、CustomEntry for ビュー (形式) の Customentries 要素です。</span><span class="sxs-lookup"><span data-stu-id="b0d6b-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b0d6b-107">構文</span><span class="sxs-lookup"><span data-stu-id="b0d6b-107">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b0d6b-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b0d6b-108">Attributes and Elements</span></span>

<span data-ttu-id="b0d6b-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomItem` ます。</span><span class="sxs-lookup"><span data-stu-id="b0d6b-109">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b0d6b-110">属性</span><span class="sxs-lookup"><span data-stu-id="b0d6b-110">Attributes</span></span>

<span data-ttu-id="b0d6b-111">なし。</span><span class="sxs-lookup"><span data-stu-id="b0d6b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b0d6b-112">子要素</span><span class="sxs-lookup"><span data-stu-id="b0d6b-112">Child Elements</span></span>

|<span data-ttu-id="b0d6b-113">要素</span><span class="sxs-lookup"><span data-stu-id="b0d6b-113">Element</span></span>|<span data-ttu-id="b0d6b-114">説明</span><span class="sxs-lookup"><span data-stu-id="b0d6b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b0d6b-115">View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b0d6b-115">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="b0d6b-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="b0d6b-116">Optional element.</span></span><br /><br /> <span data-ttu-id="b0d6b-117">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="b0d6b-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="b0d6b-118">View の CustomControl の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b0d6b-118">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="b0d6b-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="b0d6b-119">Optional element.</span></span><br /><br /> <span data-ttu-id="b0d6b-120">カスタムコントロールビューとその表示方法によって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="b0d6b-120">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="b0d6b-121">View (Format) のカスタムコントロールの CustomItem の改行要素</span><span class="sxs-lookup"><span data-stu-id="b0d6b-121">NewLine Element for CustomItem for Custom Control for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="b0d6b-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="b0d6b-122">Optional element.</span></span><br /><br /> <span data-ttu-id="b0d6b-123">コントロールの表示に空白行を追加します。</span><span class="sxs-lookup"><span data-stu-id="b0d6b-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="b0d6b-124">CustomControl for ビュー (Format) の CustomItem の Text 要素</span><span class="sxs-lookup"><span data-stu-id="b0d6b-124">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)|<span data-ttu-id="b0d6b-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="b0d6b-125">Optional element.</span></span><br /><br /> <span data-ttu-id="b0d6b-126">コントロールによって表示されるデータに追加のテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0d6b-126">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b0d6b-127">親要素</span><span class="sxs-lookup"><span data-stu-id="b0d6b-127">Parent Elements</span></span>

|<span data-ttu-id="b0d6b-128">要素</span><span class="sxs-lookup"><span data-stu-id="b0d6b-128">Element</span></span>|<span data-ttu-id="b0d6b-129">説明</span><span class="sxs-lookup"><span data-stu-id="b0d6b-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b0d6b-130">View の CustomControl の CustomEntries の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b0d6b-130">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="b0d6b-131">カスタムコントロールビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="b0d6b-131">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b0d6b-132">解説</span><span class="sxs-lookup"><span data-stu-id="b0d6b-132">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="b0d6b-133">参照</span><span class="sxs-lookup"><span data-stu-id="b0d6b-133">See Also</span></span>

[<span data-ttu-id="b0d6b-134">View (Format) の CustomEntries の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="b0d6b-134">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="b0d6b-135">View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b0d6b-135">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="b0d6b-136">View の CustomControl の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b0d6b-136">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="b0d6b-137">View の CustomControl の CustomItem の NewLine 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b0d6b-137">NewLine Element for CustomItem for CustomControl for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="b0d6b-138">CustomControl for ビュー (Format) の CustomItem の Text 要素</span><span class="sxs-lookup"><span data-stu-id="b0d6b-138">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)

[<span data-ttu-id="b0d6b-139">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="b0d6b-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
