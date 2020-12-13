---
ms.date: 09/13/2016
ms.topic: reference
title: WideControl 要素 (書式)
description: WideControl 要素 (書式)
ms.openlocfilehash: f88e1ce18f87e5e47de473298b3ecf070b71c192
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651264"
---
# <a name="widecontrol-element-format"></a><span data-ttu-id="aae9d-103">WideControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="aae9d-103">WideControl Element (Format)</span></span>

<span data-ttu-id="aae9d-104">ビューのワイド (単一値) リスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="aae9d-104">Defines a wide (single value) list format for the view.</span></span> <span data-ttu-id="aae9d-105">このビューには、各オブジェクトの1つのプロパティ値またはスクリプト値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aae9d-105">This view displays a single property value or script value for each object.</span></span>

<span data-ttu-id="aae9d-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="aae9d-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="aae9d-107">構文</span><span class="sxs-lookup"><span data-stu-id="aae9d-107">Syntax</span></span>

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber>PositiveInteger</ColumnNumber>
  <WideEntries>...</WideEntries>
</WideControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="aae9d-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="aae9d-108">Attributes and Elements</span></span>

<span data-ttu-id="aae9d-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `WideControl` ます。</span><span class="sxs-lookup"><span data-stu-id="aae9d-109">The following sections describe the attributes, child elements, and parent element of the `WideControl` element.</span></span> <span data-ttu-id="aae9d-110">との各 `AutoSize` 要素を同時に指定することはできません `ColumnNumber` 。</span><span class="sxs-lookup"><span data-stu-id="aae9d-110">You cannot specify the `AutoSize` and `ColumnNumber` elements at the same time.</span></span>

### <a name="attributes"></a><span data-ttu-id="aae9d-111">属性</span><span class="sxs-lookup"><span data-stu-id="aae9d-111">Attributes</span></span>

<span data-ttu-id="aae9d-112">なし。</span><span class="sxs-lookup"><span data-stu-id="aae9d-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="aae9d-113">子要素</span><span class="sxs-lookup"><span data-stu-id="aae9d-113">Child Elements</span></span>

|<span data-ttu-id="aae9d-114">要素</span><span class="sxs-lookup"><span data-stu-id="aae9d-114">Element</span></span>|<span data-ttu-id="aae9d-115">説明</span><span class="sxs-lookup"><span data-stu-id="aae9d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aae9d-116">WideControl の AutoSize 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="aae9d-116">AutoSize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)|<span data-ttu-id="aae9d-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="aae9d-117">Optional element.</span></span><br /><br /> <span data-ttu-id="aae9d-118">データのサイズに基づいて列のサイズと列の数を調整するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="aae9d-118">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="aae9d-119">WideControl の ColumnNumber 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="aae9d-119">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)|<span data-ttu-id="aae9d-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="aae9d-120">Optional element.</span></span><br /><br /> <span data-ttu-id="aae9d-121">ワイドビューに表示される列の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="aae9d-121">Specifies the number of columns displayed in the wide view.</span></span>|
|[<span data-ttu-id="aae9d-122">WideEntries 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="aae9d-122">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="aae9d-123">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="aae9d-123">Required element.</span></span><br /><br /> <span data-ttu-id="aae9d-124">ワイドビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="aae9d-124">Provides the definitions of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="aae9d-125">親要素</span><span class="sxs-lookup"><span data-stu-id="aae9d-125">Parent Elements</span></span>

|<span data-ttu-id="aae9d-126">要素</span><span class="sxs-lookup"><span data-stu-id="aae9d-126">Element</span></span>|<span data-ttu-id="aae9d-127">説明</span><span class="sxs-lookup"><span data-stu-id="aae9d-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aae9d-128">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="aae9d-128">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="aae9d-129">1つ以上の .NET オブジェクトを表示するために使用されるビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="aae9d-129">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="aae9d-130">解説</span><span class="sxs-lookup"><span data-stu-id="aae9d-130">Remarks</span></span>

<span data-ttu-id="aae9d-131">ワイドビューを定義する場合 `AutoSize` は、要素またはを追加でき `ColumnNumber` ますが、両方を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="aae9d-131">When defining a wide view, you can add the `AutoSize` element or the `ColumnNumber` but you cannot add both.</span></span>

<span data-ttu-id="aae9d-132">ほとんどの場合、ワイドビューごとに1つの定義のみが必要ですが、同じビューを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="aae9d-132">In most cases, only one definition is required for each wide view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="aae9d-133">このような場合は、オブジェクトまたはオブジェクトのセットごとに個別の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="aae9d-133">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

<span data-ttu-id="aae9d-134">ワイドビューのコンポーネントの詳細については、「 [ワイドビューコンポーネント](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aae9d-134">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="aae9d-135">例</span><span class="sxs-lookup"><span data-stu-id="aae9d-135">Example</span></span>

<span data-ttu-id="aae9d-136">次の例は、 `WideControl` system.object オブジェクトのプロパティを表示するために使用[](/dotnet/api/System.Diagnostics.Process)される要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="aae9d-136">The following example shows a `WideControl` element that is used to display a property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

<span data-ttu-id="aae9d-137">ワイドビューの完全な例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aae9d-137">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="aae9d-138">参照</span><span class="sxs-lookup"><span data-stu-id="aae9d-138">See Also</span></span>

[<span data-ttu-id="aae9d-139">WideControl の Autosize 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="aae9d-139">Autosize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)

[<span data-ttu-id="aae9d-140">WideControl の ColumnNumber 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="aae9d-140">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="aae9d-141">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="aae9d-141">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="aae9d-142">WideEntries 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="aae9d-142">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="aae9d-143">ワイド ビュー (基本)</span><span class="sxs-lookup"><span data-stu-id="aae9d-143">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="aae9d-144">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="aae9d-144">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="aae9d-145">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="aae9d-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
