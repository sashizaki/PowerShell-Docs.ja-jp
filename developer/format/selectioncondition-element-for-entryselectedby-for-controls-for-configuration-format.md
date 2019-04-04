---
title: 構成 (形式) のコントロールの EntrySelectedBy SelectionCondition 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f23ef405-0f1e-4607-b3f4-4017b7ead106
caps.latest.revision: 7
ms.openlocfilehash: a5098da55d0a63272a121b973cb05e26dc47e3e1
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854148"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="47530-102">Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="47530-102">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="47530-103">使用する一般的なコントロールの定義を満たす必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="47530-103">Defines a condition that must exist for a common control definition to be used.</span></span> <span data-ttu-id="47530-104">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="47530-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="47530-105">コントロールのコントロールのカスタム コントロールの構成 (形式) CustomEntries 要素の構成 (形式) のカスタム コントロール要素のコントロールの構成 (形式) のコントロール要素の構成要素 (形式) のコントロール要素CustomEntry EntrySelectedBy CustomEntry のための構成 (形式) SelectionCondition 要素のコントロール用の構成 (形式) EntrySelectedBy 要素のコントロールのカスタム コントロールの構成 (形式) CustomEntry 要素構成 (形式)</span><span class="sxs-lookup"><span data-stu-id="47530-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="47530-106">構文</span><span class="sxs-lookup"><span data-stu-id="47530-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="47530-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="47530-107">Attributes and Elements</span></span>

<span data-ttu-id="47530-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionCondition`要素。</span><span class="sxs-lookup"><span data-stu-id="47530-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="47530-109">属性</span><span class="sxs-lookup"><span data-stu-id="47530-109">Attributes</span></span>

<span data-ttu-id="47530-110">なし。</span><span class="sxs-lookup"><span data-stu-id="47530-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="47530-111">子要素</span><span class="sxs-lookup"><span data-stu-id="47530-111">Child Elements</span></span>

|<span data-ttu-id="47530-112">要素</span><span class="sxs-lookup"><span data-stu-id="47530-112">Element</span></span>|<span data-ttu-id="47530-113">説明</span><span class="sxs-lookup"><span data-stu-id="47530-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="47530-114">構成 (形式) のコントロールの SelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="47530-114">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="47530-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="47530-115">Optional element.</span></span><br /><br /> <span data-ttu-id="47530-116">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="47530-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="47530-117">構成 (形式) のコントロールの SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="47530-117">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="47530-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="47530-118">Optional element.</span></span><br /><br /> <span data-ttu-id="47530-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="47530-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="47530-120">構成 (形式) のコントロールの SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="47530-120">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="47530-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="47530-121">Optional element.</span></span><br /><br /> <span data-ttu-id="47530-122">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="47530-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="47530-123">構成 (形式) のコントロールの SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="47530-123">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="47530-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="47530-124">Optional element.</span></span><br /><br /> <span data-ttu-id="47530-125">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="47530-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="47530-126">親要素</span><span class="sxs-lookup"><span data-stu-id="47530-126">Parent Elements</span></span>

|<span data-ttu-id="47530-127">要素</span><span class="sxs-lookup"><span data-stu-id="47530-127">Element</span></span>|<span data-ttu-id="47530-128">説明</span><span class="sxs-lookup"><span data-stu-id="47530-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="47530-129">構成 (形式) のコントロールの CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="47530-129">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="47530-130">このエントリの一般的なコントロールの定義を使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="47530-130">Defines the .NET types that use this entry of the common control definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="47530-131">コメント</span><span class="sxs-lookup"><span data-stu-id="47530-131">Remarks</span></span>

<span data-ttu-id="47530-132">選択条件を定義するときに、次のガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="47530-132">The following guidelines must be followed when defining a selection condition:</span></span>

- <span data-ttu-id="47530-133">選択条件では、少なくとも 1 つのプロパティ名またはスクリプト ブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="47530-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="47530-134">選択条件が .NET 型の任意の数を指定するか、選択範囲を設定するが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="47530-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="47530-135">選択条件を使用する方法の詳細については、[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47530-135">For more information about how selection conditions can be used, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="47530-136">参照</span><span class="sxs-lookup"><span data-stu-id="47530-136">See Also</span></span>

[<span data-ttu-id="47530-137">構成 (形式) のコントロールの SelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="47530-137">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="47530-138">構成 (形式) のコントロールの SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="47530-138">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="47530-139">構成 (形式) のコントロールの SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="47530-139">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="47530-140">構成 (形式) のコントロールの SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="47530-140">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="47530-141">構成 (形式) のコントロールの CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="47530-141">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="47530-142">Windows PowerShell の書式設定の書き込みとファイルの種類</span><span class="sxs-lookup"><span data-stu-id="47530-142">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
