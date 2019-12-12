---
title: ListControl の ItemSelectionCondition の PropertyName 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5e707ae-3c84-4ceb-ba31-56b3ffde6d6c
caps.latest.revision: 7
ms.openlocfilehash: b15e26e18126f69eee7c3a857f9a461d4bdf5848
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362391"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="0a1ba-102">ListControl の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0a1ba-102">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="0a1ba-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="0a1ba-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="0a1ba-104">このプロパティが存在する場合、または `true`に評価された場合、条件が満たされ、ビューが使用されます。</span><span class="sxs-lookup"><span data-stu-id="0a1ba-104">When this property is present or when it evaluates to `true`, the condition is met, and the view is used.</span></span> <span data-ttu-id="0a1ba-105">この要素は、リストビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0a1ba-105">This element is used when defining a list view.</span></span>

<span data-ttu-id="0a1ba-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries Element (format) ListEntry の ListControl (Format) ListItems 要素の (format) ListItem の要素ListControl (Format) の ItemSelectionCondition の ListControls PropertyName 要素の ListItems for ListControl (Format) ItemSelectionCondition 要素の要素</span><span class="sxs-lookup"><span data-stu-id="0a1ba-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControls PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0a1ba-107">構文</span><span class="sxs-lookup"><span data-stu-id="0a1ba-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0a1ba-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="0a1ba-108">Attributes and Elements</span></span>

<span data-ttu-id="0a1ba-109">次のセクションでは、`PropertyName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a1ba-109">The following sections describe attributes, child elements, and the parent elements of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0a1ba-110">属性</span><span class="sxs-lookup"><span data-stu-id="0a1ba-110">Attributes</span></span>

<span data-ttu-id="0a1ba-111">なし。</span><span class="sxs-lookup"><span data-stu-id="0a1ba-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0a1ba-112">子要素</span><span class="sxs-lookup"><span data-stu-id="0a1ba-112">Child Elements</span></span>

<span data-ttu-id="0a1ba-113">なし。</span><span class="sxs-lookup"><span data-stu-id="0a1ba-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0a1ba-114">親要素</span><span class="sxs-lookup"><span data-stu-id="0a1ba-114">Parent Elements</span></span>

|<span data-ttu-id="0a1ba-115">要素</span><span class="sxs-lookup"><span data-stu-id="0a1ba-115">Element</span></span>|<span data-ttu-id="0a1ba-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="0a1ba-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0a1ba-117">ListControl の ListItem の ItemSelectionCondition 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="0a1ba-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a><span data-ttu-id="0a1ba-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="0a1ba-118">Text Value</span></span>

<span data-ttu-id="0a1ba-119">値が表示されるプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0a1ba-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="0a1ba-120">コメント</span><span class="sxs-lookup"><span data-stu-id="0a1ba-120">Remarks</span></span>

<span data-ttu-id="0a1ba-121">この要素が使用されている場合、選択条件を定義するときに[ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="0a1ba-121">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a1ba-122">参照</span><span class="sxs-lookup"><span data-stu-id="0a1ba-122">See Also</span></span>

[<span data-ttu-id="0a1ba-123">ListIControl の ItemSelectionCondition の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="0a1ba-123">ScriptBlock Element for ItemSelectionCondition for ListIControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="0a1ba-124">ListControl の ListItem の ItemSelectionCondition 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="0a1ba-124">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="0a1ba-125">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="0a1ba-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
