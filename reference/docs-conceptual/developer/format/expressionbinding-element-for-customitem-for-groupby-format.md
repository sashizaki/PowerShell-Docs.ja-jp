---
title: GroupBy (Format) の CustomItem の式のバインド要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5b0017e487aab4ffcbf901cd44aad9b275b22832
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773727"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a><span data-ttu-id="9d280-102">GroupBy の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9d280-102">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="9d280-103">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="9d280-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="9d280-104">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="9d280-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="9d280-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素を使用して、groupby (形式) の CustomControl 要素に対して、groupby (format) CustomEntries 要素の CustomControl の CustomControl for groupby (format) の CustomEntry 要素を指定します。 groupby (形式) の Customentries のバインド要素。</span><span class="sxs-lookup"><span data-stu-id="9d280-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9d280-106">構文</span><span class="sxs-lookup"><span data-stu-id="9d280-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="9d280-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9d280-107">Attributes and Elements</span></span>

<span data-ttu-id="9d280-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ExpressionBinding` ます。</span><span class="sxs-lookup"><span data-stu-id="9d280-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9d280-109">属性</span><span class="sxs-lookup"><span data-stu-id="9d280-109">Attributes</span></span>

<span data-ttu-id="9d280-110">なし。</span><span class="sxs-lookup"><span data-stu-id="9d280-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9d280-111">子要素</span><span class="sxs-lookup"><span data-stu-id="9d280-111">Child Elements</span></span>

|<span data-ttu-id="9d280-112">要素</span><span class="sxs-lookup"><span data-stu-id="9d280-112">Element</span></span>|<span data-ttu-id="9d280-113">説明</span><span class="sxs-lookup"><span data-stu-id="9d280-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="9d280-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="9d280-114">Optional element.</span></span><br /><br /> <span data-ttu-id="9d280-115">このコントロールによって使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="9d280-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="9d280-116">GroupBy の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9d280-116">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="9d280-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="9d280-117">Optional element.</span></span><br /><br /> <span data-ttu-id="9d280-118">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d280-118">Specifies the name of a common control or a view control.</span></span>|
|<span data-ttu-id="9d280-119">[GroupBy (Format) の式のバインドの列挙 Atecollection 要素](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)GroupBy (Format) の式のバインドの列挙 Atecollection 要素</span><span class="sxs-lookup"><span data-stu-id="9d280-119">[EnumerateCollection Element for ExpressionBinding for GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>|<span data-ttu-id="9d280-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="9d280-120">Optional element.</span></span><br /><br /> <span data-ttu-id="9d280-121">コレクションの要素が表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d280-121">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="9d280-122">GroupBy の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9d280-122">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="9d280-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="9d280-123">Optional element.</span></span><br /><br /> <span data-ttu-id="9d280-124">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="9d280-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="9d280-125">GroupBy の ExpressionBinding の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9d280-125">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="9d280-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="9d280-126">Optional element.</span></span><br /><br /> <span data-ttu-id="9d280-127">コントロールによって表示される値を持つ .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d280-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="9d280-128">GroupBy の ExpressionBinding の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9d280-128">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="9d280-129">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="9d280-129">Optional element.</span></span><br /><br /> <span data-ttu-id="9d280-130">コントロールによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d280-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9d280-131">親要素</span><span class="sxs-lookup"><span data-stu-id="9d280-131">Parent Elements</span></span>

|<span data-ttu-id="9d280-132">要素</span><span class="sxs-lookup"><span data-stu-id="9d280-132">Element</span></span>|<span data-ttu-id="9d280-133">説明</span><span class="sxs-lookup"><span data-stu-id="9d280-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9d280-134">GroupBy の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9d280-134">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="9d280-135">カスタムコントロールビューとその表示方法によって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="9d280-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="9d280-136">参照</span><span class="sxs-lookup"><span data-stu-id="9d280-136">See Also</span></span>

[<span data-ttu-id="9d280-137">GroupBy の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9d280-137">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="9d280-138">GroupBy の ExpressionBinding の EnumerateCollection 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9d280-138">EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="9d280-139">GroupBy の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9d280-139">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="9d280-140">GroupBy の ExpressionBinding の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9d280-140">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="9d280-141">GroupBy の ExpressionBinding の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9d280-141">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="9d280-142">GroupBy の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9d280-142">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="9d280-143">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="9d280-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
