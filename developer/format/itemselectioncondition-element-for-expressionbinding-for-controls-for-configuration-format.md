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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861688"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="f0457-102">Configuration の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f0457-102">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="f0457-103">このコントロールを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="f0457-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="f0457-104">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0457-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="f0457-105">構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素構成 (形式) のコントロールの CustomItem 構成 ExpressionBinding 要素のコントロールの CustomEntry の構成 (形式) CustomItem 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素ExpressionBinding の構成 (形式) のコントロールの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="f0457-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f0457-106">構文</span><span class="sxs-lookup"><span data-stu-id="f0457-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f0457-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="f0457-107">Attributes and Elements</span></span>

<span data-ttu-id="f0457-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`ItemSelectionCondition`要素。</span><span class="sxs-lookup"><span data-stu-id="f0457-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f0457-109">属性</span><span class="sxs-lookup"><span data-stu-id="f0457-109">Attributes</span></span>

<span data-ttu-id="f0457-110">なし。</span><span class="sxs-lookup"><span data-stu-id="f0457-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f0457-111">子要素</span><span class="sxs-lookup"><span data-stu-id="f0457-111">Child Elements</span></span>

|<span data-ttu-id="f0457-112">要素</span><span class="sxs-lookup"><span data-stu-id="f0457-112">Element</span></span>|<span data-ttu-id="f0457-113">説明</span><span class="sxs-lookup"><span data-stu-id="f0457-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f0457-114">構成 (形式) のコントロールの ItemSelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="f0457-114">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="f0457-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f0457-115">Optional element.</span></span><br /><br /> <span data-ttu-id="f0457-116">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0457-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="f0457-117">構成 (形式) のコントロールの ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="f0457-117">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="f0457-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f0457-118">Optional element.</span></span><br /><br /> <span data-ttu-id="f0457-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0457-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f0457-120">親要素</span><span class="sxs-lookup"><span data-stu-id="f0457-120">Parent Elements</span></span>

|<span data-ttu-id="f0457-121">要素</span><span class="sxs-lookup"><span data-stu-id="f0457-121">Element</span></span>|<span data-ttu-id="f0457-122">説明</span><span class="sxs-lookup"><span data-stu-id="f0457-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f0457-123">構成 (形式) のコントロールの CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="f0457-123">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="f0457-124">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="f0457-124">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f0457-125">コメント</span><span class="sxs-lookup"><span data-stu-id="f0457-125">Remarks</span></span>

<span data-ttu-id="f0457-126">1 つのプロパティ名またはこの状態のスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f0457-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0457-127">参照</span><span class="sxs-lookup"><span data-stu-id="f0457-127">See Also</span></span>

[<span data-ttu-id="f0457-128">構成 (形式) のコントロールの ItemSelectionCondition PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="f0457-128">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="f0457-129">構成 (形式) のコントロールの ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="f0457-129">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="f0457-130">構成 (形式) のコントロールの CustomItem ExpressionBinding 要素</span><span class="sxs-lookup"><span data-stu-id="f0457-130">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="f0457-131">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="f0457-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
