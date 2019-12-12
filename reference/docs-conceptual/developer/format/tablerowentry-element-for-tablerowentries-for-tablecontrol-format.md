---
title: TableControl (Format) の TableRowEntries の TableRowEntry 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18d86af7-7ff9-4968-81be-2caa61937d49
caps.latest.revision: 10
ms.openlocfilehash: 946ffb3fe857503c02b9000238a86775969abbd6
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361801"
---
# <a name="tablerowentry-element-for-tablerowentries-for-tablecontrol-format"></a><span data-ttu-id="8fca1-102">TableControl の TableRowEntries の TableRowEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8fca1-102">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>

<span data-ttu-id="8fca1-103">テーブルの行に表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="8fca1-103">Defines the data that is displayed in a row of the table.</span></span>

<span data-ttu-id="8fca1-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries の TableControl (format) TableRowEntry 要素の TableRowEntries for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8fca1-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8fca1-105">構文</span><span class="sxs-lookup"><span data-stu-id="8fca1-105">Syntax</span></span>

```xml
<TableRowEntry>
  <Wrap/>
  <EntrySelectedBy>...</EntrySelectedBy>
  <TableColumnItems>...</TableColumnItems>
</TableRowEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8fca1-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="8fca1-106">Attributes and Elements</span></span>

<span data-ttu-id="8fca1-107">次のセクションでは、`TableRowEntry` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8fca1-107">The following sections describe attributes, child elements, and parent element of the `TableRowEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8fca1-108">属性</span><span class="sxs-lookup"><span data-stu-id="8fca1-108">Attributes</span></span>

<span data-ttu-id="8fca1-109">なし。</span><span class="sxs-lookup"><span data-stu-id="8fca1-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8fca1-110">子要素</span><span class="sxs-lookup"><span data-stu-id="8fca1-110">Child Elements</span></span>

|<span data-ttu-id="8fca1-111">要素</span><span class="sxs-lookup"><span data-stu-id="8fca1-111">Element</span></span>|<span data-ttu-id="8fca1-112">[説明]</span><span class="sxs-lookup"><span data-stu-id="8fca1-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8fca1-113">TableControl (Format) の TableRowEntry の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="8fca1-113">EntrySelectedBy Element for TableRowEntry for TableControl (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="8fca1-114">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="8fca1-114">Required element.</span></span><br /><br /> <span data-ttu-id="8fca1-115">プロパティ値が行内に表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="8fca1-115">Defines the objects whose property values are displayed in the row.</span></span>|
|[<span data-ttu-id="8fca1-116">TableControl (Format) の TableRowEntry の TableColumnItems 要素</span><span class="sxs-lookup"><span data-stu-id="8fca1-116">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="8fca1-117">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="8fca1-117">Required element.</span></span><br /><br /> <span data-ttu-id="8fca1-118">値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="8fca1-118">Defines the properties or scripts whose values are displayed.</span></span>|
|[<span data-ttu-id="8fca1-119">TableControl (Format) の TableRowEntry の Wrap 要素</span><span class="sxs-lookup"><span data-stu-id="8fca1-119">Wrap Element for TableRowEntry for TableControl (Format)</span></span>](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="8fca1-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="8fca1-120">Optional element.</span></span><br /><br /> <span data-ttu-id="8fca1-121">列幅を超えるテキストを次の行に表示するように指定します。</span><span class="sxs-lookup"><span data-stu-id="8fca1-121">Specifies that text that exceeds the column width is displayed on the next line.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8fca1-122">親要素</span><span class="sxs-lookup"><span data-stu-id="8fca1-122">Parent Elements</span></span>

|<span data-ttu-id="8fca1-123">要素</span><span class="sxs-lookup"><span data-stu-id="8fca1-123">Element</span></span>|<span data-ttu-id="8fca1-124">[説明]</span><span class="sxs-lookup"><span data-stu-id="8fca1-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8fca1-125">TableControl (Format) の TableRowEntries 要素</span><span class="sxs-lookup"><span data-stu-id="8fca1-125">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)|<span data-ttu-id="8fca1-126">テーブルの行を定義します。</span><span class="sxs-lookup"><span data-stu-id="8fca1-126">Defines the rows of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8fca1-127">コメント</span><span class="sxs-lookup"><span data-stu-id="8fca1-127">Remarks</span></span>

<span data-ttu-id="8fca1-128">1つの `TableColumnItems` 要素と1つの `EntrySelectedBy` 要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fca1-128">One `TableColumnItems` element and one `EntrySelectedBy` element must be specified.</span></span>

<span data-ttu-id="8fca1-129">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fca1-129">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="8fca1-130">例</span><span class="sxs-lookup"><span data-stu-id="8fca1-130">Example</span></span>

<span data-ttu-id="8fca1-131">次の例は、`TableRowEntry` の2つのプロパティの値を表示する行を定義する要素を示してい[ます。](/dotnet/api/System.Diagnostics.Process)</span><span class="sxs-lookup"><span data-stu-id="8fca1-131">The following example shows a `TableRowEntry` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
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
```

## <a name="see-also"></a><span data-ttu-id="8fca1-132">参照</span><span class="sxs-lookup"><span data-stu-id="8fca1-132">See Also</span></span>

[<span data-ttu-id="8fca1-133">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="8fca1-133">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="8fca1-134">TableControl (Format) の TableRowEntry の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="8fca1-134">EntrySelectedBy Element for TableRowEntry for TableControl (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="8fca1-135">TableControl (Format) の TableRowEntry の TableColumnItems 要素</span><span class="sxs-lookup"><span data-stu-id="8fca1-135">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="8fca1-136">TableControl (Format) の TableRowEntries 要素</span><span class="sxs-lookup"><span data-stu-id="8fca1-136">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)

[<span data-ttu-id="8fca1-137">TableControl (Format) の TableRowEntry の Wrap 要素</span><span class="sxs-lookup"><span data-stu-id="8fca1-137">Wrap Element for TableRowEntry for TableControl (Format)</span></span>](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="8fca1-138">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="8fca1-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
