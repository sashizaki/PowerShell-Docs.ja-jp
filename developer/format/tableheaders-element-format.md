---
title: TableHeaders 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9fa2b6f-b99a-42de-9779-44e9cb583f71
caps.latest.revision: 15
ms.openlocfilehash: bd44fcf4878c858afe81fb071ce72f627ac465dc
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62075411"
---
# <a name="tableheaders-element-format"></a><span data-ttu-id="b2590-102">TableHeaders 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="b2590-102">TableHeaders Element (Format)</span></span>

<span data-ttu-id="b2590-103">テーブルの列のヘッダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="b2590-103">Defines the headers for the columns of a table.</span></span>

<span data-ttu-id="b2590-104">TableControl (形式) の表示要素 (形式) TableControl 要素 (形式) の TableHeaders 要素 ViewDefinitions 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="b2590-104">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b2590-105">構文</span><span class="sxs-lookup"><span data-stu-id="b2590-105">Syntax</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="b2590-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b2590-106">Attributes and Elements</span></span>

<span data-ttu-id="b2590-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`TableHeaders`要素。</span><span class="sxs-lookup"><span data-stu-id="b2590-107">The following sections describe the attributes, child elements, and parent elements of the `TableHeaders` element.</span></span> <span data-ttu-id="b2590-108">各プロパティが表示されるオブジェクトの子要素があります。</span><span class="sxs-lookup"><span data-stu-id="b2590-108">There must be a child element for each property of the object that is to be displayed.</span></span> <span data-ttu-id="b2590-109">列のヘッダー情報は、子要素が指定されている順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2590-109">The column header information is displayed in the order that the child elements are specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="b2590-110">属性</span><span class="sxs-lookup"><span data-stu-id="b2590-110">Attributes</span></span>

<span data-ttu-id="b2590-111">なし。</span><span class="sxs-lookup"><span data-stu-id="b2590-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b2590-112">子要素</span><span class="sxs-lookup"><span data-stu-id="b2590-112">Child Elements</span></span>

|<span data-ttu-id="b2590-113">要素</span><span class="sxs-lookup"><span data-stu-id="b2590-113">Element</span></span>|<span data-ttu-id="b2590-114">説明</span><span class="sxs-lookup"><span data-stu-id="b2590-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b2590-115">TableColumnHeader 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="b2590-115">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="b2590-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="b2590-116">Optional element.</span></span><br /><br /> <span data-ttu-id="b2590-117">ラベル、幅、およびテーブル ビューの列のデータの配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="b2590-117">Defines the label, the width, and the alignment of the data for a column of a table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b2590-118">親要素</span><span class="sxs-lookup"><span data-stu-id="b2590-118">Parent Elements</span></span>

|<span data-ttu-id="b2590-119">要素</span><span class="sxs-lookup"><span data-stu-id="b2590-119">Element</span></span>|<span data-ttu-id="b2590-120">説明</span><span class="sxs-lookup"><span data-stu-id="b2590-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b2590-121">TableControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="b2590-121">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="b2590-122">ビューのテーブル形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="b2590-122">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b2590-123">コメント</span><span class="sxs-lookup"><span data-stu-id="b2590-123">Remarks</span></span>

<span data-ttu-id="b2590-124">テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="b2590-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="b2590-125">例</span><span class="sxs-lookup"><span data-stu-id="b2590-125">Example</span></span>

<span data-ttu-id="b2590-126">この例では、 `TableHeaders` 2 つの列ヘッダーを定義する要素。</span><span class="sxs-lookup"><span data-stu-id="b2590-126">This example shows a `TableHeaders` element that defines two column headers.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b2590-127">参照</span><span class="sxs-lookup"><span data-stu-id="b2590-127">See Also</span></span>

[<span data-ttu-id="b2590-128">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2590-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="b2590-129">TableColumnHeader 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="b2590-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="b2590-130">TableControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="b2590-130">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="b2590-131">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="b2590-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
