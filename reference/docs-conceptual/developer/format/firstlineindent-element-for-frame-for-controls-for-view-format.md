---
ms.date: 09/13/2016
ms.topic: reference
title: View の Controls の Frame の FirstLineIndent 要素 (書式)
description: View の Controls の Frame の FirstLineIndent 要素 (書式)
ms.openlocfilehash: 425cd9ccafb2cbe36f238177fc73923da048f924
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660139"
---
# <a name="firstlineindent-element-for-frame-for-controls-for-view-format"></a><span data-ttu-id="46eb2-103">View の Controls の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="46eb2-103">FirstLineIndent Element for Frame for Controls for View (Format)</span></span>

<span data-ttu-id="46eb2-104">データの最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="46eb2-104">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="46eb2-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="46eb2-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="46eb2-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロール要素 (形式) コントロールのコントロールの要素 (形式) コントロールの要素 (書式) を制御するためのコントロールの CustomControl 要素 (format) CustomControl for ビュー (形式) の CustomEntries 要素ビュー (format) のコントロールの CustomEntries を使用して、ビュー (形式) のコントロールのビュー (format) の Frame 要素のコントロールのビュー (書式) のフレーム要素を表示するためのコントロールの Customentries 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="46eb2-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format) FirstLineIndent Element of Frame of Controls of View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="46eb2-107">構文</span><span class="sxs-lookup"><span data-stu-id="46eb2-107">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="46eb2-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="46eb2-108">Attributes and Elements</span></span>

<span data-ttu-id="46eb2-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `FirstLineIndent` ます。</span><span class="sxs-lookup"><span data-stu-id="46eb2-109">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="46eb2-110">属性</span><span class="sxs-lookup"><span data-stu-id="46eb2-110">Attributes</span></span>

<span data-ttu-id="46eb2-111">なし。</span><span class="sxs-lookup"><span data-stu-id="46eb2-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="46eb2-112">子要素</span><span class="sxs-lookup"><span data-stu-id="46eb2-112">Child Elements</span></span>

<span data-ttu-id="46eb2-113">なし。</span><span class="sxs-lookup"><span data-stu-id="46eb2-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="46eb2-114">親要素</span><span class="sxs-lookup"><span data-stu-id="46eb2-114">Parent Elements</span></span>

|<span data-ttu-id="46eb2-115">要素</span><span class="sxs-lookup"><span data-stu-id="46eb2-115">Element</span></span>|<span data-ttu-id="46eb2-116">説明</span><span class="sxs-lookup"><span data-stu-id="46eb2-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="46eb2-117">View の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="46eb2-117">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="46eb2-118">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="46eb2-118">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="46eb2-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="46eb2-119">Text Value</span></span>

<span data-ttu-id="46eb2-120">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="46eb2-120">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="46eb2-121">解説</span><span class="sxs-lookup"><span data-stu-id="46eb2-121">Remarks</span></span>

<span data-ttu-id="46eb2-122">この要素が指定されている場合、 [Firstlinehanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) 要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="46eb2-122">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="46eb2-123">参照</span><span class="sxs-lookup"><span data-stu-id="46eb2-123">See Also</span></span>

[<span data-ttu-id="46eb2-124">View の Controls の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="46eb2-124">FirstLineHanging Element for Frame for Controls for View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="46eb2-125">View の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="46eb2-125">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="46eb2-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="46eb2-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
