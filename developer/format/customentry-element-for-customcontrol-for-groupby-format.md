---
title: GroupBy (形式) のカスタム コントロールの要素を CustomEntry |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2987cb45-f646-45d4-b81b-7871e77af36f
caps.latest.revision: 5
ms.openlocfilehash: dcf4f8b2bbd422067ffdf9b3b4972e279e91edf9
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860368"
---
# <a name="customentry-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="92007-102">GroupBy の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="92007-102">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="92007-103">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="92007-103">Provides a definition of the control.</span></span> <span data-ttu-id="92007-104">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="92007-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="92007-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) のカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="92007-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="92007-106">構文</span><span class="sxs-lookup"><span data-stu-id="92007-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="92007-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="92007-107">Attributes and Elements</span></span>

<span data-ttu-id="92007-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomEntry`要素。</span><span class="sxs-lookup"><span data-stu-id="92007-108">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="92007-109">属性</span><span class="sxs-lookup"><span data-stu-id="92007-109">Attributes</span></span>

<span data-ttu-id="92007-110">なし。</span><span class="sxs-lookup"><span data-stu-id="92007-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="92007-111">子要素</span><span class="sxs-lookup"><span data-stu-id="92007-111">Child Elements</span></span>

|<span data-ttu-id="92007-112">要素</span><span class="sxs-lookup"><span data-stu-id="92007-112">Element</span></span>|<span data-ttu-id="92007-113">説明</span><span class="sxs-lookup"><span data-stu-id="92007-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="92007-114">GroupBy (形式) の CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="92007-114">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="92007-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="92007-115">Optional element.</span></span><br /><br /> <span data-ttu-id="92007-116">このコントロールの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="92007-116">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="92007-117">GroupBy (形式) の CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="92007-117">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="92007-118">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="92007-118">Required element.</span></span><br /><br /> <span data-ttu-id="92007-119">コントロールがデータを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="92007-119">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="92007-120">親要素</span><span class="sxs-lookup"><span data-stu-id="92007-120">Parent Elements</span></span>

|<span data-ttu-id="92007-121">要素</span><span class="sxs-lookup"><span data-stu-id="92007-121">Element</span></span>|<span data-ttu-id="92007-122">説明</span><span class="sxs-lookup"><span data-stu-id="92007-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="92007-123">GroupBy (形式) のカスタム コントロールの CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="92007-123">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="92007-124">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="92007-124">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="92007-125">コメント</span><span class="sxs-lookup"><span data-stu-id="92007-125">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="92007-126">参照</span><span class="sxs-lookup"><span data-stu-id="92007-126">See Also</span></span>

[<span data-ttu-id="92007-127">GroupBy (形式) の CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="92007-127">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="92007-128">GroupBy (形式) の CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="92007-128">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="92007-129">GroupBy (形式) のカスタム コントロールの CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="92007-129">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="92007-130">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="92007-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
