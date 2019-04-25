---
title: PropertyName 要素の構成 (形式) のコントロールの ItemSeclectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad8ab181-c559-492e-a0cf-299e381fdcc3
caps.latest.revision: 6
ms.openlocfilehash: ce25789bdfc2679372ca9e42f99dcc6a30ae2def
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064905"
---
# <a name="propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="22fa1-102">Configuration の Controls の ItemSeclectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="22fa1-102">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="22fa1-103">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="22fa1-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="22fa1-104">このプロパティが存在するかを評価すると`true`条件が満たされると、およびコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="22fa1-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="22fa1-105">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="22fa1-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="22fa1-106">構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素構成 (形式) のコントロールの CustomItem 構成 ExpressionBinding 要素のコントロールの CustomEntry の構成 (形式) CustomItem 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素ExpressionBinding ItemSeclectionCondition の構成 (形式) のコントロールの構成 (形式) PropertyName 要素のコントロールの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="22fa1-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format) PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="22fa1-107">構文</span><span class="sxs-lookup"><span data-stu-id="22fa1-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="22fa1-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="22fa1-108">Attributes and Elements</span></span>

<span data-ttu-id="22fa1-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。</span><span class="sxs-lookup"><span data-stu-id="22fa1-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="22fa1-110">属性</span><span class="sxs-lookup"><span data-stu-id="22fa1-110">Attributes</span></span>

<span data-ttu-id="22fa1-111">なし。</span><span class="sxs-lookup"><span data-stu-id="22fa1-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="22fa1-112">子要素</span><span class="sxs-lookup"><span data-stu-id="22fa1-112">Child Elements</span></span>

<span data-ttu-id="22fa1-113">なし。</span><span class="sxs-lookup"><span data-stu-id="22fa1-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="22fa1-114">親要素</span><span class="sxs-lookup"><span data-stu-id="22fa1-114">Parent Elements</span></span>

|<span data-ttu-id="22fa1-115">要素</span><span class="sxs-lookup"><span data-stu-id="22fa1-115">Element</span></span>|<span data-ttu-id="22fa1-116">説明</span><span class="sxs-lookup"><span data-stu-id="22fa1-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="22fa1-117">ExpressionBinding の構成 (形式) のコントロールの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="22fa1-117">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="22fa1-118">このコントロールを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="22fa1-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="22fa1-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="22fa1-119">Text Value</span></span>

<span data-ttu-id="22fa1-120">条件をトリガーする、.NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="22fa1-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="22fa1-121">コメント</span><span class="sxs-lookup"><span data-stu-id="22fa1-121">Remarks</span></span>

<span data-ttu-id="22fa1-122">指定できないかどうかは、この要素が使用される、 [ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)要素の選択条件を定義するときにします。</span><span class="sxs-lookup"><span data-stu-id="22fa1-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="22fa1-123">参照</span><span class="sxs-lookup"><span data-stu-id="22fa1-123">See Also</span></span>

[<span data-ttu-id="22fa1-124">構成 (形式) のコントロールの ItemSeclectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="22fa1-124">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="22fa1-125">ExpressionBinding の構成 (形式) のコントロールの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="22fa1-125">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[<span data-ttu-id="22fa1-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="22fa1-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
