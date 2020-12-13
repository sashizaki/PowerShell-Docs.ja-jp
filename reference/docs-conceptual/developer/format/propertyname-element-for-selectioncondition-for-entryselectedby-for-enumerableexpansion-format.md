---
ms.date: 09/13/2016
ms.topic: reference
title: EnumerableExpansion の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)
description: EnumerableExpansion の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)
ms.openlocfilehash: 8e28118894661b50e90a5ccc86a36fbbe77e4b03
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665840"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="765e8-103">EnumerableExpansion の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="765e8-103">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="765e8-104">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="765e8-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="765e8-105">このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="765e8-105">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="765e8-106">Configuration 要素 (Format) DefaultSettings Element (format) 列挙 able膨張要素 (format) 列挙 able膨張の要素 (format) entryselectedby の要素 (format) の entryselectedby の Selectionselectedby 要素に対して、entryselectedby (format) の selectioncondition 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="765e8-106">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="765e8-107">構文</span><span class="sxs-lookup"><span data-stu-id="765e8-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="765e8-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="765e8-108">Attributes and Elements</span></span>

<span data-ttu-id="765e8-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="765e8-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="765e8-110">属性</span><span class="sxs-lookup"><span data-stu-id="765e8-110">Attributes</span></span>

<span data-ttu-id="765e8-111">なし。</span><span class="sxs-lookup"><span data-stu-id="765e8-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="765e8-112">子要素</span><span class="sxs-lookup"><span data-stu-id="765e8-112">Child Elements</span></span>

<span data-ttu-id="765e8-113">なし。</span><span class="sxs-lookup"><span data-stu-id="765e8-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="765e8-114">親要素</span><span class="sxs-lookup"><span data-stu-id="765e8-114">Parent Elements</span></span>

|<span data-ttu-id="765e8-115">要素</span><span class="sxs-lookup"><span data-stu-id="765e8-115">Element</span></span>|<span data-ttu-id="765e8-116">説明</span><span class="sxs-lookup"><span data-stu-id="765e8-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="765e8-117">EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="765e8-117">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="765e8-118">この定義のコレクションオブジェクトを展開するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="765e8-118">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="765e8-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="765e8-119">Text Value</span></span>

<span data-ttu-id="765e8-120">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="765e8-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="765e8-121">解説</span><span class="sxs-lookup"><span data-stu-id="765e8-121">Remarks</span></span>

<span data-ttu-id="765e8-122">選択条件では、少なくとも1つのプロパティ名または評価対象のスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="765e8-122">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="765e8-123">選択条件の使用方法の詳細については、「 [データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="765e8-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="765e8-124">参照</span><span class="sxs-lookup"><span data-stu-id="765e8-124">See Also</span></span>

[<span data-ttu-id="765e8-125">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="765e8-125">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="765e8-126">EnumerableExpansion の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="765e8-126">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="765e8-127">EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="765e8-127">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="765e8-128">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="765e8-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
