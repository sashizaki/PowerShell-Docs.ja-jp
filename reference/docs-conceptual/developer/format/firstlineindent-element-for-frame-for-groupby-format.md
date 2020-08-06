---
title: GroupBy (Format) の Frame の FirstLineIndent 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: def5b4e9ca98a15edbb36675ca506e886de567dc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781666"
---
# <a name="firstlineindent-element-for-frame-for-groupby-format"></a><span data-ttu-id="6ff7f-102">GroupBy の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6ff7f-102">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>

<span data-ttu-id="6ff7f-103">データの最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="6ff7f-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="6ff7f-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ff7f-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="6ff7f-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素を使用して、groupby (形式) の CustomControl 要素を groupby (形式) CustomEntry の CustomControl の CustomEntries 要素 groupby (書式) のための groupby (format) の Customentries 要素の groupby (format) フレーム要素の CustomControl のための要素に対する groupby (Format) の Customentries 要素の設定 groupby (形式) の Frame の要素</span><span class="sxs-lookup"><span data-stu-id="6ff7f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format) FirstLineIndent Element for Frame for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6ff7f-106">構文</span><span class="sxs-lookup"><span data-stu-id="6ff7f-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6ff7f-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6ff7f-107">Attributes and Elements</span></span>

<span data-ttu-id="6ff7f-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `FirstLineIndent` ます。</span><span class="sxs-lookup"><span data-stu-id="6ff7f-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6ff7f-109">属性</span><span class="sxs-lookup"><span data-stu-id="6ff7f-109">Attributes</span></span>

<span data-ttu-id="6ff7f-110">なし。</span><span class="sxs-lookup"><span data-stu-id="6ff7f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6ff7f-111">子要素</span><span class="sxs-lookup"><span data-stu-id="6ff7f-111">Child Elements</span></span>

<span data-ttu-id="6ff7f-112">なし。</span><span class="sxs-lookup"><span data-stu-id="6ff7f-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6ff7f-113">親要素</span><span class="sxs-lookup"><span data-stu-id="6ff7f-113">Parent Elements</span></span>

|<span data-ttu-id="6ff7f-114">要素</span><span class="sxs-lookup"><span data-stu-id="6ff7f-114">Element</span></span>|<span data-ttu-id="6ff7f-115">説明</span><span class="sxs-lookup"><span data-stu-id="6ff7f-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6ff7f-116">GroupBy の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6ff7f-116">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="6ff7f-117">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="6ff7f-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6ff7f-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="6ff7f-118">Text Value</span></span>

<span data-ttu-id="6ff7f-119">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="6ff7f-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="6ff7f-120">解説</span><span class="sxs-lookup"><span data-stu-id="6ff7f-120">Remarks</span></span>

<span data-ttu-id="6ff7f-121">この要素が指定されている場合、 [Firstlinehanging](./firstlinehanging-element-for-frame-for-groupby-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="6ff7f-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ff7f-122">参照</span><span class="sxs-lookup"><span data-stu-id="6ff7f-122">See Also</span></span>

[<span data-ttu-id="6ff7f-123">GroupBy の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6ff7f-123">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="6ff7f-124">GroupBy の CustomItem の Frame 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6ff7f-124">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="6ff7f-125">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="6ff7f-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
