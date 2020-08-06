---
title: TableControl (Format) の TableRowEntries の TableRowEntry 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 83076ae5b2c48992ce5e621c65fc9937efb68b87
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787412"
---
# <a name="tablerowentry-element-for-tablerowentries-for-tablecontrol-format"></a><span data-ttu-id="44202-102">TableControl の TableRowEntries の TableRowEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="44202-102">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>

<span data-ttu-id="44202-103">テーブルの行に表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="44202-103">Defines the data that is displayed in a row of the table.</span></span>

<span data-ttu-id="44202-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries の TableControl (format) TableRowEntry 要素の TableRowEntries for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="44202-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="44202-105">構文</span><span class="sxs-lookup"><span data-stu-id="44202-105">Syntax</span></span>

```xml
<TableRowEntry>
  <Wrap/>
  <EntrySelectedBy>...</EntrySelectedBy>
  <TableColumnItems>...</TableColumnItems>
</TableRowEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="44202-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="44202-106">Attributes and Elements</span></span>

<span data-ttu-id="44202-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `TableRowEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="44202-107">The following sections describe attributes, child elements, and parent element of the `TableRowEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="44202-108">属性</span><span class="sxs-lookup"><span data-stu-id="44202-108">Attributes</span></span>

<span data-ttu-id="44202-109">なし。</span><span class="sxs-lookup"><span data-stu-id="44202-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="44202-110">子要素</span><span class="sxs-lookup"><span data-stu-id="44202-110">Child Elements</span></span>

|<span data-ttu-id="44202-111">要素</span><span class="sxs-lookup"><span data-stu-id="44202-111">Element</span></span>|<span data-ttu-id="44202-112">説明</span><span class="sxs-lookup"><span data-stu-id="44202-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="44202-113">TableControl (Format) の TableRowEntry の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="44202-113">EntrySelectedBy Element for TableRowEntry for TableControl (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="44202-114">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="44202-114">Required element.</span></span><br /><br /> <span data-ttu-id="44202-115">プロパティ値が行内に表示されるオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="44202-115">Defines the objects whose property values are displayed in the row.</span></span>|
|[<span data-ttu-id="44202-116">TableControl の TableRowEntry の TableColumnItems 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="44202-116">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="44202-117">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="44202-117">Required element.</span></span><br /><br /> <span data-ttu-id="44202-118">値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="44202-118">Defines the properties or scripts whose values are displayed.</span></span>|
|[<span data-ttu-id="44202-119">TableControl (Format) の TableRowEntry の Wrap 要素</span><span class="sxs-lookup"><span data-stu-id="44202-119">Wrap Element for TableRowEntry for TableControl (Format)</span></span>](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="44202-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="44202-120">Optional element.</span></span><br /><br /> <span data-ttu-id="44202-121">列幅を超えるテキストを次の行に表示するように指定します。</span><span class="sxs-lookup"><span data-stu-id="44202-121">Specifies that text that exceeds the column width is displayed on the next line.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="44202-122">親要素</span><span class="sxs-lookup"><span data-stu-id="44202-122">Parent Elements</span></span>

|<span data-ttu-id="44202-123">要素</span><span class="sxs-lookup"><span data-stu-id="44202-123">Element</span></span>|<span data-ttu-id="44202-124">説明</span><span class="sxs-lookup"><span data-stu-id="44202-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="44202-125">TableControl の TableRowEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="44202-125">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)|<span data-ttu-id="44202-126">テーブルの行を定義します。</span><span class="sxs-lookup"><span data-stu-id="44202-126">Defines the rows of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="44202-127">解説</span><span class="sxs-lookup"><span data-stu-id="44202-127">Remarks</span></span>

<span data-ttu-id="44202-128">1つ `TableColumnItems` の要素と1つの `EntrySelectedBy` 要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44202-128">One `TableColumnItems` element and one `EntrySelectedBy` element must be specified.</span></span>

<span data-ttu-id="44202-129">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44202-129">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="44202-130">例</span><span class="sxs-lookup"><span data-stu-id="44202-130">Example</span></span>

<span data-ttu-id="44202-131">次の例は、system.string `TableRowEntry` オブジェクトの2つのプロパティの値を表示する行を[System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)定義する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="44202-131">The following example shows a `TableRowEntry` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="44202-132">参照</span><span class="sxs-lookup"><span data-stu-id="44202-132">See Also</span></span>

[<span data-ttu-id="44202-133">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="44202-133">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="44202-134">TableControl (Format) の TableRowEntry の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="44202-134">EntrySelectedBy Element for TableRowEntry for TableControl (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="44202-135">TableControl の TableRowEntry の TableColumnItems 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="44202-135">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="44202-136">TableControl の TableRowEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="44202-136">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)

[<span data-ttu-id="44202-137">TableControl (Format) の TableRowEntry の Wrap 要素</span><span class="sxs-lookup"><span data-stu-id="44202-137">Wrap Element for TableRowEntry for TableControl (Format)</span></span>](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="44202-138">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="44202-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
