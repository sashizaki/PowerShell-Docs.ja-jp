---
ms.date: 09/13/2016
ms.topic: reference
title: View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)
description: View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)
ms.openlocfilehash: 8f4bfef4f6c65c6dabc7a776dda1083bac11fdf7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648189"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="893b8-103">View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="893b8-103">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="893b8-104">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="893b8-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="893b8-105">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="893b8-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="893b8-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の CustomControl 要素を表示するための CustomControl for view (format) CustomEntries 要素に対して、CustomControl for view (format) customentries 要素の CustomEntries for for view (format) の Customentries 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="893b8-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="893b8-107">構文</span><span class="sxs-lookup"><span data-stu-id="893b8-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="893b8-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="893b8-108">Attributes and Elements</span></span>

<span data-ttu-id="893b8-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ExpressionBinding` ます。</span><span class="sxs-lookup"><span data-stu-id="893b8-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="893b8-110">属性</span><span class="sxs-lookup"><span data-stu-id="893b8-110">Attributes</span></span>

<span data-ttu-id="893b8-111">なし。</span><span class="sxs-lookup"><span data-stu-id="893b8-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="893b8-112">子要素</span><span class="sxs-lookup"><span data-stu-id="893b8-112">Child Elements</span></span>

|<span data-ttu-id="893b8-113">要素</span><span class="sxs-lookup"><span data-stu-id="893b8-113">Element</span></span>|<span data-ttu-id="893b8-114">説明</span><span class="sxs-lookup"><span data-stu-id="893b8-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="893b8-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="893b8-115">Optional element.</span></span><br /><br /> <span data-ttu-id="893b8-116">このコントロールによって使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="893b8-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="893b8-117">View の CustomControl の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="893b8-117">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="893b8-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="893b8-118">Optional element.</span></span><br /><br /> <span data-ttu-id="893b8-119">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="893b8-119">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="893b8-120">View の CustomControl の ExpressionBinding の EnumerateCollection 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="893b8-120">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="893b8-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="893b8-121">Optional element.</span></span><br /><br /> <span data-ttu-id="893b8-122">コレクションの要素が表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="893b8-122">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="893b8-123">CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="893b8-123">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="893b8-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="893b8-124">Optional element.</span></span><br /><br /> <span data-ttu-id="893b8-125">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="893b8-125">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="893b8-126">View の CustomControl の ExpressionBinding の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="893b8-126">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="893b8-127">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="893b8-127">Optional element.</span></span><br /><br /> <span data-ttu-id="893b8-128">コントロールによって表示される値を持つ .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="893b8-128">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="893b8-129">CustomCustomControl for View (Format) の式のバインドの ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="893b8-129">ScriptBlock Element for ExpressionBinding for CustomCustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="893b8-130">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="893b8-130">Optional element.</span></span><br /><br /> <span data-ttu-id="893b8-131">コントロールによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="893b8-131">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="893b8-132">親要素</span><span class="sxs-lookup"><span data-stu-id="893b8-132">Parent Elements</span></span>

|<span data-ttu-id="893b8-133">要素</span><span class="sxs-lookup"><span data-stu-id="893b8-133">Element</span></span>|<span data-ttu-id="893b8-134">説明</span><span class="sxs-lookup"><span data-stu-id="893b8-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="893b8-135">View の CustomControl の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="893b8-135">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="893b8-136">カスタムコントロールビューとその表示方法によって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="893b8-136">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="893b8-137">解説</span><span class="sxs-lookup"><span data-stu-id="893b8-137">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="893b8-138">参照</span><span class="sxs-lookup"><span data-stu-id="893b8-138">See Also</span></span>

[<span data-ttu-id="893b8-139">View の CustomControl の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="893b8-139">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="893b8-140">View の CustomControl の ExpressionBinding の EnumerateCollection 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="893b8-140">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="893b8-141">CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="893b8-141">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="893b8-142">View の CustomControl の ExpressionBinding の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="893b8-142">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="893b8-143">View の CustomControl の ExpressionBinding の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="893b8-143">ScriptBlock Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="893b8-144">View の CustomControl の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="893b8-144">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="893b8-145">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="893b8-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
