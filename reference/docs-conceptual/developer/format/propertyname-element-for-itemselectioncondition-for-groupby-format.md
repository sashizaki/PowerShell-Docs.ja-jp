---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の ItemSelectionCondition の PropertyName 要素 (書式)
description: GroupBy の ItemSelectionCondition の PropertyName 要素 (書式)
ms.openlocfilehash: 9667a389ded33d0744f0f7f8d739635a8b21d98b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666112"
---
# <a name="propertyname-element-for-itemselectioncondition-for-groupby-format"></a><span data-ttu-id="f4256-103">GroupBy の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f4256-103">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="f4256-104">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4256-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="f4256-105">このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、コントロールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f4256-105">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="f4256-106">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f4256-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="f4256-107">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素の groupby (format) CustomControl 要素の groupby (形式) CustomControl の CustomControl の CustomEntry 要素に対して、groupby (Format) CustomEntry for groupby (形式) の式のバインド要素 groupby (format) ItemSelectionCondition 要素の、groupby (書式) の ItemSelectionCondition のオブジェクトのバインドのバインド要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4256-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format) PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f4256-108">構文</span><span class="sxs-lookup"><span data-stu-id="f4256-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f4256-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f4256-109">Attributes and Elements</span></span>

<span data-ttu-id="f4256-110">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="f4256-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f4256-111">属性</span><span class="sxs-lookup"><span data-stu-id="f4256-111">Attributes</span></span>

<span data-ttu-id="f4256-112">なし。</span><span class="sxs-lookup"><span data-stu-id="f4256-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f4256-113">子要素</span><span class="sxs-lookup"><span data-stu-id="f4256-113">Child Elements</span></span>

<span data-ttu-id="f4256-114">なし。</span><span class="sxs-lookup"><span data-stu-id="f4256-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f4256-115">親要素</span><span class="sxs-lookup"><span data-stu-id="f4256-115">Parent Elements</span></span>

|<span data-ttu-id="f4256-116">要素</span><span class="sxs-lookup"><span data-stu-id="f4256-116">Element</span></span>|<span data-ttu-id="f4256-117">説明</span><span class="sxs-lookup"><span data-stu-id="f4256-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f4256-118">GroupBy の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f4256-118">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="f4256-119">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="f4256-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f4256-120">テキスト値</span><span class="sxs-lookup"><span data-stu-id="f4256-120">Text Value</span></span>

<span data-ttu-id="f4256-121">条件をトリガーする .NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4256-121">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4256-122">解説</span><span class="sxs-lookup"><span data-stu-id="f4256-122">Remarks</span></span>

<span data-ttu-id="f4256-123">この要素が使用されている場合、選択条件を定義するときに [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md) 要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f4256-123">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4256-124">参照</span><span class="sxs-lookup"><span data-stu-id="f4256-124">See Also</span></span>

[<span data-ttu-id="f4256-125">GroupBy の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f4256-125">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)

[<span data-ttu-id="f4256-126">GroupBy の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f4256-126">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="f4256-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="f4256-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
