---
title: CustomControl (Format) の式のバインドの ItemSelectionCondition 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6a5c66a63c02980b16c2d2d9dd689410c8aec51c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781190"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a><span data-ttu-id="636b9-102">CustomControl の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="636b9-102">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>

<span data-ttu-id="636b9-103">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="636b9-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="636b9-104">コントロール項目に指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="636b9-104">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="636b9-105">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="636b9-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="636b9-106">Configuration 要素 (Format) ViewDefinitions 要素 (形式) view Element (Format) CustomControl 要素 (Format) ビューの CustomEntries の CustomEntry 要素の CustomControl for view (format) の CustomEntries 要素を表示します。) CustomControl for View (Format) の式のバインドのための CustomControl for view (format) ItemSelectionCondition 要素の customentries 要素に対する CustomEntry for view (format) 式のバインド要素のための Customentries 要素</span><span class="sxs-lookup"><span data-stu-id="636b9-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="636b9-107">構文</span><span class="sxs-lookup"><span data-stu-id="636b9-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="636b9-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="636b9-108">Attributes and Elements</span></span>

<span data-ttu-id="636b9-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ItemSelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="636b9-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="636b9-110">属性</span><span class="sxs-lookup"><span data-stu-id="636b9-110">Attributes</span></span>

<span data-ttu-id="636b9-111">なし。</span><span class="sxs-lookup"><span data-stu-id="636b9-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="636b9-112">子要素</span><span class="sxs-lookup"><span data-stu-id="636b9-112">Child Elements</span></span>

|<span data-ttu-id="636b9-113">要素</span><span class="sxs-lookup"><span data-stu-id="636b9-113">Element</span></span>|<span data-ttu-id="636b9-114">説明</span><span class="sxs-lookup"><span data-stu-id="636b9-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="636b9-115">ビューの CustomControl の ItemSelectionCondition の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="636b9-115">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="636b9-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="636b9-116">Optional element.</span></span><br /><br /> <span data-ttu-id="636b9-117">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="636b9-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="636b9-118">View の CustomControl の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="636b9-118">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="636b9-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="636b9-119">Optional element.</span></span><br /><br /> <span data-ttu-id="636b9-120">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="636b9-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="636b9-121">親要素</span><span class="sxs-lookup"><span data-stu-id="636b9-121">Parent Elements</span></span>

|<span data-ttu-id="636b9-122">要素</span><span class="sxs-lookup"><span data-stu-id="636b9-122">Element</span></span>|<span data-ttu-id="636b9-123">説明</span><span class="sxs-lookup"><span data-stu-id="636b9-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="636b9-124">View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="636b9-124">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="636b9-125">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="636b9-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="636b9-126">解説</span><span class="sxs-lookup"><span data-stu-id="636b9-126">Remarks</span></span>

<span data-ttu-id="636b9-127">この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="636b9-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="636b9-128">参照</span><span class="sxs-lookup"><span data-stu-id="636b9-128">See Also</span></span>

[<span data-ttu-id="636b9-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="636b9-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="636b9-130">View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="636b9-130">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
