---
ms.date: 09/13/2016
ms.topic: reference
title: WideControl の AutoSize 要素 (書式)
description: WideControl の AutoSize 要素 (書式)
ms.openlocfilehash: 42dfae337ba8805e1ddcff4269401afdb3e281f6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650006"
---
# <a name="autosize-element-for-widecontrol-format"></a><span data-ttu-id="a7883-103">WideControl の AutoSize 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a7883-103">AutoSize Element for WideControl (Format)</span></span>

<span data-ttu-id="a7883-104">データのサイズに基づいて列のサイズと列の数を調整するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7883-104">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>

<span data-ttu-id="a7883-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl 要素 (Format) WideControl の Autosize 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="a7883-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) Autosize Element for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a7883-106">構文</span><span class="sxs-lookup"><span data-stu-id="a7883-106">Syntax</span></span>

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a7883-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a7883-107">Attributes and Elements</span></span>

<span data-ttu-id="a7883-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `AutoSize` ます。</span><span class="sxs-lookup"><span data-stu-id="a7883-108">The following sections describe attributes, child elements, and the parent element of the `AutoSize` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a7883-109">属性</span><span class="sxs-lookup"><span data-stu-id="a7883-109">Attributes</span></span>

<span data-ttu-id="a7883-110">なし。</span><span class="sxs-lookup"><span data-stu-id="a7883-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a7883-111">子要素</span><span class="sxs-lookup"><span data-stu-id="a7883-111">Child Elements</span></span>

<span data-ttu-id="a7883-112">なし</span><span class="sxs-lookup"><span data-stu-id="a7883-112">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a7883-113">親要素</span><span class="sxs-lookup"><span data-stu-id="a7883-113">Parent Elements</span></span>

|<span data-ttu-id="a7883-114">要素</span><span class="sxs-lookup"><span data-stu-id="a7883-114">Element</span></span>|<span data-ttu-id="a7883-115">説明</span><span class="sxs-lookup"><span data-stu-id="a7883-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a7883-116">WideControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a7883-116">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="a7883-117">ビューのワイド (単一値) リスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="a7883-117">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a7883-118">解説</span><span class="sxs-lookup"><span data-stu-id="a7883-118">Remarks</span></span>

<span data-ttu-id="a7883-119">ワイドビューを定義する場合は、 `AutoSize` 要素または [columnnumber](./columnnumber-element-for-widecontrol-format.md) 要素を追加できますが、両方を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="a7883-119">When defining a wide view, you can add the `AutoSize` element or the [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element, but you cannot add both.</span></span>

<span data-ttu-id="a7883-120">ワイドビューのコンポーネントの詳細については、「 [ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7883-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="a7883-121">ワイドビューの例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7883-121">For an example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a7883-122">参照</span><span class="sxs-lookup"><span data-stu-id="a7883-122">See Also</span></span>

[<span data-ttu-id="a7883-123">WideControl の ColumnNumber 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a7883-123">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="a7883-124">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="a7883-124">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="a7883-125">WideControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a7883-125">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="a7883-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="a7883-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
