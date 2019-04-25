---
title: GroupBy (形式) の CustomEntry CustomItem 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7c517aa-24f5-41ae-b82d-cb0fac81a245
caps.latest.revision: 7
ms.openlocfilehash: 2d821f5e3bc8d0f81ef8a8a040c6f9bcb1658bee
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066399"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a><span data-ttu-id="563ee-102">GroupBy の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="563ee-102">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="563ee-103">カスタム コントロールのビューで表示するデータと表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="563ee-103">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="563ee-104">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="563ee-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="563ee-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomItem 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) の CustomEntry</span><span class="sxs-lookup"><span data-stu-id="563ee-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="563ee-106">構文</span><span class="sxs-lookup"><span data-stu-id="563ee-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="563ee-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="563ee-107">Attributes and Elements</span></span>

<span data-ttu-id="563ee-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomItem`要素。</span><span class="sxs-lookup"><span data-stu-id="563ee-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="563ee-109">属性</span><span class="sxs-lookup"><span data-stu-id="563ee-109">Attributes</span></span>

<span data-ttu-id="563ee-110">なし。</span><span class="sxs-lookup"><span data-stu-id="563ee-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="563ee-111">子要素</span><span class="sxs-lookup"><span data-stu-id="563ee-111">Child Elements</span></span>

|<span data-ttu-id="563ee-112">要素</span><span class="sxs-lookup"><span data-stu-id="563ee-112">Element</span></span>|<span data-ttu-id="563ee-113">説明</span><span class="sxs-lookup"><span data-stu-id="563ee-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="563ee-114">GroupBy (形式) の CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="563ee-114">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="563ee-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="563ee-115">Optional element.</span></span><br /><br /> <span data-ttu-id="563ee-116">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="563ee-116">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="563ee-117">GroupBy (形式) の CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="563ee-117">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="563ee-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="563ee-118">Optional element.</span></span><br /><br /> <span data-ttu-id="563ee-119">カスタム コントロールのビューで表示するデータと表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="563ee-119">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="563ee-120">GroupBy (形式) の CustomItem に改行要素</span><span class="sxs-lookup"><span data-stu-id="563ee-120">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="563ee-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="563ee-121">Optional element.</span></span><br /><br /> <span data-ttu-id="563ee-122">コントロールの表示には、空白行を追加します。</span><span class="sxs-lookup"><span data-stu-id="563ee-122">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="563ee-123">CustomItem GroupBy (形式) 用のテキスト要素</span><span class="sxs-lookup"><span data-stu-id="563ee-123">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="563ee-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="563ee-124">Optional element.</span></span><br /><br /> <span data-ttu-id="563ee-125">コントロールによって表示されるデータを追加のテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="563ee-125">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="563ee-126">親要素</span><span class="sxs-lookup"><span data-stu-id="563ee-126">Parent Elements</span></span>

|<span data-ttu-id="563ee-127">要素</span><span class="sxs-lookup"><span data-stu-id="563ee-127">Element</span></span>|<span data-ttu-id="563ee-128">説明</span><span class="sxs-lookup"><span data-stu-id="563ee-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="563ee-129">GroupBy (形式) のカスタム コントロールの CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="563ee-129">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="563ee-130">カスタム コントロールのビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="563ee-130">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="563ee-131">コメント</span><span class="sxs-lookup"><span data-stu-id="563ee-131">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="563ee-132">参照</span><span class="sxs-lookup"><span data-stu-id="563ee-132">See Also</span></span>

[<span data-ttu-id="563ee-133">GroupBy (形式) のカスタム コントロールの CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="563ee-133">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="563ee-134">GroupBy (形式) の CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="563ee-134">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="563ee-135">GroupBy (形式) の CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="563ee-135">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="563ee-136">GroupBy (形式) の CustomItem に改行要素</span><span class="sxs-lookup"><span data-stu-id="563ee-136">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="563ee-137">CustomItem GroupBy (形式) 用のテキスト要素</span><span class="sxs-lookup"><span data-stu-id="563ee-137">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="563ee-138">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="563ee-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
