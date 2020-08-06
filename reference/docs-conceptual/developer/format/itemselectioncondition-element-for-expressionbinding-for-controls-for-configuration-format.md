---
title: 構成用のコントロールの式のバインドの ItemSelectionCondition 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 3bfd3efe916b4d88c024de8f959482cab515f777
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781224"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="9a40f-102">Configuration の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9a40f-102">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="9a40f-103">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="9a40f-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="9a40f-104">この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="9a40f-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="9a40f-105">Configuration 要素 (Format) コントロールの構成 (format) コントロールの要素の構成 (format) の CustomControl 要素の構成のためのコントロールの要素の構成 (形式) CustomControl の構成 (書式) の CustomEntries 要素 CustomControl の CustomEntry 要素コントロールのために、CustomEntry 用のカスタム Customentries 要素を構成するためのコントロールに対して、構成のためのコントロールのための構成 (Format) ItemSelectionCondition 要素の構成 (形式) のコントロールのための式のバインド要素のバインド要素</span><span class="sxs-lookup"><span data-stu-id="9a40f-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9a40f-106">構文</span><span class="sxs-lookup"><span data-stu-id="9a40f-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9a40f-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9a40f-107">Attributes and Elements</span></span>

<span data-ttu-id="9a40f-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ItemSelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="9a40f-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9a40f-109">属性</span><span class="sxs-lookup"><span data-stu-id="9a40f-109">Attributes</span></span>

<span data-ttu-id="9a40f-110">なし。</span><span class="sxs-lookup"><span data-stu-id="9a40f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9a40f-111">子要素</span><span class="sxs-lookup"><span data-stu-id="9a40f-111">Child Elements</span></span>

|<span data-ttu-id="9a40f-112">要素</span><span class="sxs-lookup"><span data-stu-id="9a40f-112">Element</span></span>|<span data-ttu-id="9a40f-113">説明</span><span class="sxs-lookup"><span data-stu-id="9a40f-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9a40f-114">構成用のコントロールの ItemSelectionCondition の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="9a40f-114">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="9a40f-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="9a40f-115">Optional element.</span></span><br /><br /> <span data-ttu-id="9a40f-116">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="9a40f-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="9a40f-117">構成用のコントロールの ItemSelectionCondition の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="9a40f-117">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="9a40f-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="9a40f-118">Optional element.</span></span><br /><br /> <span data-ttu-id="9a40f-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="9a40f-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9a40f-120">親要素</span><span class="sxs-lookup"><span data-stu-id="9a40f-120">Parent Elements</span></span>

|<span data-ttu-id="9a40f-121">要素</span><span class="sxs-lookup"><span data-stu-id="9a40f-121">Element</span></span>|<span data-ttu-id="9a40f-122">説明</span><span class="sxs-lookup"><span data-stu-id="9a40f-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9a40f-123">Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9a40f-123">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="9a40f-124">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="9a40f-124">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9a40f-125">解説</span><span class="sxs-lookup"><span data-stu-id="9a40f-125">Remarks</span></span>

<span data-ttu-id="9a40f-126">この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="9a40f-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a40f-127">参照</span><span class="sxs-lookup"><span data-stu-id="9a40f-127">See Also</span></span>

[<span data-ttu-id="9a40f-128">構成用のコントロールの ItemSelectionCondition の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="9a40f-128">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="9a40f-129">構成用のコントロールの ItemSelectionCondition の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="9a40f-129">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="9a40f-130">Configuration の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9a40f-130">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="9a40f-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="9a40f-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
