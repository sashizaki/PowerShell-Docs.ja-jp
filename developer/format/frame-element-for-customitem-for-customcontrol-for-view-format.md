---
title: CustomItem の表示 (形式) のカスタム コントロールの要素をフレーム |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1a13100-41a4-4847-9f07-458c85783505
caps.latest.revision: 6
ms.openlocfilehash: 925ef86e61801f5a66f89dd25e0756f00dd35155
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065582"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="d4f24-102">View の CustomControl の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d4f24-102">Frame Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="d4f24-103">データを左または右にシフトなど、データを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="d4f24-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="d4f24-104">この要素は、カスタム コントロールのビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d4f24-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="d4f24-105">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) CustomItem 要素 CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールCustomEntry CustomItem ビュー (形式) のカスタム コントロール用のフレーム要素を CustomControlView (形式)</span><span class="sxs-lookup"><span data-stu-id="d4f24-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d4f24-106">構文</span><span class="sxs-lookup"><span data-stu-id="d4f24-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d4f24-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d4f24-107">Attributes and Elements</span></span>

<span data-ttu-id="d4f24-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`Frame`要素。</span><span class="sxs-lookup"><span data-stu-id="d4f24-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d4f24-109">属性</span><span class="sxs-lookup"><span data-stu-id="d4f24-109">Attributes</span></span>

<span data-ttu-id="d4f24-110">なし。</span><span class="sxs-lookup"><span data-stu-id="d4f24-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d4f24-111">子要素</span><span class="sxs-lookup"><span data-stu-id="d4f24-111">Child Elements</span></span>

|<span data-ttu-id="d4f24-112">要素</span><span class="sxs-lookup"><span data-stu-id="d4f24-112">Element</span></span>|<span data-ttu-id="d4f24-113">説明</span><span class="sxs-lookup"><span data-stu-id="d4f24-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="d4f24-114">必要な要素</span><span class="sxs-lookup"><span data-stu-id="d4f24-114">Required Element</span></span>|
|[<span data-ttu-id="d4f24-115">FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="d4f24-115">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="d4f24-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d4f24-116">Optional element.</span></span><br /><br /> <span data-ttu-id="d4f24-117">データの最初の行が左にシフト文字の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4f24-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="d4f24-118">FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="d4f24-118">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="d4f24-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d4f24-119">Optional element.</span></span><br /><br /> <span data-ttu-id="d4f24-120">データの最初の行が右側にシフトした文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4f24-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="d4f24-121">LeftIndent 要素</span><span class="sxs-lookup"><span data-stu-id="d4f24-121">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="d4f24-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d4f24-122">Optional element.</span></span><br /><br /> <span data-ttu-id="d4f24-123">左余白からデータを移動する文字の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4f24-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="d4f24-124">RightIndent 要素</span><span class="sxs-lookup"><span data-stu-id="d4f24-124">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="d4f24-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d4f24-125">Optional element.</span></span><br /><br /> <span data-ttu-id="d4f24-126">右の余白からデータを移動する文字の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4f24-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d4f24-127">親要素</span><span class="sxs-lookup"><span data-stu-id="d4f24-127">Parent Elements</span></span>

|<span data-ttu-id="d4f24-128">要素</span><span class="sxs-lookup"><span data-stu-id="d4f24-128">Element</span></span>|<span data-ttu-id="d4f24-129">説明</span><span class="sxs-lookup"><span data-stu-id="d4f24-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d4f24-130">表示 (形式) CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="d4f24-130">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="d4f24-131">どのようなデータが、コントロールによって表示され、表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="d4f24-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d4f24-132">コメント</span><span class="sxs-lookup"><span data-stu-id="d4f24-132">Remarks</span></span>

<span data-ttu-id="d4f24-133">指定することはできません、 [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)と[FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)要素で同じ`Frame`要素。</span><span class="sxs-lookup"><span data-stu-id="d4f24-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4f24-134">参照</span><span class="sxs-lookup"><span data-stu-id="d4f24-134">See Also</span></span>

[<span data-ttu-id="d4f24-135">FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="d4f24-135">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="d4f24-136">FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="d4f24-136">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="d4f24-137">LeftIndent 要素</span><span class="sxs-lookup"><span data-stu-id="d4f24-137">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="d4f24-138">RightIndent 要素</span><span class="sxs-lookup"><span data-stu-id="d4f24-138">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="d4f24-139">表示 (形式) CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="d4f24-139">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="d4f24-140">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="d4f24-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
