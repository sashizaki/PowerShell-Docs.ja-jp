---
title: GroupBy (Format) の CustomControl の CustomEntries 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af83c0f6-7fdd-4aa0-af12-efc62f632974
caps.latest.revision: 7
ms.openlocfilehash: f073142bf836ae892f161cf8c36ed16c35e311f5
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364091"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="10777-102">GroupBy の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="10777-102">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="10777-103">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="10777-103">Provides the definitions for the control.</span></span> <span data-ttu-id="10777-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="10777-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="10777-105">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー Element (format) GroupBy 要素の groupby (format) CustomControl 要素を groupby (形式) の CustomControl の CustomEntries 要素に設定します。</span><span class="sxs-lookup"><span data-stu-id="10777-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="10777-106">構文</span><span class="sxs-lookup"><span data-stu-id="10777-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="10777-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="10777-107">Attributes and Elements</span></span>

<span data-ttu-id="10777-108">次のセクションでは、`CustomEntries` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="10777-108">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="10777-109">指定できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="10777-109">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="10777-110">属性</span><span class="sxs-lookup"><span data-stu-id="10777-110">Attributes</span></span>

<span data-ttu-id="10777-111">なし。</span><span class="sxs-lookup"><span data-stu-id="10777-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="10777-112">子要素</span><span class="sxs-lookup"><span data-stu-id="10777-112">Child Elements</span></span>

|<span data-ttu-id="10777-113">要素</span><span class="sxs-lookup"><span data-stu-id="10777-113">Element</span></span>|<span data-ttu-id="10777-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="10777-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="10777-115">GroupBy (Format) の CustomControl の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="10777-115">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="10777-116">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="10777-116">Required element.</span></span><br /><br /> <span data-ttu-id="10777-117">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="10777-117">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="10777-118">親要素</span><span class="sxs-lookup"><span data-stu-id="10777-118">Parent Elements</span></span>

|<span data-ttu-id="10777-119">要素</span><span class="sxs-lookup"><span data-stu-id="10777-119">Element</span></span>|<span data-ttu-id="10777-120">[説明]</span><span class="sxs-lookup"><span data-stu-id="10777-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="10777-121">GroupBy (Format) の CustomControl 要素</span><span class="sxs-lookup"><span data-stu-id="10777-121">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="10777-122">新しいグループを表示するカスタムコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="10777-122">Defines the custom control that displays the new group.</span></span>|

## <a name="remarks"></a><span data-ttu-id="10777-123">コメント</span><span class="sxs-lookup"><span data-stu-id="10777-123">Remarks</span></span>

<span data-ttu-id="10777-124">ほとんどの場合、コントロールの定義は1つだけであり、1つの @no__t 0 要素で指定されます。</span><span class="sxs-lookup"><span data-stu-id="10777-124">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="10777-125">ただし、同じコントロールを使用して異なるグループを表示する場合は、複数の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="10777-125">However, it is possible to provide multiple definitions if you want to use the same control to display different groups.</span></span> <span data-ttu-id="10777-126">そのような場合は、グループの @no__t 0 要素を定義できます。</span><span class="sxs-lookup"><span data-stu-id="10777-126">In those cases, you can define a `CustomEntry` element for a group.</span></span>

## <a name="see-also"></a><span data-ttu-id="10777-127">参照</span><span class="sxs-lookup"><span data-stu-id="10777-127">See Also</span></span>

[<span data-ttu-id="10777-128">ビューのコントロール (Format) の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="10777-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="10777-129">GroupBy (Format) の CustomControl 要素</span><span class="sxs-lookup"><span data-stu-id="10777-129">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="10777-130">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="10777-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
