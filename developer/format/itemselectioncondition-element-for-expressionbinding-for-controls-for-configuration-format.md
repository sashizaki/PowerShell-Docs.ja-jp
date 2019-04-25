---
title: ExpressionBinding の構成 (形式) のコントロールの要素を ItemSelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd3ddc33-b21c-4464-b3f2-a78dbe0062a8
caps.latest.revision: 8
ms.openlocfilehash: 4865d716ebe0460b662253a3019e93e82428b882
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065512"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="6cb30-102">Configuration の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6cb30-102">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="6cb30-103">このコントロールを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="6cb30-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="6cb30-104">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6cb30-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="6cb30-105">構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素構成 (形式) のコントロールの CustomItem 構成 ExpressionBinding 要素のコントロールの CustomEntry の構成 (形式) CustomItem 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素ExpressionBinding の構成 (形式) のコントロールの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="6cb30-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6cb30-106">構文</span><span class="sxs-lookup"><span data-stu-id="6cb30-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6cb30-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6cb30-107">Attributes and Elements</span></span>

<span data-ttu-id="6cb30-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`ItemSelectionCondition`要素。</span><span class="sxs-lookup"><span data-stu-id="6cb30-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6cb30-109">属性</span><span class="sxs-lookup"><span data-stu-id="6cb30-109">Attributes</span></span>

<span data-ttu-id="6cb30-110">なし。</span><span class="sxs-lookup"><span data-stu-id="6cb30-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6cb30-111">子要素</span><span class="sxs-lookup"><span data-stu-id="6cb30-111">Child Elements</span></span>

|<span data-ttu-id="6cb30-112">要素</span><span class="sxs-lookup"><span data-stu-id="6cb30-112">Element</span></span>|<span data-ttu-id="6cb30-113">説明</span><span class="sxs-lookup"><span data-stu-id="6cb30-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6cb30-114">構成 (形式) のコントロールの ItemSelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="6cb30-114">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="6cb30-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="6cb30-115">Optional element.</span></span><br /><br /> <span data-ttu-id="6cb30-116">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="6cb30-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="6cb30-117">構成 (形式) のコントロールの ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="6cb30-117">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="6cb30-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="6cb30-118">Optional element.</span></span><br /><br /> <span data-ttu-id="6cb30-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="6cb30-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6cb30-120">親要素</span><span class="sxs-lookup"><span data-stu-id="6cb30-120">Parent Elements</span></span>

|<span data-ttu-id="6cb30-121">要素</span><span class="sxs-lookup"><span data-stu-id="6cb30-121">Element</span></span>|<span data-ttu-id="6cb30-122">説明</span><span class="sxs-lookup"><span data-stu-id="6cb30-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6cb30-123">構成 (形式) のコントロールの CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="6cb30-123">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="6cb30-124">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="6cb30-124">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6cb30-125">コメント</span><span class="sxs-lookup"><span data-stu-id="6cb30-125">Remarks</span></span>

<span data-ttu-id="6cb30-126">1 つのプロパティ名またはこの状態のスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="6cb30-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="6cb30-127">参照</span><span class="sxs-lookup"><span data-stu-id="6cb30-127">See Also</span></span>

[<span data-ttu-id="6cb30-128">構成 (形式) のコントロールの ItemSelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="6cb30-128">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="6cb30-129">構成 (形式) のコントロールの ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="6cb30-129">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="6cb30-130">構成 (形式) のコントロールの CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="6cb30-130">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="6cb30-131">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="6cb30-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
