---
title: AutoSize 要素 WideControl (形式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: def37479-7b6e-40cf-bc81-0f7cbc651b31
caps.latest.revision: 11
ms.openlocfilehash: 6dbaef5886a0600bd9fe96dbc8d21f00a674dfcf
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857088"
---
# <a name="autosize-element-for-widecontrol-format"></a><span data-ttu-id="db638-102">WideControl の AutoSize 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="db638-102">AutoSize Element for WideControl (Format)</span></span>

<span data-ttu-id="db638-103">かどうか、列のサイズと列の数が調整のデータのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="db638-103">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>

<span data-ttu-id="db638-104">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) WideControl 要素 (形式) Autosize の構成要素 WideControl (形式)</span><span class="sxs-lookup"><span data-stu-id="db638-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) Autosize Element for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="db638-105">構文</span><span class="sxs-lookup"><span data-stu-id="db638-105">Syntax</span></span>

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="db638-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="db638-106">Attributes and Elements</span></span>

<span data-ttu-id="db638-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`AutoSize`要素。</span><span class="sxs-lookup"><span data-stu-id="db638-107">The following sections describe attributes, child elements, and the parent element of the `AutoSize` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="db638-108">属性</span><span class="sxs-lookup"><span data-stu-id="db638-108">Attributes</span></span>

<span data-ttu-id="db638-109">なし。</span><span class="sxs-lookup"><span data-stu-id="db638-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="db638-110">子要素</span><span class="sxs-lookup"><span data-stu-id="db638-110">Child Elements</span></span>

<span data-ttu-id="db638-111">None</span><span class="sxs-lookup"><span data-stu-id="db638-111">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="db638-112">親要素</span><span class="sxs-lookup"><span data-stu-id="db638-112">Parent Elements</span></span>

|<span data-ttu-id="db638-113">要素</span><span class="sxs-lookup"><span data-stu-id="db638-113">Element</span></span>|<span data-ttu-id="db638-114">説明</span><span class="sxs-lookup"><span data-stu-id="db638-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="db638-115">WideControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="db638-115">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="db638-116">ワイド (1 つの値) を定義するビューの一覧の形式。</span><span class="sxs-lookup"><span data-stu-id="db638-116">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="db638-117">コメント</span><span class="sxs-lookup"><span data-stu-id="db638-117">Remarks</span></span>

<span data-ttu-id="db638-118">ワイド ビューを定義するときに追加できます、`AutoSize`要素、または[ColumnNumber](./columnnumber-element-for-widecontrol-format.md)は、要素は両方で追加できません。</span><span class="sxs-lookup"><span data-stu-id="db638-118">When defining a wide view, you can add the `AutoSize` element or the [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element, but you cannot add both.</span></span>

<span data-ttu-id="db638-119">ワイド ビューのコンポーネントに関する詳細については、次を参照してください。[ワイド ビューを作成する](./creating-a-wide-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="db638-119">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="db638-120">ワイド ビューの例は、次を参照してください。[表示 (Basic) の幅が広い](./wide-view-basic.md)します。</span><span class="sxs-lookup"><span data-stu-id="db638-120">For an example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="db638-121">参照</span><span class="sxs-lookup"><span data-stu-id="db638-121">See Also</span></span>

[<span data-ttu-id="db638-122">ColumnNumber 要素 WideControl (形式)</span><span class="sxs-lookup"><span data-stu-id="db638-122">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="db638-123">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="db638-123">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="db638-124">WideControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="db638-124">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="db638-125">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="db638-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
