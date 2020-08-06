---
title: WideControl の AutoSize 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 64e62142738916978b37eb1cd3a73536b0447099
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783876"
---
# <a name="autosize-element-for-widecontrol-format"></a><span data-ttu-id="12da2-102">WideControl の AutoSize 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="12da2-102">AutoSize Element for WideControl (Format)</span></span>

<span data-ttu-id="12da2-103">データのサイズに基づいて列のサイズと列の数を調整するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="12da2-103">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>

<span data-ttu-id="12da2-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl 要素 (Format) WideControl の Autosize 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="12da2-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) Autosize Element for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="12da2-105">構文</span><span class="sxs-lookup"><span data-stu-id="12da2-105">Syntax</span></span>

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="12da2-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="12da2-106">Attributes and Elements</span></span>

<span data-ttu-id="12da2-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `AutoSize` ます。</span><span class="sxs-lookup"><span data-stu-id="12da2-107">The following sections describe attributes, child elements, and the parent element of the `AutoSize` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="12da2-108">属性</span><span class="sxs-lookup"><span data-stu-id="12da2-108">Attributes</span></span>

<span data-ttu-id="12da2-109">なし。</span><span class="sxs-lookup"><span data-stu-id="12da2-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="12da2-110">子要素</span><span class="sxs-lookup"><span data-stu-id="12da2-110">Child Elements</span></span>

<span data-ttu-id="12da2-111">なし</span><span class="sxs-lookup"><span data-stu-id="12da2-111">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="12da2-112">親要素</span><span class="sxs-lookup"><span data-stu-id="12da2-112">Parent Elements</span></span>

|<span data-ttu-id="12da2-113">要素</span><span class="sxs-lookup"><span data-stu-id="12da2-113">Element</span></span>|<span data-ttu-id="12da2-114">説明</span><span class="sxs-lookup"><span data-stu-id="12da2-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="12da2-115">WideControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="12da2-115">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="12da2-116">ビューのワイド (単一値) リスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="12da2-116">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="12da2-117">解説</span><span class="sxs-lookup"><span data-stu-id="12da2-117">Remarks</span></span>

<span data-ttu-id="12da2-118">ワイドビューを定義する場合は、 `AutoSize` 要素または[columnnumber](./columnnumber-element-for-widecontrol-format.md)要素を追加できますが、両方を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="12da2-118">When defining a wide view, you can add the `AutoSize` element or the [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element, but you cannot add both.</span></span>

<span data-ttu-id="12da2-119">ワイドビューのコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12da2-119">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="12da2-120">ワイドビューの例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12da2-120">For an example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="12da2-121">参照</span><span class="sxs-lookup"><span data-stu-id="12da2-121">See Also</span></span>

[<span data-ttu-id="12da2-122">WideControl の ColumnNumber 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="12da2-122">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="12da2-123">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="12da2-123">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="12da2-124">WideControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="12da2-124">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="12da2-125">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="12da2-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
