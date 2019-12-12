---
title: ビューのコントロールのフレームの FirstLineHanging 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53694f08-57f7-4185-b443-1636a0918afc
caps.latest.revision: 8
ms.openlocfilehash: 387340cd9b0aae2ad0419b187d96ab4fee183d5a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363791"
---
# <a name="firstlinehanging-element-for-frame-for-controls-for-view-format"></a><span data-ttu-id="3f5b0-102">View の Controls の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3f5b0-102">FirstLineHanging Element for Frame for Controls for View (Format)</span></span>

<span data-ttu-id="3f5b0-103">データの最初の行を左にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f5b0-103">Specifies how many characters the first line of data is shifted to the left.</span></span> <span data-ttu-id="3f5b0-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f5b0-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="3f5b0-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素CustomControl for view (format) CustomEntry 要素は、ビュー (format) の customentries 要素に対して、コントロールのビュー (format) Frame 要素のコントロールのビュー (形式) の customentries 要素を表示します。ビューのコントロールのフレーム (書式)</span><span class="sxs-lookup"><span data-stu-id="3f5b0-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format) FirstLineHanging Element of Frame of Controls of View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3f5b0-106">構文</span><span class="sxs-lookup"><span data-stu-id="3f5b0-106">Syntax</span></span>

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3f5b0-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="3f5b0-107">Attributes and Elements</span></span>

<span data-ttu-id="3f5b0-108">次のセクションでは、`FirstLineHanging` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3f5b0-108">The following sections describe attributes, child elements, and parent element of the `FirstLineHanging` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3f5b0-109">属性</span><span class="sxs-lookup"><span data-stu-id="3f5b0-109">Attributes</span></span>

<span data-ttu-id="3f5b0-110">なし。</span><span class="sxs-lookup"><span data-stu-id="3f5b0-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3f5b0-111">子要素</span><span class="sxs-lookup"><span data-stu-id="3f5b0-111">Child Elements</span></span>

<span data-ttu-id="3f5b0-112">なし。</span><span class="sxs-lookup"><span data-stu-id="3f5b0-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3f5b0-113">親要素</span><span class="sxs-lookup"><span data-stu-id="3f5b0-113">Parent Elements</span></span>

|<span data-ttu-id="3f5b0-114">要素</span><span class="sxs-lookup"><span data-stu-id="3f5b0-114">Element</span></span>|<span data-ttu-id="3f5b0-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="3f5b0-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3f5b0-116">ビューのコントロールの CustomItem の Frame 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="3f5b0-116">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="3f5b0-117">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="3f5b0-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3f5b0-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="3f5b0-118">Text Value</span></span>

<span data-ttu-id="3f5b0-119">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f5b0-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="3f5b0-120">コメント</span><span class="sxs-lookup"><span data-stu-id="3f5b0-120">Remarks</span></span>

<span data-ttu-id="3f5b0-121">この要素が指定されている場合、 [Firstlineindent](./firstlineindent-element-for-frame-for-controls-for-view-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3f5b0-121">If this element is specified, you cannot specify the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f5b0-122">参照</span><span class="sxs-lookup"><span data-stu-id="3f5b0-122">See Also</span></span>

[<span data-ttu-id="3f5b0-123">ビューのコントロールのフレームの FirstLineIndent 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="3f5b0-123">FirstLineIndent Element for Frame for Controls for View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="3f5b0-124">ビューのコントロールの CustomItem の Frame 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="3f5b0-124">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="3f5b0-125">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="3f5b0-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
