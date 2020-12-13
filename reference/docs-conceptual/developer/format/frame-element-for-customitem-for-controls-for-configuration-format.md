---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration の Controls の CustomItem の Frame 要素 (書式)
description: Configuration の Controls の CustomItem の Frame 要素 (書式)
ms.openlocfilehash: 85d095b9b0c25b68b2353bce56b85333aff91b98
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652232"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="24a90-103">Configuration の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="24a90-103">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="24a90-104">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="24a90-104">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="24a90-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="24a90-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="24a90-106">Configuration 要素 (Format) コントロールの構成 (format) コントロールの要素の構成 (形式) の CustomControl 要素の構成のためのコントロールの構成 (書式) の CustomEntries 要素の構成のための CustomControl の構成 (書式) のカスタム Customentries 要素を構成するためのコントロールの configuration (形式) customentries 要素を構成するためのコントロールの構成 (形式)</span><span class="sxs-lookup"><span data-stu-id="24a90-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="24a90-107">構文</span><span class="sxs-lookup"><span data-stu-id="24a90-107">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="24a90-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="24a90-108">Attributes and Elements</span></span>

<span data-ttu-id="24a90-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `Frame` ます。</span><span class="sxs-lookup"><span data-stu-id="24a90-109">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="24a90-110">属性</span><span class="sxs-lookup"><span data-stu-id="24a90-110">Attributes</span></span>

<span data-ttu-id="24a90-111">なし。</span><span class="sxs-lookup"><span data-stu-id="24a90-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="24a90-112">子要素</span><span class="sxs-lookup"><span data-stu-id="24a90-112">Child Elements</span></span>

|<span data-ttu-id="24a90-113">要素</span><span class="sxs-lookup"><span data-stu-id="24a90-113">Element</span></span>|<span data-ttu-id="24a90-114">説明</span><span class="sxs-lookup"><span data-stu-id="24a90-114">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="24a90-115">必須の要素</span><span class="sxs-lookup"><span data-stu-id="24a90-115">Required Element</span></span>|
|[<span data-ttu-id="24a90-116">Configuration の Controls の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="24a90-116">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="24a90-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="24a90-117">Optional element.</span></span><br /><br /> <span data-ttu-id="24a90-118">データの最初の行を左にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="24a90-118">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="24a90-119">Configuration の Controls の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="24a90-119">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="24a90-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="24a90-120">Optional element.</span></span><br /><br /> <span data-ttu-id="24a90-121">データの最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="24a90-121">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="24a90-122">Configuration の Controls の Frame の LeftIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="24a90-122">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="24a90-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="24a90-123">Optional element.</span></span><br /><br /> <span data-ttu-id="24a90-124">データを左余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="24a90-124">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="24a90-125">Configuration の Controls の Frame の RightIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="24a90-125">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="24a90-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="24a90-126">Optional element.</span></span><br /><br /> <span data-ttu-id="24a90-127">データを右余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="24a90-127">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="24a90-128">親要素</span><span class="sxs-lookup"><span data-stu-id="24a90-128">Parent Elements</span></span>

|<span data-ttu-id="24a90-129">要素</span><span class="sxs-lookup"><span data-stu-id="24a90-129">Element</span></span>|<span data-ttu-id="24a90-130">説明</span><span class="sxs-lookup"><span data-stu-id="24a90-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="24a90-131">構成のための CustomEntry コントロールの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="24a90-131">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="24a90-132">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="24a90-132">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="24a90-133">解説</span><span class="sxs-lookup"><span data-stu-id="24a90-133">Remarks</span></span>

<span data-ttu-id="24a90-134">同じ要素で [Firstlinehanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) と [firstlinehanging](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) 要素を指定することはできません `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="24a90-134">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="24a90-135">参照</span><span class="sxs-lookup"><span data-stu-id="24a90-135">See Also</span></span>

[<span data-ttu-id="24a90-136">Configuration の Controls の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="24a90-136">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="24a90-137">Configuration の Controls の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="24a90-137">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="24a90-138">Configuration の Controls の Frame の LeftIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="24a90-138">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="24a90-139">Configuration の Controls の Frame の RightIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="24a90-139">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="24a90-140">構成のための CustomEntry コントロールの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="24a90-140">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="24a90-141">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="24a90-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
