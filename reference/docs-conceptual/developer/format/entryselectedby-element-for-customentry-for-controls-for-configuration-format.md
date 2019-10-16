---
title: Configuration 用のコントロール用の CustomEntry 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30abae8f-c7f7-479d-ad85-19e07ddef204
caps.latest.revision: 10
ms.openlocfilehash: 81eca4f66f0057074612f2d60482b45adc36357b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368771"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="4fdb7-102">Configuration の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4fdb7-102">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="4fdb7-103">コモンコントロールの定義、またはこのコントロールを使用するために存在する必要がある条件を使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="4fdb7-103">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span> <span data-ttu-id="4fdb7-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4fdb7-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="4fdb7-105">Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素Format) CustomControl の CustomEntry 要素を構成するためのコントロール用の CustomEntry 要素 (形式) を構成するために、CustomEntry のコントロールの EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="4fdb7-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4fdb7-106">構文</span><span class="sxs-lookup"><span data-stu-id="4fdb7-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4fdb7-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="4fdb7-107">Attributes and Elements</span></span>

<span data-ttu-id="4fdb7-108">次のセクションでは、属性、子要素、`EntrySelectedBy` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fdb7-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4fdb7-109">属性</span><span class="sxs-lookup"><span data-stu-id="4fdb7-109">Attributes</span></span>

<span data-ttu-id="4fdb7-110">なし。</span><span class="sxs-lookup"><span data-stu-id="4fdb7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4fdb7-111">子要素</span><span class="sxs-lookup"><span data-stu-id="4fdb7-111">Child Elements</span></span>

|<span data-ttu-id="4fdb7-112">要素</span><span class="sxs-lookup"><span data-stu-id="4fdb7-112">Element</span></span>|<span data-ttu-id="4fdb7-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="4fdb7-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4fdb7-114">構成用のコントロール (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="4fdb7-114">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="4fdb7-115">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="4fdb7-115">Optional element.</span></span><br /><br /> <span data-ttu-id="4fdb7-116">共通のコントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="4fdb7-116">Defines the condition that must exist for the common control definition to be used.</span></span>|
|[<span data-ttu-id="4fdb7-117">構成用のコントロール (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="4fdb7-117">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="4fdb7-118">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="4fdb7-118">Optional element.</span></span><br /><br /> <span data-ttu-id="4fdb7-119">コモンコントロールのこの定義を使用する一連の .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="4fdb7-119">Specifies a set of .NET types that use this definition of the common control.</span></span>|
|[<span data-ttu-id="4fdb7-120">構成用のコントロール (Format) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="4fdb7-120">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="4fdb7-121">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="4fdb7-121">Optional element.</span></span><br /><br /> <span data-ttu-id="4fdb7-122">コモンコントロールのこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="4fdb7-122">Specifies a .NET type that uses this definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4fdb7-123">親要素</span><span class="sxs-lookup"><span data-stu-id="4fdb7-123">Parent Elements</span></span>

|<span data-ttu-id="4fdb7-124">要素</span><span class="sxs-lookup"><span data-stu-id="4fdb7-124">Element</span></span>|<span data-ttu-id="4fdb7-125">[説明]</span><span class="sxs-lookup"><span data-stu-id="4fdb7-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4fdb7-126">CustomControl の CustomEntry 要素 (構成用コントロール用) (形式)</span><span class="sxs-lookup"><span data-stu-id="4fdb7-126">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="4fdb7-127">コモンコントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="4fdb7-127">Provides a definition of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4fdb7-128">コメント</span><span class="sxs-lookup"><span data-stu-id="4fdb7-128">Remarks</span></span>

<span data-ttu-id="4fdb7-129">少なくとも、各定義には、少なくとも1つの .NET 型、選択セット、または選択条件が指定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fdb7-129">At a minimum, each definition must have at least one .NET type, selection set, or selection condition specified.</span></span> <span data-ttu-id="4fdb7-130">指定できる型、選択セット、または選択条件の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="4fdb7-130">There is no maximum limit to the number of types, selection sets, or selection conditions that you can specify.</span></span>

## <a name="see-also"></a><span data-ttu-id="4fdb7-131">参照</span><span class="sxs-lookup"><span data-stu-id="4fdb7-131">See Also</span></span>

[<span data-ttu-id="4fdb7-132">構成用のコントロール (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="4fdb7-132">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="4fdb7-133">構成用のコントロール (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="4fdb7-133">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="4fdb7-134">CustomControl の CustomEntry 要素 (構成用コントロール用) (形式)</span><span class="sxs-lookup"><span data-stu-id="4fdb7-134">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="4fdb7-135">構成用のコントロール (Format) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="4fdb7-135">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="4fdb7-136">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="4fdb7-136">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
