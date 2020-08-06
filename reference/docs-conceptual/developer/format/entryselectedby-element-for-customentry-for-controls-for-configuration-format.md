---
title: Configuration 用のコントロール用の CustomEntry 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e9467c8c2d80e46c0a47c31569efbddbabe25bb1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774271"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="1cbdf-102">Configuration の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1cbdf-102">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="1cbdf-103">コモンコントロールの定義、またはこのコントロールを使用するために存在する必要がある条件を使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="1cbdf-103">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span> <span data-ttu-id="1cbdf-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1cbdf-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="1cbdf-105">Configuration 要素 (Format) コントロールの構成 (format) コントロールの要素の構成 (形式) の CustomControl 要素の構成のためのコントロール要素の構成 (形式) の CustomEntries 要素を構成するための CustomControl for configuration (形式) の CustomEntries 要素の構成用コントロール (書式) のための構成 (形式) のコントロールの設定 (形式)</span><span class="sxs-lookup"><span data-stu-id="1cbdf-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1cbdf-106">構文</span><span class="sxs-lookup"><span data-stu-id="1cbdf-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1cbdf-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1cbdf-107">Attributes and Elements</span></span>

<span data-ttu-id="1cbdf-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `EntrySelectedBy` ます。</span><span class="sxs-lookup"><span data-stu-id="1cbdf-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1cbdf-109">属性</span><span class="sxs-lookup"><span data-stu-id="1cbdf-109">Attributes</span></span>

<span data-ttu-id="1cbdf-110">なし。</span><span class="sxs-lookup"><span data-stu-id="1cbdf-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1cbdf-111">子要素</span><span class="sxs-lookup"><span data-stu-id="1cbdf-111">Child Elements</span></span>

|<span data-ttu-id="1cbdf-112">要素</span><span class="sxs-lookup"><span data-stu-id="1cbdf-112">Element</span></span>|<span data-ttu-id="1cbdf-113">説明</span><span class="sxs-lookup"><span data-stu-id="1cbdf-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1cbdf-114">Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1cbdf-114">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="1cbdf-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="1cbdf-115">Optional element.</span></span><br /><br /> <span data-ttu-id="1cbdf-116">共通のコントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="1cbdf-116">Defines the condition that must exist for the common control definition to be used.</span></span>|
|[<span data-ttu-id="1cbdf-117">Configuration の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1cbdf-117">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="1cbdf-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="1cbdf-118">Optional element.</span></span><br /><br /> <span data-ttu-id="1cbdf-119">コモンコントロールのこの定義を使用する一連の .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="1cbdf-119">Specifies a set of .NET types that use this definition of the common control.</span></span>|
|[<span data-ttu-id="1cbdf-120">Configuration の Controls の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1cbdf-120">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="1cbdf-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="1cbdf-121">Optional element.</span></span><br /><br /> <span data-ttu-id="1cbdf-122">コモンコントロールのこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="1cbdf-122">Specifies a .NET type that uses this definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1cbdf-123">親要素</span><span class="sxs-lookup"><span data-stu-id="1cbdf-123">Parent Elements</span></span>

|<span data-ttu-id="1cbdf-124">要素</span><span class="sxs-lookup"><span data-stu-id="1cbdf-124">Element</span></span>|<span data-ttu-id="1cbdf-125">説明</span><span class="sxs-lookup"><span data-stu-id="1cbdf-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1cbdf-126">Configuration の Controls の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1cbdf-126">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="1cbdf-127">コモンコントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="1cbdf-127">Provides a definition of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1cbdf-128">解説</span><span class="sxs-lookup"><span data-stu-id="1cbdf-128">Remarks</span></span>

<span data-ttu-id="1cbdf-129">少なくとも、各定義には、少なくとも1つの .NET 型、選択セット、または選択条件が指定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cbdf-129">At a minimum, each definition must have at least one .NET type, selection set, or selection condition specified.</span></span> <span data-ttu-id="1cbdf-130">指定できる型、選択セット、または選択条件の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="1cbdf-130">There is no maximum limit to the number of types, selection sets, or selection conditions that you can specify.</span></span>

## <a name="see-also"></a><span data-ttu-id="1cbdf-131">参照</span><span class="sxs-lookup"><span data-stu-id="1cbdf-131">See Also</span></span>

[<span data-ttu-id="1cbdf-132">Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1cbdf-132">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="1cbdf-133">Configuration の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1cbdf-133">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="1cbdf-134">Configuration の Controls の CustomControl の CustomEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1cbdf-134">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="1cbdf-135">Configuration の Controls の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1cbdf-135">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="1cbdf-136">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="1cbdf-136">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
