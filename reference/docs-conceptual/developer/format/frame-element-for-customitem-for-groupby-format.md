---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の CustomItem の Frame 要素 (書式)
description: GroupBy の CustomItem の Frame 要素 (書式)
ms.openlocfilehash: 86b51766974ebfcae06583ade237a77c6db92866
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652168"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a><span data-ttu-id="04ba5-103">GroupBy の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="04ba5-103">Frame Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="04ba5-104">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="04ba5-104">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="04ba5-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="04ba5-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="04ba5-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素については、groupby (format) の CustomControl 要素に対して、groupby (形式) の CustomEntries 要素を指定します。 groupby (書式) の customentries 要素については、groupby (format) の Customentries の groupby (format) フレーム要素の CustomControl</span><span class="sxs-lookup"><span data-stu-id="04ba5-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="04ba5-107">構文</span><span class="sxs-lookup"><span data-stu-id="04ba5-107">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="04ba5-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="04ba5-108">Attributes and Elements</span></span>

<span data-ttu-id="04ba5-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `Frame` ます。</span><span class="sxs-lookup"><span data-stu-id="04ba5-109">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="04ba5-110">属性</span><span class="sxs-lookup"><span data-stu-id="04ba5-110">Attributes</span></span>

<span data-ttu-id="04ba5-111">なし。</span><span class="sxs-lookup"><span data-stu-id="04ba5-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="04ba5-112">子要素</span><span class="sxs-lookup"><span data-stu-id="04ba5-112">Child Elements</span></span>

|<span data-ttu-id="04ba5-113">要素</span><span class="sxs-lookup"><span data-stu-id="04ba5-113">Element</span></span>|<span data-ttu-id="04ba5-114">説明</span><span class="sxs-lookup"><span data-stu-id="04ba5-114">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="04ba5-115">必須の要素</span><span class="sxs-lookup"><span data-stu-id="04ba5-115">Required Element</span></span>|
|[<span data-ttu-id="04ba5-116">GroupBy の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="04ba5-116">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)|<span data-ttu-id="04ba5-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="04ba5-117">Optional element.</span></span><br /><br /> <span data-ttu-id="04ba5-118">データの最初の行を左にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="04ba5-118">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="04ba5-119">GroupBy の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="04ba5-119">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="04ba5-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="04ba5-120">Optional element.</span></span><br /><br /> <span data-ttu-id="04ba5-121">データの最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="04ba5-121">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="04ba5-122">GroupBy の Frame の LeftIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="04ba5-122">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="04ba5-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="04ba5-123">Optional element.</span></span><br /><br /> <span data-ttu-id="04ba5-124">データを左余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="04ba5-124">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|<span data-ttu-id="04ba5-125">[GroupBy (Format) の Frame の右インデント要素](./rightindent-element-for-frame-for-groupby-format.md)右インデント要素</span><span class="sxs-lookup"><span data-stu-id="04ba5-125">[RightIndent Element for Frame for GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent Element</span></span>|<span data-ttu-id="04ba5-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="04ba5-126">Optional element.</span></span><br /><br /> <span data-ttu-id="04ba5-127">データを右余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="04ba5-127">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="04ba5-128">親要素</span><span class="sxs-lookup"><span data-stu-id="04ba5-128">Parent Elements</span></span>

|<span data-ttu-id="04ba5-129">要素</span><span class="sxs-lookup"><span data-stu-id="04ba5-129">Element</span></span>|<span data-ttu-id="04ba5-130">説明</span><span class="sxs-lookup"><span data-stu-id="04ba5-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="04ba5-131">GroupBy の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="04ba5-131">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="04ba5-132">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="04ba5-132">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="04ba5-133">解説</span><span class="sxs-lookup"><span data-stu-id="04ba5-133">Remarks</span></span>

<span data-ttu-id="04ba5-134">同じ要素で [Firstlinehanging](./firstlinehanging-element-for-frame-for-groupby-format.md) と [firstlinehanging](./firstlineindent-element-for-frame-for-groupby-format.md) 要素を指定することはできません `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="04ba5-134">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="04ba5-135">参照</span><span class="sxs-lookup"><span data-stu-id="04ba5-135">See Also</span></span>

[<span data-ttu-id="04ba5-136">GroupBy の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="04ba5-136">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="04ba5-137">GroupBy の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="04ba5-137">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="04ba5-138">GroupBy の Frame の LeftIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="04ba5-138">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="04ba5-139">GroupBy の Frame の RightIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="04ba5-139">RightIndent Element for Frame for GroupBy (Format)</span></span>](./rightindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="04ba5-140">GroupBy の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="04ba5-140">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="04ba5-141">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="04ba5-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
