---
ms.date: 09/13/2016
ms.topic: reference
title: View の CustomControl の CustomEntries 要素 (書式)
description: View の CustomControl の CustomEntries 要素 (書式)
ms.openlocfilehash: 6e757bccdface2503667f8786462a2b43134a07d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649981"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a><span data-ttu-id="cdecc-103">View の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cdecc-103">CustomEntries Element for CustomControl for View (Format)</span></span>

<span data-ttu-id="cdecc-104">カスタムコントロールビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="cdecc-104">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="cdecc-105">カスタムコントロールビューでは、1つまたは複数の定義を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdecc-105">The custom control view must specify one or more definitions.</span></span>

<span data-ttu-id="cdecc-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl Element (Format) CustomControl for View (Format) の CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="cdecc-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cdecc-107">構文</span><span class="sxs-lookup"><span data-stu-id="cdecc-107">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cdecc-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cdecc-108">Attributes and Elements</span></span>

<span data-ttu-id="cdecc-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomControlEntries` ます。</span><span class="sxs-lookup"><span data-stu-id="cdecc-109">The following sections describe attributes, child elements, and the parent element of the `CustomControlEntries` element.</span></span> <span data-ttu-id="cdecc-110">1つまたは複数の子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdecc-110">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="cdecc-111">属性</span><span class="sxs-lookup"><span data-stu-id="cdecc-111">Attributes</span></span>

<span data-ttu-id="cdecc-112">なし。</span><span class="sxs-lookup"><span data-stu-id="cdecc-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cdecc-113">子要素</span><span class="sxs-lookup"><span data-stu-id="cdecc-113">Child Elements</span></span>

|<span data-ttu-id="cdecc-114">要素</span><span class="sxs-lookup"><span data-stu-id="cdecc-114">Element</span></span>|<span data-ttu-id="cdecc-115">説明</span><span class="sxs-lookup"><span data-stu-id="cdecc-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cdecc-116">View (Format) の CustomEntries の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="cdecc-116">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="cdecc-117">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="cdecc-117">Required element.</span></span><br /><br /> <span data-ttu-id="cdecc-118">カスタムコントロールビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="cdecc-118">Provides a definition of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cdecc-119">親要素</span><span class="sxs-lookup"><span data-stu-id="cdecc-119">Parent Elements</span></span>

|<span data-ttu-id="cdecc-120">要素</span><span class="sxs-lookup"><span data-stu-id="cdecc-120">Element</span></span>|<span data-ttu-id="cdecc-121">説明</span><span class="sxs-lookup"><span data-stu-id="cdecc-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cdecc-122">View の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cdecc-122">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)|<span data-ttu-id="cdecc-123">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="cdecc-123">Required element.</span></span><br /><br /> <span data-ttu-id="cdecc-124">ビューのカスタムコントロール形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="cdecc-124">Defines a custom control format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cdecc-125">解説</span><span class="sxs-lookup"><span data-stu-id="cdecc-125">Remarks</span></span>

<span data-ttu-id="cdecc-126">ほとんどの場合、コントロールには定義が1つだけあります。定義は1つの要素で定義されてい `CustomEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="cdecc-126">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="cdecc-127">ただし、同じコントロールを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="cdecc-127">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="cdecc-128">そのような場合は、 `CustomEntry` オブジェクトまたはオブジェクトのセットごとに要素を定義できます。</span><span class="sxs-lookup"><span data-stu-id="cdecc-128">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="cdecc-129">参照</span><span class="sxs-lookup"><span data-stu-id="cdecc-129">See Also</span></span>

[<span data-ttu-id="cdecc-130">View の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cdecc-130">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="cdecc-131">View (Format) の CustomEntries の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="cdecc-131">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="cdecc-132">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="cdecc-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
