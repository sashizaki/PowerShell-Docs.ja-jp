---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)
description: Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)
ms.openlocfilehash: ce00cdf868a3075875043aeb59f2cb8a17d049a9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645782"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="02ed4-103">Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="02ed4-103">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="02ed4-104">共通のコントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="02ed4-104">Defines a condition that must exist for a common control definition to be used.</span></span> <span data-ttu-id="02ed4-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="02ed4-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="02ed4-106">Configuration 要素 (Format) コントロールの configuration (format) コントロールの要素の構成 (format) CustomControl 要素の構成のためのコントロールの CustomControl の構成 (形式) の CustomEntries 要素の構成 (書式設定用コントロール) CustomControl のためのコントロールのためのコントロールのための構成 (形式) の構成 (形式) のために、customentry for Configuration (形式) の SelectionCondition 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="02ed4-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="02ed4-107">構文</span><span class="sxs-lookup"><span data-stu-id="02ed4-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="02ed4-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="02ed4-108">Attributes and Elements</span></span>

<span data-ttu-id="02ed4-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="02ed4-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="02ed4-110">属性</span><span class="sxs-lookup"><span data-stu-id="02ed4-110">Attributes</span></span>

<span data-ttu-id="02ed4-111">なし。</span><span class="sxs-lookup"><span data-stu-id="02ed4-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="02ed4-112">子要素</span><span class="sxs-lookup"><span data-stu-id="02ed4-112">Child Elements</span></span>

|<span data-ttu-id="02ed4-113">要素</span><span class="sxs-lookup"><span data-stu-id="02ed4-113">Element</span></span>|<span data-ttu-id="02ed4-114">説明</span><span class="sxs-lookup"><span data-stu-id="02ed4-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="02ed4-115">Configuration の Controls の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="02ed4-115">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="02ed4-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="02ed4-116">Optional element.</span></span><br /><br /> <span data-ttu-id="02ed4-117">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="02ed4-117">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="02ed4-118">Configuration の Controls の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="02ed4-118">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="02ed4-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="02ed4-119">Optional element.</span></span><br /><br /> <span data-ttu-id="02ed4-120">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="02ed4-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="02ed4-121">Configuration の Controls の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="02ed4-121">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="02ed4-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="02ed4-122">Optional element.</span></span><br /><br /> <span data-ttu-id="02ed4-123">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="02ed4-123">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="02ed4-124">Configuration の Controls の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="02ed4-124">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="02ed4-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="02ed4-125">Optional element.</span></span><br /><br /> <span data-ttu-id="02ed4-126">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="02ed4-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="02ed4-127">親要素</span><span class="sxs-lookup"><span data-stu-id="02ed4-127">Parent Elements</span></span>

|<span data-ttu-id="02ed4-128">要素</span><span class="sxs-lookup"><span data-stu-id="02ed4-128">Element</span></span>|<span data-ttu-id="02ed4-129">説明</span><span class="sxs-lookup"><span data-stu-id="02ed4-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="02ed4-130">Configuration の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="02ed4-130">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="02ed4-131">コモンコントロール定義のこのエントリを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="02ed4-131">Defines the .NET types that use this entry of the common control definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="02ed4-132">解説</span><span class="sxs-lookup"><span data-stu-id="02ed4-132">Remarks</span></span>

<span data-ttu-id="02ed4-133">選択条件を定義するときは、次のガイドラインに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="02ed4-133">The following guidelines must be followed when defining a selection condition:</span></span>

- <span data-ttu-id="02ed4-134">選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="02ed4-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="02ed4-135">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="02ed4-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="02ed4-136">選択条件を使用する方法の詳細については、「 [データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02ed4-136">For more information about how selection conditions can be used, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="02ed4-137">参照</span><span class="sxs-lookup"><span data-stu-id="02ed4-137">See Also</span></span>

[<span data-ttu-id="02ed4-138">Configuration の Controls の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="02ed4-138">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="02ed4-139">Configuration の Controls の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="02ed4-139">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="02ed4-140">Configuration の Controls の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="02ed4-140">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="02ed4-141">Configuration の Controls の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="02ed4-141">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="02ed4-142">Configuration の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="02ed4-142">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="02ed4-143">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="02ed4-143">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
