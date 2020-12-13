---
ms.date: 09/13/2016
ms.topic: reference
title: CustomControl の ExpressionBinding の ItemSelectionCondition 要素 (書式)
description: CustomControl の ExpressionBinding の ItemSelectionCondition 要素 (書式)
ms.openlocfilehash: 38c88ad47e57cd20902c6b8aabdb0b8e8b682ba4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648040"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a><span data-ttu-id="9fe80-103">CustomControl の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9fe80-103">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>

<span data-ttu-id="9fe80-104">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="9fe80-104">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="9fe80-105">コントロール項目に指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="9fe80-105">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="9fe80-106">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="9fe80-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="9fe80-107">Configuration 要素 (Format) ViewDefinitions 要素 (形式) view Element (Format) CustomControl 要素 (Format) ビューの CustomEntries の CustomEntry 要素の CustomControl for view (format) の CustomEntries 要素を表示します。) CustomControl for View (Format) の式のバインドのための CustomControl for view (format) ItemSelectionCondition 要素の customentries 要素に対する CustomEntry for view (format) 式のバインド要素のための Customentries 要素</span><span class="sxs-lookup"><span data-stu-id="9fe80-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9fe80-108">構文</span><span class="sxs-lookup"><span data-stu-id="9fe80-108">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9fe80-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9fe80-109">Attributes and Elements</span></span>

<span data-ttu-id="9fe80-110">次のセクションでは、要素の属性、子要素、および親要素について説明し `ItemSelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="9fe80-110">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9fe80-111">属性</span><span class="sxs-lookup"><span data-stu-id="9fe80-111">Attributes</span></span>

<span data-ttu-id="9fe80-112">なし。</span><span class="sxs-lookup"><span data-stu-id="9fe80-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9fe80-113">子要素</span><span class="sxs-lookup"><span data-stu-id="9fe80-113">Child Elements</span></span>

|<span data-ttu-id="9fe80-114">要素</span><span class="sxs-lookup"><span data-stu-id="9fe80-114">Element</span></span>|<span data-ttu-id="9fe80-115">説明</span><span class="sxs-lookup"><span data-stu-id="9fe80-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9fe80-116">ビューの CustomControl の ItemSelectionCondition の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="9fe80-116">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="9fe80-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="9fe80-117">Optional element.</span></span><br /><br /> <span data-ttu-id="9fe80-118">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="9fe80-118">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="9fe80-119">View の CustomControl の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9fe80-119">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="9fe80-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="9fe80-120">Optional element.</span></span><br /><br /> <span data-ttu-id="9fe80-121">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="9fe80-121">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9fe80-122">親要素</span><span class="sxs-lookup"><span data-stu-id="9fe80-122">Parent Elements</span></span>

|<span data-ttu-id="9fe80-123">要素</span><span class="sxs-lookup"><span data-stu-id="9fe80-123">Element</span></span>|<span data-ttu-id="9fe80-124">説明</span><span class="sxs-lookup"><span data-stu-id="9fe80-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9fe80-125">View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9fe80-125">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="9fe80-126">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="9fe80-126">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9fe80-127">解説</span><span class="sxs-lookup"><span data-stu-id="9fe80-127">Remarks</span></span>

<span data-ttu-id="9fe80-128">この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="9fe80-128">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="9fe80-129">参照</span><span class="sxs-lookup"><span data-stu-id="9fe80-129">See Also</span></span>

[<span data-ttu-id="9fe80-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="9fe80-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="9fe80-131">View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9fe80-131">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
