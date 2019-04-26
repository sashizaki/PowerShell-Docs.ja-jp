---
title: ExpressionBinding のビュー (形式) のコントロールの要素を ItemSelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82c15014-2440-410d-b02d-b7f1a49240a0
caps.latest.revision: 7
ms.openlocfilehash: 80f375c53c205c793600655fa6031d114871618e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065480"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="cc2d3-102">View の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cc2d3-102">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="cc2d3-103">このコントロールを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="cc2d3-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="cc2d3-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cc2d3-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="cc2d3-105">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry CustomItem ビュー (形式) のコントロールのビュー (形式) ExpressionBinding 要素のコントロールのビュー (形式) CustomItem 要素のコントロールのビュー (形式) CustomEntry 要素のカスタム コントロールコントロールが表示されます (形式) の ExpressionBinding の ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="cc2d3-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cc2d3-106">構文</span><span class="sxs-lookup"><span data-stu-id="cc2d3-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cc2d3-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cc2d3-107">Attributes and Elements</span></span>

<span data-ttu-id="cc2d3-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`ItemSelectionCondition`要素。</span><span class="sxs-lookup"><span data-stu-id="cc2d3-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cc2d3-109">属性</span><span class="sxs-lookup"><span data-stu-id="cc2d3-109">Attributes</span></span>

<span data-ttu-id="cc2d3-110">なし。</span><span class="sxs-lookup"><span data-stu-id="cc2d3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cc2d3-111">子要素</span><span class="sxs-lookup"><span data-stu-id="cc2d3-111">Child Elements</span></span>

|<span data-ttu-id="cc2d3-112">要素</span><span class="sxs-lookup"><span data-stu-id="cc2d3-112">Element</span></span>|<span data-ttu-id="cc2d3-113">説明</span><span class="sxs-lookup"><span data-stu-id="cc2d3-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cc2d3-114">コントロールが表示されます (形式) の ItemSelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="cc2d3-114">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="cc2d3-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="cc2d3-115">Optional element.</span></span><br /><br /> <span data-ttu-id="cc2d3-116">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="cc2d3-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="cc2d3-117">コントロールが表示されます (形式) の ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="cc2d3-117">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="cc2d3-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="cc2d3-118">Optional element.</span></span><br /><br /> <span data-ttu-id="cc2d3-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="cc2d3-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cc2d3-120">親要素</span><span class="sxs-lookup"><span data-stu-id="cc2d3-120">Parent Elements</span></span>

|<span data-ttu-id="cc2d3-121">要素</span><span class="sxs-lookup"><span data-stu-id="cc2d3-121">Element</span></span>|<span data-ttu-id="cc2d3-122">説明</span><span class="sxs-lookup"><span data-stu-id="cc2d3-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cc2d3-123">コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="cc2d3-123">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="cc2d3-124">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="cc2d3-124">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cc2d3-125">コメント</span><span class="sxs-lookup"><span data-stu-id="cc2d3-125">Remarks</span></span>

<span data-ttu-id="cc2d3-126">1 つのプロパティ名またはこの状態のスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="cc2d3-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc2d3-127">参照</span><span class="sxs-lookup"><span data-stu-id="cc2d3-127">See Also</span></span>

[<span data-ttu-id="cc2d3-128">コントロールが表示されます (形式) の ItemSelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="cc2d3-128">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="cc2d3-129">コントロールが表示されます (形式) の ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="cc2d3-129">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="cc2d3-130">コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="cc2d3-130">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="cc2d3-131">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="cc2d3-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
