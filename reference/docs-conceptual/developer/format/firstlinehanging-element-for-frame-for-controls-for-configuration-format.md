---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration の Controls の Frame の FirstLineHanging 要素 (書式)
description: Configuration の Controls の Frame の FirstLineHanging 要素 (書式)
ms.openlocfilehash: 94d59ef7b54e036f76e38a3b06b769700443b9fb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655236"
---
# <a name="firstlinehanging-element-for-frame-for-controls-for-configuration-format"></a><span data-ttu-id="82ef1-103">Configuration の Controls の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="82ef1-103">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>

<span data-ttu-id="82ef1-104">データの最初の行を左にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="82ef1-104">Specifies how many characters the first line of data is shifted to the left.</span></span> <span data-ttu-id="82ef1-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="82ef1-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="82ef1-106">Configuration 要素 (Format) コントロールの configuration (format) コントロールの要素の構成 (format) の CustomControl 要素の構成 (形式) の CustomControl の構成 (書式) の CustomEntries 要素のコントロール要素 CustomControl for Controls の構成 (フォーマット) Customentries 要素を使用した CustomEntry コントロールの構成フレーム要素の構成のためのコントロールの構成 (形式) の FirstLineHanging 要素の構成用コントロールのフレーム (形式)</span><span class="sxs-lookup"><span data-stu-id="82ef1-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format) FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="82ef1-107">構文</span><span class="sxs-lookup"><span data-stu-id="82ef1-107">Syntax</span></span>

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="82ef1-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="82ef1-108">Attributes and Elements</span></span>

<span data-ttu-id="82ef1-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `FirstLineHanging` ます。</span><span class="sxs-lookup"><span data-stu-id="82ef1-109">The following sections describe attributes, child elements, and parent element of the `FirstLineHanging` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="82ef1-110">属性</span><span class="sxs-lookup"><span data-stu-id="82ef1-110">Attributes</span></span>

<span data-ttu-id="82ef1-111">なし。</span><span class="sxs-lookup"><span data-stu-id="82ef1-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="82ef1-112">子要素</span><span class="sxs-lookup"><span data-stu-id="82ef1-112">Child Elements</span></span>

<span data-ttu-id="82ef1-113">なし。</span><span class="sxs-lookup"><span data-stu-id="82ef1-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="82ef1-114">親要素</span><span class="sxs-lookup"><span data-stu-id="82ef1-114">Parent Elements</span></span>

|<span data-ttu-id="82ef1-115">要素</span><span class="sxs-lookup"><span data-stu-id="82ef1-115">Element</span></span>|<span data-ttu-id="82ef1-116">説明</span><span class="sxs-lookup"><span data-stu-id="82ef1-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="82ef1-117">Configuration の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="82ef1-117">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="82ef1-118">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="82ef1-118">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="82ef1-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="82ef1-119">Text Value</span></span>

<span data-ttu-id="82ef1-120">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="82ef1-120">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="82ef1-121">解説</span><span class="sxs-lookup"><span data-stu-id="82ef1-121">Remarks</span></span>

<span data-ttu-id="82ef1-122">この要素が指定されている場合、要素を指定することはできません `FirstLineIndent` 。</span><span class="sxs-lookup"><span data-stu-id="82ef1-122">If this element is specified, you cannot specify the `FirstLineIndent` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="82ef1-123">参照</span><span class="sxs-lookup"><span data-stu-id="82ef1-123">See Also</span></span>

[<span data-ttu-id="82ef1-124">Configuration の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="82ef1-124">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="82ef1-125">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="82ef1-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
