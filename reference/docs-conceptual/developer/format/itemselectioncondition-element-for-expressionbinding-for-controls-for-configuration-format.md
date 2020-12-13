---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)
description: Configuration の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)
ms.openlocfilehash: 6bd3d386ba64b33a1744fcc9e602cf13404765a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648097"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="e78ee-103">Configuration の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e78ee-103">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="e78ee-104">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="e78ee-104">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="e78ee-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e78ee-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="e78ee-106">Configuration 要素 (Format) コントロールの構成 (format) コントロールの要素の構成 (format) の CustomControl 要素の構成のためのコントロールの要素の構成 (形式) CustomControl の構成 (書式) の CustomEntries 要素 CustomControl の CustomEntry 要素コントロールのために、CustomEntry 用のカスタム Customentries 要素を構成するためのコントロールに対して、構成のためのコントロールのための構成 (Format) ItemSelectionCondition 要素の構成 (形式) のコントロールのための式のバインド要素のバインド要素</span><span class="sxs-lookup"><span data-stu-id="e78ee-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e78ee-107">構文</span><span class="sxs-lookup"><span data-stu-id="e78ee-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e78ee-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e78ee-108">Attributes and Elements</span></span>

<span data-ttu-id="e78ee-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ItemSelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="e78ee-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e78ee-110">属性</span><span class="sxs-lookup"><span data-stu-id="e78ee-110">Attributes</span></span>

<span data-ttu-id="e78ee-111">なし。</span><span class="sxs-lookup"><span data-stu-id="e78ee-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e78ee-112">子要素</span><span class="sxs-lookup"><span data-stu-id="e78ee-112">Child Elements</span></span>

|<span data-ttu-id="e78ee-113">要素</span><span class="sxs-lookup"><span data-stu-id="e78ee-113">Element</span></span>|<span data-ttu-id="e78ee-114">説明</span><span class="sxs-lookup"><span data-stu-id="e78ee-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e78ee-115">構成用のコントロールの ItemSelectionCondition の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e78ee-115">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="e78ee-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e78ee-116">Optional element.</span></span><br /><br /> <span data-ttu-id="e78ee-117">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="e78ee-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="e78ee-118">構成用のコントロールの ItemSelectionCondition の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e78ee-118">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="e78ee-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e78ee-119">Optional element.</span></span><br /><br /> <span data-ttu-id="e78ee-120">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e78ee-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e78ee-121">親要素</span><span class="sxs-lookup"><span data-stu-id="e78ee-121">Parent Elements</span></span>

|<span data-ttu-id="e78ee-122">要素</span><span class="sxs-lookup"><span data-stu-id="e78ee-122">Element</span></span>|<span data-ttu-id="e78ee-123">説明</span><span class="sxs-lookup"><span data-stu-id="e78ee-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e78ee-124">Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e78ee-124">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="e78ee-125">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="e78ee-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e78ee-126">解説</span><span class="sxs-lookup"><span data-stu-id="e78ee-126">Remarks</span></span>

<span data-ttu-id="e78ee-127">この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e78ee-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="e78ee-128">参照</span><span class="sxs-lookup"><span data-stu-id="e78ee-128">See Also</span></span>

[<span data-ttu-id="e78ee-129">構成用のコントロールの ItemSelectionCondition の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e78ee-129">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="e78ee-130">構成用のコントロールの ItemSelectionCondition の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e78ee-130">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="e78ee-131">Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e78ee-131">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="e78ee-132">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="e78ee-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
