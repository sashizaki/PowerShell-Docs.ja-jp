---
title: CustomControl for ビュー (Format) の CustomItem の Frame 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1a13100-41a4-4847-9f07-458c85783505
caps.latest.revision: 6
ms.openlocfilehash: 925ef86e61801f5a66f89dd25e0756f00dd35155
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363641"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="cca64-102">View の CustomControl の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cca64-102">Frame Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="cca64-103">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="cca64-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="cca64-104">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cca64-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="cca64-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素を表示するための CustomEntries for ビュー (形式) の Custommentry 要素CustomControl for ビュー (Format) の CustomItem for CustomControlView (Format) Frame 要素のための CustomEntry</span><span class="sxs-lookup"><span data-stu-id="cca64-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cca64-106">構文</span><span class="sxs-lookup"><span data-stu-id="cca64-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cca64-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="cca64-107">Attributes and Elements</span></span>

<span data-ttu-id="cca64-108">次のセクションでは、`Frame` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cca64-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cca64-109">属性</span><span class="sxs-lookup"><span data-stu-id="cca64-109">Attributes</span></span>

<span data-ttu-id="cca64-110">なし。</span><span class="sxs-lookup"><span data-stu-id="cca64-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cca64-111">子要素</span><span class="sxs-lookup"><span data-stu-id="cca64-111">Child Elements</span></span>

|<span data-ttu-id="cca64-112">要素</span><span class="sxs-lookup"><span data-stu-id="cca64-112">Element</span></span>|<span data-ttu-id="cca64-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="cca64-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="cca64-114">必須の要素</span><span class="sxs-lookup"><span data-stu-id="cca64-114">Required Element</span></span>|
|[<span data-ttu-id="cca64-115">FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="cca64-115">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="cca64-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="cca64-116">Optional element.</span></span><br /><br /> <span data-ttu-id="cca64-117">データの最初の行を左にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="cca64-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="cca64-118">FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="cca64-118">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="cca64-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="cca64-119">Optional element.</span></span><br /><br /> <span data-ttu-id="cca64-120">データの最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="cca64-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="cca64-121">左インデント要素</span><span class="sxs-lookup"><span data-stu-id="cca64-121">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="cca64-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="cca64-122">Optional element.</span></span><br /><br /> <span data-ttu-id="cca64-123">データを左余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="cca64-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="cca64-124">右インデント要素</span><span class="sxs-lookup"><span data-stu-id="cca64-124">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="cca64-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="cca64-125">Optional element.</span></span><br /><br /> <span data-ttu-id="cca64-126">データを右余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="cca64-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cca64-127">親要素</span><span class="sxs-lookup"><span data-stu-id="cca64-127">Parent Elements</span></span>

|<span data-ttu-id="cca64-128">要素</span><span class="sxs-lookup"><span data-stu-id="cca64-128">Element</span></span>|<span data-ttu-id="cca64-129">[説明]</span><span class="sxs-lookup"><span data-stu-id="cca64-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cca64-130">CustomEntry for ビューの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="cca64-130">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="cca64-131">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="cca64-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cca64-132">コメント</span><span class="sxs-lookup"><span data-stu-id="cca64-132">Remarks</span></span>

<span data-ttu-id="cca64-133">同じ `Frame` 要素で[Firstlinehanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)と[firstlinehanging](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="cca64-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="cca64-134">参照</span><span class="sxs-lookup"><span data-stu-id="cca64-134">See Also</span></span>

[<span data-ttu-id="cca64-135">FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="cca64-135">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="cca64-136">FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="cca64-136">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="cca64-137">左インデント要素</span><span class="sxs-lookup"><span data-stu-id="cca64-137">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="cca64-138">右インデント要素</span><span class="sxs-lookup"><span data-stu-id="cca64-138">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="cca64-139">CustomEntry for ビューの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="cca64-139">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="cca64-140">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="cca64-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
