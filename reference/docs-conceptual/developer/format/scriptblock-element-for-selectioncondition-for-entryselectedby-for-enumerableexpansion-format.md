---
ms.date: 09/13/2016
ms.topic: reference
title: EnumerableExpansion の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)
description: EnumerableExpansion の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)
ms.openlocfilehash: bd72a9bc914ea6543d8dab768b5e20e9a580ada7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664912"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="8fe37-103">EnumerableExpansion の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8fe37-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="8fe37-104">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="8fe37-104">Specifies the script that triggers the condition.</span></span>

<span data-ttu-id="8fe37-105">Configuration 要素 (Format) DefaultSettings 要素 (format) の列挙 able膨張要素 (format) 列挙 able膨張拡張要素 (format) の entryselectedby 要素 (format) に対して、enumerableexpansions (format) に対して、entryselectedby の Selectionselectedby を指定します。</span><span class="sxs-lookup"><span data-stu-id="8fe37-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8fe37-106">構文</span><span class="sxs-lookup"><span data-stu-id="8fe37-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8fe37-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8fe37-107">Attributes and Elements</span></span>

<span data-ttu-id="8fe37-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="8fe37-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8fe37-109">属性</span><span class="sxs-lookup"><span data-stu-id="8fe37-109">Attributes</span></span>

<span data-ttu-id="8fe37-110">なし。</span><span class="sxs-lookup"><span data-stu-id="8fe37-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8fe37-111">子要素</span><span class="sxs-lookup"><span data-stu-id="8fe37-111">Child Elements</span></span>

<span data-ttu-id="8fe37-112">なし。</span><span class="sxs-lookup"><span data-stu-id="8fe37-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8fe37-113">親要素</span><span class="sxs-lookup"><span data-stu-id="8fe37-113">Parent Elements</span></span>

|<span data-ttu-id="8fe37-114">要素</span><span class="sxs-lookup"><span data-stu-id="8fe37-114">Element</span></span>|<span data-ttu-id="8fe37-115">説明</span><span class="sxs-lookup"><span data-stu-id="8fe37-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8fe37-116">EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8fe37-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="8fe37-117">この定義のコレクションオブジェクトを展開するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="8fe37-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8fe37-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="8fe37-118">Text Value</span></span>

<span data-ttu-id="8fe37-119">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="8fe37-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="8fe37-120">解説</span><span class="sxs-lookup"><span data-stu-id="8fe37-120">Remarks</span></span>

<span data-ttu-id="8fe37-121">選択条件では、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="8fe37-121">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="8fe37-122">選択条件の使用方法の詳細については、「 [データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe37-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8fe37-123">参照</span><span class="sxs-lookup"><span data-stu-id="8fe37-123">See Also</span></span>

[<span data-ttu-id="8fe37-124">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="8fe37-124">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="8fe37-125">EnumerableExpansion の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8fe37-125">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="8fe37-126">EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8fe37-126">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="8fe37-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="8fe37-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
