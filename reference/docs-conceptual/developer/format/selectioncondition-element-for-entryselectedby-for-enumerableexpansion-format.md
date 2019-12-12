---
title: 列挙 Able膨張 (Format) の EntrySelectedBy の SelectionCondition 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c012115-9241-4851-9015-841eb508faf3
caps.latest.revision: 10
ms.openlocfilehash: d6adf2fa62384d671fd6a07dd185a941daa44cec
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362011"
---
# <a name="selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="89bff-102">EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="89bff-102">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="89bff-103">この定義のコレクションオブジェクトを展開するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="89bff-103">Defines the condition that must exist to expand the collection objects of this definition.</span></span>

<span data-ttu-id="89bff-104">Configuration 要素 (Format) DefaultSettings 要素 (format) 列挙 Able膨張要素 (format) 列挙 able膨張拡張要素 (format) の Entryselectedby 要素の entryselectedby 要素の EntrySelectedBy 要素列挙 Able展開 (形式)</span><span class="sxs-lookup"><span data-stu-id="89bff-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="89bff-105">構文</span><span class="sxs-lookup"><span data-stu-id="89bff-105">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="89bff-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="89bff-106">Attributes and Elements</span></span>

<span data-ttu-id="89bff-107">次のセクションでは、`SelectionCondition` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="89bff-107">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="89bff-108">1つの `PropertyName` または `ScriptBlock` 要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89bff-108">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="89bff-109">`SelectionSetName` 要素と `TypeName` 要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="89bff-109">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="89bff-110">いずれかの要素を指定できます。</span><span class="sxs-lookup"><span data-stu-id="89bff-110">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="89bff-111">属性</span><span class="sxs-lookup"><span data-stu-id="89bff-111">Attributes</span></span>

<span data-ttu-id="89bff-112">なし。</span><span class="sxs-lookup"><span data-stu-id="89bff-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="89bff-113">子要素</span><span class="sxs-lookup"><span data-stu-id="89bff-113">Child Elements</span></span>

|<span data-ttu-id="89bff-114">要素</span><span class="sxs-lookup"><span data-stu-id="89bff-114">Element</span></span>|<span data-ttu-id="89bff-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="89bff-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="89bff-116">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="89bff-116">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="89bff-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="89bff-117">Optional element.</span></span><br /><br /> <span data-ttu-id="89bff-118">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="89bff-118">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="89bff-119">列挙 Able展開の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="89bff-119">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="89bff-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="89bff-120">Optional element.</span></span><br /><br /> <span data-ttu-id="89bff-121">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="89bff-121">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="89bff-122">列挙 Able膨張 (Format) の EntrySelectedBy の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="89bff-122">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="89bff-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="89bff-123">Optional element.</span></span><br /><br /> <span data-ttu-id="89bff-124">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="89bff-124">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="89bff-125">列挙型拡張の EntrySelectedBy の SelectionCondition の TypeName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="89bff-125">TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="89bff-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="89bff-126">Optional element.</span></span><br /><br /> <span data-ttu-id="89bff-127">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="89bff-127">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="89bff-128">親要素</span><span class="sxs-lookup"><span data-stu-id="89bff-128">Parent Elements</span></span>

|<span data-ttu-id="89bff-129">要素</span><span class="sxs-lookup"><span data-stu-id="89bff-129">Element</span></span>|<span data-ttu-id="89bff-130">[説明]</span><span class="sxs-lookup"><span data-stu-id="89bff-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="89bff-131">列挙 Able展開 (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="89bff-131">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="89bff-132">この定義によって展開される .NET コレクションオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="89bff-132">Defines which .NET collection objects are expanded by this definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="89bff-133">コメント</span><span class="sxs-lookup"><span data-stu-id="89bff-133">Remarks</span></span>

<span data-ttu-id="89bff-134">各定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="89bff-134">Each definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="89bff-135">選択条件を定義する場合は、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="89bff-135">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="89bff-136">選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="89bff-136">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="89bff-137">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="89bff-137">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="89bff-138">選択条件の使用方法の詳細については、「[データの Diplaying の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89bff-138">For more information about how to use selection conditions, see [Defining Conditions for Diplaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="89bff-139">ワイドビューのその他のコンポーネントの詳細については、「 [Wide ビュー](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89bff-139">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="89bff-140">参照</span><span class="sxs-lookup"><span data-stu-id="89bff-140">See Also</span></span>

[<span data-ttu-id="89bff-141">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="89bff-141">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="89bff-142">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="89bff-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
