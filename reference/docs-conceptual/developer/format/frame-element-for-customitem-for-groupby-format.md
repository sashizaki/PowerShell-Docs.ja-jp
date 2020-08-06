---
title: GroupBy (Format) の CustomItem の Frame 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1568236ff7b6142f7e41be70a3ae5e28307cf790
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785763"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a><span data-ttu-id="b0d7a-102">GroupBy の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b0d7a-102">Frame Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="b0d7a-103">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="b0d7a-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="b0d7a-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0d7a-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="b0d7a-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素については、groupby (format) の CustomControl 要素に対して、groupby (形式) の CustomEntries 要素を指定します。 groupby (書式) の customentries 要素については、groupby (format) の Customentries の groupby (format) フレーム要素の CustomControl</span><span class="sxs-lookup"><span data-stu-id="b0d7a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b0d7a-106">構文</span><span class="sxs-lookup"><span data-stu-id="b0d7a-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b0d7a-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b0d7a-107">Attributes and Elements</span></span>

<span data-ttu-id="b0d7a-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `Frame` ます。</span><span class="sxs-lookup"><span data-stu-id="b0d7a-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b0d7a-109">属性</span><span class="sxs-lookup"><span data-stu-id="b0d7a-109">Attributes</span></span>

<span data-ttu-id="b0d7a-110">なし。</span><span class="sxs-lookup"><span data-stu-id="b0d7a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b0d7a-111">子要素</span><span class="sxs-lookup"><span data-stu-id="b0d7a-111">Child Elements</span></span>

|<span data-ttu-id="b0d7a-112">要素</span><span class="sxs-lookup"><span data-stu-id="b0d7a-112">Element</span></span>|<span data-ttu-id="b0d7a-113">説明</span><span class="sxs-lookup"><span data-stu-id="b0d7a-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="b0d7a-114">必須の要素</span><span class="sxs-lookup"><span data-stu-id="b0d7a-114">Required Element</span></span>|
|[<span data-ttu-id="b0d7a-115">GroupBy の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b0d7a-115">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)|<span data-ttu-id="b0d7a-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="b0d7a-116">Optional element.</span></span><br /><br /> <span data-ttu-id="b0d7a-117">データの最初の行を左にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0d7a-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="b0d7a-118">GroupBy の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b0d7a-118">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="b0d7a-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="b0d7a-119">Optional element.</span></span><br /><br /> <span data-ttu-id="b0d7a-120">データの最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0d7a-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="b0d7a-121">GroupBy の Frame の LeftIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b0d7a-121">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="b0d7a-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="b0d7a-122">Optional element.</span></span><br /><br /> <span data-ttu-id="b0d7a-123">データを左余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0d7a-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|<span data-ttu-id="b0d7a-124">[GroupBy (Format) の Frame の右インデント要素](./rightindent-element-for-frame-for-groupby-format.md)右インデント要素</span><span class="sxs-lookup"><span data-stu-id="b0d7a-124">[RightIndent Element for Frame for GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent Element</span></span>|<span data-ttu-id="b0d7a-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="b0d7a-125">Optional element.</span></span><br /><br /> <span data-ttu-id="b0d7a-126">データを右余白から移動する文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0d7a-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b0d7a-127">親要素</span><span class="sxs-lookup"><span data-stu-id="b0d7a-127">Parent Elements</span></span>

|<span data-ttu-id="b0d7a-128">要素</span><span class="sxs-lookup"><span data-stu-id="b0d7a-128">Element</span></span>|<span data-ttu-id="b0d7a-129">説明</span><span class="sxs-lookup"><span data-stu-id="b0d7a-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b0d7a-130">GroupBy の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b0d7a-130">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="b0d7a-131">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="b0d7a-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b0d7a-132">解説</span><span class="sxs-lookup"><span data-stu-id="b0d7a-132">Remarks</span></span>

<span data-ttu-id="b0d7a-133">同じ要素で[Firstlinehanging](./firstlinehanging-element-for-frame-for-groupby-format.md)と[firstlinehanging](./firstlineindent-element-for-frame-for-groupby-format.md)要素を指定することはできません `Frame` 。</span><span class="sxs-lookup"><span data-stu-id="b0d7a-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0d7a-134">参照</span><span class="sxs-lookup"><span data-stu-id="b0d7a-134">See Also</span></span>

[<span data-ttu-id="b0d7a-135">GroupBy の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b0d7a-135">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="b0d7a-136">GroupBy の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b0d7a-136">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="b0d7a-137">GroupBy の Frame の LeftIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b0d7a-137">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="b0d7a-138">GroupBy の Frame の RightIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b0d7a-138">RightIndent Element for Frame for GroupBy (Format)</span></span>](./rightindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="b0d7a-139">GroupBy の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b0d7a-139">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="b0d7a-140">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="b0d7a-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
