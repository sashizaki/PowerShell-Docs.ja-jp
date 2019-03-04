---
title: コントロールが表示されます (形式) の ItemSelectionCondition の ScriptBlock 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4191157-bf01-4831-b221-6f8cc581cd53
caps.latest.revision: 6
ms.openlocfilehash: 0cbefbb48427b56d4ae2a5ae27c7726dcfad7b84
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856738"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="0d6b6-102">View の Controls の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0d6b6-102">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="0d6b6-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="0d6b6-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="0d6b6-104">このスクリプトを評価するときに`true`条件が満たされると、およびコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="0d6b6-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="0d6b6-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d6b6-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="0d6b6-106">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry CustomItem ビュー (形式) のコントロールのビュー (形式) ExpressionBinding 要素のコントロールのビュー (形式) CustomItem 要素のコントロールのビュー (形式) CustomEntry 要素のカスタム コントロールExpressionBinding ItemSelectionCondition ビュー (形式) のコントロールのビュー (形式) スクリプト ブロックの要素のコントロールの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="0d6b6-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0d6b6-107">構文</span><span class="sxs-lookup"><span data-stu-id="0d6b6-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0d6b6-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="0d6b6-108">Attributes and Elements</span></span>

<span data-ttu-id="0d6b6-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。</span><span class="sxs-lookup"><span data-stu-id="0d6b6-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0d6b6-110">属性</span><span class="sxs-lookup"><span data-stu-id="0d6b6-110">Attributes</span></span>

<span data-ttu-id="0d6b6-111">なし。</span><span class="sxs-lookup"><span data-stu-id="0d6b6-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0d6b6-112">子要素</span><span class="sxs-lookup"><span data-stu-id="0d6b6-112">Child Elements</span></span>

<span data-ttu-id="0d6b6-113">なし。</span><span class="sxs-lookup"><span data-stu-id="0d6b6-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0d6b6-114">親要素</span><span class="sxs-lookup"><span data-stu-id="0d6b6-114">Parent Elements</span></span>

|<span data-ttu-id="0d6b6-115">要素</span><span class="sxs-lookup"><span data-stu-id="0d6b6-115">Element</span></span>|<span data-ttu-id="0d6b6-116">説明</span><span class="sxs-lookup"><span data-stu-id="0d6b6-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0d6b6-117">コントロールが表示されます (形式) の ExpressionBinding の ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="0d6b6-117">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="0d6b6-118">このコントロールを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="0d6b6-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0d6b6-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="0d6b6-119">Text Value</span></span>

<span data-ttu-id="0d6b6-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="0d6b6-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="0d6b6-121">コメント</span><span class="sxs-lookup"><span data-stu-id="0d6b6-121">Remarks</span></span>

<span data-ttu-id="0d6b6-122">指定できないかどうかは、この要素が使用される、 [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)要素の選択条件を定義するときにします。</span><span class="sxs-lookup"><span data-stu-id="0d6b6-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d6b6-123">参照</span><span class="sxs-lookup"><span data-stu-id="0d6b6-123">See Also</span></span>

[<span data-ttu-id="0d6b6-124">コントロールが表示されます (形式) の ItemSelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="0d6b6-124">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="0d6b6-125">コントロールが表示されます (形式) の ExpressionBinding の ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="0d6b6-125">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="0d6b6-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="0d6b6-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
