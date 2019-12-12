---
title: CustomControl の CustomEntry 要素 (構成用コントロール用) (形式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9dfba86f-29b2-473c-9e98-9d679176acce
caps.latest.revision: 11
ms.openlocfilehash: 497485a388d1cdc834ecc1d1079b0714a7d7f9db
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364071"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="15f37-102">Configuration の Controls の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="15f37-102">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="15f37-103">コモンコントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="15f37-103">Provides a definition of the common control.</span></span> <span data-ttu-id="15f37-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="15f37-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="15f37-105">Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素形式) CustomControl の CustomEntry 要素を構成用のコントロール (形式)</span><span class="sxs-lookup"><span data-stu-id="15f37-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="15f37-106">構文</span><span class="sxs-lookup"><span data-stu-id="15f37-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="15f37-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="15f37-107">Attributes and Elements</span></span>

<span data-ttu-id="15f37-108">次のセクションでは、`CustomEntry` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="15f37-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="15f37-109">定義によって表示される項目を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15f37-109">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="15f37-110">属性</span><span class="sxs-lookup"><span data-stu-id="15f37-110">Attributes</span></span>

<span data-ttu-id="15f37-111">なし。</span><span class="sxs-lookup"><span data-stu-id="15f37-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="15f37-112">子要素</span><span class="sxs-lookup"><span data-stu-id="15f37-112">Child Elements</span></span>

|<span data-ttu-id="15f37-113">要素</span><span class="sxs-lookup"><span data-stu-id="15f37-113">Element</span></span>|<span data-ttu-id="15f37-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="15f37-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="15f37-115">Configuration 用のコントロール用の CustomEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="15f37-115">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="15f37-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="15f37-116">Optional element.</span></span><br /><br /> <span data-ttu-id="15f37-117">コモンコントロールの定義、またはこのコントロールを使用するために存在する必要がある条件を使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="15f37-117">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="15f37-118">構成のための CustomEntry コントロールの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="15f37-118">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="15f37-119">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="15f37-119">Required element.</span></span><br /><br /> <span data-ttu-id="15f37-120">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="15f37-120">Defines what data is displayed by the control and how it is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="15f37-121">親要素</span><span class="sxs-lookup"><span data-stu-id="15f37-121">Parent Elements</span></span>

|<span data-ttu-id="15f37-122">要素</span><span class="sxs-lookup"><span data-stu-id="15f37-122">Element</span></span>|<span data-ttu-id="15f37-123">[説明]</span><span class="sxs-lookup"><span data-stu-id="15f37-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="15f37-124">Configuration の CustomControl の CustomEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="15f37-124">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="15f37-125">コモンコントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="15f37-125">Provides the definitions of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="15f37-126">コメント</span><span class="sxs-lookup"><span data-stu-id="15f37-126">Remarks</span></span>

<span data-ttu-id="15f37-127">ほとんどの場合、共通のカスタムコントロールごとに1つの定義のみが必要ですが、同じコントロールを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="15f37-127">In most cases, only one definition is required for each common custom control, but it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="15f37-128">このような場合は、オブジェクトまたはオブジェクトのセットごとに個別の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="15f37-128">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="15f37-129">参照</span><span class="sxs-lookup"><span data-stu-id="15f37-129">See Also</span></span>

[<span data-ttu-id="15f37-130">Configuration の CustomControl の CustomEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="15f37-130">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="15f37-131">構成のための CustomEntry コントロールの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="15f37-131">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="15f37-132">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="15f37-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
