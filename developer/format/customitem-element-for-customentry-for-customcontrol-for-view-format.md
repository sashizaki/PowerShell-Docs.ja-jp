---
title: ビュー (形式) のカスタム コントロールの CustomEntry CustomItem 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98708c1d-6f39-4a76-b454-31153a6ade8c
caps.latest.revision: 12
ms.openlocfilehash: 3c110bd5fe3ef2f790ef136556afa7c29d0b5b29
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066415"
---
# <a name="customitem-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="b2564-102">View の CustomControl の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b2564-102">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="b2564-103">カスタム コントロールのビューで表示するデータと表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="b2564-103">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="b2564-104">この要素は、カスタム コントロールのビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b2564-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="b2564-105">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) CustomItem 要素 CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールCustomEntry 表示されます (形式)</span><span class="sxs-lookup"><span data-stu-id="b2564-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b2564-106">構文</span><span class="sxs-lookup"><span data-stu-id="b2564-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b2564-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b2564-107">Attributes and Elements</span></span>

<span data-ttu-id="b2564-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomItem`要素。</span><span class="sxs-lookup"><span data-stu-id="b2564-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b2564-109">属性</span><span class="sxs-lookup"><span data-stu-id="b2564-109">Attributes</span></span>

<span data-ttu-id="b2564-110">なし。</span><span class="sxs-lookup"><span data-stu-id="b2564-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b2564-111">子要素</span><span class="sxs-lookup"><span data-stu-id="b2564-111">Child Elements</span></span>

|<span data-ttu-id="b2564-112">要素</span><span class="sxs-lookup"><span data-stu-id="b2564-112">Element</span></span>|<span data-ttu-id="b2564-113">説明</span><span class="sxs-lookup"><span data-stu-id="b2564-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b2564-114">ビュー (形式) のカスタム コントロールの CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="b2564-114">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="b2564-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="b2564-115">Optional element.</span></span><br /><br /> <span data-ttu-id="b2564-116">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="b2564-116">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="b2564-117">ビュー (形式) のカスタム コントロールの CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="b2564-117">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="b2564-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="b2564-118">Optional element.</span></span><br /><br /> <span data-ttu-id="b2564-119">カスタム コントロールのビューで表示するデータと表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="b2564-119">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="b2564-120">ビュー (形式) 用のカスタム コントロールの CustomItem に改行要素</span><span class="sxs-lookup"><span data-stu-id="b2564-120">NewLine Element for CustomItem for Custom Control for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="b2564-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="b2564-121">Optional element.</span></span><br /><br /> <span data-ttu-id="b2564-122">コントロールの表示には、空白行を追加します。</span><span class="sxs-lookup"><span data-stu-id="b2564-122">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="b2564-123">CustomItem ビュー (形式) のカスタム コントロールのテキスト要素</span><span class="sxs-lookup"><span data-stu-id="b2564-123">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)|<span data-ttu-id="b2564-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="b2564-124">Optional element.</span></span><br /><br /> <span data-ttu-id="b2564-125">コントロールによって表示されるデータを追加のテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="b2564-125">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b2564-126">親要素</span><span class="sxs-lookup"><span data-stu-id="b2564-126">Parent Elements</span></span>

|<span data-ttu-id="b2564-127">要素</span><span class="sxs-lookup"><span data-stu-id="b2564-127">Element</span></span>|<span data-ttu-id="b2564-128">説明</span><span class="sxs-lookup"><span data-stu-id="b2564-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b2564-129">ビュー (形式) のカスタム コントロールの CustomEntries CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="b2564-129">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="b2564-130">カスタム コントロールのビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="b2564-130">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b2564-131">コメント</span><span class="sxs-lookup"><span data-stu-id="b2564-131">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="b2564-132">参照</span><span class="sxs-lookup"><span data-stu-id="b2564-132">See Also</span></span>

[<span data-ttu-id="b2564-133">表示 (形式) CustomEntries CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="b2564-133">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="b2564-134">ビュー (形式) のカスタム コントロールの CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="b2564-134">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="b2564-135">ビュー (形式) のカスタム コントロールの CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="b2564-135">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="b2564-136">ビュー (形式) のカスタム コントロールの CustomItem に改行要素</span><span class="sxs-lookup"><span data-stu-id="b2564-136">NewLine Element for CustomItem for CustomControl for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="b2564-137">CustomItem ビュー (形式) のカスタム コントロールのテキスト要素</span><span class="sxs-lookup"><span data-stu-id="b2564-137">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)

[<span data-ttu-id="b2564-138">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="b2564-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
