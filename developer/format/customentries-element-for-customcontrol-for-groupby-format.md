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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066543"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="44d68-102">GroupBy の CustomControl の CustomEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="44d68-102">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="44d68-103">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="44d68-103">Provides the definitions for the control.</span></span> <span data-ttu-id="44d68-104">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="44d68-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="44d68-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) の GroupBy (形式) のカスタム コントロールの GroupBy (形式) CustomEntries 要素のビュー (形式) のカスタム コントロール要素の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="44d68-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="44d68-106">構文</span><span class="sxs-lookup"><span data-stu-id="44d68-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="44d68-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="44d68-107">Attributes and Elements</span></span>

<span data-ttu-id="44d68-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomEntries`要素。</span><span class="sxs-lookup"><span data-stu-id="44d68-108">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="44d68-109">指定できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="44d68-109">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="44d68-110">属性</span><span class="sxs-lookup"><span data-stu-id="44d68-110">Attributes</span></span>

<span data-ttu-id="44d68-111">なし。</span><span class="sxs-lookup"><span data-stu-id="44d68-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="44d68-112">子要素</span><span class="sxs-lookup"><span data-stu-id="44d68-112">Child Elements</span></span>

|<span data-ttu-id="44d68-113">要素</span><span class="sxs-lookup"><span data-stu-id="44d68-113">Element</span></span>|<span data-ttu-id="44d68-114">説明</span><span class="sxs-lookup"><span data-stu-id="44d68-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="44d68-115">GroupBy (形式) のカスタム コントロールの CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="44d68-115">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="44d68-116">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="44d68-116">Required element.</span></span><br /><br /> <span data-ttu-id="44d68-117">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="44d68-117">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="44d68-118">親要素</span><span class="sxs-lookup"><span data-stu-id="44d68-118">Parent Elements</span></span>

|<span data-ttu-id="44d68-119">要素</span><span class="sxs-lookup"><span data-stu-id="44d68-119">Element</span></span>|<span data-ttu-id="44d68-120">説明</span><span class="sxs-lookup"><span data-stu-id="44d68-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="44d68-121">GroupBy (形式) のカスタム コントロール要素</span><span class="sxs-lookup"><span data-stu-id="44d68-121">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="44d68-122">新しいグループを表示するカスタム コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="44d68-122">Defines the custom control that displays the new group.</span></span>|

## <a name="remarks"></a><span data-ttu-id="44d68-123">コメント</span><span class="sxs-lookup"><span data-stu-id="44d68-123">Remarks</span></span>

<span data-ttu-id="44d68-124">ほとんどの場合、コントロールが 1 つの指定された 1 つだけ定義`CustomEntry`要素。</span><span class="sxs-lookup"><span data-stu-id="44d68-124">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="44d68-125">ただし、別のグループを表示する同じコントロールを使用する場合は、複数の定義を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="44d68-125">However, it is possible to provide multiple definitions if you want to use the same control to display different groups.</span></span> <span data-ttu-id="44d68-126">その場合で定義できますを`CustomEntry`グループの要素。</span><span class="sxs-lookup"><span data-stu-id="44d68-126">In those cases, you can define a `CustomEntry` element for a group.</span></span>

## <a name="see-also"></a><span data-ttu-id="44d68-127">参照</span><span class="sxs-lookup"><span data-stu-id="44d68-127">See Also</span></span>

[<span data-ttu-id="44d68-128">コントロールが表示されます (形式) の CustomEntries CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="44d68-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="44d68-129">GroupBy (形式) のカスタム コントロール要素</span><span class="sxs-lookup"><span data-stu-id="44d68-129">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="44d68-130">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="44d68-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
