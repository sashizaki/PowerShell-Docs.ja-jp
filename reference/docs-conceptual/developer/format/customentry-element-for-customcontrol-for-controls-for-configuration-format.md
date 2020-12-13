---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration の Controls の CustomControl の CustomEntry 要素 (書式)
description: Configuration の Controls の CustomControl の CustomEntry 要素 (書式)
ms.openlocfilehash: 3967be86a1d6c12c7215ef19d50bac9fafd5ad6d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648273"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="326f8-103">Configuration の Controls の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="326f8-103">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="326f8-104">コモンコントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="326f8-104">Provides a definition of the common control.</span></span> <span data-ttu-id="326f8-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="326f8-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="326f8-106">Configuration 要素 (Format) コントロールの configuration (format) コントロールの要素の構成 (形式) の CustomControl 要素の構成のためのコントロールの要素の構成 (書式) の CustomControl の構成 (形式) の CustomEntries 要素の構成のためのコントロールの CustomControl のための構成 (形式)</span><span class="sxs-lookup"><span data-stu-id="326f8-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="326f8-107">構文</span><span class="sxs-lookup"><span data-stu-id="326f8-107">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="326f8-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="326f8-108">Attributes and Elements</span></span>

<span data-ttu-id="326f8-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="326f8-109">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="326f8-110">定義によって表示される項目を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="326f8-110">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="326f8-111">属性</span><span class="sxs-lookup"><span data-stu-id="326f8-111">Attributes</span></span>

<span data-ttu-id="326f8-112">なし。</span><span class="sxs-lookup"><span data-stu-id="326f8-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="326f8-113">子要素</span><span class="sxs-lookup"><span data-stu-id="326f8-113">Child Elements</span></span>

|<span data-ttu-id="326f8-114">要素</span><span class="sxs-lookup"><span data-stu-id="326f8-114">Element</span></span>|<span data-ttu-id="326f8-115">説明</span><span class="sxs-lookup"><span data-stu-id="326f8-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="326f8-116">Configuration の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="326f8-116">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="326f8-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="326f8-117">Optional element.</span></span><br /><br /> <span data-ttu-id="326f8-118">コモンコントロールの定義、またはこのコントロールを使用するために存在する必要がある条件を使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="326f8-118">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="326f8-119">構成のための CustomEntry コントロールの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="326f8-119">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="326f8-120">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="326f8-120">Required element.</span></span><br /><br /> <span data-ttu-id="326f8-121">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="326f8-121">Defines what data is displayed by the control and how it is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="326f8-122">親要素</span><span class="sxs-lookup"><span data-stu-id="326f8-122">Parent Elements</span></span>

|<span data-ttu-id="326f8-123">要素</span><span class="sxs-lookup"><span data-stu-id="326f8-123">Element</span></span>|<span data-ttu-id="326f8-124">説明</span><span class="sxs-lookup"><span data-stu-id="326f8-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="326f8-125">Configuration の CustomControl の CustomEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="326f8-125">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="326f8-126">コモンコントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="326f8-126">Provides the definitions of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="326f8-127">解説</span><span class="sxs-lookup"><span data-stu-id="326f8-127">Remarks</span></span>

<span data-ttu-id="326f8-128">ほとんどの場合、共通のカスタムコントロールごとに1つの定義のみが必要ですが、同じコントロールを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="326f8-128">In most cases, only one definition is required for each common custom control, but it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="326f8-129">このような場合は、オブジェクトまたはオブジェクトのセットごとに個別の定義を指定できます。</span><span class="sxs-lookup"><span data-stu-id="326f8-129">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="326f8-130">参照</span><span class="sxs-lookup"><span data-stu-id="326f8-130">See Also</span></span>

[<span data-ttu-id="326f8-131">Configuration の CustomControl の CustomEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="326f8-131">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="326f8-132">構成のための CustomEntry コントロールの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="326f8-132">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="326f8-133">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="326f8-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
