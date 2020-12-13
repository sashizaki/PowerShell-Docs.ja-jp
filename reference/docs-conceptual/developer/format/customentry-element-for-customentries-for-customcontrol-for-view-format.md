---
ms.date: 09/13/2016
ms.topic: reference
title: View の CustomControl の CustomEntries の CustomEntry 要素 (書式)
description: View の CustomControl の CustomEntries の CustomEntry 要素 (書式)
ms.openlocfilehash: ff481f13e6f16267bdda4c3053faebc96d9a6d3a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646048"
---
# <a name="customentry-element-for-customentries-for-customcontrol-for-view-format"></a><span data-ttu-id="adec9-103">View の CustomControl の CustomEntries の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="adec9-103">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>

<span data-ttu-id="adec9-104">カスタムコントロールビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="adec9-104">Provides a definition of the custom control view.</span></span>

<span data-ttu-id="adec9-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素の CustomControl for view (Format) ビューの Custommentry 要素 for View (Format)</span><span class="sxs-lookup"><span data-stu-id="adec9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="adec9-106">構文</span><span class="sxs-lookup"><span data-stu-id="adec9-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="adec9-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="adec9-107">Attributes and Elements</span></span>

<span data-ttu-id="adec9-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="adec9-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="adec9-109">定義によって表示される項目を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="adec9-109">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="adec9-110">属性</span><span class="sxs-lookup"><span data-stu-id="adec9-110">Attributes</span></span>

<span data-ttu-id="adec9-111">なし。</span><span class="sxs-lookup"><span data-stu-id="adec9-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="adec9-112">子要素</span><span class="sxs-lookup"><span data-stu-id="adec9-112">Child Elements</span></span>

|<span data-ttu-id="adec9-113">要素</span><span class="sxs-lookup"><span data-stu-id="adec9-113">Element</span></span>|<span data-ttu-id="adec9-114">説明</span><span class="sxs-lookup"><span data-stu-id="adec9-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="adec9-115">CustomEntry for ビューの EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="adec9-115">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="adec9-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="adec9-116">Optional element.</span></span><br /><br /> <span data-ttu-id="adec9-117">カスタムコントロールビューの定義、またはこの定義を使用するために存在する必要がある条件を使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="adec9-117">Defines the .NET types that use the definition of the custom control view or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="adec9-118">CustomEntry for ビューの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="adec9-118">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="adec9-119">カスタムコントロール定義のコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="adec9-119">Defines a control for the custom control definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="adec9-120">親要素</span><span class="sxs-lookup"><span data-stu-id="adec9-120">Parent Elements</span></span>

|<span data-ttu-id="adec9-121">要素</span><span class="sxs-lookup"><span data-stu-id="adec9-121">Element</span></span>|<span data-ttu-id="adec9-122">説明</span><span class="sxs-lookup"><span data-stu-id="adec9-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="adec9-123">View の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="adec9-123">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="adec9-124">カスタムコントロールビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="adec9-124">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="adec9-125">カスタムコントロールビューでは、1つまたは複数の定義を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="adec9-125">The custom control view must specify one or more definitions.</span></span>|

## <a name="remarks"></a><span data-ttu-id="adec9-126">解説</span><span class="sxs-lookup"><span data-stu-id="adec9-126">Remarks</span></span>

<span data-ttu-id="adec9-127">ほとんどの場合、カスタムコントロールビューごとに1つの定義のみが必要ですが、同じビューを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="adec9-127">In most cases, only one definition is required for each custom control view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="adec9-128">このような場合は、オブジェクトまたはオブジェクトのセットごとに個別の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="adec9-128">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="adec9-129">参照</span><span class="sxs-lookup"><span data-stu-id="adec9-129">See Also</span></span>

[<span data-ttu-id="adec9-130">View の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="adec9-130">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="adec9-131">CustomEntry for ビューの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="adec9-131">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="adec9-132">CustomEntry for ビューの EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="adec9-132">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="adec9-133">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="adec9-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
