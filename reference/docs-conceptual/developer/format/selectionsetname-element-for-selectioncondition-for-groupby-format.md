---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の SelectionCondition の SelectionSetName 要素 (書式)
description: GroupBy の SelectionCondition の SelectionSetName 要素 (書式)
ms.openlocfilehash: a4f28c1caba3790718b99f63659cb0cbed8def16
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654990"
---
# <a name="selectionsetname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="2dba3-103">GroupBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2dba3-103">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="2dba3-104">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="2dba3-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="2dba3-105">このセット内のいずれかの型が存在する場合、条件が満たされ、このコントロールを使用してオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2dba3-105">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="2dba3-106">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2dba3-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="2dba3-107">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素を groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素 CustomControl for groupby (Format) の CustomEntry for groupby (format) Selectionselectedby 要素の EntrySelectedBy を使用して groupby (format) SelectionSetName 要素を指定して、GroupBy (形式) の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="2dba3-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2dba3-108">構文</span><span class="sxs-lookup"><span data-stu-id="2dba3-108">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2dba3-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2dba3-109">Attributes and Elements</span></span>

<span data-ttu-id="2dba3-110">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="2dba3-110">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2dba3-111">属性</span><span class="sxs-lookup"><span data-stu-id="2dba3-111">Attributes</span></span>

<span data-ttu-id="2dba3-112">なし。</span><span class="sxs-lookup"><span data-stu-id="2dba3-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2dba3-113">子要素</span><span class="sxs-lookup"><span data-stu-id="2dba3-113">Child Elements</span></span>

<span data-ttu-id="2dba3-114">なし。</span><span class="sxs-lookup"><span data-stu-id="2dba3-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2dba3-115">親要素</span><span class="sxs-lookup"><span data-stu-id="2dba3-115">Parent Elements</span></span>

|<span data-ttu-id="2dba3-116">要素</span><span class="sxs-lookup"><span data-stu-id="2dba3-116">Element</span></span>|<span data-ttu-id="2dba3-117">説明</span><span class="sxs-lookup"><span data-stu-id="2dba3-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2dba3-118">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2dba3-118">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="2dba3-119">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="2dba3-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2dba3-120">テキスト値</span><span class="sxs-lookup"><span data-stu-id="2dba3-120">Text Value</span></span>

<span data-ttu-id="2dba3-121">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2dba3-121">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="2dba3-122">解説</span><span class="sxs-lookup"><span data-stu-id="2dba3-122">Remarks</span></span>

<span data-ttu-id="2dba3-123">選択セットは、書式設定ファイルによって定義される任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="2dba3-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="2dba3-124">選択セットの作成と参照の詳細については、「 [選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dba3-124">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="2dba3-125">この要素が指定されている場合、 [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md) 要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="2dba3-125">When this element is specified, you cannot specify the [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md) element.</span></span> <span data-ttu-id="2dba3-126">選択条件の定義の詳細については、「 [データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dba3-126">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2dba3-127">参照</span><span class="sxs-lookup"><span data-stu-id="2dba3-127">See Also</span></span>

[<span data-ttu-id="2dba3-128">GroupBy の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2dba3-128">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="2dba3-129">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2dba3-129">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="2dba3-130">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="2dba3-130">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="2dba3-131">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="2dba3-131">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="2dba3-132">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="2dba3-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
