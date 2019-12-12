---
title: ListControl の ListItem の ItemSelectionCondition 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2668aea-37e9-4753-a4e9-7980ae5ec2eb
caps.latest.revision: 10
ms.openlocfilehash: 6bc0ccbcc5bd62429f63ed220da66dc66f44f7ca
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365191"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="28045-102">ListControl の ListItem の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="28045-102">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="28045-103">このリスト項目を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="28045-103">Defines the condition that must exist for this list item to be used.</span></span>

<span data-ttu-id="28045-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (Format) ListControl (format) ListEntry 要素の listentries の ListControl (Format) ListItems 要素の listentries 要素for ListControl (Format) ListItem 要素 for ListItems for ListControl (format) ItemSelectionCondition Element for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="28045-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="28045-105">構文</span><span class="sxs-lookup"><span data-stu-id="28045-105">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="28045-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="28045-106">Attributes and Elements</span></span>

<span data-ttu-id="28045-107">次のセクションでは、`ItemSelectionCondition` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="28045-107">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="28045-108">属性</span><span class="sxs-lookup"><span data-stu-id="28045-108">Attributes</span></span>

<span data-ttu-id="28045-109">なし。</span><span class="sxs-lookup"><span data-stu-id="28045-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="28045-110">子要素</span><span class="sxs-lookup"><span data-stu-id="28045-110">Child Elements</span></span>

|<span data-ttu-id="28045-111">要素</span><span class="sxs-lookup"><span data-stu-id="28045-111">Element</span></span>|<span data-ttu-id="28045-112">[説明]</span><span class="sxs-lookup"><span data-stu-id="28045-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="28045-113">ListControl の ItemSelectionCondition の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="28045-113">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="28045-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="28045-114">Optional element.</span></span><br /><br /> <span data-ttu-id="28045-115">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="28045-115">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="28045-116">ListControl の ItemSelectionCondition の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="28045-116">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="28045-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="28045-117">Optional element.</span></span><br /><br /> <span data-ttu-id="28045-118">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="28045-118">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="28045-119">親要素</span><span class="sxs-lookup"><span data-stu-id="28045-119">Parent Elements</span></span>

|<span data-ttu-id="28045-120">要素</span><span class="sxs-lookup"><span data-stu-id="28045-120">Element</span></span>|<span data-ttu-id="28045-121">[説明]</span><span class="sxs-lookup"><span data-stu-id="28045-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="28045-122">ListControl の ListItems の ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="28045-122">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="28045-123">リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="28045-123">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="28045-124">コメント</span><span class="sxs-lookup"><span data-stu-id="28045-124">Remarks</span></span>

<span data-ttu-id="28045-125">この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="28045-125">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="28045-126">参照</span><span class="sxs-lookup"><span data-stu-id="28045-126">See Also</span></span>

[<span data-ttu-id="28045-127">ListControl の ListItems の ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="28045-127">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="28045-128">ListControl の ItemSelectionCondition の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="28045-128">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="28045-129">ListControl の ItemSelectionCondition の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="28045-129">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="28045-130">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="28045-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
