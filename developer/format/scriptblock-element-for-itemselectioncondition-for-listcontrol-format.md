---
title: ItemSelectionCondition ListControl (形式) 用のスクリプト ブロックの要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c929a6df-d050-416a-9de0-e913dd5a035c
caps.latest.revision: 8
ms.openlocfilehash: a0768a9c1ac66cd9dcf1848c4b031ccbc722b4c2
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064409"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="03c8b-102">ListControl の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="03c8b-102">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="03c8b-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="03c8b-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="03c8b-104">このスクリプトを評価するときに`true`条件が満たされ、リスト項目を使用します。</span><span class="sxs-lookup"><span data-stu-id="03c8b-104">When this script is evaluated to `true`, the condition is met, and the list item is used.</span></span> <span data-ttu-id="03c8b-105">この要素は、リスト ビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="03c8b-105">This element is used when defining a list view.</span></span>

<span data-ttu-id="03c8b-106">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素の要素に ListControl (形式) ListEntry ListEntries ListEntry の ListControl (形式) のリスト項目要素のListItem ListControl (形式) の ItemSelectionCondition の ListControl (形式) スクリプト ブロックの要素のリスト コントロール (形式) ItemSelectionCondition 要素の ListItems の ListItem 要素を ListControl (形式)</span><span class="sxs-lookup"><span data-stu-id="03c8b-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for List Control (Format) ItemSelectionCondition Element for ListItem for ListControl (Format) ScriptBlock Element for ItemSelectionCondition for ListControl  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="03c8b-107">構文</span><span class="sxs-lookup"><span data-stu-id="03c8b-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="03c8b-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="03c8b-108">Attributes and Elements</span></span>

<span data-ttu-id="03c8b-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。</span><span class="sxs-lookup"><span data-stu-id="03c8b-109">The following sections describe attributes, child elements, and the parent elements of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="03c8b-110">属性</span><span class="sxs-lookup"><span data-stu-id="03c8b-110">Attributes</span></span>

<span data-ttu-id="03c8b-111">なし。</span><span class="sxs-lookup"><span data-stu-id="03c8b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="03c8b-112">子要素</span><span class="sxs-lookup"><span data-stu-id="03c8b-112">Child Elements</span></span>

<span data-ttu-id="03c8b-113">なし。</span><span class="sxs-lookup"><span data-stu-id="03c8b-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="03c8b-114">親要素</span><span class="sxs-lookup"><span data-stu-id="03c8b-114">Parent Elements</span></span>

|<span data-ttu-id="03c8b-115">要素</span><span class="sxs-lookup"><span data-stu-id="03c8b-115">Element</span></span>|<span data-ttu-id="03c8b-116">説明</span><span class="sxs-lookup"><span data-stu-id="03c8b-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="03c8b-117">ItemSelectionCondition ListControl (形式) を ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="03c8b-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="03c8b-118">使用するには、このリスト項目の存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="03c8b-118">Defines the condition that must exist for this list item to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="03c8b-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="03c8b-119">Text Value</span></span>

<span data-ttu-id="03c8b-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="03c8b-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="03c8b-121">コメント</span><span class="sxs-lookup"><span data-stu-id="03c8b-121">Remarks</span></span>

<span data-ttu-id="03c8b-122">指定できないかどうかは、この要素が使用される、`PropertyName`要素の選択条件を定義するときにします。</span><span class="sxs-lookup"><span data-stu-id="03c8b-122">If this element is used, you cannot specify the `PropertyName` element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="03c8b-123">参照</span><span class="sxs-lookup"><span data-stu-id="03c8b-123">See Also</span></span>

[<span data-ttu-id="03c8b-124">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="03c8b-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
