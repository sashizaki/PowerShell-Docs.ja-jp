---
title: TableControl の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: db751c40b22db52985bc7cd9f8f4296a64a523f0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787463"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="454d9-102">TableControl の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="454d9-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="454d9-103">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="454d9-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="454d9-104">このセット内のいずれかの型が存在する場合、条件が満たされ、テーブルビューのこの定義を使用してオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="454d9-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the table view.</span></span>

<span data-ttu-id="454d9-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (format) TableRowEntries Element (format) TableRowEntry Element (format) TableRowEntry (format) の SelectionCondition 要素の entryselectedby for TableRowEntry (Format) SelectionSetName Element for EntrySelectedBy for TableRowEntry (Format) を指定します。</span><span class="sxs-lookup"><span data-stu-id="454d9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="454d9-106">構文</span><span class="sxs-lookup"><span data-stu-id="454d9-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="454d9-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="454d9-107">Attributes and Elements</span></span>

<span data-ttu-id="454d9-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="454d9-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="454d9-109">属性</span><span class="sxs-lookup"><span data-stu-id="454d9-109">Attributes</span></span>

<span data-ttu-id="454d9-110">なし。</span><span class="sxs-lookup"><span data-stu-id="454d9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="454d9-111">子要素</span><span class="sxs-lookup"><span data-stu-id="454d9-111">Child Elements</span></span>

<span data-ttu-id="454d9-112">なし。</span><span class="sxs-lookup"><span data-stu-id="454d9-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="454d9-113">親要素</span><span class="sxs-lookup"><span data-stu-id="454d9-113">Parent Elements</span></span>

|<span data-ttu-id="454d9-114">要素</span><span class="sxs-lookup"><span data-stu-id="454d9-114">Element</span></span>|<span data-ttu-id="454d9-115">説明</span><span class="sxs-lookup"><span data-stu-id="454d9-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="454d9-116">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="454d9-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="454d9-117">テーブルビューのこの定義に使用する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="454d9-117">Defines the condition that must exist to use for this definition of the table view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="454d9-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="454d9-118">Text Value</span></span>

<span data-ttu-id="454d9-119">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="454d9-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="454d9-120">解説</span><span class="sxs-lookup"><span data-stu-id="454d9-120">Remarks</span></span>

<span data-ttu-id="454d9-121">選択条件では、選択セットまたは .NET 型を指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="454d9-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="454d9-122">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="454d9-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="454d9-123">選択セットは、書式設定ファイルによって定義される任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="454d9-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="454d9-124">選択セットの作成と参照の詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="454d9-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="454d9-125">ワイドビューのその他のコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="454d9-125">For more information about other components of a wide view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="454d9-126">参照</span><span class="sxs-lookup"><span data-stu-id="454d9-126">See Also</span></span>

[<span data-ttu-id="454d9-127">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="454d9-127">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="454d9-128">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="454d9-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="454d9-129">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="454d9-129">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="454d9-130">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="454d9-130">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="454d9-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="454d9-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
