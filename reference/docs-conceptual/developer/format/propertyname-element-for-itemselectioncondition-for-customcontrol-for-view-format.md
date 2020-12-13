---
ms.date: 09/13/2016
ms.topic: reference
title: View の CustomControl の ItemSelectionCondition の PropertyName 要素 (書式)
description: View の CustomControl の ItemSelectionCondition の PropertyName 要素 (書式)
ms.openlocfilehash: 5687bb781ce2db27b875f829147ee8b436f04adc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666129"
---
# <a name="propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="469db-103">View の CustomControl の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="469db-103">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="469db-104">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="469db-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="469db-105">このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、コントロールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="469db-105">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="469db-106">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="469db-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="469db-107">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (Format) CustomControl 要素 (形式) CustomControl for view (format) の CustomEntries for ビュー (形式) の CustomEntries を指定します。 Mentry for view (format) 式のバインド要素の CustomControl for view (format) ItemSelectionCondition 要素の式のバインドの CustomControl for view (format) の PropertyName 要素の CustomControl for ビューの ItemSelectionCondition (形式)</span><span class="sxs-lookup"><span data-stu-id="469db-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format) PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>

## <a name="syntax"></a><span data-ttu-id="469db-108">構文</span><span class="sxs-lookup"><span data-stu-id="469db-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="469db-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="469db-109">Attributes and Elements</span></span>

<span data-ttu-id="469db-110">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="469db-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="469db-111">属性</span><span class="sxs-lookup"><span data-stu-id="469db-111">Attributes</span></span>

<span data-ttu-id="469db-112">なし。</span><span class="sxs-lookup"><span data-stu-id="469db-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="469db-113">子要素</span><span class="sxs-lookup"><span data-stu-id="469db-113">Child Elements</span></span>

<span data-ttu-id="469db-114">なし。</span><span class="sxs-lookup"><span data-stu-id="469db-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="469db-115">親要素</span><span class="sxs-lookup"><span data-stu-id="469db-115">Parent Elements</span></span>

|<span data-ttu-id="469db-116">要素</span><span class="sxs-lookup"><span data-stu-id="469db-116">Element</span></span>|<span data-ttu-id="469db-117">説明</span><span class="sxs-lookup"><span data-stu-id="469db-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="469db-118">CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="469db-118">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="469db-119">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="469db-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="469db-120">テキスト値</span><span class="sxs-lookup"><span data-stu-id="469db-120">Text Value</span></span>

<span data-ttu-id="469db-121">条件をトリガーする .NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="469db-121">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="469db-122">解説</span><span class="sxs-lookup"><span data-stu-id="469db-122">Remarks</span></span>

<span data-ttu-id="469db-123">この要素が使用されている場合、選択条件を定義するときに [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) 要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="469db-123">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="469db-124">参照</span><span class="sxs-lookup"><span data-stu-id="469db-124">See Also</span></span>

[<span data-ttu-id="469db-125">View の CustomControl の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="469db-125">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="469db-126">CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="469db-126">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="469db-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="469db-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
