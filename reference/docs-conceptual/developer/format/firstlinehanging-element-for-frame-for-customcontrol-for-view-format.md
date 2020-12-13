---
ms.date: 09/13/2016
ms.topic: reference
title: View の CustomControl の Frame の FirstLineHanging 要素 (書式)
description: View の CustomControl の Frame の FirstLineHanging 要素 (書式)
ms.openlocfilehash: 8b9601b2afd7ab5523e339fb45119f5cf9f4a535
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648143"
---
# <a name="firstlinehanging-element-for-frame-for-customcontrol-for-view-format"></a><span data-ttu-id="cc0d0-103">View の CustomControl の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cc0d0-103">FirstLineHanging Element for Frame for CustomControl for View (Format)</span></span>

<span data-ttu-id="cc0d0-104">データの最初の行を左にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc0d0-104">Specifies how many characters the first line of data is shifted to the left.</span></span> <span data-ttu-id="cc0d0-105">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cc0d0-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="cc0d0-106">Configuration 要素 (Format) ViewDefinitions 要素 (形式) view Element (Format) CustomControl 要素 (Format) ビューの CustomEntries の CustomEntry 要素の CustomControl for view (format) の CustomEntries 要素を表示します。) CustomControl for View (Format) の Frame の CustomControl for ビュー (Format) FirstLineHanging 要素の customentries 要素の CustomEntry for CustomControlView (format) Frame 要素の Customentries 要素</span><span class="sxs-lookup"><span data-stu-id="cc0d0-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format) FirstLineHanging Element for Frame for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cc0d0-107">構文</span><span class="sxs-lookup"><span data-stu-id="cc0d0-107">Syntax</span></span>

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cc0d0-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cc0d0-108">Attributes and Elements</span></span>

<span data-ttu-id="cc0d0-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `FirstLineHanging` ます。</span><span class="sxs-lookup"><span data-stu-id="cc0d0-109">The following sections describe attributes, child elements, and parent element of the `FirstLineHanging` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cc0d0-110">属性</span><span class="sxs-lookup"><span data-stu-id="cc0d0-110">Attributes</span></span>

<span data-ttu-id="cc0d0-111">なし。</span><span class="sxs-lookup"><span data-stu-id="cc0d0-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cc0d0-112">子要素</span><span class="sxs-lookup"><span data-stu-id="cc0d0-112">Child Elements</span></span>

<span data-ttu-id="cc0d0-113">なし。</span><span class="sxs-lookup"><span data-stu-id="cc0d0-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cc0d0-114">親要素</span><span class="sxs-lookup"><span data-stu-id="cc0d0-114">Parent Elements</span></span>

|<span data-ttu-id="cc0d0-115">要素</span><span class="sxs-lookup"><span data-stu-id="cc0d0-115">Element</span></span>|<span data-ttu-id="cc0d0-116">説明</span><span class="sxs-lookup"><span data-stu-id="cc0d0-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cc0d0-117">View の CustomControl の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cc0d0-117">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="cc0d0-118">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="cc0d0-118">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="cc0d0-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="cc0d0-119">Text Value</span></span>

<span data-ttu-id="cc0d0-120">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc0d0-120">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc0d0-121">解説</span><span class="sxs-lookup"><span data-stu-id="cc0d0-121">Remarks</span></span>

<span data-ttu-id="cc0d0-122">この要素が指定されている場合、 [Firstlineindent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) 要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="cc0d0-122">If this element is specified, you cannot specify the [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc0d0-123">参照</span><span class="sxs-lookup"><span data-stu-id="cc0d0-123">See Also</span></span>

[<span data-ttu-id="cc0d0-124">View の CustomControl の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cc0d0-124">FirstLineIndent Element for Frame for CustomControl for View (Format)</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="cc0d0-125">View の CustomControl の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cc0d0-125">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="cc0d0-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="cc0d0-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
