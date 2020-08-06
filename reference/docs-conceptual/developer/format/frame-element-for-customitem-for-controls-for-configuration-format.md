---
title: 構成用のコントロールの CustomItem の Frame 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: fa435b8d6b868d2d7c94b7926321d94edc2ec290
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781479"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="eb9b7-102">Configuration の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="eb9b7-102">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="eb9b7-103">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="eb9b7-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="eb9b7-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb9b7-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="eb9b7-105">Configuration 要素 (Format) コントロールの構成 (format) コントロールの要素の構成 (形式) の CustomControl 要素の構成のためのコントロールの構成 (書式) の CustomEntries 要素の構成のための CustomControl の構成 (書式) のカスタム Customentries 要素を構成するためのコントロールの configuration (形式) customentries 要素を構成するためのコントロールの構成 (形式)</span><span class="sxs-lookup"><span data-stu-id="eb9b7-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="eb9b7-106">構文</span><span class="sxs-lookup"><span data-stu-id="eb9b7-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="eb9b7-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="eb9b7-107">Attributes and Elements</span></span>

<span data-ttu-id="eb9b7-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `Frame` ます。</span><span class="sxs-lookup"><span data-stu-id="eb9b7-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="eb9b7-109">属性</span><span class="sxs-lookup"><span data-stu-id="eb9b7-109">Attributes</span></span>

<span data-ttu-id="eb9b7-110">なし。</span><span class="sxs-lookup"><span data-stu-id="eb9b7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="eb9b7-111">子要素</span><span class="sxs-lookup"><span data-stu-id="eb9b7-111">Child Elements</span></span>

|<span data-ttu-id="eb9b7-112">要素</span><span class="sxs-lookup"><span data-stu-id="eb9b7-112">Element</span></span>|<span data-ttu-id="eb9b7-113">説明</span><span class="sxs-lookup"><span data-stu-id="eb9b7-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="eb9b7-114">必須の要素</span><span class="sxs-lookup"><span data-stu-id="eb9b7-114">Required Element</span></span>|
|[<span data-ttu-id="eb9b7-115">Configuration の Controls の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="eb9b7-115">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="eb9b7-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="eb9b7-116">Optional element.</span></span><br /><br /> <span data-ttu-id="eb9b7-117">データの最初の行を左にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb9b7-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="eb9b7-118">Configuration の Controls の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="eb9b7-118">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="eb9b7-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="eb9b7-119">Optional element.</span></span><br /><br /> <span data-ttu-id="eb9b7-120">データの最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb9b7-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="eb9b7-121">Configuration の Controls の Frame の LeftIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="eb9b7-121">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="eb9b7-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="eb9b7-122">Optional element.</span></span><br /><br /> <span data-ttu-id="eb9b7-123">データを左余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb9b7-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="eb9b7-124">Configuration の Controls の Frame の RightIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="eb9b7-124">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="eb9b7-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="eb9b7-125">Optional element.</span></span><br /><br /> <span data-ttu-id="eb9b7-126">データを右余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb9b7-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="eb9b7-127">親要素</span><span class="sxs-lookup"><span data-stu-id="eb9b7-127">Parent Elements</span></span>

|<span data-ttu-id="eb9b7-128">要素</span><span class="sxs-lookup"><span data-stu-id="eb9b7-128">Element</span></span>|<span data-ttu-id="eb9b7-129">説明</span><span class="sxs-lookup"><span data-stu-id="eb9b7-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="eb9b7-130">構成のための CustomEntry コントロールの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="eb9b7-130">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="eb9b7-131">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="eb9b7-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="eb9b7-132">解説</span><span class="sxs-lookup"><span data-stu-id="eb9b7-132">Remarks</span></span>

<span data-ttu-id="eb9b7-133">同じ要素で[Firstlinehanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)と[firstlinehanging](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)要素を指定することはできません `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="eb9b7-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb9b7-134">参照</span><span class="sxs-lookup"><span data-stu-id="eb9b7-134">See Also</span></span>

[<span data-ttu-id="eb9b7-135">Configuration の Controls の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="eb9b7-135">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="eb9b7-136">Configuration の Controls の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="eb9b7-136">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="eb9b7-137">Configuration の Controls の Frame の LeftIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="eb9b7-137">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="eb9b7-138">Configuration の Controls の Frame の RightIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="eb9b7-138">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="eb9b7-139">構成のための CustomEntry コントロールの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="eb9b7-139">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="eb9b7-140">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="eb9b7-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
