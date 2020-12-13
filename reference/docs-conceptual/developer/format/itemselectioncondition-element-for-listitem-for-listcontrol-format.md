---
ms.date: 09/13/2016
ms.topic: reference
title: ListControl の ListItem の ItemSelectionCondition 要素 (書式)
description: ListControl の ListItem の ItemSelectionCondition 要素 (書式)
ms.openlocfilehash: 13d925da10c2386123983d52b109c03a0c3c63ab
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667812"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="b07a9-103">ListControl の ListItem の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b07a9-103">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="b07a9-104">このリスト項目を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="b07a9-104">Defines the condition that must exist for this list item to be used.</span></span>

<span data-ttu-id="b07a9-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (形式) ListEntries for ListItems (format) ListEntry 要素の ListControl (format) ListEntry 要素の ListEntries for ListControl (format) の ListItem 要素の ListItems for ListControl (format) ItemSelectionCondition 要素 for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b07a9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b07a9-106">構文</span><span class="sxs-lookup"><span data-stu-id="b07a9-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b07a9-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b07a9-107">Attributes and Elements</span></span>

<span data-ttu-id="b07a9-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ItemSelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="b07a9-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b07a9-109">属性</span><span class="sxs-lookup"><span data-stu-id="b07a9-109">Attributes</span></span>

<span data-ttu-id="b07a9-110">なし。</span><span class="sxs-lookup"><span data-stu-id="b07a9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b07a9-111">子要素</span><span class="sxs-lookup"><span data-stu-id="b07a9-111">Child Elements</span></span>

|<span data-ttu-id="b07a9-112">要素</span><span class="sxs-lookup"><span data-stu-id="b07a9-112">Element</span></span>|<span data-ttu-id="b07a9-113">説明</span><span class="sxs-lookup"><span data-stu-id="b07a9-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b07a9-114">ListControl の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b07a9-114">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="b07a9-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="b07a9-115">Optional element.</span></span><br /><br /> <span data-ttu-id="b07a9-116">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="b07a9-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="b07a9-117">ListControl の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b07a9-117">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="b07a9-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="b07a9-118">Optional element.</span></span><br /><br /> <span data-ttu-id="b07a9-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="b07a9-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b07a9-120">親要素</span><span class="sxs-lookup"><span data-stu-id="b07a9-120">Parent Elements</span></span>

|<span data-ttu-id="b07a9-121">要素</span><span class="sxs-lookup"><span data-stu-id="b07a9-121">Element</span></span>|<span data-ttu-id="b07a9-122">説明</span><span class="sxs-lookup"><span data-stu-id="b07a9-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b07a9-123">ListControl の ListItems の ListItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b07a9-123">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="b07a9-124">リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="b07a9-124">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b07a9-125">解説</span><span class="sxs-lookup"><span data-stu-id="b07a9-125">Remarks</span></span>

<span data-ttu-id="b07a9-126">この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b07a9-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="b07a9-127">参照</span><span class="sxs-lookup"><span data-stu-id="b07a9-127">See Also</span></span>

[<span data-ttu-id="b07a9-128">ListControl の ListItems の ListItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b07a9-128">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="b07a9-129">ListControl の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b07a9-129">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="b07a9-130">ListControl の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b07a9-130">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="b07a9-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="b07a9-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
