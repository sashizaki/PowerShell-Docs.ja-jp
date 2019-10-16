---
title: 構成用のコントロールのフレームの FirstLineHanging 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 679c8bcb-b49d-4bb4-91f5-ea1af6c217e3
caps.latest.revision: 8
ms.openlocfilehash: 4553f95e48a2b1440c00b4951bea56376b00628a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363171"
---
# <a name="firstlinehanging-element-for-frame-for-controls-for-configuration-format"></a><span data-ttu-id="7d56d-102">Configuration の Controls の Frame の FirstLineHanging 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7d56d-102">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>

<span data-ttu-id="7d56d-103">データの最初の行を左にシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7d56d-103">Specifies how many characters the first line of data is shifted to the left.</span></span> <span data-ttu-id="7d56d-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7d56d-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="7d56d-105">Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素Format) CustomEntry 要素を使用して CustomControl 用に構成 (format) CustomItem 要素を構成するためのコントロールのための構成 (書式設定) 用の構成フレーム要素を構成するためのコントロール用 CustomItem 要素フレームの FirstLineHanging 要素構成用のコントロール (形式)</span><span class="sxs-lookup"><span data-stu-id="7d56d-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format) FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7d56d-106">構文</span><span class="sxs-lookup"><span data-stu-id="7d56d-106">Syntax</span></span>

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7d56d-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="7d56d-107">Attributes and Elements</span></span>

<span data-ttu-id="7d56d-108">次のセクションでは、`FirstLineHanging` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d56d-108">The following sections describe attributes, child elements, and parent element of the `FirstLineHanging` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7d56d-109">属性</span><span class="sxs-lookup"><span data-stu-id="7d56d-109">Attributes</span></span>

<span data-ttu-id="7d56d-110">なし。</span><span class="sxs-lookup"><span data-stu-id="7d56d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7d56d-111">子要素</span><span class="sxs-lookup"><span data-stu-id="7d56d-111">Child Elements</span></span>

<span data-ttu-id="7d56d-112">なし。</span><span class="sxs-lookup"><span data-stu-id="7d56d-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7d56d-113">親要素</span><span class="sxs-lookup"><span data-stu-id="7d56d-113">Parent Elements</span></span>

|<span data-ttu-id="7d56d-114">要素</span><span class="sxs-lookup"><span data-stu-id="7d56d-114">Element</span></span>|<span data-ttu-id="7d56d-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="7d56d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7d56d-116">構成用のコントロールの CustomItem の Frame 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7d56d-116">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="7d56d-117">データを左右に移動するなど、データの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="7d56d-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7d56d-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="7d56d-118">Text Value</span></span>

<span data-ttu-id="7d56d-119">データの最初の行をシフトする文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7d56d-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="7d56d-120">コメント</span><span class="sxs-lookup"><span data-stu-id="7d56d-120">Remarks</span></span>

<span data-ttu-id="7d56d-121">この要素が指定されている場合、`FirstLineIndent` 要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="7d56d-121">If this element is specified, you cannot specify the `FirstLineIndent` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d56d-122">参照</span><span class="sxs-lookup"><span data-stu-id="7d56d-122">See Also</span></span>

[<span data-ttu-id="7d56d-123">構成用のコントロールの CustomItem の Frame 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7d56d-123">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="7d56d-124">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="7d56d-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
