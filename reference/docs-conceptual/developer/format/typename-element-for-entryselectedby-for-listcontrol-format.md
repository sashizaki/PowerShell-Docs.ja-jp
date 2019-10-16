---
title: ListControl (Format) の EntrySelectedBy の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33c7345c-b808-4c1e-bd54-cb870b407432
caps.latest.revision: 14
ms.openlocfilehash: 0f7216d4dcc0380bceb47ea7c15b3d4a7e5ceeb2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361661"
---
# <a name="typename-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="919c3-102">ListControl の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="919c3-102">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="919c3-103">リストビューのこのエントリを使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="919c3-103">Specifies a .NET type that uses this entry of the list view.</span></span> <span data-ttu-id="919c3-104">リストエントリに指定できる型の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="919c3-104">There is no limit to the number of types that can be specified for a list entry.</span></span>

<span data-ttu-id="919c3-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries Element (format) ListEntry Element (format) ListEntry (Format) TypeName 要素の (format) EntrySelectedBy ElementListControl の EntrySelectedBy (形式)</span><span class="sxs-lookup"><span data-stu-id="919c3-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="919c3-106">構文</span><span class="sxs-lookup"><span data-stu-id="919c3-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="919c3-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="919c3-107">Attributes and Elements</span></span>

<span data-ttu-id="919c3-108">次のセクションでは、属性、子要素、`TypeName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="919c3-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="919c3-109">属性</span><span class="sxs-lookup"><span data-stu-id="919c3-109">Attributes</span></span>

<span data-ttu-id="919c3-110">なし。</span><span class="sxs-lookup"><span data-stu-id="919c3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="919c3-111">子要素</span><span class="sxs-lookup"><span data-stu-id="919c3-111">Child Elements</span></span>

<span data-ttu-id="919c3-112">なし。</span><span class="sxs-lookup"><span data-stu-id="919c3-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="919c3-113">親要素</span><span class="sxs-lookup"><span data-stu-id="919c3-113">Parent Elements</span></span>

|<span data-ttu-id="919c3-114">要素</span><span class="sxs-lookup"><span data-stu-id="919c3-114">Element</span></span>|<span data-ttu-id="919c3-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="919c3-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="919c3-116">ListEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="919c3-116">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="919c3-117">このリストエントリを使用する .NET 型、またはこのエントリが使用されるために存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="919c3-117">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="919c3-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="919c3-118">Text Value</span></span>

<span data-ttu-id="919c3-119">@No__t-0 など、.NET 型の完全修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="919c3-119">Specify the fully-qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="919c3-120">コメント</span><span class="sxs-lookup"><span data-stu-id="919c3-120">Remarks</span></span>

<span data-ttu-id="919c3-121">各リストエントリには、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="919c3-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="919c3-122">リストビューでのこの要素の使用方法の詳細については、「[リストビュー](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="919c3-122">For more information about how this element is used in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="919c3-123">例</span><span class="sxs-lookup"><span data-stu-id="919c3-123">Example</span></span>

<span data-ttu-id="919c3-124">次の例では、リストビューのエントリの選択セットを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="919c3-124">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>Nameof.NetType</TypeName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="919c3-125">参照</span><span class="sxs-lookup"><span data-stu-id="919c3-125">See Also</span></span>

[<span data-ttu-id="919c3-126">リストビューの作成</span><span class="sxs-lookup"><span data-stu-id="919c3-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="919c3-127">ListEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="919c3-127">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="919c3-128">ListEntry (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="919c3-128">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="919c3-129">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="919c3-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
