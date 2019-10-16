---
title: TableControl の EntrySelectedBy の TypeName 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd872ada-d476-4c4d-a788-ccac3f983070
caps.latest.revision: 10
ms.openlocfilehash: 7bbb47268a23fcb37a34e2287a6ce949313a13bb
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361631"
---
# <a name="typename-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="b23e9-102">TableControl の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b23e9-102">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="b23e9-103">テーブルビューのこのエントリを使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="b23e9-103">Specifies a .NET type that uses this entry of the table view.</span></span> <span data-ttu-id="b23e9-104">テーブルエントリに指定できる型の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="b23e9-104">There is no limit to the number of types that can be specified for a table entry.</span></span>

<span data-ttu-id="b23e9-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) EntrySelectedBy Element (Format) の TypeName 要素TableRowEntry の場合 (形式)</span><span class="sxs-lookup"><span data-stu-id="b23e9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) TypeName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b23e9-106">構文</span><span class="sxs-lookup"><span data-stu-id="b23e9-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b23e9-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="b23e9-107">Attributes and Elements</span></span>

<span data-ttu-id="b23e9-108">次のセクションでは、属性、子要素、`TypeName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b23e9-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b23e9-109">属性</span><span class="sxs-lookup"><span data-stu-id="b23e9-109">Attributes</span></span>

<span data-ttu-id="b23e9-110">なし。</span><span class="sxs-lookup"><span data-stu-id="b23e9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b23e9-111">子要素</span><span class="sxs-lookup"><span data-stu-id="b23e9-111">Child Elements</span></span>

<span data-ttu-id="b23e9-112">なし。</span><span class="sxs-lookup"><span data-stu-id="b23e9-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b23e9-113">親要素</span><span class="sxs-lookup"><span data-stu-id="b23e9-113">Parent Elements</span></span>

|<span data-ttu-id="b23e9-114">要素</span><span class="sxs-lookup"><span data-stu-id="b23e9-114">Element</span></span>|<span data-ttu-id="b23e9-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="b23e9-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b23e9-116">EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="b23e9-116">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="b23e9-117">このエントリを使用する .NET 型、またはこのエントリが使用されるために存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="b23e9-117">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b23e9-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="b23e9-118">Text Value</span></span>

<span data-ttu-id="b23e9-119">.NET 型の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b23e9-119">Specify the name of the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="b23e9-120">コメント</span><span class="sxs-lookup"><span data-stu-id="b23e9-120">Remarks</span></span>

<span data-ttu-id="b23e9-121">各リストエントリには、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b23e9-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="b23e9-122">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b23e9-122">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b23e9-123">参照</span><span class="sxs-lookup"><span data-stu-id="b23e9-123">See Also</span></span>

[<span data-ttu-id="b23e9-124">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="b23e9-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="b23e9-125">EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="b23e9-125">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="b23e9-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="b23e9-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
