---
ms.date: 09/13/2016
ms.topic: reference
title: View の Controls の CustomControl の CustomEntries 要素 (書式)
description: View の Controls の CustomControl の CustomEntries 要素 (書式)
ms.openlocfilehash: 43187294a407d08f765f8c42aba25d13dba6d901
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652377"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-view-format"></a><span data-ttu-id="bf477-103">View の Controls の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bf477-103">CustomEntries Element for CustomControl for Controls for View (Format)</span></span>

<span data-ttu-id="bf477-104">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="bf477-104">Provides the definitions for the control.</span></span> <span data-ttu-id="bf477-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf477-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="bf477-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (形式) コントロールのコントロールの要素 (書式) のコントロール要素 (format) のコントロールの CustomControl 要素 (format) のコントロールのコントロール要素 (形式) のコントロールの CustomControl</span><span class="sxs-lookup"><span data-stu-id="bf477-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bf477-107">構文</span><span class="sxs-lookup"><span data-stu-id="bf477-107">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bf477-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bf477-108">Attributes and Elements</span></span>

<span data-ttu-id="bf477-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomEntries` ます。</span><span class="sxs-lookup"><span data-stu-id="bf477-109">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="bf477-110">指定できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="bf477-110">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="bf477-111">属性</span><span class="sxs-lookup"><span data-stu-id="bf477-111">Attributes</span></span>

<span data-ttu-id="bf477-112">なし。</span><span class="sxs-lookup"><span data-stu-id="bf477-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bf477-113">子要素</span><span class="sxs-lookup"><span data-stu-id="bf477-113">Child Elements</span></span>

|<span data-ttu-id="bf477-114">要素</span><span class="sxs-lookup"><span data-stu-id="bf477-114">Element</span></span>|<span data-ttu-id="bf477-115">説明</span><span class="sxs-lookup"><span data-stu-id="bf477-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bf477-116">View の Controls の CustomEntries の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bf477-116">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="bf477-117">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="bf477-117">Required element.</span></span><br /><br /> <span data-ttu-id="bf477-118">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="bf477-118">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bf477-119">親要素</span><span class="sxs-lookup"><span data-stu-id="bf477-119">Parent Elements</span></span>

|<span data-ttu-id="bf477-120">要素</span><span class="sxs-lookup"><span data-stu-id="bf477-120">Element</span></span>|<span data-ttu-id="bf477-121">説明</span><span class="sxs-lookup"><span data-stu-id="bf477-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bf477-122">View の Controls の Control の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bf477-122">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="bf477-123">ビューによって使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="bf477-123">Defines the control used by the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bf477-124">解説</span><span class="sxs-lookup"><span data-stu-id="bf477-124">Remarks</span></span>

<span data-ttu-id="bf477-125">ほとんどの場合、コントロールには定義が1つだけあります。定義は1つの要素で指定され `CustomEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="bf477-125">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="bf477-126">ただし、同じコントロールを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bf477-126">However, it is possible to provide multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="bf477-127">そのような場合は、 `CustomEntry` オブジェクトまたはオブジェクトのセットごとに要素を定義できます。</span><span class="sxs-lookup"><span data-stu-id="bf477-127">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf477-128">参照</span><span class="sxs-lookup"><span data-stu-id="bf477-128">See Also</span></span>

[<span data-ttu-id="bf477-129">View の Controls の CustomEntries の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bf477-129">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="bf477-130">View の Controls の Control の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bf477-130">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="bf477-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="bf477-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
