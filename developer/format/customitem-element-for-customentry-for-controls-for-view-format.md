---
title: コントロールが表示されます (形式) の CustomEntry CustomItem 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33cb5350-73ef-4b79-a879-0edf051869e4
caps.latest.revision: 7
ms.openlocfilehash: 174ba6a14819f823ec39f72e49a626e781221d8c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855608"
---
# <a name="customitem-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="cf9f1-102">View の Controls の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cf9f1-102">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="cf9f1-103">どのようなデータが、コントロールによって表示され、表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="cf9f1-103">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="cf9f1-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf9f1-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="cf9f1-105">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry ビュー (形式) のコントロールのビュー (形式) CustomItem 要素のコントロールのビュー (形式) CustomEntry 要素のカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="cf9f1-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cf9f1-106">構文</span><span class="sxs-lookup"><span data-stu-id="cf9f1-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...<Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cf9f1-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="cf9f1-107">Attributes and Elements</span></span>

<span data-ttu-id="cf9f1-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomItem`要素。</span><span class="sxs-lookup"><span data-stu-id="cf9f1-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="cf9f1-109">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf9f1-109">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="cf9f1-110">属性</span><span class="sxs-lookup"><span data-stu-id="cf9f1-110">Attributes</span></span>

<span data-ttu-id="cf9f1-111">なし。</span><span class="sxs-lookup"><span data-stu-id="cf9f1-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cf9f1-112">子要素</span><span class="sxs-lookup"><span data-stu-id="cf9f1-112">Child Elements</span></span>

|<span data-ttu-id="cf9f1-113">要素</span><span class="sxs-lookup"><span data-stu-id="cf9f1-113">Element</span></span>|<span data-ttu-id="cf9f1-114">説明</span><span class="sxs-lookup"><span data-stu-id="cf9f1-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cf9f1-115">コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="cf9f1-115">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="cf9f1-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="cf9f1-116">Optional element.</span></span><br /><br /> <span data-ttu-id="cf9f1-117">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="cf9f1-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="cf9f1-118">コントロールが表示されます (形式) の CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="cf9f1-118">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="cf9f1-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="cf9f1-119">Optional element.</span></span><br /><br /> <span data-ttu-id="cf9f1-120">データを左または右にシフトなど、データを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="cf9f1-120">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="cf9f1-121">コントロールが表示されます (形式) の CustomItem の改行要素</span><span class="sxs-lookup"><span data-stu-id="cf9f1-121">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="cf9f1-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="cf9f1-122">Optional element.</span></span><br /><br /> <span data-ttu-id="cf9f1-123">コントロールの表示には、空白行を追加します。</span><span class="sxs-lookup"><span data-stu-id="cf9f1-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="cf9f1-124">CustomItem ビュー (形式) のコントロールのテキスト要素</span><span class="sxs-lookup"><span data-stu-id="cf9f1-124">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="cf9f1-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="cf9f1-125">Optional element.</span></span><br /><br /> <span data-ttu-id="cf9f1-126">コントロールの表示には、かっこ、角かっこなどのテキストを追加します。</span><span class="sxs-lookup"><span data-stu-id="cf9f1-126">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cf9f1-127">親要素</span><span class="sxs-lookup"><span data-stu-id="cf9f1-127">Parent Elements</span></span>

|<span data-ttu-id="cf9f1-128">要素</span><span class="sxs-lookup"><span data-stu-id="cf9f1-128">Element</span></span>|<span data-ttu-id="cf9f1-129">説明</span><span class="sxs-lookup"><span data-stu-id="cf9f1-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cf9f1-130">コントロールが表示されます (形式) の CustomEntries CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="cf9f1-130">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="cf9f1-131">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="cf9f1-131">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cf9f1-132">コメント</span><span class="sxs-lookup"><span data-stu-id="cf9f1-132">Remarks</span></span>

<span data-ttu-id="cf9f1-133">子要素を指定するときに、`CustomItem`要素、次に留意します。</span><span class="sxs-lookup"><span data-stu-id="cf9f1-133">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="cf9f1-134">次の順序で子要素を追加する必要があります: `ExpressionBinding`、 `NewLine`、 `Text`、および`Frame`します。</span><span class="sxs-lookup"><span data-stu-id="cf9f1-134">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="cf9f1-135">指定できるシーケンスの数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="cf9f1-135">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="cf9f1-136">各シーケンスの数に上限はありません`ExpressionBinding`要素を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="cf9f1-136">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf9f1-137">参照</span><span class="sxs-lookup"><span data-stu-id="cf9f1-137">See Also</span></span>

[<span data-ttu-id="cf9f1-138">コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="cf9f1-138">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="cf9f1-139">コントロールが表示されます (形式) の CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="cf9f1-139">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="cf9f1-140">コントロールが表示されます (形式) の CustomItem の改行要素</span><span class="sxs-lookup"><span data-stu-id="cf9f1-140">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="cf9f1-141">CustomItem ビュー (形式) のコントロールのテキスト要素</span><span class="sxs-lookup"><span data-stu-id="cf9f1-141">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="cf9f1-142">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="cf9f1-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
