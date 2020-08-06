---
title: ビューのコントロールの SelectionCondition の ScriptBlock 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e5f4295a989307cb6ffb655c2c39596f3d1ea806
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785423"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="d7d99-102">View の Controls の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d7d99-102">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="d7d99-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d7d99-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="d7d99-104">このスクリプトがに評価されると、 `true` 条件が満たされ、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d7d99-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="d7d99-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d7d99-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="d7d99-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールのコントロールの要素 (形式) コントロールのコントロール要素 (format) のコントロールの要素 (書式) を制御するためのコントロールの要素 (書式) の CustomControl 要素 (format) のコントロールの CustomControl のカスタム CustomEntries ビュー (format) のためのコントロールの CustomEntries の参照 (書式) の参照 (形式) の SelectionCondition 要素を表示するためのコントロールの場合は、ビュー (形式) のコントロールの SelectionCondition のコントロールに対して、ビュー (format) の SelectionCondition 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="d7d99-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d7d99-107">構文</span><span class="sxs-lookup"><span data-stu-id="d7d99-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d7d99-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d7d99-108">Attributes and Elements</span></span>

<span data-ttu-id="d7d99-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="d7d99-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d7d99-110">属性</span><span class="sxs-lookup"><span data-stu-id="d7d99-110">Attributes</span></span>

<span data-ttu-id="d7d99-111">なし。</span><span class="sxs-lookup"><span data-stu-id="d7d99-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d7d99-112">子要素</span><span class="sxs-lookup"><span data-stu-id="d7d99-112">Child Elements</span></span>

<span data-ttu-id="d7d99-113">なし。</span><span class="sxs-lookup"><span data-stu-id="d7d99-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d7d99-114">親要素</span><span class="sxs-lookup"><span data-stu-id="d7d99-114">Parent Elements</span></span>

|<span data-ttu-id="d7d99-115">要素</span><span class="sxs-lookup"><span data-stu-id="d7d99-115">Element</span></span>|<span data-ttu-id="d7d99-116">説明</span><span class="sxs-lookup"><span data-stu-id="d7d99-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d7d99-117">View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d7d99-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="d7d99-118">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="d7d99-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d7d99-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="d7d99-119">Text Value</span></span>

<span data-ttu-id="d7d99-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d7d99-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="d7d99-121">解説</span><span class="sxs-lookup"><span data-stu-id="d7d99-121">Remarks</span></span>

<span data-ttu-id="d7d99-122">選択条件には、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d7d99-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="d7d99-123">選択条件の使用方法の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7d99-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d7d99-124">参照</span><span class="sxs-lookup"><span data-stu-id="d7d99-124">See Also</span></span>

[<span data-ttu-id="d7d99-125">View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d7d99-125">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="d7d99-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="d7d99-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
