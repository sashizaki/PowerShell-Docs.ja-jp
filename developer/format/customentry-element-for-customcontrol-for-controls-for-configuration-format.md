---
title: 構成 (形式) のコントロールのカスタム コントロールの要素を CustomEntry |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9dfba86f-29b2-473c-9e98-9d679176acce
caps.latest.revision: 11
ms.openlocfilehash: 497485a388d1cdc834ecc1d1079b0714a7d7f9db
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066474"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="9f6b3-102">Configuration の Controls の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9f6b3-102">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="9f6b3-103">コモン コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="9f6b3-103">Provides a definition of the common control.</span></span> <span data-ttu-id="9f6b3-104">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="9f6b3-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="9f6b3-105">構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素構成 (形式) のコントロールのカスタム コントロールの形式) CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="9f6b3-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9f6b3-106">構文</span><span class="sxs-lookup"><span data-stu-id="9f6b3-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="9f6b3-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9f6b3-107">Attributes and Elements</span></span>

<span data-ttu-id="9f6b3-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomEntry`要素。</span><span class="sxs-lookup"><span data-stu-id="9f6b3-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="9f6b3-109">定義によって表示される項目を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f6b3-109">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="9f6b3-110">属性</span><span class="sxs-lookup"><span data-stu-id="9f6b3-110">Attributes</span></span>

<span data-ttu-id="9f6b3-111">なし。</span><span class="sxs-lookup"><span data-stu-id="9f6b3-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9f6b3-112">子要素</span><span class="sxs-lookup"><span data-stu-id="9f6b3-112">Child Elements</span></span>

|<span data-ttu-id="9f6b3-113">要素</span><span class="sxs-lookup"><span data-stu-id="9f6b3-113">Element</span></span>|<span data-ttu-id="9f6b3-114">説明</span><span class="sxs-lookup"><span data-stu-id="9f6b3-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9f6b3-115">構成 (形式) のコントロールの CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="9f6b3-115">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="9f6b3-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="9f6b3-116">Optional element.</span></span><br /><br /> <span data-ttu-id="9f6b3-117">一般的なコントロールまたは使用するには、このコントロールに必要な条件の定義を使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="9f6b3-117">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="9f6b3-118">コントロールの構成の CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="9f6b3-118">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="9f6b3-119">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="9f6b3-119">Required element.</span></span><br /><br /> <span data-ttu-id="9f6b3-120">どのようなデータが、コントロールによって表示され、表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="9f6b3-120">Defines what data is displayed by the control and how it is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9f6b3-121">親要素</span><span class="sxs-lookup"><span data-stu-id="9f6b3-121">Parent Elements</span></span>

|<span data-ttu-id="9f6b3-122">要素</span><span class="sxs-lookup"><span data-stu-id="9f6b3-122">Element</span></span>|<span data-ttu-id="9f6b3-123">説明</span><span class="sxs-lookup"><span data-stu-id="9f6b3-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9f6b3-124">構成 (形式) のカスタム コントロールの CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="9f6b3-124">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="9f6b3-125">コモン コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="9f6b3-125">Provides the definitions of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9f6b3-126">コメント</span><span class="sxs-lookup"><span data-stu-id="9f6b3-126">Remarks</span></span>

<span data-ttu-id="9f6b3-127">ほとんどの場合、1 つだけ定義が必要ですが、各の一般的なカスタム コントロールのさまざまな .NET オブジェクトを表示する同じコントロールを使用する場合、複数の定義を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="9f6b3-127">In most cases, only one definition is required for each common custom control, but it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="9f6b3-128">その場合の各オブジェクトまたはオブジェクトのセットを別の定義を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9f6b3-128">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f6b3-129">参照</span><span class="sxs-lookup"><span data-stu-id="9f6b3-129">See Also</span></span>

[<span data-ttu-id="9f6b3-130">構成 (形式) のカスタム コントロールの CustomEntries 要素</span><span class="sxs-lookup"><span data-stu-id="9f6b3-130">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="9f6b3-131">コントロールの構成の CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="9f6b3-131">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="9f6b3-132">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="9f6b3-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
