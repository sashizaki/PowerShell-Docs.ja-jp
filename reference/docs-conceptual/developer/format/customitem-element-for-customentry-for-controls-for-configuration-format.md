---
title: CustomEntry for Controls for Controls の CustomItem 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73fb11ee-0ebd-477a-ac36-acdfbb32e70d
caps.latest.revision: 7
ms.openlocfilehash: bd0cb69770817ec215ddb1862a43a838baddefcf
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364031"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="93294-102">Configuration の Controls の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="93294-102">CustomItem Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="93294-103">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="93294-103">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="93294-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="93294-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="93294-105">Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素形式) CustomControl の CustomEntry 要素を構成するための管理用の Configuration (形式) CustomItem 要素を構成するためのコントロール用に設定します。</span><span class="sxs-lookup"><span data-stu-id="93294-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration</span></span>

## <a name="syntax"></a><span data-ttu-id="93294-106">構文</span><span class="sxs-lookup"><span data-stu-id="93294-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="93294-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="93294-107">Attributes and Elements</span></span>

<span data-ttu-id="93294-108">次のセクションでは、属性、子要素、`CustomItem` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="93294-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="93294-109">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93294-109">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="93294-110">属性</span><span class="sxs-lookup"><span data-stu-id="93294-110">Attributes</span></span>

<span data-ttu-id="93294-111">なし。</span><span class="sxs-lookup"><span data-stu-id="93294-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="93294-112">子要素</span><span class="sxs-lookup"><span data-stu-id="93294-112">Child Elements</span></span>

|<span data-ttu-id="93294-113">要素</span><span class="sxs-lookup"><span data-stu-id="93294-113">Element</span></span>|<span data-ttu-id="93294-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="93294-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="93294-115">構成用のコントロールに対する CustomItem の式のバインド要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="93294-115">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="93294-116">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="93294-116">Optional element.</span></span><br /><br /> <span data-ttu-id="93294-117">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="93294-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="93294-118">構成用のコントロールの CustomItem の Frame 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="93294-118">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="93294-119">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="93294-119">Optional element.</span></span><br /><br /> <span data-ttu-id="93294-120">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="93294-120">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="93294-121">構成用のコントロールの CustomItem の改行要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="93294-121">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="93294-122">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="93294-122">Optional element.</span></span><br /><br /> <span data-ttu-id="93294-123">コントロールの表示に空白行を追加します。</span><span class="sxs-lookup"><span data-stu-id="93294-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="93294-124">構成用のコントロールの CustomItem のテキスト要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="93294-124">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="93294-125">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="93294-125">Optional element.</span></span><br /><br /> <span data-ttu-id="93294-126">かっこや角かっこなどのテキストをコントロールの表示に追加します。</span><span class="sxs-lookup"><span data-stu-id="93294-126">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="93294-127">親要素</span><span class="sxs-lookup"><span data-stu-id="93294-127">Parent Elements</span></span>

|<span data-ttu-id="93294-128">要素</span><span class="sxs-lookup"><span data-stu-id="93294-128">Element</span></span>|<span data-ttu-id="93294-129">[説明]</span><span class="sxs-lookup"><span data-stu-id="93294-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="93294-130">CustomControl の CustomEntry 要素 (構成用コントロール用) (形式)</span><span class="sxs-lookup"><span data-stu-id="93294-130">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="93294-131">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="93294-131">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="93294-132">コメント</span><span class="sxs-lookup"><span data-stu-id="93294-132">Remarks</span></span>

<span data-ttu-id="93294-133">@No__t-0 要素の子要素を指定する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="93294-133">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="93294-134">子要素は、`ExpressionBinding`、`NewLine`、`Text`、`Frame` の順に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93294-134">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="93294-135">指定できるシーケンスの数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="93294-135">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="93294-136">各シーケンスでは、使用できる @no__t 0 要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="93294-136">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="93294-137">参照</span><span class="sxs-lookup"><span data-stu-id="93294-137">See Also</span></span>

[<span data-ttu-id="93294-138">構成用のコントロールに対する CustomItem の式のバインド要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="93294-138">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="93294-139">構成用のコントロールの CustomItem の Frame 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="93294-139">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="93294-140">構成用のコントロールの CustomItem の改行要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="93294-140">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="93294-141">構成用のコントロールの CustomItem のテキスト要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="93294-141">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="93294-142">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="93294-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
