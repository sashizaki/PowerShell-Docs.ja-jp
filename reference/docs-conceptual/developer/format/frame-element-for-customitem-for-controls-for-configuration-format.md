---
title: 構成用のコントロールの CustomItem の Frame 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d879c8ce-679d-4622-bc43-c207f6413871
caps.latest.revision: 9
ms.openlocfilehash: b11b154a94daccead57bdfb5e579e1de2c190c09
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363661"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="bf9ba-102">Configuration の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bf9ba-102">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="bf9ba-103">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="bf9ba-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="bf9ba-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf9ba-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="bf9ba-105">Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素形式) CustomControl のための CustomEntry 要素を構成するためのコントロールのための CustomEntry 要素を構成するためのコントロールの CustomItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bf9ba-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bf9ba-106">構文</span><span class="sxs-lookup"><span data-stu-id="bf9ba-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bf9ba-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="bf9ba-107">Attributes and Elements</span></span>

<span data-ttu-id="bf9ba-108">次のセクションでは、`Frame` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bf9ba-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bf9ba-109">属性</span><span class="sxs-lookup"><span data-stu-id="bf9ba-109">Attributes</span></span>

<span data-ttu-id="bf9ba-110">なし。</span><span class="sxs-lookup"><span data-stu-id="bf9ba-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bf9ba-111">子要素</span><span class="sxs-lookup"><span data-stu-id="bf9ba-111">Child Elements</span></span>

|<span data-ttu-id="bf9ba-112">要素</span><span class="sxs-lookup"><span data-stu-id="bf9ba-112">Element</span></span>|<span data-ttu-id="bf9ba-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="bf9ba-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="bf9ba-114">必須の要素</span><span class="sxs-lookup"><span data-stu-id="bf9ba-114">Required Element</span></span>|
|[<span data-ttu-id="bf9ba-115">構成対象のコントロールのフレームの FirstLineHanging 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bf9ba-115">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="bf9ba-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="bf9ba-116">Optional element.</span></span><br /><br /> <span data-ttu-id="bf9ba-117">データの最初の行を左にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="bf9ba-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="bf9ba-118">構成対象のコントロールのフレームの FirstLineIndent 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bf9ba-118">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="bf9ba-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="bf9ba-119">Optional element.</span></span><br /><br /> <span data-ttu-id="bf9ba-120">データの最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="bf9ba-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="bf9ba-121">構成対象のコントロールのフレームの左インデント要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bf9ba-121">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="bf9ba-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="bf9ba-122">Optional element.</span></span><br /><br /> <span data-ttu-id="bf9ba-123">データを左余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="bf9ba-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="bf9ba-124">構成対象のコントロールのフレームの右インデント要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bf9ba-124">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="bf9ba-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="bf9ba-125">Optional element.</span></span><br /><br /> <span data-ttu-id="bf9ba-126">データを右余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="bf9ba-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bf9ba-127">親要素</span><span class="sxs-lookup"><span data-stu-id="bf9ba-127">Parent Elements</span></span>

|<span data-ttu-id="bf9ba-128">要素</span><span class="sxs-lookup"><span data-stu-id="bf9ba-128">Element</span></span>|<span data-ttu-id="bf9ba-129">[説明]</span><span class="sxs-lookup"><span data-stu-id="bf9ba-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bf9ba-130">構成のための CustomEntry コントロールの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="bf9ba-130">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="bf9ba-131">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="bf9ba-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bf9ba-132">コメント</span><span class="sxs-lookup"><span data-stu-id="bf9ba-132">Remarks</span></span>

<span data-ttu-id="bf9ba-133">同じ `Frame` 要素で[Firstlinehanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)と[firstlinehanging](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="bf9ba-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf9ba-134">参照</span><span class="sxs-lookup"><span data-stu-id="bf9ba-134">See Also</span></span>

[<span data-ttu-id="bf9ba-135">構成対象のコントロールのフレームの FirstLineHanging 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bf9ba-135">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="bf9ba-136">構成対象のコントロールのフレームの FirstLineIndent 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bf9ba-136">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="bf9ba-137">構成対象のコントロールのフレームの左インデント要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bf9ba-137">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="bf9ba-138">構成対象のコントロールのフレームの右インデント要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bf9ba-138">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="bf9ba-139">構成のための CustomEntry コントロールの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="bf9ba-139">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="bf9ba-140">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="bf9ba-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
