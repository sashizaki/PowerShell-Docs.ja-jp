---
title: 構成用のコントロールのフレームの FirstLineIndent 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 9ac1d8dc74af12b87f0b490d7c1f75d028e3521f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773591"
---
# <a name="firstlineindent-element-for-frame-for-controls-for-configuration-format"></a><span data-ttu-id="94dc1-102">Configuration の Controls の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="94dc1-102">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>

<span data-ttu-id="94dc1-103">データの最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="94dc1-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="94dc1-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="94dc1-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="94dc1-105">Configuration 要素 (Format) コントロールの configuration (format) コントロールの要素の構成 (format) の CustomControl 要素の構成 (形式) の CustomControl の構成 (書式) の CustomEntries 要素のコントロール要素 CustomControl for Controls の構成 (書式) Customentries 要素のコントロール用の構成フレーム要素の構成用コントロールの構成 (形式) の Customlineindent 要素を構成するためのコントロールのためのフレーム (形式)</span><span class="sxs-lookup"><span data-stu-id="94dc1-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format) FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="94dc1-106">構文</span><span class="sxs-lookup"><span data-stu-id="94dc1-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="94dc1-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="94dc1-107">Attributes and Elements</span></span>

<span data-ttu-id="94dc1-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `FirstLineIndent` ます。</span><span class="sxs-lookup"><span data-stu-id="94dc1-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="94dc1-109">属性</span><span class="sxs-lookup"><span data-stu-id="94dc1-109">Attributes</span></span>

<span data-ttu-id="94dc1-110">なし。</span><span class="sxs-lookup"><span data-stu-id="94dc1-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="94dc1-111">子要素</span><span class="sxs-lookup"><span data-stu-id="94dc1-111">Child Elements</span></span>

<span data-ttu-id="94dc1-112">なし。</span><span class="sxs-lookup"><span data-stu-id="94dc1-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="94dc1-113">親要素</span><span class="sxs-lookup"><span data-stu-id="94dc1-113">Parent Elements</span></span>

|<span data-ttu-id="94dc1-114">要素</span><span class="sxs-lookup"><span data-stu-id="94dc1-114">Element</span></span>|<span data-ttu-id="94dc1-115">説明</span><span class="sxs-lookup"><span data-stu-id="94dc1-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="94dc1-116">Configuration の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="94dc1-116">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="94dc1-117">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="94dc1-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="94dc1-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="94dc1-118">Text Value</span></span>

<span data-ttu-id="94dc1-119">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="94dc1-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="94dc1-120">解説</span><span class="sxs-lookup"><span data-stu-id="94dc1-120">Remarks</span></span>

<span data-ttu-id="94dc1-121">この要素が指定されている場合、 [Firstlinehanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="94dc1-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="94dc1-122">参照</span><span class="sxs-lookup"><span data-stu-id="94dc1-122">See Also</span></span>

[<span data-ttu-id="94dc1-123">Configuration の Controls の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="94dc1-123">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="94dc1-124">Configuration の Controls の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="94dc1-124">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="94dc1-125">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="94dc1-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
