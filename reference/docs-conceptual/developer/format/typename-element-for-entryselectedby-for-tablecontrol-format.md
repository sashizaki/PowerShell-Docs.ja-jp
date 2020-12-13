---
ms.date: 09/13/2016
ms.topic: reference
title: TableControl の EntrySelectedBy の TypeName 要素 (書式)
description: TableControl の EntrySelectedBy の TypeName 要素 (書式)
ms.openlocfilehash: 5a9f5cda1810d461d19ffb48a1cfa2d41f87ca96
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651429"
---
# <a name="typename-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="3fe0b-103">TableControl の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3fe0b-103">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="3fe0b-104">テーブルビューのこのエントリを使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="3fe0b-104">Specifies a .NET type that uses this entry of the table view.</span></span> <span data-ttu-id="3fe0b-105">テーブルエントリに指定できる型の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="3fe0b-105">There is no limit to the number of types that can be specified for a table entry.</span></span>

<span data-ttu-id="3fe0b-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (format) TableRowEntries Element (format) TableRowEntry Element (format) TableRowEntry の EntrySelectedBy Element (format) TypeName 要素 (format)</span><span class="sxs-lookup"><span data-stu-id="3fe0b-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) TypeName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3fe0b-107">構文</span><span class="sxs-lookup"><span data-stu-id="3fe0b-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3fe0b-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3fe0b-108">Attributes and Elements</span></span>

<span data-ttu-id="3fe0b-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="3fe0b-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3fe0b-110">属性</span><span class="sxs-lookup"><span data-stu-id="3fe0b-110">Attributes</span></span>

<span data-ttu-id="3fe0b-111">なし。</span><span class="sxs-lookup"><span data-stu-id="3fe0b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3fe0b-112">子要素</span><span class="sxs-lookup"><span data-stu-id="3fe0b-112">Child Elements</span></span>

<span data-ttu-id="3fe0b-113">なし。</span><span class="sxs-lookup"><span data-stu-id="3fe0b-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3fe0b-114">親要素</span><span class="sxs-lookup"><span data-stu-id="3fe0b-114">Parent Elements</span></span>

|<span data-ttu-id="3fe0b-115">要素</span><span class="sxs-lookup"><span data-stu-id="3fe0b-115">Element</span></span>|<span data-ttu-id="3fe0b-116">説明</span><span class="sxs-lookup"><span data-stu-id="3fe0b-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3fe0b-117">EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="3fe0b-117">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="3fe0b-118">このエントリを使用する .NET 型、またはこのエントリが使用されるために存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="3fe0b-118">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3fe0b-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="3fe0b-119">Text Value</span></span>

<span data-ttu-id="3fe0b-120">.NET 型の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3fe0b-120">Specify the name of the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="3fe0b-121">解説</span><span class="sxs-lookup"><span data-stu-id="3fe0b-121">Remarks</span></span>

<span data-ttu-id="3fe0b-122">各リストエントリには、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fe0b-122">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="3fe0b-123">テーブルビューのコンポーネントの詳細については、「 [テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fe0b-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3fe0b-124">参照</span><span class="sxs-lookup"><span data-stu-id="3fe0b-124">See Also</span></span>

[<span data-ttu-id="3fe0b-125">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="3fe0b-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="3fe0b-126">EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="3fe0b-126">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="3fe0b-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="3fe0b-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
