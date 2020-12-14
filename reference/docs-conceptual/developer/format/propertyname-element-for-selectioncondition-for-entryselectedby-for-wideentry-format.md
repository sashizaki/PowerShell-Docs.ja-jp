---
ms.date: 09/13/2016
ms.topic: reference
title: WideEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)
description: WideEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)
ms.openlocfilehash: bda34b0c1e97fb85536132bedcec3986072801b7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665704"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="d50a4-103">WideEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d50a4-103">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="d50a4-104">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="d50a4-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="d50a4-105">このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d50a4-105">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="d50a4-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideEntry (format) の SelectionCondition 要素に対する (format) の SelectionCondition 要素のエントリ (format) の selectioncondition に対する SelectionCondition for WideEntry (format) PropertyName Element for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="d50a4-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d50a4-107">構文</span><span class="sxs-lookup"><span data-stu-id="d50a4-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

```csharp

```

## <a name="attributes-and-elements"></a><span data-ttu-id="d50a4-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d50a4-108">Attributes and Elements</span></span>

<span data-ttu-id="d50a4-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="d50a4-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d50a4-110">属性</span><span class="sxs-lookup"><span data-stu-id="d50a4-110">Attributes</span></span>

<span data-ttu-id="d50a4-111">なし。</span><span class="sxs-lookup"><span data-stu-id="d50a4-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d50a4-112">子要素</span><span class="sxs-lookup"><span data-stu-id="d50a4-112">Child Elements</span></span>

<span data-ttu-id="d50a4-113">なし。</span><span class="sxs-lookup"><span data-stu-id="d50a4-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d50a4-114">親要素</span><span class="sxs-lookup"><span data-stu-id="d50a4-114">Parent Elements</span></span>

|<span data-ttu-id="d50a4-115">要素</span><span class="sxs-lookup"><span data-stu-id="d50a4-115">Element</span></span>|<span data-ttu-id="d50a4-116">説明</span><span class="sxs-lookup"><span data-stu-id="d50a4-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d50a4-117">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="d50a4-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="d50a4-118">この定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="d50a4-118">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d50a4-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="d50a4-119">Text Value</span></span>

<span data-ttu-id="d50a4-120">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d50a4-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="d50a4-121">解説</span><span class="sxs-lookup"><span data-stu-id="d50a4-121">Remarks</span></span>

<span data-ttu-id="d50a4-122">選択条件では、少なくとも1つのプロパティ名または評価対象のスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d50a4-122">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="d50a4-123">選択条件の使用方法の詳細については、「 [データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d50a4-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="d50a4-124">ワイドビューのその他のコンポーネントの詳細については、「 [Wide ビュー](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d50a4-124">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d50a4-125">参照</span><span class="sxs-lookup"><span data-stu-id="d50a4-125">See Also</span></span>

[<span data-ttu-id="d50a4-126">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="d50a4-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="d50a4-127">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="d50a4-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="d50a4-128">WideEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="d50a4-128">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="d50a4-129">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="d50a4-129">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="d50a4-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="d50a4-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
