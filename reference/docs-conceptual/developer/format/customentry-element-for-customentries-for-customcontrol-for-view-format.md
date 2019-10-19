---
title: CustomControl for ビュー (Format) の CustomEntries の CustomEntry 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac3c0a25-f2ca-4e28-b3dc-9cb06a76d92a
caps.latest.revision: 11
ms.openlocfilehash: 7804155bffeb1f0df8339f797bf59f8def56a3fc
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364021"
---
# <a name="customentry-element-for-customentries-for-customcontrol-for-view-format"></a><span data-ttu-id="e37ac-102">View の CustomControl の CustomEntries の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e37ac-102">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>

<span data-ttu-id="e37ac-103">カスタムコントロールビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="e37ac-103">Provides a definition of the custom control view.</span></span>

<span data-ttu-id="e37ac-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素の CustomControl for view (Format) ビューの Custommentry 要素 for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e37ac-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e37ac-105">構文</span><span class="sxs-lookup"><span data-stu-id="e37ac-105">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e37ac-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="e37ac-106">Attributes and Elements</span></span>

<span data-ttu-id="e37ac-107">次のセクションでは、属性、子要素、`CustomEntry` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e37ac-107">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="e37ac-108">定義によって表示される項目を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e37ac-108">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="e37ac-109">属性</span><span class="sxs-lookup"><span data-stu-id="e37ac-109">Attributes</span></span>

<span data-ttu-id="e37ac-110">なし。</span><span class="sxs-lookup"><span data-stu-id="e37ac-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e37ac-111">子要素</span><span class="sxs-lookup"><span data-stu-id="e37ac-111">Child Elements</span></span>

|<span data-ttu-id="e37ac-112">要素</span><span class="sxs-lookup"><span data-stu-id="e37ac-112">Element</span></span>|<span data-ttu-id="e37ac-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="e37ac-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e37ac-114">CustomEntry for ビューの EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="e37ac-114">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="e37ac-115">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="e37ac-115">Optional element.</span></span><br /><br /> <span data-ttu-id="e37ac-116">カスタムコントロールビューの定義、またはこの定義を使用するために存在する必要がある条件を使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="e37ac-116">Defines the .NET types that use the definition of the custom control view or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="e37ac-117">CustomEntry for ビューの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="e37ac-117">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="e37ac-118">カスタムコントロール定義のコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="e37ac-118">Defines a control for the custom control definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e37ac-119">親要素</span><span class="sxs-lookup"><span data-stu-id="e37ac-119">Parent Elements</span></span>

|<span data-ttu-id="e37ac-120">要素</span><span class="sxs-lookup"><span data-stu-id="e37ac-120">Element</span></span>|<span data-ttu-id="e37ac-121">[説明]</span><span class="sxs-lookup"><span data-stu-id="e37ac-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e37ac-122">CustomControl for View (Format) の CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="e37ac-122">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="e37ac-123">カスタムコントロールビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="e37ac-123">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="e37ac-124">カスタムコントロールビューでは、1つまたは複数の定義を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e37ac-124">The custom control view must specify one or more definitions.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e37ac-125">コメント</span><span class="sxs-lookup"><span data-stu-id="e37ac-125">Remarks</span></span>

<span data-ttu-id="e37ac-126">ほとんどの場合、カスタムコントロールビューごとに1つの定義のみが必要ですが、同じビューを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e37ac-126">In most cases, only one definition is required for each custom control view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="e37ac-127">このような場合は、オブジェクトまたはオブジェクトのセットごとに個別の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e37ac-127">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="e37ac-128">参照</span><span class="sxs-lookup"><span data-stu-id="e37ac-128">See Also</span></span>

[<span data-ttu-id="e37ac-129">View (Format) の CustomControl 要素</span><span class="sxs-lookup"><span data-stu-id="e37ac-129">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="e37ac-130">CustomEntry for ビューの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="e37ac-130">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e37ac-131">CustomEntry for ビューの EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="e37ac-131">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e37ac-132">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="e37ac-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)