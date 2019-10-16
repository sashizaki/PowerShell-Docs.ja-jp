---
title: ListControl の ItemSelectionCondition の ScriptBlock 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c929a6df-d050-416a-9de0-e913dd5a035c
caps.latest.revision: 8
ms.openlocfilehash: a0768a9c1ac66cd9dcf1848c4b031ccbc722b4c2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362101"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="f5d92-102">ListControl の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f5d92-102">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="f5d92-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5d92-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="f5d92-104">このスクリプトが `true` に評価されると、条件が満たされ、リスト項目が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5d92-104">When this script is evaluated to `true`, the condition is met, and the list item is used.</span></span> <span data-ttu-id="f5d92-105">この要素は、リストビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5d92-105">This element is used when defining a list view.</span></span>

<span data-ttu-id="f5d92-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (Format) ListControl (format) ListEntry 要素の listentries の ListControl (Format) ListItems 要素の listentries 要素ListControl (Format) の ListItem 要素の ListItems のリストコントロール (format) ItemSelectionCondition 要素の ListControl (書式) の ItemSelectionCondition の (Format) ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="f5d92-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for List Control (Format) ItemSelectionCondition Element for ListItem for ListControl (Format) ScriptBlock Element for ItemSelectionCondition for ListControl  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f5d92-107">構文</span><span class="sxs-lookup"><span data-stu-id="f5d92-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f5d92-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="f5d92-108">Attributes and Elements</span></span>

<span data-ttu-id="f5d92-109">次のセクションでは、`ScriptBlock` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f5d92-109">The following sections describe attributes, child elements, and the parent elements of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f5d92-110">属性</span><span class="sxs-lookup"><span data-stu-id="f5d92-110">Attributes</span></span>

<span data-ttu-id="f5d92-111">なし。</span><span class="sxs-lookup"><span data-stu-id="f5d92-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f5d92-112">子要素</span><span class="sxs-lookup"><span data-stu-id="f5d92-112">Child Elements</span></span>

<span data-ttu-id="f5d92-113">なし。</span><span class="sxs-lookup"><span data-stu-id="f5d92-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f5d92-114">親要素</span><span class="sxs-lookup"><span data-stu-id="f5d92-114">Parent Elements</span></span>

|<span data-ttu-id="f5d92-115">要素</span><span class="sxs-lookup"><span data-stu-id="f5d92-115">Element</span></span>|<span data-ttu-id="f5d92-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="f5d92-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f5d92-117">ListControl の ListItem の ItemSelectionCondition 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="f5d92-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="f5d92-118">このリスト項目を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="f5d92-118">Defines the condition that must exist for this list item to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f5d92-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="f5d92-119">Text Value</span></span>

<span data-ttu-id="f5d92-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5d92-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="f5d92-121">コメント</span><span class="sxs-lookup"><span data-stu-id="f5d92-121">Remarks</span></span>

<span data-ttu-id="f5d92-122">この要素が使用されている場合、選択条件を定義するときに `PropertyName` 要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f5d92-122">If this element is used, you cannot specify the `PropertyName` element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5d92-123">参照</span><span class="sxs-lookup"><span data-stu-id="f5d92-123">See Also</span></span>

[<span data-ttu-id="f5d92-124">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="f5d92-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
