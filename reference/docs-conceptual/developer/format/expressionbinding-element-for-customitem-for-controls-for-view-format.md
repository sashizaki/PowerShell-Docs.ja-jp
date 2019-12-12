---
title: ビューのコントロールに対する CustomItem の式のバインド要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b9da6c5-548b-480f-86ae-6de6fecabaca
caps.latest.revision: 8
ms.openlocfilehash: 06089730008839f18c471711a4b4411722f99c38
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363781"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="a5f62-102">View の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a5f62-102">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="a5f62-103">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="a5f62-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="a5f62-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5f62-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="a5f62-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素CustomControl for view (format) CustomEntry 要素は、ビュー (形式) のコントロールに対する Customentries のビュー (形式) 式のバインド要素のビュー (形式) の Customentries 要素のコントロールの CustomEntries に対して、ビュー (形式) 用に設定します。</span><span class="sxs-lookup"><span data-stu-id="a5f62-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a5f62-106">構文</span><span class="sxs-lookup"><span data-stu-id="a5f62-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="a5f62-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="a5f62-107">Attributes and Elements</span></span>

<span data-ttu-id="a5f62-108">次のセクションでは、`ExpressionBinding` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5f62-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a5f62-109">属性</span><span class="sxs-lookup"><span data-stu-id="a5f62-109">Attributes</span></span>

<span data-ttu-id="a5f62-110">なし。</span><span class="sxs-lookup"><span data-stu-id="a5f62-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a5f62-111">子要素</span><span class="sxs-lookup"><span data-stu-id="a5f62-111">Child Elements</span></span>

|<span data-ttu-id="a5f62-112">要素</span><span class="sxs-lookup"><span data-stu-id="a5f62-112">Element</span></span>|<span data-ttu-id="a5f62-113">[説明]</span><span class="sxs-lookup"><span data-stu-id="a5f62-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="a5f62-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a5f62-114">Optional element.</span></span><br /><br /> <span data-ttu-id="a5f62-115">このコントロールによって使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="a5f62-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="a5f62-116">ビューのコントロール (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="a5f62-116">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="a5f62-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a5f62-117">Optional element.</span></span><br /><br /> <span data-ttu-id="a5f62-118">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5f62-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="a5f62-119">ビューのコントロール (Format) の式のバインドの列挙 Atecollection 要素</span><span class="sxs-lookup"><span data-stu-id="a5f62-119">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="a5f62-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a5f62-120">Optional element.</span></span><br /><br /> <span data-ttu-id="a5f62-121">コレクションの要素を表示することを指定します。</span><span class="sxs-lookup"><span data-stu-id="a5f62-121">Specifies that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="a5f62-122">ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="a5f62-122">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="a5f62-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a5f62-123">Optional element.</span></span><br /><br /> <span data-ttu-id="a5f62-124">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="a5f62-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="a5f62-125">ビューのコントロール (Format) の式のバインドの PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="a5f62-125">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="a5f62-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a5f62-126">Optional element.</span></span><br /><br /> <span data-ttu-id="a5f62-127">コントロールによって表示される値を持つ .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="a5f62-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="a5f62-128">ビューのコントロール (Format) の式のバインドの ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="a5f62-128">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="a5f62-129">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a5f62-129">Optional element.</span></span><br /><br /> <span data-ttu-id="a5f62-130">コントロールによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a5f62-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a5f62-131">親要素</span><span class="sxs-lookup"><span data-stu-id="a5f62-131">Parent Elements</span></span>

|<span data-ttu-id="a5f62-132">要素</span><span class="sxs-lookup"><span data-stu-id="a5f62-132">Element</span></span>|<span data-ttu-id="a5f62-133">[説明]</span><span class="sxs-lookup"><span data-stu-id="a5f62-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a5f62-134">ビュー用のコントロール用の Custommentry の CustomItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a5f62-134">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="a5f62-135">コントロールによって表示されるデータとその表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="a5f62-135">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a5f62-136">コメント</span><span class="sxs-lookup"><span data-stu-id="a5f62-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="a5f62-137">参照</span><span class="sxs-lookup"><span data-stu-id="a5f62-137">See Also</span></span>

[<span data-ttu-id="a5f62-138">ビュー用のコントロール用の Custommentry の CustomItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a5f62-138">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="a5f62-139">ビューのコントロール (Format) の式のバインドの CustomControlName 要素</span><span class="sxs-lookup"><span data-stu-id="a5f62-139">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="a5f62-140">ビューのコントロール (Format) の式のバインドの列挙 Atecollection 要素</span><span class="sxs-lookup"><span data-stu-id="a5f62-140">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="a5f62-141">ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="a5f62-141">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="a5f62-142">ビューのコントロール (Format) の式のバインドの PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="a5f62-142">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="a5f62-143">ビューのコントロール (Format) の式のバインドの ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="a5f62-143">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="a5f62-144">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="a5f62-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
