---
ms.date: 09/13/2016
ms.topic: reference
title: View の CustomControl 要素 (書式)
description: View の CustomControl 要素 (書式)
ms.openlocfilehash: 41352be55f0c03b2eaca0dbe2d7345e7cf804a7c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655461"
---
# <a name="customcontrol-element-for-view-format"></a><span data-ttu-id="17fb1-103">View の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="17fb1-103">CustomControl Element for View (Format)</span></span>

<span data-ttu-id="17fb1-104">ビューのカスタムコントロール形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="17fb1-104">Defines a custom control format for the view.</span></span>

<span data-ttu-id="17fb1-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="17fb1-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="17fb1-106">構文</span><span class="sxs-lookup"><span data-stu-id="17fb1-106">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="17fb1-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="17fb1-107">Attributes and Elements</span></span>

<span data-ttu-id="17fb1-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomControl` ます。</span><span class="sxs-lookup"><span data-stu-id="17fb1-108">The following sections describe attributes, child elements, and the parent element of the `CustomControl` element.</span></span> <span data-ttu-id="17fb1-109">1つの子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17fb1-109">You must specify one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="17fb1-110">属性</span><span class="sxs-lookup"><span data-stu-id="17fb1-110">Attributes</span></span>

<span data-ttu-id="17fb1-111">なし。</span><span class="sxs-lookup"><span data-stu-id="17fb1-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="17fb1-112">子要素</span><span class="sxs-lookup"><span data-stu-id="17fb1-112">Child Elements</span></span>

|<span data-ttu-id="17fb1-113">要素</span><span class="sxs-lookup"><span data-stu-id="17fb1-113">Element</span></span>|<span data-ttu-id="17fb1-114">説明</span><span class="sxs-lookup"><span data-stu-id="17fb1-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="17fb1-115">View の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="17fb1-115">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="17fb1-116">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="17fb1-116">Required element.</span></span><br /><br /> <span data-ttu-id="17fb1-117">カスタムコントロールビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="17fb1-117">Provides the definitions of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="17fb1-118">親要素</span><span class="sxs-lookup"><span data-stu-id="17fb1-118">Parent Elements</span></span>

|<span data-ttu-id="17fb1-119">要素</span><span class="sxs-lookup"><span data-stu-id="17fb1-119">Element</span></span>|<span data-ttu-id="17fb1-120">説明</span><span class="sxs-lookup"><span data-stu-id="17fb1-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="17fb1-121">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="17fb1-121">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="17fb1-122">1つ以上の .NET オブジェクトを表示するために使用されるビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="17fb1-122">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="17fb1-123">解説</span><span class="sxs-lookup"><span data-stu-id="17fb1-123">Remarks</span></span>

<span data-ttu-id="17fb1-124">ほとんどの場合、各コントロールビューに必要な定義は1つだけですが、同じビューを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="17fb1-124">In most cases, only one definition is required for each control view, but it is possible to provide multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="17fb1-125">このような場合は、オブジェクトまたはオブジェクトのセットごとに個別の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="17fb1-125">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="17fb1-126">参照</span><span class="sxs-lookup"><span data-stu-id="17fb1-126">See Also</span></span>

[<span data-ttu-id="17fb1-127">View の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="17fb1-127">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="17fb1-128">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="17fb1-128">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="17fb1-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="17fb1-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
