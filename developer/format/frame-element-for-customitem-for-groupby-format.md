---
title: CustomItem の GroupBy (形式) の要素をフレーム |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab2a5379-299d-4c97-86a2-b639ea890fae
caps.latest.revision: 6
ms.openlocfilehash: 7f9066c0fe0954fadff9dc8f0c35a62c6710f516
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065599"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a><span data-ttu-id="1a20c-102">GroupBy の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1a20c-102">Frame Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="1a20c-103">データを左または右にシフトなど、データを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="1a20c-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="1a20c-104">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a20c-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="1a20c-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) の CustomItem の GroupBy (形式) フレーム要素 CustomEntry の GroupBy (形式) CustomItem 要素にカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="1a20c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1a20c-106">構文</span><span class="sxs-lookup"><span data-stu-id="1a20c-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1a20c-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1a20c-107">Attributes and Elements</span></span>

<span data-ttu-id="1a20c-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`Frame`要素。</span><span class="sxs-lookup"><span data-stu-id="1a20c-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1a20c-109">属性</span><span class="sxs-lookup"><span data-stu-id="1a20c-109">Attributes</span></span>

<span data-ttu-id="1a20c-110">なし。</span><span class="sxs-lookup"><span data-stu-id="1a20c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1a20c-111">子要素</span><span class="sxs-lookup"><span data-stu-id="1a20c-111">Child Elements</span></span>

|<span data-ttu-id="1a20c-112">要素</span><span class="sxs-lookup"><span data-stu-id="1a20c-112">Element</span></span>|<span data-ttu-id="1a20c-113">説明</span><span class="sxs-lookup"><span data-stu-id="1a20c-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="1a20c-114">必要な要素</span><span class="sxs-lookup"><span data-stu-id="1a20c-114">Required Element</span></span>|
|[<span data-ttu-id="1a20c-115">GroupBy (形式) のフレームの FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="1a20c-115">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)|<span data-ttu-id="1a20c-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="1a20c-116">Optional element.</span></span><br /><br /> <span data-ttu-id="1a20c-117">データの最初の行が左にシフト文字の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a20c-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="1a20c-118">GroupBy (形式) のフレームの FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="1a20c-118">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="1a20c-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="1a20c-119">Optional element.</span></span><br /><br /> <span data-ttu-id="1a20c-120">データの最初の行が右側にシフトした文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a20c-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="1a20c-121">GroupBy (形式) のフレームの LeftIndent 要素</span><span class="sxs-lookup"><span data-stu-id="1a20c-121">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="1a20c-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="1a20c-122">Optional element.</span></span><br /><br /> <span data-ttu-id="1a20c-123">左余白からデータを移動する文字の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a20c-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|<span data-ttu-id="1a20c-124">[GroupBy (形式) のフレームの RightIndent 要素](./rightindent-element-for-frame-for-groupby-format.md)RightIndent 要素</span><span class="sxs-lookup"><span data-stu-id="1a20c-124">[RightIndent Element for Frame for GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent Element</span></span>|<span data-ttu-id="1a20c-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="1a20c-125">Optional element.</span></span><br /><br /> <span data-ttu-id="1a20c-126">右の余白からデータを移動する文字の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a20c-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1a20c-127">親要素</span><span class="sxs-lookup"><span data-stu-id="1a20c-127">Parent Elements</span></span>

|<span data-ttu-id="1a20c-128">要素</span><span class="sxs-lookup"><span data-stu-id="1a20c-128">Element</span></span>|<span data-ttu-id="1a20c-129">説明</span><span class="sxs-lookup"><span data-stu-id="1a20c-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1a20c-130">GroupBy (形式) の CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="1a20c-130">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="1a20c-131">どのようなデータが、コントロールによって表示され、表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="1a20c-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1a20c-132">コメント</span><span class="sxs-lookup"><span data-stu-id="1a20c-132">Remarks</span></span>

<span data-ttu-id="1a20c-133">指定することはできません、 [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md)と[FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md)要素で同じ`Frame`要素。</span><span class="sxs-lookup"><span data-stu-id="1a20c-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a20c-134">参照</span><span class="sxs-lookup"><span data-stu-id="1a20c-134">See Also</span></span>

[<span data-ttu-id="1a20c-135">GroupBy (形式) のフレームの FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="1a20c-135">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="1a20c-136">GroupBy (形式) のフレームの FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="1a20c-136">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="1a20c-137">GroupBy (形式) のフレームの LeftIndent 要素</span><span class="sxs-lookup"><span data-stu-id="1a20c-137">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="1a20c-138">GroupBy (形式) のフレームの RightIndent 要素</span><span class="sxs-lookup"><span data-stu-id="1a20c-138">RightIndent Element for Frame for GroupBy (Format)</span></span>](./rightindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="1a20c-139">GroupBy (形式) の CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="1a20c-139">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="1a20c-140">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="1a20c-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
