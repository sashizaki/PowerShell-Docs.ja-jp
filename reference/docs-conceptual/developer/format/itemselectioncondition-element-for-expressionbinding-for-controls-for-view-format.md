---
ms.date: 09/13/2016
ms.topic: reference
title: View の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)
description: View の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)
ms.openlocfilehash: adbe747bdb4f6c1d180e5b630247de0fd3d72b85
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648064"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="a446f-103">View の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a446f-103">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="a446f-104">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="a446f-104">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="a446f-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a446f-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="a446f-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロール要素 (書式) のコントロールの要素 (形式) コントロール要素を表示するためのコントロールの CustomControl 要素 (形式) CustomControl for ビュー (形式) の CustomEntries 要素ビュー (format) のコントロール用の CustomEntries のコントロールのビュー (形式) の式のバインド要素を表示するためのコントロール用の Customentries のバインド要素 (format) ビューのコントロールの式のバインドのバインド要素 (format)</span><span class="sxs-lookup"><span data-stu-id="a446f-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a446f-107">構文</span><span class="sxs-lookup"><span data-stu-id="a446f-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a446f-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a446f-108">Attributes and Elements</span></span>

<span data-ttu-id="a446f-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ItemSelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="a446f-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a446f-110">属性</span><span class="sxs-lookup"><span data-stu-id="a446f-110">Attributes</span></span>

<span data-ttu-id="a446f-111">なし。</span><span class="sxs-lookup"><span data-stu-id="a446f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a446f-112">子要素</span><span class="sxs-lookup"><span data-stu-id="a446f-112">Child Elements</span></span>

|<span data-ttu-id="a446f-113">要素</span><span class="sxs-lookup"><span data-stu-id="a446f-113">Element</span></span>|<span data-ttu-id="a446f-114">説明</span><span class="sxs-lookup"><span data-stu-id="a446f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a446f-115">View の Controls の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a446f-115">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="a446f-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a446f-116">Optional element.</span></span><br /><br /> <span data-ttu-id="a446f-117">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="a446f-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="a446f-118">View の Controls の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a446f-118">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="a446f-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a446f-119">Optional element.</span></span><br /><br /> <span data-ttu-id="a446f-120">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a446f-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a446f-121">親要素</span><span class="sxs-lookup"><span data-stu-id="a446f-121">Parent Elements</span></span>

|<span data-ttu-id="a446f-122">要素</span><span class="sxs-lookup"><span data-stu-id="a446f-122">Element</span></span>|<span data-ttu-id="a446f-123">説明</span><span class="sxs-lookup"><span data-stu-id="a446f-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a446f-124">View の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a446f-124">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="a446f-125">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="a446f-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a446f-126">解説</span><span class="sxs-lookup"><span data-stu-id="a446f-126">Remarks</span></span>

<span data-ttu-id="a446f-127">この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a446f-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="a446f-128">参照</span><span class="sxs-lookup"><span data-stu-id="a446f-128">See Also</span></span>

[<span data-ttu-id="a446f-129">View の Controls の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a446f-129">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="a446f-130">View の Controls の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a446f-130">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="a446f-131">View の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a446f-131">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="a446f-132">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="a446f-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
