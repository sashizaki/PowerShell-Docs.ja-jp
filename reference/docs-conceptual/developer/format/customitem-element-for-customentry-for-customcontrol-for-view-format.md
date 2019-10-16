---
title: CustomControl for ビュー (Format) の CustomEntry の CustomItem 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98708c1d-6f39-4a76-b454-31153a6ade8c
caps.latest.revision: 12
ms.openlocfilehash: 3c110bd5fe3ef2f790ef136556afa7c29d0b5b29
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363951"
---
# <a name="customitem-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="57fcb-102">View の CustomControl の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="57fcb-102">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="57fcb-103">カスタムコントロールビューとその表示方法によって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="57fcb-103">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="57fcb-104">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="57fcb-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="57fcb-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素を表示するための CustomEntries for ビュー (形式) の Custommentry 要素CustomEntry ビュー (形式)</span><span class="sxs-lookup"><span data-stu-id="57fcb-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="57fcb-106">構文</span><span class="sxs-lookup"><span data-stu-id="57fcb-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="57fcb-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="57fcb-107">Attributes and Elements</span></span>

<span data-ttu-id="57fcb-108">次のセクションでは、属性、子要素、`CustomItem` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="57fcb-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="57fcb-109">属性</span><span class="sxs-lookup"><span data-stu-id="57fcb-109">Attributes</span></span>

<span data-ttu-id="57fcb-110">なし。</span><span class="sxs-lookup"><span data-stu-id="57fcb-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="57fcb-111">子要素</span><span class="sxs-lookup"><span data-stu-id="57fcb-111">Child Elements</span></span>

|<span data-ttu-id="57fcb-112">要素</span><span class="sxs-lookup"><span data-stu-id="57fcb-112">Element</span></span>|<span data-ttu-id="57fcb-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="57fcb-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="57fcb-114">CustomControl for ビュー (Format) に対する CustomItem の式のバインド要素</span><span class="sxs-lookup"><span data-stu-id="57fcb-114">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="57fcb-115">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="57fcb-115">Optional element.</span></span><br /><br /> <span data-ttu-id="57fcb-116">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="57fcb-116">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="57fcb-117">CustomControl for ビュー (Format) の CustomItem の Frame 要素</span><span class="sxs-lookup"><span data-stu-id="57fcb-117">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="57fcb-118">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="57fcb-118">Optional element.</span></span><br /><br /> <span data-ttu-id="57fcb-119">カスタムコントロールビューとその表示方法によって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="57fcb-119">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="57fcb-120">View (Format) のカスタムコントロールの CustomItem の改行要素</span><span class="sxs-lookup"><span data-stu-id="57fcb-120">NewLine Element for CustomItem for Custom Control for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="57fcb-121">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="57fcb-121">Optional element.</span></span><br /><br /> <span data-ttu-id="57fcb-122">コントロールの表示に空白行を追加します。</span><span class="sxs-lookup"><span data-stu-id="57fcb-122">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="57fcb-123">CustomControl for ビュー (Format) の CustomItem の Text 要素</span><span class="sxs-lookup"><span data-stu-id="57fcb-123">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)|<span data-ttu-id="57fcb-124">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="57fcb-124">Optional element.</span></span><br /><br /> <span data-ttu-id="57fcb-125">コントロールによって表示されるデータに追加のテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="57fcb-125">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="57fcb-126">親要素</span><span class="sxs-lookup"><span data-stu-id="57fcb-126">Parent Elements</span></span>

|<span data-ttu-id="57fcb-127">要素</span><span class="sxs-lookup"><span data-stu-id="57fcb-127">Element</span></span>|<span data-ttu-id="57fcb-128">[説明]</span><span class="sxs-lookup"><span data-stu-id="57fcb-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="57fcb-129">CustomControl for ビュー (Format) の CustomEntries の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="57fcb-129">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="57fcb-130">カスタムコントロールビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="57fcb-130">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="57fcb-131">コメント</span><span class="sxs-lookup"><span data-stu-id="57fcb-131">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="57fcb-132">参照</span><span class="sxs-lookup"><span data-stu-id="57fcb-132">See Also</span></span>

[<span data-ttu-id="57fcb-133">View (Format) の CustomEntries の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="57fcb-133">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="57fcb-134">CustomControl for ビュー (Format) に対する CustomItem の式のバインド要素</span><span class="sxs-lookup"><span data-stu-id="57fcb-134">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="57fcb-135">CustomControl for ビュー (Format) の CustomItem の Frame 要素</span><span class="sxs-lookup"><span data-stu-id="57fcb-135">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="57fcb-136">CustomControl for ビュー (Format) の CustomItem の改行要素</span><span class="sxs-lookup"><span data-stu-id="57fcb-136">NewLine Element for CustomItem for CustomControl for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="57fcb-137">CustomControl for ビュー (Format) の CustomItem の Text 要素</span><span class="sxs-lookup"><span data-stu-id="57fcb-137">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)

[<span data-ttu-id="57fcb-138">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="57fcb-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
