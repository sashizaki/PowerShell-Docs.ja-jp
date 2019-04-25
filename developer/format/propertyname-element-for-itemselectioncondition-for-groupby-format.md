---
title: GroupBy (形式) の ItemSelectionCondition PropertyName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 221cbdc2-f794-4f3a-9d40-bfdd8cba1013
caps.latest.revision: 6
ms.openlocfilehash: aae65789cf5572cbcc9251eca802a2d43065e49f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064766"
---
# <a name="propertyname-element-for-itemselectioncondition-for-groupby-format"></a><span data-ttu-id="3ad2a-102">GroupBy の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3ad2a-102">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="3ad2a-103">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ad2a-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="3ad2a-104">このプロパティが存在するかを評価すると`true`条件が満たされると、およびコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ad2a-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="3ad2a-105">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ad2a-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="3ad2a-106">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)ExpressionBinding の GroupBy (形式) PropertyName 要素の GroupBy (形式) ItemSelectionCondition 要素 CustomItem の GroupBy (形式) ExpressionBinding 要素 CustomEntry の GroupBy (形式) CustomItem 要素にカスタム コントロールGroupBy (形式) の ItemSelectionCondition</span><span class="sxs-lookup"><span data-stu-id="3ad2a-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format) PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3ad2a-107">構文</span><span class="sxs-lookup"><span data-stu-id="3ad2a-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3ad2a-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3ad2a-108">Attributes and Elements</span></span>

<span data-ttu-id="3ad2a-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。</span><span class="sxs-lookup"><span data-stu-id="3ad2a-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3ad2a-110">属性</span><span class="sxs-lookup"><span data-stu-id="3ad2a-110">Attributes</span></span>

<span data-ttu-id="3ad2a-111">なし。</span><span class="sxs-lookup"><span data-stu-id="3ad2a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3ad2a-112">子要素</span><span class="sxs-lookup"><span data-stu-id="3ad2a-112">Child Elements</span></span>

<span data-ttu-id="3ad2a-113">なし。</span><span class="sxs-lookup"><span data-stu-id="3ad2a-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3ad2a-114">親要素</span><span class="sxs-lookup"><span data-stu-id="3ad2a-114">Parent Elements</span></span>

|<span data-ttu-id="3ad2a-115">要素</span><span class="sxs-lookup"><span data-stu-id="3ad2a-115">Element</span></span>|<span data-ttu-id="3ad2a-116">説明</span><span class="sxs-lookup"><span data-stu-id="3ad2a-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3ad2a-117">GroupBy (形式) の ExpressionBinding ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="3ad2a-117">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="3ad2a-118">このコントロールを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="3ad2a-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3ad2a-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="3ad2a-119">Text Value</span></span>

<span data-ttu-id="3ad2a-120">条件をトリガーする、.NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ad2a-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="3ad2a-121">コメント</span><span class="sxs-lookup"><span data-stu-id="3ad2a-121">Remarks</span></span>

<span data-ttu-id="3ad2a-122">指定できないかどうかは、この要素が使用される、 [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)要素の選択条件を定義するときにします。</span><span class="sxs-lookup"><span data-stu-id="3ad2a-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ad2a-123">参照</span><span class="sxs-lookup"><span data-stu-id="3ad2a-123">See Also</span></span>

[<span data-ttu-id="3ad2a-124">GroupBy (形式) の ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="3ad2a-124">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)

[<span data-ttu-id="3ad2a-125">GroupBy (形式) の ExpressionBinding ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="3ad2a-125">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="3ad2a-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="3ad2a-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
