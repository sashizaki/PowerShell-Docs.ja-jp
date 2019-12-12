---
title: TableControl (Format) の EntrySelectedBy の SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5dd0bd5d-f206-4cc6-a0f8-70700ee2c4b7
caps.latest.revision: 8
ms.openlocfilehash: 819906127e81355c45103ede85ef3608e1c1cfeb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368321"
---
# <a name="selectionsetname-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="5ffcb-102">TableControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5ffcb-102">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="5ffcb-103">テーブルビューのこのエントリを使用する .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="5ffcb-103">Specifies a set of .NET types the use this entry of the table view.</span></span> <span data-ttu-id="5ffcb-104">エントリに指定できる選択セットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="5ffcb-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="5ffcb-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) SelectionSetName Element By Element (Format) 要素TableRowEntry の EntrySelectedBy (形式)</span><span class="sxs-lookup"><span data-stu-id="5ffcb-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) SelectionSetName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5ffcb-106">構文</span><span class="sxs-lookup"><span data-stu-id="5ffcb-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5ffcb-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="5ffcb-107">Attributes and Elements</span></span>

<span data-ttu-id="5ffcb-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5ffcb-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="5ffcb-109">属性</span><span class="sxs-lookup"><span data-stu-id="5ffcb-109">Attributes</span></span>

<span data-ttu-id="5ffcb-110">なし。</span><span class="sxs-lookup"><span data-stu-id="5ffcb-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5ffcb-111">子要素</span><span class="sxs-lookup"><span data-stu-id="5ffcb-111">Child Elements</span></span>

<span data-ttu-id="5ffcb-112">なし。</span><span class="sxs-lookup"><span data-stu-id="5ffcb-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5ffcb-113">親要素</span><span class="sxs-lookup"><span data-stu-id="5ffcb-113">Parent Elements</span></span>

|<span data-ttu-id="5ffcb-114">要素</span><span class="sxs-lookup"><span data-stu-id="5ffcb-114">Element</span></span>|<span data-ttu-id="5ffcb-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="5ffcb-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5ffcb-116">EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="5ffcb-116">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="5ffcb-117">このエントリを使用する .NET 型、またはこのエントリが使用されるために存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="5ffcb-117">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5ffcb-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="5ffcb-118">Text Value</span></span>

<span data-ttu-id="5ffcb-119">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5ffcb-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="5ffcb-120">コメント</span><span class="sxs-lookup"><span data-stu-id="5ffcb-120">Remarks</span></span>

<span data-ttu-id="5ffcb-121">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="5ffcb-121">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="5ffcb-122">たとえば、同じオブジェクトのセットに対してテーブルビューとリストビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5ffcb-122">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="5ffcb-123">選択セットの定義の詳細については、「[ビューのオブジェクトセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ffcb-123">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="5ffcb-124">エントリの選択セットを指定する場合、型名を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="5ffcb-124">If you specify a selection set for an entry, you cannot specify a type name.</span></span> <span data-ttu-id="5ffcb-125">.NET 型を指定する方法の詳細については、「 [TableRowEntry (Format) の EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-tablecontrol-format.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ffcb-125">For more information about how to specify a .NET type, see [TypeName Element for EntrySelectedBy for TableRowEntry (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).</span></span>

<span data-ttu-id="5ffcb-126">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ffcb-126">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5ffcb-127">参照</span><span class="sxs-lookup"><span data-stu-id="5ffcb-127">See Also</span></span>

[<span data-ttu-id="5ffcb-128">EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="5ffcb-128">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="5ffcb-129">ビューに対するオブジェクトのセットの定義</span><span class="sxs-lookup"><span data-stu-id="5ffcb-129">Defining Sets of objects for a View</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="5ffcb-130">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="5ffcb-130">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="5ffcb-131">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="5ffcb-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
