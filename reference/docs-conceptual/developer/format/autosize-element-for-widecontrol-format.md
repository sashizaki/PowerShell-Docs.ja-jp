---
title: WideControl の AutoSize 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: def37479-7b6e-40cf-bc81-0f7cbc651b31
caps.latest.revision: 11
ms.openlocfilehash: 6dbaef5886a0600bd9fe96dbc8d21f00a674dfcf
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369051"
---
# <a name="autosize-element-for-widecontrol-format"></a><span data-ttu-id="b15fc-102">WideControl の AutoSize 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b15fc-102">AutoSize Element for WideControl (Format)</span></span>

<span data-ttu-id="b15fc-103">データのサイズに基づいて列のサイズと列の数を調整するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b15fc-103">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>

<span data-ttu-id="b15fc-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl 要素 (Format) WideControl の Autosize 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="b15fc-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) Autosize Element for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b15fc-105">構文</span><span class="sxs-lookup"><span data-stu-id="b15fc-105">Syntax</span></span>

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b15fc-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="b15fc-106">Attributes and Elements</span></span>

<span data-ttu-id="b15fc-107">次のセクションでは、属性、子要素、`AutoSize` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b15fc-107">The following sections describe attributes, child elements, and the parent element of the `AutoSize` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b15fc-108">属性</span><span class="sxs-lookup"><span data-stu-id="b15fc-108">Attributes</span></span>

<span data-ttu-id="b15fc-109">なし。</span><span class="sxs-lookup"><span data-stu-id="b15fc-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b15fc-110">子要素</span><span class="sxs-lookup"><span data-stu-id="b15fc-110">Child Elements</span></span>

<span data-ttu-id="b15fc-111">None</span><span class="sxs-lookup"><span data-stu-id="b15fc-111">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b15fc-112">親要素</span><span class="sxs-lookup"><span data-stu-id="b15fc-112">Parent Elements</span></span>

|<span data-ttu-id="b15fc-113">要素</span><span class="sxs-lookup"><span data-stu-id="b15fc-113">Element</span></span>|<span data-ttu-id="b15fc-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="b15fc-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b15fc-115">WideControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="b15fc-115">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="b15fc-116">ビューのワイド (単一値) リスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="b15fc-116">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b15fc-117">コメント</span><span class="sxs-lookup"><span data-stu-id="b15fc-117">Remarks</span></span>

<span data-ttu-id="b15fc-118">ワイドビューを定義する場合は、@no__t 0 要素または[Columnnumber](./columnnumber-element-for-widecontrol-format.md)要素を追加できますが、両方を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="b15fc-118">When defining a wide view, you can add the `AutoSize` element or the [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element, but you cannot add both.</span></span>

<span data-ttu-id="b15fc-119">ワイドビューのコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b15fc-119">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="b15fc-120">ワイドビューの例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b15fc-120">For an example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b15fc-121">参照</span><span class="sxs-lookup"><span data-stu-id="b15fc-121">See Also</span></span>

[<span data-ttu-id="b15fc-122">WideControl の ColumnNumber 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="b15fc-122">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="b15fc-123">ワイドビューの作成</span><span class="sxs-lookup"><span data-stu-id="b15fc-123">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="b15fc-124">WideControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="b15fc-124">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="b15fc-125">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="b15fc-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
