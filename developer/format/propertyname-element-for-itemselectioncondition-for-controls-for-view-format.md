---
title: コントロールが表示されます (形式) の ItemSelectionCondition PropertyName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba3955bc-f3a1-4ef6-86ac-80ffc133ad1b
caps.latest.revision: 6
ms.openlocfilehash: 28ad31be4be7be20f1f43ea1b69ad5d294de86f6
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62075853"
---
# <a name="propertyname-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="5ad61-102">View の Controls の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5ad61-102">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="5ad61-103">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="5ad61-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="5ad61-104">このプロパティが存在するかを評価すると`true`条件が満たされると、およびコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ad61-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="5ad61-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5ad61-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="5ad61-106">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry CustomItem ビュー (形式) のコントロールのビュー (形式) ExpressionBinding 要素のコントロールのビュー (形式) CustomItem 要素のコントロールのビュー (形式) CustomEntry 要素のカスタム コントロールExpressionBinding ItemSelectionCondition ビュー (形式) のコントロールのビュー (形式) PropertyName 要素のコントロールの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="5ad61-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5ad61-107">構文</span><span class="sxs-lookup"><span data-stu-id="5ad61-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5ad61-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5ad61-108">Attributes and Elements</span></span>

<span data-ttu-id="5ad61-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。</span><span class="sxs-lookup"><span data-stu-id="5ad61-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5ad61-110">属性</span><span class="sxs-lookup"><span data-stu-id="5ad61-110">Attributes</span></span>

<span data-ttu-id="5ad61-111">なし。</span><span class="sxs-lookup"><span data-stu-id="5ad61-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5ad61-112">子要素</span><span class="sxs-lookup"><span data-stu-id="5ad61-112">Child Elements</span></span>

<span data-ttu-id="5ad61-113">なし。</span><span class="sxs-lookup"><span data-stu-id="5ad61-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5ad61-114">親要素</span><span class="sxs-lookup"><span data-stu-id="5ad61-114">Parent Elements</span></span>

|<span data-ttu-id="5ad61-115">要素</span><span class="sxs-lookup"><span data-stu-id="5ad61-115">Element</span></span>|<span data-ttu-id="5ad61-116">説明</span><span class="sxs-lookup"><span data-stu-id="5ad61-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5ad61-117">コントロールが表示されます (形式) の ExpressionBinding の ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="5ad61-117">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="5ad61-118">このコントロールを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="5ad61-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5ad61-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="5ad61-119">Text Value</span></span>

<span data-ttu-id="5ad61-120">条件をトリガーする、.NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5ad61-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="5ad61-121">コメント</span><span class="sxs-lookup"><span data-stu-id="5ad61-121">Remarks</span></span>

<span data-ttu-id="5ad61-122">指定できないかどうかは、この要素が使用される、 [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)要素の選択条件を定義するときにします。</span><span class="sxs-lookup"><span data-stu-id="5ad61-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ad61-123">参照</span><span class="sxs-lookup"><span data-stu-id="5ad61-123">See Also</span></span>

[<span data-ttu-id="5ad61-124">コントロールが表示されます (形式) の ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="5ad61-124">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="5ad61-125">コントロールが表示されます (形式) の ExpressionBinding の ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="5ad61-125">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="5ad61-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="5ad61-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
