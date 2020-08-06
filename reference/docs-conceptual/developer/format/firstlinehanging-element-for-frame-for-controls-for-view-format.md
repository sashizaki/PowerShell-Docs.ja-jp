---
title: ビューのコントロールのフレームの FirstLineHanging 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 88c64619715c935089eb6c5a771584e4f69171d3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773625"
---
# <a name="firstlinehanging-element-for-frame-for-controls-for-view-format"></a><span data-ttu-id="396b1-102">View の Controls の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="396b1-102">FirstLineHanging Element for Frame for Controls for View (Format)</span></span>

<span data-ttu-id="396b1-103">データの最初の行を左にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="396b1-103">Specifies how many characters the first line of data is shifted to the left.</span></span> <span data-ttu-id="396b1-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="396b1-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="396b1-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロール要素 (形式) コントロールのコントロールの要素 (形式) コントロールの要素 (書式) を制御するためのコントロールの CustomControl 要素 (format) CustomControl for ビュー (形式) の CustomEntries 要素ビュー (format) のコントロールの CustomEntries のカスタムコントロールのビュー (format) Frame 要素のコントロールのビュー (形式) のフレーム要素を表示するためのコントロールの Customentries 要素を使用します。ビューのコントロールのフレームのビュー (Format) の Frame 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="396b1-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format) FirstLineHanging Element of Frame of Controls of View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="396b1-106">構文</span><span class="sxs-lookup"><span data-stu-id="396b1-106">Syntax</span></span>

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="396b1-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="396b1-107">Attributes and Elements</span></span>

<span data-ttu-id="396b1-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `FirstLineHanging` ます。</span><span class="sxs-lookup"><span data-stu-id="396b1-108">The following sections describe attributes, child elements, and parent element of the `FirstLineHanging` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="396b1-109">属性</span><span class="sxs-lookup"><span data-stu-id="396b1-109">Attributes</span></span>

<span data-ttu-id="396b1-110">なし。</span><span class="sxs-lookup"><span data-stu-id="396b1-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="396b1-111">子要素</span><span class="sxs-lookup"><span data-stu-id="396b1-111">Child Elements</span></span>

<span data-ttu-id="396b1-112">なし。</span><span class="sxs-lookup"><span data-stu-id="396b1-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="396b1-113">親要素</span><span class="sxs-lookup"><span data-stu-id="396b1-113">Parent Elements</span></span>

|<span data-ttu-id="396b1-114">要素</span><span class="sxs-lookup"><span data-stu-id="396b1-114">Element</span></span>|<span data-ttu-id="396b1-115">説明</span><span class="sxs-lookup"><span data-stu-id="396b1-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="396b1-116">View の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="396b1-116">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="396b1-117">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="396b1-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="396b1-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="396b1-118">Text Value</span></span>

<span data-ttu-id="396b1-119">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="396b1-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="396b1-120">解説</span><span class="sxs-lookup"><span data-stu-id="396b1-120">Remarks</span></span>

<span data-ttu-id="396b1-121">この要素が指定されている場合、 [Firstlineindent](./firstlineindent-element-for-frame-for-controls-for-view-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="396b1-121">If this element is specified, you cannot specify the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="396b1-122">参照</span><span class="sxs-lookup"><span data-stu-id="396b1-122">See Also</span></span>

[<span data-ttu-id="396b1-123">View の Controls の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="396b1-123">FirstLineIndent Element for Frame for Controls for View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="396b1-124">View の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="396b1-124">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="396b1-125">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="396b1-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
