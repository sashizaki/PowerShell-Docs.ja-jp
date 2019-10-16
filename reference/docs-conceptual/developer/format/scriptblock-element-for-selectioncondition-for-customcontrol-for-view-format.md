---
title: CustomControl for View (Format) の SelectionCondition の ScriptBlock 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7031fa8b-3e2b-4ea8-89cb-95171f467b5a
caps.latest.revision: 6
ms.openlocfilehash: e55d1c5aa533005b258ecbbbf3ed9d55f852eab6
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368641"
---
# <a name="scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="528f5-102">View の CustomControl の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="528f5-102">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="528f5-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="528f5-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="528f5-104">このスクリプトが `true` に評価されると、条件が満たされ、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="528f5-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="528f5-105">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="528f5-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="528f5-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の CustomControl 要素を表示するための CustomControl for ビュー (形式) の Custommentry 要素の CustomControl for View (Format) CustomControl for view (Format) の SelectionCondition の CustomControl for View (format) ScriptBlock 要素について、CustomEntry for CustomControl for view (format) の SelectionCondition 要素を検索するための CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="528f5-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="528f5-107">構文</span><span class="sxs-lookup"><span data-stu-id="528f5-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="528f5-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="528f5-108">Attributes and Elements</span></span>

<span data-ttu-id="528f5-109">次のセクションでは、属性、子要素、`ScriptBlock` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="528f5-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="528f5-110">属性</span><span class="sxs-lookup"><span data-stu-id="528f5-110">Attributes</span></span>

<span data-ttu-id="528f5-111">なし。</span><span class="sxs-lookup"><span data-stu-id="528f5-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="528f5-112">子要素</span><span class="sxs-lookup"><span data-stu-id="528f5-112">Child Elements</span></span>

<span data-ttu-id="528f5-113">なし。</span><span class="sxs-lookup"><span data-stu-id="528f5-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="528f5-114">親要素</span><span class="sxs-lookup"><span data-stu-id="528f5-114">Parent Elements</span></span>

|<span data-ttu-id="528f5-115">要素</span><span class="sxs-lookup"><span data-stu-id="528f5-115">Element</span></span>|<span data-ttu-id="528f5-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="528f5-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="528f5-117">CustomControl for ビュー (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="528f5-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="528f5-118">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="528f5-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="528f5-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="528f5-119">Text Value</span></span>

<span data-ttu-id="528f5-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="528f5-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="528f5-121">コメント</span><span class="sxs-lookup"><span data-stu-id="528f5-121">Remarks</span></span>

<span data-ttu-id="528f5-122">選択条件には、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="528f5-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="528f5-123">選択条件の使用方法の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="528f5-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="528f5-124">参照</span><span class="sxs-lookup"><span data-stu-id="528f5-124">See Also</span></span>

[<span data-ttu-id="528f5-125">CustomControl for ビュー (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="528f5-125">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="528f5-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="528f5-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
