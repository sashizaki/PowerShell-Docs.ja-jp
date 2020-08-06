---
title: TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: bec8377fb13b8f288196a809e7aa4e7f46c66e31
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785542"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format"></a><span data-ttu-id="8c4d3-102">TableRowEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8c4d3-102">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

<span data-ttu-id="8c4d3-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="8c4d3-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="8c4d3-104">このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、テーブルエントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c4d3-104">When this property is present or when it evaluates to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="8c4d3-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (format) TableRowEntries Element (format) TableRowEntry Element (format) TableRowEntry (format) の SelectionCondition 要素を TableRowEntry (Format) の SelectionCondition for entryselectedby on TableRowEntry (Format) 用に指定します。</span><span class="sxs-lookup"><span data-stu-id="8c4d3-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8c4d3-106">構文</span><span class="sxs-lookup"><span data-stu-id="8c4d3-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8c4d3-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8c4d3-107">Attributes and Elements</span></span>

<span data-ttu-id="8c4d3-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="8c4d3-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8c4d3-109">属性</span><span class="sxs-lookup"><span data-stu-id="8c4d3-109">Attributes</span></span>

<span data-ttu-id="8c4d3-110">なし。</span><span class="sxs-lookup"><span data-stu-id="8c4d3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8c4d3-111">子要素</span><span class="sxs-lookup"><span data-stu-id="8c4d3-111">Child Elements</span></span>

<span data-ttu-id="8c4d3-112">なし。</span><span class="sxs-lookup"><span data-stu-id="8c4d3-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8c4d3-113">親要素</span><span class="sxs-lookup"><span data-stu-id="8c4d3-113">Parent Elements</span></span>

|<span data-ttu-id="8c4d3-114">要素</span><span class="sxs-lookup"><span data-stu-id="8c4d3-114">Element</span></span>|<span data-ttu-id="8c4d3-115">説明</span><span class="sxs-lookup"><span data-stu-id="8c4d3-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8c4d3-116">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="8c4d3-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="8c4d3-117">このテーブルエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="8c4d3-117">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8c4d3-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="8c4d3-118">Text Value</span></span>

<span data-ttu-id="8c4d3-119">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c4d3-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c4d3-120">解説</span><span class="sxs-lookup"><span data-stu-id="8c4d3-120">Remarks</span></span>

<span data-ttu-id="8c4d3-121">選択条件では、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="8c4d3-121">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="8c4d3-122">選択条件を使用する方法の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c4d3-122">For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="8c4d3-123">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c4d3-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8c4d3-124">参照</span><span class="sxs-lookup"><span data-stu-id="8c4d3-124">See Also</span></span>

[<span data-ttu-id="8c4d3-125">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="8c4d3-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="8c4d3-126">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="8c4d3-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="8c4d3-127">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="8c4d3-127">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="8c4d3-128">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="8c4d3-128">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="8c4d3-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="8c4d3-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
