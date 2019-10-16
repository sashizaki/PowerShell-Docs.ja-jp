---
title: WideControl の WideEntries 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c4bff45-0960-4b3a-95e7-47f2cee03ac5
caps.latest.revision: 12
ms.openlocfilehash: 083f3c8df8136858e32778ed231943ef983e47aa
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361431"
---
# <a name="wideentries-element-for-widecontrol-format"></a><span data-ttu-id="6e3d6-102">WideControl の WideEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6e3d6-102">WideEntries Element for WideControl (Format)</span></span>

<span data-ttu-id="6e3d6-103">ワイドビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="6e3d6-103">Provides the definitions of the wide view.</span></span> <span data-ttu-id="6e3d6-104">ワイドビューでは、1つまたは複数の定義を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e3d6-104">The wide view must specify one or more definitions.</span></span>

<span data-ttu-id="6e3d6-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl 要素 (format) WideEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="6e3d6-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6e3d6-106">構文</span><span class="sxs-lookup"><span data-stu-id="6e3d6-106">Syntax</span></span>

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="6e3d6-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="6e3d6-107">Attributes and Elements</span></span>

<span data-ttu-id="6e3d6-108">次のセクションでは、`WideEntries` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e3d6-108">The following sections describe the attributes, child elements, and parent element of the `WideEntries` element.</span></span> <span data-ttu-id="6e3d6-109">少なくとも1つの子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e3d6-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="6e3d6-110">属性</span><span class="sxs-lookup"><span data-stu-id="6e3d6-110">Attributes</span></span>

<span data-ttu-id="6e3d6-111">なし。</span><span class="sxs-lookup"><span data-stu-id="6e3d6-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6e3d6-112">子要素</span><span class="sxs-lookup"><span data-stu-id="6e3d6-112">Child Elements</span></span>

|<span data-ttu-id="6e3d6-113">要素</span><span class="sxs-lookup"><span data-stu-id="6e3d6-113">Element</span></span>|<span data-ttu-id="6e3d6-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="6e3d6-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6e3d6-115">WideEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="6e3d6-115">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="6e3d6-116">ワイドビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="6e3d6-116">Provides a definition of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6e3d6-117">親要素</span><span class="sxs-lookup"><span data-stu-id="6e3d6-117">Parent Elements</span></span>

|<span data-ttu-id="6e3d6-118">要素</span><span class="sxs-lookup"><span data-stu-id="6e3d6-118">Element</span></span>|<span data-ttu-id="6e3d6-119">[説明]</span><span class="sxs-lookup"><span data-stu-id="6e3d6-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6e3d6-120">WideControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="6e3d6-120">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="6e3d6-121">ビューのワイド (単一値) リスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="6e3d6-121">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6e3d6-122">コメント</span><span class="sxs-lookup"><span data-stu-id="6e3d6-122">Remarks</span></span>

<span data-ttu-id="6e3d6-123">ワイドビューは、オブジェクトごとに1つのプロパティ値またはスクリプト値を表示するリスト形式です。</span><span class="sxs-lookup"><span data-stu-id="6e3d6-123">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="6e3d6-124">ワイドビューのコンポーネントの詳細については、「[ワイドビューコンポーネント](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e3d6-124">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="6e3d6-125">例</span><span class="sxs-lookup"><span data-stu-id="6e3d6-125">Example</span></span>

<span data-ttu-id="6e3d6-126">次の例は、1つの @no__t 1 つの要素を定義する @no__t 0 の要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="6e3d6-126">The following example shows a `WideEntries` element that defines a single `WideEntry` element.</span></span> <span data-ttu-id="6e3d6-127">@No__t-0 要素には、ビューに表示されるプロパティまたはスクリプトの値を定義する1つの @no__t 要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e3d6-127">The `WideEntry` element contains a single `WideItem` element that defines what property or script value is displayed in the view.</span></span>

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="6e3d6-128">ワイドビューの完全な例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e3d6-128">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6e3d6-129">参照</span><span class="sxs-lookup"><span data-stu-id="6e3d6-129">See Also</span></span>

[<span data-ttu-id="6e3d6-130">ワイドビューの作成</span><span class="sxs-lookup"><span data-stu-id="6e3d6-130">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="6e3d6-131">WideControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="6e3d6-131">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="6e3d6-132">WideEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="6e3d6-132">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="6e3d6-133">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="6e3d6-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
