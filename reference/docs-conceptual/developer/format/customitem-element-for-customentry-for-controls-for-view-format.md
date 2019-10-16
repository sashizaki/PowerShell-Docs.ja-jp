---
title: ビュー (Format) のコントロールに対する CustomEntry の CustomItem 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33cb5350-73ef-4b79-a879-0edf051869e4
caps.latest.revision: 7
ms.openlocfilehash: 174ba6a14819f823ec39f72e49a626e781221d8c
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363941"
---
# <a name="customitem-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="5da95-102">View の Controls の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5da95-102">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="5da95-103">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="5da95-103">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="5da95-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5da95-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="5da95-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素CustomControl for view (Format) CustomEntry 要素を使用して、ビュー (形式) のコントロールのためのビュー (形式) Customentries 要素を表示します。</span><span class="sxs-lookup"><span data-stu-id="5da95-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5da95-106">構文</span><span class="sxs-lookup"><span data-stu-id="5da95-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...<Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5da95-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="5da95-107">Attributes and Elements</span></span>

<span data-ttu-id="5da95-108">次のセクションでは、属性、子要素、`CustomItem` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5da95-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="5da95-109">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5da95-109">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="5da95-110">属性</span><span class="sxs-lookup"><span data-stu-id="5da95-110">Attributes</span></span>

<span data-ttu-id="5da95-111">なし。</span><span class="sxs-lookup"><span data-stu-id="5da95-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5da95-112">子要素</span><span class="sxs-lookup"><span data-stu-id="5da95-112">Child Elements</span></span>

|<span data-ttu-id="5da95-113">要素</span><span class="sxs-lookup"><span data-stu-id="5da95-113">Element</span></span>|<span data-ttu-id="5da95-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="5da95-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5da95-115">ビューのコントロールに対する CustomItem の式のバインド要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="5da95-115">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="5da95-116">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="5da95-116">Optional element.</span></span><br /><br /> <span data-ttu-id="5da95-117">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="5da95-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="5da95-118">ビューのコントロールの CustomItem の Frame 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="5da95-118">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="5da95-119">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="5da95-119">Optional element.</span></span><br /><br /> <span data-ttu-id="5da95-120">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="5da95-120">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="5da95-121">ビューのコントロールの CustomItem の改行要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="5da95-121">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="5da95-122">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="5da95-122">Optional element.</span></span><br /><br /> <span data-ttu-id="5da95-123">コントロールの表示に空白行を追加します。</span><span class="sxs-lookup"><span data-stu-id="5da95-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="5da95-124">ビューのコントロールの CustomItem のテキスト要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5da95-124">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="5da95-125">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="5da95-125">Optional element.</span></span><br /><br /> <span data-ttu-id="5da95-126">かっこや角かっこなどのテキストをコントロールの表示に追加します。</span><span class="sxs-lookup"><span data-stu-id="5da95-126">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5da95-127">親要素</span><span class="sxs-lookup"><span data-stu-id="5da95-127">Parent Elements</span></span>

|<span data-ttu-id="5da95-128">要素</span><span class="sxs-lookup"><span data-stu-id="5da95-128">Element</span></span>|<span data-ttu-id="5da95-129">[説明]</span><span class="sxs-lookup"><span data-stu-id="5da95-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5da95-130">ビューのコントロール (Format) の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="5da95-130">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="5da95-131">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="5da95-131">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5da95-132">コメント</span><span class="sxs-lookup"><span data-stu-id="5da95-132">Remarks</span></span>

<span data-ttu-id="5da95-133">@No__t-0 要素の子要素を指定する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="5da95-133">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="5da95-134">子要素は、`ExpressionBinding`、`NewLine`、`Text`、`Frame` の順に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5da95-134">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="5da95-135">指定できるシーケンスの数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="5da95-135">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="5da95-136">各シーケンスでは、使用できる @no__t 0 要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="5da95-136">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="5da95-137">参照</span><span class="sxs-lookup"><span data-stu-id="5da95-137">See Also</span></span>

[<span data-ttu-id="5da95-138">ビューのコントロールに対する CustomItem の式のバインド要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="5da95-138">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="5da95-139">ビューのコントロールの CustomItem の Frame 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="5da95-139">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="5da95-140">ビューのコントロールの CustomItem の改行要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="5da95-140">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="5da95-141">ビューのコントロールの CustomItem のテキスト要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5da95-141">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="5da95-142">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="5da95-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
