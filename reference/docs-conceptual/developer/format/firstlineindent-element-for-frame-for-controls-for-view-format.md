---
title: ビューのコントロールのフレームの FirstLineIndent 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec63f4f9-8858-4529-8646-ffbbc278f83e
caps.latest.revision: 7
ms.openlocfilehash: 694c5baaa5e90a772257276ba139d90acf7ec0e3
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363091"
---
# <a name="firstlineindent-element-for-frame-for-controls-for-view-format"></a><span data-ttu-id="91b41-102">View の Controls の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="91b41-102">FirstLineIndent Element for Frame for Controls for View (Format)</span></span>

<span data-ttu-id="91b41-103">データの最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="91b41-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="91b41-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="91b41-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="91b41-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素CustomControl for view (Format) CustomEntry 要素は、ビュー (format) の customentries 要素を使用して、コントロールのビュー (format) フレーム要素を表示するためのコントロールの Customentries 要素を指定します。ビューのコントロールの (書式)</span><span class="sxs-lookup"><span data-stu-id="91b41-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format) FirstLineIndent Element of Frame of Controls of View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="91b41-106">構文</span><span class="sxs-lookup"><span data-stu-id="91b41-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="91b41-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="91b41-107">Attributes and Elements</span></span>

<span data-ttu-id="91b41-108">次のセクションでは、`FirstLineIndent` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="91b41-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="91b41-109">属性</span><span class="sxs-lookup"><span data-stu-id="91b41-109">Attributes</span></span>

<span data-ttu-id="91b41-110">なし。</span><span class="sxs-lookup"><span data-stu-id="91b41-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="91b41-111">子要素</span><span class="sxs-lookup"><span data-stu-id="91b41-111">Child Elements</span></span>

<span data-ttu-id="91b41-112">なし。</span><span class="sxs-lookup"><span data-stu-id="91b41-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="91b41-113">親要素</span><span class="sxs-lookup"><span data-stu-id="91b41-113">Parent Elements</span></span>

|<span data-ttu-id="91b41-114">要素</span><span class="sxs-lookup"><span data-stu-id="91b41-114">Element</span></span>|<span data-ttu-id="91b41-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="91b41-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="91b41-116">ビューのコントロールの CustomItem の Frame 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="91b41-116">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="91b41-117">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="91b41-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="91b41-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="91b41-118">Text Value</span></span>

<span data-ttu-id="91b41-119">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="91b41-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="91b41-120">コメント</span><span class="sxs-lookup"><span data-stu-id="91b41-120">Remarks</span></span>

<span data-ttu-id="91b41-121">この要素が指定されている場合、 [Firstlinehanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="91b41-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="91b41-122">参照</span><span class="sxs-lookup"><span data-stu-id="91b41-122">See Also</span></span>

[<span data-ttu-id="91b41-123">ビューのコントロールのフレームの FirstLineHanging 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="91b41-123">FirstLineHanging Element for Frame for Controls for View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="91b41-124">ビューのコントロールの CustomItem の Frame 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="91b41-124">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="91b41-125">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="91b41-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
