---
title: GroupBy (Format) の Frame の FirstLineIndent 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33be3b9e-53c8-433f-8c11-c65b0d46744c
caps.latest.revision: 6
ms.openlocfilehash: 9ba6fc1b9924a4b0d5b56ee15290a2293217403c
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363081"
---
# <a name="firstlineindent-element-for-frame-for-groupby-format"></a><span data-ttu-id="8f260-102">GroupBy の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8f260-102">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>

<span data-ttu-id="8f260-103">データの最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f260-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="8f260-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f260-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="8f260-105">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素CustomControl for groupby (format) CustomItem 要素の CustomEntry for groupby (書式) の Frame 要素の CustomItem for groupby (format) のフレームの FirstLineIndent 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="8f260-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format) FirstLineIndent Element for Frame for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8f260-106">構文</span><span class="sxs-lookup"><span data-stu-id="8f260-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8f260-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="8f260-107">Attributes and Elements</span></span>

<span data-ttu-id="8f260-108">次のセクションでは、`FirstLineIndent` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8f260-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8f260-109">属性</span><span class="sxs-lookup"><span data-stu-id="8f260-109">Attributes</span></span>

<span data-ttu-id="8f260-110">なし。</span><span class="sxs-lookup"><span data-stu-id="8f260-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8f260-111">子要素</span><span class="sxs-lookup"><span data-stu-id="8f260-111">Child Elements</span></span>

<span data-ttu-id="8f260-112">なし。</span><span class="sxs-lookup"><span data-stu-id="8f260-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8f260-113">親要素</span><span class="sxs-lookup"><span data-stu-id="8f260-113">Parent Elements</span></span>

|<span data-ttu-id="8f260-114">要素</span><span class="sxs-lookup"><span data-stu-id="8f260-114">Element</span></span>|<span data-ttu-id="8f260-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="8f260-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8f260-116">GroupBy (Format) の CustomItem の Frame 要素</span><span class="sxs-lookup"><span data-stu-id="8f260-116">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="8f260-117">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="8f260-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8f260-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="8f260-118">Text Value</span></span>

<span data-ttu-id="8f260-119">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f260-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="8f260-120">コメント</span><span class="sxs-lookup"><span data-stu-id="8f260-120">Remarks</span></span>

<span data-ttu-id="8f260-121">この要素が指定されている場合、 [Firstlinehanging](./firstlinehanging-element-for-frame-for-groupby-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="8f260-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f260-122">参照</span><span class="sxs-lookup"><span data-stu-id="8f260-122">See Also</span></span>

[<span data-ttu-id="8f260-123">GroupBy (Format) の Frame の FirstLineHanging 要素</span><span class="sxs-lookup"><span data-stu-id="8f260-123">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="8f260-124">GroupBy (Format) の CustomItem の Frame 要素</span><span class="sxs-lookup"><span data-stu-id="8f260-124">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="8f260-125">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="8f260-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
