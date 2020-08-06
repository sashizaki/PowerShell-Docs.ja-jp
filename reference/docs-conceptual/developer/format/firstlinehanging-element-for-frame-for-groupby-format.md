---
title: GroupBy (Format) の Frame の FirstLineHanging 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 3def56e918810d9e201d7a9ae73776d90646d8b3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773608"
---
# <a name="firstlinehanging-element-for-frame-for-groupby-format"></a><span data-ttu-id="d6a2e-102">GroupBy の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d6a2e-102">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>

<span data-ttu-id="d6a2e-103">データの最初の行を左にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6a2e-103">Specifies how many characters the first line of data is shifted to the left.</span></span> <span data-ttu-id="d6a2e-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d6a2e-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="d6a2e-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素を使用して、groupby (形式) の CustomControl 要素を groupby (形式) CustomEntry の CustomControl の CustomEntries 要素 CustomControl for groupby (format) Customentries 要素の CustomEntry for groupby (書式) の Frame 要素の Customentries for groupby (format) のフレームの ' groupby (形式) ' の frame 要素の要素です。</span><span class="sxs-lookup"><span data-stu-id="d6a2e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format) FirstLineHanging Element for Frame for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d6a2e-106">構文</span><span class="sxs-lookup"><span data-stu-id="d6a2e-106">Syntax</span></span>

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d6a2e-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d6a2e-107">Attributes and Elements</span></span>

<span data-ttu-id="d6a2e-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `FirstLineHanging` ます。</span><span class="sxs-lookup"><span data-stu-id="d6a2e-108">The following sections describe attributes, child elements, and parent element of the `FirstLineHanging` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d6a2e-109">属性</span><span class="sxs-lookup"><span data-stu-id="d6a2e-109">Attributes</span></span>

<span data-ttu-id="d6a2e-110">なし。</span><span class="sxs-lookup"><span data-stu-id="d6a2e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d6a2e-111">子要素</span><span class="sxs-lookup"><span data-stu-id="d6a2e-111">Child Elements</span></span>

<span data-ttu-id="d6a2e-112">なし。</span><span class="sxs-lookup"><span data-stu-id="d6a2e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d6a2e-113">親要素</span><span class="sxs-lookup"><span data-stu-id="d6a2e-113">Parent Elements</span></span>

|<span data-ttu-id="d6a2e-114">要素</span><span class="sxs-lookup"><span data-stu-id="d6a2e-114">Element</span></span>|<span data-ttu-id="d6a2e-115">説明</span><span class="sxs-lookup"><span data-stu-id="d6a2e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d6a2e-116">GroupBy の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d6a2e-116">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="d6a2e-117">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="d6a2e-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d6a2e-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="d6a2e-118">Text Value</span></span>

<span data-ttu-id="d6a2e-119">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6a2e-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="d6a2e-120">解説</span><span class="sxs-lookup"><span data-stu-id="d6a2e-120">Remarks</span></span>

<span data-ttu-id="d6a2e-121">この要素が指定されている場合、 [Firstlineindent](./firstlineindent-element-for-frame-for-groupby-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d6a2e-121">If this element is specified, you cannot specify the [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6a2e-122">参照</span><span class="sxs-lookup"><span data-stu-id="d6a2e-122">See Also</span></span>

[<span data-ttu-id="d6a2e-123">GroupBy の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d6a2e-123">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="d6a2e-124">GroupBy の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d6a2e-124">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="d6a2e-125">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="d6a2e-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
