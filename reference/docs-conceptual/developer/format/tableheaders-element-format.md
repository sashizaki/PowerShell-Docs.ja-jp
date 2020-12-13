---
ms.date: 09/13/2016
ms.topic: reference
title: TableHeaders 要素 (Format)
description: TableHeaders 要素 (Format)
ms.openlocfilehash: 5ac4dccae746c167ebf95add9f3d18030a2b3a99
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659819"
---
# <a name="tableheaders-element-format"></a><span data-ttu-id="d2e76-103">TableHeaders 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="d2e76-103">TableHeaders Element (Format)</span></span>

<span data-ttu-id="d2e76-104">テーブルの列のヘッダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="d2e76-104">Defines the headers for the columns of a table.</span></span>

<span data-ttu-id="d2e76-105">ViewDefinitions 要素 (Format) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="d2e76-105">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d2e76-106">構文</span><span class="sxs-lookup"><span data-stu-id="d2e76-106">Syntax</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="d2e76-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d2e76-107">Attributes and Elements</span></span>

<span data-ttu-id="d2e76-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `TableHeaders` ます。</span><span class="sxs-lookup"><span data-stu-id="d2e76-108">The following sections describe the attributes, child elements, and parent elements of the `TableHeaders` element.</span></span> <span data-ttu-id="d2e76-109">表示されるオブジェクトの各プロパティには、子要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="d2e76-109">There must be a child element for each property of the object that is to be displayed.</span></span> <span data-ttu-id="d2e76-110">列ヘッダー情報は、子要素が指定されている順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="d2e76-110">The column header information is displayed in the order that the child elements are specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="d2e76-111">属性</span><span class="sxs-lookup"><span data-stu-id="d2e76-111">Attributes</span></span>

<span data-ttu-id="d2e76-112">なし。</span><span class="sxs-lookup"><span data-stu-id="d2e76-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d2e76-113">子要素</span><span class="sxs-lookup"><span data-stu-id="d2e76-113">Child Elements</span></span>

|<span data-ttu-id="d2e76-114">要素</span><span class="sxs-lookup"><span data-stu-id="d2e76-114">Element</span></span>|<span data-ttu-id="d2e76-115">説明</span><span class="sxs-lookup"><span data-stu-id="d2e76-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d2e76-116">TableColumnHeader 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d2e76-116">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="d2e76-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d2e76-117">Optional element.</span></span><br /><br /> <span data-ttu-id="d2e76-118">テーブルビューの列のデータのラベル、幅、および配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="d2e76-118">Defines the label, the width, and the alignment of the data for a column of a table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d2e76-119">親要素</span><span class="sxs-lookup"><span data-stu-id="d2e76-119">Parent Elements</span></span>

|<span data-ttu-id="d2e76-120">要素</span><span class="sxs-lookup"><span data-stu-id="d2e76-120">Element</span></span>|<span data-ttu-id="d2e76-121">説明</span><span class="sxs-lookup"><span data-stu-id="d2e76-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d2e76-122">TableControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d2e76-122">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="d2e76-123">ビューのテーブル形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="d2e76-123">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d2e76-124">解説</span><span class="sxs-lookup"><span data-stu-id="d2e76-124">Remarks</span></span>

<span data-ttu-id="d2e76-125">テーブルビューのコンポーネントの詳細については、「 [テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2e76-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="d2e76-126">例</span><span class="sxs-lookup"><span data-stu-id="d2e76-126">Example</span></span>

<span data-ttu-id="d2e76-127">次の例は、 `TableHeaders` 2 つの列ヘッダーを定義する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="d2e76-127">This example shows a `TableHeaders` element that defines two column headers.</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>
    <Label>Column 1</Label)
    <Width>16</Width>
    <Alignment>Left</Alignment>
  </TableColumnHeader>
  <TableColumnHeader>
    <Label>Column 2</Label)
    <Width>10</Width>
    <Alignment>Centered</Alignment>
  </TableColumnHeader>
</TableHeaders>
```

## <a name="see-also"></a><span data-ttu-id="d2e76-128">参照</span><span class="sxs-lookup"><span data-stu-id="d2e76-128">See Also</span></span>

[<span data-ttu-id="d2e76-129">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="d2e76-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="d2e76-130">TableColumnHeader 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d2e76-130">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="d2e76-131">TableControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d2e76-131">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="d2e76-132">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="d2e76-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
