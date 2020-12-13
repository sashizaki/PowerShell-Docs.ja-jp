---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration の Controls の CustomEntry の EntrySelectedBy 要素 (書式)
description: Configuration の Controls の CustomEntry の EntrySelectedBy 要素 (書式)
ms.openlocfilehash: fadcdb69ac71269ba2f2f80baf139bb363d4acba
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666673"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="92cc5-103">Configuration の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="92cc5-103">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="92cc5-104">コモンコントロールの定義、またはこのコントロールを使用するために存在する必要がある条件を使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="92cc5-104">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span> <span data-ttu-id="92cc5-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="92cc5-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="92cc5-106">Configuration 要素 (Format) コントロールの構成 (format) コントロールの要素の構成 (形式) の CustomControl 要素の構成のためのコントロール要素の構成 (形式) の CustomEntries 要素を構成するための CustomControl for configuration (形式) の CustomEntries 要素の構成用コントロール (書式) のための構成 (形式) のコントロールの設定 (形式)</span><span class="sxs-lookup"><span data-stu-id="92cc5-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="92cc5-107">構文</span><span class="sxs-lookup"><span data-stu-id="92cc5-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="92cc5-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="92cc5-108">Attributes and Elements</span></span>

<span data-ttu-id="92cc5-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `EntrySelectedBy` ます。</span><span class="sxs-lookup"><span data-stu-id="92cc5-109">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="92cc5-110">属性</span><span class="sxs-lookup"><span data-stu-id="92cc5-110">Attributes</span></span>

<span data-ttu-id="92cc5-111">なし。</span><span class="sxs-lookup"><span data-stu-id="92cc5-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="92cc5-112">子要素</span><span class="sxs-lookup"><span data-stu-id="92cc5-112">Child Elements</span></span>

|<span data-ttu-id="92cc5-113">要素</span><span class="sxs-lookup"><span data-stu-id="92cc5-113">Element</span></span>|<span data-ttu-id="92cc5-114">説明</span><span class="sxs-lookup"><span data-stu-id="92cc5-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="92cc5-115">Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="92cc5-115">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="92cc5-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="92cc5-116">Optional element.</span></span><br /><br /> <span data-ttu-id="92cc5-117">共通のコントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="92cc5-117">Defines the condition that must exist for the common control definition to be used.</span></span>|
|[<span data-ttu-id="92cc5-118">Configuration の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="92cc5-118">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="92cc5-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="92cc5-119">Optional element.</span></span><br /><br /> <span data-ttu-id="92cc5-120">コモンコントロールのこの定義を使用する一連の .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="92cc5-120">Specifies a set of .NET types that use this definition of the common control.</span></span>|
|[<span data-ttu-id="92cc5-121">Configuration の Controls の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="92cc5-121">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="92cc5-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="92cc5-122">Optional element.</span></span><br /><br /> <span data-ttu-id="92cc5-123">コモンコントロールのこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="92cc5-123">Specifies a .NET type that uses this definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="92cc5-124">親要素</span><span class="sxs-lookup"><span data-stu-id="92cc5-124">Parent Elements</span></span>

|<span data-ttu-id="92cc5-125">要素</span><span class="sxs-lookup"><span data-stu-id="92cc5-125">Element</span></span>|<span data-ttu-id="92cc5-126">説明</span><span class="sxs-lookup"><span data-stu-id="92cc5-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="92cc5-127">Configuration の Controls の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="92cc5-127">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="92cc5-128">コモンコントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="92cc5-128">Provides a definition of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="92cc5-129">解説</span><span class="sxs-lookup"><span data-stu-id="92cc5-129">Remarks</span></span>

<span data-ttu-id="92cc5-130">少なくとも、各定義には、少なくとも1つの .NET 型、選択セット、または選択条件が指定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="92cc5-130">At a minimum, each definition must have at least one .NET type, selection set, or selection condition specified.</span></span> <span data-ttu-id="92cc5-131">指定できる型、選択セット、または選択条件の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="92cc5-131">There is no maximum limit to the number of types, selection sets, or selection conditions that you can specify.</span></span>

## <a name="see-also"></a><span data-ttu-id="92cc5-132">参照</span><span class="sxs-lookup"><span data-stu-id="92cc5-132">See Also</span></span>

[<span data-ttu-id="92cc5-133">Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="92cc5-133">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="92cc5-134">Configuration の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="92cc5-134">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="92cc5-135">Configuration の Controls の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="92cc5-135">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="92cc5-136">Configuration の Controls の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="92cc5-136">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="92cc5-137">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="92cc5-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
