---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration の Controls の ItemSeclectionCondition の PropertyName 要素 (書式)
description: Configuration の Controls の ItemSeclectionCondition の PropertyName 要素 (書式)
ms.openlocfilehash: 860683eb54b2a3579767640c1d3f0937897b8f8e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655127"
---
# <a name="propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="12685-103">Configuration の Controls の ItemSeclectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="12685-103">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="12685-104">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="12685-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="12685-105">このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、コントロールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="12685-105">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="12685-106">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="12685-106">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="12685-107">Configuration 要素 (Format) コントロールの構成 (形式) の CustomControl 要素の構成 (書式設定) の CustomControl の構成 (形式) の CustomEntries 要素を構成するためのコントロールの構成 (形式) の CustomEntries 要素 CustomControl の構成 (形式) のコントロール要素) に対する CustomEntry コントロールの構成式のバインド要素の構成のバインド要素の構成のバインド要素の構成のためのコントロールの構成 (format) 要素のバインド要素の構成用コントロールの ItemSeclectionCondition の PropertyName 要素の構成 (形式)</span><span class="sxs-lookup"><span data-stu-id="12685-107">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format) PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="12685-108">構文</span><span class="sxs-lookup"><span data-stu-id="12685-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="12685-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="12685-109">Attributes and Elements</span></span>

<span data-ttu-id="12685-110">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="12685-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="12685-111">属性</span><span class="sxs-lookup"><span data-stu-id="12685-111">Attributes</span></span>

<span data-ttu-id="12685-112">なし。</span><span class="sxs-lookup"><span data-stu-id="12685-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="12685-113">子要素</span><span class="sxs-lookup"><span data-stu-id="12685-113">Child Elements</span></span>

<span data-ttu-id="12685-114">なし。</span><span class="sxs-lookup"><span data-stu-id="12685-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="12685-115">親要素</span><span class="sxs-lookup"><span data-stu-id="12685-115">Parent Elements</span></span>

|<span data-ttu-id="12685-116">要素</span><span class="sxs-lookup"><span data-stu-id="12685-116">Element</span></span>|<span data-ttu-id="12685-117">説明</span><span class="sxs-lookup"><span data-stu-id="12685-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="12685-118">Configuration の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="12685-118">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="12685-119">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="12685-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="12685-120">テキスト値</span><span class="sxs-lookup"><span data-stu-id="12685-120">Text Value</span></span>

<span data-ttu-id="12685-121">条件をトリガーする .NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="12685-121">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="12685-122">解説</span><span class="sxs-lookup"><span data-stu-id="12685-122">Remarks</span></span>

<span data-ttu-id="12685-123">この要素が使用されている場合、選択条件を定義するときに [ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) 要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="12685-123">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="12685-124">参照</span><span class="sxs-lookup"><span data-stu-id="12685-124">See Also</span></span>

[<span data-ttu-id="12685-125">Configuration の Controls の ItemSeclectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="12685-125">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="12685-126">Configuration の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="12685-126">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[<span data-ttu-id="12685-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="12685-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
