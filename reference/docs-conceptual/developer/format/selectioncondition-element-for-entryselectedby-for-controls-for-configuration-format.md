---
title: 構成用のコントロール (Format) の EntrySelectedBy の SelectionCondition 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f23ef405-0f1e-4607-b3f4-4017b7ead106
caps.latest.revision: 7
ms.openlocfilehash: a5098da55d0a63272a121b973cb05e26dc47e3e1
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368451"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="d726b-102">Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d726b-102">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="d726b-103">共通のコントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="d726b-103">Defines a condition that must exist for a common control definition to be used.</span></span> <span data-ttu-id="d726b-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d726b-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="d726b-105">Configuration 要素 (Format) コントロールの configuration (format) CustomControl 要素のコントロール要素を構成するためのコントロールの構成 (形式) のコントロール要素の構成 (書式設定) 要素構成 (Format) CustomEntry 要素の CustomControl のためのコントロール用の構成 (形式) の構成 (形式) のために、customentry に対して EntrySelectedBy の Configuration (Format) SelectionCondition 要素を指定します。構成 (形式)</span><span class="sxs-lookup"><span data-stu-id="d726b-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d726b-106">構文</span><span class="sxs-lookup"><span data-stu-id="d726b-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d726b-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="d726b-107">Attributes and Elements</span></span>

<span data-ttu-id="d726b-108">次のセクションでは、`SelectionCondition` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d726b-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d726b-109">属性</span><span class="sxs-lookup"><span data-stu-id="d726b-109">Attributes</span></span>

<span data-ttu-id="d726b-110">なし。</span><span class="sxs-lookup"><span data-stu-id="d726b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d726b-111">子要素</span><span class="sxs-lookup"><span data-stu-id="d726b-111">Child Elements</span></span>

|<span data-ttu-id="d726b-112">要素</span><span class="sxs-lookup"><span data-stu-id="d726b-112">Element</span></span>|<span data-ttu-id="d726b-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="d726b-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d726b-114">構成用のコントロールの SelectionCondition の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="d726b-114">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="d726b-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d726b-115">Optional element.</span></span><br /><br /> <span data-ttu-id="d726b-116">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="d726b-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="d726b-117">構成用のコントロールの SelectionCondition の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="d726b-117">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="d726b-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d726b-118">Optional element.</span></span><br /><br /> <span data-ttu-id="d726b-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d726b-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="d726b-120">構成用のコントロールの SelectionCondition の SelectionSetName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="d726b-120">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="d726b-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d726b-121">Optional element.</span></span><br /><br /> <span data-ttu-id="d726b-122">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="d726b-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="d726b-123">構成用のコントロールの SelectionCondition の TypeName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="d726b-123">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="d726b-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d726b-124">Optional element.</span></span><br /><br /> <span data-ttu-id="d726b-125">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="d726b-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d726b-126">親要素</span><span class="sxs-lookup"><span data-stu-id="d726b-126">Parent Elements</span></span>

|<span data-ttu-id="d726b-127">要素</span><span class="sxs-lookup"><span data-stu-id="d726b-127">Element</span></span>|<span data-ttu-id="d726b-128">[説明]</span><span class="sxs-lookup"><span data-stu-id="d726b-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d726b-129">Configuration 用のコントロール用の CustomEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="d726b-129">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="d726b-130">コモンコントロール定義のこのエントリを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="d726b-130">Defines the .NET types that use this entry of the common control definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d726b-131">コメント</span><span class="sxs-lookup"><span data-stu-id="d726b-131">Remarks</span></span>

<span data-ttu-id="d726b-132">選択条件を定義するときは、次のガイドラインに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d726b-132">The following guidelines must be followed when defining a selection condition:</span></span>

- <span data-ttu-id="d726b-133">選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d726b-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="d726b-134">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d726b-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="d726b-135">選択条件を使用する方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d726b-135">For more information about how selection conditions can be used, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d726b-136">参照</span><span class="sxs-lookup"><span data-stu-id="d726b-136">See Also</span></span>

[<span data-ttu-id="d726b-137">構成用のコントロールの SelectionCondition の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="d726b-137">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="d726b-138">構成用のコントロールの SelectionCondition の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="d726b-138">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="d726b-139">構成用のコントロールの SelectionCondition の SelectionSetName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="d726b-139">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="d726b-140">構成用のコントロールの SelectionCondition の TypeName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="d726b-140">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="d726b-141">Configuration 用のコントロール用の CustomEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="d726b-141">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="d726b-142">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="d726b-142">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
