---
title: View (Format) の CustomControl の ItemSelectionCondition の ScriptBlock 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 31873e886af04f8eedaf859af1d6bc1d5bcfdbf7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772877"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="88a24-102">View の CustomControl の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="88a24-102">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="88a24-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="88a24-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="88a24-104">このスクリプトがに評価されると、 `true` 条件が満たされ、コントロールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="88a24-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="88a24-105">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="88a24-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="88a24-106">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (Format) CustomControl 要素 (形式) CustomControl for view (format) の CustomEntries for ビュー (形式) の CustomEntries を指定します。 Mentry for view (format) 式のバインド要素の CustomControl for view (format) ItemSelectionCondition 要素の CustomControl for view (format) ScriptBlock 要素の CustomControl for ビューの ItemSelectionCondition のバインド要素</span><span class="sxs-lookup"><span data-stu-id="88a24-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format) ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="88a24-107">構文</span><span class="sxs-lookup"><span data-stu-id="88a24-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="88a24-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="88a24-108">Attributes and Elements</span></span>

<span data-ttu-id="88a24-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="88a24-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="88a24-110">属性</span><span class="sxs-lookup"><span data-stu-id="88a24-110">Attributes</span></span>

<span data-ttu-id="88a24-111">なし。</span><span class="sxs-lookup"><span data-stu-id="88a24-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="88a24-112">子要素</span><span class="sxs-lookup"><span data-stu-id="88a24-112">Child Elements</span></span>

<span data-ttu-id="88a24-113">なし。</span><span class="sxs-lookup"><span data-stu-id="88a24-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="88a24-114">親要素</span><span class="sxs-lookup"><span data-stu-id="88a24-114">Parent Elements</span></span>

|<span data-ttu-id="88a24-115">要素</span><span class="sxs-lookup"><span data-stu-id="88a24-115">Element</span></span>|<span data-ttu-id="88a24-116">説明</span><span class="sxs-lookup"><span data-stu-id="88a24-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="88a24-117">CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="88a24-117">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="88a24-118">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="88a24-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="88a24-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="88a24-119">Text Value</span></span>

<span data-ttu-id="88a24-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="88a24-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="88a24-121">解説</span><span class="sxs-lookup"><span data-stu-id="88a24-121">Remarks</span></span>

<span data-ttu-id="88a24-122">この要素が使用されている場合、選択条件を定義するときに[PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="88a24-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="88a24-123">参照</span><span class="sxs-lookup"><span data-stu-id="88a24-123">See Also</span></span>

[<span data-ttu-id="88a24-124">View の CustomControl の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="88a24-124">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="88a24-125">CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="88a24-125">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="88a24-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="88a24-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
