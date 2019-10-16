---
title: CustomControl (Format) の式のバインドの ItemSelectionCondition 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f4bea9d8-27ad-410e-ad48-287f807d3e4e
caps.latest.revision: 7
ms.openlocfilehash: 18b0113c9b7b0895a1093cb0b56cd2d02c74a6c1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362911"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a><span data-ttu-id="d17ca-102">CustomControl の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d17ca-102">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>

<span data-ttu-id="d17ca-103">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="d17ca-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="d17ca-104">コントロール項目に指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="d17ca-104">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="d17ca-105">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d17ca-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="d17ca-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素を表示するための CustomEntries for ビュー (形式) の Custommentry 要素CustomControl for View (Format) の式バインドの CustomControl for view (format) ItemSelectionCondition 要素のための CustomEntry for view (format) 式のバインド要素</span><span class="sxs-lookup"><span data-stu-id="d17ca-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d17ca-107">構文</span><span class="sxs-lookup"><span data-stu-id="d17ca-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d17ca-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="d17ca-108">Attributes and Elements</span></span>

<span data-ttu-id="d17ca-109">次のセクションでは、属性、子要素、`ItemSelectionCondition` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d17ca-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d17ca-110">属性</span><span class="sxs-lookup"><span data-stu-id="d17ca-110">Attributes</span></span>

<span data-ttu-id="d17ca-111">なし。</span><span class="sxs-lookup"><span data-stu-id="d17ca-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d17ca-112">子要素</span><span class="sxs-lookup"><span data-stu-id="d17ca-112">Child Elements</span></span>

|<span data-ttu-id="d17ca-113">要素</span><span class="sxs-lookup"><span data-stu-id="d17ca-113">Element</span></span>|<span data-ttu-id="d17ca-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="d17ca-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d17ca-115">ビューの CustomControl の ItemSelectionCondition の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="d17ca-115">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="d17ca-116">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="d17ca-116">Optional element.</span></span><br /><br /> <span data-ttu-id="d17ca-117">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="d17ca-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="d17ca-118">CustomControl for ビュー (Format) の ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="d17ca-118">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="d17ca-119">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="d17ca-119">Optional element.</span></span><br /><br /> <span data-ttu-id="d17ca-120">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d17ca-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d17ca-121">親要素</span><span class="sxs-lookup"><span data-stu-id="d17ca-121">Parent Elements</span></span>

|<span data-ttu-id="d17ca-122">要素</span><span class="sxs-lookup"><span data-stu-id="d17ca-122">Element</span></span>|<span data-ttu-id="d17ca-123">[説明]</span><span class="sxs-lookup"><span data-stu-id="d17ca-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d17ca-124">CustomControl for ビュー (Format) に対する CustomItem の式のバインド要素</span><span class="sxs-lookup"><span data-stu-id="d17ca-124">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="d17ca-125">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="d17ca-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d17ca-126">コメント</span><span class="sxs-lookup"><span data-stu-id="d17ca-126">Remarks</span></span>

<span data-ttu-id="d17ca-127">この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d17ca-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="d17ca-128">参照</span><span class="sxs-lookup"><span data-stu-id="d17ca-128">See Also</span></span>

[<span data-ttu-id="d17ca-129">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="d17ca-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="d17ca-130">CustomControl for ビュー (Format) に対する CustomItem の式のバインド要素</span><span class="sxs-lookup"><span data-stu-id="d17ca-130">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
