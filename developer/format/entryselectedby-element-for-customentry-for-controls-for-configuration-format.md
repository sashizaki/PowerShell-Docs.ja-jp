---
title: 構成 (形式) のコントロールの CustomEntry EntrySelectedBy 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30abae8f-c7f7-479d-ad85-19e07ddef204
caps.latest.revision: 10
ms.openlocfilehash: 81eca4f66f0057074612f2d60482b45adc36357b
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066296"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="da3cc-102">Configuration の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="da3cc-102">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="da3cc-103">一般的なコントロールまたは使用するには、このコントロールに必要な条件の定義を使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="da3cc-103">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span> <span data-ttu-id="da3cc-104">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="da3cc-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="da3cc-105">構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素構成 (形式) のコントロールの CustomEntry の構成 (形式) EntrySelectedBy 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="da3cc-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="da3cc-106">構文</span><span class="sxs-lookup"><span data-stu-id="da3cc-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="da3cc-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="da3cc-107">Attributes and Elements</span></span>

<span data-ttu-id="da3cc-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`EntrySelectedBy`要素。</span><span class="sxs-lookup"><span data-stu-id="da3cc-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="da3cc-109">属性</span><span class="sxs-lookup"><span data-stu-id="da3cc-109">Attributes</span></span>

<span data-ttu-id="da3cc-110">なし。</span><span class="sxs-lookup"><span data-stu-id="da3cc-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="da3cc-111">子要素</span><span class="sxs-lookup"><span data-stu-id="da3cc-111">Child Elements</span></span>

|<span data-ttu-id="da3cc-112">要素</span><span class="sxs-lookup"><span data-stu-id="da3cc-112">Element</span></span>|<span data-ttu-id="da3cc-113">説明</span><span class="sxs-lookup"><span data-stu-id="da3cc-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="da3cc-114">構成 (形式) のコントロールの EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="da3cc-114">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="da3cc-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="da3cc-115">Optional element.</span></span><br /><br /> <span data-ttu-id="da3cc-116">使用する一般的なコントロールの定義を満たす必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="da3cc-116">Defines the condition that must exist for the common control definition to be used.</span></span>|
|[<span data-ttu-id="da3cc-117">構成 (形式) のコントロールの EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="da3cc-117">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="da3cc-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="da3cc-118">Optional element.</span></span><br /><br /> <span data-ttu-id="da3cc-119">コモン コントロールのこの定義を使用する .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="da3cc-119">Specifies a set of .NET types that use this definition of the common control.</span></span>|
|[<span data-ttu-id="da3cc-120">構成 (形式) のコントロールの EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="da3cc-120">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="da3cc-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="da3cc-121">Optional element.</span></span><br /><br /> <span data-ttu-id="da3cc-122">コモン コントロールのこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="da3cc-122">Specifies a .NET type that uses this definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="da3cc-123">親要素</span><span class="sxs-lookup"><span data-stu-id="da3cc-123">Parent Elements</span></span>

|<span data-ttu-id="da3cc-124">要素</span><span class="sxs-lookup"><span data-stu-id="da3cc-124">Element</span></span>|<span data-ttu-id="da3cc-125">説明</span><span class="sxs-lookup"><span data-stu-id="da3cc-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="da3cc-126">構成 (形式) のコントロールのカスタム コントロールの CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="da3cc-126">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="da3cc-127">コモン コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="da3cc-127">Provides a definition of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="da3cc-128">コメント</span><span class="sxs-lookup"><span data-stu-id="da3cc-128">Remarks</span></span>

<span data-ttu-id="da3cc-129">少なくとも、各定義は、少なくとも 1 つの .NET 型、選択範囲のセット、または指定された選択条件が必要です。</span><span class="sxs-lookup"><span data-stu-id="da3cc-129">At a minimum, each definition must have at least one .NET type, selection set, or selection condition specified.</span></span> <span data-ttu-id="da3cc-130">型、選択範囲のセット、または指定できる選択条件の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="da3cc-130">There is no maximum limit to the number of types, selection sets, or selection conditions that you can specify.</span></span>

## <a name="see-also"></a><span data-ttu-id="da3cc-131">参照</span><span class="sxs-lookup"><span data-stu-id="da3cc-131">See Also</span></span>

[<span data-ttu-id="da3cc-132">構成 (形式) のコントロールの EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="da3cc-132">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="da3cc-133">構成 (形式) のコントロールの EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="da3cc-133">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="da3cc-134">構成 (形式) のコントロールのカスタム コントロールの CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="da3cc-134">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="da3cc-135">構成 (形式) のコントロールの EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="da3cc-135">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="da3cc-136">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="da3cc-136">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
