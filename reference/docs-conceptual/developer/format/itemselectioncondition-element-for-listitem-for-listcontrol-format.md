---
title: ListControl の ListItem の ItemSelectionCondition 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f5c388928668e03b96923130fb5849f637548f12
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783621"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="f8c70-102">ListControl の ListItem の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f8c70-102">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="f8c70-103">このリスト項目を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="f8c70-103">Defines the condition that must exist for this list item to be used.</span></span>

<span data-ttu-id="f8c70-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (形式) ListEntries for ListItems (format) ListEntry 要素の ListControl (format) ListEntry 要素の ListEntries for ListControl (format) の ListItem 要素の ListItems for ListControl (format) ItemSelectionCondition 要素 for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f8c70-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f8c70-105">構文</span><span class="sxs-lookup"><span data-stu-id="f8c70-105">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f8c70-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f8c70-106">Attributes and Elements</span></span>

<span data-ttu-id="f8c70-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `ItemSelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="f8c70-107">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f8c70-108">属性</span><span class="sxs-lookup"><span data-stu-id="f8c70-108">Attributes</span></span>

<span data-ttu-id="f8c70-109">なし。</span><span class="sxs-lookup"><span data-stu-id="f8c70-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f8c70-110">子要素</span><span class="sxs-lookup"><span data-stu-id="f8c70-110">Child Elements</span></span>

|<span data-ttu-id="f8c70-111">要素</span><span class="sxs-lookup"><span data-stu-id="f8c70-111">Element</span></span>|<span data-ttu-id="f8c70-112">説明</span><span class="sxs-lookup"><span data-stu-id="f8c70-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f8c70-113">ListControl の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f8c70-113">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="f8c70-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f8c70-114">Optional element.</span></span><br /><br /> <span data-ttu-id="f8c70-115">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="f8c70-115">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="f8c70-116">ListControl の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f8c70-116">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="f8c70-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="f8c70-117">Optional element.</span></span><br /><br /> <span data-ttu-id="f8c70-118">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="f8c70-118">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f8c70-119">親要素</span><span class="sxs-lookup"><span data-stu-id="f8c70-119">Parent Elements</span></span>

|<span data-ttu-id="f8c70-120">要素</span><span class="sxs-lookup"><span data-stu-id="f8c70-120">Element</span></span>|<span data-ttu-id="f8c70-121">説明</span><span class="sxs-lookup"><span data-stu-id="f8c70-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f8c70-122">ListControl の ListItems の ListItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f8c70-122">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="f8c70-123">リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="f8c70-123">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f8c70-124">解説</span><span class="sxs-lookup"><span data-stu-id="f8c70-124">Remarks</span></span>

<span data-ttu-id="f8c70-125">この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f8c70-125">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8c70-126">参照</span><span class="sxs-lookup"><span data-stu-id="f8c70-126">See Also</span></span>

[<span data-ttu-id="f8c70-127">ListControl の ListItems の ListItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f8c70-127">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="f8c70-128">ListControl の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f8c70-128">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="f8c70-129">ListControl の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f8c70-129">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="f8c70-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="f8c70-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
