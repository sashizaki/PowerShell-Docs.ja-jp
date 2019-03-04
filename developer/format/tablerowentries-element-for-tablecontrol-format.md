---
title: TableControl (形式) の要素を TableRowEntries |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d10b68ca-256c-4c58-b503-73f7777b39ae
caps.latest.revision: 15
ms.openlocfilehash: d93750f919c1075f173dc9ac70324cc003e36879
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862188"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a><span data-ttu-id="7bb3a-102">TableControl の TableRowEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7bb3a-102">TableRowEntries Element for TableControl (Format)</span></span>

<span data-ttu-id="7bb3a-103">テーブルの行を定義します。</span><span class="sxs-lookup"><span data-stu-id="7bb3a-103">Defines the rows of the table.</span></span>

<span data-ttu-id="7bb3a-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素を TableControl (形式)</span><span class="sxs-lookup"><span data-stu-id="7bb3a-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7bb3a-105">構文</span><span class="sxs-lookup"><span data-stu-id="7bb3a-105">Syntax</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7bb3a-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="7bb3a-106">Attributes and Elements</span></span>

<span data-ttu-id="7bb3a-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`TableRowEntries`要素。</span><span class="sxs-lookup"><span data-stu-id="7bb3a-107">The following sections describe the attributes, child elements, and parent element of the `TableRowEntries` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7bb3a-108">属性</span><span class="sxs-lookup"><span data-stu-id="7bb3a-108">Attributes</span></span>

<span data-ttu-id="7bb3a-109">なし。</span><span class="sxs-lookup"><span data-stu-id="7bb3a-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7bb3a-110">子要素</span><span class="sxs-lookup"><span data-stu-id="7bb3a-110">Child Elements</span></span>

|<span data-ttu-id="7bb3a-111">要素</span><span class="sxs-lookup"><span data-stu-id="7bb3a-111">Element</span></span>|<span data-ttu-id="7bb3a-112">説明</span><span class="sxs-lookup"><span data-stu-id="7bb3a-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7bb3a-113">TableControl (形式) の TableRowEntries TableRowEntry 要素</span><span class="sxs-lookup"><span data-stu-id="7bb3a-113">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md)|<span data-ttu-id="7bb3a-114">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="7bb3a-114">Required element.</span></span><br /><br /> <span data-ttu-id="7bb3a-115">テーブルの行に表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="7bb3a-115">Defines the data that is displayed in a row of the table.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7bb3a-116">親要素</span><span class="sxs-lookup"><span data-stu-id="7bb3a-116">Parent Elements</span></span>

|<span data-ttu-id="7bb3a-117">要素</span><span class="sxs-lookup"><span data-stu-id="7bb3a-117">Element</span></span>|<span data-ttu-id="7bb3a-118">説明</span><span class="sxs-lookup"><span data-stu-id="7bb3a-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7bb3a-119">TableControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7bb3a-119">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="7bb3a-120">ビューのテーブル形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="7bb3a-120">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7bb3a-121">コメント</span><span class="sxs-lookup"><span data-stu-id="7bb3a-121">Remarks</span></span>

<span data-ttu-id="7bb3a-122">1 つ以上を指定する必要があります`TableRowEntry`テーブル ビューの要素。</span><span class="sxs-lookup"><span data-stu-id="7bb3a-122">You must specify one or more `TableRowEntry` elements for the table view.</span></span> <span data-ttu-id="7bb3a-123">数に上限はありません`TableRowEntry`追加できる要素の順序は重要ではもします。</span><span class="sxs-lookup"><span data-stu-id="7bb3a-123">There is no maximum limit to the number of `TableRowEntry` elements that can be added nor is their order significant.</span></span>

<span data-ttu-id="7bb3a-124">テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="7bb3a-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="7bb3a-125">例</span><span class="sxs-lookup"><span data-stu-id="7bb3a-125">Example</span></span>

<span data-ttu-id="7bb3a-126">次の例は、`TableRowEntries`の 2 つのプロパティの値を表示する行を定義する要素、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7bb3a-126">The following example shows a `TableRowEntries` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>
    <EntrySelectedBy>
      <TypeName>System.Diagnostics.Process</TypeName>
    </EntrySelectedBy>
    <TableColumnItems>
      <TableColumnItem>
        <PropertyName> Property for first column</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName> Property for second column</PropertyName>
      </TableColumnItem>
    </TableColumnItems>
  </TableRowEntry>
</TableRowEntries>

```

## <a name="see-also"></a><span data-ttu-id="7bb3a-127">参照</span><span class="sxs-lookup"><span data-stu-id="7bb3a-127">See Also</span></span>

[<span data-ttu-id="7bb3a-128">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="7bb3a-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="7bb3a-129">TableControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7bb3a-129">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="7bb3a-130">TableRowEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7bb3a-130">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md)

[<span data-ttu-id="7bb3a-131">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="7bb3a-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
