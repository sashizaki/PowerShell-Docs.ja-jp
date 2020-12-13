---
ms.date: 09/13/2016
ms.topic: reference
title: TableControl の EntrySelectedBy の SelectionSetName 要素 (書式)
description: TableControl の EntrySelectedBy の SelectionSetName 要素 (書式)
ms.openlocfilehash: a5a395f718d0e1a2d7f33d120ce4fd2ff787cc34
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651772"
---
# <a name="selectionsetname-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="0899d-103">TableControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="0899d-103">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="0899d-104">テーブルビューのこのエントリを使用する .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="0899d-104">Specifies a set of .NET types the use this entry of the table view.</span></span> <span data-ttu-id="0899d-105">エントリに指定できる選択セットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="0899d-105">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="0899d-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (format) TableRowEntries Element (format) TableRowEntry Element (format) SelectionSetName 要素 (format) の EntrySelectedBy for TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="0899d-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) SelectionSetName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0899d-107">構文</span><span class="sxs-lookup"><span data-stu-id="0899d-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0899d-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0899d-108">Attributes and Elements</span></span>

<span data-ttu-id="0899d-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0899d-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0899d-110">属性</span><span class="sxs-lookup"><span data-stu-id="0899d-110">Attributes</span></span>

<span data-ttu-id="0899d-111">なし。</span><span class="sxs-lookup"><span data-stu-id="0899d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0899d-112">子要素</span><span class="sxs-lookup"><span data-stu-id="0899d-112">Child Elements</span></span>

<span data-ttu-id="0899d-113">なし。</span><span class="sxs-lookup"><span data-stu-id="0899d-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0899d-114">親要素</span><span class="sxs-lookup"><span data-stu-id="0899d-114">Parent Elements</span></span>

|<span data-ttu-id="0899d-115">要素</span><span class="sxs-lookup"><span data-stu-id="0899d-115">Element</span></span>|<span data-ttu-id="0899d-116">説明</span><span class="sxs-lookup"><span data-stu-id="0899d-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0899d-117">EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="0899d-117">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="0899d-118">このエントリを使用する .NET 型、またはこのエントリが使用されるために存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="0899d-118">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0899d-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="0899d-119">Text Value</span></span>

<span data-ttu-id="0899d-120">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0899d-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="0899d-121">解説</span><span class="sxs-lookup"><span data-stu-id="0899d-121">Remarks</span></span>

<span data-ttu-id="0899d-122">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="0899d-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="0899d-123">たとえば、同じオブジェクトのセットに対してテーブルビューとリストビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="0899d-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="0899d-124">選択セットの定義の詳細については、「 [ビューのオブジェクトセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0899d-124">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="0899d-125">エントリの選択セットを指定する場合、型名を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="0899d-125">If you specify a selection set for an entry, you cannot specify a type name.</span></span> <span data-ttu-id="0899d-126">.NET 型を指定する方法の詳細については、「 [TableRowEntry (Format) の EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-tablecontrol-format.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0899d-126">For more information about how to specify a .NET type, see [TypeName Element for EntrySelectedBy for TableRowEntry (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).</span></span>

<span data-ttu-id="0899d-127">テーブルビューのコンポーネントの詳細については、「 [テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0899d-127">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0899d-128">参照</span><span class="sxs-lookup"><span data-stu-id="0899d-128">See Also</span></span>

[<span data-ttu-id="0899d-129">EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="0899d-129">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="0899d-130">ビューに対するオブジェクトのセットの定義</span><span class="sxs-lookup"><span data-stu-id="0899d-130">Defining Sets of objects for a View</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="0899d-131">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="0899d-131">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="0899d-132">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="0899d-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
