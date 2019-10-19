---
title: ビューのコントロールの式のバインドの ItemSelectionCondition 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82c15014-2440-410d-b02d-b7f1a49240a0
caps.latest.revision: 7
ms.openlocfilehash: 80f375c53c205c793600655fa6031d114871618e
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362941"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="51855-102">View の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="51855-102">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="51855-103">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="51855-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="51855-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="51855-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="51855-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素CustomControl for view (format) CustomEntry 要素は、ビュー (形式) のコントロールに対する Customentries のビュー (形式) 式のバインド要素のビュー (形式) の Customentries 要素のコントロールの CustomEntries に対して、ビュー (形式) 用に設定します。ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="51855-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="51855-106">構文</span><span class="sxs-lookup"><span data-stu-id="51855-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="51855-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="51855-107">Attributes and Elements</span></span>

<span data-ttu-id="51855-108">次のセクションでは、属性、子要素、`ItemSelectionCondition` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="51855-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="51855-109">属性</span><span class="sxs-lookup"><span data-stu-id="51855-109">Attributes</span></span>

<span data-ttu-id="51855-110">なし。</span><span class="sxs-lookup"><span data-stu-id="51855-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="51855-111">子要素</span><span class="sxs-lookup"><span data-stu-id="51855-111">Child Elements</span></span>

|<span data-ttu-id="51855-112">要素</span><span class="sxs-lookup"><span data-stu-id="51855-112">Element</span></span>|<span data-ttu-id="51855-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="51855-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="51855-114">ビューのコントロール (Format) の ItemSelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="51855-114">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="51855-115">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="51855-115">Optional element.</span></span><br /><br /> <span data-ttu-id="51855-116">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="51855-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="51855-117">ビューのコントロール (Format) の ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="51855-117">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="51855-118">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="51855-118">Optional element.</span></span><br /><br /> <span data-ttu-id="51855-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="51855-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="51855-120">親要素</span><span class="sxs-lookup"><span data-stu-id="51855-120">Parent Elements</span></span>

|<span data-ttu-id="51855-121">要素</span><span class="sxs-lookup"><span data-stu-id="51855-121">Element</span></span>|<span data-ttu-id="51855-122">[説明]</span><span class="sxs-lookup"><span data-stu-id="51855-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="51855-123">ビューのコントロールに対する CustomItem の式のバインド要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="51855-123">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="51855-124">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="51855-124">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="51855-125">コメント</span><span class="sxs-lookup"><span data-stu-id="51855-125">Remarks</span></span>

<span data-ttu-id="51855-126">この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="51855-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="51855-127">参照</span><span class="sxs-lookup"><span data-stu-id="51855-127">See Also</span></span>

[<span data-ttu-id="51855-128">ビューのコントロール (Format) の ItemSelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="51855-128">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="51855-129">ビューのコントロール (Format) の ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="51855-129">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="51855-130">ビューのコントロールに対する CustomItem の式のバインド要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="51855-130">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="51855-131">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="51855-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)