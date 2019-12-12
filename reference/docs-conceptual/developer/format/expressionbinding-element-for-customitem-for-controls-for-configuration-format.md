---
title: 構成用のコントロール用の CustomItem の式のバインド要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6649d07-4762-4602-9b4b-d9e2e9e63312
caps.latest.revision: 13
ms.openlocfilehash: 531ff447f8407a737131a38351d7e4c6e7da90fb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363191"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="7038b-102">Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7038b-102">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="7038b-103">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="7038b-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="7038b-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7038b-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="7038b-105">Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素形式) CustomControl の CustomEntry 要素を構成するためのコントロール用の CustomEntry 要素を構成するためのコントロール用 CustomItem 要素の構成式のバインド要素 CustomItem の構成 (形式)</span><span class="sxs-lookup"><span data-stu-id="7038b-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7038b-106">構文</span><span class="sxs-lookup"><span data-stu-id="7038b-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="7038b-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="7038b-107">Attributes and Elements</span></span>

<span data-ttu-id="7038b-108">次のセクションでは、`ExpressionBinding` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7038b-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7038b-109">属性</span><span class="sxs-lookup"><span data-stu-id="7038b-109">Attributes</span></span>

<span data-ttu-id="7038b-110">なし。</span><span class="sxs-lookup"><span data-stu-id="7038b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7038b-111">子要素</span><span class="sxs-lookup"><span data-stu-id="7038b-111">Child Elements</span></span>

|<span data-ttu-id="7038b-112">要素</span><span class="sxs-lookup"><span data-stu-id="7038b-112">Element</span></span>|<span data-ttu-id="7038b-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="7038b-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="7038b-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="7038b-114">Optional element.</span></span><br /><br /> <span data-ttu-id="7038b-115">このコントロールによって使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="7038b-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="7038b-116">構成用のコントロールの式のバインドの CustomControlName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7038b-116">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="7038b-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="7038b-117">Optional element.</span></span><br /><br /> <span data-ttu-id="7038b-118">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7038b-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="7038b-119">構成対象のコントロールの式のバインドの列挙 Atecollection 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7038b-119">EnumerateCollection Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="7038b-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="7038b-120">Optional element.</span></span><br /><br /> <span data-ttu-id="7038b-121">コレクションの要素がコントロールによって表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7038b-121">Specified that the elements of collections are displayed by the control.</span></span>|
|[<span data-ttu-id="7038b-122">構成用のコントロールの式のバインドの ItemSelectionCondition 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7038b-122">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="7038b-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="7038b-123">Optional element.</span></span><br /><br /> <span data-ttu-id="7038b-124">このコモンコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="7038b-124">Defines the condition that must exist for this common control to be used.</span></span>|
|[<span data-ttu-id="7038b-125">構成用のコントロールの式のバインドの PropertyName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="7038b-125">PropertyName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="7038b-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="7038b-126">Optional element.</span></span><br /><br /> <span data-ttu-id="7038b-127">コモンコントロールによって表示される値を持つ .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="7038b-127">Specifies the .NET property whose value is displayed by the common control.</span></span>|
|[<span data-ttu-id="7038b-128">構成用のコントロールの式のバインドの ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7038b-128">ScriptBlock Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="7038b-129">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="7038b-129">Optional element.</span></span><br /><br /> <span data-ttu-id="7038b-130">共通コントロールによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7038b-130">Specifies the script whose value is displayed by the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7038b-131">親要素</span><span class="sxs-lookup"><span data-stu-id="7038b-131">Parent Elements</span></span>

|<span data-ttu-id="7038b-132">要素</span><span class="sxs-lookup"><span data-stu-id="7038b-132">Element</span></span>|<span data-ttu-id="7038b-133">[説明]</span><span class="sxs-lookup"><span data-stu-id="7038b-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7038b-134">構成のための CustomEntry コントロールの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="7038b-134">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="7038b-135">カスタムコントロールビューとその表示方法によって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="7038b-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7038b-136">コメント</span><span class="sxs-lookup"><span data-stu-id="7038b-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="7038b-137">参照</span><span class="sxs-lookup"><span data-stu-id="7038b-137">See Also</span></span>

[<span data-ttu-id="7038b-138">構成のための CustomEntry コントロールの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="7038b-138">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="7038b-139">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="7038b-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
