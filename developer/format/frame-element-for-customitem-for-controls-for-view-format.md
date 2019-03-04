---
title: CustomItem の表示 (形式) のコントロールの要素をフレーム |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5729091-78a9-4bc1-abac-210bc20c6dbe
caps.latest.revision: 7
ms.openlocfilehash: f93dc20a9c5f87c14605578062b1e60f5a3d25cf
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859818"
---
# <a name="frame-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="42bf7-102">View の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="42bf7-102">Frame Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="42bf7-103">データを左または右にシフトなど、データを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="42bf7-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="42bf7-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="42bf7-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="42bf7-105">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry CustomItem ビュー (形式) のコントロールのビュー (形式) フレーム要素のコントロールのビュー (形式) CustomItem 要素のコントロールのビュー (形式) CustomEntry 要素のカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="42bf7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="42bf7-106">構文</span><span class="sxs-lookup"><span data-stu-id="42bf7-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="42bf7-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="42bf7-107">Attributes and Elements</span></span>

<span data-ttu-id="42bf7-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`Frame`要素。</span><span class="sxs-lookup"><span data-stu-id="42bf7-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="42bf7-109">属性</span><span class="sxs-lookup"><span data-stu-id="42bf7-109">Attributes</span></span>

<span data-ttu-id="42bf7-110">なし。</span><span class="sxs-lookup"><span data-stu-id="42bf7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="42bf7-111">子要素</span><span class="sxs-lookup"><span data-stu-id="42bf7-111">Child Elements</span></span>

|<span data-ttu-id="42bf7-112">要素</span><span class="sxs-lookup"><span data-stu-id="42bf7-112">Element</span></span>|<span data-ttu-id="42bf7-113">説明</span><span class="sxs-lookup"><span data-stu-id="42bf7-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="42bf7-114">必要な要素</span><span class="sxs-lookup"><span data-stu-id="42bf7-114">Required Element</span></span>|
|[<span data-ttu-id="42bf7-115">ビュー (形式) のコントロールのフレームの FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="42bf7-115">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="42bf7-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="42bf7-116">Optional element.</span></span><br /><br /> <span data-ttu-id="42bf7-117">最初の行が左にシフト文字の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="42bf7-117">Specifies how many characters the first line is shifted to the left.</span></span>|
|[<span data-ttu-id="42bf7-118">ビュー (形式) のコントロールのフレームの FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="42bf7-118">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="42bf7-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="42bf7-119">Optional element.</span></span><br /><br /> <span data-ttu-id="42bf7-120">最初の行が右側にシフト文字の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="42bf7-120">Specifies how many characters the first line is shifted to the right.</span></span>|
|[<span data-ttu-id="42bf7-121">ビュー (形式) のコントロールのフレームの LeftIndent 要素</span><span class="sxs-lookup"><span data-stu-id="42bf7-121">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="42bf7-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="42bf7-122">Optional element.</span></span><br /><br /> <span data-ttu-id="42bf7-123">左余白からデータを移動する文字の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="42bf7-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="42bf7-124">ビュー (形式) のコントロールのフレームの RightIndent 要素</span><span class="sxs-lookup"><span data-stu-id="42bf7-124">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="42bf7-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="42bf7-125">Optional element.</span></span><br /><br /> <span data-ttu-id="42bf7-126">右の余白からデータを移動する文字の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="42bf7-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="42bf7-127">親要素</span><span class="sxs-lookup"><span data-stu-id="42bf7-127">Parent Elements</span></span>

|<span data-ttu-id="42bf7-128">要素</span><span class="sxs-lookup"><span data-stu-id="42bf7-128">Element</span></span>|<span data-ttu-id="42bf7-129">説明</span><span class="sxs-lookup"><span data-stu-id="42bf7-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="42bf7-130">コントロールが表示されます (形式) の CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="42bf7-130">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="42bf7-131">どのようなデータが、コントロールによって表示され、表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="42bf7-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="42bf7-132">コメント</span><span class="sxs-lookup"><span data-stu-id="42bf7-132">Remarks</span></span>

<span data-ttu-id="42bf7-133">指定することはできません、 [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)と[FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md)要素で同じ`Frame`要素。</span><span class="sxs-lookup"><span data-stu-id="42bf7-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="42bf7-134">参照</span><span class="sxs-lookup"><span data-stu-id="42bf7-134">See Also</span></span>

[<span data-ttu-id="42bf7-135">ビュー (形式) のコントロールのフレームの FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="42bf7-135">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="42bf7-136">ビュー (形式) のコントロールのフレームの FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="42bf7-136">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="42bf7-137">ビュー (形式) のコントロールのフレームの LeftIndent 要素</span><span class="sxs-lookup"><span data-stu-id="42bf7-137">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="42bf7-138">ビュー (形式) のコントロールのフレームの RightIndent 要素</span><span class="sxs-lookup"><span data-stu-id="42bf7-138">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="42bf7-139">コントロールが表示されます (形式) の CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="42bf7-139">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="42bf7-140">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="42bf7-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
