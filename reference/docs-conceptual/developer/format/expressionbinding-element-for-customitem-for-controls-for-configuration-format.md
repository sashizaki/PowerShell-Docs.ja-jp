---
title: 構成用のコントロール用の CustomItem の式のバインド要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1ad83fa9d915822eaefb490658f8a219defdddf2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773914"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="bd118-102">Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bd118-102">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="bd118-103">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="bd118-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="bd118-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd118-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="bd118-105">Configuration 要素 (Format) コントロールの構成 (format) コントロールの要素の構成 (format) の CustomControl 要素の構成のためのコントロール要素の構成 (書式) の CustomControl の構成 (形式) のカスタム Customentries 要素の構成のためのコントロールの構成式の構成 (書式設定) のカスタム項目のバインド要素の構成 (形式)</span><span class="sxs-lookup"><span data-stu-id="bd118-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bd118-106">構文</span><span class="sxs-lookup"><span data-stu-id="bd118-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="bd118-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bd118-107">Attributes and Elements</span></span>

<span data-ttu-id="bd118-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ExpressionBinding` ます。</span><span class="sxs-lookup"><span data-stu-id="bd118-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bd118-109">属性</span><span class="sxs-lookup"><span data-stu-id="bd118-109">Attributes</span></span>

<span data-ttu-id="bd118-110">なし。</span><span class="sxs-lookup"><span data-stu-id="bd118-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bd118-111">子要素</span><span class="sxs-lookup"><span data-stu-id="bd118-111">Child Elements</span></span>

|<span data-ttu-id="bd118-112">要素</span><span class="sxs-lookup"><span data-stu-id="bd118-112">Element</span></span>|<span data-ttu-id="bd118-113">説明</span><span class="sxs-lookup"><span data-stu-id="bd118-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="bd118-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="bd118-114">Optional element.</span></span><br /><br /> <span data-ttu-id="bd118-115">このコントロールによって使用されるコントロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="bd118-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="bd118-116">Configuration の Controls の ExpressionBinding の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bd118-116">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="bd118-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="bd118-117">Optional element.</span></span><br /><br /> <span data-ttu-id="bd118-118">コモンコントロールまたはビューコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd118-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="bd118-119">Configuration の Controls の ExpressionBinding の EnumerateCollection 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bd118-119">EnumerateCollection Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="bd118-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="bd118-120">Optional element.</span></span><br /><br /> <span data-ttu-id="bd118-121">コレクションの要素がコントロールによって表示されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="bd118-121">Specified that the elements of collections are displayed by the control.</span></span>|
|[<span data-ttu-id="bd118-122">Configuration の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bd118-122">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="bd118-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="bd118-123">Optional element.</span></span><br /><br /> <span data-ttu-id="bd118-124">このコモンコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="bd118-124">Defines the condition that must exist for this common control to be used.</span></span>|
|[<span data-ttu-id="bd118-125">Configuration の Controls の ExpressionBinding の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bd118-125">PropertyName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="bd118-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="bd118-126">Optional element.</span></span><br /><br /> <span data-ttu-id="bd118-127">コモンコントロールによって表示される値を持つ .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="bd118-127">Specifies the .NET property whose value is displayed by the common control.</span></span>|
|[<span data-ttu-id="bd118-128">Configuration の Controls の ExpressionBinding の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bd118-128">ScriptBlock Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="bd118-129">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="bd118-129">Optional element.</span></span><br /><br /> <span data-ttu-id="bd118-130">共通コントロールによって値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="bd118-130">Specifies the script whose value is displayed by the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bd118-131">親要素</span><span class="sxs-lookup"><span data-stu-id="bd118-131">Parent Elements</span></span>

|<span data-ttu-id="bd118-132">要素</span><span class="sxs-lookup"><span data-stu-id="bd118-132">Element</span></span>|<span data-ttu-id="bd118-133">説明</span><span class="sxs-lookup"><span data-stu-id="bd118-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bd118-134">構成のための CustomEntry コントロールの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="bd118-134">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="bd118-135">カスタムコントロールビューとその表示方法によって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="bd118-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bd118-136">解説</span><span class="sxs-lookup"><span data-stu-id="bd118-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="bd118-137">参照</span><span class="sxs-lookup"><span data-stu-id="bd118-137">See Also</span></span>

[<span data-ttu-id="bd118-138">構成のための CustomEntry コントロールの CustomItem 要素</span><span class="sxs-lookup"><span data-stu-id="bd118-138">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="bd118-139">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="bd118-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
