---
title: 構成用のコントロール (Format) の EntrySelectedBy の SelectionCondition 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 748aa1aa0ba603a44334d9401e9e2c0e68f14e03
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783417"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="c0b2a-102">Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c0b2a-102">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="c0b2a-103">共通のコントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="c0b2a-103">Defines a condition that must exist for a common control definition to be used.</span></span> <span data-ttu-id="c0b2a-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c0b2a-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="c0b2a-105">Configuration 要素 (Format) コントロールの configuration (format) コントロールの要素の構成 (format) CustomControl 要素の構成のためのコントロールの CustomControl の構成 (形式) の CustomEntries 要素の構成 (書式設定用コントロール) CustomControl のためのコントロールのためのコントロールのための構成 (形式) の構成 (形式) のために、customentry for Configuration (形式) の SelectionCondition 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0b2a-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c0b2a-106">構文</span><span class="sxs-lookup"><span data-stu-id="c0b2a-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c0b2a-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c0b2a-107">Attributes and Elements</span></span>

<span data-ttu-id="c0b2a-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="c0b2a-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c0b2a-109">属性</span><span class="sxs-lookup"><span data-stu-id="c0b2a-109">Attributes</span></span>

<span data-ttu-id="c0b2a-110">なし。</span><span class="sxs-lookup"><span data-stu-id="c0b2a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c0b2a-111">子要素</span><span class="sxs-lookup"><span data-stu-id="c0b2a-111">Child Elements</span></span>

|<span data-ttu-id="c0b2a-112">要素</span><span class="sxs-lookup"><span data-stu-id="c0b2a-112">Element</span></span>|<span data-ttu-id="c0b2a-113">説明</span><span class="sxs-lookup"><span data-stu-id="c0b2a-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c0b2a-114">Configuration の Controls の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c0b2a-114">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="c0b2a-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c0b2a-115">Optional element.</span></span><br /><br /> <span data-ttu-id="c0b2a-116">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0b2a-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="c0b2a-117">Configuration の Controls の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c0b2a-117">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="c0b2a-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c0b2a-118">Optional element.</span></span><br /><br /> <span data-ttu-id="c0b2a-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0b2a-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="c0b2a-120">Configuration の Controls の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c0b2a-120">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="c0b2a-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c0b2a-121">Optional element.</span></span><br /><br /> <span data-ttu-id="c0b2a-122">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0b2a-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="c0b2a-123">Configuration の Controls の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c0b2a-123">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="c0b2a-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c0b2a-124">Optional element.</span></span><br /><br /> <span data-ttu-id="c0b2a-125">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0b2a-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c0b2a-126">親要素</span><span class="sxs-lookup"><span data-stu-id="c0b2a-126">Parent Elements</span></span>

|<span data-ttu-id="c0b2a-127">要素</span><span class="sxs-lookup"><span data-stu-id="c0b2a-127">Element</span></span>|<span data-ttu-id="c0b2a-128">説明</span><span class="sxs-lookup"><span data-stu-id="c0b2a-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c0b2a-129">Configuration の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c0b2a-129">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="c0b2a-130">コモンコントロール定義のこのエントリを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="c0b2a-130">Defines the .NET types that use this entry of the common control definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c0b2a-131">解説</span><span class="sxs-lookup"><span data-stu-id="c0b2a-131">Remarks</span></span>

<span data-ttu-id="c0b2a-132">選択条件を定義するときは、次のガイドラインに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0b2a-132">The following guidelines must be followed when defining a selection condition:</span></span>

- <span data-ttu-id="c0b2a-133">選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c0b2a-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="c0b2a-134">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c0b2a-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="c0b2a-135">選択条件を使用する方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0b2a-135">For more information about how selection conditions can be used, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c0b2a-136">参照</span><span class="sxs-lookup"><span data-stu-id="c0b2a-136">See Also</span></span>

[<span data-ttu-id="c0b2a-137">Configuration の Controls の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c0b2a-137">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="c0b2a-138">Configuration の Controls の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c0b2a-138">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="c0b2a-139">Configuration の Controls の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c0b2a-139">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="c0b2a-140">Configuration の Controls の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c0b2a-140">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="c0b2a-141">Configuration の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c0b2a-141">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="c0b2a-142">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="c0b2a-142">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
