---
title: ListControl (形式) の EntrySelectedBy SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cff7763c-5ce0-49c1-a480-1249c9f57a13
caps.latest.revision: 11
ms.openlocfilehash: 7fd431b4b1ddecd3a7358c2bf97f299b97162b34
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860158"
---
# <a name="selectionsetname-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="5d23a-102">ListControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5d23a-102">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="5d23a-103">.NET オブジェクト、リストのエントリのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d23a-103">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="5d23a-104">エントリに指定できる選択セットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="5d23a-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="5d23a-105">構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) ListControl 要素 (形式) ListEntries 要素 (形式) ListEntry 要素 (形式) EntrySelectedBy 要素の ListEntry (形式) SelectionSetName 要素EntrySelectedBy ListEntry (形式) の</span><span class="sxs-lookup"><span data-stu-id="5d23a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5d23a-106">構文</span><span class="sxs-lookup"><span data-stu-id="5d23a-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5d23a-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="5d23a-107">Attributes and Elements</span></span>

<span data-ttu-id="5d23a-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。</span><span class="sxs-lookup"><span data-stu-id="5d23a-108">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5d23a-109">属性</span><span class="sxs-lookup"><span data-stu-id="5d23a-109">Attributes</span></span>

<span data-ttu-id="5d23a-110">なし。</span><span class="sxs-lookup"><span data-stu-id="5d23a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5d23a-111">子要素</span><span class="sxs-lookup"><span data-stu-id="5d23a-111">Child Elements</span></span>

<span data-ttu-id="5d23a-112">なし。</span><span class="sxs-lookup"><span data-stu-id="5d23a-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5d23a-113">親要素</span><span class="sxs-lookup"><span data-stu-id="5d23a-113">Parent Elements</span></span>

|<span data-ttu-id="5d23a-114">要素</span><span class="sxs-lookup"><span data-stu-id="5d23a-114">Element</span></span>|<span data-ttu-id="5d23a-115">説明</span><span class="sxs-lookup"><span data-stu-id="5d23a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5d23a-116">ListEntry (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="5d23a-116">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="5d23a-117">このリストのエントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="5d23a-117">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5d23a-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="5d23a-118">Text Value</span></span>

<span data-ttu-id="5d23a-119">選択範囲のセットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5d23a-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="5d23a-120">コメント</span><span class="sxs-lookup"><span data-stu-id="5d23a-120">Remarks</span></span>

<span data-ttu-id="5d23a-121">リストの各エントリに少なくとも 1 つの型名、選択範囲のセット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d23a-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="5d23a-122">複数のビューで使用されるオブジェクトのグループを定義するときに、選択範囲のセットが通常使用されます。</span><span class="sxs-lookup"><span data-stu-id="5d23a-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="5d23a-123">たとえば、テーブル ビューと同じオブジェクトのセットのリスト ビューを作成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5d23a-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="5d23a-124">選択範囲のセットを定義する詳細については、[ビューのオブジェクトのセットを定義する](./defining-selection-sets.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d23a-124">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="5d23a-125">リスト ビューのコンポーネントに関する詳細については、[リスト ビューを作成する](./creating-a-list-view.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d23a-125">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="5d23a-126">例</span><span class="sxs-lookup"><span data-stu-id="5d23a-126">Example</span></span>

<span data-ttu-id="5d23a-127">次の例では、選択リスト ビューのエントリのセットを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5d23a-127">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="5d23a-128">参照</span><span class="sxs-lookup"><span data-stu-id="5d23a-128">See Also</span></span>

[<span data-ttu-id="5d23a-129">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="5d23a-129">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="5d23a-130">ListEntry (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="5d23a-130">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="5d23a-131">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="5d23a-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
