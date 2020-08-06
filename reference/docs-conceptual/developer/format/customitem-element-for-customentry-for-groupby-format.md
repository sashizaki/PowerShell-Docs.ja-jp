---
title: GroupBy (Format) の CustomEntry の CustomItem 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e8086c5330b6644f83316ad4ae33c33ba40d9eee
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783723"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a><span data-ttu-id="3361b-102">GroupBy の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3361b-102">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="3361b-103">カスタムコントロールビューとその表示方法によって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="3361b-103">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="3361b-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3361b-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="3361b-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素を groupby (形式) の CustomEntries 要素の groupby (format) Customentries 要素の CustomEntry の groupby (形式) 用に指定します。</span><span class="sxs-lookup"><span data-stu-id="3361b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3361b-106">構文</span><span class="sxs-lookup"><span data-stu-id="3361b-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3361b-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3361b-107">Attributes and Elements</span></span>

<span data-ttu-id="3361b-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomItem` ます。</span><span class="sxs-lookup"><span data-stu-id="3361b-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3361b-109">属性</span><span class="sxs-lookup"><span data-stu-id="3361b-109">Attributes</span></span>

<span data-ttu-id="3361b-110">なし。</span><span class="sxs-lookup"><span data-stu-id="3361b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3361b-111">子要素</span><span class="sxs-lookup"><span data-stu-id="3361b-111">Child Elements</span></span>

|<span data-ttu-id="3361b-112">要素</span><span class="sxs-lookup"><span data-stu-id="3361b-112">Element</span></span>|<span data-ttu-id="3361b-113">説明</span><span class="sxs-lookup"><span data-stu-id="3361b-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3361b-114">GroupBy の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3361b-114">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="3361b-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="3361b-115">Optional element.</span></span><br /><br /> <span data-ttu-id="3361b-116">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="3361b-116">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="3361b-117">GroupBy の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3361b-117">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="3361b-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="3361b-118">Optional element.</span></span><br /><br /> <span data-ttu-id="3361b-119">カスタムコントロールビューとその表示方法によって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="3361b-119">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="3361b-120">GroupBy の CustomItem の NewLine 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3361b-120">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="3361b-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="3361b-121">Optional element.</span></span><br /><br /> <span data-ttu-id="3361b-122">コントロールの表示に空白行を追加します。</span><span class="sxs-lookup"><span data-stu-id="3361b-122">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="3361b-123">GroupBy の CustomItem の Text 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3361b-123">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="3361b-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="3361b-124">Optional element.</span></span><br /><br /> <span data-ttu-id="3361b-125">コントロールによって表示されるデータに追加のテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="3361b-125">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3361b-126">親要素</span><span class="sxs-lookup"><span data-stu-id="3361b-126">Parent Elements</span></span>

|<span data-ttu-id="3361b-127">要素</span><span class="sxs-lookup"><span data-stu-id="3361b-127">Element</span></span>|<span data-ttu-id="3361b-128">説明</span><span class="sxs-lookup"><span data-stu-id="3361b-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3361b-129">GroupBy の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3361b-129">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="3361b-130">カスタムコントロールビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="3361b-130">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3361b-131">解説</span><span class="sxs-lookup"><span data-stu-id="3361b-131">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="3361b-132">参照</span><span class="sxs-lookup"><span data-stu-id="3361b-132">See Also</span></span>

[<span data-ttu-id="3361b-133">GroupBy の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3361b-133">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="3361b-134">GroupBy の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3361b-134">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="3361b-135">GroupBy の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3361b-135">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="3361b-136">GroupBy の CustomItem の NewLine 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3361b-136">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="3361b-137">GroupBy の CustomItem の Text 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3361b-137">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="3361b-138">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="3361b-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
