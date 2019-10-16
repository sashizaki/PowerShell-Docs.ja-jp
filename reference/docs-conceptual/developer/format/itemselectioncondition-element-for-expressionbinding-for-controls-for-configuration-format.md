---
title: 構成用のコントロールの式のバインドの ItemSelectionCondition 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd3ddc33-b21c-4464-b3f2-a78dbe0062a8
caps.latest.revision: 8
ms.openlocfilehash: 4865d716ebe0460b662253a3019e93e82428b882
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362921"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="83793-102">Configuration の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="83793-102">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="83793-103">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="83793-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="83793-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="83793-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="83793-105">Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素形式) CustomControl の CustomEntry 要素を構成するためのコントロール用の CustomEntry 要素を構成するためのコントロール用 CustomItem 要素の構成式のバインド要素 CustomItem の構成 (形式)構成用のコントロールの式のバインドの ItemSelectionCondition 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="83793-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="83793-106">構文</span><span class="sxs-lookup"><span data-stu-id="83793-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="83793-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="83793-107">Attributes and Elements</span></span>

<span data-ttu-id="83793-108">次のセクションでは、属性、子要素、`ItemSelectionCondition` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="83793-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="83793-109">属性</span><span class="sxs-lookup"><span data-stu-id="83793-109">Attributes</span></span>

<span data-ttu-id="83793-110">なし。</span><span class="sxs-lookup"><span data-stu-id="83793-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="83793-111">子要素</span><span class="sxs-lookup"><span data-stu-id="83793-111">Child Elements</span></span>

|<span data-ttu-id="83793-112">要素</span><span class="sxs-lookup"><span data-stu-id="83793-112">Element</span></span>|<span data-ttu-id="83793-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="83793-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="83793-114">構成用のコントロールの ItemSelectionCondition の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="83793-114">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="83793-115">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="83793-115">Optional element.</span></span><br /><br /> <span data-ttu-id="83793-116">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="83793-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="83793-117">構成用のコントロールの ItemSelectionCondition の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="83793-117">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="83793-118">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="83793-118">Optional element.</span></span><br /><br /> <span data-ttu-id="83793-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="83793-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="83793-120">親要素</span><span class="sxs-lookup"><span data-stu-id="83793-120">Parent Elements</span></span>

|<span data-ttu-id="83793-121">要素</span><span class="sxs-lookup"><span data-stu-id="83793-121">Element</span></span>|<span data-ttu-id="83793-122">[説明]</span><span class="sxs-lookup"><span data-stu-id="83793-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="83793-123">構成用のコントロールに対する CustomItem の式のバインド要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="83793-123">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="83793-124">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="83793-124">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="83793-125">コメント</span><span class="sxs-lookup"><span data-stu-id="83793-125">Remarks</span></span>

<span data-ttu-id="83793-126">この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="83793-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="83793-127">参照</span><span class="sxs-lookup"><span data-stu-id="83793-127">See Also</span></span>

[<span data-ttu-id="83793-128">構成用のコントロールの ItemSelectionCondition の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="83793-128">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="83793-129">構成用のコントロールの ItemSelectionCondition の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="83793-129">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="83793-130">構成用のコントロールに対する CustomItem の式のバインド要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="83793-130">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="83793-131">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="83793-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
