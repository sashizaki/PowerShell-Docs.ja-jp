---
title: TableHeaders 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9fa2b6f-b99a-42de-9779-44e9cb583f71
caps.latest.revision: 15
ms.openlocfilehash: bd44fcf4878c858afe81fb071ce72f627ac465dc
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361821"
---
# <a name="tableheaders-element-format"></a><span data-ttu-id="2c37c-102">TableHeaders 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="2c37c-102">TableHeaders Element (Format)</span></span>

<span data-ttu-id="2c37c-103">テーブルの列のヘッダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="2c37c-103">Defines the headers for the columns of a table.</span></span>

<span data-ttu-id="2c37c-104">ViewDefinitions 要素 (Format) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="2c37c-104">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2c37c-105">構文</span><span class="sxs-lookup"><span data-stu-id="2c37c-105">Syntax</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="2c37c-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="2c37c-106">Attributes and Elements</span></span>

<span data-ttu-id="2c37c-107">次のセクションでは、`TableHeaders` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c37c-107">The following sections describe the attributes, child elements, and parent elements of the `TableHeaders` element.</span></span> <span data-ttu-id="2c37c-108">表示されるオブジェクトの各プロパティには、子要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="2c37c-108">There must be a child element for each property of the object that is to be displayed.</span></span> <span data-ttu-id="2c37c-109">列ヘッダー情報は、子要素が指定されている順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c37c-109">The column header information is displayed in the order that the child elements are specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="2c37c-110">属性</span><span class="sxs-lookup"><span data-stu-id="2c37c-110">Attributes</span></span>

<span data-ttu-id="2c37c-111">なし。</span><span class="sxs-lookup"><span data-stu-id="2c37c-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2c37c-112">子要素</span><span class="sxs-lookup"><span data-stu-id="2c37c-112">Child Elements</span></span>

|<span data-ttu-id="2c37c-113">要素</span><span class="sxs-lookup"><span data-stu-id="2c37c-113">Element</span></span>|<span data-ttu-id="2c37c-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="2c37c-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2c37c-115">TableColumnHeader 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="2c37c-115">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="2c37c-116">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="2c37c-116">Optional element.</span></span><br /><br /> <span data-ttu-id="2c37c-117">テーブルビューの列のデータのラベル、幅、および配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="2c37c-117">Defines the label, the width, and the alignment of the data for a column of a table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2c37c-118">親要素</span><span class="sxs-lookup"><span data-stu-id="2c37c-118">Parent Elements</span></span>

|<span data-ttu-id="2c37c-119">要素</span><span class="sxs-lookup"><span data-stu-id="2c37c-119">Element</span></span>|<span data-ttu-id="2c37c-120">[説明]</span><span class="sxs-lookup"><span data-stu-id="2c37c-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2c37c-121">TableControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="2c37c-121">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="2c37c-122">ビューのテーブル形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="2c37c-122">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2c37c-123">コメント</span><span class="sxs-lookup"><span data-stu-id="2c37c-123">Remarks</span></span>

<span data-ttu-id="2c37c-124">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c37c-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="2c37c-125">例</span><span class="sxs-lookup"><span data-stu-id="2c37c-125">Example</span></span>

<span data-ttu-id="2c37c-126">この例は、2つの列ヘッダーを定義する @no__t 0 の要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="2c37c-126">This example shows a `TableHeaders` element that defines two column headers.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2c37c-127">参照</span><span class="sxs-lookup"><span data-stu-id="2c37c-127">See Also</span></span>

[<span data-ttu-id="2c37c-128">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="2c37c-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="2c37c-129">TableColumnHeader 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="2c37c-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="2c37c-130">TableControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="2c37c-130">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="2c37c-131">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="2c37c-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
