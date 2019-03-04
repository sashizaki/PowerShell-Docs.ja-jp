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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858188"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a><span data-ttu-id="55451-102">CustomControl の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="55451-102">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>

<span data-ttu-id="55451-103">このコントロールを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="55451-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="55451-104">コントロールの項目の指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="55451-104">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="55451-105">この要素は、カスタム コントロールのビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="55451-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="55451-106">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) CustomItem 要素 CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールCustomEntry CustomItem のカスタム コントロールの表示 (形式) の式バインディングのビュー (形式) ItemSelectionCondition 要素のカスタム コントロールのビュー (形式) ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="55451-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="55451-107">構文</span><span class="sxs-lookup"><span data-stu-id="55451-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="55451-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="55451-108">Attributes and Elements</span></span>

<span data-ttu-id="55451-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`ItemSelectionCondition`要素。</span><span class="sxs-lookup"><span data-stu-id="55451-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="55451-110">属性</span><span class="sxs-lookup"><span data-stu-id="55451-110">Attributes</span></span>

<span data-ttu-id="55451-111">なし。</span><span class="sxs-lookup"><span data-stu-id="55451-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="55451-112">子要素</span><span class="sxs-lookup"><span data-stu-id="55451-112">Child Elements</span></span>

|<span data-ttu-id="55451-113">要素</span><span class="sxs-lookup"><span data-stu-id="55451-113">Element</span></span>|<span data-ttu-id="55451-114">説明</span><span class="sxs-lookup"><span data-stu-id="55451-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="55451-115">ビュー (形式のカスタム コントロールの ItemSelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="55451-115">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="55451-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="55451-116">Optional element.</span></span><br /><br /> <span data-ttu-id="55451-117">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="55451-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="55451-118">ビュー (形式) のカスタム コントロールの ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="55451-118">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="55451-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="55451-119">Optional element.</span></span><br /><br /> <span data-ttu-id="55451-120">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="55451-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="55451-121">親要素</span><span class="sxs-lookup"><span data-stu-id="55451-121">Parent Elements</span></span>

|<span data-ttu-id="55451-122">要素</span><span class="sxs-lookup"><span data-stu-id="55451-122">Element</span></span>|<span data-ttu-id="55451-123">説明</span><span class="sxs-lookup"><span data-stu-id="55451-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="55451-124">ビュー (形式) のカスタム コントロールの CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="55451-124">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="55451-125">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="55451-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="55451-126">コメント</span><span class="sxs-lookup"><span data-stu-id="55451-126">Remarks</span></span>

<span data-ttu-id="55451-127">1 つのプロパティ名またはこの状態のスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="55451-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="55451-128">参照</span><span class="sxs-lookup"><span data-stu-id="55451-128">See Also</span></span>

[<span data-ttu-id="55451-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="55451-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="55451-130">ビュー (形式) のカスタム コントロールの CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="55451-130">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
