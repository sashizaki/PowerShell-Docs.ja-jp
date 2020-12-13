---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration の Controls の Frame の FirstLineIndent 要素 (書式)
description: Configuration の Controls の Frame の FirstLineIndent 要素 (書式)
ms.openlocfilehash: 59a41410160879c2414819de4d367ecdedd8e182
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660167"
---
# <a name="firstlineindent-element-for-frame-for-controls-for-configuration-format"></a><span data-ttu-id="2624e-103">Configuration の Controls の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2624e-103">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>

<span data-ttu-id="2624e-104">データの最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2624e-104">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="2624e-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2624e-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="2624e-106">Configuration 要素 (Format) コントロールの configuration (format) コントロールの要素の構成 (format) の CustomControl 要素の構成 (形式) の CustomControl の構成 (書式) の CustomEntries 要素のコントロール要素 CustomControl for Controls の構成 (書式) Customentries 要素のコントロール用の構成フレーム要素の構成用コントロールの構成 (形式) の Customlineindent 要素を構成するためのコントロールのためのフレーム (形式)</span><span class="sxs-lookup"><span data-stu-id="2624e-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format) FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2624e-107">構文</span><span class="sxs-lookup"><span data-stu-id="2624e-107">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2624e-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2624e-108">Attributes and Elements</span></span>

<span data-ttu-id="2624e-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `FirstLineIndent` ます。</span><span class="sxs-lookup"><span data-stu-id="2624e-109">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2624e-110">属性</span><span class="sxs-lookup"><span data-stu-id="2624e-110">Attributes</span></span>

<span data-ttu-id="2624e-111">なし。</span><span class="sxs-lookup"><span data-stu-id="2624e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2624e-112">子要素</span><span class="sxs-lookup"><span data-stu-id="2624e-112">Child Elements</span></span>

<span data-ttu-id="2624e-113">なし。</span><span class="sxs-lookup"><span data-stu-id="2624e-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2624e-114">親要素</span><span class="sxs-lookup"><span data-stu-id="2624e-114">Parent Elements</span></span>

|<span data-ttu-id="2624e-115">要素</span><span class="sxs-lookup"><span data-stu-id="2624e-115">Element</span></span>|<span data-ttu-id="2624e-116">説明</span><span class="sxs-lookup"><span data-stu-id="2624e-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2624e-117">Configuration の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2624e-117">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="2624e-118">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="2624e-118">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2624e-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="2624e-119">Text Value</span></span>

<span data-ttu-id="2624e-120">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2624e-120">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="2624e-121">解説</span><span class="sxs-lookup"><span data-stu-id="2624e-121">Remarks</span></span>

<span data-ttu-id="2624e-122">この要素が指定されている場合、 [Firstlinehanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) 要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="2624e-122">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="2624e-123">参照</span><span class="sxs-lookup"><span data-stu-id="2624e-123">See Also</span></span>

[<span data-ttu-id="2624e-124">Configuration の Controls の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2624e-124">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="2624e-125">Configuration の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2624e-125">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="2624e-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="2624e-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
