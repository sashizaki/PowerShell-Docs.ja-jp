---
title: GroupBy (Format) の CustomEntry の CustomItem 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7c517aa-24f5-41ae-b82d-cb0fac81a245
caps.latest.revision: 7
ms.openlocfilehash: 2d821f5e3bc8d0f81ef8a8a040c6f9bcb1658bee
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363881"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a><span data-ttu-id="f2de9-102">GroupBy の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f2de9-102">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="f2de9-103">カスタムコントロールビューとその表示方法によって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="f2de9-103">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="f2de9-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f2de9-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="f2de9-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素の groupby (format) CustomControl 要素の groupby (書式) Customentries 要素の CustomControl の CustomEntries 要素GroupBy の CustomEntry (形式)</span><span class="sxs-lookup"><span data-stu-id="f2de9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f2de9-106">構文</span><span class="sxs-lookup"><span data-stu-id="f2de9-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f2de9-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="f2de9-107">Attributes and Elements</span></span>

<span data-ttu-id="f2de9-108">次のセクションでは、`CustomItem` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f2de9-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f2de9-109">属性</span><span class="sxs-lookup"><span data-stu-id="f2de9-109">Attributes</span></span>

<span data-ttu-id="f2de9-110">なし。</span><span class="sxs-lookup"><span data-stu-id="f2de9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f2de9-111">子要素</span><span class="sxs-lookup"><span data-stu-id="f2de9-111">Child Elements</span></span>

|<span data-ttu-id="f2de9-112">要素</span><span class="sxs-lookup"><span data-stu-id="f2de9-112">Element</span></span>|<span data-ttu-id="f2de9-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="f2de9-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f2de9-114">GroupBy (Format) の CustomItem の式のバインド要素</span><span class="sxs-lookup"><span data-stu-id="f2de9-114">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="f2de9-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f2de9-115">Optional element.</span></span><br /><br /> <span data-ttu-id="f2de9-116">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="f2de9-116">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="f2de9-117">GroupBy (Format) の CustomItem の Frame 要素</span><span class="sxs-lookup"><span data-stu-id="f2de9-117">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="f2de9-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f2de9-118">Optional element.</span></span><br /><br /> <span data-ttu-id="f2de9-119">カスタムコントロールビューとその表示方法によって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="f2de9-119">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="f2de9-120">GroupBy (Format) の CustomItem の改行要素</span><span class="sxs-lookup"><span data-stu-id="f2de9-120">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="f2de9-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f2de9-121">Optional element.</span></span><br /><br /> <span data-ttu-id="f2de9-122">コントロールの表示に空白行を追加します。</span><span class="sxs-lookup"><span data-stu-id="f2de9-122">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="f2de9-123">GroupBy (Format) の CustomItem のテキスト要素</span><span class="sxs-lookup"><span data-stu-id="f2de9-123">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="f2de9-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f2de9-124">Optional element.</span></span><br /><br /> <span data-ttu-id="f2de9-125">コントロールによって表示されるデータに追加のテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="f2de9-125">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f2de9-126">親要素</span><span class="sxs-lookup"><span data-stu-id="f2de9-126">Parent Elements</span></span>

|<span data-ttu-id="f2de9-127">要素</span><span class="sxs-lookup"><span data-stu-id="f2de9-127">Element</span></span>|<span data-ttu-id="f2de9-128">[説明]</span><span class="sxs-lookup"><span data-stu-id="f2de9-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f2de9-129">GroupBy (Format) の CustomControl の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="f2de9-129">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="f2de9-130">カスタムコントロールビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="f2de9-130">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f2de9-131">コメント</span><span class="sxs-lookup"><span data-stu-id="f2de9-131">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="f2de9-132">参照</span><span class="sxs-lookup"><span data-stu-id="f2de9-132">See Also</span></span>

[<span data-ttu-id="f2de9-133">GroupBy (Format) の CustomControl の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="f2de9-133">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="f2de9-134">GroupBy (Format) の CustomItem の式のバインド要素</span><span class="sxs-lookup"><span data-stu-id="f2de9-134">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="f2de9-135">GroupBy (Format) の CustomItem の Frame 要素</span><span class="sxs-lookup"><span data-stu-id="f2de9-135">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="f2de9-136">GroupBy (Format) の CustomItem の改行要素</span><span class="sxs-lookup"><span data-stu-id="f2de9-136">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="f2de9-137">GroupBy (Format) の CustomItem のテキスト要素</span><span class="sxs-lookup"><span data-stu-id="f2de9-137">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="f2de9-138">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="f2de9-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
