---
title: ビューのコントロールに対する CustomItem の式のバインド要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6760bf17be58411948ecb3437bf18bce40073954
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773812"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="6a178-102">View の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6a178-102">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="6a178-103">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="6a178-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="6a178-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6a178-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="6a178-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロールの要素 (形式) コントロール要素 (format) の CustomControl の CustomControl 要素 view (Format) CustomEntry 要素を使用して、ビュー (形式) のコントロールの Customentries の View (format) 式のバインド要素のビュー (形式) の Customentries 要素を表示します。</span><span class="sxs-lookup"><span data-stu-id="6a178-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6a178-106">構文</span><span class="sxs-lookup"><span data-stu-id="6a178-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="6a178-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6a178-107">Attributes and Elements</span></span>

<span data-ttu-id="6a178-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ExpressionBinding` ます。</span><span class="sxs-lookup"><span data-stu-id="6a178-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6a178-109">属性</span><span class="sxs-lookup"><span data-stu-id="6a178-109">Attributes</span></span>

<span data-ttu-id="6a178-110">なし。</span><span class="sxs-lookup"><span data-stu-id="6a178-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6a178-111">子要素</span><span class="sxs-lookup"><span data-stu-id="6a178-111">Child Elements</span></span>

|<span data-ttu-id="6a178-112">要素</span><span class="sxs-lookup"><span data-stu-id="6a178-112">Element</span></span>|<span data-ttu-id="6a178-113">説明</span><span class="sxs-lookup"><span data-stu-id="6a178-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="6a178-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="6a178-114">Optional element.</span></span><br /><br /> <span data-ttu-id="6a178-115">このコントロールによって使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="6a178-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="6a178-116">View の Controls の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6a178-116">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="6a178-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="6a178-117">Optional element.</span></span><br /><br /> <span data-ttu-id="6a178-118">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a178-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="6a178-119">View の Controls の ExpressionBinding の EnumerateCollection 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6a178-119">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="6a178-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="6a178-120">Optional element.</span></span><br /><br /> <span data-ttu-id="6a178-121">コレクションの要素を表示することを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a178-121">Specifies that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="6a178-122">ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="6a178-122">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="6a178-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="6a178-123">Optional element.</span></span><br /><br /> <span data-ttu-id="6a178-124">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="6a178-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="6a178-125">View の Controls の ExpressionBinding の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6a178-125">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="6a178-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="6a178-126">Optional element.</span></span><br /><br /> <span data-ttu-id="6a178-127">コントロールによって表示される値を持つ .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a178-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="6a178-128">View の Controls の ExpressionBinding の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6a178-128">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="6a178-129">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="6a178-129">Optional element.</span></span><br /><br /> <span data-ttu-id="6a178-130">コントロールによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a178-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6a178-131">親要素</span><span class="sxs-lookup"><span data-stu-id="6a178-131">Parent Elements</span></span>

|<span data-ttu-id="6a178-132">要素</span><span class="sxs-lookup"><span data-stu-id="6a178-132">Element</span></span>|<span data-ttu-id="6a178-133">説明</span><span class="sxs-lookup"><span data-stu-id="6a178-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6a178-134">View の Controls の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6a178-134">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="6a178-135">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="6a178-135">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6a178-136">解説</span><span class="sxs-lookup"><span data-stu-id="6a178-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="6a178-137">参照</span><span class="sxs-lookup"><span data-stu-id="6a178-137">See Also</span></span>

[<span data-ttu-id="6a178-138">View の Controls の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6a178-138">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="6a178-139">View の Controls の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6a178-139">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="6a178-140">View の Controls の ExpressionBinding の EnumerateCollection 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6a178-140">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="6a178-141">ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="6a178-141">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="6a178-142">View の Controls の ExpressionBinding の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6a178-142">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="6a178-143">View の Controls の ExpressionBinding の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6a178-143">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="6a178-144">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="6a178-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
