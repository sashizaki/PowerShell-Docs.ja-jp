---
title: ListControl の ItemSelectionCondition の PropertyName 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 8bdbb05326f7ff5ccffa46215631a5c954080dc1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780867"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="5152d-102">ListControl の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5152d-102">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="5152d-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="5152d-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="5152d-104">このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、ビューが使用されます。</span><span class="sxs-lookup"><span data-stu-id="5152d-104">When this property is present or when it evaluates to `true`, the condition is met, and the view is used.</span></span> <span data-ttu-id="5152d-105">この要素は、リストビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5152d-105">This element is used when defining a list view.</span></span>

<span data-ttu-id="5152d-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (format) ListControl Element (format) ListEntries Element (format) ListEntry 要素 for ListEntry (format) ListControl (format) ListItems 要素の ListControl for ListItems (format) 項目の (format) 項目の listitem 要素の ListItem 要素の Listentries の (形式)</span><span class="sxs-lookup"><span data-stu-id="5152d-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControls PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5152d-107">構文</span><span class="sxs-lookup"><span data-stu-id="5152d-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5152d-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5152d-108">Attributes and Elements</span></span>

<span data-ttu-id="5152d-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="5152d-109">The following sections describe attributes, child elements, and the parent elements of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5152d-110">属性</span><span class="sxs-lookup"><span data-stu-id="5152d-110">Attributes</span></span>

<span data-ttu-id="5152d-111">なし。</span><span class="sxs-lookup"><span data-stu-id="5152d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5152d-112">子要素</span><span class="sxs-lookup"><span data-stu-id="5152d-112">Child Elements</span></span>

<span data-ttu-id="5152d-113">なし。</span><span class="sxs-lookup"><span data-stu-id="5152d-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5152d-114">親要素</span><span class="sxs-lookup"><span data-stu-id="5152d-114">Parent Elements</span></span>

|<span data-ttu-id="5152d-115">要素</span><span class="sxs-lookup"><span data-stu-id="5152d-115">Element</span></span>|<span data-ttu-id="5152d-116">説明</span><span class="sxs-lookup"><span data-stu-id="5152d-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5152d-117">ListControl の ListItem の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5152d-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a><span data-ttu-id="5152d-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="5152d-118">Text Value</span></span>

<span data-ttu-id="5152d-119">値が表示されるプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5152d-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="5152d-120">解説</span><span class="sxs-lookup"><span data-stu-id="5152d-120">Remarks</span></span>

<span data-ttu-id="5152d-121">この要素が使用されている場合、選択条件を定義するときに[ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="5152d-121">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="5152d-122">参照</span><span class="sxs-lookup"><span data-stu-id="5152d-122">See Also</span></span>

[<span data-ttu-id="5152d-123">ListIControl の ItemSelectionCondition の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="5152d-123">ScriptBlock Element for ItemSelectionCondition for ListIControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="5152d-124">ListControl の ListItem の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5152d-124">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="5152d-125">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="5152d-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
