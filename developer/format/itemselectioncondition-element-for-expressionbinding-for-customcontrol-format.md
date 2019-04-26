---
title: カスタム コントロール (形式) の ExpressionBinding ItemSelectionCondition 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f4bea9d8-27ad-410e-ad48-287f807d3e4e
caps.latest.revision: 7
ms.openlocfilehash: 18b0113c9b7b0895a1093cb0b56cd2d02c74a6c1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065826"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a><span data-ttu-id="01b49-102">CustomControl の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="01b49-102">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>

<span data-ttu-id="01b49-103">このコントロールを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="01b49-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="01b49-104">コントロールの項目の指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="01b49-104">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="01b49-105">この要素は、カスタム コントロールのビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="01b49-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="01b49-106">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) CustomItem 要素 CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールCustomEntry CustomItem のカスタム コントロールの表示 (形式) の式バインディングのビュー (形式) ItemSelectionCondition 要素のカスタム コントロールのビュー (形式) ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="01b49-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="01b49-107">構文</span><span class="sxs-lookup"><span data-stu-id="01b49-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="01b49-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="01b49-108">Attributes and Elements</span></span>

<span data-ttu-id="01b49-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`ItemSelectionCondition`要素。</span><span class="sxs-lookup"><span data-stu-id="01b49-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="01b49-110">属性</span><span class="sxs-lookup"><span data-stu-id="01b49-110">Attributes</span></span>

<span data-ttu-id="01b49-111">なし。</span><span class="sxs-lookup"><span data-stu-id="01b49-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="01b49-112">子要素</span><span class="sxs-lookup"><span data-stu-id="01b49-112">Child Elements</span></span>

|<span data-ttu-id="01b49-113">要素</span><span class="sxs-lookup"><span data-stu-id="01b49-113">Element</span></span>|<span data-ttu-id="01b49-114">説明</span><span class="sxs-lookup"><span data-stu-id="01b49-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="01b49-115">ビュー (形式のカスタム コントロールの ItemSelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="01b49-115">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="01b49-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="01b49-116">Optional element.</span></span><br /><br /> <span data-ttu-id="01b49-117">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="01b49-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="01b49-118">ビュー (形式) のカスタム コントロールの ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="01b49-118">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="01b49-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="01b49-119">Optional element.</span></span><br /><br /> <span data-ttu-id="01b49-120">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="01b49-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="01b49-121">親要素</span><span class="sxs-lookup"><span data-stu-id="01b49-121">Parent Elements</span></span>

|<span data-ttu-id="01b49-122">要素</span><span class="sxs-lookup"><span data-stu-id="01b49-122">Element</span></span>|<span data-ttu-id="01b49-123">説明</span><span class="sxs-lookup"><span data-stu-id="01b49-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="01b49-124">ビュー (形式) のカスタム コントロールの CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="01b49-124">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="01b49-125">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="01b49-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="01b49-126">コメント</span><span class="sxs-lookup"><span data-stu-id="01b49-126">Remarks</span></span>

<span data-ttu-id="01b49-127">1 つのプロパティ名またはこの状態のスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="01b49-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="01b49-128">参照</span><span class="sxs-lookup"><span data-stu-id="01b49-128">See Also</span></span>

[<span data-ttu-id="01b49-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="01b49-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="01b49-130">ビュー (形式) のカスタム コントロールの CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="01b49-130">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
