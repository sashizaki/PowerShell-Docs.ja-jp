---
title: TableControl (Format) の TableRowEntries 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d10b68ca-256c-4c58-b503-73f7777b39ae
caps.latest.revision: 15
ms.openlocfilehash: 88de19be02de4933f892e02093403a82ccdd5788
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368151"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a><span data-ttu-id="e37de-102">TableControl の TableRowEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e37de-102">TableRowEntries Element for TableControl (Format)</span></span>

<span data-ttu-id="e37de-103">テーブルの行を定義します。</span><span class="sxs-lookup"><span data-stu-id="e37de-103">Defines the rows of the table.</span></span>

<span data-ttu-id="e37de-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries 要素 (format)</span><span class="sxs-lookup"><span data-stu-id="e37de-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e37de-105">構文</span><span class="sxs-lookup"><span data-stu-id="e37de-105">Syntax</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e37de-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="e37de-106">Attributes and Elements</span></span>

<span data-ttu-id="e37de-107">次のセクションでは、`TableRowEntries` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e37de-107">The following sections describe the attributes, child elements, and parent element of the `TableRowEntries` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e37de-108">属性</span><span class="sxs-lookup"><span data-stu-id="e37de-108">Attributes</span></span>

<span data-ttu-id="e37de-109">なし。</span><span class="sxs-lookup"><span data-stu-id="e37de-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e37de-110">子要素</span><span class="sxs-lookup"><span data-stu-id="e37de-110">Child Elements</span></span>

|<span data-ttu-id="e37de-111">要素</span><span class="sxs-lookup"><span data-stu-id="e37de-111">Element</span></span>|<span data-ttu-id="e37de-112">[説明]</span><span class="sxs-lookup"><span data-stu-id="e37de-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e37de-113">TableControl (Format) の TableRowEntries の TableRowEntry 要素</span><span class="sxs-lookup"><span data-stu-id="e37de-113">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="e37de-114">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="e37de-114">Required element.</span></span><br /><br /> <span data-ttu-id="e37de-115">テーブルの行に表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="e37de-115">Defines the data that is displayed in a row of the table.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e37de-116">親要素</span><span class="sxs-lookup"><span data-stu-id="e37de-116">Parent Elements</span></span>

|<span data-ttu-id="e37de-117">要素</span><span class="sxs-lookup"><span data-stu-id="e37de-117">Element</span></span>|<span data-ttu-id="e37de-118">[説明]</span><span class="sxs-lookup"><span data-stu-id="e37de-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e37de-119">TableControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e37de-119">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="e37de-120">ビューのテーブル形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="e37de-120">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e37de-121">コメント</span><span class="sxs-lookup"><span data-stu-id="e37de-121">Remarks</span></span>

<span data-ttu-id="e37de-122">テーブルビューには1つ以上の @no__t 0 要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e37de-122">You must specify one or more `TableRowEntry` elements for the table view.</span></span> <span data-ttu-id="e37de-123">追加できる @no__t 0 要素の数に上限はありません。また、順序が重要でもありません。</span><span class="sxs-lookup"><span data-stu-id="e37de-123">There is no maximum limit to the number of `TableRowEntry` elements that can be added nor is their order significant.</span></span>

<span data-ttu-id="e37de-124">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e37de-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e37de-125">例</span><span class="sxs-lookup"><span data-stu-id="e37de-125">Example</span></span>

<span data-ttu-id="e37de-126">次の例は、2つのプロパティの値を表示する行を定義する @no__t 0 要素を示してい[ます。](/dotnet/api/System.Diagnostics.Process)</span><span class="sxs-lookup"><span data-stu-id="e37de-126">The following example shows a `TableRowEntries` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e37de-127">参照</span><span class="sxs-lookup"><span data-stu-id="e37de-127">See Also</span></span>

[<span data-ttu-id="e37de-128">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="e37de-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="e37de-129">TableControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e37de-129">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="e37de-130">TableRowEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="e37de-130">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="e37de-131">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="e37de-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
