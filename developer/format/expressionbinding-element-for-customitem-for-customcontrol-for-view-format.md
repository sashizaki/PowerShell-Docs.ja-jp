---
title: ExpressionBinding 要素のビュー (形式) のカスタム コントロールの CustomItem |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f5ebea5-ee9c-4b90-a116-12a1daa28fc7
caps.latest.revision: 7
ms.openlocfilehash: 226bbea1d7613ad3099e05e8caa9817ff16c1f42
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860688"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="44bb5-102">View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="44bb5-102">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="44bb5-103">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="44bb5-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="44bb5-104">この要素は、カスタム コントロールのビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="44bb5-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="44bb5-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素の表示 (カスタム コントロールの CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールのビュー (形式) CustomEntries 要素CustomEntry CustomItem ビュー (形式) のカスタム コントロール用のビュー (形式) ExpressionBinding 要素のカスタム コントロール用の形式) CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="44bb5-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="44bb5-106">構文</span><span class="sxs-lookup"><span data-stu-id="44bb5-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="44bb5-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="44bb5-107">Attributes and Elements</span></span>

<span data-ttu-id="44bb5-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`ExpressionBinding`要素。</span><span class="sxs-lookup"><span data-stu-id="44bb5-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="44bb5-109">属性</span><span class="sxs-lookup"><span data-stu-id="44bb5-109">Attributes</span></span>

<span data-ttu-id="44bb5-110">なし。</span><span class="sxs-lookup"><span data-stu-id="44bb5-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="44bb5-111">子要素</span><span class="sxs-lookup"><span data-stu-id="44bb5-111">Child Elements</span></span>

|<span data-ttu-id="44bb5-112">要素</span><span class="sxs-lookup"><span data-stu-id="44bb5-112">Element</span></span>|<span data-ttu-id="44bb5-113">説明</span><span class="sxs-lookup"><span data-stu-id="44bb5-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="44bb5-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="44bb5-114">Optional element.</span></span><br /><br /> <span data-ttu-id="44bb5-115">このコントロールで使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="44bb5-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="44bb5-116">ビュー (形式) のカスタム コントロールの ExpressionBinding CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="44bb5-116">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="44bb5-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="44bb5-117">Optional element.</span></span><br /><br /> <span data-ttu-id="44bb5-118">一般的なコントロールまたはビューのコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="44bb5-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="44bb5-119">ビュー (形式) のカスタム コントロールの ExpressionBinding EnumerateCollection 要素</span><span class="sxs-lookup"><span data-stu-id="44bb5-119">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="44bb5-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="44bb5-120">Optional element.</span></span><br /><br /> <span data-ttu-id="44bb5-121">コレクションの要素が表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="44bb5-121">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="44bb5-122">ビュー (形式) のカスタム コントロールの ExpressionBinding ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="44bb5-122">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="44bb5-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="44bb5-123">Optional element.</span></span><br /><br /> <span data-ttu-id="44bb5-124">このコントロールを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="44bb5-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="44bb5-125">ビュー (形式) のカスタム コントロールの ExpressionBinding の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="44bb5-125">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="44bb5-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="44bb5-126">Optional element.</span></span><br /><br /> <span data-ttu-id="44bb5-127">値を持つが、コントロールによって表示される、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="44bb5-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="44bb5-128">表示 (形式) CustomCustomControl ExpressionBinding の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="44bb5-128">ScriptBlock Element for ExpressionBinding for CustomCustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="44bb5-129">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="44bb5-129">Optional element.</span></span><br /><br /> <span data-ttu-id="44bb5-130">値を持つが、コントロールによって表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="44bb5-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="44bb5-131">親要素</span><span class="sxs-lookup"><span data-stu-id="44bb5-131">Parent Elements</span></span>

|<span data-ttu-id="44bb5-132">要素</span><span class="sxs-lookup"><span data-stu-id="44bb5-132">Element</span></span>|<span data-ttu-id="44bb5-133">説明</span><span class="sxs-lookup"><span data-stu-id="44bb5-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="44bb5-134">ビュー (形式) のカスタム コントロールの CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="44bb5-134">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="44bb5-135">カスタム コントロールのビューで表示するデータと表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="44bb5-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="44bb5-136">コメント</span><span class="sxs-lookup"><span data-stu-id="44bb5-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="44bb5-137">参照</span><span class="sxs-lookup"><span data-stu-id="44bb5-137">See Also</span></span>

[<span data-ttu-id="44bb5-138">ビュー (形式) のカスタム コントロールの ExpressionBinding CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="44bb5-138">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="44bb5-139">ビュー (形式) のカスタム コントロールの ExpressionBinding EnumerateCollection 要素</span><span class="sxs-lookup"><span data-stu-id="44bb5-139">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="44bb5-140">ビュー (形式) のカスタム コントロールの ExpressionBinding ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="44bb5-140">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="44bb5-141">ビュー (形式) のカスタム コントロールの ExpressionBinding の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="44bb5-141">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="44bb5-142">ビュー (形式) のカスタム コントロールの ExpressionBinding の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="44bb5-142">ScriptBlock Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="44bb5-143">ビュー (形式) のカスタム コントロールの CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="44bb5-143">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="44bb5-144">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="44bb5-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
