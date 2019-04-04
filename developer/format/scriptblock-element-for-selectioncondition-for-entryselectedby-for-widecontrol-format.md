---
title: SelectionCondition EntrySelectedBy WideControl (形式) のためのスクリプト ブロックの要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ec68309-7826-4643-a521-e29c996663fb
caps.latest.revision: 11
ms.openlocfilehash: 649a978e21e9421a3f3e953261e1d309e23c3f9c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862948"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="255c6-102">WideControl の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="255c6-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="255c6-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="255c6-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="255c6-104">このスクリプトを評価するときに`true`条件が満たされると、およびワイド エントリの定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="255c6-104">When this script is evaluated to `true`, the condition is met, and the wide entry definition is used.</span></span>

<span data-ttu-id="255c6-105">構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式) EntrySelectedBy 要素の WideEntry (形式) SelectionCondition 要素EntrySelectedBy SelectionCondition EntrySelectedBy WideEntry (形式) のためのスクリプト ブロック要素を WideEntry (形式)</span><span class="sxs-lookup"><span data-stu-id="255c6-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="255c6-106">構文</span><span class="sxs-lookup"><span data-stu-id="255c6-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="255c6-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="255c6-107">Attributes and Elements</span></span>

<span data-ttu-id="255c6-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。</span><span class="sxs-lookup"><span data-stu-id="255c6-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="255c6-109">属性</span><span class="sxs-lookup"><span data-stu-id="255c6-109">Attributes</span></span>

<span data-ttu-id="255c6-110">なし。</span><span class="sxs-lookup"><span data-stu-id="255c6-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="255c6-111">子要素</span><span class="sxs-lookup"><span data-stu-id="255c6-111">Child Elements</span></span>

<span data-ttu-id="255c6-112">なし。</span><span class="sxs-lookup"><span data-stu-id="255c6-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="255c6-113">親要素</span><span class="sxs-lookup"><span data-stu-id="255c6-113">Parent Elements</span></span>

|<span data-ttu-id="255c6-114">要素</span><span class="sxs-lookup"><span data-stu-id="255c6-114">Element</span></span>|<span data-ttu-id="255c6-115">説明</span><span class="sxs-lookup"><span data-stu-id="255c6-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="255c6-116">WideEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="255c6-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="255c6-117">この定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="255c6-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="255c6-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="255c6-118">Text Value</span></span>

<span data-ttu-id="255c6-119">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="255c6-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="255c6-120">コメント</span><span class="sxs-lookup"><span data-stu-id="255c6-120">Remarks</span></span>

<span data-ttu-id="255c6-121">選択条件を評価するために、少なくとも 1 つのスクリプトまたはプロパティ名を指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="255c6-121">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="255c6-122">選択条件を使用する方法の詳細については、[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="255c6-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="255c6-123">ワイド ビューの他のコンポーネントに関する詳細については、[表示幅が広い](./creating-a-wide-view.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="255c6-123">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="255c6-124">参照</span><span class="sxs-lookup"><span data-stu-id="255c6-124">See Also</span></span>

[<span data-ttu-id="255c6-125">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="255c6-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="255c6-126">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="255c6-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="255c6-127">SelectionCondition EntrySelectedBy WideEntry (形式) のための PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="255c6-127">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="255c6-128">WideEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="255c6-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="255c6-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="255c6-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
