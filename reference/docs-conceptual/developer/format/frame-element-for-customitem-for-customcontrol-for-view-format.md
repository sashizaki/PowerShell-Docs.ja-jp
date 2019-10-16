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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363641"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="e5c42-102">View の CustomControl の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e5c42-102">Frame Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="e5c42-103">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="e5c42-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="e5c42-104">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5c42-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="e5c42-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素を表示するための CustomEntries for ビュー (形式) の Custommentry 要素CustomControl for ビュー (Format) の CustomItem for CustomControlView (Format) Frame 要素のための CustomEntry</span><span class="sxs-lookup"><span data-stu-id="e5c42-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e5c42-106">構文</span><span class="sxs-lookup"><span data-stu-id="e5c42-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e5c42-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="e5c42-107">Attributes and Elements</span></span>

<span data-ttu-id="e5c42-108">次のセクションでは、属性、子要素、`Frame` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5c42-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e5c42-109">属性</span><span class="sxs-lookup"><span data-stu-id="e5c42-109">Attributes</span></span>

<span data-ttu-id="e5c42-110">なし。</span><span class="sxs-lookup"><span data-stu-id="e5c42-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e5c42-111">子要素</span><span class="sxs-lookup"><span data-stu-id="e5c42-111">Child Elements</span></span>

|<span data-ttu-id="e5c42-112">要素</span><span class="sxs-lookup"><span data-stu-id="e5c42-112">Element</span></span>|<span data-ttu-id="e5c42-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="e5c42-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="e5c42-114">必須の要素</span><span class="sxs-lookup"><span data-stu-id="e5c42-114">Required Element</span></span>|
|[<span data-ttu-id="e5c42-115">FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="e5c42-115">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="e5c42-116">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="e5c42-116">Optional element.</span></span><br /><br /> <span data-ttu-id="e5c42-117">データの最初の行を左にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5c42-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="e5c42-118">FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="e5c42-118">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="e5c42-119">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="e5c42-119">Optional element.</span></span><br /><br /> <span data-ttu-id="e5c42-120">データの最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5c42-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="e5c42-121">左インデント要素</span><span class="sxs-lookup"><span data-stu-id="e5c42-121">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="e5c42-122">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="e5c42-122">Optional element.</span></span><br /><br /> <span data-ttu-id="e5c42-123">データを左余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5c42-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="e5c42-124">右インデント要素</span><span class="sxs-lookup"><span data-stu-id="e5c42-124">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="e5c42-125">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="e5c42-125">Optional element.</span></span><br /><br /> <span data-ttu-id="e5c42-126">データを右余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5c42-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e5c42-127">親要素</span><span class="sxs-lookup"><span data-stu-id="e5c42-127">Parent Elements</span></span>

|<span data-ttu-id="e5c42-128">要素</span><span class="sxs-lookup"><span data-stu-id="e5c42-128">Element</span></span>|<span data-ttu-id="e5c42-129">[説明]</span><span class="sxs-lookup"><span data-stu-id="e5c42-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e5c42-130">CustomEntry for ビューの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="e5c42-130">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="e5c42-131">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="e5c42-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e5c42-132">コメント</span><span class="sxs-lookup"><span data-stu-id="e5c42-132">Remarks</span></span>

<span data-ttu-id="e5c42-133">[Firstlinehanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)と[firstlinehanging](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)要素を同じ `Frame` 要素で指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e5c42-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5c42-134">参照</span><span class="sxs-lookup"><span data-stu-id="e5c42-134">See Also</span></span>

[<span data-ttu-id="e5c42-135">FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="e5c42-135">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e5c42-136">FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="e5c42-136">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e5c42-137">左インデント要素</span><span class="sxs-lookup"><span data-stu-id="e5c42-137">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e5c42-138">右インデント要素</span><span class="sxs-lookup"><span data-stu-id="e5c42-138">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e5c42-139">CustomEntry for ビューの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="e5c42-139">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e5c42-140">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="e5c42-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
