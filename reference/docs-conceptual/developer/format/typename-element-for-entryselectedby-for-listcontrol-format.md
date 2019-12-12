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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361661"
---
# <a name="typename-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="88cb4-102">ListControl の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="88cb4-102">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="88cb4-103">リストビューのこのエントリを使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="88cb4-103">Specifies a .NET type that uses this entry of the list view.</span></span> <span data-ttu-id="88cb4-104">リストエントリに指定できる型の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="88cb4-104">There is no limit to the number of types that can be specified for a list entry.</span></span>

<span data-ttu-id="88cb4-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries Element (format) ListEntry Element (format) ListEntry (Format) TypeName 要素の (format) EntrySelectedBy ElementListControl の EntrySelectedBy (形式)</span><span class="sxs-lookup"><span data-stu-id="88cb4-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="88cb4-106">構文</span><span class="sxs-lookup"><span data-stu-id="88cb4-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="88cb4-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="88cb4-107">Attributes and Elements</span></span>

<span data-ttu-id="88cb4-108">次のセクションでは、`TypeName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="88cb4-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="88cb4-109">属性</span><span class="sxs-lookup"><span data-stu-id="88cb4-109">Attributes</span></span>

<span data-ttu-id="88cb4-110">なし。</span><span class="sxs-lookup"><span data-stu-id="88cb4-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="88cb4-111">子要素</span><span class="sxs-lookup"><span data-stu-id="88cb4-111">Child Elements</span></span>

<span data-ttu-id="88cb4-112">なし。</span><span class="sxs-lookup"><span data-stu-id="88cb4-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="88cb4-113">親要素</span><span class="sxs-lookup"><span data-stu-id="88cb4-113">Parent Elements</span></span>

|<span data-ttu-id="88cb4-114">要素</span><span class="sxs-lookup"><span data-stu-id="88cb4-114">Element</span></span>|<span data-ttu-id="88cb4-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="88cb4-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="88cb4-116">ListEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="88cb4-116">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="88cb4-117">このリストエントリを使用する .NET 型、またはこのエントリが使用されるために存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="88cb4-117">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="88cb4-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="88cb4-118">Text Value</span></span>

<span data-ttu-id="88cb4-119">`System.IO.DirectoryInfo`など、.NET 型の完全修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="88cb4-119">Specify the fully-qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="88cb4-120">コメント</span><span class="sxs-lookup"><span data-stu-id="88cb4-120">Remarks</span></span>

<span data-ttu-id="88cb4-121">各リストエントリには、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="88cb4-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="88cb4-122">リストビューでのこの要素の使用方法の詳細については、「[リストビュー](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88cb4-122">For more information about how this element is used in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="88cb4-123">例</span><span class="sxs-lookup"><span data-stu-id="88cb4-123">Example</span></span>

<span data-ttu-id="88cb4-124">次の例では、リストビューのエントリの選択セットを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="88cb4-124">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>Nameof.NetType</TypeName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="88cb4-125">参照</span><span class="sxs-lookup"><span data-stu-id="88cb4-125">See Also</span></span>

[<span data-ttu-id="88cb4-126">リストビューの作成</span><span class="sxs-lookup"><span data-stu-id="88cb4-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="88cb4-127">ListEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="88cb4-127">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="88cb4-128">ListEntry (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="88cb4-128">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="88cb4-129">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="88cb4-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
