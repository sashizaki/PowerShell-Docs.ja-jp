---
title: GroupBy (形式) のカスタム コントロールの要素を CustomEntries |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af83c0f6-7fdd-4aa0-af12-efc62f632974
caps.latest.revision: 7
ms.openlocfilehash: f073142bf836ae892f161cf8c36ed16c35e311f5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853678"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="50428-102">GroupBy の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="50428-102">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="50428-103">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="50428-103">Provides the definitions for the control.</span></span> <span data-ttu-id="50428-104">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="50428-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="50428-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) の GroupBy (形式) のカスタム コントロールの GroupBy (形式) CustomEntries 要素のビュー (形式) のカスタム コントロール要素の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="50428-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="50428-106">構文</span><span class="sxs-lookup"><span data-stu-id="50428-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="50428-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="50428-107">Attributes and Elements</span></span>

<span data-ttu-id="50428-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomEntries`要素。</span><span class="sxs-lookup"><span data-stu-id="50428-108">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="50428-109">指定できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="50428-109">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="50428-110">属性</span><span class="sxs-lookup"><span data-stu-id="50428-110">Attributes</span></span>

<span data-ttu-id="50428-111">なし。</span><span class="sxs-lookup"><span data-stu-id="50428-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="50428-112">子要素</span><span class="sxs-lookup"><span data-stu-id="50428-112">Child Elements</span></span>

|<span data-ttu-id="50428-113">要素</span><span class="sxs-lookup"><span data-stu-id="50428-113">Element</span></span>|<span data-ttu-id="50428-114">説明</span><span class="sxs-lookup"><span data-stu-id="50428-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="50428-115">GroupBy (形式) のカスタム コントロールの CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="50428-115">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="50428-116">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="50428-116">Required element.</span></span><br /><br /> <span data-ttu-id="50428-117">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="50428-117">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="50428-118">親要素</span><span class="sxs-lookup"><span data-stu-id="50428-118">Parent Elements</span></span>

|<span data-ttu-id="50428-119">要素</span><span class="sxs-lookup"><span data-stu-id="50428-119">Element</span></span>|<span data-ttu-id="50428-120">説明</span><span class="sxs-lookup"><span data-stu-id="50428-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="50428-121">GroupBy (形式) のカスタム コントロール要素</span><span class="sxs-lookup"><span data-stu-id="50428-121">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="50428-122">新しいグループを表示するカスタム コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="50428-122">Defines the custom control that displays the new group.</span></span>|

## <a name="remarks"></a><span data-ttu-id="50428-123">コメント</span><span class="sxs-lookup"><span data-stu-id="50428-123">Remarks</span></span>

<span data-ttu-id="50428-124">ほとんどの場合、コントロールが 1 つの指定された 1 つだけ定義`CustomEntry`要素。</span><span class="sxs-lookup"><span data-stu-id="50428-124">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="50428-125">ただし、別のグループを表示する同じコントロールを使用する場合は、複数の定義を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="50428-125">However, it is possible to provide multiple definitions if you want to use the same control to display different groups.</span></span> <span data-ttu-id="50428-126">その場合で定義できますを`CustomEntry`グループの要素。</span><span class="sxs-lookup"><span data-stu-id="50428-126">In those cases, you can define a `CustomEntry` element for a group.</span></span>

## <a name="see-also"></a><span data-ttu-id="50428-127">参照</span><span class="sxs-lookup"><span data-stu-id="50428-127">See Also</span></span>

[<span data-ttu-id="50428-128">コントロールが表示されます (形式) の CustomEntries CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="50428-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="50428-129">GroupBy (形式) のカスタム コントロール要素</span><span class="sxs-lookup"><span data-stu-id="50428-129">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="50428-130">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="50428-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
