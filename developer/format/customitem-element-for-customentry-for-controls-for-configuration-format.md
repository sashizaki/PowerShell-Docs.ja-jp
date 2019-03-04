---
title: 構成 (形式) のコントロールの CustomEntry CustomItem 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73fb11ee-0ebd-477a-ac36-acdfbb32e70d
caps.latest.revision: 7
ms.openlocfilehash: bd0cb69770817ec215ddb1862a43a838baddefcf
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862938"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="f91f4-102">Configuration の Controls の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f91f4-102">CustomItem Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="f91f4-103">どのようなデータが、コントロールによって表示され、表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="f91f4-103">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="f91f4-104">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f91f4-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="f91f4-105">構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素コントロールの構成の CustomEntry の構成 (形式) CustomItem 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="f91f4-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration</span></span>

## <a name="syntax"></a><span data-ttu-id="f91f4-106">構文</span><span class="sxs-lookup"><span data-stu-id="f91f4-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f91f4-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="f91f4-107">Attributes and Elements</span></span>

<span data-ttu-id="f91f4-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomItem`要素。</span><span class="sxs-lookup"><span data-stu-id="f91f4-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="f91f4-109">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f91f4-109">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="f91f4-110">属性</span><span class="sxs-lookup"><span data-stu-id="f91f4-110">Attributes</span></span>

<span data-ttu-id="f91f4-111">なし。</span><span class="sxs-lookup"><span data-stu-id="f91f4-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f91f4-112">子要素</span><span class="sxs-lookup"><span data-stu-id="f91f4-112">Child Elements</span></span>

|<span data-ttu-id="f91f4-113">要素</span><span class="sxs-lookup"><span data-stu-id="f91f4-113">Element</span></span>|<span data-ttu-id="f91f4-114">説明</span><span class="sxs-lookup"><span data-stu-id="f91f4-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f91f4-115">構成 (形式) のコントロールの CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="f91f4-115">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="f91f4-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f91f4-116">Optional element.</span></span><br /><br /> <span data-ttu-id="f91f4-117">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="f91f4-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="f91f4-118">構成 (形式) のコントロールの CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="f91f4-118">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="f91f4-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f91f4-119">Optional element.</span></span><br /><br /> <span data-ttu-id="f91f4-120">データを左または右にシフトなど、データを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="f91f4-120">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="f91f4-121">コントロールの構成 (形式) の CustomItem の改行要素</span><span class="sxs-lookup"><span data-stu-id="f91f4-121">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="f91f4-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f91f4-122">Optional element.</span></span><br /><br /> <span data-ttu-id="f91f4-123">コントロールの表示には、空白行を追加します。</span><span class="sxs-lookup"><span data-stu-id="f91f4-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="f91f4-124">CustomItem の構成 (形式) のコントロールのテキスト要素</span><span class="sxs-lookup"><span data-stu-id="f91f4-124">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="f91f4-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f91f4-125">Optional element.</span></span><br /><br /> <span data-ttu-id="f91f4-126">コントロールの表示には、かっこ、角かっこなどのテキストを追加します。</span><span class="sxs-lookup"><span data-stu-id="f91f4-126">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f91f4-127">親要素</span><span class="sxs-lookup"><span data-stu-id="f91f4-127">Parent Elements</span></span>

|<span data-ttu-id="f91f4-128">要素</span><span class="sxs-lookup"><span data-stu-id="f91f4-128">Element</span></span>|<span data-ttu-id="f91f4-129">説明</span><span class="sxs-lookup"><span data-stu-id="f91f4-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f91f4-130">構成 (形式) のコントロールのカスタム コントロールの CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="f91f4-130">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="f91f4-131">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="f91f4-131">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f91f4-132">コメント</span><span class="sxs-lookup"><span data-stu-id="f91f4-132">Remarks</span></span>

<span data-ttu-id="f91f4-133">子要素を指定するときに、`CustomItem`要素、次に留意します。</span><span class="sxs-lookup"><span data-stu-id="f91f4-133">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="f91f4-134">次の順序で子要素を追加する必要があります: `ExpressionBinding`、 `NewLine`、 `Text`、および`Frame`します。</span><span class="sxs-lookup"><span data-stu-id="f91f4-134">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="f91f4-135">指定できるシーケンスの数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="f91f4-135">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="f91f4-136">各シーケンスの数に上限はありません`ExpressionBinding`要素を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f91f4-136">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="f91f4-137">参照</span><span class="sxs-lookup"><span data-stu-id="f91f4-137">See Also</span></span>

[<span data-ttu-id="f91f4-138">構成 (形式) のコントロールの CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="f91f4-138">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="f91f4-139">構成 (形式) のコントロールの CustomItem フレーム要素</span><span class="sxs-lookup"><span data-stu-id="f91f4-139">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="f91f4-140">コントロールの構成 (形式) の CustomItem の改行要素</span><span class="sxs-lookup"><span data-stu-id="f91f4-140">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="f91f4-141">CustomItem の構成 (形式) のコントロールのテキスト要素</span><span class="sxs-lookup"><span data-stu-id="f91f4-141">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="f91f4-142">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="f91f4-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
