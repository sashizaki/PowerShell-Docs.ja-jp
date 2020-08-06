---
title: CustomControl for ビュー (Format) に対する CustomItem の式のバインド要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1885a2820c0cb250aa6fda80544f58d06136cfeb
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773795"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="55af8-102">View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="55af8-102">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="55af8-103">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="55af8-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="55af8-104">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="55af8-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="55af8-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の CustomControl 要素を表示するための CustomControl for view (format) CustomEntries 要素に対して、CustomControl for view (format) customentries 要素の CustomEntries for for view (format) の Customentries 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="55af8-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="55af8-106">構文</span><span class="sxs-lookup"><span data-stu-id="55af8-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="55af8-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="55af8-107">Attributes and Elements</span></span>

<span data-ttu-id="55af8-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ExpressionBinding` ます。</span><span class="sxs-lookup"><span data-stu-id="55af8-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="55af8-109">属性</span><span class="sxs-lookup"><span data-stu-id="55af8-109">Attributes</span></span>

<span data-ttu-id="55af8-110">なし。</span><span class="sxs-lookup"><span data-stu-id="55af8-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="55af8-111">子要素</span><span class="sxs-lookup"><span data-stu-id="55af8-111">Child Elements</span></span>

|<span data-ttu-id="55af8-112">要素</span><span class="sxs-lookup"><span data-stu-id="55af8-112">Element</span></span>|<span data-ttu-id="55af8-113">説明</span><span class="sxs-lookup"><span data-stu-id="55af8-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="55af8-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="55af8-114">Optional element.</span></span><br /><br /> <span data-ttu-id="55af8-115">このコントロールによって使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="55af8-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="55af8-116">View の CustomControl の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="55af8-116">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="55af8-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="55af8-117">Optional element.</span></span><br /><br /> <span data-ttu-id="55af8-118">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="55af8-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="55af8-119">View の CustomControl の ExpressionBinding の EnumerateCollection 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="55af8-119">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="55af8-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="55af8-120">Optional element.</span></span><br /><br /> <span data-ttu-id="55af8-121">コレクションの要素が表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="55af8-121">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="55af8-122">CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="55af8-122">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="55af8-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="55af8-123">Optional element.</span></span><br /><br /> <span data-ttu-id="55af8-124">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="55af8-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="55af8-125">View の CustomControl の ExpressionBinding の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="55af8-125">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="55af8-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="55af8-126">Optional element.</span></span><br /><br /> <span data-ttu-id="55af8-127">コントロールによって表示される値を持つ .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="55af8-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="55af8-128">CustomCustomControl for View (Format) の式のバインドの ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="55af8-128">ScriptBlock Element for ExpressionBinding for CustomCustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="55af8-129">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="55af8-129">Optional element.</span></span><br /><br /> <span data-ttu-id="55af8-130">コントロールによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="55af8-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="55af8-131">親要素</span><span class="sxs-lookup"><span data-stu-id="55af8-131">Parent Elements</span></span>

|<span data-ttu-id="55af8-132">要素</span><span class="sxs-lookup"><span data-stu-id="55af8-132">Element</span></span>|<span data-ttu-id="55af8-133">説明</span><span class="sxs-lookup"><span data-stu-id="55af8-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="55af8-134">View の CustomControl の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="55af8-134">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="55af8-135">カスタムコントロールビューとその表示方法によって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="55af8-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="55af8-136">解説</span><span class="sxs-lookup"><span data-stu-id="55af8-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="55af8-137">参照</span><span class="sxs-lookup"><span data-stu-id="55af8-137">See Also</span></span>

[<span data-ttu-id="55af8-138">View の CustomControl の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="55af8-138">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="55af8-139">View の CustomControl の ExpressionBinding の EnumerateCollection 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="55af8-139">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="55af8-140">CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="55af8-140">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="55af8-141">View の CustomControl の ExpressionBinding の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="55af8-141">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="55af8-142">View の CustomControl の ExpressionBinding の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="55af8-142">ScriptBlock Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="55af8-143">View の CustomControl の CustomEntry の CustomItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="55af8-143">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="55af8-144">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="55af8-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
