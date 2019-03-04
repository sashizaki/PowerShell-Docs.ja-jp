---
title: CustomItem の構成 (形式) のコントロールの要素をフレーム |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d879c8ce-679d-4622-bc43-c207f6413871
caps.latest.revision: 9
ms.openlocfilehash: b11b154a94daccead57bdfb5e579e1de2c190c09
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862978"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="2d121-102">Configuration の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2d121-102">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="2d121-103">データを左または右にシフトなど、データを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="2d121-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="2d121-104">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d121-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="2d121-105">構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素構成 (形式) のコントロールの CustomItem 構成フレーム要素のコントロールの CustomEntry の構成 (形式) CustomItem 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="2d121-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2d121-106">構文</span><span class="sxs-lookup"><span data-stu-id="2d121-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2d121-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="2d121-107">Attributes and Elements</span></span>

<span data-ttu-id="2d121-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`Frame`要素。</span><span class="sxs-lookup"><span data-stu-id="2d121-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2d121-109">属性</span><span class="sxs-lookup"><span data-stu-id="2d121-109">Attributes</span></span>

<span data-ttu-id="2d121-110">なし。</span><span class="sxs-lookup"><span data-stu-id="2d121-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2d121-111">子要素</span><span class="sxs-lookup"><span data-stu-id="2d121-111">Child Elements</span></span>

|<span data-ttu-id="2d121-112">要素</span><span class="sxs-lookup"><span data-stu-id="2d121-112">Element</span></span>|<span data-ttu-id="2d121-113">説明</span><span class="sxs-lookup"><span data-stu-id="2d121-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="2d121-114">必要な要素</span><span class="sxs-lookup"><span data-stu-id="2d121-114">Required Element</span></span>|
|[<span data-ttu-id="2d121-115">コントロールの構成 (形式) のフレームの FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="2d121-115">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="2d121-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2d121-116">Optional element.</span></span><br /><br /> <span data-ttu-id="2d121-117">データの最初の行が左にシフト文字の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d121-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="2d121-118">コントロールの構成 (形式) のフレームの FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="2d121-118">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="2d121-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2d121-119">Optional element.</span></span><br /><br /> <span data-ttu-id="2d121-120">データの最初の行が右側にシフトした文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d121-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="2d121-121">コントロールの構成 (形式) のフレームの LeftIndent 要素</span><span class="sxs-lookup"><span data-stu-id="2d121-121">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="2d121-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2d121-122">Optional element.</span></span><br /><br /> <span data-ttu-id="2d121-123">左余白からデータを移動する文字の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d121-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="2d121-124">コントロールの構成 (形式) のフレームの RightIndent 要素</span><span class="sxs-lookup"><span data-stu-id="2d121-124">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="2d121-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2d121-125">Optional element.</span></span><br /><br /> <span data-ttu-id="2d121-126">右の余白からデータを移動する文字の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d121-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2d121-127">親要素</span><span class="sxs-lookup"><span data-stu-id="2d121-127">Parent Elements</span></span>

|<span data-ttu-id="2d121-128">要素</span><span class="sxs-lookup"><span data-stu-id="2d121-128">Element</span></span>|<span data-ttu-id="2d121-129">説明</span><span class="sxs-lookup"><span data-stu-id="2d121-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2d121-130">コントロールの構成の CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="2d121-130">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="2d121-131">どのようなデータが、コントロールによって表示され、表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="2d121-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2d121-132">コメント</span><span class="sxs-lookup"><span data-stu-id="2d121-132">Remarks</span></span>

<span data-ttu-id="2d121-133">指定することはできません、 [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)と[FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)要素で同じ`Frame`要素。</span><span class="sxs-lookup"><span data-stu-id="2d121-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d121-134">参照</span><span class="sxs-lookup"><span data-stu-id="2d121-134">See Also</span></span>

[<span data-ttu-id="2d121-135">コントロールの構成 (形式) のフレームの FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="2d121-135">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="2d121-136">コントロールの構成 (形式) のフレームの FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="2d121-136">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="2d121-137">コントロールの構成 (形式) のフレームの LeftIndent 要素</span><span class="sxs-lookup"><span data-stu-id="2d121-137">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="2d121-138">コントロールの構成 (形式) のフレームの RightIndent 要素</span><span class="sxs-lookup"><span data-stu-id="2d121-138">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="2d121-139">コントロールの構成の CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="2d121-139">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="2d121-140">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="2d121-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
