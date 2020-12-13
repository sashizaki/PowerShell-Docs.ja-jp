---
ms.date: 09/13/2016
ms.topic: reference
title: View の Controls の Frame の FirstLineHanging 要素 (書式)
description: View の Controls の Frame の FirstLineHanging 要素 (書式)
ms.openlocfilehash: a7a2aa533a74bd3c347307ab49a467d1f9844fc3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655206"
---
# <a name="firstlinehanging-element-for-frame-for-controls-for-view-format"></a><span data-ttu-id="ec221-103">View の Controls の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ec221-103">FirstLineHanging Element for Frame for Controls for View (Format)</span></span>

<span data-ttu-id="ec221-104">データの最初の行を左にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ec221-104">Specifies how many characters the first line of data is shifted to the left.</span></span> <span data-ttu-id="ec221-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ec221-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="ec221-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロール要素 (形式) コントロールのコントロールの要素 (形式) コントロールの要素 (書式) を制御するためのコントロールの CustomControl 要素 (format) CustomControl for ビュー (形式) の CustomEntries 要素ビュー (format) のコントロールの CustomEntries のカスタムコントロールのビュー (format) Frame 要素のコントロールのビュー (形式) のフレーム要素を表示するためのコントロールの Customentries 要素を使用します。ビューのコントロールのフレームのビュー (Format) の Frame 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="ec221-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format) FirstLineHanging Element of Frame of Controls of View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ec221-107">構文</span><span class="sxs-lookup"><span data-stu-id="ec221-107">Syntax</span></span>

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ec221-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ec221-108">Attributes and Elements</span></span>

<span data-ttu-id="ec221-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `FirstLineHanging` ます。</span><span class="sxs-lookup"><span data-stu-id="ec221-109">The following sections describe attributes, child elements, and parent element of the `FirstLineHanging` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ec221-110">属性</span><span class="sxs-lookup"><span data-stu-id="ec221-110">Attributes</span></span>

<span data-ttu-id="ec221-111">なし。</span><span class="sxs-lookup"><span data-stu-id="ec221-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ec221-112">子要素</span><span class="sxs-lookup"><span data-stu-id="ec221-112">Child Elements</span></span>

<span data-ttu-id="ec221-113">なし。</span><span class="sxs-lookup"><span data-stu-id="ec221-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ec221-114">親要素</span><span class="sxs-lookup"><span data-stu-id="ec221-114">Parent Elements</span></span>

|<span data-ttu-id="ec221-115">要素</span><span class="sxs-lookup"><span data-stu-id="ec221-115">Element</span></span>|<span data-ttu-id="ec221-116">説明</span><span class="sxs-lookup"><span data-stu-id="ec221-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ec221-117">View の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ec221-117">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="ec221-118">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="ec221-118">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ec221-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="ec221-119">Text Value</span></span>

<span data-ttu-id="ec221-120">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ec221-120">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="ec221-121">解説</span><span class="sxs-lookup"><span data-stu-id="ec221-121">Remarks</span></span>

<span data-ttu-id="ec221-122">この要素が指定されている場合、 [Firstlineindent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) 要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="ec221-122">If this element is specified, you cannot specify the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec221-123">参照</span><span class="sxs-lookup"><span data-stu-id="ec221-123">See Also</span></span>

[<span data-ttu-id="ec221-124">View の Controls の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ec221-124">FirstLineIndent Element for Frame for Controls for View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="ec221-125">View の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ec221-125">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="ec221-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="ec221-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
