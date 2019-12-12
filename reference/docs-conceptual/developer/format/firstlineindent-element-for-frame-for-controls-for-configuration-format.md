---
title: 構成用のコントロールのフレームの FirstLineIndent 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f489720-11f6-4019-940e-07f423d4278d
caps.latest.revision: 6
ms.openlocfilehash: c5b2d971fe1590116f96b024ae8769334768acf2
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363121"
---
# <a name="firstlineindent-element-for-frame-for-controls-for-configuration-format"></a><span data-ttu-id="5c43e-102">Configuration の Controls の Frame の FirstLineIndent 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5c43e-102">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>

<span data-ttu-id="5c43e-103">データの最初の行を右にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c43e-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="5c43e-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5c43e-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="5c43e-105">Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素Format) CustomEntry 要素を使用して、CustomControl for Controls の configuration (書式) CustomItem 要素を構成するためのコントロールの構成要素の構成 (書式設定) 用の構成フレーム要素の構成要素構成用のコントロール (形式)</span><span class="sxs-lookup"><span data-stu-id="5c43e-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format) FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5c43e-106">構文</span><span class="sxs-lookup"><span data-stu-id="5c43e-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5c43e-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="5c43e-107">Attributes and Elements</span></span>

<span data-ttu-id="5c43e-108">次のセクションでは、`FirstLineIndent` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5c43e-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5c43e-109">属性</span><span class="sxs-lookup"><span data-stu-id="5c43e-109">Attributes</span></span>

<span data-ttu-id="5c43e-110">なし。</span><span class="sxs-lookup"><span data-stu-id="5c43e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5c43e-111">子要素</span><span class="sxs-lookup"><span data-stu-id="5c43e-111">Child Elements</span></span>

<span data-ttu-id="5c43e-112">なし。</span><span class="sxs-lookup"><span data-stu-id="5c43e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5c43e-113">親要素</span><span class="sxs-lookup"><span data-stu-id="5c43e-113">Parent Elements</span></span>

|<span data-ttu-id="5c43e-114">要素</span><span class="sxs-lookup"><span data-stu-id="5c43e-114">Element</span></span>|<span data-ttu-id="5c43e-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="5c43e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5c43e-116">構成用のコントロールの CustomItem の Frame 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="5c43e-116">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="5c43e-117">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="5c43e-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5c43e-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="5c43e-118">Text Value</span></span>

<span data-ttu-id="5c43e-119">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c43e-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="5c43e-120">コメント</span><span class="sxs-lookup"><span data-stu-id="5c43e-120">Remarks</span></span>

<span data-ttu-id="5c43e-121">この要素が指定されている場合、 [Firstlinehanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="5c43e-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c43e-122">参照</span><span class="sxs-lookup"><span data-stu-id="5c43e-122">See Also</span></span>

[<span data-ttu-id="5c43e-123">構成対象のコントロールのフレームの FirstLineHanging 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="5c43e-123">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="5c43e-124">構成用のコントロールの CustomItem の Frame 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="5c43e-124">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="5c43e-125">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="5c43e-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
