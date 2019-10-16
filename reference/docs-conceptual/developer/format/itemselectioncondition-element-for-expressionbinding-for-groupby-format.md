---
title: GroupBy (Format) の式のバインドの ItemSelectionCondition 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6af3be7d-921e-4cf7-bd5a-d87aa0b4efbd
caps.latest.revision: 7
ms.openlocfilehash: b2b0a0d1996392614807e08b820a72978e38a0cb
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365291"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="b316a-102">GroupBy の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b316a-102">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="b316a-103">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="b316a-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="b316a-104">コントロール項目に指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="b316a-104">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="b316a-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b316a-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="b316a-106">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素CustomControl for groupby (format) CustomItem 要素の CustomEntry for groupby (形式) の式のバインド要素 groupby (format) ItemSelectionCondition 要素に対して groupby (形式) の式のバインドのバインド要素</span><span class="sxs-lookup"><span data-stu-id="b316a-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b316a-107">構文</span><span class="sxs-lookup"><span data-stu-id="b316a-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b316a-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="b316a-108">Attributes and Elements</span></span>

<span data-ttu-id="b316a-109">次のセクションでは、属性、子要素、`ItemSelectionCondition` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b316a-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b316a-110">属性</span><span class="sxs-lookup"><span data-stu-id="b316a-110">Attributes</span></span>

<span data-ttu-id="b316a-111">なし。</span><span class="sxs-lookup"><span data-stu-id="b316a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b316a-112">子要素</span><span class="sxs-lookup"><span data-stu-id="b316a-112">Child Elements</span></span>

|<span data-ttu-id="b316a-113">要素</span><span class="sxs-lookup"><span data-stu-id="b316a-113">Element</span></span>|<span data-ttu-id="b316a-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="b316a-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b316a-115">GroupBy (Format) の ItemSelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="b316a-115">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="b316a-116">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="b316a-116">Optional element.</span></span><br /><br /> <span data-ttu-id="b316a-117">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="b316a-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="b316a-118">GroupBy (Format) の ItemSelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="b316a-118">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="b316a-119">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="b316a-119">Optional element.</span></span><br /><br /> <span data-ttu-id="b316a-120">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="b316a-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b316a-121">親要素</span><span class="sxs-lookup"><span data-stu-id="b316a-121">Parent Elements</span></span>

|<span data-ttu-id="b316a-122">要素</span><span class="sxs-lookup"><span data-stu-id="b316a-122">Element</span></span>|<span data-ttu-id="b316a-123">[説明]</span><span class="sxs-lookup"><span data-stu-id="b316a-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b316a-124">GroupBy (Format) の CustomItem の式のバインド要素</span><span class="sxs-lookup"><span data-stu-id="b316a-124">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="b316a-125">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="b316a-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b316a-126">コメント</span><span class="sxs-lookup"><span data-stu-id="b316a-126">Remarks</span></span>

<span data-ttu-id="b316a-127">この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b316a-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="b316a-128">参照</span><span class="sxs-lookup"><span data-stu-id="b316a-128">See Also</span></span>

[<span data-ttu-id="b316a-129">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="b316a-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="b316a-130">GroupBy (Format) の CustomItem の式のバインド要素</span><span class="sxs-lookup"><span data-stu-id="b316a-130">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)
