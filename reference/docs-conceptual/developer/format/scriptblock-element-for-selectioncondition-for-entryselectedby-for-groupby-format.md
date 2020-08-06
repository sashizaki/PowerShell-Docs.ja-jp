---
title: GroupBy (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e70e1555a8f2fe0d15d3e864d80d35527af81b03
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785389"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="1535c-102">GroupBy の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1535c-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="1535c-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="1535c-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="1535c-104">このスクリプトがに評価されると、 `true` 条件が満たされ、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1535c-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="1535c-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1535c-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="1535c-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素を groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素 CustomControl for GroupBy (Format) の CustomEntry for groupby (形式) Selectionselectedby 要素に対して、groupby (format) の SelectionCondition に対する Entry(format) ScriptBlock 要素の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="1535c-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1535c-107">構文</span><span class="sxs-lookup"><span data-stu-id="1535c-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1535c-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1535c-108">Attributes and Elements</span></span>

<span data-ttu-id="1535c-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="1535c-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1535c-110">属性</span><span class="sxs-lookup"><span data-stu-id="1535c-110">Attributes</span></span>

<span data-ttu-id="1535c-111">なし。</span><span class="sxs-lookup"><span data-stu-id="1535c-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1535c-112">子要素</span><span class="sxs-lookup"><span data-stu-id="1535c-112">Child Elements</span></span>

<span data-ttu-id="1535c-113">なし。</span><span class="sxs-lookup"><span data-stu-id="1535c-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1535c-114">親要素</span><span class="sxs-lookup"><span data-stu-id="1535c-114">Parent Elements</span></span>

|<span data-ttu-id="1535c-115">要素</span><span class="sxs-lookup"><span data-stu-id="1535c-115">Element</span></span>|<span data-ttu-id="1535c-116">説明</span><span class="sxs-lookup"><span data-stu-id="1535c-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1535c-117">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1535c-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="1535c-118">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="1535c-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1535c-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="1535c-119">Text Value</span></span>

<span data-ttu-id="1535c-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="1535c-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="1535c-121">解説</span><span class="sxs-lookup"><span data-stu-id="1535c-121">Remarks</span></span>

<span data-ttu-id="1535c-122">選択条件には、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="1535c-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="1535c-123">選択条件の使用方法の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1535c-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1535c-124">参照</span><span class="sxs-lookup"><span data-stu-id="1535c-124">See Also</span></span>

[<span data-ttu-id="1535c-125">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1535c-125">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="1535c-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="1535c-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
