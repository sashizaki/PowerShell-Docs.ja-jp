---
title: PropertyName ItemSelectionCondition ListControl (形式) の要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5e707ae-3c84-4ceb-ba31-56b3ffde6d6c
caps.latest.revision: 7
ms.openlocfilehash: b15e26e18126f69eee7c3a857f9a461d4bdf5848
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064749"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="76ea7-102">ListControl の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="76ea7-102">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="76ea7-103">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="76ea7-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="76ea7-104">このプロパティが存在するかを評価すると`true`条件が満たされ、ビューを使用します。</span><span class="sxs-lookup"><span data-stu-id="76ea7-104">When this property is present or when it evaluates to `true`, the condition is met, and the view is used.</span></span> <span data-ttu-id="76ea7-105">この要素は、リスト ビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="76ea7-105">This element is used when defining a list view.</span></span>

<span data-ttu-id="76ea7-106">構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) ListControl 要素 (形式) ListEntries 要素 (形式) ListEntry 要素 ListControl (形式) ListItem の ListEntry の ListControl (形式) のリスト項目要素ListItem ItemSelectionCondition ListControl (形式) 用の ListControls PropertyName 要素に対して ListControl (形式) ItemSelectionCondition 要素の ListItems 要素</span><span class="sxs-lookup"><span data-stu-id="76ea7-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControls PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="76ea7-107">構文</span><span class="sxs-lookup"><span data-stu-id="76ea7-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="76ea7-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="76ea7-108">Attributes and Elements</span></span>

<span data-ttu-id="76ea7-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。</span><span class="sxs-lookup"><span data-stu-id="76ea7-109">The following sections describe attributes, child elements, and the parent elements of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="76ea7-110">属性</span><span class="sxs-lookup"><span data-stu-id="76ea7-110">Attributes</span></span>

<span data-ttu-id="76ea7-111">なし。</span><span class="sxs-lookup"><span data-stu-id="76ea7-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="76ea7-112">子要素</span><span class="sxs-lookup"><span data-stu-id="76ea7-112">Child Elements</span></span>

<span data-ttu-id="76ea7-113">なし。</span><span class="sxs-lookup"><span data-stu-id="76ea7-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="76ea7-114">親要素</span><span class="sxs-lookup"><span data-stu-id="76ea7-114">Parent Elements</span></span>

|<span data-ttu-id="76ea7-115">要素</span><span class="sxs-lookup"><span data-stu-id="76ea7-115">Element</span></span>|<span data-ttu-id="76ea7-116">説明</span><span class="sxs-lookup"><span data-stu-id="76ea7-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="76ea7-117">ItemSelectionCondition ListControl (形式) を ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="76ea7-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a><span data-ttu-id="76ea7-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="76ea7-118">Text Value</span></span>

<span data-ttu-id="76ea7-119">値が表示されるプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="76ea7-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="76ea7-120">コメント</span><span class="sxs-lookup"><span data-stu-id="76ea7-120">Remarks</span></span>

<span data-ttu-id="76ea7-121">指定できないかどうかは、この要素が使用される、 [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)要素の選択条件を定義するときにします。</span><span class="sxs-lookup"><span data-stu-id="76ea7-121">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="76ea7-122">参照</span><span class="sxs-lookup"><span data-stu-id="76ea7-122">See Also</span></span>

[<span data-ttu-id="76ea7-123">ItemSelectionCondition ListIControl (形式) 用のスクリプト ブロックの要素</span><span class="sxs-lookup"><span data-stu-id="76ea7-123">ScriptBlock Element for ItemSelectionCondition for ListIControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="76ea7-124">ItemSelectionCondition ListControl (形式) を ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="76ea7-124">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="76ea7-125">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="76ea7-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
