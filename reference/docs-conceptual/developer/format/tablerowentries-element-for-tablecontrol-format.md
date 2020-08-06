---
title: TableControl (Format) の TableRowEntries 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4cc5d354df3e552e181a95148caa020f0041db92
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785117"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a><span data-ttu-id="8f1b4-102">TableControl の TableRowEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8f1b4-102">TableRowEntries Element for TableControl (Format)</span></span>

<span data-ttu-id="8f1b4-103">テーブルの行を定義します。</span><span class="sxs-lookup"><span data-stu-id="8f1b4-103">Defines the rows of the table.</span></span>

<span data-ttu-id="8f1b4-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries 要素 (format)</span><span class="sxs-lookup"><span data-stu-id="8f1b4-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8f1b4-105">構文</span><span class="sxs-lookup"><span data-stu-id="8f1b4-105">Syntax</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8f1b4-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8f1b4-106">Attributes and Elements</span></span>

<span data-ttu-id="8f1b4-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `TableRowEntries` ます。</span><span class="sxs-lookup"><span data-stu-id="8f1b4-107">The following sections describe the attributes, child elements, and parent element of the `TableRowEntries` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8f1b4-108">属性</span><span class="sxs-lookup"><span data-stu-id="8f1b4-108">Attributes</span></span>

<span data-ttu-id="8f1b4-109">なし。</span><span class="sxs-lookup"><span data-stu-id="8f1b4-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8f1b4-110">子要素</span><span class="sxs-lookup"><span data-stu-id="8f1b4-110">Child Elements</span></span>

|<span data-ttu-id="8f1b4-111">要素</span><span class="sxs-lookup"><span data-stu-id="8f1b4-111">Element</span></span>|<span data-ttu-id="8f1b4-112">説明</span><span class="sxs-lookup"><span data-stu-id="8f1b4-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8f1b4-113">TableControl の TableRowEntries の TableRowEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8f1b4-113">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="8f1b4-114">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="8f1b4-114">Required element.</span></span><br /><br /> <span data-ttu-id="8f1b4-115">テーブルの行に表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="8f1b4-115">Defines the data that is displayed in a row of the table.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8f1b4-116">親要素</span><span class="sxs-lookup"><span data-stu-id="8f1b4-116">Parent Elements</span></span>

|<span data-ttu-id="8f1b4-117">要素</span><span class="sxs-lookup"><span data-stu-id="8f1b4-117">Element</span></span>|<span data-ttu-id="8f1b4-118">説明</span><span class="sxs-lookup"><span data-stu-id="8f1b4-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8f1b4-119">TableControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8f1b4-119">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="8f1b4-120">ビューのテーブル形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="8f1b4-120">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8f1b4-121">解説</span><span class="sxs-lookup"><span data-stu-id="8f1b4-121">Remarks</span></span>

<span data-ttu-id="8f1b4-122">テーブルビューには1つ以上の要素を指定する必要があり `TableRowEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="8f1b4-122">You must specify one or more `TableRowEntry` elements for the table view.</span></span> <span data-ttu-id="8f1b4-123">追加できる要素の数に上限はありません `TableRowEntry` 。また、順序が重要でもありません。</span><span class="sxs-lookup"><span data-stu-id="8f1b4-123">There is no maximum limit to the number of `TableRowEntry` elements that can be added nor is their order significant.</span></span>

<span data-ttu-id="8f1b4-124">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f1b4-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="8f1b4-125">例</span><span class="sxs-lookup"><span data-stu-id="8f1b4-125">Example</span></span>

<span data-ttu-id="8f1b4-126">次の例は、system.string `TableRowEntries` オブジェクトの2つのプロパティの値を表示する行を[System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)定義する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="8f1b4-126">The following example shows a `TableRowEntries` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8f1b4-127">参照</span><span class="sxs-lookup"><span data-stu-id="8f1b4-127">See Also</span></span>

[<span data-ttu-id="8f1b4-128">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="8f1b4-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="8f1b4-129">TableControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8f1b4-129">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="8f1b4-130">TableRowEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="8f1b4-130">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="8f1b4-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="8f1b4-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
