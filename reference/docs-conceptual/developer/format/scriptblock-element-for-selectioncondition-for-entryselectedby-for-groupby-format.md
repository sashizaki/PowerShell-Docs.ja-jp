---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)
description: GroupBy の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)
ms.openlocfilehash: cc92aa642b42fa3e4c4f974e954d5eac73179de3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664879"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="ff369-103">GroupBy の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ff369-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="ff369-104">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ff369-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="ff369-105">このスクリプトがに評価されると、 `true` 条件が満たされ、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ff369-105">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="ff369-106">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ff369-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="ff369-107">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素を groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素 CustomControl for GroupBy (Format) の CustomEntry for groupby (形式) Selectionselectedby 要素に対して、groupby (format) の SelectionCondition に対する Entry(format) ScriptBlock 要素の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="ff369-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ff369-108">構文</span><span class="sxs-lookup"><span data-stu-id="ff369-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ff369-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ff369-109">Attributes and Elements</span></span>

<span data-ttu-id="ff369-110">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="ff369-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ff369-111">属性</span><span class="sxs-lookup"><span data-stu-id="ff369-111">Attributes</span></span>

<span data-ttu-id="ff369-112">なし。</span><span class="sxs-lookup"><span data-stu-id="ff369-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ff369-113">子要素</span><span class="sxs-lookup"><span data-stu-id="ff369-113">Child Elements</span></span>

<span data-ttu-id="ff369-114">なし。</span><span class="sxs-lookup"><span data-stu-id="ff369-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ff369-115">親要素</span><span class="sxs-lookup"><span data-stu-id="ff369-115">Parent Elements</span></span>

|<span data-ttu-id="ff369-116">要素</span><span class="sxs-lookup"><span data-stu-id="ff369-116">Element</span></span>|<span data-ttu-id="ff369-117">説明</span><span class="sxs-lookup"><span data-stu-id="ff369-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ff369-118">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ff369-118">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="ff369-119">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="ff369-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ff369-120">テキスト値</span><span class="sxs-lookup"><span data-stu-id="ff369-120">Text Value</span></span>

<span data-ttu-id="ff369-121">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ff369-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff369-122">解説</span><span class="sxs-lookup"><span data-stu-id="ff369-122">Remarks</span></span>

<span data-ttu-id="ff369-123">選択条件には、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="ff369-123">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="ff369-124">選択条件の使用方法の詳細については、「 [データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff369-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ff369-125">参照</span><span class="sxs-lookup"><span data-stu-id="ff369-125">See Also</span></span>

[<span data-ttu-id="ff369-126">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ff369-126">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="ff369-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="ff369-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
