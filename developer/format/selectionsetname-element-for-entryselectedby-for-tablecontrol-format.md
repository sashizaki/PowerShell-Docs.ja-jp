---
title: TableControl (形式) の EntrySelectedBy SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5dd0bd5d-f206-4cc6-a0f8-70700ee2c4b7
caps.latest.revision: 8
ms.openlocfilehash: 819906127e81355c45103ede85ef3608e1c1cfeb
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856098"
---
# <a name="selectionsetname-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="92fd3-102">TableControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="92fd3-102">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="92fd3-103">一連の .NET 型、使用して、テーブル ビューのこのエントリを指定します。</span><span class="sxs-lookup"><span data-stu-id="92fd3-103">Specifies a set of .NET types the use this entry of the table view.</span></span> <span data-ttu-id="92fd3-104">エントリに指定できる選択セットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="92fd3-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="92fd3-105">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素 (形式) TableRowEntry 要素 (形式) EntrySelectedBy 要素 (形式) SelectionSetName の構成要素EntrySelectedBy TableRowEntry (形式) の</span><span class="sxs-lookup"><span data-stu-id="92fd3-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) SelectionSetName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="92fd3-106">構文</span><span class="sxs-lookup"><span data-stu-id="92fd3-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="92fd3-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="92fd3-107">Attributes and Elements</span></span>

<span data-ttu-id="92fd3-108">次のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="92fd3-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="92fd3-109">属性</span><span class="sxs-lookup"><span data-stu-id="92fd3-109">Attributes</span></span>

<span data-ttu-id="92fd3-110">なし。</span><span class="sxs-lookup"><span data-stu-id="92fd3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="92fd3-111">子要素</span><span class="sxs-lookup"><span data-stu-id="92fd3-111">Child Elements</span></span>

<span data-ttu-id="92fd3-112">なし。</span><span class="sxs-lookup"><span data-stu-id="92fd3-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="92fd3-113">親要素</span><span class="sxs-lookup"><span data-stu-id="92fd3-113">Parent Elements</span></span>

|<span data-ttu-id="92fd3-114">要素</span><span class="sxs-lookup"><span data-stu-id="92fd3-114">Element</span></span>|<span data-ttu-id="92fd3-115">説明</span><span class="sxs-lookup"><span data-stu-id="92fd3-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="92fd3-116">EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="92fd3-116">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="92fd3-117">このエントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="92fd3-117">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="92fd3-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="92fd3-118">Text Value</span></span>

<span data-ttu-id="92fd3-119">選択範囲のセットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="92fd3-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="92fd3-120">コメント</span><span class="sxs-lookup"><span data-stu-id="92fd3-120">Remarks</span></span>

<span data-ttu-id="92fd3-121">複数のビューで使用されるオブジェクトのグループを定義するときに、選択範囲のセットが通常使用されます。</span><span class="sxs-lookup"><span data-stu-id="92fd3-121">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="92fd3-122">たとえば、テーブル ビューと同じオブジェクトのセットのリスト ビューを作成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="92fd3-122">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="92fd3-123">選択範囲のセットを定義する詳細については、次を参照してください。[ビューのオブジェクトのセットを定義する](./defining-selection-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="92fd3-123">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="92fd3-124">選択のエントリのセットを指定する場合は、型名を指定できません。</span><span class="sxs-lookup"><span data-stu-id="92fd3-124">If you specify a selection set for an entry, you cannot specify a type name.</span></span> <span data-ttu-id="92fd3-125">.NET 型を指定する方法の詳細については、次を参照してください。 [TableRowEntry (形式) の EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-tablecontrol-format.md)します。</span><span class="sxs-lookup"><span data-stu-id="92fd3-125">For more information about how to specify a .NET type, see [TypeName Element for EntrySelectedBy for TableRowEntry (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).</span></span>

<span data-ttu-id="92fd3-126">テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="92fd3-126">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="92fd3-127">参照</span><span class="sxs-lookup"><span data-stu-id="92fd3-127">See Also</span></span>

[<span data-ttu-id="92fd3-128">EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="92fd3-128">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="92fd3-129">ビューのオブジェクトのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="92fd3-129">Defining Sets of objects for a View</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="92fd3-130">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="92fd3-130">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="92fd3-131">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="92fd3-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
