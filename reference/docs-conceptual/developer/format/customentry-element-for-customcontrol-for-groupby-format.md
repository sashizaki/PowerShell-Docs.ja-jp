---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の CustomControl の CustomEntry 要素 (書式)
description: GroupBy の CustomControl の CustomEntry 要素 (書式)
ms.openlocfilehash: 0df2ff9c15308939e6d2552f51e2961bdabc59fb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646066"
---
# <a name="customentry-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="c31e8-103">GroupBy の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c31e8-103">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="c31e8-104">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="c31e8-104">Provides a definition of the control.</span></span> <span data-ttu-id="c31e8-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c31e8-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="c31e8-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素を表示 (format) の CustomControl 要素を groupby (形式) の CustomControl の CustomControl の CustomEntry 要素の groupby (形式)</span><span class="sxs-lookup"><span data-stu-id="c31e8-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c31e8-107">構文</span><span class="sxs-lookup"><span data-stu-id="c31e8-107">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c31e8-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c31e8-108">Attributes and Elements</span></span>

<span data-ttu-id="c31e8-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="c31e8-109">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c31e8-110">属性</span><span class="sxs-lookup"><span data-stu-id="c31e8-110">Attributes</span></span>

<span data-ttu-id="c31e8-111">なし。</span><span class="sxs-lookup"><span data-stu-id="c31e8-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c31e8-112">子要素</span><span class="sxs-lookup"><span data-stu-id="c31e8-112">Child Elements</span></span>

|<span data-ttu-id="c31e8-113">要素</span><span class="sxs-lookup"><span data-stu-id="c31e8-113">Element</span></span>|<span data-ttu-id="c31e8-114">説明</span><span class="sxs-lookup"><span data-stu-id="c31e8-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c31e8-115">GroupBy の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c31e8-115">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="c31e8-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c31e8-116">Optional element.</span></span><br /><br /> <span data-ttu-id="c31e8-117">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="c31e8-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="c31e8-118">GroupBy の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c31e8-118">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="c31e8-119">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="c31e8-119">Required element.</span></span><br /><br /> <span data-ttu-id="c31e8-120">コントロールがデータを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="c31e8-120">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c31e8-121">親要素</span><span class="sxs-lookup"><span data-stu-id="c31e8-121">Parent Elements</span></span>

|<span data-ttu-id="c31e8-122">要素</span><span class="sxs-lookup"><span data-stu-id="c31e8-122">Element</span></span>|<span data-ttu-id="c31e8-123">説明</span><span class="sxs-lookup"><span data-stu-id="c31e8-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c31e8-124">GroupBy の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c31e8-124">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="c31e8-125">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="c31e8-125">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c31e8-126">解説</span><span class="sxs-lookup"><span data-stu-id="c31e8-126">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="c31e8-127">参照</span><span class="sxs-lookup"><span data-stu-id="c31e8-127">See Also</span></span>

[<span data-ttu-id="c31e8-128">GroupBy の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c31e8-128">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="c31e8-129">GroupBy の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c31e8-129">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="c31e8-130">GroupBy の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c31e8-130">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="c31e8-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="c31e8-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
