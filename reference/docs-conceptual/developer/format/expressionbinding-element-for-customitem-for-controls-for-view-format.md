---
ms.date: 09/13/2016
ms.topic: reference
title: View の Controls の CustomItem の ExpressionBinding 要素 (書式)
description: View の Controls の CustomItem の ExpressionBinding 要素 (書式)
ms.openlocfilehash: da87bb26d21dcb051871e67997cc3fba7ce73c74
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649893"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="4267b-103">View の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4267b-103">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="4267b-104">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="4267b-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="4267b-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4267b-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="4267b-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロールの要素 (形式) コントロール要素 (format) の CustomControl の CustomControl 要素 view (Format) CustomEntry 要素を使用して、ビュー (形式) のコントロールの Customentries の View (format) 式のバインド要素のビュー (形式) の Customentries 要素を表示します。</span><span class="sxs-lookup"><span data-stu-id="4267b-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4267b-107">構文</span><span class="sxs-lookup"><span data-stu-id="4267b-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="4267b-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4267b-108">Attributes and Elements</span></span>

<span data-ttu-id="4267b-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ExpressionBinding` ます。</span><span class="sxs-lookup"><span data-stu-id="4267b-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4267b-110">属性</span><span class="sxs-lookup"><span data-stu-id="4267b-110">Attributes</span></span>

<span data-ttu-id="4267b-111">なし。</span><span class="sxs-lookup"><span data-stu-id="4267b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4267b-112">子要素</span><span class="sxs-lookup"><span data-stu-id="4267b-112">Child Elements</span></span>

|<span data-ttu-id="4267b-113">要素</span><span class="sxs-lookup"><span data-stu-id="4267b-113">Element</span></span>|<span data-ttu-id="4267b-114">説明</span><span class="sxs-lookup"><span data-stu-id="4267b-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="4267b-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4267b-115">Optional element.</span></span><br /><br /> <span data-ttu-id="4267b-116">このコントロールによって使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="4267b-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="4267b-117">View の Controls の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4267b-117">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="4267b-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4267b-118">Optional element.</span></span><br /><br /> <span data-ttu-id="4267b-119">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4267b-119">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="4267b-120">View の Controls の ExpressionBinding の EnumerateCollection 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4267b-120">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="4267b-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4267b-121">Optional element.</span></span><br /><br /> <span data-ttu-id="4267b-122">コレクションの要素を表示することを指定します。</span><span class="sxs-lookup"><span data-stu-id="4267b-122">Specifies that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="4267b-123">ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="4267b-123">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="4267b-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4267b-124">Optional element.</span></span><br /><br /> <span data-ttu-id="4267b-125">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="4267b-125">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="4267b-126">View の Controls の ExpressionBinding の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4267b-126">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="4267b-127">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4267b-127">Optional element.</span></span><br /><br /> <span data-ttu-id="4267b-128">コントロールによって表示される値を持つ .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="4267b-128">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="4267b-129">View の Controls の ExpressionBinding の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4267b-129">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="4267b-130">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4267b-130">Optional element.</span></span><br /><br /> <span data-ttu-id="4267b-131">コントロールによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="4267b-131">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4267b-132">親要素</span><span class="sxs-lookup"><span data-stu-id="4267b-132">Parent Elements</span></span>

|<span data-ttu-id="4267b-133">要素</span><span class="sxs-lookup"><span data-stu-id="4267b-133">Element</span></span>|<span data-ttu-id="4267b-134">説明</span><span class="sxs-lookup"><span data-stu-id="4267b-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4267b-135">View の Controls の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4267b-135">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="4267b-136">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="4267b-136">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4267b-137">解説</span><span class="sxs-lookup"><span data-stu-id="4267b-137">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="4267b-138">参照</span><span class="sxs-lookup"><span data-stu-id="4267b-138">See Also</span></span>

[<span data-ttu-id="4267b-139">View の Controls の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4267b-139">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="4267b-140">View の Controls の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4267b-140">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="4267b-141">View の Controls の ExpressionBinding の EnumerateCollection 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4267b-141">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="4267b-142">ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="4267b-142">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="4267b-143">View の Controls の ExpressionBinding の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4267b-143">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="4267b-144">View の Controls の ExpressionBinding の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4267b-144">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="4267b-145">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="4267b-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
