---
title: WideControl 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715ea055-037b-46ad-b70f-87b3f5134403
caps.latest.revision: 14
ms.openlocfilehash: 2742be0389a1bf04af100a490a59c0d938165811
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367991"
---
# <a name="widecontrol-element-format"></a><span data-ttu-id="90430-102">WideControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="90430-102">WideControl Element (Format)</span></span>

<span data-ttu-id="90430-103">ビューのワイド (単一値) リスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="90430-103">Defines a wide (single value) list format for the view.</span></span> <span data-ttu-id="90430-104">このビューには、各オブジェクトの1つのプロパティ値またはスクリプト値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90430-104">This view displays a single property value or script value for each object.</span></span>

<span data-ttu-id="90430-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="90430-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="90430-106">構文</span><span class="sxs-lookup"><span data-stu-id="90430-106">Syntax</span></span>

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber>PositiveInteger</ColumnNumber>
  <WideEntries>...</WideEntries>
</WideControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="90430-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="90430-107">Attributes and Elements</span></span>

<span data-ttu-id="90430-108">次のセクションでは、`WideControl` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="90430-108">The following sections describe the attributes, child elements, and parent element of the `WideControl` element.</span></span> <span data-ttu-id="90430-109">@No__t-0 と `ColumnNumber` の要素を同時に指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="90430-109">You cannot specify the `AutoSize` and `ColumnNumber` elements at the same time.</span></span>

### <a name="attributes"></a><span data-ttu-id="90430-110">属性</span><span class="sxs-lookup"><span data-stu-id="90430-110">Attributes</span></span>

<span data-ttu-id="90430-111">なし。</span><span class="sxs-lookup"><span data-stu-id="90430-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="90430-112">子要素</span><span class="sxs-lookup"><span data-stu-id="90430-112">Child Elements</span></span>

|<span data-ttu-id="90430-113">要素</span><span class="sxs-lookup"><span data-stu-id="90430-113">Element</span></span>|<span data-ttu-id="90430-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="90430-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="90430-115">WideControl の AutoSize 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="90430-115">AutoSize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)|<span data-ttu-id="90430-116">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="90430-116">Optional element.</span></span><br /><br /> <span data-ttu-id="90430-117">データのサイズに基づいて列のサイズと列の数を調整するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="90430-117">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="90430-118">WideControl の ColumnNumber 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="90430-118">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)|<span data-ttu-id="90430-119">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="90430-119">Optional element.</span></span><br /><br /> <span data-ttu-id="90430-120">ワイドビューに表示される列の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="90430-120">Specifies the number of columns displayed in the wide view.</span></span>|
|[<span data-ttu-id="90430-121">WideEntries 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="90430-121">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="90430-122">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="90430-122">Required element.</span></span><br /><br /> <span data-ttu-id="90430-123">ワイドビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="90430-123">Provides the definitions of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="90430-124">親要素</span><span class="sxs-lookup"><span data-stu-id="90430-124">Parent Elements</span></span>

|<span data-ttu-id="90430-125">要素</span><span class="sxs-lookup"><span data-stu-id="90430-125">Element</span></span>|<span data-ttu-id="90430-126">[説明]</span><span class="sxs-lookup"><span data-stu-id="90430-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="90430-127">View 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="90430-127">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="90430-128">1つ以上の .NET オブジェクトを表示するために使用されるビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="90430-128">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="90430-129">コメント</span><span class="sxs-lookup"><span data-stu-id="90430-129">Remarks</span></span>

<span data-ttu-id="90430-130">ワイドビューを定義する場合は、@no__t 0 要素または `ColumnNumber` を追加できますが、両方を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="90430-130">When defining a wide view, you can add the `AutoSize` element or the `ColumnNumber` but you cannot add both.</span></span>

<span data-ttu-id="90430-131">ほとんどの場合、ワイドビューごとに1つの定義のみが必要ですが、同じビューを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="90430-131">In most cases, only one definition is required for each wide view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="90430-132">このような場合は、オブジェクトまたはオブジェクトのセットごとに個別の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="90430-132">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

<span data-ttu-id="90430-133">ワイドビューのコンポーネントの詳細については、「[ワイドビューコンポーネント](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90430-133">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="90430-134">例</span><span class="sxs-lookup"><span data-stu-id="90430-134">Example</span></span>

<span data-ttu-id="90430-135">次の例は、@no__t 0 の要素を示しています。この要素は[、system.object オブジェクト](/dotnet/api/System.Diagnostics.Process)のプロパティを表示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="90430-135">The following example shows a `WideControl` element that is used to display a property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

<span data-ttu-id="90430-136">ワイドビューの完全な例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90430-136">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="90430-137">参照</span><span class="sxs-lookup"><span data-stu-id="90430-137">See Also</span></span>

[<span data-ttu-id="90430-138">WideControl の Autosize 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="90430-138">Autosize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)

[<span data-ttu-id="90430-139">WideControl の ColumnNumber 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="90430-139">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="90430-140">View 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="90430-140">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="90430-141">WideEntries 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="90430-141">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="90430-142">ワイドビュー (基本)</span><span class="sxs-lookup"><span data-stu-id="90430-142">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="90430-143">ワイドビューの作成</span><span class="sxs-lookup"><span data-stu-id="90430-143">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="90430-144">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="90430-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
