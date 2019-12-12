---
title: GroupBy (Format) の ItemSelectionCondition の ScriptBlock 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58d25835-4636-4c58-9f6c-0332b9318051
caps.latest.revision: 6
ms.openlocfilehash: 4045196e306e766cd805b3e7ae31bfcb3de184ee
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364831"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-groupby-format"></a><span data-ttu-id="bc035-102">GroupBy の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bc035-102">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="bc035-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="bc035-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="bc035-104">このスクリプトが `true`に評価されると、条件が満たされ、コントロールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc035-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="bc035-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc035-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="bc035-106">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素CustomControl for groupby (format) CustomItem 要素の CustomEntry for groupby (format) 式のバインド要素に対して、groupby (format) ScriptBlock 要素の式のバインドのバインド要素GroupBy の ItemSelectionCondition (形式)</span><span class="sxs-lookup"><span data-stu-id="bc035-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format) ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bc035-107">構文</span><span class="sxs-lookup"><span data-stu-id="bc035-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bc035-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="bc035-108">Attributes and Elements</span></span>

<span data-ttu-id="bc035-109">次のセクションでは、`ScriptBlock` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc035-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bc035-110">属性</span><span class="sxs-lookup"><span data-stu-id="bc035-110">Attributes</span></span>

<span data-ttu-id="bc035-111">なし。</span><span class="sxs-lookup"><span data-stu-id="bc035-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bc035-112">子要素</span><span class="sxs-lookup"><span data-stu-id="bc035-112">Child Elements</span></span>

<span data-ttu-id="bc035-113">なし。</span><span class="sxs-lookup"><span data-stu-id="bc035-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bc035-114">親要素</span><span class="sxs-lookup"><span data-stu-id="bc035-114">Parent Elements</span></span>

|<span data-ttu-id="bc035-115">要素</span><span class="sxs-lookup"><span data-stu-id="bc035-115">Element</span></span>|<span data-ttu-id="bc035-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="bc035-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bc035-117">GroupBy (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="bc035-117">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="bc035-118">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="bc035-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="bc035-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="bc035-119">Text Value</span></span>

<span data-ttu-id="bc035-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="bc035-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="bc035-121">コメント</span><span class="sxs-lookup"><span data-stu-id="bc035-121">Remarks</span></span>

<span data-ttu-id="bc035-122">この要素が使用されている場合、選択条件を定義するときに[PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="bc035-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc035-123">参照</span><span class="sxs-lookup"><span data-stu-id="bc035-123">See Also</span></span>

[<span data-ttu-id="bc035-124">GroupBy (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="bc035-124">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="bc035-125">GroupBy (Format) の ItemSelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="bc035-125">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)

[<span data-ttu-id="bc035-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="bc035-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
