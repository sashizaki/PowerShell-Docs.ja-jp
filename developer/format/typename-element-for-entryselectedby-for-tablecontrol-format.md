---
title: TableControl (形式) の EntrySelectedBy の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd872ada-d476-4c4d-a788-ccac3f983070
caps.latest.revision: 10
ms.openlocfilehash: 7bbb47268a23fcb37a34e2287a6ce949313a13bb
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855728"
---
# <a name="typename-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="6f6e9-102">TableControl の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6f6e9-102">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="6f6e9-103">テーブル ビューのこのエントリを使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f6e9-103">Specifies a .NET type that uses this entry of the table view.</span></span> <span data-ttu-id="6f6e9-104">テーブルのエントリに指定できる型の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="6f6e9-104">There is no limit to the number of types that can be specified for a table entry.</span></span>

<span data-ttu-id="6f6e9-105">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素 (形式) TableRowEntry 要素 (形式) EntrySelectedBy 要素 (形式) TypeName の構成要素 EntrySelectedByTableRowEntry (形式) の</span><span class="sxs-lookup"><span data-stu-id="6f6e9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) TypeName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6f6e9-106">構文</span><span class="sxs-lookup"><span data-stu-id="6f6e9-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6f6e9-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="6f6e9-107">Attributes and Elements</span></span>

<span data-ttu-id="6f6e9-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。</span><span class="sxs-lookup"><span data-stu-id="6f6e9-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6f6e9-109">属性</span><span class="sxs-lookup"><span data-stu-id="6f6e9-109">Attributes</span></span>

<span data-ttu-id="6f6e9-110">なし。</span><span class="sxs-lookup"><span data-stu-id="6f6e9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6f6e9-111">子要素</span><span class="sxs-lookup"><span data-stu-id="6f6e9-111">Child Elements</span></span>

<span data-ttu-id="6f6e9-112">なし。</span><span class="sxs-lookup"><span data-stu-id="6f6e9-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6f6e9-113">親要素</span><span class="sxs-lookup"><span data-stu-id="6f6e9-113">Parent Elements</span></span>

|<span data-ttu-id="6f6e9-114">要素</span><span class="sxs-lookup"><span data-stu-id="6f6e9-114">Element</span></span>|<span data-ttu-id="6f6e9-115">説明</span><span class="sxs-lookup"><span data-stu-id="6f6e9-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6f6e9-116">EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="6f6e9-116">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="6f6e9-117">このエントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="6f6e9-117">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6f6e9-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="6f6e9-118">Text Value</span></span>

<span data-ttu-id="6f6e9-119">.NET 型の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f6e9-119">Specify the name of the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="6f6e9-120">コメント</span><span class="sxs-lookup"><span data-stu-id="6f6e9-120">Remarks</span></span>

<span data-ttu-id="6f6e9-121">リストの各エントリに少なくとも 1 つの型名、選択範囲のセット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f6e9-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="6f6e9-122">テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="6f6e9-122">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6f6e9-123">参照</span><span class="sxs-lookup"><span data-stu-id="6f6e9-123">See Also</span></span>

[<span data-ttu-id="6f6e9-124">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="6f6e9-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="6f6e9-125">EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="6f6e9-125">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="6f6e9-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="6f6e9-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
