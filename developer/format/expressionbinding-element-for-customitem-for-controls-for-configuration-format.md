---
title: ExpressionBinding 要素の構成 (形式) のコントロールの CustomItem |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6649d07-4762-4602-9b4b-d9e2e9e63312
caps.latest.revision: 13
ms.openlocfilehash: 531ff447f8407a737131a38351d7e4c6e7da90fb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065946"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="2e8b2-102">Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2e8b2-102">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="2e8b2-103">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="2e8b2-104">この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="2e8b2-105">構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素構成 (形式) のコントロールの CustomItem 構成 ExpressionBinding 要素のコントロールの CustomEntry の構成 (形式) CustomItem 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="2e8b2-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2e8b2-106">構文</span><span class="sxs-lookup"><span data-stu-id="2e8b2-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="2e8b2-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2e8b2-107">Attributes and Elements</span></span>

<span data-ttu-id="2e8b2-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`ExpressionBinding`要素。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2e8b2-109">属性</span><span class="sxs-lookup"><span data-stu-id="2e8b2-109">Attributes</span></span>

<span data-ttu-id="2e8b2-110">なし。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2e8b2-111">子要素</span><span class="sxs-lookup"><span data-stu-id="2e8b2-111">Child Elements</span></span>

|<span data-ttu-id="2e8b2-112">要素</span><span class="sxs-lookup"><span data-stu-id="2e8b2-112">Element</span></span>|<span data-ttu-id="2e8b2-113">説明</span><span class="sxs-lookup"><span data-stu-id="2e8b2-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="2e8b2-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-114">Optional element.</span></span><br /><br /> <span data-ttu-id="2e8b2-115">このコントロールで使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="2e8b2-116">ExpressionBinding の構成 (形式) のコントロールの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="2e8b2-116">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="2e8b2-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-117">Optional element.</span></span><br /><br /> <span data-ttu-id="2e8b2-118">一般的なコントロールまたはビューのコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="2e8b2-119">ExpressionBinding の構成 (形式) のコントロールの EnumerateCollection 要素</span><span class="sxs-lookup"><span data-stu-id="2e8b2-119">EnumerateCollection Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="2e8b2-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-120">Optional element.</span></span><br /><br /> <span data-ttu-id="2e8b2-121">コレクションの要素がコントロールによって表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-121">Specified that the elements of collections are displayed by the control.</span></span>|
|[<span data-ttu-id="2e8b2-122">ExpressionBinding の構成 (形式) のコントロールの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="2e8b2-122">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="2e8b2-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-123">Optional element.</span></span><br /><br /> <span data-ttu-id="2e8b2-124">この一般的なコントロールを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-124">Defines the condition that must exist for this common control to be used.</span></span>|
|[<span data-ttu-id="2e8b2-125">ExpressionBinding の構成 (形式) のコントロールの PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="2e8b2-125">PropertyName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="2e8b2-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-126">Optional element.</span></span><br /><br /> <span data-ttu-id="2e8b2-127">値を持つが、一般的なコントロールによって表示される、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-127">Specifies the .NET property whose value is displayed by the common control.</span></span>|
|[<span data-ttu-id="2e8b2-128">ExpressionBinding の構成 (形式) のコントロールの ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="2e8b2-128">ScriptBlock Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="2e8b2-129">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-129">Optional element.</span></span><br /><br /> <span data-ttu-id="2e8b2-130">値を持つが、一般的なコントロールによって表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-130">Specifies the script whose value is displayed by the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2e8b2-131">親要素</span><span class="sxs-lookup"><span data-stu-id="2e8b2-131">Parent Elements</span></span>

|<span data-ttu-id="2e8b2-132">要素</span><span class="sxs-lookup"><span data-stu-id="2e8b2-132">Element</span></span>|<span data-ttu-id="2e8b2-133">説明</span><span class="sxs-lookup"><span data-stu-id="2e8b2-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2e8b2-134">コントロールの構成の CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="2e8b2-134">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="2e8b2-135">カスタム コントロールのビューで表示するデータと表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2e8b2-136">コメント</span><span class="sxs-lookup"><span data-stu-id="2e8b2-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="2e8b2-137">参照</span><span class="sxs-lookup"><span data-stu-id="2e8b2-137">See Also</span></span>

[<span data-ttu-id="2e8b2-138">コントロールの構成の CustomEntry CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="2e8b2-138">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="2e8b2-139">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="2e8b2-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
