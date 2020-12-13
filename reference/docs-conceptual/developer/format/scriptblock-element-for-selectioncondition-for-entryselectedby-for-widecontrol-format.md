---
ms.date: 09/13/2016
ms.topic: reference
title: WideControl の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)
description: WideControl の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)
ms.openlocfilehash: 53d3eba9d453dbcc96afbe8f81a16b61573f2874
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651974"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="75e98-103">WideControl の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="75e98-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="75e98-104">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="75e98-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="75e98-105">このスクリプトがに評価されると、 `true` 条件が満たされ、ワイドエントリの定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="75e98-105">When this script is evaluated to `true`, the condition is met, and the wide entry definition is used.</span></span>

<span data-ttu-id="75e98-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) Element (format) Element (format) EntrySelectedBy for WideEntry (format) の SelectionCondition 要素を WideEntry (format) の selectioncondition 要素に指定します。 EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="75e98-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="75e98-107">構文</span><span class="sxs-lookup"><span data-stu-id="75e98-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="75e98-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="75e98-108">Attributes and Elements</span></span>

<span data-ttu-id="75e98-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="75e98-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="75e98-110">属性</span><span class="sxs-lookup"><span data-stu-id="75e98-110">Attributes</span></span>

<span data-ttu-id="75e98-111">なし。</span><span class="sxs-lookup"><span data-stu-id="75e98-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="75e98-112">子要素</span><span class="sxs-lookup"><span data-stu-id="75e98-112">Child Elements</span></span>

<span data-ttu-id="75e98-113">なし。</span><span class="sxs-lookup"><span data-stu-id="75e98-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="75e98-114">親要素</span><span class="sxs-lookup"><span data-stu-id="75e98-114">Parent Elements</span></span>

|<span data-ttu-id="75e98-115">要素</span><span class="sxs-lookup"><span data-stu-id="75e98-115">Element</span></span>|<span data-ttu-id="75e98-116">説明</span><span class="sxs-lookup"><span data-stu-id="75e98-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="75e98-117">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="75e98-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="75e98-118">この定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="75e98-118">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="75e98-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="75e98-119">Text Value</span></span>

<span data-ttu-id="75e98-120">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="75e98-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="75e98-121">解説</span><span class="sxs-lookup"><span data-stu-id="75e98-121">Remarks</span></span>

<span data-ttu-id="75e98-122">選択条件では、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="75e98-122">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="75e98-123">選択条件の使用方法の詳細については、「 [データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75e98-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="75e98-124">ワイドビューのその他のコンポーネントの詳細については、「 [Wide ビュー](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75e98-124">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="75e98-125">参照</span><span class="sxs-lookup"><span data-stu-id="75e98-125">See Also</span></span>

[<span data-ttu-id="75e98-126">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="75e98-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="75e98-127">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="75e98-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="75e98-128">WideEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="75e98-128">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="75e98-129">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="75e98-129">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="75e98-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="75e98-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
