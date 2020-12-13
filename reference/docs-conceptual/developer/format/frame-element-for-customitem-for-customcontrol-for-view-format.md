---
ms.date: 09/13/2016
ms.topic: reference
title: View の CustomControl の CustomItem の Frame 要素 (書式)
description: View の CustomControl の CustomItem の Frame 要素 (書式)
ms.openlocfilehash: 1ffe071bb6c4f590e4c79803a3faff2108c7b636
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652195"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="08681-103">View の CustomControl の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="08681-103">Frame Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="08681-104">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="08681-104">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="08681-105">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="08681-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="08681-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) CustomControl 要素 (形式) CustomControl for view (format) の customentries 要素を表示するための CustomEntries for CustomControl for CustomControlView (Format) Frame Element for for View (Format) の Customentries 要素</span><span class="sxs-lookup"><span data-stu-id="08681-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="08681-107">構文</span><span class="sxs-lookup"><span data-stu-id="08681-107">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="08681-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="08681-108">Attributes and Elements</span></span>

<span data-ttu-id="08681-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `Frame` ます。</span><span class="sxs-lookup"><span data-stu-id="08681-109">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="08681-110">属性</span><span class="sxs-lookup"><span data-stu-id="08681-110">Attributes</span></span>

<span data-ttu-id="08681-111">なし。</span><span class="sxs-lookup"><span data-stu-id="08681-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="08681-112">子要素</span><span class="sxs-lookup"><span data-stu-id="08681-112">Child Elements</span></span>

|<span data-ttu-id="08681-113">要素</span><span class="sxs-lookup"><span data-stu-id="08681-113">Element</span></span>|<span data-ttu-id="08681-114">説明</span><span class="sxs-lookup"><span data-stu-id="08681-114">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="08681-115">必須の要素</span><span class="sxs-lookup"><span data-stu-id="08681-115">Required Element</span></span>|
|[<span data-ttu-id="08681-116">FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="08681-116">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="08681-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="08681-117">Optional element.</span></span><br /><br /> <span data-ttu-id="08681-118">データの最初の行を左にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="08681-118">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="08681-119">FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="08681-119">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="08681-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="08681-120">Optional element.</span></span><br /><br /> <span data-ttu-id="08681-121">データの最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="08681-121">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="08681-122">左インデント要素</span><span class="sxs-lookup"><span data-stu-id="08681-122">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="08681-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="08681-123">Optional element.</span></span><br /><br /> <span data-ttu-id="08681-124">データを左余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="08681-124">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="08681-125">右インデント要素</span><span class="sxs-lookup"><span data-stu-id="08681-125">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="08681-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="08681-126">Optional element.</span></span><br /><br /> <span data-ttu-id="08681-127">データを右余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="08681-127">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="08681-128">親要素</span><span class="sxs-lookup"><span data-stu-id="08681-128">Parent Elements</span></span>

|<span data-ttu-id="08681-129">要素</span><span class="sxs-lookup"><span data-stu-id="08681-129">Element</span></span>|<span data-ttu-id="08681-130">説明</span><span class="sxs-lookup"><span data-stu-id="08681-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="08681-131">CustomEntry for ビューの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="08681-131">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="08681-132">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="08681-132">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="08681-133">解説</span><span class="sxs-lookup"><span data-stu-id="08681-133">Remarks</span></span>

<span data-ttu-id="08681-134">同じ要素で [Firstlinehanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) と [firstlinehanging](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) 要素を指定することはできません `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="08681-134">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="08681-135">参照</span><span class="sxs-lookup"><span data-stu-id="08681-135">See Also</span></span>

[<span data-ttu-id="08681-136">FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="08681-136">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="08681-137">FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="08681-137">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="08681-138">左インデント要素</span><span class="sxs-lookup"><span data-stu-id="08681-138">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="08681-139">右インデント要素</span><span class="sxs-lookup"><span data-stu-id="08681-139">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="08681-140">CustomEntry for ビューの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="08681-140">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="08681-141">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="08681-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
