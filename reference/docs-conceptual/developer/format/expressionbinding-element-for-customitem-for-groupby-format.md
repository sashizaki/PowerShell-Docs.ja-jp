---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の CustomItem の ExpressionBinding 要素 (書式)
description: GroupBy の CustomItem の ExpressionBinding 要素 (書式)
ms.openlocfilehash: 742d9f081a674dc3ee4c84d600933aaf57b2aa6b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655305"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a><span data-ttu-id="4c978-103">GroupBy の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4c978-103">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="4c978-104">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="4c978-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="4c978-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4c978-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="4c978-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素を使用して、groupby (形式) の CustomControl 要素に対して、groupby (format) CustomEntries 要素の CustomControl の CustomControl for groupby (format) の CustomEntry 要素を指定します。 groupby (形式) の Customentries のバインド要素。</span><span class="sxs-lookup"><span data-stu-id="4c978-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4c978-107">構文</span><span class="sxs-lookup"><span data-stu-id="4c978-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="4c978-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4c978-108">Attributes and Elements</span></span>

<span data-ttu-id="4c978-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ExpressionBinding` ます。</span><span class="sxs-lookup"><span data-stu-id="4c978-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4c978-110">属性</span><span class="sxs-lookup"><span data-stu-id="4c978-110">Attributes</span></span>

<span data-ttu-id="4c978-111">なし。</span><span class="sxs-lookup"><span data-stu-id="4c978-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4c978-112">子要素</span><span class="sxs-lookup"><span data-stu-id="4c978-112">Child Elements</span></span>

|<span data-ttu-id="4c978-113">要素</span><span class="sxs-lookup"><span data-stu-id="4c978-113">Element</span></span>|<span data-ttu-id="4c978-114">説明</span><span class="sxs-lookup"><span data-stu-id="4c978-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="4c978-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4c978-115">Optional element.</span></span><br /><br /> <span data-ttu-id="4c978-116">このコントロールによって使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="4c978-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="4c978-117">GroupBy の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4c978-117">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="4c978-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4c978-118">Optional element.</span></span><br /><br /> <span data-ttu-id="4c978-119">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4c978-119">Specifies the name of a common control or a view control.</span></span>|
|<span data-ttu-id="4c978-120">[GroupBy (Format) の式のバインドの列挙 Atecollection 要素](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)GroupBy (Format) の式のバインドの列挙 Atecollection 要素</span><span class="sxs-lookup"><span data-stu-id="4c978-120">[EnumerateCollection Element for ExpressionBinding for GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>|<span data-ttu-id="4c978-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4c978-121">Optional element.</span></span><br /><br /> <span data-ttu-id="4c978-122">コレクションの要素が表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4c978-122">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="4c978-123">GroupBy の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4c978-123">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="4c978-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4c978-124">Optional element.</span></span><br /><br /> <span data-ttu-id="4c978-125">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="4c978-125">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="4c978-126">GroupBy の ExpressionBinding の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4c978-126">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="4c978-127">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4c978-127">Optional element.</span></span><br /><br /> <span data-ttu-id="4c978-128">コントロールによって表示される値を持つ .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="4c978-128">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="4c978-129">GroupBy の ExpressionBinding の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4c978-129">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="4c978-130">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4c978-130">Optional element.</span></span><br /><br /> <span data-ttu-id="4c978-131">コントロールによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="4c978-131">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4c978-132">親要素</span><span class="sxs-lookup"><span data-stu-id="4c978-132">Parent Elements</span></span>

|<span data-ttu-id="4c978-133">要素</span><span class="sxs-lookup"><span data-stu-id="4c978-133">Element</span></span>|<span data-ttu-id="4c978-134">説明</span><span class="sxs-lookup"><span data-stu-id="4c978-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4c978-135">GroupBy の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4c978-135">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="4c978-136">カスタムコントロールビューとその表示方法によって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="4c978-136">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="4c978-137">参照</span><span class="sxs-lookup"><span data-stu-id="4c978-137">See Also</span></span>

[<span data-ttu-id="4c978-138">GroupBy の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4c978-138">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="4c978-139">GroupBy の ExpressionBinding の EnumerateCollection 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4c978-139">EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="4c978-140">GroupBy の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4c978-140">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="4c978-141">GroupBy の ExpressionBinding の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4c978-141">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="4c978-142">GroupBy の ExpressionBinding の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4c978-142">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="4c978-143">GroupBy の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4c978-143">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="4c978-144">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="4c978-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
