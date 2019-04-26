---
title: ビュー (形式) のカスタム コントロールの CustomEntry EntrySelectedBy 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7828b45b-eabf-4432-b127-131b4ef0c800
caps.latest.revision: 8
ms.openlocfilehash: e7176f9f6ef67116ea7c07a46797fb0ba84f915d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066279"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="825cf-102">View の CustomControl の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="825cf-102">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="825cf-103">このカスタム エントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="825cf-103">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>

<span data-ttu-id="825cf-104">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) EntrySelectedBy CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロール表示 (形式) CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="825cf-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="825cf-105">構文</span><span class="sxs-lookup"><span data-stu-id="825cf-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="825cf-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="825cf-106">Attributes and Elements</span></span>

<span data-ttu-id="825cf-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`EntrySelectedBy`要素。</span><span class="sxs-lookup"><span data-stu-id="825cf-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="825cf-108">属性</span><span class="sxs-lookup"><span data-stu-id="825cf-108">Attributes</span></span>

<span data-ttu-id="825cf-109">なし。</span><span class="sxs-lookup"><span data-stu-id="825cf-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="825cf-110">子要素</span><span class="sxs-lookup"><span data-stu-id="825cf-110">Child Elements</span></span>

|<span data-ttu-id="825cf-111">要素</span><span class="sxs-lookup"><span data-stu-id="825cf-111">Element</span></span>|<span data-ttu-id="825cf-112">説明</span><span class="sxs-lookup"><span data-stu-id="825cf-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="825cf-113">CustomEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="825cf-113">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="825cf-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="825cf-114">Optional element.</span></span><br /><br /> <span data-ttu-id="825cf-115">この定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="825cf-115">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="825cf-116">CustomEntry (形式) の EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="825cf-116">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|<span data-ttu-id="825cf-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="825cf-117">Optional element.</span></span><br /><br /> <span data-ttu-id="825cf-118">このコントロールのビューの定義を使用して .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="825cf-118">Specifies a set of .NET types that use this definition of the control view.</span></span>|
|[<span data-ttu-id="825cf-119">EntrySelectedBy CustomEntry (形式) 用の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="825cf-119">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="825cf-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="825cf-120">Optional element.</span></span><br /><br /> <span data-ttu-id="825cf-121">このコントロールのビューの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="825cf-121">Specifies a .NET type that uses this definition of the control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="825cf-122">親要素</span><span class="sxs-lookup"><span data-stu-id="825cf-122">Parent Elements</span></span>

|<span data-ttu-id="825cf-123">要素</span><span class="sxs-lookup"><span data-stu-id="825cf-123">Element</span></span>|<span data-ttu-id="825cf-124">説明</span><span class="sxs-lookup"><span data-stu-id="825cf-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="825cf-125">表示 (形式) CustomEntries CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="825cf-125">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="825cf-126">特定の .NET オブジェクトで使用される制御を定義します。</span><span class="sxs-lookup"><span data-stu-id="825cf-126">Defines the controls used by specific .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="825cf-127">コメント</span><span class="sxs-lookup"><span data-stu-id="825cf-127">Remarks</span></span>

<span data-ttu-id="825cf-128">少なくとも 1 つの型、選択範囲のセット、またはエントリの選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="825cf-128">You must specify at least one type, selection set, or selection condition for an entry.</span></span> <span data-ttu-id="825cf-129">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="825cf-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="825cf-130">選択条件を使用して、使用するエントリのオブジェクトが特定のプロパティがなどときや、特定のプロパティ値の条件が存在する必要がありますを定義またはスクリプトを評価する`true`します。</span><span class="sxs-lookup"><span data-stu-id="825cf-130">Selection conditions are used to define a condition that must exist for the entry to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="825cf-131">選択条件の詳細については、次を参照してください。[とビューのエントリの定義の条件またはアイテムが使用されて](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="825cf-131">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="825cf-132">カスタム コントロールのビューのコンポーネントに関する詳細については、次を参照してください。[カスタムのコントロール ビュー](./creating-custom-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="825cf-132">For more information about the components of a custom control view, see [Custom Control View](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="825cf-133">参照</span><span class="sxs-lookup"><span data-stu-id="825cf-133">See Also</span></span>

[<span data-ttu-id="825cf-134">CustomEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="825cf-134">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="825cf-135">CustomEntry (形式) の EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="825cf-135">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[<span data-ttu-id="825cf-136">EntrySelectedBy CustomEntry (形式) 用の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="825cf-136">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="825cf-137">表示 (形式) CustomEntries CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="825cf-137">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="825cf-138">カスタム コントロールのビュー</span><span class="sxs-lookup"><span data-stu-id="825cf-138">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="825cf-139">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="825cf-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
