---
title: TableControl (Format) の TableRowEntry の TableColumnItems 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d43684ce-7c3d-4d14-8dbd-061c111ee805
caps.latest.revision: 12
ms.openlocfilehash: d05437aaa9652e7f81d0854d1a746acffe145699
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361811"
---
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a><span data-ttu-id="30e2b-102">TableControl の TableRowEntry の TableColumnItems 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="30e2b-102">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>

<span data-ttu-id="30e2b-103">値が行内に表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="30e2b-103">Defines the properties or scripts whose values are displayed in a row.</span></span>

<span data-ttu-id="30e2b-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries の TableControl (format) TableRowEntry 要素の TableRowEntries for TableControl (Format)TableControl (Format) の TableControlEntry の TableColumnItems 要素</span><span class="sxs-lookup"><span data-stu-id="30e2b-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="30e2b-105">構文</span><span class="sxs-lookup"><span data-stu-id="30e2b-105">Syntax</span></span>

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="30e2b-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="30e2b-106">Attributes and Elements</span></span>

<span data-ttu-id="30e2b-107">次のセクションでは、`TableColumnItems` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="30e2b-107">The following sections describe the attributes, child elements, and parent element of the `TableColumnItems` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="30e2b-108">属性</span><span class="sxs-lookup"><span data-stu-id="30e2b-108">Attributes</span></span>

<span data-ttu-id="30e2b-109">なし。</span><span class="sxs-lookup"><span data-stu-id="30e2b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="30e2b-110">子要素</span><span class="sxs-lookup"><span data-stu-id="30e2b-110">Child Elements</span></span>

|<span data-ttu-id="30e2b-111">要素</span><span class="sxs-lookup"><span data-stu-id="30e2b-111">Element</span></span>|<span data-ttu-id="30e2b-112">説明</span><span class="sxs-lookup"><span data-stu-id="30e2b-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="30e2b-113">TableControl (Format) の TableColumnItems の TableColumnItem 要素</span><span class="sxs-lookup"><span data-stu-id="30e2b-113">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="30e2b-114">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="30e2b-114">Required element.</span></span><br /><br /> <span data-ttu-id="30e2b-115">行の列に値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="30e2b-115">Defines the property or script whose value is displayed in a column of the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="30e2b-116">親要素</span><span class="sxs-lookup"><span data-stu-id="30e2b-116">Parent Elements</span></span>

|<span data-ttu-id="30e2b-117">要素</span><span class="sxs-lookup"><span data-stu-id="30e2b-117">Element</span></span>|<span data-ttu-id="30e2b-118">説明</span><span class="sxs-lookup"><span data-stu-id="30e2b-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="30e2b-119">TableControl (Format) の TableRowEntries の TableRowEntry 要素</span><span class="sxs-lookup"><span data-stu-id="30e2b-119">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="30e2b-120">テーブルの行に表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="30e2b-120">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="30e2b-121">コメント</span><span class="sxs-lookup"><span data-stu-id="30e2b-121">Remarks</span></span>

<span data-ttu-id="30e2b-122">行の各列には、`TableColumnItem` 要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="30e2b-122">A `TableColumnItem` element is required for each column of the row.</span></span> <span data-ttu-id="30e2b-123">最初のエントリは最初の列に、2番目の列には2番目のエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="30e2b-123">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

<span data-ttu-id="30e2b-124">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30e2b-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="30e2b-125">例</span><span class="sxs-lookup"><span data-stu-id="30e2b-125">Example</span></span>

<span data-ttu-id="30e2b-126">次の例は[、system.object オブジェクト](/dotnet/api/System.Diagnostics.Process)の3つのプロパティを定義する `TableColumnItems` 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="30e2b-126">The following example shows a `TableColumnItems` element that defines three properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="30e2b-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="30e2b-127">See Also</span></span>

[<span data-ttu-id="30e2b-128">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="30e2b-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="30e2b-129">TableColumnItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="30e2b-129">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="30e2b-130">TableRowEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="30e2b-130">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="30e2b-131">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="30e2b-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
