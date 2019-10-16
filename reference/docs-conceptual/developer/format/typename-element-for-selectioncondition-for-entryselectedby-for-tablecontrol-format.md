---
title: TableControl の EntrySelectedBy の SelectionCondition の TypeName 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e97d56fb-4e35-447a-9282-26f10d0a4609
caps.latest.revision: 11
ms.openlocfilehash: fe65ac95cead7df0069ffdae666fb34b7309fbb6
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361471"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="00f2b-102">TableControl の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="00f2b-102">TypeName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="00f2b-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="00f2b-104">この型が存在する場合、条件が満たされ、テーブルの行が使用されます。</span><span class="sxs-lookup"><span data-stu-id="00f2b-104">When this type is present, the condition is met, and the table row is used.</span></span>

<span data-ttu-id="00f2b-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) TableRowEntry (Format) の要素EntrySelectedBy for TableRowEntry (Format) の SelectionCondition に対して EntrySelectedBy for TableRowEntry (Format) の TypeName 要素の selectioncondition 要素</span><span class="sxs-lookup"><span data-stu-id="00f2b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="00f2b-106">構文</span><span class="sxs-lookup"><span data-stu-id="00f2b-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="00f2b-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="00f2b-107">Attributes and Elements</span></span>

<span data-ttu-id="00f2b-108">次のセクションでは、属性、子要素、`TypeName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="00f2b-109">属性</span><span class="sxs-lookup"><span data-stu-id="00f2b-109">Attributes</span></span>

<span data-ttu-id="00f2b-110">なし。</span><span class="sxs-lookup"><span data-stu-id="00f2b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="00f2b-111">子要素</span><span class="sxs-lookup"><span data-stu-id="00f2b-111">Child Elements</span></span>

<span data-ttu-id="00f2b-112">なし。</span><span class="sxs-lookup"><span data-stu-id="00f2b-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="00f2b-113">親要素</span><span class="sxs-lookup"><span data-stu-id="00f2b-113">Parent Elements</span></span>

|<span data-ttu-id="00f2b-114">要素</span><span class="sxs-lookup"><span data-stu-id="00f2b-114">Element</span></span>|<span data-ttu-id="00f2b-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="00f2b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="00f2b-116">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="00f2b-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="00f2b-117">このテーブル行を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-117">Defines the condition that must exist for this table row to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="00f2b-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="00f2b-118">Text Value</span></span>

<span data-ttu-id="00f2b-119">.NET 型の完全修飾名 (`System.IO.DirectoryInfo` など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="00f2b-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="00f2b-120">コメント</span><span class="sxs-lookup"><span data-stu-id="00f2b-120">Remarks</span></span>

<span data-ttu-id="00f2b-121">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="00f2b-121">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="00f2b-122">選択条件の使用方法の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00f2b-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="00f2b-123">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00f2b-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="00f2b-124">参照</span><span class="sxs-lookup"><span data-stu-id="00f2b-124">See Also</span></span>

[<span data-ttu-id="00f2b-125">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="00f2b-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="00f2b-126">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="00f2b-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="00f2b-127">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="00f2b-127">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="00f2b-128">EntrySelectedBy for TableRowEntry (Format) の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="00f2b-128">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="00f2b-129">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="00f2b-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
