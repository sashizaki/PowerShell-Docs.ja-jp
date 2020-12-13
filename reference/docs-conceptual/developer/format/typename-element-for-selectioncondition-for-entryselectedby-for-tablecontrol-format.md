---
ms.date: 09/13/2016
ms.topic: reference
title: TableControl の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)
description: TableControl の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)
ms.openlocfilehash: 66e90ab33775cf35d5e98e45266996d2d1a622d7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659629"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="5d269-103">TableControl の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5d269-103">TypeName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="5d269-104">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="5d269-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="5d269-105">この型が存在する場合、条件が満たされ、テーブルの行が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5d269-105">When this type is present, the condition is met, and the table row is used.</span></span>

<span data-ttu-id="5d269-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (format) TableRowEntries Element (format) TableRowEntry Element (format) TableRowEntry (format) の SelectionCondition 要素を TableRowEntry (Format) の selectioncondition for entryselectedby on TableRowEntry (Format) 用に指定します。</span><span class="sxs-lookup"><span data-stu-id="5d269-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5d269-107">構文</span><span class="sxs-lookup"><span data-stu-id="5d269-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5d269-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5d269-108">Attributes and Elements</span></span>

<span data-ttu-id="5d269-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="5d269-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5d269-110">属性</span><span class="sxs-lookup"><span data-stu-id="5d269-110">Attributes</span></span>

<span data-ttu-id="5d269-111">なし。</span><span class="sxs-lookup"><span data-stu-id="5d269-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5d269-112">子要素</span><span class="sxs-lookup"><span data-stu-id="5d269-112">Child Elements</span></span>

<span data-ttu-id="5d269-113">なし。</span><span class="sxs-lookup"><span data-stu-id="5d269-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5d269-114">親要素</span><span class="sxs-lookup"><span data-stu-id="5d269-114">Parent Elements</span></span>

|<span data-ttu-id="5d269-115">要素</span><span class="sxs-lookup"><span data-stu-id="5d269-115">Element</span></span>|<span data-ttu-id="5d269-116">説明</span><span class="sxs-lookup"><span data-stu-id="5d269-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5d269-117">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="5d269-117">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="5d269-118">このテーブル行を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="5d269-118">Defines the condition that must exist for this table row to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5d269-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="5d269-119">Text Value</span></span>

<span data-ttu-id="5d269-120">.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="5d269-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5d269-121">解説</span><span class="sxs-lookup"><span data-stu-id="5d269-121">Remarks</span></span>

<span data-ttu-id="5d269-122">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="5d269-122">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="5d269-123">選択条件の使用方法の詳細については、「 [ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d269-123">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="5d269-124">テーブルビューのコンポーネントの詳細については、「 [テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d269-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5d269-125">参照</span><span class="sxs-lookup"><span data-stu-id="5d269-125">See Also</span></span>

[<span data-ttu-id="5d269-126">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="5d269-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="5d269-127">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="5d269-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="5d269-128">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="5d269-128">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="5d269-129">EntrySelectedBy for TableRowEntry (Format) の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="5d269-129">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="5d269-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="5d269-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
