---
ms.date: 09/13/2016
ms.topic: reference
title: TableRowEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)
description: TableRowEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)
ms.openlocfilehash: dcb59fc438ae217870566f09204fb16b8f031614
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665789"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format"></a><span data-ttu-id="dee01-103">TableRowEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="dee01-103">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

<span data-ttu-id="dee01-104">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="dee01-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="dee01-105">このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、テーブルエントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="dee01-105">When this property is present or when it evaluates to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="dee01-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (format) TableRowEntries Element (format) TableRowEntry Element (format) TableRowEntry (format) の SelectionCondition 要素を TableRowEntry (Format) の SelectionCondition for entryselectedby on TableRowEntry (Format) 用に指定します。</span><span class="sxs-lookup"><span data-stu-id="dee01-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dee01-107">構文</span><span class="sxs-lookup"><span data-stu-id="dee01-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dee01-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="dee01-108">Attributes and Elements</span></span>

<span data-ttu-id="dee01-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="dee01-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="dee01-110">属性</span><span class="sxs-lookup"><span data-stu-id="dee01-110">Attributes</span></span>

<span data-ttu-id="dee01-111">なし。</span><span class="sxs-lookup"><span data-stu-id="dee01-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dee01-112">子要素</span><span class="sxs-lookup"><span data-stu-id="dee01-112">Child Elements</span></span>

<span data-ttu-id="dee01-113">なし。</span><span class="sxs-lookup"><span data-stu-id="dee01-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="dee01-114">親要素</span><span class="sxs-lookup"><span data-stu-id="dee01-114">Parent Elements</span></span>

|<span data-ttu-id="dee01-115">要素</span><span class="sxs-lookup"><span data-stu-id="dee01-115">Element</span></span>|<span data-ttu-id="dee01-116">説明</span><span class="sxs-lookup"><span data-stu-id="dee01-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dee01-117">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="dee01-117">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="dee01-118">このテーブルエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="dee01-118">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="dee01-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="dee01-119">Text Value</span></span>

<span data-ttu-id="dee01-120">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="dee01-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="dee01-121">解説</span><span class="sxs-lookup"><span data-stu-id="dee01-121">Remarks</span></span>

<span data-ttu-id="dee01-122">選択条件では、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="dee01-122">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="dee01-123">選択条件を使用する方法の詳細については、「 [ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dee01-123">For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="dee01-124">テーブルビューのコンポーネントの詳細については、「 [テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dee01-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dee01-125">参照</span><span class="sxs-lookup"><span data-stu-id="dee01-125">See Also</span></span>

[<span data-ttu-id="dee01-126">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="dee01-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="dee01-127">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="dee01-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="dee01-128">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="dee01-128">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="dee01-129">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="dee01-129">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="dee01-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="dee01-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
