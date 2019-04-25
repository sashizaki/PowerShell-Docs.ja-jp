---
title: GroupBy (形式) の ItemSelectionCondition の ScriptBlock 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58d25835-4636-4c58-9f6c-0332b9318051
caps.latest.revision: 6
ms.openlocfilehash: 4045196e306e766cd805b3e7ae31bfcb3de184ee
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064545"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-groupby-format"></a><span data-ttu-id="acecd-102">GroupBy の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="acecd-102">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="acecd-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="acecd-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="acecd-104">このスクリプトを評価するときに`true`条件が満たされると、およびコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="acecd-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="acecd-105">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="acecd-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="acecd-106">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)ExpressionBinding の GroupBy (形式) スクリプト ブロックの要素の GroupBy (形式) ItemSelectionCondition 要素 CustomItem の GroupBy (形式) ExpressionBinding 要素 CustomEntry の GroupBy (形式) CustomItem 要素にカスタム コントロールGroupBy (形式) の ItemSelectionCondition</span><span class="sxs-lookup"><span data-stu-id="acecd-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format) ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="acecd-107">構文</span><span class="sxs-lookup"><span data-stu-id="acecd-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="acecd-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="acecd-108">Attributes and Elements</span></span>

<span data-ttu-id="acecd-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。</span><span class="sxs-lookup"><span data-stu-id="acecd-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="acecd-110">属性</span><span class="sxs-lookup"><span data-stu-id="acecd-110">Attributes</span></span>

<span data-ttu-id="acecd-111">なし。</span><span class="sxs-lookup"><span data-stu-id="acecd-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="acecd-112">子要素</span><span class="sxs-lookup"><span data-stu-id="acecd-112">Child Elements</span></span>

<span data-ttu-id="acecd-113">なし。</span><span class="sxs-lookup"><span data-stu-id="acecd-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="acecd-114">親要素</span><span class="sxs-lookup"><span data-stu-id="acecd-114">Parent Elements</span></span>

|<span data-ttu-id="acecd-115">要素</span><span class="sxs-lookup"><span data-stu-id="acecd-115">Element</span></span>|<span data-ttu-id="acecd-116">説明</span><span class="sxs-lookup"><span data-stu-id="acecd-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="acecd-117">GroupBy (形式) の ExpressionBinding ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="acecd-117">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="acecd-118">このコントロールを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="acecd-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="acecd-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="acecd-119">Text Value</span></span>

<span data-ttu-id="acecd-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="acecd-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="acecd-121">コメント</span><span class="sxs-lookup"><span data-stu-id="acecd-121">Remarks</span></span>

<span data-ttu-id="acecd-122">指定できないかどうかは、この要素が使用される、 [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)要素の選択条件を定義するときにします。</span><span class="sxs-lookup"><span data-stu-id="acecd-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="acecd-123">参照</span><span class="sxs-lookup"><span data-stu-id="acecd-123">See Also</span></span>

[<span data-ttu-id="acecd-124">GroupBy (形式) の ExpressionBinding ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="acecd-124">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="acecd-125">GroupBy (形式) の ItemSelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="acecd-125">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)

[<span data-ttu-id="acecd-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="acecd-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
