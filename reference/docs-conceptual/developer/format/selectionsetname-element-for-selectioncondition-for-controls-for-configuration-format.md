---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration の Controls の SelectionCondition の SelectionSetName 要素 (書式)
description: Configuration の Controls の SelectionCondition の SelectionSetName 要素 (書式)
ms.openlocfilehash: 4177aace5a6a9374900e7339167c69b531c1e2e7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651669"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="668d7-103">Configuration の Controls の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="668d7-103">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="668d7-104">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="668d7-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="668d7-105">このセット内のいずれかの型が存在する場合、条件が満たされ、このコントロールを使用してオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="668d7-105">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="668d7-106">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="668d7-106">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="668d7-107">Configuration 要素 (Format) コントロールの構成 (format) コントロールの要素の構成 (形式) CustomControl 要素の構成のためのコントロールの CustomControl の構成 (形式) の CustomEntries 要素の構成 (書式設定) のためのコントロール要素の CustomControl の CustomEntry 要素構成 (形式) のためのコントロールに対する CustomEntry for コントロールの構成 (形式) の SelectionCondition 要素を構成するためのコントロールのためのコントロールの構成 (format) の SelectionSetName 要素の構成 (形式) のコントロールの SelectionCondition</span><span class="sxs-lookup"><span data-stu-id="668d7-107">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="668d7-108">構文</span><span class="sxs-lookup"><span data-stu-id="668d7-108">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="668d7-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="668d7-109">Attributes and Elements</span></span>

<span data-ttu-id="668d7-110">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="668d7-110">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="668d7-111">属性</span><span class="sxs-lookup"><span data-stu-id="668d7-111">Attributes</span></span>

<span data-ttu-id="668d7-112">なし。</span><span class="sxs-lookup"><span data-stu-id="668d7-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="668d7-113">子要素</span><span class="sxs-lookup"><span data-stu-id="668d7-113">Child Elements</span></span>

<span data-ttu-id="668d7-114">なし。</span><span class="sxs-lookup"><span data-stu-id="668d7-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="668d7-115">親要素</span><span class="sxs-lookup"><span data-stu-id="668d7-115">Parent Elements</span></span>

|<span data-ttu-id="668d7-116">要素</span><span class="sxs-lookup"><span data-stu-id="668d7-116">Element</span></span>|<span data-ttu-id="668d7-117">説明</span><span class="sxs-lookup"><span data-stu-id="668d7-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="668d7-118">Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="668d7-118">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="668d7-119">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="668d7-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="668d7-120">テキスト値</span><span class="sxs-lookup"><span data-stu-id="668d7-120">Text Value</span></span>

<span data-ttu-id="668d7-121">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="668d7-121">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="668d7-122">解説</span><span class="sxs-lookup"><span data-stu-id="668d7-122">Remarks</span></span>

<span data-ttu-id="668d7-123">選択セットは、書式設定ファイルによって定義される任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="668d7-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="668d7-124">選択セットの作成と参照の詳細については、「 [オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="668d7-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="668d7-125">選択条件では、選択セットまたは .NET 型を指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="668d7-125">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="668d7-126">選択条件の使用方法の詳細については、「 [データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="668d7-126">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="668d7-127">参照</span><span class="sxs-lookup"><span data-stu-id="668d7-127">See Also</span></span>

[<span data-ttu-id="668d7-128">Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="668d7-128">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="668d7-129">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="668d7-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="668d7-130">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="668d7-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="668d7-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="668d7-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
