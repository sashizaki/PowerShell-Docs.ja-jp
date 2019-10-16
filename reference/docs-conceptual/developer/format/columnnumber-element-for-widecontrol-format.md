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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364221"
---
# <a name="columnnumber-element-for-widecontrol-format"></a><span data-ttu-id="4fb0c-102">WideControl の ColumnNumber 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4fb0c-102">ColumnNumber Element for WideControl (Format)</span></span>

<span data-ttu-id="4fb0c-103">ワイドビューに表示される列の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4fb0c-103">Specifies the number of columns displayed in the wide view.</span></span>

<span data-ttu-id="4fb0c-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl 要素 (format) WideControl の ColumnNumber 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="4fb0c-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) ColumnNumber Element for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4fb0c-105">構文</span><span class="sxs-lookup"><span data-stu-id="4fb0c-105">Syntax</span></span>

```xml
<ColumnNumber>PositiveInteger</ColumnNumber>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4fb0c-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="4fb0c-106">Attributes and Elements</span></span>

<span data-ttu-id="4fb0c-107">次のセクションでは、属性、子要素、`ColumnNumber` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fb0c-107">The following sections describe attributes, child elements, and the parent element of the `ColumnNumber` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4fb0c-108">属性</span><span class="sxs-lookup"><span data-stu-id="4fb0c-108">Attributes</span></span>

<span data-ttu-id="4fb0c-109">なし。</span><span class="sxs-lookup"><span data-stu-id="4fb0c-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4fb0c-110">子要素</span><span class="sxs-lookup"><span data-stu-id="4fb0c-110">Child Elements</span></span>

<span data-ttu-id="4fb0c-111">なし。</span><span class="sxs-lookup"><span data-stu-id="4fb0c-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4fb0c-112">親要素</span><span class="sxs-lookup"><span data-stu-id="4fb0c-112">Parent Elements</span></span>

|<span data-ttu-id="4fb0c-113">要素</span><span class="sxs-lookup"><span data-stu-id="4fb0c-113">Element</span></span>|<span data-ttu-id="4fb0c-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="4fb0c-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4fb0c-115">WideControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="4fb0c-115">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="4fb0c-116">ビューのワイド (単一値) リスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="4fb0c-116">Defines a wide (single value) list format for the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4fb0c-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="4fb0c-117">Text Value</span></span>

<span data-ttu-id="4fb0c-118">正の整数値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="4fb0c-118">Specify a positive integer value.</span></span>

## <a name="remarks"></a><span data-ttu-id="4fb0c-119">コメント</span><span class="sxs-lookup"><span data-stu-id="4fb0c-119">Remarks</span></span>

<span data-ttu-id="4fb0c-120">ワイドビューを定義する場合は、`AutoSize` 要素または `ColumnNumber` 要素を追加できますが、両方を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="4fb0c-120">When defining a wide view, you can add the `AutoSize` element or the `ColumnNumber` element, but you cannot add both.</span></span>

<span data-ttu-id="4fb0c-121">ワイドビューのコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fb0c-121">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="4fb0c-122">ワイドビューの例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fb0c-122">For an example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4fb0c-123">参照</span><span class="sxs-lookup"><span data-stu-id="4fb0c-123">See Also</span></span>

[<span data-ttu-id="4fb0c-124">WideControl の Autosize 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="4fb0c-124">Autosize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)

[<span data-ttu-id="4fb0c-125">ワイドビューの作成</span><span class="sxs-lookup"><span data-stu-id="4fb0c-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="4fb0c-126">ワイドビュー (基本)</span><span class="sxs-lookup"><span data-stu-id="4fb0c-126">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="4fb0c-127">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="4fb0c-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
