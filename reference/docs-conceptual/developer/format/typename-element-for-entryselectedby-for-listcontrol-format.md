---
title: ListControl (Format) の EntrySelectedBy の TypeName 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5e7b73db5aa597d96141454008c5c58b1827df24
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780221"
---
# <a name="typename-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="c85fd-102">ListControl の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c85fd-102">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="c85fd-103">リストビューのこのエントリを使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="c85fd-103">Specifies a .NET type that uses this entry of the list view.</span></span> <span data-ttu-id="c85fd-104">リストエントリに指定できる型の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="c85fd-104">There is no limit to the number of types that can be specified for a list entry.</span></span>

<span data-ttu-id="c85fd-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries Element (format) ListEntry Element (format) ListEntry (Format) の (format) TypeName 要素の EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="c85fd-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c85fd-106">構文</span><span class="sxs-lookup"><span data-stu-id="c85fd-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c85fd-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c85fd-107">Attributes and Elements</span></span>

<span data-ttu-id="c85fd-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="c85fd-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c85fd-109">属性</span><span class="sxs-lookup"><span data-stu-id="c85fd-109">Attributes</span></span>

<span data-ttu-id="c85fd-110">なし。</span><span class="sxs-lookup"><span data-stu-id="c85fd-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c85fd-111">子要素</span><span class="sxs-lookup"><span data-stu-id="c85fd-111">Child Elements</span></span>

<span data-ttu-id="c85fd-112">なし。</span><span class="sxs-lookup"><span data-stu-id="c85fd-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c85fd-113">親要素</span><span class="sxs-lookup"><span data-stu-id="c85fd-113">Parent Elements</span></span>

|<span data-ttu-id="c85fd-114">要素</span><span class="sxs-lookup"><span data-stu-id="c85fd-114">Element</span></span>|<span data-ttu-id="c85fd-115">説明</span><span class="sxs-lookup"><span data-stu-id="c85fd-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c85fd-116">ListEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c85fd-116">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="c85fd-117">このリストエントリを使用する .NET 型、またはこのエントリが使用されるために存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="c85fd-117">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c85fd-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="c85fd-118">Text Value</span></span>

<span data-ttu-id="c85fd-119">.NET 型の完全修飾名を指定します (例 `System.IO.DirectoryInfo` :)。</span><span class="sxs-lookup"><span data-stu-id="c85fd-119">Specify the fully-qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c85fd-120">解説</span><span class="sxs-lookup"><span data-stu-id="c85fd-120">Remarks</span></span>

<span data-ttu-id="c85fd-121">各リストエントリには、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c85fd-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="c85fd-122">リストビューでのこの要素の使用方法の詳細については、「[リストビュー](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c85fd-122">For more information about how this element is used in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="c85fd-123">例</span><span class="sxs-lookup"><span data-stu-id="c85fd-123">Example</span></span>

<span data-ttu-id="c85fd-124">次の例では、リストビューのエントリの選択セットを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c85fd-124">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>Nameof.NetType</TypeName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="c85fd-125">参照</span><span class="sxs-lookup"><span data-stu-id="c85fd-125">See Also</span></span>

[<span data-ttu-id="c85fd-126">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="c85fd-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="c85fd-127">ListEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c85fd-127">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="c85fd-128">ListEntry (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="c85fd-128">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="c85fd-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="c85fd-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
