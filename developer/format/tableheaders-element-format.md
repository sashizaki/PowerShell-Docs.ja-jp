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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856878"
---
# <a name="tableheaders-element-format"></a><span data-ttu-id="45d16-102">TableHeaders 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="45d16-102">TableHeaders Element (Format)</span></span>

<span data-ttu-id="45d16-103">テーブルの列のヘッダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="45d16-103">Defines the headers for the columns of a table.</span></span>

<span data-ttu-id="45d16-104">TableControl (形式) の表示要素 (形式) TableControl 要素 (形式) の TableHeaders 要素 ViewDefinitions 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="45d16-104">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="45d16-105">構文</span><span class="sxs-lookup"><span data-stu-id="45d16-105">Syntax</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="45d16-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="45d16-106">Attributes and Elements</span></span>

<span data-ttu-id="45d16-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`TableHeaders`要素。</span><span class="sxs-lookup"><span data-stu-id="45d16-107">The following sections describe the attributes, child elements, and parent elements of the `TableHeaders` element.</span></span> <span data-ttu-id="45d16-108">各プロパティが表示されるオブジェクトの子要素があります。</span><span class="sxs-lookup"><span data-stu-id="45d16-108">There must be a child element for each property of the object that is to be displayed.</span></span> <span data-ttu-id="45d16-109">列のヘッダー情報は、子要素が指定されている順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="45d16-109">The column header information is displayed in the order that the child elements are specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="45d16-110">属性</span><span class="sxs-lookup"><span data-stu-id="45d16-110">Attributes</span></span>

<span data-ttu-id="45d16-111">なし。</span><span class="sxs-lookup"><span data-stu-id="45d16-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="45d16-112">子要素</span><span class="sxs-lookup"><span data-stu-id="45d16-112">Child Elements</span></span>

|<span data-ttu-id="45d16-113">要素</span><span class="sxs-lookup"><span data-stu-id="45d16-113">Element</span></span>|<span data-ttu-id="45d16-114">説明</span><span class="sxs-lookup"><span data-stu-id="45d16-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="45d16-115">TableColumnHeader 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="45d16-115">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="45d16-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="45d16-116">Optional element.</span></span><br /><br /> <span data-ttu-id="45d16-117">ラベル、幅、およびテーブル ビューの列のデータの配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="45d16-117">Defines the label, the width, and the alignment of the data for a column of a table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="45d16-118">親要素</span><span class="sxs-lookup"><span data-stu-id="45d16-118">Parent Elements</span></span>

|<span data-ttu-id="45d16-119">要素</span><span class="sxs-lookup"><span data-stu-id="45d16-119">Element</span></span>|<span data-ttu-id="45d16-120">説明</span><span class="sxs-lookup"><span data-stu-id="45d16-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="45d16-121">TableControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="45d16-121">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="45d16-122">ビューのテーブル形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="45d16-122">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="45d16-123">コメント</span><span class="sxs-lookup"><span data-stu-id="45d16-123">Remarks</span></span>

<span data-ttu-id="45d16-124">テーブル ビューのコンポーネントに関する詳細については、[テーブル ビューを作成する](./creating-a-table-view.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45d16-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="45d16-125">例</span><span class="sxs-lookup"><span data-stu-id="45d16-125">Example</span></span>

<span data-ttu-id="45d16-126">この例では、 `TableHeaders` 2 つの列ヘッダーを定義する要素。</span><span class="sxs-lookup"><span data-stu-id="45d16-126">This example shows a `TableHeaders` element that defines two column headers.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="45d16-127">参照</span><span class="sxs-lookup"><span data-stu-id="45d16-127">See Also</span></span>

[<span data-ttu-id="45d16-128">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="45d16-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="45d16-129">TableColumnHeader 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="45d16-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="45d16-130">TableControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="45d16-130">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="45d16-131">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="45d16-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
