---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の SelectionCondition の PropertyName 要素 (書式)
description: GroupBy の SelectionCondition の PropertyName 要素 (書式)
ms.openlocfilehash: b89fead6185c88ca03956dc265135833696b91d7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665670"
---
# <a name="propertyname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="ac7eb-103">GroupBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ac7eb-103">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="ac7eb-104">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="ac7eb-105">このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-105">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="ac7eb-106">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="ac7eb-107">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素を groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素 groupby (format) の CustomControl の Entryselectedby for groupby (format) Selectionselectedby 要素について、groupby (format) の selectioncondition 要素に対して groupby (形式) の SelectionCondition 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ac7eb-108">構文</span><span class="sxs-lookup"><span data-stu-id="ac7eb-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ac7eb-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ac7eb-109">Attributes and Elements</span></span>

<span data-ttu-id="ac7eb-110">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ac7eb-111">属性</span><span class="sxs-lookup"><span data-stu-id="ac7eb-111">Attributes</span></span>

<span data-ttu-id="ac7eb-112">なし。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ac7eb-113">子要素</span><span class="sxs-lookup"><span data-stu-id="ac7eb-113">Child Elements</span></span>

<span data-ttu-id="ac7eb-114">なし。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ac7eb-115">親要素</span><span class="sxs-lookup"><span data-stu-id="ac7eb-115">Parent Elements</span></span>

|<span data-ttu-id="ac7eb-116">要素</span><span class="sxs-lookup"><span data-stu-id="ac7eb-116">Element</span></span>|<span data-ttu-id="ac7eb-117">説明</span><span class="sxs-lookup"><span data-stu-id="ac7eb-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ac7eb-118">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ac7eb-118">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="ac7eb-119">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ac7eb-120">テキスト値</span><span class="sxs-lookup"><span data-stu-id="ac7eb-120">Text Value</span></span>

<span data-ttu-id="ac7eb-121">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-121">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="ac7eb-122">解説</span><span class="sxs-lookup"><span data-stu-id="ac7eb-122">Remarks</span></span>

<span data-ttu-id="ac7eb-123">選択条件には、少なくとも1つのプロパティ名またはスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-123">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="ac7eb-124">選択条件の使用方法の詳細については、「 [データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ac7eb-125">参照</span><span class="sxs-lookup"><span data-stu-id="ac7eb-125">See Also</span></span>

[<span data-ttu-id="ac7eb-126">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ac7eb-126">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="ac7eb-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="ac7eb-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
