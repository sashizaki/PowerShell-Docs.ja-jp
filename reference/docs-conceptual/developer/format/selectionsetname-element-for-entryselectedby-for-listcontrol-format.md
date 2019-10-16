---
title: ListControl (Format) の EntrySelectedBy の SelectionSetName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cff7763c-5ce0-49c1-a480-1249c9f57a13
caps.latest.revision: 11
ms.openlocfilehash: 7fd431b4b1ddecd3a7358c2bf97f299b97162b34
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362001"
---
# <a name="selectionsetname-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="6692e-102">ListControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6692e-102">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="6692e-103">リストエントリの一連の .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="6692e-103">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="6692e-104">エントリに指定できる選択セットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="6692e-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="6692e-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (形式) ListEntries Element (format) ListEntry Element (format) ListEntry (Format) SelectionSetName Element for Element (書式)ListEntry の EntrySelectedBy (形式)</span><span class="sxs-lookup"><span data-stu-id="6692e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6692e-106">構文</span><span class="sxs-lookup"><span data-stu-id="6692e-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6692e-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="6692e-107">Attributes and Elements</span></span>

<span data-ttu-id="6692e-108">次のセクションでは、`SelectionSetName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6692e-108">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6692e-109">属性</span><span class="sxs-lookup"><span data-stu-id="6692e-109">Attributes</span></span>

<span data-ttu-id="6692e-110">なし。</span><span class="sxs-lookup"><span data-stu-id="6692e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6692e-111">子要素</span><span class="sxs-lookup"><span data-stu-id="6692e-111">Child Elements</span></span>

<span data-ttu-id="6692e-112">なし。</span><span class="sxs-lookup"><span data-stu-id="6692e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6692e-113">親要素</span><span class="sxs-lookup"><span data-stu-id="6692e-113">Parent Elements</span></span>

|<span data-ttu-id="6692e-114">要素</span><span class="sxs-lookup"><span data-stu-id="6692e-114">Element</span></span>|<span data-ttu-id="6692e-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="6692e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6692e-116">ListEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="6692e-116">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="6692e-117">このリストエントリを使用する .NET 型、またはこのエントリが使用されるために存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="6692e-117">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6692e-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="6692e-118">Text Value</span></span>

<span data-ttu-id="6692e-119">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6692e-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="6692e-120">コメント</span><span class="sxs-lookup"><span data-stu-id="6692e-120">Remarks</span></span>

<span data-ttu-id="6692e-121">各リストエントリには、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6692e-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="6692e-122">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="6692e-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="6692e-123">たとえば、同じオブジェクトのセットに対してテーブルビューとリストビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="6692e-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="6692e-124">選択セットの定義の詳細については、「[ビューのオブジェクトセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6692e-124">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="6692e-125">リストビューのコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6692e-125">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="6692e-126">例</span><span class="sxs-lookup"><span data-stu-id="6692e-126">Example</span></span>

<span data-ttu-id="6692e-127">次の例では、リストビューのエントリの選択セットを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6692e-127">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="6692e-128">参照</span><span class="sxs-lookup"><span data-stu-id="6692e-128">See Also</span></span>

[<span data-ttu-id="6692e-129">リストビューの作成</span><span class="sxs-lookup"><span data-stu-id="6692e-129">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="6692e-130">ListEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="6692e-130">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="6692e-131">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="6692e-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
