---
title: GroupBy (Format) の CustomItem の Frame 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab2a5379-299d-4c97-86a2-b639ea890fae
caps.latest.revision: 6
ms.openlocfilehash: 7f9066c0fe0954fadff9dc8f0c35a62c6710f516
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362951"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a><span data-ttu-id="da29e-102">GroupBy の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="da29e-102">Frame Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="da29e-103">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="da29e-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="da29e-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="da29e-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="da29e-105">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素Groupby (形式) の CustomItem の groupby (format) Frame 要素の CustomControl for groupby (format) の CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="da29e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="da29e-106">構文</span><span class="sxs-lookup"><span data-stu-id="da29e-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="da29e-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="da29e-107">Attributes and Elements</span></span>

<span data-ttu-id="da29e-108">次のセクションでは、属性、子要素、`Frame` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="da29e-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="da29e-109">属性</span><span class="sxs-lookup"><span data-stu-id="da29e-109">Attributes</span></span>

<span data-ttu-id="da29e-110">なし。</span><span class="sxs-lookup"><span data-stu-id="da29e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="da29e-111">子要素</span><span class="sxs-lookup"><span data-stu-id="da29e-111">Child Elements</span></span>

|<span data-ttu-id="da29e-112">要素</span><span class="sxs-lookup"><span data-stu-id="da29e-112">Element</span></span>|<span data-ttu-id="da29e-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="da29e-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="da29e-114">必須の要素</span><span class="sxs-lookup"><span data-stu-id="da29e-114">Required Element</span></span>|
|[<span data-ttu-id="da29e-115">GroupBy (Format) の Frame の FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="da29e-115">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)|<span data-ttu-id="da29e-116">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="da29e-116">Optional element.</span></span><br /><br /> <span data-ttu-id="da29e-117">データの最初の行を左にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="da29e-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="da29e-118">GroupBy (Format) の Frame の FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="da29e-118">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="da29e-119">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="da29e-119">Optional element.</span></span><br /><br /> <span data-ttu-id="da29e-120">データの最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="da29e-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="da29e-121">GroupBy (Format) の Frame の左インデント要素</span><span class="sxs-lookup"><span data-stu-id="da29e-121">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="da29e-122">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="da29e-122">Optional element.</span></span><br /><br /> <span data-ttu-id="da29e-123">データを左余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="da29e-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|<span data-ttu-id="da29e-124">[GroupBy (Format) の Frame の右インデント要素](./rightindent-element-for-frame-for-groupby-format.md)右インデント要素</span><span class="sxs-lookup"><span data-stu-id="da29e-124">[RightIndent Element for Frame for GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent Element</span></span>|<span data-ttu-id="da29e-125">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="da29e-125">Optional element.</span></span><br /><br /> <span data-ttu-id="da29e-126">データを右余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="da29e-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="da29e-127">親要素</span><span class="sxs-lookup"><span data-stu-id="da29e-127">Parent Elements</span></span>

|<span data-ttu-id="da29e-128">要素</span><span class="sxs-lookup"><span data-stu-id="da29e-128">Element</span></span>|<span data-ttu-id="da29e-129">[説明]</span><span class="sxs-lookup"><span data-stu-id="da29e-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="da29e-130">GroupBy の CustomEntry の CustomItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="da29e-130">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="da29e-131">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="da29e-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="da29e-132">コメント</span><span class="sxs-lookup"><span data-stu-id="da29e-132">Remarks</span></span>

<span data-ttu-id="da29e-133">[Firstlinehanging](./firstlinehanging-element-for-frame-for-groupby-format.md)と[firstlinehanging](./firstlineindent-element-for-frame-for-groupby-format.md)要素を同じ `Frame` 要素で指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="da29e-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="da29e-134">参照</span><span class="sxs-lookup"><span data-stu-id="da29e-134">See Also</span></span>

[<span data-ttu-id="da29e-135">GroupBy (Format) の Frame の FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="da29e-135">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="da29e-136">GroupBy (Format) の Frame の FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="da29e-136">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="da29e-137">GroupBy (Format) の Frame の左インデント要素</span><span class="sxs-lookup"><span data-stu-id="da29e-137">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="da29e-138">GroupBy (Format) の Frame の右インデント要素</span><span class="sxs-lookup"><span data-stu-id="da29e-138">RightIndent Element for Frame for GroupBy (Format)</span></span>](./rightindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="da29e-139">GroupBy の CustomEntry の CustomItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="da29e-139">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="da29e-140">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="da29e-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
