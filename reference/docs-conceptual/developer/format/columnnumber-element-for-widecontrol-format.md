---
title: WideControl (Format) の ColumnNumber 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5f151bb0e629efcebe6295cdcae6cebcbbb1b39b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783859"
---
# <a name="columnnumber-element-for-widecontrol-format"></a><span data-ttu-id="87dfb-102">WideControl の ColumnNumber 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="87dfb-102">ColumnNumber Element for WideControl (Format)</span></span>

<span data-ttu-id="87dfb-103">ワイドビューに表示される列の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="87dfb-103">Specifies the number of columns displayed in the wide view.</span></span>

<span data-ttu-id="87dfb-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl 要素 (format) WideControl の ColumnNumber 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="87dfb-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) ColumnNumber Element for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="87dfb-105">構文</span><span class="sxs-lookup"><span data-stu-id="87dfb-105">Syntax</span></span>

```xml
<ColumnNumber>PositiveInteger</ColumnNumber>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="87dfb-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="87dfb-106">Attributes and Elements</span></span>

<span data-ttu-id="87dfb-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `ColumnNumber` ます。</span><span class="sxs-lookup"><span data-stu-id="87dfb-107">The following sections describe attributes, child elements, and the parent element of the `ColumnNumber` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="87dfb-108">属性</span><span class="sxs-lookup"><span data-stu-id="87dfb-108">Attributes</span></span>

<span data-ttu-id="87dfb-109">なし。</span><span class="sxs-lookup"><span data-stu-id="87dfb-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="87dfb-110">子要素</span><span class="sxs-lookup"><span data-stu-id="87dfb-110">Child Elements</span></span>

<span data-ttu-id="87dfb-111">なし。</span><span class="sxs-lookup"><span data-stu-id="87dfb-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="87dfb-112">親要素</span><span class="sxs-lookup"><span data-stu-id="87dfb-112">Parent Elements</span></span>

|<span data-ttu-id="87dfb-113">要素</span><span class="sxs-lookup"><span data-stu-id="87dfb-113">Element</span></span>|<span data-ttu-id="87dfb-114">説明</span><span class="sxs-lookup"><span data-stu-id="87dfb-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="87dfb-115">WideControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="87dfb-115">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="87dfb-116">ビューのワイド (単一値) リスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="87dfb-116">Defines a wide (single value) list format for the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="87dfb-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="87dfb-117">Text Value</span></span>

<span data-ttu-id="87dfb-118">正の整数値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="87dfb-118">Specify a positive integer value.</span></span>

## <a name="remarks"></a><span data-ttu-id="87dfb-119">解説</span><span class="sxs-lookup"><span data-stu-id="87dfb-119">Remarks</span></span>

<span data-ttu-id="87dfb-120">ワイドビューを定義する場合は、 `AutoSize` 要素または `ColumnNumber` 要素を追加できますが、両方を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="87dfb-120">When defining a wide view, you can add the `AutoSize` element or the `ColumnNumber` element, but you cannot add both.</span></span>

<span data-ttu-id="87dfb-121">ワイドビューのコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87dfb-121">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="87dfb-122">ワイドビューの例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87dfb-122">For an example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="87dfb-123">参照</span><span class="sxs-lookup"><span data-stu-id="87dfb-123">See Also</span></span>

[<span data-ttu-id="87dfb-124">WideControl の Autosize 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="87dfb-124">Autosize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)

[<span data-ttu-id="87dfb-125">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="87dfb-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="87dfb-126">ワイド ビュー (基本)</span><span class="sxs-lookup"><span data-stu-id="87dfb-126">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="87dfb-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="87dfb-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
