---
title: ItemSelectionCondition ListControl (形式) を ListItem 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2668aea-37e9-4753-a4e9-7980ae5ec2eb
caps.latest.revision: 10
ms.openlocfilehash: 6bc0ccbcc5bd62429f63ed220da66dc66f44f7ca
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861868"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="fff60-102">ListControl の ListItem の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="fff60-102">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="fff60-103">使用するには、このリスト項目の存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="fff60-103">Defines the condition that must exist for this list item to be used.</span></span>

<span data-ttu-id="fff60-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素の要素に ListControl (形式) ListEntry ListEntries ListEntry の ListControl (形式) のリスト項目要素のListControl (形式) を ListItem の ListControl (形式) ItemSelectionCondition 要素の ListItems の ListItem 要素を ListControl (形式)</span><span class="sxs-lookup"><span data-stu-id="fff60-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fff60-105">構文</span><span class="sxs-lookup"><span data-stu-id="fff60-105">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fff60-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="fff60-106">Attributes and Elements</span></span>

<span data-ttu-id="fff60-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`ItemSelectionCondition`要素。</span><span class="sxs-lookup"><span data-stu-id="fff60-107">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fff60-108">属性</span><span class="sxs-lookup"><span data-stu-id="fff60-108">Attributes</span></span>

<span data-ttu-id="fff60-109">なし。</span><span class="sxs-lookup"><span data-stu-id="fff60-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fff60-110">子要素</span><span class="sxs-lookup"><span data-stu-id="fff60-110">Child Elements</span></span>

|<span data-ttu-id="fff60-111">要素</span><span class="sxs-lookup"><span data-stu-id="fff60-111">Element</span></span>|<span data-ttu-id="fff60-112">説明</span><span class="sxs-lookup"><span data-stu-id="fff60-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fff60-113">PropertyName ItemSelectionCondition ListControl (形式) の要素</span><span class="sxs-lookup"><span data-stu-id="fff60-113">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="fff60-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="fff60-114">Optional element.</span></span><br /><br /> <span data-ttu-id="fff60-115">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="fff60-115">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="fff60-116">ItemSelectionCondition ListControl (形式) 用のスクリプト ブロックの要素</span><span class="sxs-lookup"><span data-stu-id="fff60-116">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="fff60-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="fff60-117">Optional element.</span></span><br /><br /> <span data-ttu-id="fff60-118">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="fff60-118">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="fff60-119">親要素</span><span class="sxs-lookup"><span data-stu-id="fff60-119">Parent Elements</span></span>

|<span data-ttu-id="fff60-120">要素</span><span class="sxs-lookup"><span data-stu-id="fff60-120">Element</span></span>|<span data-ttu-id="fff60-121">説明</span><span class="sxs-lookup"><span data-stu-id="fff60-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fff60-122">ListControl (形式) のリスト項目の ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="fff60-122">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="fff60-123">プロパティまたはリスト ビューの行の値が表示されているスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="fff60-123">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fff60-124">コメント</span><span class="sxs-lookup"><span data-stu-id="fff60-124">Remarks</span></span>

<span data-ttu-id="fff60-125">1 つのプロパティ名またはこの状態のスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="fff60-125">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="fff60-126">参照</span><span class="sxs-lookup"><span data-stu-id="fff60-126">See Also</span></span>

[<span data-ttu-id="fff60-127">ListControl (形式) のリスト項目の ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="fff60-127">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="fff60-128">PropertyName ItemSelectionCondition ListControl (形式) の要素</span><span class="sxs-lookup"><span data-stu-id="fff60-128">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="fff60-129">ItemSelectionCondition ListControl (形式) 用のスクリプト ブロックの要素</span><span class="sxs-lookup"><span data-stu-id="fff60-129">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="fff60-130">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="fff60-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
