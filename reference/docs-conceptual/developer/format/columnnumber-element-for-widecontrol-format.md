---
title: WideControl (Format) の ColumnNumber 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe9eb5f9-a193-41a4-ad47-a96ba3f8d7e3
caps.latest.revision: 8
ms.openlocfilehash: 49f501538b8f72777984a5e575b999866abcdebf
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364221"
---
# <a name="columnnumber-element-for-widecontrol-format"></a><span data-ttu-id="cb459-102">WideControl の ColumnNumber 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cb459-102">ColumnNumber Element for WideControl (Format)</span></span>

<span data-ttu-id="cb459-103">ワイドビューに表示される列の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="cb459-103">Specifies the number of columns displayed in the wide view.</span></span>

<span data-ttu-id="cb459-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl 要素 (format) WideControl の ColumnNumber 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="cb459-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) ColumnNumber Element for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cb459-105">構文</span><span class="sxs-lookup"><span data-stu-id="cb459-105">Syntax</span></span>

```xml
<ColumnNumber>PositiveInteger</ColumnNumber>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cb459-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="cb459-106">Attributes and Elements</span></span>

<span data-ttu-id="cb459-107">次のセクションでは、`ColumnNumber` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cb459-107">The following sections describe attributes, child elements, and the parent element of the `ColumnNumber` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cb459-108">属性</span><span class="sxs-lookup"><span data-stu-id="cb459-108">Attributes</span></span>

<span data-ttu-id="cb459-109">なし。</span><span class="sxs-lookup"><span data-stu-id="cb459-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cb459-110">子要素</span><span class="sxs-lookup"><span data-stu-id="cb459-110">Child Elements</span></span>

<span data-ttu-id="cb459-111">なし。</span><span class="sxs-lookup"><span data-stu-id="cb459-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cb459-112">親要素</span><span class="sxs-lookup"><span data-stu-id="cb459-112">Parent Elements</span></span>

|<span data-ttu-id="cb459-113">要素</span><span class="sxs-lookup"><span data-stu-id="cb459-113">Element</span></span>|<span data-ttu-id="cb459-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="cb459-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cb459-115">WideControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="cb459-115">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="cb459-116">ビューのワイド (単一値) リスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="cb459-116">Defines a wide (single value) list format for the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="cb459-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="cb459-117">Text Value</span></span>

<span data-ttu-id="cb459-118">正の整数値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="cb459-118">Specify a positive integer value.</span></span>

## <a name="remarks"></a><span data-ttu-id="cb459-119">コメント</span><span class="sxs-lookup"><span data-stu-id="cb459-119">Remarks</span></span>

<span data-ttu-id="cb459-120">ワイドビューを定義する場合は、`AutoSize` 要素または `ColumnNumber` 要素を追加できますが、両方を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="cb459-120">When defining a wide view, you can add the `AutoSize` element or the `ColumnNumber` element, but you cannot add both.</span></span>

<span data-ttu-id="cb459-121">ワイドビューのコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb459-121">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="cb459-122">ワイドビューの例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb459-122">For an example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cb459-123">参照</span><span class="sxs-lookup"><span data-stu-id="cb459-123">See Also</span></span>

[<span data-ttu-id="cb459-124">WideControl の Autosize 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="cb459-124">Autosize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)

[<span data-ttu-id="cb459-125">ワイドビューの作成</span><span class="sxs-lookup"><span data-stu-id="cb459-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="cb459-126">ワイドビュー (基本)</span><span class="sxs-lookup"><span data-stu-id="cb459-126">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="cb459-127">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="cb459-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
