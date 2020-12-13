---
ms.date: 09/13/2016
ms.topic: reference
title: ListControl の ItemSelectionCondition の PropertyName 要素 (書式)
description: ListControl の ItemSelectionCondition の PropertyName 要素 (書式)
ms.openlocfilehash: c515efe70afdb1c1186c0a07fe1f52dc49ad57b9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665993"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="6cf66-103">ListControl の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6cf66-103">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="6cf66-104">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="6cf66-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="6cf66-105">このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、ビューが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6cf66-105">When this property is present or when it evaluates to `true`, the condition is met, and the view is used.</span></span> <span data-ttu-id="6cf66-106">この要素は、リストビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6cf66-106">This element is used when defining a list view.</span></span>

<span data-ttu-id="6cf66-107">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (format) ListControl Element (format) ListEntries Element (format) ListEntry 要素 for ListEntry (format) ListControl (format) ListItems 要素の ListControl for ListItems (format) 項目の (format) 項目の listitem 要素の ListItem 要素の Listentries の (形式)</span><span class="sxs-lookup"><span data-stu-id="6cf66-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControls PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6cf66-108">構文</span><span class="sxs-lookup"><span data-stu-id="6cf66-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6cf66-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6cf66-109">Attributes and Elements</span></span>

<span data-ttu-id="6cf66-110">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="6cf66-110">The following sections describe attributes, child elements, and the parent elements of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6cf66-111">属性</span><span class="sxs-lookup"><span data-stu-id="6cf66-111">Attributes</span></span>

<span data-ttu-id="6cf66-112">なし。</span><span class="sxs-lookup"><span data-stu-id="6cf66-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6cf66-113">子要素</span><span class="sxs-lookup"><span data-stu-id="6cf66-113">Child Elements</span></span>

<span data-ttu-id="6cf66-114">なし。</span><span class="sxs-lookup"><span data-stu-id="6cf66-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6cf66-115">親要素</span><span class="sxs-lookup"><span data-stu-id="6cf66-115">Parent Elements</span></span>

|<span data-ttu-id="6cf66-116">要素</span><span class="sxs-lookup"><span data-stu-id="6cf66-116">Element</span></span>|<span data-ttu-id="6cf66-117">説明</span><span class="sxs-lookup"><span data-stu-id="6cf66-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6cf66-118">ListControl の ListItem の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6cf66-118">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a><span data-ttu-id="6cf66-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="6cf66-119">Text Value</span></span>

<span data-ttu-id="6cf66-120">値が表示されるプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6cf66-120">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="6cf66-121">解説</span><span class="sxs-lookup"><span data-stu-id="6cf66-121">Remarks</span></span>

<span data-ttu-id="6cf66-122">この要素が使用されている場合、選択条件を定義するときに [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) 要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="6cf66-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="6cf66-123">参照</span><span class="sxs-lookup"><span data-stu-id="6cf66-123">See Also</span></span>

[<span data-ttu-id="6cf66-124">ListIControl の ItemSelectionCondition の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="6cf66-124">ScriptBlock Element for ItemSelectionCondition for ListIControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="6cf66-125">ListControl の ListItem の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6cf66-125">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="6cf66-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="6cf66-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
