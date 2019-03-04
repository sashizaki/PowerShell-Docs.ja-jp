---
title: GroupBy (形式) の ExpressionBinding ItemSelectionCondition 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6af3be7d-921e-4cf7-bd5a-d87aa0b4efbd
caps.latest.revision: 7
ms.openlocfilehash: b2b0a0d1996392614807e08b820a72978e38a0cb
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853138"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="df9b3-102">GroupBy の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="df9b3-102">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="df9b3-103">このコントロールを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="df9b3-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="df9b3-104">コントロールの項目の指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="df9b3-104">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="df9b3-105">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="df9b3-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="df9b3-106">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)ExpressionBinding の GroupBy (形式) の GroupBy (形式) ItemSelectionCondition 要素 CustomItem の GroupBy (形式) ExpressionBinding 要素 CustomEntry の GroupBy (形式) CustomItem 要素にカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="df9b3-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="df9b3-107">構文</span><span class="sxs-lookup"><span data-stu-id="df9b3-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="df9b3-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="df9b3-108">Attributes and Elements</span></span>

<span data-ttu-id="df9b3-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`ItemSelectionCondition`要素。</span><span class="sxs-lookup"><span data-stu-id="df9b3-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="df9b3-110">属性</span><span class="sxs-lookup"><span data-stu-id="df9b3-110">Attributes</span></span>

<span data-ttu-id="df9b3-111">なし。</span><span class="sxs-lookup"><span data-stu-id="df9b3-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="df9b3-112">子要素</span><span class="sxs-lookup"><span data-stu-id="df9b3-112">Child Elements</span></span>

|<span data-ttu-id="df9b3-113">要素</span><span class="sxs-lookup"><span data-stu-id="df9b3-113">Element</span></span>|<span data-ttu-id="df9b3-114">説明</span><span class="sxs-lookup"><span data-stu-id="df9b3-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="df9b3-115">GroupBy (形式) の ItemSelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="df9b3-115">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="df9b3-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="df9b3-116">Optional element.</span></span><br /><br /> <span data-ttu-id="df9b3-117">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="df9b3-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="df9b3-118">GroupBy (形式) の ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="df9b3-118">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="df9b3-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="df9b3-119">Optional element.</span></span><br /><br /> <span data-ttu-id="df9b3-120">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="df9b3-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="df9b3-121">親要素</span><span class="sxs-lookup"><span data-stu-id="df9b3-121">Parent Elements</span></span>

|<span data-ttu-id="df9b3-122">要素</span><span class="sxs-lookup"><span data-stu-id="df9b3-122">Element</span></span>|<span data-ttu-id="df9b3-123">説明</span><span class="sxs-lookup"><span data-stu-id="df9b3-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="df9b3-124">GroupBy (形式) の CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="df9b3-124">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="df9b3-125">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="df9b3-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="df9b3-126">コメント</span><span class="sxs-lookup"><span data-stu-id="df9b3-126">Remarks</span></span>

<span data-ttu-id="df9b3-127">1 つのプロパティ名またはこの状態のスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="df9b3-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="df9b3-128">参照</span><span class="sxs-lookup"><span data-stu-id="df9b3-128">See Also</span></span>

[<span data-ttu-id="df9b3-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="df9b3-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="df9b3-130">GroupBy (形式) の CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="df9b3-130">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)
