---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)
description: Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)
ms.openlocfilehash: 1abcf2173e18d45839161b4c7e59f1ad238f81a1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655338"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="109cf-103">Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="109cf-103">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="109cf-104">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="109cf-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="109cf-105">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="109cf-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="109cf-106">Configuration 要素 (Format) コントロールの構成 (format) コントロールの要素の構成 (format) の CustomControl 要素の構成のためのコントロール要素の構成 (書式) の CustomControl の構成 (形式) のカスタム Customentries 要素の構成のためのコントロールの構成式の構成 (書式設定) のカスタム項目のバインド要素の構成 (形式)</span><span class="sxs-lookup"><span data-stu-id="109cf-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="109cf-107">構文</span><span class="sxs-lookup"><span data-stu-id="109cf-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="109cf-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="109cf-108">Attributes and Elements</span></span>

<span data-ttu-id="109cf-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ExpressionBinding` ます。</span><span class="sxs-lookup"><span data-stu-id="109cf-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="109cf-110">属性</span><span class="sxs-lookup"><span data-stu-id="109cf-110">Attributes</span></span>

<span data-ttu-id="109cf-111">なし。</span><span class="sxs-lookup"><span data-stu-id="109cf-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="109cf-112">子要素</span><span class="sxs-lookup"><span data-stu-id="109cf-112">Child Elements</span></span>

|<span data-ttu-id="109cf-113">要素</span><span class="sxs-lookup"><span data-stu-id="109cf-113">Element</span></span>|<span data-ttu-id="109cf-114">説明</span><span class="sxs-lookup"><span data-stu-id="109cf-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="109cf-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="109cf-115">Optional element.</span></span><br /><br /> <span data-ttu-id="109cf-116">このコントロールによって使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="109cf-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="109cf-117">Configuration の Controls の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="109cf-117">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="109cf-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="109cf-118">Optional element.</span></span><br /><br /> <span data-ttu-id="109cf-119">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="109cf-119">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="109cf-120">Configuration の Controls の ExpressionBinding の EnumerateCollection 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="109cf-120">EnumerateCollection Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="109cf-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="109cf-121">Optional element.</span></span><br /><br /> <span data-ttu-id="109cf-122">コレクションの要素がコントロールによって表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="109cf-122">Specified that the elements of collections are displayed by the control.</span></span>|
|[<span data-ttu-id="109cf-123">Configuration の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="109cf-123">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="109cf-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="109cf-124">Optional element.</span></span><br /><br /> <span data-ttu-id="109cf-125">このコモンコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="109cf-125">Defines the condition that must exist for this common control to be used.</span></span>|
|[<span data-ttu-id="109cf-126">Configuration の Controls の ExpressionBinding の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="109cf-126">PropertyName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="109cf-127">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="109cf-127">Optional element.</span></span><br /><br /> <span data-ttu-id="109cf-128">コモンコントロールによって表示される値を持つ .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="109cf-128">Specifies the .NET property whose value is displayed by the common control.</span></span>|
|[<span data-ttu-id="109cf-129">Configuration の Controls の ExpressionBinding の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="109cf-129">ScriptBlock Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="109cf-130">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="109cf-130">Optional element.</span></span><br /><br /> <span data-ttu-id="109cf-131">共通コントロールによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="109cf-131">Specifies the script whose value is displayed by the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="109cf-132">親要素</span><span class="sxs-lookup"><span data-stu-id="109cf-132">Parent Elements</span></span>

|<span data-ttu-id="109cf-133">要素</span><span class="sxs-lookup"><span data-stu-id="109cf-133">Element</span></span>|<span data-ttu-id="109cf-134">説明</span><span class="sxs-lookup"><span data-stu-id="109cf-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="109cf-135">構成のための CustomEntry コントロールの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="109cf-135">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="109cf-136">カスタムコントロールビューとその表示方法によって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="109cf-136">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="109cf-137">解説</span><span class="sxs-lookup"><span data-stu-id="109cf-137">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="109cf-138">参照</span><span class="sxs-lookup"><span data-stu-id="109cf-138">See Also</span></span>

[<span data-ttu-id="109cf-139">構成のための CustomEntry コントロールの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="109cf-139">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="109cf-140">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="109cf-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
