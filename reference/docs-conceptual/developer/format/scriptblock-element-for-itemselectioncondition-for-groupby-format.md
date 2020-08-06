---
title: GroupBy (Format) の ItemSelectionCondition の ScriptBlock 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7738b180f328c7360275058cdb9dea01df6ea285
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787650"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-groupby-format"></a><span data-ttu-id="54124-102">GroupBy の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="54124-102">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="54124-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="54124-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="54124-104">このスクリプトがに評価されると、 `true` 条件が満たされ、コントロールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="54124-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="54124-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="54124-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="54124-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素の groupby (format) CustomControl 要素の groupby (形式) CustomControl の CustomControl の CustomEntry 要素に対して、groupby (Format) CustomEntry for groupby (形式) の式のバインド要素 groupby (format) ItemSelectionCondition 要素の場合は、groupby (format) 要素のバインド要素を指定します。 groupby (形式) の ItemSelectionCondition の ScriptBlock (format) ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="54124-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format) ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="54124-107">構文</span><span class="sxs-lookup"><span data-stu-id="54124-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="54124-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="54124-108">Attributes and Elements</span></span>

<span data-ttu-id="54124-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="54124-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="54124-110">属性</span><span class="sxs-lookup"><span data-stu-id="54124-110">Attributes</span></span>

<span data-ttu-id="54124-111">なし。</span><span class="sxs-lookup"><span data-stu-id="54124-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="54124-112">子要素</span><span class="sxs-lookup"><span data-stu-id="54124-112">Child Elements</span></span>

<span data-ttu-id="54124-113">なし。</span><span class="sxs-lookup"><span data-stu-id="54124-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="54124-114">親要素</span><span class="sxs-lookup"><span data-stu-id="54124-114">Parent Elements</span></span>

|<span data-ttu-id="54124-115">要素</span><span class="sxs-lookup"><span data-stu-id="54124-115">Element</span></span>|<span data-ttu-id="54124-116">説明</span><span class="sxs-lookup"><span data-stu-id="54124-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="54124-117">GroupBy の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="54124-117">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="54124-118">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="54124-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="54124-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="54124-119">Text Value</span></span>

<span data-ttu-id="54124-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="54124-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="54124-121">解説</span><span class="sxs-lookup"><span data-stu-id="54124-121">Remarks</span></span>

<span data-ttu-id="54124-122">この要素が使用されている場合、選択条件を定義するときに[PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="54124-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="54124-123">参照</span><span class="sxs-lookup"><span data-stu-id="54124-123">See Also</span></span>

[<span data-ttu-id="54124-124">GroupBy の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="54124-124">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="54124-125">GroupBy の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="54124-125">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)

[<span data-ttu-id="54124-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="54124-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
