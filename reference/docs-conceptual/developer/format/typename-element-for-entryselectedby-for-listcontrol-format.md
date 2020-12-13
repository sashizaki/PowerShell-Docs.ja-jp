---
ms.date: 09/13/2016
ms.topic: reference
title: ListControl の EntrySelectedBy の TypeName 要素 (書式)
description: ListControl の EntrySelectedBy の TypeName 要素 (書式)
ms.openlocfilehash: 6fc5a2385fde3140abbc984e3da6a4dda483b2a8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645666"
---
# <a name="typename-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="ee5b4-103">ListControl の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ee5b4-103">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="ee5b4-104">リストビューのこのエントリを使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="ee5b4-104">Specifies a .NET type that uses this entry of the list view.</span></span> <span data-ttu-id="ee5b4-105">リストエントリに指定できる型の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="ee5b4-105">There is no limit to the number of types that can be specified for a list entry.</span></span>

<span data-ttu-id="ee5b4-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries Element (format) ListEntry Element (format) ListEntry (Format) の (format) TypeName 要素の EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ee5b4-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ee5b4-107">構文</span><span class="sxs-lookup"><span data-stu-id="ee5b4-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ee5b4-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ee5b4-108">Attributes and Elements</span></span>

<span data-ttu-id="ee5b4-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="ee5b4-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ee5b4-110">属性</span><span class="sxs-lookup"><span data-stu-id="ee5b4-110">Attributes</span></span>

<span data-ttu-id="ee5b4-111">なし。</span><span class="sxs-lookup"><span data-stu-id="ee5b4-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ee5b4-112">子要素</span><span class="sxs-lookup"><span data-stu-id="ee5b4-112">Child Elements</span></span>

<span data-ttu-id="ee5b4-113">なし。</span><span class="sxs-lookup"><span data-stu-id="ee5b4-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ee5b4-114">親要素</span><span class="sxs-lookup"><span data-stu-id="ee5b4-114">Parent Elements</span></span>

|<span data-ttu-id="ee5b4-115">要素</span><span class="sxs-lookup"><span data-stu-id="ee5b4-115">Element</span></span>|<span data-ttu-id="ee5b4-116">説明</span><span class="sxs-lookup"><span data-stu-id="ee5b4-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ee5b4-117">ListEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ee5b4-117">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="ee5b4-118">このリストエントリを使用する .NET 型、またはこのエントリが使用されるために存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="ee5b4-118">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ee5b4-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="ee5b4-119">Text Value</span></span>

<span data-ttu-id="ee5b4-120">.NET 型の完全修飾名を指定します (例 `System.IO.DirectoryInfo` :)。</span><span class="sxs-lookup"><span data-stu-id="ee5b4-120">Specify the fully-qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee5b4-121">解説</span><span class="sxs-lookup"><span data-stu-id="ee5b4-121">Remarks</span></span>

<span data-ttu-id="ee5b4-122">各リストエントリには、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee5b4-122">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="ee5b4-123">リストビューでのこの要素の使用方法の詳細については、「 [リストビュー](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee5b4-123">For more information about how this element is used in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ee5b4-124">例</span><span class="sxs-lookup"><span data-stu-id="ee5b4-124">Example</span></span>

<span data-ttu-id="ee5b4-125">次の例では、リストビューのエントリの選択セットを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ee5b4-125">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>Nameof.NetType</TypeName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="ee5b4-126">参照</span><span class="sxs-lookup"><span data-stu-id="ee5b4-126">See Also</span></span>

[<span data-ttu-id="ee5b4-127">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="ee5b4-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="ee5b4-128">ListEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ee5b4-128">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="ee5b4-129">ListEntry (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="ee5b4-129">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="ee5b4-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="ee5b4-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
