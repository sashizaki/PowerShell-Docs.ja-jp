---
title: GroupBy (Format) の ItemSelectionCondition の PropertyName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 221cbdc2-f794-4f3a-9d40-bfdd8cba1013
caps.latest.revision: 6
ms.openlocfilehash: aae65789cf5572cbcc9251eca802a2d43065e49f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362411"
---
# <a name="propertyname-element-for-itemselectioncondition-for-groupby-format"></a><span data-ttu-id="88b22-102">GroupBy の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="88b22-102">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="88b22-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="88b22-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="88b22-104">このプロパティが存在する場合、または `true`に評価された場合、条件が満たされ、コントロールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="88b22-104">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="88b22-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="88b22-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="88b22-106">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素CustomControl for groupby (format) CustomItem 要素の CustomEntry for groupby (format) 式のバインド要素に対して、groupby (format) PropertyName 要素のオブジェクトのバインドのバインド要素GroupBy の ItemSelectionCondition (形式)</span><span class="sxs-lookup"><span data-stu-id="88b22-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format) PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="88b22-107">構文</span><span class="sxs-lookup"><span data-stu-id="88b22-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="88b22-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="88b22-108">Attributes and Elements</span></span>

<span data-ttu-id="88b22-109">次のセクションでは、`PropertyName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="88b22-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="88b22-110">属性</span><span class="sxs-lookup"><span data-stu-id="88b22-110">Attributes</span></span>

<span data-ttu-id="88b22-111">なし。</span><span class="sxs-lookup"><span data-stu-id="88b22-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="88b22-112">子要素</span><span class="sxs-lookup"><span data-stu-id="88b22-112">Child Elements</span></span>

<span data-ttu-id="88b22-113">なし。</span><span class="sxs-lookup"><span data-stu-id="88b22-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="88b22-114">親要素</span><span class="sxs-lookup"><span data-stu-id="88b22-114">Parent Elements</span></span>

|<span data-ttu-id="88b22-115">要素</span><span class="sxs-lookup"><span data-stu-id="88b22-115">Element</span></span>|<span data-ttu-id="88b22-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="88b22-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="88b22-117">GroupBy (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="88b22-117">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="88b22-118">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="88b22-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="88b22-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="88b22-119">Text Value</span></span>

<span data-ttu-id="88b22-120">条件をトリガーする .NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="88b22-120">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="88b22-121">コメント</span><span class="sxs-lookup"><span data-stu-id="88b22-121">Remarks</span></span>

<span data-ttu-id="88b22-122">この要素が使用されている場合、選択条件を定義するときに[ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="88b22-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="88b22-123">参照</span><span class="sxs-lookup"><span data-stu-id="88b22-123">See Also</span></span>

[<span data-ttu-id="88b22-124">GroupBy (Format) の ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="88b22-124">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)

[<span data-ttu-id="88b22-125">GroupBy (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="88b22-125">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="88b22-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="88b22-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
