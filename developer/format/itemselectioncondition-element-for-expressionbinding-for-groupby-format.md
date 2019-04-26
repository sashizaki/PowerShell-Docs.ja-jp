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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065463"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="4b78d-102">GroupBy の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4b78d-102">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="4b78d-103">このコントロールを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="4b78d-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="4b78d-104">コントロールの項目の指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="4b78d-104">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="4b78d-105">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4b78d-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="4b78d-106">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)ExpressionBinding の GroupBy (形式) の GroupBy (形式) ItemSelectionCondition 要素 CustomItem の GroupBy (形式) ExpressionBinding 要素 CustomEntry の GroupBy (形式) CustomItem 要素にカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="4b78d-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4b78d-107">構文</span><span class="sxs-lookup"><span data-stu-id="4b78d-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4b78d-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4b78d-108">Attributes and Elements</span></span>

<span data-ttu-id="4b78d-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`ItemSelectionCondition`要素。</span><span class="sxs-lookup"><span data-stu-id="4b78d-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4b78d-110">属性</span><span class="sxs-lookup"><span data-stu-id="4b78d-110">Attributes</span></span>

<span data-ttu-id="4b78d-111">なし。</span><span class="sxs-lookup"><span data-stu-id="4b78d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4b78d-112">子要素</span><span class="sxs-lookup"><span data-stu-id="4b78d-112">Child Elements</span></span>

|<span data-ttu-id="4b78d-113">要素</span><span class="sxs-lookup"><span data-stu-id="4b78d-113">Element</span></span>|<span data-ttu-id="4b78d-114">説明</span><span class="sxs-lookup"><span data-stu-id="4b78d-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4b78d-115">GroupBy (形式) の ItemSelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="4b78d-115">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="4b78d-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4b78d-116">Optional element.</span></span><br /><br /> <span data-ttu-id="4b78d-117">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="4b78d-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="4b78d-118">GroupBy (形式) の ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="4b78d-118">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="4b78d-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4b78d-119">Optional element.</span></span><br /><br /> <span data-ttu-id="4b78d-120">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="4b78d-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4b78d-121">親要素</span><span class="sxs-lookup"><span data-stu-id="4b78d-121">Parent Elements</span></span>

|<span data-ttu-id="4b78d-122">要素</span><span class="sxs-lookup"><span data-stu-id="4b78d-122">Element</span></span>|<span data-ttu-id="4b78d-123">説明</span><span class="sxs-lookup"><span data-stu-id="4b78d-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4b78d-124">GroupBy (形式) の CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="4b78d-124">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="4b78d-125">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="4b78d-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4b78d-126">コメント</span><span class="sxs-lookup"><span data-stu-id="4b78d-126">Remarks</span></span>

<span data-ttu-id="4b78d-127">1 つのプロパティ名またはこの状態のスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="4b78d-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b78d-128">参照</span><span class="sxs-lookup"><span data-stu-id="4b78d-128">See Also</span></span>

[<span data-ttu-id="4b78d-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="4b78d-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="4b78d-130">GroupBy (形式) の CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="4b78d-130">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)
