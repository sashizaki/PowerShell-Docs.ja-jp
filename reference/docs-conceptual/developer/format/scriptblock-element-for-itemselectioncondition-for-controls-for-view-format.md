---
ms.date: 09/13/2016
ms.topic: reference
title: View の Controls の ItemSelectionCondition の ScriptBlock 要素 (書式)
description: View の Controls の ItemSelectionCondition の ScriptBlock 要素 (書式)
ms.openlocfilehash: c005215f7b7984541806d2f5de47372d536787ff
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665185"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="53382-103">View の Controls の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="53382-103">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="53382-104">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="53382-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="53382-105">このスクリプトがに評価されると、 `true` 条件が満たされ、コントロールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="53382-105">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="53382-106">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="53382-106">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="53382-107">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (形式) コントロールのコントロールの要素 (書式) のコントロールの要素 (形式) コントロールのコントロール要素を表示するためのコントロールの CustomControl 要素 (形式) の CustomControl for View (書式) の Custommentry 要素コントロールの CustomEntries for view (format) Customentries 要素を使用して、ビュー (形式) の式のバインド要素を表示するためのコントロールの、ビュー (format) ItemSelectionCondition 要素の要素を表示するためのコントロールのビュー (format) ScriptBlock 要素のバインド要素を表示するコントロールの ItemSelectionCondition の要素を表示 (Format)</span><span class="sxs-lookup"><span data-stu-id="53382-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="53382-108">構文</span><span class="sxs-lookup"><span data-stu-id="53382-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="53382-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="53382-109">Attributes and Elements</span></span>

<span data-ttu-id="53382-110">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="53382-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="53382-111">属性</span><span class="sxs-lookup"><span data-stu-id="53382-111">Attributes</span></span>

<span data-ttu-id="53382-112">なし。</span><span class="sxs-lookup"><span data-stu-id="53382-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="53382-113">子要素</span><span class="sxs-lookup"><span data-stu-id="53382-113">Child Elements</span></span>

<span data-ttu-id="53382-114">なし。</span><span class="sxs-lookup"><span data-stu-id="53382-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="53382-115">親要素</span><span class="sxs-lookup"><span data-stu-id="53382-115">Parent Elements</span></span>

|<span data-ttu-id="53382-116">要素</span><span class="sxs-lookup"><span data-stu-id="53382-116">Element</span></span>|<span data-ttu-id="53382-117">説明</span><span class="sxs-lookup"><span data-stu-id="53382-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="53382-118">ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="53382-118">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="53382-119">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="53382-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="53382-120">テキスト値</span><span class="sxs-lookup"><span data-stu-id="53382-120">Text Value</span></span>

<span data-ttu-id="53382-121">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="53382-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="53382-122">解説</span><span class="sxs-lookup"><span data-stu-id="53382-122">Remarks</span></span>

<span data-ttu-id="53382-123">この要素が使用されている場合、選択条件を定義するときに [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) 要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="53382-123">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="53382-124">参照</span><span class="sxs-lookup"><span data-stu-id="53382-124">See Also</span></span>

[<span data-ttu-id="53382-125">View の Controls の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="53382-125">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="53382-126">ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="53382-126">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="53382-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="53382-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
