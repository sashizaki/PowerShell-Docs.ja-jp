---
title: WideControl (形式) の要素を WideEntries |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c4bff45-0960-4b3a-95e7-47f2cee03ac5
caps.latest.revision: 12
ms.openlocfilehash: 083f3c8df8136858e32778ed231943ef983e47aa
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853278"
---
# <a name="wideentries-element-for-widecontrol-format"></a><span data-ttu-id="0f8c1-102">WideControl の WideEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0f8c1-102">WideEntries Element for WideControl (Format)</span></span>

<span data-ttu-id="0f8c1-103">表示幅が広いの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="0f8c1-103">Provides the definitions of the wide view.</span></span> <span data-ttu-id="0f8c1-104">表示幅が広いには、1 つまたは複数の定義を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f8c1-104">The wide view must specify one or more definitions.</span></span>

<span data-ttu-id="0f8c1-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="0f8c1-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0f8c1-106">構文</span><span class="sxs-lookup"><span data-stu-id="0f8c1-106">Syntax</span></span>

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="0f8c1-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="0f8c1-107">Attributes and Elements</span></span>

<span data-ttu-id="0f8c1-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`WideEntries`要素。</span><span class="sxs-lookup"><span data-stu-id="0f8c1-108">The following sections describe the attributes, child elements, and parent element of the `WideEntries` element.</span></span> <span data-ttu-id="0f8c1-109">少なくとも 1 つの子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f8c1-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="0f8c1-110">属性</span><span class="sxs-lookup"><span data-stu-id="0f8c1-110">Attributes</span></span>

<span data-ttu-id="0f8c1-111">なし。</span><span class="sxs-lookup"><span data-stu-id="0f8c1-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0f8c1-112">子要素</span><span class="sxs-lookup"><span data-stu-id="0f8c1-112">Child Elements</span></span>

|<span data-ttu-id="0f8c1-113">要素</span><span class="sxs-lookup"><span data-stu-id="0f8c1-113">Element</span></span>|<span data-ttu-id="0f8c1-114">説明</span><span class="sxs-lookup"><span data-stu-id="0f8c1-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0f8c1-115">WideEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="0f8c1-115">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="0f8c1-116">ワイド ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="0f8c1-116">Provides a definition of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0f8c1-117">親要素</span><span class="sxs-lookup"><span data-stu-id="0f8c1-117">Parent Elements</span></span>

|<span data-ttu-id="0f8c1-118">要素</span><span class="sxs-lookup"><span data-stu-id="0f8c1-118">Element</span></span>|<span data-ttu-id="0f8c1-119">説明</span><span class="sxs-lookup"><span data-stu-id="0f8c1-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0f8c1-120">WideControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="0f8c1-120">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="0f8c1-121">ワイド (1 つの値) を定義するビューの一覧の形式。</span><span class="sxs-lookup"><span data-stu-id="0f8c1-121">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0f8c1-122">コメント</span><span class="sxs-lookup"><span data-stu-id="0f8c1-122">Remarks</span></span>

<span data-ttu-id="0f8c1-123">ワイド ビューは、1 つのプロパティの値または各オブジェクトのスクリプト値を表示する一覧の形式です。</span><span class="sxs-lookup"><span data-stu-id="0f8c1-123">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="0f8c1-124">ワイド ビューのコンポーネントに関する詳細については、次を参照してください。[ワイド ビュー コンポーネント](./creating-a-wide-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="0f8c1-124">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="0f8c1-125">例</span><span class="sxs-lookup"><span data-stu-id="0f8c1-125">Example</span></span>

<span data-ttu-id="0f8c1-126">次の例は、 `WideEntries` 、1 つを定義する要素`WideEntry`要素。</span><span class="sxs-lookup"><span data-stu-id="0f8c1-126">The following example shows a `WideEntries` element that defines a single `WideEntry` element.</span></span> <span data-ttu-id="0f8c1-127">`WideEntry`要素には、1 つが含まれています。`WideItem`ビューに表示されるどのようなプロパティやスクリプトの値を定義する要素。</span><span class="sxs-lookup"><span data-stu-id="0f8c1-127">The `WideEntry` element contains a single `WideItem` element that defines what property or script value is displayed in the view.</span></span>

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="0f8c1-128">ワイド ビューの完全な例を参照してください。[表示 (Basic) の幅が広い](./wide-view-basic.md)します。</span><span class="sxs-lookup"><span data-stu-id="0f8c1-128">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0f8c1-129">参照</span><span class="sxs-lookup"><span data-stu-id="0f8c1-129">See Also</span></span>

[<span data-ttu-id="0f8c1-130">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f8c1-130">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="0f8c1-131">WideControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="0f8c1-131">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="0f8c1-132">WideEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="0f8c1-132">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="0f8c1-133">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="0f8c1-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
