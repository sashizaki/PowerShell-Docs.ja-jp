---
title: ListControl (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 3f0a6b6b381f39492da36dab271503fc7cf6e7fc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785559"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="094ae-102">ListControl の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="094ae-102">PropertyName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="094ae-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="094ae-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="094ae-104">このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、リストエントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="094ae-104">When this property is present or when it evaluates to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="094ae-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries Element (format) ListEntry Element (format) ListEntry (format) の SelectionCondition 要素を ListEntry (Format) の selectioncondition 要素に指定します。 EntrySelectedBy on ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="094ae-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="094ae-106">構文</span><span class="sxs-lookup"><span data-stu-id="094ae-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="094ae-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="094ae-107">Attributes and Elements</span></span>

<span data-ttu-id="094ae-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="094ae-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="094ae-109">属性</span><span class="sxs-lookup"><span data-stu-id="094ae-109">Attributes</span></span>

<span data-ttu-id="094ae-110">なし。</span><span class="sxs-lookup"><span data-stu-id="094ae-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="094ae-111">子要素</span><span class="sxs-lookup"><span data-stu-id="094ae-111">Child Elements</span></span>

<span data-ttu-id="094ae-112">なし。</span><span class="sxs-lookup"><span data-stu-id="094ae-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="094ae-113">親要素</span><span class="sxs-lookup"><span data-stu-id="094ae-113">Parent Elements</span></span>

|<span data-ttu-id="094ae-114">要素</span><span class="sxs-lookup"><span data-stu-id="094ae-114">Element</span></span>|<span data-ttu-id="094ae-115">説明</span><span class="sxs-lookup"><span data-stu-id="094ae-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="094ae-116">ListEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="094ae-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="094ae-117">このリストエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="094ae-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="094ae-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="094ae-118">Text Value</span></span>

<span data-ttu-id="094ae-119">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="094ae-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="094ae-120">解説</span><span class="sxs-lookup"><span data-stu-id="094ae-120">Remarks</span></span>

<span data-ttu-id="094ae-121">選択条件では、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="094ae-121">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="094ae-122">選択条件の使用方法の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="094ae-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="094ae-123">リストビューのその他のコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="094ae-123">For more information about other components of a list view, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="094ae-124">参照</span><span class="sxs-lookup"><span data-stu-id="094ae-124">See Also</span></span>

[<span data-ttu-id="094ae-125">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="094ae-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="094ae-126">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="094ae-126">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="094ae-127">ListEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="094ae-127">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="094ae-128">ListEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="094ae-128">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="094ae-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="094ae-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
