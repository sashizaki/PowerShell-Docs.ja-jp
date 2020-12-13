---
ms.date: 09/13/2016
ms.topic: reference
title: TableControl の TableRowEntries 要素 (書式)
description: TableControl の TableRowEntries 要素 (書式)
ms.openlocfilehash: 1df63e645234da8276c7ccc5af34e81a56475e43
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651481"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a><span data-ttu-id="aa3db-103">TableControl の TableRowEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="aa3db-103">TableRowEntries Element for TableControl (Format)</span></span>

<span data-ttu-id="aa3db-104">テーブルの行を定義します。</span><span class="sxs-lookup"><span data-stu-id="aa3db-104">Defines the rows of the table.</span></span>

<span data-ttu-id="aa3db-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries 要素 (format)</span><span class="sxs-lookup"><span data-stu-id="aa3db-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="aa3db-106">構文</span><span class="sxs-lookup"><span data-stu-id="aa3db-106">Syntax</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="aa3db-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="aa3db-107">Attributes and Elements</span></span>

<span data-ttu-id="aa3db-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `TableRowEntries` ます。</span><span class="sxs-lookup"><span data-stu-id="aa3db-108">The following sections describe the attributes, child elements, and parent element of the `TableRowEntries` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="aa3db-109">属性</span><span class="sxs-lookup"><span data-stu-id="aa3db-109">Attributes</span></span>

<span data-ttu-id="aa3db-110">なし。</span><span class="sxs-lookup"><span data-stu-id="aa3db-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="aa3db-111">子要素</span><span class="sxs-lookup"><span data-stu-id="aa3db-111">Child Elements</span></span>

|<span data-ttu-id="aa3db-112">要素</span><span class="sxs-lookup"><span data-stu-id="aa3db-112">Element</span></span>|<span data-ttu-id="aa3db-113">説明</span><span class="sxs-lookup"><span data-stu-id="aa3db-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aa3db-114">TableControl の TableRowEntries の TableRowEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="aa3db-114">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="aa3db-115">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="aa3db-115">Required element.</span></span><br /><br /> <span data-ttu-id="aa3db-116">テーブルの行に表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="aa3db-116">Defines the data that is displayed in a row of the table.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="aa3db-117">親要素</span><span class="sxs-lookup"><span data-stu-id="aa3db-117">Parent Elements</span></span>

|<span data-ttu-id="aa3db-118">要素</span><span class="sxs-lookup"><span data-stu-id="aa3db-118">Element</span></span>|<span data-ttu-id="aa3db-119">説明</span><span class="sxs-lookup"><span data-stu-id="aa3db-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aa3db-120">TableControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="aa3db-120">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="aa3db-121">ビューのテーブル形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="aa3db-121">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="aa3db-122">解説</span><span class="sxs-lookup"><span data-stu-id="aa3db-122">Remarks</span></span>

<span data-ttu-id="aa3db-123">テーブルビューには1つ以上の要素を指定する必要があり `TableRowEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="aa3db-123">You must specify one or more `TableRowEntry` elements for the table view.</span></span> <span data-ttu-id="aa3db-124">追加できる要素の数に上限はありません `TableRowEntry` 。また、順序が重要でもありません。</span><span class="sxs-lookup"><span data-stu-id="aa3db-124">There is no maximum limit to the number of `TableRowEntry` elements that can be added nor is their order significant.</span></span>

<span data-ttu-id="aa3db-125">テーブルビューのコンポーネントの詳細については、「 [テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa3db-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="aa3db-126">例</span><span class="sxs-lookup"><span data-stu-id="aa3db-126">Example</span></span>

<span data-ttu-id="aa3db-127">次の例は、system.string `TableRowEntries` オブジェクトの2つのプロパティの値を表示する行を[](/dotnet/api/System.Diagnostics.Process)定義する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="aa3db-127">The following example shows a `TableRowEntries` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="aa3db-128">参照</span><span class="sxs-lookup"><span data-stu-id="aa3db-128">See Also</span></span>

[<span data-ttu-id="aa3db-129">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="aa3db-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="aa3db-130">TableControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="aa3db-130">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="aa3db-131">TableRowEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="aa3db-131">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="aa3db-132">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="aa3db-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
