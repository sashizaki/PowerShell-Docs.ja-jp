---
title: ビュー用のコントロールの CustomItem の Frame 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5729091-78a9-4bc1-abac-210bc20c6dbe
caps.latest.revision: 7
ms.openlocfilehash: f93dc20a9c5f87c14605578062b1e60f5a3d25cf
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363651"
---
# <a name="frame-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="8d4ea-102">View の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8d4ea-102">Frame Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="8d4ea-103">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="8d4ea-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="8d4ea-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d4ea-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="8d4ea-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素CustomControl for view (format) CustomEntry 要素は、ビュー (Format) のコントロールに対して Customentries のビュー (format) フレーム要素のビュー (書式) の Customentries 要素のコントロールの CustomEntries 要素を表示します。</span><span class="sxs-lookup"><span data-stu-id="8d4ea-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8d4ea-106">構文</span><span class="sxs-lookup"><span data-stu-id="8d4ea-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8d4ea-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="8d4ea-107">Attributes and Elements</span></span>

<span data-ttu-id="8d4ea-108">次のセクションでは、`Frame` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d4ea-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8d4ea-109">属性</span><span class="sxs-lookup"><span data-stu-id="8d4ea-109">Attributes</span></span>

<span data-ttu-id="8d4ea-110">なし。</span><span class="sxs-lookup"><span data-stu-id="8d4ea-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8d4ea-111">子要素</span><span class="sxs-lookup"><span data-stu-id="8d4ea-111">Child Elements</span></span>

|<span data-ttu-id="8d4ea-112">要素</span><span class="sxs-lookup"><span data-stu-id="8d4ea-112">Element</span></span>|<span data-ttu-id="8d4ea-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="8d4ea-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="8d4ea-114">必須の要素</span><span class="sxs-lookup"><span data-stu-id="8d4ea-114">Required Element</span></span>|
|[<span data-ttu-id="8d4ea-115">ビューのコントロールのフレームの FirstLineHanging 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="8d4ea-115">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="8d4ea-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="8d4ea-116">Optional element.</span></span><br /><br /> <span data-ttu-id="8d4ea-117">最初の行を左にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d4ea-117">Specifies how many characters the first line is shifted to the left.</span></span>|
|[<span data-ttu-id="8d4ea-118">ビューのコントロールのフレームの FirstLineIndent 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="8d4ea-118">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="8d4ea-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="8d4ea-119">Optional element.</span></span><br /><br /> <span data-ttu-id="8d4ea-120">最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d4ea-120">Specifies how many characters the first line is shifted to the right.</span></span>|
|[<span data-ttu-id="8d4ea-121">ビューのコントロールのフレームの左インデント要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8d4ea-121">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="8d4ea-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="8d4ea-122">Optional element.</span></span><br /><br /> <span data-ttu-id="8d4ea-123">データを左余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d4ea-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="8d4ea-124">ビューのコントロールのフレームの右インデント要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8d4ea-124">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="8d4ea-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="8d4ea-125">Optional element.</span></span><br /><br /> <span data-ttu-id="8d4ea-126">データを右余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d4ea-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8d4ea-127">親要素</span><span class="sxs-lookup"><span data-stu-id="8d4ea-127">Parent Elements</span></span>

|<span data-ttu-id="8d4ea-128">要素</span><span class="sxs-lookup"><span data-stu-id="8d4ea-128">Element</span></span>|<span data-ttu-id="8d4ea-129">[説明]</span><span class="sxs-lookup"><span data-stu-id="8d4ea-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8d4ea-130">ビュー用のコントロール用の Custommentry の CustomItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="8d4ea-130">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="8d4ea-131">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="8d4ea-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8d4ea-132">コメント</span><span class="sxs-lookup"><span data-stu-id="8d4ea-132">Remarks</span></span>

<span data-ttu-id="8d4ea-133">同じ `Frame` 要素で[Firstlinehanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)と[firstlinehanging](./firstlineindent-element-for-frame-for-controls-for-view-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="8d4ea-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d4ea-134">参照</span><span class="sxs-lookup"><span data-stu-id="8d4ea-134">See Also</span></span>

[<span data-ttu-id="8d4ea-135">ビューのコントロールのフレームの FirstLineHanging 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="8d4ea-135">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="8d4ea-136">ビューのコントロールのフレームの FirstLineIndent 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="8d4ea-136">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="8d4ea-137">ビューのコントロールのフレームの左インデント要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8d4ea-137">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="8d4ea-138">ビューのコントロールのフレームの右インデント要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8d4ea-138">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="8d4ea-139">ビュー用のコントロール用の Custommentry の CustomItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="8d4ea-139">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="8d4ea-140">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="8d4ea-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
