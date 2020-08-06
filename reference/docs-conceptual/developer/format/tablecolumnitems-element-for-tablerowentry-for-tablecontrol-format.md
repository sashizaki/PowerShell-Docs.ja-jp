---
title: TableControl (Format) の TableRowEntry の TableColumnItems 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 661b938e8db0e68e10dc05f552e4f3a14608bc55
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785151"
---
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a><span data-ttu-id="45baa-102">TableControl の TableRowEntry の TableColumnItems 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="45baa-102">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>

<span data-ttu-id="45baa-103">値が行内に表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="45baa-103">Defines the properties or scripts whose values are displayed in a row.</span></span>

<span data-ttu-id="45baa-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries 要素の tablecontrol (format) TableRowEntry 要素の TableRowEntries for TableControl (Format) TableColumnItems Element for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="45baa-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="45baa-105">構文</span><span class="sxs-lookup"><span data-stu-id="45baa-105">Syntax</span></span>

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="45baa-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="45baa-106">Attributes and Elements</span></span>

<span data-ttu-id="45baa-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `TableColumnItems` ます。</span><span class="sxs-lookup"><span data-stu-id="45baa-107">The following sections describe the attributes, child elements, and parent element of the `TableColumnItems` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="45baa-108">属性</span><span class="sxs-lookup"><span data-stu-id="45baa-108">Attributes</span></span>

<span data-ttu-id="45baa-109">なし。</span><span class="sxs-lookup"><span data-stu-id="45baa-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="45baa-110">子要素</span><span class="sxs-lookup"><span data-stu-id="45baa-110">Child Elements</span></span>

|<span data-ttu-id="45baa-111">要素</span><span class="sxs-lookup"><span data-stu-id="45baa-111">Element</span></span>|<span data-ttu-id="45baa-112">説明</span><span class="sxs-lookup"><span data-stu-id="45baa-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="45baa-113">TableControl の TableColumnItems の TableColumnItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="45baa-113">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="45baa-114">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="45baa-114">Required element.</span></span><br /><br /> <span data-ttu-id="45baa-115">行の列に値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="45baa-115">Defines the property or script whose value is displayed in a column of the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="45baa-116">親要素</span><span class="sxs-lookup"><span data-stu-id="45baa-116">Parent Elements</span></span>

|<span data-ttu-id="45baa-117">要素</span><span class="sxs-lookup"><span data-stu-id="45baa-117">Element</span></span>|<span data-ttu-id="45baa-118">説明</span><span class="sxs-lookup"><span data-stu-id="45baa-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="45baa-119">TableControl の TableRowEntries の TableRowEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="45baa-119">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="45baa-120">テーブルの行に表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="45baa-120">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="45baa-121">解説</span><span class="sxs-lookup"><span data-stu-id="45baa-121">Remarks</span></span>

<span data-ttu-id="45baa-122">`TableColumnItem`行の各列には要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="45baa-122">A `TableColumnItem` element is required for each column of the row.</span></span> <span data-ttu-id="45baa-123">最初のエントリは最初の列に、2番目の列には2番目のエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45baa-123">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

<span data-ttu-id="45baa-124">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45baa-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="45baa-125">例</span><span class="sxs-lookup"><span data-stu-id="45baa-125">Example</span></span>

<span data-ttu-id="45baa-126">次の例は、 `TableColumnItems` system.object オブジェクトの3つのプロパティ[System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)を定義する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="45baa-126">The following example shows a `TableColumnItems` element that defines three properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItems>
  <TableColumnItem>
    <PropertyName>Status</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>Name</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>DisplayName</PropertyName>
  </TableColumnItem>
</TableColumnItems>

```

## <a name="see-also"></a><span data-ttu-id="45baa-127">参照</span><span class="sxs-lookup"><span data-stu-id="45baa-127">See Also</span></span>

[<span data-ttu-id="45baa-128">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="45baa-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="45baa-129">TableColumnItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="45baa-129">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="45baa-130">TableRowEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="45baa-130">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="45baa-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="45baa-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
