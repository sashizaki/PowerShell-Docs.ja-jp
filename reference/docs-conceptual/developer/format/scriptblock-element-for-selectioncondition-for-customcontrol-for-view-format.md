---
ms.date: 09/13/2016
ms.topic: reference
title: View の CustomControl の SelectionCondition の ScriptBlock 要素 (書式)
description: View の CustomControl の SelectionCondition の ScriptBlock 要素 (書式)
ms.openlocfilehash: 78b977548243b6f3a658f15a0249d8cad12e2f1b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664922"
---
# <a name="scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="fae00-103">View の CustomControl の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="fae00-103">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="fae00-104">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="fae00-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="fae00-105">このスクリプトがに評価されると、 `true` 条件が満たされ、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="fae00-105">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="fae00-106">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="fae00-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="fae00-107">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (format) CustomControl のビュー (形式) の CustomEntries 要素の CustomControl for view (format) の CustomEntries の要素の CustomControl for ビューの CustomEntries に使用します。 (フォーマット) CustomControl for view (Format) の SelectionCondition の CustomControl for ビュー (format) ScriptBlock 要素の EntrySelectedBy for CustomControl for ビュー (形式) の SelectionCondition 要素のための Customentries 要素</span><span class="sxs-lookup"><span data-stu-id="fae00-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fae00-108">構文</span><span class="sxs-lookup"><span data-stu-id="fae00-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fae00-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fae00-109">Attributes and Elements</span></span>

<span data-ttu-id="fae00-110">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="fae00-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fae00-111">属性</span><span class="sxs-lookup"><span data-stu-id="fae00-111">Attributes</span></span>

<span data-ttu-id="fae00-112">なし。</span><span class="sxs-lookup"><span data-stu-id="fae00-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fae00-113">子要素</span><span class="sxs-lookup"><span data-stu-id="fae00-113">Child Elements</span></span>

<span data-ttu-id="fae00-114">なし。</span><span class="sxs-lookup"><span data-stu-id="fae00-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fae00-115">親要素</span><span class="sxs-lookup"><span data-stu-id="fae00-115">Parent Elements</span></span>

|<span data-ttu-id="fae00-116">要素</span><span class="sxs-lookup"><span data-stu-id="fae00-116">Element</span></span>|<span data-ttu-id="fae00-117">説明</span><span class="sxs-lookup"><span data-stu-id="fae00-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fae00-118">CustomControl for ビュー (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="fae00-118">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="fae00-119">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="fae00-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fae00-120">テキスト値</span><span class="sxs-lookup"><span data-stu-id="fae00-120">Text Value</span></span>

<span data-ttu-id="fae00-121">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="fae00-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="fae00-122">解説</span><span class="sxs-lookup"><span data-stu-id="fae00-122">Remarks</span></span>

<span data-ttu-id="fae00-123">選択条件には、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="fae00-123">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="fae00-124">選択条件の使用方法の詳細については、「 [データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fae00-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fae00-125">参照</span><span class="sxs-lookup"><span data-stu-id="fae00-125">See Also</span></span>

[<span data-ttu-id="fae00-126">CustomControl for ビュー (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="fae00-126">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="fae00-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="fae00-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
