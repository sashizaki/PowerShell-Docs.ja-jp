---
ms.date: 09/13/2016
ms.topic: reference
title: View の Controls の CustomItem の Frame 要素 (書式)
description: View の Controls の CustomItem の Frame 要素 (書式)
ms.openlocfilehash: 6f26e19a6894ac213b924108a56cb80f9ffd1143
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652213"
---
# <a name="frame-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="7bf3d-103">View の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7bf3d-103">Frame Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="7bf3d-104">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="7bf3d-104">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="7bf3d-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7bf3d-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="7bf3d-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (形式) コントロールのコントロール要素を表示するためのコントロールの CustomControl 要素 (format) CustomControl のビュー (書式) の CustomEntries 要素 for view (format) CustomEntry 要素を使用して、コントロールのカスタム項目のビュー (形式) の Customentries 要素を表示するためのコントロールの Customentries の Frame 要素を表示するためのコントロール (形式)</span><span class="sxs-lookup"><span data-stu-id="7bf3d-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7bf3d-107">構文</span><span class="sxs-lookup"><span data-stu-id="7bf3d-107">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7bf3d-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7bf3d-108">Attributes and Elements</span></span>

<span data-ttu-id="7bf3d-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `Frame` ます。</span><span class="sxs-lookup"><span data-stu-id="7bf3d-109">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7bf3d-110">属性</span><span class="sxs-lookup"><span data-stu-id="7bf3d-110">Attributes</span></span>

<span data-ttu-id="7bf3d-111">なし。</span><span class="sxs-lookup"><span data-stu-id="7bf3d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7bf3d-112">子要素</span><span class="sxs-lookup"><span data-stu-id="7bf3d-112">Child Elements</span></span>

|<span data-ttu-id="7bf3d-113">要素</span><span class="sxs-lookup"><span data-stu-id="7bf3d-113">Element</span></span>|<span data-ttu-id="7bf3d-114">説明</span><span class="sxs-lookup"><span data-stu-id="7bf3d-114">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="7bf3d-115">必須の要素</span><span class="sxs-lookup"><span data-stu-id="7bf3d-115">Required Element</span></span>|
|[<span data-ttu-id="7bf3d-116">ビューのコントロールのフレームの FirstLineHanging 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7bf3d-116">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="7bf3d-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="7bf3d-117">Optional element.</span></span><br /><br /> <span data-ttu-id="7bf3d-118">最初の行を左にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7bf3d-118">Specifies how many characters the first line is shifted to the left.</span></span>|
|[<span data-ttu-id="7bf3d-119">ビューのコントロールのフレームの FirstLineIndent 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="7bf3d-119">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="7bf3d-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="7bf3d-120">Optional element.</span></span><br /><br /> <span data-ttu-id="7bf3d-121">最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7bf3d-121">Specifies how many characters the first line is shifted to the right.</span></span>|
|[<span data-ttu-id="7bf3d-122">ビューのコントロールのフレームの左インデント要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7bf3d-122">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="7bf3d-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="7bf3d-123">Optional element.</span></span><br /><br /> <span data-ttu-id="7bf3d-124">データを左余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7bf3d-124">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="7bf3d-125">ビューのコントロールのフレームの右インデント要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7bf3d-125">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="7bf3d-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="7bf3d-126">Optional element.</span></span><br /><br /> <span data-ttu-id="7bf3d-127">データを右余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7bf3d-127">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7bf3d-128">親要素</span><span class="sxs-lookup"><span data-stu-id="7bf3d-128">Parent Elements</span></span>

|<span data-ttu-id="7bf3d-129">要素</span><span class="sxs-lookup"><span data-stu-id="7bf3d-129">Element</span></span>|<span data-ttu-id="7bf3d-130">説明</span><span class="sxs-lookup"><span data-stu-id="7bf3d-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7bf3d-131">View の Controls の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7bf3d-131">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="7bf3d-132">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="7bf3d-132">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7bf3d-133">解説</span><span class="sxs-lookup"><span data-stu-id="7bf3d-133">Remarks</span></span>

<span data-ttu-id="7bf3d-134">同じ要素で [Firstlinehanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) と [firstlinehanging](./firstlineindent-element-for-frame-for-controls-for-view-format.md) 要素を指定することはできません `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="7bf3d-134">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="7bf3d-135">参照</span><span class="sxs-lookup"><span data-stu-id="7bf3d-135">See Also</span></span>

[<span data-ttu-id="7bf3d-136">ビューのコントロールのフレームの FirstLineHanging 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7bf3d-136">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="7bf3d-137">ビューのコントロールのフレームの FirstLineIndent 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="7bf3d-137">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="7bf3d-138">ビューのコントロールのフレームの左インデント要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7bf3d-138">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="7bf3d-139">ビューのコントロールのフレームの右インデント要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7bf3d-139">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="7bf3d-140">View の Controls の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7bf3d-140">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="7bf3d-141">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="7bf3d-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
