---
ms.date: 09/13/2016
ms.topic: reference
title: ListControl の ItemSelectionCondition の ScriptBlock 要素 (書式)
description: ListControl の ItemSelectionCondition の ScriptBlock 要素 (書式)
ms.openlocfilehash: 1e518f898e0e1e62ca64f9897b1323cc6dd89ae9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665062"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="8d884-103">ListControl の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8d884-103">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="8d884-104">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="8d884-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="8d884-105">このスクリプトがに評価されると、 `true` 条件が満たされ、リスト項目が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d884-105">When this script is evaluated to `true`, the condition is met, and the list item is used.</span></span> <span data-ttu-id="8d884-106">この要素は、リストビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d884-106">This element is used when defining a list view.</span></span>

<span data-ttu-id="8d884-107">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (Format) ListControl (format) ListEntry 要素の listentries for ListControl (Format) ListItems 要素の ListEntries 要素 ListEntry for ListControl (Format) の ListItem 要素 for ListItems for List コントロール (format) ItemSelectionCondition の ItemSelectionCondition for ListControl (Format) ScriptBlock 要素 for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8d884-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for List Control (Format) ItemSelectionCondition Element for ListItem for ListControl (Format) ScriptBlock Element for ItemSelectionCondition for ListControl  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8d884-108">構文</span><span class="sxs-lookup"><span data-stu-id="8d884-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8d884-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8d884-109">Attributes and Elements</span></span>

<span data-ttu-id="8d884-110">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="8d884-110">The following sections describe attributes, child elements, and the parent elements of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8d884-111">属性</span><span class="sxs-lookup"><span data-stu-id="8d884-111">Attributes</span></span>

<span data-ttu-id="8d884-112">なし。</span><span class="sxs-lookup"><span data-stu-id="8d884-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8d884-113">子要素</span><span class="sxs-lookup"><span data-stu-id="8d884-113">Child Elements</span></span>

<span data-ttu-id="8d884-114">なし。</span><span class="sxs-lookup"><span data-stu-id="8d884-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8d884-115">親要素</span><span class="sxs-lookup"><span data-stu-id="8d884-115">Parent Elements</span></span>

|<span data-ttu-id="8d884-116">要素</span><span class="sxs-lookup"><span data-stu-id="8d884-116">Element</span></span>|<span data-ttu-id="8d884-117">説明</span><span class="sxs-lookup"><span data-stu-id="8d884-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8d884-118">ListControl の ListItem の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8d884-118">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="8d884-119">このリスト項目を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="8d884-119">Defines the condition that must exist for this list item to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8d884-120">テキスト値</span><span class="sxs-lookup"><span data-stu-id="8d884-120">Text Value</span></span>

<span data-ttu-id="8d884-121">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="8d884-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="8d884-122">解説</span><span class="sxs-lookup"><span data-stu-id="8d884-122">Remarks</span></span>

<span data-ttu-id="8d884-123">この要素が使用されている場合、 `PropertyName` 選択条件を定義するときに要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="8d884-123">If this element is used, you cannot specify the `PropertyName` element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d884-124">参照</span><span class="sxs-lookup"><span data-stu-id="8d884-124">See Also</span></span>

[<span data-ttu-id="8d884-125">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="8d884-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
