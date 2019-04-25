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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065922"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="97e3a-102">View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="97e3a-102">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="97e3a-103">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="97e3a-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="97e3a-104">この要素は、カスタム コントロールのビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="97e3a-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="97e3a-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素の表示 (カスタム コントロールの CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールのビュー (形式) CustomEntries 要素CustomEntry CustomItem ビュー (形式) のカスタム コントロール用のビュー (形式) ExpressionBinding 要素のカスタム コントロール用の形式) CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="97e3a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="97e3a-106">構文</span><span class="sxs-lookup"><span data-stu-id="97e3a-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="97e3a-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="97e3a-107">Attributes and Elements</span></span>

<span data-ttu-id="97e3a-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`ExpressionBinding`要素。</span><span class="sxs-lookup"><span data-stu-id="97e3a-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="97e3a-109">属性</span><span class="sxs-lookup"><span data-stu-id="97e3a-109">Attributes</span></span>

<span data-ttu-id="97e3a-110">なし。</span><span class="sxs-lookup"><span data-stu-id="97e3a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="97e3a-111">子要素</span><span class="sxs-lookup"><span data-stu-id="97e3a-111">Child Elements</span></span>

|<span data-ttu-id="97e3a-112">要素</span><span class="sxs-lookup"><span data-stu-id="97e3a-112">Element</span></span>|<span data-ttu-id="97e3a-113">説明</span><span class="sxs-lookup"><span data-stu-id="97e3a-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="97e3a-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="97e3a-114">Optional element.</span></span><br /><br /> <span data-ttu-id="97e3a-115">このコントロールで使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="97e3a-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="97e3a-116">ビュー (形式) のカスタム コントロールの ExpressionBinding CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="97e3a-116">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="97e3a-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="97e3a-117">Optional element.</span></span><br /><br /> <span data-ttu-id="97e3a-118">一般的なコントロールまたはビューのコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="97e3a-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="97e3a-119">ビュー (形式) のカスタム コントロールの ExpressionBinding EnumerateCollection 要素</span><span class="sxs-lookup"><span data-stu-id="97e3a-119">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="97e3a-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="97e3a-120">Optional element.</span></span><br /><br /> <span data-ttu-id="97e3a-121">コレクションの要素が表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="97e3a-121">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="97e3a-122">ビュー (形式) のカスタム コントロールの ExpressionBinding ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="97e3a-122">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="97e3a-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="97e3a-123">Optional element.</span></span><br /><br /> <span data-ttu-id="97e3a-124">このコントロールを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="97e3a-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="97e3a-125">ビュー (形式) のカスタム コントロールの ExpressionBinding の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="97e3a-125">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="97e3a-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="97e3a-126">Optional element.</span></span><br /><br /> <span data-ttu-id="97e3a-127">値を持つが、コントロールによって表示される、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="97e3a-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="97e3a-128">表示 (形式) CustomCustomControl ExpressionBinding の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="97e3a-128">ScriptBlock Element for ExpressionBinding for CustomCustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="97e3a-129">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="97e3a-129">Optional element.</span></span><br /><br /> <span data-ttu-id="97e3a-130">値を持つが、コントロールによって表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="97e3a-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="97e3a-131">親要素</span><span class="sxs-lookup"><span data-stu-id="97e3a-131">Parent Elements</span></span>

|<span data-ttu-id="97e3a-132">要素</span><span class="sxs-lookup"><span data-stu-id="97e3a-132">Element</span></span>|<span data-ttu-id="97e3a-133">説明</span><span class="sxs-lookup"><span data-stu-id="97e3a-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="97e3a-134">ビュー (形式) のカスタム コントロールの CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="97e3a-134">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="97e3a-135">カスタム コントロールのビューで表示するデータと表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="97e3a-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="97e3a-136">コメント</span><span class="sxs-lookup"><span data-stu-id="97e3a-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="97e3a-137">参照</span><span class="sxs-lookup"><span data-stu-id="97e3a-137">See Also</span></span>

[<span data-ttu-id="97e3a-138">ビュー (形式) のカスタム コントロールの ExpressionBinding CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="97e3a-138">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="97e3a-139">ビュー (形式) のカスタム コントロールの ExpressionBinding EnumerateCollection 要素</span><span class="sxs-lookup"><span data-stu-id="97e3a-139">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="97e3a-140">ビュー (形式) のカスタム コントロールの ExpressionBinding ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="97e3a-140">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="97e3a-141">ビュー (形式) のカスタム コントロールの ExpressionBinding の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="97e3a-141">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="97e3a-142">ビュー (形式) のカスタム コントロールの ExpressionBinding の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="97e3a-142">ScriptBlock Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="97e3a-143">ビュー (形式) のカスタム コントロールの CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="97e3a-143">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="97e3a-144">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="97e3a-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
