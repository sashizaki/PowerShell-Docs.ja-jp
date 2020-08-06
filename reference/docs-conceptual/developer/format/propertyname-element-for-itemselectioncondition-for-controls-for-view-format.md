---
title: ビューのコントロール (Format) の ItemSelectionCondition の PropertyName 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c6517b8f63e0511ce071926ac3ac39ba82e7ed21
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783485"
---
# <a name="propertyname-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="e8ca8-102">View の Controls の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e8ca8-102">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="e8ca8-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="e8ca8-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="e8ca8-104">このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、コントロールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8ca8-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="e8ca8-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8ca8-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="e8ca8-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (形式) コントロールのコントロールの要素 (書式) のコントロールの要素 (形式) コントロールのコントロール要素を表示するためのコントロールの CustomControl 要素 (形式) の CustomControl for View (書式) の Custommentry 要素コントロールの CustomEntries for view (format) Customentries 要素を使用して、ビュー (形式) の式のバインド要素を表示するためのコントロールの、ビュー (format) のバインド要素を表示するためのコントロールのバインド要素ビュー (format) のコントロールの ItemSelectionCondition のビュー (形式) の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="e8ca8-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e8ca8-107">構文</span><span class="sxs-lookup"><span data-stu-id="e8ca8-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e8ca8-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e8ca8-108">Attributes and Elements</span></span>

<span data-ttu-id="e8ca8-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="e8ca8-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e8ca8-110">属性</span><span class="sxs-lookup"><span data-stu-id="e8ca8-110">Attributes</span></span>

<span data-ttu-id="e8ca8-111">なし。</span><span class="sxs-lookup"><span data-stu-id="e8ca8-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e8ca8-112">子要素</span><span class="sxs-lookup"><span data-stu-id="e8ca8-112">Child Elements</span></span>

<span data-ttu-id="e8ca8-113">なし。</span><span class="sxs-lookup"><span data-stu-id="e8ca8-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e8ca8-114">親要素</span><span class="sxs-lookup"><span data-stu-id="e8ca8-114">Parent Elements</span></span>

|<span data-ttu-id="e8ca8-115">要素</span><span class="sxs-lookup"><span data-stu-id="e8ca8-115">Element</span></span>|<span data-ttu-id="e8ca8-116">説明</span><span class="sxs-lookup"><span data-stu-id="e8ca8-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e8ca8-117">ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="e8ca8-117">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="e8ca8-118">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="e8ca8-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e8ca8-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="e8ca8-119">Text Value</span></span>

<span data-ttu-id="e8ca8-120">条件をトリガーする .NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e8ca8-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="e8ca8-121">解説</span><span class="sxs-lookup"><span data-stu-id="e8ca8-121">Remarks</span></span>

<span data-ttu-id="e8ca8-122">この要素が使用されている場合、選択条件を定義するときに[ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e8ca8-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8ca8-123">参照</span><span class="sxs-lookup"><span data-stu-id="e8ca8-123">See Also</span></span>

[<span data-ttu-id="e8ca8-124">View の Controls の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e8ca8-124">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="e8ca8-125">ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="e8ca8-125">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="e8ca8-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="e8ca8-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
