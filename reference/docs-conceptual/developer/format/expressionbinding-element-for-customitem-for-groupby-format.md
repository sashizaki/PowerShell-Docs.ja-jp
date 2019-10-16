---
title: GroupBy (Format) の CustomItem の式のバインド要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eae5088-7605-4ef2-a703-faf3e5a5fc94
caps.latest.revision: 8
ms.openlocfilehash: 4714bfd1530585aa80aabc010b86d25bf0c7f9c4
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368631"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a><span data-ttu-id="ca3fd-102">GroupBy の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ca3fd-102">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="ca3fd-103">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="ca3fd-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="ca3fd-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ca3fd-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="ca3fd-105">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素Groupby (format) の CustomControl の CustomItem 要素には、GroupBy (format) の CustomItem のバインド要素が指定しています。</span><span class="sxs-lookup"><span data-stu-id="ca3fd-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ca3fd-106">構文</span><span class="sxs-lookup"><span data-stu-id="ca3fd-106">Syntax</span></span>

```xml
<ExpressionBinding>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameofCommonCustomControl</CustomControlName>
  <EnumerateCollection/>
  <ItemSelectionCondition>...</ItemSelectionCondition>
  <PropertyName>Nameof.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate></ScriptBlock>
</ExpressionBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ca3fd-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="ca3fd-107">Attributes and Elements</span></span>

<span data-ttu-id="ca3fd-108">次のセクションでは、属性、子要素、`ExpressionBinding` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca3fd-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ca3fd-109">属性</span><span class="sxs-lookup"><span data-stu-id="ca3fd-109">Attributes</span></span>

<span data-ttu-id="ca3fd-110">なし。</span><span class="sxs-lookup"><span data-stu-id="ca3fd-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ca3fd-111">子要素</span><span class="sxs-lookup"><span data-stu-id="ca3fd-111">Child Elements</span></span>

|<span data-ttu-id="ca3fd-112">要素</span><span class="sxs-lookup"><span data-stu-id="ca3fd-112">Element</span></span>|<span data-ttu-id="ca3fd-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="ca3fd-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="ca3fd-114">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="ca3fd-114">Optional element.</span></span><br /><br /> <span data-ttu-id="ca3fd-115">このコントロールによって使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="ca3fd-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="ca3fd-116">GroupBy (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="ca3fd-116">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="ca3fd-117">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="ca3fd-117">Optional element.</span></span><br /><br /> <span data-ttu-id="ca3fd-118">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca3fd-118">Specifies the name of a common control or a view control.</span></span>|
|<span data-ttu-id="ca3fd-119">[GroupBy (Format) の式のバインドの列挙 Atecollection 要素](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)GroupBy (Format) の式のバインドの列挙 Atecollection 要素</span><span class="sxs-lookup"><span data-stu-id="ca3fd-119">[EnumerateCollection Element for ExpressionBinding for GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>|<span data-ttu-id="ca3fd-120">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="ca3fd-120">Optional element.</span></span><br /><br /> <span data-ttu-id="ca3fd-121">コレクションの要素が表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca3fd-121">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="ca3fd-122">GroupBy (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="ca3fd-122">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="ca3fd-123">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="ca3fd-123">Optional element.</span></span><br /><br /> <span data-ttu-id="ca3fd-124">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="ca3fd-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="ca3fd-125">GroupBy (Format) の式のバインドの PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="ca3fd-125">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="ca3fd-126">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="ca3fd-126">Optional element.</span></span><br /><br /> <span data-ttu-id="ca3fd-127">コントロールによって表示される値を持つ .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca3fd-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="ca3fd-128">GroupBy (Format) の式のバインドの ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="ca3fd-128">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="ca3fd-129">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="ca3fd-129">Optional element.</span></span><br /><br /> <span data-ttu-id="ca3fd-130">コントロールによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca3fd-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ca3fd-131">親要素</span><span class="sxs-lookup"><span data-stu-id="ca3fd-131">Parent Elements</span></span>

|<span data-ttu-id="ca3fd-132">要素</span><span class="sxs-lookup"><span data-stu-id="ca3fd-132">Element</span></span>|<span data-ttu-id="ca3fd-133">[説明]</span><span class="sxs-lookup"><span data-stu-id="ca3fd-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ca3fd-134">GroupBy の CustomEntry の CustomItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ca3fd-134">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="ca3fd-135">カスタムコントロールビューとその表示方法によって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="ca3fd-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="ca3fd-136">参照</span><span class="sxs-lookup"><span data-stu-id="ca3fd-136">See Also</span></span>

[<span data-ttu-id="ca3fd-137">GroupBy (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="ca3fd-137">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="ca3fd-138">GroupBy (Format) の式のバインドの列挙 Atecollection 要素</span><span class="sxs-lookup"><span data-stu-id="ca3fd-138">EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="ca3fd-139">GroupBy (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="ca3fd-139">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="ca3fd-140">GroupBy (Format) の式のバインドの PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="ca3fd-140">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="ca3fd-141">GroupBy (Format) の式のバインドの ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="ca3fd-141">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="ca3fd-142">GroupBy の CustomEntry の CustomItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ca3fd-142">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="ca3fd-143">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="ca3fd-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
