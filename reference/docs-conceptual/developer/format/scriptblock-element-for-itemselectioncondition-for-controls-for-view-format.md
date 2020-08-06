---
title: ビューのコントロール (Format) の ItemSelectionCondition の ScriptBlock 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 74b3e23005f595c4c550320849cac5b196e9d479
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787667"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="16342-102">View の Controls の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="16342-102">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="16342-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="16342-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="16342-104">このスクリプトがに評価されると、 `true` 条件が満たされ、コントロールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="16342-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="16342-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="16342-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="16342-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (形式) コントロールのコントロールの要素 (書式) のコントロールの要素 (形式) コントロールのコントロール要素を表示するためのコントロールの CustomControl 要素 (形式) の CustomControl for View (書式) の Custommentry 要素コントロールの CustomEntries for view (format) Customentries 要素を使用して、ビュー (形式) の式のバインド要素を表示するためのコントロールの、ビュー (format) ItemSelectionCondition 要素の要素を表示するためのコントロールのビュー (format) ScriptBlock 要素のバインド要素を表示するコントロールの ItemSelectionCondition の要素を表示 (Format)</span><span class="sxs-lookup"><span data-stu-id="16342-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="16342-107">構文</span><span class="sxs-lookup"><span data-stu-id="16342-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="16342-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="16342-108">Attributes and Elements</span></span>

<span data-ttu-id="16342-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="16342-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="16342-110">属性</span><span class="sxs-lookup"><span data-stu-id="16342-110">Attributes</span></span>

<span data-ttu-id="16342-111">なし。</span><span class="sxs-lookup"><span data-stu-id="16342-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="16342-112">子要素</span><span class="sxs-lookup"><span data-stu-id="16342-112">Child Elements</span></span>

<span data-ttu-id="16342-113">なし。</span><span class="sxs-lookup"><span data-stu-id="16342-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="16342-114">親要素</span><span class="sxs-lookup"><span data-stu-id="16342-114">Parent Elements</span></span>

|<span data-ttu-id="16342-115">要素</span><span class="sxs-lookup"><span data-stu-id="16342-115">Element</span></span>|<span data-ttu-id="16342-116">説明</span><span class="sxs-lookup"><span data-stu-id="16342-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="16342-117">ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="16342-117">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="16342-118">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="16342-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="16342-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="16342-119">Text Value</span></span>

<span data-ttu-id="16342-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="16342-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="16342-121">解説</span><span class="sxs-lookup"><span data-stu-id="16342-121">Remarks</span></span>

<span data-ttu-id="16342-122">この要素が使用されている場合、選択条件を定義するときに[PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="16342-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="16342-123">参照</span><span class="sxs-lookup"><span data-stu-id="16342-123">See Also</span></span>

[<span data-ttu-id="16342-124">View の Controls の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="16342-124">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="16342-125">ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="16342-125">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="16342-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="16342-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
