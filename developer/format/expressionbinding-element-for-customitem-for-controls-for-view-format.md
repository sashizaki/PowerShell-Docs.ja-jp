---
title: ExpressionBinding 要素のビュー (形式) のコントロールの CustomItem |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b9da6c5-548b-480f-86ae-6de6fecabaca
caps.latest.revision: 8
ms.openlocfilehash: 06089730008839f18c471711a4b4411722f99c38
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858298"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="0a89d-102">View の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0a89d-102">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="0a89d-103">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="0a89d-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="0a89d-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0a89d-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="0a89d-105">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry CustomItem ビュー (形式) のコントロールのビュー (形式) ExpressionBinding 要素のコントロールのビュー (形式) CustomItem 要素のコントロールのビュー (形式) CustomEntry 要素のカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="0a89d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0a89d-106">構文</span><span class="sxs-lookup"><span data-stu-id="0a89d-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="0a89d-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="0a89d-107">Attributes and Elements</span></span>

<span data-ttu-id="0a89d-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`ExpressionBinding`要素。</span><span class="sxs-lookup"><span data-stu-id="0a89d-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0a89d-109">属性</span><span class="sxs-lookup"><span data-stu-id="0a89d-109">Attributes</span></span>

<span data-ttu-id="0a89d-110">なし。</span><span class="sxs-lookup"><span data-stu-id="0a89d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0a89d-111">子要素</span><span class="sxs-lookup"><span data-stu-id="0a89d-111">Child Elements</span></span>

|<span data-ttu-id="0a89d-112">要素</span><span class="sxs-lookup"><span data-stu-id="0a89d-112">Element</span></span>|<span data-ttu-id="0a89d-113">説明</span><span class="sxs-lookup"><span data-stu-id="0a89d-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="0a89d-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="0a89d-114">Optional element.</span></span><br /><br /> <span data-ttu-id="0a89d-115">このコントロールで使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="0a89d-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="0a89d-116">コントロールが表示されます (形式) の ExpressionBinding CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="0a89d-116">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="0a89d-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="0a89d-117">Optional element.</span></span><br /><br /> <span data-ttu-id="0a89d-118">一般的なコントロールまたはビューのコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0a89d-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="0a89d-119">コントロールが表示されます (形式) の ExpressionBinding EnumerateCollection 要素</span><span class="sxs-lookup"><span data-stu-id="0a89d-119">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="0a89d-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="0a89d-120">Optional element.</span></span><br /><br /> <span data-ttu-id="0a89d-121">コレクションの要素が表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="0a89d-121">Specifies that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="0a89d-122">コントロールが表示されます (形式) の ExpressionBinding の ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="0a89d-122">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="0a89d-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="0a89d-123">Optional element.</span></span><br /><br /> <span data-ttu-id="0a89d-124">このコントロールを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="0a89d-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="0a89d-125">コントロールが表示されます (形式) の ExpressionBinding の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="0a89d-125">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="0a89d-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="0a89d-126">Optional element.</span></span><br /><br /> <span data-ttu-id="0a89d-127">値を持つが、コントロールによって表示される、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="0a89d-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="0a89d-128">コントロールが表示されます (形式) の ExpressionBinding の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="0a89d-128">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="0a89d-129">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="0a89d-129">Optional element.</span></span><br /><br /> <span data-ttu-id="0a89d-130">値を持つが、コントロールによって表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="0a89d-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0a89d-131">親要素</span><span class="sxs-lookup"><span data-stu-id="0a89d-131">Parent Elements</span></span>

|<span data-ttu-id="0a89d-132">要素</span><span class="sxs-lookup"><span data-stu-id="0a89d-132">Element</span></span>|<span data-ttu-id="0a89d-133">説明</span><span class="sxs-lookup"><span data-stu-id="0a89d-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0a89d-134">コントロールが表示されます (形式) の CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="0a89d-134">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="0a89d-135">どのようなデータが、コントロールによって表示され、表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="0a89d-135">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0a89d-136">コメント</span><span class="sxs-lookup"><span data-stu-id="0a89d-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="0a89d-137">参照</span><span class="sxs-lookup"><span data-stu-id="0a89d-137">See Also</span></span>

[<span data-ttu-id="0a89d-138">コントロールが表示されます (形式) の CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="0a89d-138">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="0a89d-139">コントロールが表示されます (形式) の ExpressionBinding CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="0a89d-139">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="0a89d-140">コントロールが表示されます (形式) の ExpressionBinding EnumerateCollection 要素</span><span class="sxs-lookup"><span data-stu-id="0a89d-140">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="0a89d-141">コントロールが表示されます (形式) の ExpressionBinding の ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="0a89d-141">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="0a89d-142">コントロールが表示されます (形式) の ExpressionBinding の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="0a89d-142">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="0a89d-143">コントロールが表示されます (形式) の ExpressionBinding の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="0a89d-143">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="0a89d-144">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="0a89d-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
