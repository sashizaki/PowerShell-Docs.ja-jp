---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の Frame の FirstLineIndent 要素 (書式)
description: GroupBy の Frame の FirstLineIndent 要素 (書式)
ms.openlocfilehash: 391a6f338e264fd9fdd1948ded74bf022cb114d1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645796"
---
# <a name="firstlineindent-element-for-frame-for-groupby-format"></a><span data-ttu-id="cbb98-103">GroupBy の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cbb98-103">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>

<span data-ttu-id="cbb98-104">データの最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="cbb98-104">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="cbb98-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cbb98-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="cbb98-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素を使用して、groupby (形式) の CustomControl 要素を groupby (形式) CustomEntry の CustomControl の CustomEntries 要素 groupby (書式) のための groupby (format) の Customentries 要素の groupby (format) フレーム要素の CustomControl のための要素に対する groupby (Format) の Customentries 要素の設定 groupby (形式) の Frame の要素</span><span class="sxs-lookup"><span data-stu-id="cbb98-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format) FirstLineIndent Element for Frame for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cbb98-107">構文</span><span class="sxs-lookup"><span data-stu-id="cbb98-107">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cbb98-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cbb98-108">Attributes and Elements</span></span>

<span data-ttu-id="cbb98-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `FirstLineIndent` ます。</span><span class="sxs-lookup"><span data-stu-id="cbb98-109">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cbb98-110">属性</span><span class="sxs-lookup"><span data-stu-id="cbb98-110">Attributes</span></span>

<span data-ttu-id="cbb98-111">なし。</span><span class="sxs-lookup"><span data-stu-id="cbb98-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cbb98-112">子要素</span><span class="sxs-lookup"><span data-stu-id="cbb98-112">Child Elements</span></span>

<span data-ttu-id="cbb98-113">なし。</span><span class="sxs-lookup"><span data-stu-id="cbb98-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cbb98-114">親要素</span><span class="sxs-lookup"><span data-stu-id="cbb98-114">Parent Elements</span></span>

|<span data-ttu-id="cbb98-115">要素</span><span class="sxs-lookup"><span data-stu-id="cbb98-115">Element</span></span>|<span data-ttu-id="cbb98-116">説明</span><span class="sxs-lookup"><span data-stu-id="cbb98-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cbb98-117">GroupBy の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cbb98-117">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="cbb98-118">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="cbb98-118">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="cbb98-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="cbb98-119">Text Value</span></span>

<span data-ttu-id="cbb98-120">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="cbb98-120">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="cbb98-121">解説</span><span class="sxs-lookup"><span data-stu-id="cbb98-121">Remarks</span></span>

<span data-ttu-id="cbb98-122">この要素が指定されている場合、 [Firstlinehanging](./firstlinehanging-element-for-frame-for-groupby-format.md) 要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="cbb98-122">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="cbb98-123">参照</span><span class="sxs-lookup"><span data-stu-id="cbb98-123">See Also</span></span>

[<span data-ttu-id="cbb98-124">GroupBy の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cbb98-124">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="cbb98-125">GroupBy の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cbb98-125">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="cbb98-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="cbb98-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
