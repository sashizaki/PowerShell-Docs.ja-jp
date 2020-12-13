---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の ExpressionBinding の ItemSelectionCondition 要素 (書式)
description: GroupBy の ExpressionBinding の ItemSelectionCondition 要素 (書式)
ms.openlocfilehash: 92120ace5ed316fbfbf1d51422071c27d5a604cf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651989"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="4eb1d-103">GroupBy の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4eb1d-103">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="4eb1d-104">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="4eb1d-104">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="4eb1d-105">コントロール項目に指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="4eb1d-105">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="4eb1d-106">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4eb1d-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="4eb1d-107">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素を groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素 CustomControl for GroupBy (format) Customentries 要素の CustomEntry for groupby (format) 式のバインド要素で groupby (format) ItemSelectionCondition 要素に対して groupby (形式) の式のバインドのバインド要素</span><span class="sxs-lookup"><span data-stu-id="4eb1d-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4eb1d-108">構文</span><span class="sxs-lookup"><span data-stu-id="4eb1d-108">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4eb1d-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4eb1d-109">Attributes and Elements</span></span>

<span data-ttu-id="4eb1d-110">次のセクションでは、要素の属性、子要素、および親要素について説明し `ItemSelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="4eb1d-110">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4eb1d-111">属性</span><span class="sxs-lookup"><span data-stu-id="4eb1d-111">Attributes</span></span>

<span data-ttu-id="4eb1d-112">なし。</span><span class="sxs-lookup"><span data-stu-id="4eb1d-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4eb1d-113">子要素</span><span class="sxs-lookup"><span data-stu-id="4eb1d-113">Child Elements</span></span>

|<span data-ttu-id="4eb1d-114">要素</span><span class="sxs-lookup"><span data-stu-id="4eb1d-114">Element</span></span>|<span data-ttu-id="4eb1d-115">説明</span><span class="sxs-lookup"><span data-stu-id="4eb1d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4eb1d-116">GroupBy の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4eb1d-116">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="4eb1d-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4eb1d-117">Optional element.</span></span><br /><br /> <span data-ttu-id="4eb1d-118">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="4eb1d-118">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="4eb1d-119">GroupBy の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4eb1d-119">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="4eb1d-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4eb1d-120">Optional element.</span></span><br /><br /> <span data-ttu-id="4eb1d-121">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="4eb1d-121">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4eb1d-122">親要素</span><span class="sxs-lookup"><span data-stu-id="4eb1d-122">Parent Elements</span></span>

|<span data-ttu-id="4eb1d-123">要素</span><span class="sxs-lookup"><span data-stu-id="4eb1d-123">Element</span></span>|<span data-ttu-id="4eb1d-124">説明</span><span class="sxs-lookup"><span data-stu-id="4eb1d-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4eb1d-125">GroupBy の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4eb1d-125">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="4eb1d-126">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="4eb1d-126">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4eb1d-127">解説</span><span class="sxs-lookup"><span data-stu-id="4eb1d-127">Remarks</span></span>

<span data-ttu-id="4eb1d-128">この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="4eb1d-128">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="4eb1d-129">参照</span><span class="sxs-lookup"><span data-stu-id="4eb1d-129">See Also</span></span>

[<span data-ttu-id="4eb1d-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="4eb1d-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="4eb1d-131">GroupBy の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4eb1d-131">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)
