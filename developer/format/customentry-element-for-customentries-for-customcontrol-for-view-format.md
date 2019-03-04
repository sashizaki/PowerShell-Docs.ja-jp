---
title: ビュー (形式) のカスタム コントロールの CustomEntries CustomEntry 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac3c0a25-f2ca-4e28-b3dc-9cb06a76d92a
caps.latest.revision: 11
ms.openlocfilehash: 7804155bffeb1f0df8339f797bf59f8def56a3fc
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861818"
---
# <a name="customentry-element-for-customentries-for-customcontrol-for-view-format"></a><span data-ttu-id="dc4e0-102">View の CustomControl の CustomEntries の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="dc4e0-102">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>

<span data-ttu-id="dc4e0-103">カスタム コントロールのビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="dc4e0-103">Provides a definition of the custom control view.</span></span>

<span data-ttu-id="dc4e0-104">要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素の表示 (形式) CustomEntries ビュー (形式) CustomEntry 要素のカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="dc4e0-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dc4e0-105">構文</span><span class="sxs-lookup"><span data-stu-id="dc4e0-105">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dc4e0-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="dc4e0-106">Attributes and Elements</span></span>

<span data-ttu-id="dc4e0-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomEntry`要素。</span><span class="sxs-lookup"><span data-stu-id="dc4e0-107">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="dc4e0-108">定義によって表示される項目を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc4e0-108">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="dc4e0-109">属性</span><span class="sxs-lookup"><span data-stu-id="dc4e0-109">Attributes</span></span>

<span data-ttu-id="dc4e0-110">なし。</span><span class="sxs-lookup"><span data-stu-id="dc4e0-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dc4e0-111">子要素</span><span class="sxs-lookup"><span data-stu-id="dc4e0-111">Child Elements</span></span>

|<span data-ttu-id="dc4e0-112">要素</span><span class="sxs-lookup"><span data-stu-id="dc4e0-112">Element</span></span>|<span data-ttu-id="dc4e0-113">説明</span><span class="sxs-lookup"><span data-stu-id="dc4e0-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dc4e0-114">表示 (形式) CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="dc4e0-114">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="dc4e0-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="dc4e0-115">Optional element.</span></span><br /><br /> <span data-ttu-id="dc4e0-116">カスタム コントロールのビューまたはこの定義を使用するのに必要な条件の定義を使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="dc4e0-116">Defines the .NET types that use the definition of the custom control view or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="dc4e0-117">表示 (形式) CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="dc4e0-117">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="dc4e0-118">カスタム コントロールの定義については、コントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="dc4e0-118">Defines a control for the custom control definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="dc4e0-119">親要素</span><span class="sxs-lookup"><span data-stu-id="dc4e0-119">Parent Elements</span></span>

|<span data-ttu-id="dc4e0-120">要素</span><span class="sxs-lookup"><span data-stu-id="dc4e0-120">Element</span></span>|<span data-ttu-id="dc4e0-121">説明</span><span class="sxs-lookup"><span data-stu-id="dc4e0-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dc4e0-122">ビュー (形式) のカスタム コントロールの CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="dc4e0-122">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="dc4e0-123">カスタム コントロールのビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="dc4e0-123">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="dc4e0-124">カスタム コントロールのビューには、1 つまたは複数の定義を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc4e0-124">The custom control view must specify one or more definitions.</span></span>|

## <a name="remarks"></a><span data-ttu-id="dc4e0-125">コメント</span><span class="sxs-lookup"><span data-stu-id="dc4e0-125">Remarks</span></span>

<span data-ttu-id="dc4e0-126">ほとんどの場合、1 つだけ定義が必要ですがカスタム コントロールのビューごとに、同じビューを使用して、さまざまな .NET オブジェクトを表示する場合、複数の定義を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="dc4e0-126">In most cases, only one definition is required for each custom control view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="dc4e0-127">その場合の各オブジェクトまたはオブジェクトのセットを別の定義を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="dc4e0-127">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc4e0-128">参照</span><span class="sxs-lookup"><span data-stu-id="dc4e0-128">See Also</span></span>

[<span data-ttu-id="dc4e0-129">カスタム コントロールの要素のビュー (形式)</span><span class="sxs-lookup"><span data-stu-id="dc4e0-129">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="dc4e0-130">表示 (形式) CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="dc4e0-130">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="dc4e0-131">表示 (形式) CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="dc4e0-131">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="dc4e0-132">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="dc4e0-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
