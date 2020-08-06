---
title: CustomControl for ビュー (Format) の CustomItem の Frame 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4864ea1a865f77c9de6e495d7e8296e81c19b366
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781445"
---
# <a name="frame-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="abf3d-102">View の CustomControl の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="abf3d-102">Frame Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="abf3d-103">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="abf3d-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="abf3d-104">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="abf3d-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="abf3d-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) CustomControl 要素 (形式) CustomControl for view (format) の customentries 要素を表示するための CustomEntries for CustomControl for CustomControlView (Format) Frame Element for for View (Format) の Customentries 要素</span><span class="sxs-lookup"><span data-stu-id="abf3d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="abf3d-106">構文</span><span class="sxs-lookup"><span data-stu-id="abf3d-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="abf3d-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="abf3d-107">Attributes and Elements</span></span>

<span data-ttu-id="abf3d-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `Frame` ます。</span><span class="sxs-lookup"><span data-stu-id="abf3d-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="abf3d-109">属性</span><span class="sxs-lookup"><span data-stu-id="abf3d-109">Attributes</span></span>

<span data-ttu-id="abf3d-110">なし。</span><span class="sxs-lookup"><span data-stu-id="abf3d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="abf3d-111">子要素</span><span class="sxs-lookup"><span data-stu-id="abf3d-111">Child Elements</span></span>

|<span data-ttu-id="abf3d-112">要素</span><span class="sxs-lookup"><span data-stu-id="abf3d-112">Element</span></span>|<span data-ttu-id="abf3d-113">説明</span><span class="sxs-lookup"><span data-stu-id="abf3d-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="abf3d-114">必須の要素</span><span class="sxs-lookup"><span data-stu-id="abf3d-114">Required Element</span></span>|
|[<span data-ttu-id="abf3d-115">FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="abf3d-115">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="abf3d-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="abf3d-116">Optional element.</span></span><br /><br /> <span data-ttu-id="abf3d-117">データの最初の行を左にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="abf3d-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="abf3d-118">FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="abf3d-118">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="abf3d-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="abf3d-119">Optional element.</span></span><br /><br /> <span data-ttu-id="abf3d-120">データの最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="abf3d-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="abf3d-121">左インデント要素</span><span class="sxs-lookup"><span data-stu-id="abf3d-121">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="abf3d-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="abf3d-122">Optional element.</span></span><br /><br /> <span data-ttu-id="abf3d-123">データを左余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="abf3d-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="abf3d-124">右インデント要素</span><span class="sxs-lookup"><span data-stu-id="abf3d-124">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)|<span data-ttu-id="abf3d-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="abf3d-125">Optional element.</span></span><br /><br /> <span data-ttu-id="abf3d-126">データを右余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="abf3d-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="abf3d-127">親要素</span><span class="sxs-lookup"><span data-stu-id="abf3d-127">Parent Elements</span></span>

|<span data-ttu-id="abf3d-128">要素</span><span class="sxs-lookup"><span data-stu-id="abf3d-128">Element</span></span>|<span data-ttu-id="abf3d-129">説明</span><span class="sxs-lookup"><span data-stu-id="abf3d-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="abf3d-130">CustomEntry for ビューの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="abf3d-130">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="abf3d-131">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="abf3d-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="abf3d-132">解説</span><span class="sxs-lookup"><span data-stu-id="abf3d-132">Remarks</span></span>

<span data-ttu-id="abf3d-133">同じ要素で[Firstlinehanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)と[firstlinehanging](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)要素を指定することはできません `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="abf3d-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="abf3d-134">参照</span><span class="sxs-lookup"><span data-stu-id="abf3d-134">See Also</span></span>

[<span data-ttu-id="abf3d-135">FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="abf3d-135">FirstLineHanging Element</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="abf3d-136">FirstLineIndent 要素</span><span class="sxs-lookup"><span data-stu-id="abf3d-136">FirstLineIndent Element</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="abf3d-137">左インデント要素</span><span class="sxs-lookup"><span data-stu-id="abf3d-137">LeftIndent Element</span></span>](./leftindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="abf3d-138">右インデント要素</span><span class="sxs-lookup"><span data-stu-id="abf3d-138">RightIndent Element</span></span>](./rightindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="abf3d-139">CustomEntry for ビューの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="abf3d-139">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="abf3d-140">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="abf3d-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
