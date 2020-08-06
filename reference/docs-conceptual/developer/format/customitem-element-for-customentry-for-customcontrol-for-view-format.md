---
title: CustomControl for ビュー (Format) の CustomEntry の CustomItem 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 25101c9c156ef91657f51db7044bf9a6653142a2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785831"
---
# <a name="customitem-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="28cff-102">View の CustomControl の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="28cff-102">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="28cff-103">カスタムコントロールビューとその表示方法によって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="28cff-103">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="28cff-104">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="28cff-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="28cff-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl 要素 (形式) CustomControl for view (format) の CustomEntries 要素のビュー (形式) の CustomEntries を指定します。この要素は、CustomEntry for ビュー (形式) の Customentries 要素です。</span><span class="sxs-lookup"><span data-stu-id="28cff-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="28cff-106">構文</span><span class="sxs-lookup"><span data-stu-id="28cff-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="28cff-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="28cff-107">Attributes and Elements</span></span>

<span data-ttu-id="28cff-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomItem` ます。</span><span class="sxs-lookup"><span data-stu-id="28cff-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="28cff-109">属性</span><span class="sxs-lookup"><span data-stu-id="28cff-109">Attributes</span></span>

<span data-ttu-id="28cff-110">なし。</span><span class="sxs-lookup"><span data-stu-id="28cff-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="28cff-111">子要素</span><span class="sxs-lookup"><span data-stu-id="28cff-111">Child Elements</span></span>

|<span data-ttu-id="28cff-112">要素</span><span class="sxs-lookup"><span data-stu-id="28cff-112">Element</span></span>|<span data-ttu-id="28cff-113">説明</span><span class="sxs-lookup"><span data-stu-id="28cff-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="28cff-114">View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="28cff-114">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="28cff-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="28cff-115">Optional element.</span></span><br /><br /> <span data-ttu-id="28cff-116">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="28cff-116">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="28cff-117">View の CustomControl の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="28cff-117">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="28cff-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="28cff-118">Optional element.</span></span><br /><br /> <span data-ttu-id="28cff-119">カスタムコントロールビューとその表示方法によって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="28cff-119">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="28cff-120">View (Format) のカスタムコントロールの CustomItem の改行要素</span><span class="sxs-lookup"><span data-stu-id="28cff-120">NewLine Element for CustomItem for Custom Control for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="28cff-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="28cff-121">Optional element.</span></span><br /><br /> <span data-ttu-id="28cff-122">コントロールの表示に空白行を追加します。</span><span class="sxs-lookup"><span data-stu-id="28cff-122">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="28cff-123">CustomControl for ビュー (Format) の CustomItem の Text 要素</span><span class="sxs-lookup"><span data-stu-id="28cff-123">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)|<span data-ttu-id="28cff-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="28cff-124">Optional element.</span></span><br /><br /> <span data-ttu-id="28cff-125">コントロールによって表示されるデータに追加のテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="28cff-125">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="28cff-126">親要素</span><span class="sxs-lookup"><span data-stu-id="28cff-126">Parent Elements</span></span>

|<span data-ttu-id="28cff-127">要素</span><span class="sxs-lookup"><span data-stu-id="28cff-127">Element</span></span>|<span data-ttu-id="28cff-128">説明</span><span class="sxs-lookup"><span data-stu-id="28cff-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="28cff-129">View の CustomControl の CustomEntries の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="28cff-129">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="28cff-130">カスタムコントロールビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="28cff-130">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="28cff-131">解説</span><span class="sxs-lookup"><span data-stu-id="28cff-131">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="28cff-132">参照</span><span class="sxs-lookup"><span data-stu-id="28cff-132">See Also</span></span>

[<span data-ttu-id="28cff-133">View (Format) の CustomEntries の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="28cff-133">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="28cff-134">View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="28cff-134">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="28cff-135">View の CustomControl の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="28cff-135">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="28cff-136">View の CustomControl の CustomItem の NewLine 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="28cff-136">NewLine Element for CustomItem for CustomControl for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="28cff-137">CustomControl for ビュー (Format) の CustomItem の Text 要素</span><span class="sxs-lookup"><span data-stu-id="28cff-137">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)

[<span data-ttu-id="28cff-138">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="28cff-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
