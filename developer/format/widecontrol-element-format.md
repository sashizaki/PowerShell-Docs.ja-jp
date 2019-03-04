---
title: WideControl 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715ea055-037b-46ad-b70f-87b3f5134403
caps.latest.revision: 14
ms.openlocfilehash: 2742be0389a1bf04af100a490a59c0d938165811
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859828"
---
# <a name="widecontrol-element-format"></a><span data-ttu-id="76d84-102">WideControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="76d84-102">WideControl Element (Format)</span></span>

<span data-ttu-id="76d84-103">ワイド (1 つの値) を定義するビューの一覧の形式。</span><span class="sxs-lookup"><span data-stu-id="76d84-103">Defines a wide (single value) list format for the view.</span></span> <span data-ttu-id="76d84-104">このビューには、1 つのプロパティの値または各オブジェクトのスクリプトの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="76d84-104">This view displays a single property value or script value for each object.</span></span>

<span data-ttu-id="76d84-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) WideControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="76d84-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="76d84-106">構文</span><span class="sxs-lookup"><span data-stu-id="76d84-106">Syntax</span></span>

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber>PositiveInteger</ColumnNumber>
  <WideEntries>...</WideEntries>
</WideControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="76d84-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="76d84-107">Attributes and Elements</span></span>

<span data-ttu-id="76d84-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`WideControl`要素。</span><span class="sxs-lookup"><span data-stu-id="76d84-108">The following sections describe the attributes, child elements, and parent element of the `WideControl` element.</span></span> <span data-ttu-id="76d84-109">指定することはできません、`AutoSize`と`ColumnNumber`同時要素。</span><span class="sxs-lookup"><span data-stu-id="76d84-109">You cannot specify the `AutoSize` and `ColumnNumber` elements at the same time.</span></span>

### <a name="attributes"></a><span data-ttu-id="76d84-110">属性</span><span class="sxs-lookup"><span data-stu-id="76d84-110">Attributes</span></span>

<span data-ttu-id="76d84-111">なし。</span><span class="sxs-lookup"><span data-stu-id="76d84-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="76d84-112">子要素</span><span class="sxs-lookup"><span data-stu-id="76d84-112">Child Elements</span></span>

|<span data-ttu-id="76d84-113">要素</span><span class="sxs-lookup"><span data-stu-id="76d84-113">Element</span></span>|<span data-ttu-id="76d84-114">説明</span><span class="sxs-lookup"><span data-stu-id="76d84-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="76d84-115">WideControl (形式) の AutoSize 要素</span><span class="sxs-lookup"><span data-stu-id="76d84-115">AutoSize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)|<span data-ttu-id="76d84-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="76d84-116">Optional element.</span></span><br /><br /> <span data-ttu-id="76d84-117">かどうか、列のサイズと列の数が調整のデータのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="76d84-117">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="76d84-118">ColumnNumber 要素 WideControl (形式)</span><span class="sxs-lookup"><span data-stu-id="76d84-118">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)|<span data-ttu-id="76d84-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="76d84-119">Optional element.</span></span><br /><br /> <span data-ttu-id="76d84-120">表示幅が広いに表示される列の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="76d84-120">Specifies the number of columns displayed in the wide view.</span></span>|
|[<span data-ttu-id="76d84-121">WideEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="76d84-121">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="76d84-122">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="76d84-122">Required element.</span></span><br /><br /> <span data-ttu-id="76d84-123">表示幅が広いの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="76d84-123">Provides the definitions of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="76d84-124">親要素</span><span class="sxs-lookup"><span data-stu-id="76d84-124">Parent Elements</span></span>

|<span data-ttu-id="76d84-125">要素</span><span class="sxs-lookup"><span data-stu-id="76d84-125">Element</span></span>|<span data-ttu-id="76d84-126">説明</span><span class="sxs-lookup"><span data-stu-id="76d84-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="76d84-127">ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="76d84-127">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="76d84-128">1 つまたは複数の .NET オブジェクトを表示するために使用するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="76d84-128">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="76d84-129">コメント</span><span class="sxs-lookup"><span data-stu-id="76d84-129">Remarks</span></span>

<span data-ttu-id="76d84-130">ワイド ビューを定義するときに追加できます、`AutoSize`要素、または`ColumnNumber`が、両方を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="76d84-130">When defining a wide view, you can add the `AutoSize` element or the `ColumnNumber` but you cannot add both.</span></span>

<span data-ttu-id="76d84-131">ほとんどの場合、1 つだけ定義が必要ですがワイド ビューごとに、同じビューを使用して、さまざまな .NET オブジェクトを表示する場合、複数の定義を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="76d84-131">In most cases, only one definition is required for each wide view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="76d84-132">その場合の各オブジェクトまたはオブジェクトのセットを別の定義を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="76d84-132">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

<span data-ttu-id="76d84-133">ワイド ビューのコンポーネントに関する詳細については、次を参照してください。[ワイド ビュー コンポーネント](./creating-a-wide-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="76d84-133">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="76d84-134">例</span><span class="sxs-lookup"><span data-stu-id="76d84-134">Example</span></span>

<span data-ttu-id="76d84-135">次の例は、`WideControl`要素のプロパティを表示するために使用される、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="76d84-135">The following example shows a `WideControl` element that is used to display a property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>...</WideEntries>
  </WideControl>
</View>
```

<span data-ttu-id="76d84-136">ワイド ビューの完全な例を参照してください。[表示 (Basic) の幅が広い](./wide-view-basic.md)します。</span><span class="sxs-lookup"><span data-stu-id="76d84-136">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="76d84-137">参照</span><span class="sxs-lookup"><span data-stu-id="76d84-137">See Also</span></span>

[<span data-ttu-id="76d84-138">WideControl (形式) の Autosize 要素</span><span class="sxs-lookup"><span data-stu-id="76d84-138">Autosize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)

[<span data-ttu-id="76d84-139">ColumnNumber 要素 WideControl (形式)</span><span class="sxs-lookup"><span data-stu-id="76d84-139">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="76d84-140">ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="76d84-140">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="76d84-141">WideEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="76d84-141">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="76d84-142">表示幅が広い (Basic)</span><span class="sxs-lookup"><span data-stu-id="76d84-142">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="76d84-143">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="76d84-143">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="76d84-144">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="76d84-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
