---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の CustomControl の CustomEntries 要素 (書式)
description: GroupBy の CustomControl の CustomEntries 要素 (書式)
ms.openlocfilehash: cde59d38b83930cb64a3a0040891783e4ab96723
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666792"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="5f4cc-103">GroupBy の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5f4cc-103">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="5f4cc-104">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="5f4cc-104">Provides the definitions for the control.</span></span> <span data-ttu-id="5f4cc-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5f4cc-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="5f4cc-106">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー Element (format) GroupBy 要素の groupby (format) CustomControl 要素を groupby (形式) の CustomControl の CustomEntries 要素に設定します。</span><span class="sxs-lookup"><span data-stu-id="5f4cc-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5f4cc-107">構文</span><span class="sxs-lookup"><span data-stu-id="5f4cc-107">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5f4cc-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5f4cc-108">Attributes and Elements</span></span>

<span data-ttu-id="5f4cc-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomEntries` ます。</span><span class="sxs-lookup"><span data-stu-id="5f4cc-109">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="5f4cc-110">指定できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="5f4cc-110">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="5f4cc-111">属性</span><span class="sxs-lookup"><span data-stu-id="5f4cc-111">Attributes</span></span>

<span data-ttu-id="5f4cc-112">なし。</span><span class="sxs-lookup"><span data-stu-id="5f4cc-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5f4cc-113">子要素</span><span class="sxs-lookup"><span data-stu-id="5f4cc-113">Child Elements</span></span>

|<span data-ttu-id="5f4cc-114">要素</span><span class="sxs-lookup"><span data-stu-id="5f4cc-114">Element</span></span>|<span data-ttu-id="5f4cc-115">説明</span><span class="sxs-lookup"><span data-stu-id="5f4cc-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5f4cc-116">GroupBy の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5f4cc-116">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="5f4cc-117">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="5f4cc-117">Required element.</span></span><br /><br /> <span data-ttu-id="5f4cc-118">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="5f4cc-118">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5f4cc-119">親要素</span><span class="sxs-lookup"><span data-stu-id="5f4cc-119">Parent Elements</span></span>

|<span data-ttu-id="5f4cc-120">要素</span><span class="sxs-lookup"><span data-stu-id="5f4cc-120">Element</span></span>|<span data-ttu-id="5f4cc-121">説明</span><span class="sxs-lookup"><span data-stu-id="5f4cc-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5f4cc-122">GroupBy の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5f4cc-122">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="5f4cc-123">新しいグループを表示するカスタムコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="5f4cc-123">Defines the custom control that displays the new group.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5f4cc-124">解説</span><span class="sxs-lookup"><span data-stu-id="5f4cc-124">Remarks</span></span>

<span data-ttu-id="5f4cc-125">ほとんどの場合、コントロールには定義が1つだけあります。定義は1つの要素で指定され `CustomEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="5f4cc-125">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="5f4cc-126">ただし、同じコントロールを使用して異なるグループを表示する場合は、複数の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5f4cc-126">However, it is possible to provide multiple definitions if you want to use the same control to display different groups.</span></span> <span data-ttu-id="5f4cc-127">そのような場合は、 `CustomEntry` グループの要素を定義できます。</span><span class="sxs-lookup"><span data-stu-id="5f4cc-127">In those cases, you can define a `CustomEntry` element for a group.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f4cc-128">参照</span><span class="sxs-lookup"><span data-stu-id="5f4cc-128">See Also</span></span>

[<span data-ttu-id="5f4cc-129">View の Controls の CustomEntries の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5f4cc-129">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="5f4cc-130">GroupBy の CustomControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5f4cc-130">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="5f4cc-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="5f4cc-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
