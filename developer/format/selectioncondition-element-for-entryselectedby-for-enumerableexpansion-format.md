---
title: EnumerableExpansion (形式) の EntrySelectedBy SelectionCondition 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c012115-9241-4851-9015-841eb508faf3
caps.latest.revision: 10
ms.openlocfilehash: d6adf2fa62384d671fd6a07dd185a941daa44cec
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858288"
---
# <a name="selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="e7a0b-102">EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e7a0b-102">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="e7a0b-103">この定義のコレクション オブジェクトの展開に必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-103">Defines the condition that must exist to expand the collection objects of this definition.</span></span>

<span data-ttu-id="e7a0b-104">構成要素 (形式) DefaultSettings 要素 (形式) EnumerableExpansions 要素 (形式) EnumerableExpansion 要素 (形式) EntrySelectedBy 要素の EntrySelectedBy の EnumerableExpansion (形式) SelectionCondition 要素EnumerableExpansion (形式)</span><span class="sxs-lookup"><span data-stu-id="e7a0b-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e7a0b-105">構文</span><span class="sxs-lookup"><span data-stu-id="e7a0b-105">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e7a0b-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="e7a0b-106">Attributes and Elements</span></span>

<span data-ttu-id="e7a0b-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionCondition`要素。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-107">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="e7a0b-108">1 つを指定する必要があります`PropertyName`または`ScriptBlock`要素。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-108">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="e7a0b-109">`SelectionSetName`と`TypeName`要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-109">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="e7a0b-110">要素のいずれかのいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-110">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e7a0b-111">属性</span><span class="sxs-lookup"><span data-stu-id="e7a0b-111">Attributes</span></span>

<span data-ttu-id="e7a0b-112">なし。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e7a0b-113">子要素</span><span class="sxs-lookup"><span data-stu-id="e7a0b-113">Child Elements</span></span>

|<span data-ttu-id="e7a0b-114">要素</span><span class="sxs-lookup"><span data-stu-id="e7a0b-114">Element</span></span>|<span data-ttu-id="e7a0b-115">説明</span><span class="sxs-lookup"><span data-stu-id="e7a0b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e7a0b-116">SelectionCondition EntrySelectedBy EnumerableExpansion (形式) のための PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="e7a0b-116">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="e7a0b-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-117">Optional element.</span></span><br /><br /> <span data-ttu-id="e7a0b-118">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-118">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="e7a0b-119">SelectionCondition EntrySelectedBy EnumerableExpansion (形式) のためのスクリプト ブロックの要素</span><span class="sxs-lookup"><span data-stu-id="e7a0b-119">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="e7a0b-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-120">Optional element.</span></span><br /><br /> <span data-ttu-id="e7a0b-121">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-121">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="e7a0b-122">EntrySelectedBy EnumerableExpansion (形式) 用の SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="e7a0b-122">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="e7a0b-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-123">Optional element.</span></span><br /><br /> <span data-ttu-id="e7a0b-124">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-124">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="e7a0b-125">SelectionCondition EntrySelectedBy EnumerableExpansion (形式) のための TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="e7a0b-125">TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="e7a0b-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-126">Optional element.</span></span><br /><br /> <span data-ttu-id="e7a0b-127">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-127">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e7a0b-128">親要素</span><span class="sxs-lookup"><span data-stu-id="e7a0b-128">Parent Elements</span></span>

|<span data-ttu-id="e7a0b-129">要素</span><span class="sxs-lookup"><span data-stu-id="e7a0b-129">Element</span></span>|<span data-ttu-id="e7a0b-130">説明</span><span class="sxs-lookup"><span data-stu-id="e7a0b-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e7a0b-131">EnumerableExpansion (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="e7a0b-131">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="e7a0b-132">.NET コレクション オブジェクトの拡張機能では、この定義を定義します。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-132">Defines which .NET collection objects are expanded by this definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e7a0b-133">コメント</span><span class="sxs-lookup"><span data-stu-id="e7a0b-133">Remarks</span></span>

<span data-ttu-id="e7a0b-134">各定義に少なくとも 1 つの型名、選択範囲のセット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-134">Each definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="e7a0b-135">選択条件を定義している場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-135">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="e7a0b-136">選択条件では、少なくとも 1 つのプロパティ名またはスクリプト ブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-136">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="e7a0b-137">選択条件が .NET 型の任意の数を指定するか、選択範囲を設定するが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-137">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="e7a0b-138">選択条件を使用する方法の詳細については、次を参照してください。 [Diplaying データの条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-138">For more information about how to use selection conditions, see [Defining Conditions for Diplaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="e7a0b-139">ワイド ビューの他のコンポーネントに関する詳細については、次を参照してください。[表示幅が広い](./creating-a-wide-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="e7a0b-139">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e7a0b-140">参照</span><span class="sxs-lookup"><span data-stu-id="e7a0b-140">See Also</span></span>

[<span data-ttu-id="e7a0b-141">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="e7a0b-141">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="e7a0b-142">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="e7a0b-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
