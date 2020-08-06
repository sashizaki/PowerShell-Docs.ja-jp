---
title: GroupBy (Format) の式のバインドの ItemSelectionCondition 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a9b74f1882efc578f7d9ab27b8cd2f8a52833ab8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773438"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="529af-102">GroupBy の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="529af-102">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="529af-103">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="529af-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="529af-104">コントロール項目に指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="529af-104">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="529af-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="529af-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="529af-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素を groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素 CustomControl for GroupBy (format) Customentries 要素の CustomEntry for groupby (format) 式のバインド要素で groupby (format) ItemSelectionCondition 要素に対して groupby (形式) の式のバインドのバインド要素</span><span class="sxs-lookup"><span data-stu-id="529af-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="529af-107">構文</span><span class="sxs-lookup"><span data-stu-id="529af-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="529af-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="529af-108">Attributes and Elements</span></span>

<span data-ttu-id="529af-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ItemSelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="529af-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="529af-110">属性</span><span class="sxs-lookup"><span data-stu-id="529af-110">Attributes</span></span>

<span data-ttu-id="529af-111">なし。</span><span class="sxs-lookup"><span data-stu-id="529af-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="529af-112">子要素</span><span class="sxs-lookup"><span data-stu-id="529af-112">Child Elements</span></span>

|<span data-ttu-id="529af-113">要素</span><span class="sxs-lookup"><span data-stu-id="529af-113">Element</span></span>|<span data-ttu-id="529af-114">説明</span><span class="sxs-lookup"><span data-stu-id="529af-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="529af-115">GroupBy の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="529af-115">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="529af-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="529af-116">Optional element.</span></span><br /><br /> <span data-ttu-id="529af-117">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="529af-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="529af-118">GroupBy の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="529af-118">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="529af-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="529af-119">Optional element.</span></span><br /><br /> <span data-ttu-id="529af-120">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="529af-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="529af-121">親要素</span><span class="sxs-lookup"><span data-stu-id="529af-121">Parent Elements</span></span>

|<span data-ttu-id="529af-122">要素</span><span class="sxs-lookup"><span data-stu-id="529af-122">Element</span></span>|<span data-ttu-id="529af-123">説明</span><span class="sxs-lookup"><span data-stu-id="529af-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="529af-124">GroupBy の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="529af-124">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="529af-125">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="529af-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="529af-126">解説</span><span class="sxs-lookup"><span data-stu-id="529af-126">Remarks</span></span>

<span data-ttu-id="529af-127">この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="529af-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="529af-128">参照</span><span class="sxs-lookup"><span data-stu-id="529af-128">See Also</span></span>

[<span data-ttu-id="529af-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="529af-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="529af-130">GroupBy の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="529af-130">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)
