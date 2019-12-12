---
title: CustomControl for ビュー (Format) に対する CustomItem の式のバインド要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f5ebea5-ee9c-4b90-a116-12a1daa28fc7
caps.latest.revision: 7
ms.openlocfilehash: 226bbea1d7613ad3099e05e8caa9817ff16c1f42
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363151"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="f3241-102">View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f3241-102">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="f3241-103">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="f3241-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="f3241-104">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3241-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="f3241-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の CustomControl 要素を表示するための CustomControl for ビュー (形式) の Custommentry 要素の CustomControl for View (Format) CustomEntry for CustomControl の CustomItem 要素 for view (Format) CustomControl for View (format) の CustomItem のバインド要素</span><span class="sxs-lookup"><span data-stu-id="f3241-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f3241-106">構文</span><span class="sxs-lookup"><span data-stu-id="f3241-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="f3241-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="f3241-107">Attributes and Elements</span></span>

<span data-ttu-id="f3241-108">次のセクションでは、`ExpressionBinding` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f3241-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f3241-109">属性</span><span class="sxs-lookup"><span data-stu-id="f3241-109">Attributes</span></span>

<span data-ttu-id="f3241-110">なし。</span><span class="sxs-lookup"><span data-stu-id="f3241-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f3241-111">子要素</span><span class="sxs-lookup"><span data-stu-id="f3241-111">Child Elements</span></span>

|<span data-ttu-id="f3241-112">要素</span><span class="sxs-lookup"><span data-stu-id="f3241-112">Element</span></span>|<span data-ttu-id="f3241-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="f3241-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="f3241-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f3241-114">Optional element.</span></span><br /><br /> <span data-ttu-id="f3241-115">このコントロールによって使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="f3241-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="f3241-116">CustomControl for View (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="f3241-116">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="f3241-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f3241-117">Optional element.</span></span><br /><br /> <span data-ttu-id="f3241-118">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3241-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="f3241-119">CustomControl for View (Format) の式のバインドの列挙 Atecollection 要素</span><span class="sxs-lookup"><span data-stu-id="f3241-119">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="f3241-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f3241-120">Optional element.</span></span><br /><br /> <span data-ttu-id="f3241-121">コレクションの要素が表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3241-121">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="f3241-122">CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="f3241-122">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="f3241-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f3241-123">Optional element.</span></span><br /><br /> <span data-ttu-id="f3241-124">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="f3241-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="f3241-125">CustomControl for View (Format) の式のバインドの PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="f3241-125">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="f3241-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f3241-126">Optional element.</span></span><br /><br /> <span data-ttu-id="f3241-127">コントロールによって表示される値を持つ .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3241-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="f3241-128">CustomCustomControl for View (Format) の式のバインドの ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="f3241-128">ScriptBlock Element for ExpressionBinding for CustomCustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="f3241-129">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f3241-129">Optional element.</span></span><br /><br /> <span data-ttu-id="f3241-130">コントロールによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3241-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f3241-131">親要素</span><span class="sxs-lookup"><span data-stu-id="f3241-131">Parent Elements</span></span>

|<span data-ttu-id="f3241-132">要素</span><span class="sxs-lookup"><span data-stu-id="f3241-132">Element</span></span>|<span data-ttu-id="f3241-133">[説明]</span><span class="sxs-lookup"><span data-stu-id="f3241-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f3241-134">CustomEntry for CustomControl の CustomItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="f3241-134">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="f3241-135">カスタムコントロールビューとその表示方法によって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="f3241-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f3241-136">コメント</span><span class="sxs-lookup"><span data-stu-id="f3241-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="f3241-137">参照</span><span class="sxs-lookup"><span data-stu-id="f3241-137">See Also</span></span>

[<span data-ttu-id="f3241-138">CustomControl for View (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="f3241-138">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="f3241-139">CustomControl for View (Format) の式のバインドの列挙 Atecollection 要素</span><span class="sxs-lookup"><span data-stu-id="f3241-139">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="f3241-140">CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="f3241-140">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="f3241-141">CustomControl for View (Format) の式のバインドの PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="f3241-141">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="f3241-142">CustomControl for View (Format) の式のバインドの ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="f3241-142">ScriptBlock Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="f3241-143">CustomEntry for CustomControl の CustomItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="f3241-143">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="f3241-144">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="f3241-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
