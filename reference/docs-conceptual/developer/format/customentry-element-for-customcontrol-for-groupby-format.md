---
title: GroupBy (Format) の CustomControl の CustomEntry 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2987cb45-f646-45d4-b81b-7871e77af36f
caps.latest.revision: 5
ms.openlocfilehash: dcf4f8b2bbd422067ffdf9b3b4972e279e91edf9
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364061"
---
# <a name="customentry-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="e9ddf-102">GroupBy の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e9ddf-102">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="e9ddf-103">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-103">Provides a definition of the control.</span></span> <span data-ttu-id="e9ddf-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="e9ddf-105">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素GroupBy (Format) の CustomControl</span><span class="sxs-lookup"><span data-stu-id="e9ddf-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e9ddf-106">構文</span><span class="sxs-lookup"><span data-stu-id="e9ddf-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e9ddf-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="e9ddf-107">Attributes and Elements</span></span>

<span data-ttu-id="e9ddf-108">次のセクションでは、`CustomEntry` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-108">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e9ddf-109">属性</span><span class="sxs-lookup"><span data-stu-id="e9ddf-109">Attributes</span></span>

<span data-ttu-id="e9ddf-110">なし。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e9ddf-111">子要素</span><span class="sxs-lookup"><span data-stu-id="e9ddf-111">Child Elements</span></span>

|<span data-ttu-id="e9ddf-112">要素</span><span class="sxs-lookup"><span data-stu-id="e9ddf-112">Element</span></span>|<span data-ttu-id="e9ddf-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="e9ddf-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e9ddf-114">GroupBy の CustomEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e9ddf-114">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="e9ddf-115">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-115">Optional element.</span></span><br /><br /> <span data-ttu-id="e9ddf-116">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-116">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="e9ddf-117">GroupBy の CustomEntry の CustomItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e9ddf-117">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="e9ddf-118">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-118">Required element.</span></span><br /><br /> <span data-ttu-id="e9ddf-119">コントロールがデータを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-119">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e9ddf-120">親要素</span><span class="sxs-lookup"><span data-stu-id="e9ddf-120">Parent Elements</span></span>

|<span data-ttu-id="e9ddf-121">要素</span><span class="sxs-lookup"><span data-stu-id="e9ddf-121">Element</span></span>|<span data-ttu-id="e9ddf-122">[説明]</span><span class="sxs-lookup"><span data-stu-id="e9ddf-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e9ddf-123">GroupBy (Format) の CustomControl の CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="e9ddf-123">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="e9ddf-124">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-124">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e9ddf-125">コメント</span><span class="sxs-lookup"><span data-stu-id="e9ddf-125">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="e9ddf-126">参照</span><span class="sxs-lookup"><span data-stu-id="e9ddf-126">See Also</span></span>

[<span data-ttu-id="e9ddf-127">GroupBy の CustomEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e9ddf-127">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="e9ddf-128">GroupBy の CustomEntry の CustomItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e9ddf-128">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="e9ddf-129">GroupBy (Format) の CustomControl の CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="e9ddf-129">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="e9ddf-130">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="e9ddf-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
