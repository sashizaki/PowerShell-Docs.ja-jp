---
ms.date: 09/13/2016
ms.topic: reference
title: WideControl の ColumnNumber 要素 (書式)
description: WideControl の ColumnNumber 要素 (書式)
ms.openlocfilehash: 1ddbbfbd5b53065afcc6c1326d6abf1fadedc67b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648403"
---
# <a name="columnnumber-element-for-widecontrol-format"></a><span data-ttu-id="f0c95-103">WideControl の ColumnNumber 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f0c95-103">ColumnNumber Element for WideControl (Format)</span></span>

<span data-ttu-id="f0c95-104">ワイドビューに表示される列の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0c95-104">Specifies the number of columns displayed in the wide view.</span></span>

<span data-ttu-id="f0c95-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl 要素 (format) WideControl の ColumnNumber 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="f0c95-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) ColumnNumber Element for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f0c95-106">構文</span><span class="sxs-lookup"><span data-stu-id="f0c95-106">Syntax</span></span>

```xml
<ColumnNumber>PositiveInteger</ColumnNumber>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f0c95-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f0c95-107">Attributes and Elements</span></span>

<span data-ttu-id="f0c95-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ColumnNumber` ます。</span><span class="sxs-lookup"><span data-stu-id="f0c95-108">The following sections describe attributes, child elements, and the parent element of the `ColumnNumber` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f0c95-109">属性</span><span class="sxs-lookup"><span data-stu-id="f0c95-109">Attributes</span></span>

<span data-ttu-id="f0c95-110">なし。</span><span class="sxs-lookup"><span data-stu-id="f0c95-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f0c95-111">子要素</span><span class="sxs-lookup"><span data-stu-id="f0c95-111">Child Elements</span></span>

<span data-ttu-id="f0c95-112">なし。</span><span class="sxs-lookup"><span data-stu-id="f0c95-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f0c95-113">親要素</span><span class="sxs-lookup"><span data-stu-id="f0c95-113">Parent Elements</span></span>

|<span data-ttu-id="f0c95-114">要素</span><span class="sxs-lookup"><span data-stu-id="f0c95-114">Element</span></span>|<span data-ttu-id="f0c95-115">説明</span><span class="sxs-lookup"><span data-stu-id="f0c95-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f0c95-116">WideControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f0c95-116">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="f0c95-117">ビューのワイド (単一値) リスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="f0c95-117">Defines a wide (single value) list format for the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f0c95-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="f0c95-118">Text Value</span></span>

<span data-ttu-id="f0c95-119">正の整数値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="f0c95-119">Specify a positive integer value.</span></span>

## <a name="remarks"></a><span data-ttu-id="f0c95-120">解説</span><span class="sxs-lookup"><span data-stu-id="f0c95-120">Remarks</span></span>

<span data-ttu-id="f0c95-121">ワイドビューを定義する場合は、 `AutoSize` 要素または `ColumnNumber` 要素を追加できますが、両方を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="f0c95-121">When defining a wide view, you can add the `AutoSize` element or the `ColumnNumber` element, but you cannot add both.</span></span>

<span data-ttu-id="f0c95-122">ワイドビューのコンポーネントの詳細については、「 [ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0c95-122">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="f0c95-123">ワイドビューの例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0c95-123">For an example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f0c95-124">参照</span><span class="sxs-lookup"><span data-stu-id="f0c95-124">See Also</span></span>

[<span data-ttu-id="f0c95-125">WideControl の Autosize 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="f0c95-125">Autosize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)

[<span data-ttu-id="f0c95-126">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="f0c95-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="f0c95-127">ワイド ビュー (基本)</span><span class="sxs-lookup"><span data-stu-id="f0c95-127">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="f0c95-128">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="f0c95-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
