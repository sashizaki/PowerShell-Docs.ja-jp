---
title: TableControl (Format) の TableColumnHeader の Label 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7196f039-2f6a-41fd-b252-5b1623ebb9f9
caps.latest.revision: 11
ms.openlocfilehash: 09183a538c179f19347c3f1ed45b4ad38c2ca451
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365171"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="fed17-102">TableControl の TableColumnHeader の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="fed17-102">Label Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="fed17-103">列の上部に表示されるラベルを定義します。</span><span class="sxs-lookup"><span data-stu-id="fed17-103">Defines the label that is displayed at the top of a column.</span></span> <span data-ttu-id="fed17-104">この要素は、テーブルビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="fed17-104">This element is used when defining a table view.</span></span>

<span data-ttu-id="fed17-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素の tablecontrol (format) TableColumnHeader 要素の tablecontrol (Format) ラベル要素のTableControl (Format) の TableColumnHeader</span><span class="sxs-lookup"><span data-stu-id="fed17-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format) Label Element  for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fed17-106">構文</span><span class="sxs-lookup"><span data-stu-id="fed17-106">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="fed17-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="fed17-107">Attributes and Elements</span></span>

<span data-ttu-id="fed17-108">次のセクションでは、`Label` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fed17-108">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span> <span data-ttu-id="fed17-109">各列に対して使用できるラベルは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="fed17-109">Only one label is allowed for each column.</span></span>

### <a name="attributes"></a><span data-ttu-id="fed17-110">属性</span><span class="sxs-lookup"><span data-stu-id="fed17-110">Attributes</span></span>

<span data-ttu-id="fed17-111">なし。</span><span class="sxs-lookup"><span data-stu-id="fed17-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fed17-112">子要素</span><span class="sxs-lookup"><span data-stu-id="fed17-112">Child Elements</span></span>

<span data-ttu-id="fed17-113">なし。</span><span class="sxs-lookup"><span data-stu-id="fed17-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fed17-114">親要素</span><span class="sxs-lookup"><span data-stu-id="fed17-114">Parent Elements</span></span>

|<span data-ttu-id="fed17-115">要素</span><span class="sxs-lookup"><span data-stu-id="fed17-115">Element</span></span>|<span data-ttu-id="fed17-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="fed17-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fed17-117">TableControl の TableHeaders の TableColumnHeader 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="fed17-117">TableColumnHeader Element for TableHeaders for TableControl  (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="fed17-118">テーブルの列のデータのラベル、幅、および配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="fed17-118">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fed17-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="fed17-119">Text Value</span></span>

<span data-ttu-id="fed17-120">テーブルの列の上部に表示されるテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="fed17-120">Specify the text that is displayed at the top of the column of the table.</span></span> <span data-ttu-id="fed17-121">列ラベルに使用できる文字は制限されていません。</span><span class="sxs-lookup"><span data-stu-id="fed17-121">There are no restricted characters for the column label.</span></span>

## <a name="remarks"></a><span data-ttu-id="fed17-122">コメント</span><span class="sxs-lookup"><span data-stu-id="fed17-122">Remarks</span></span>

<span data-ttu-id="fed17-123">ラベルが指定されていない場合は、行に表示される値を持つプロパティの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="fed17-123">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>

<span data-ttu-id="fed17-124">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fed17-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="fed17-125">例</span><span class="sxs-lookup"><span data-stu-id="fed17-125">Example</span></span>

<span data-ttu-id="fed17-126">この例では、ラベルが "Column 1" である @no__t 0 の要素を示します。</span><span class="sxs-lookup"><span data-stu-id="fed17-126">This example shows a `TableColumnHeader` element whose label is "Column 1".</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="fed17-127">参照</span><span class="sxs-lookup"><span data-stu-id="fed17-127">See Also</span></span>

[<span data-ttu-id="fed17-128">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="fed17-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="fed17-129">TableColumnHeader 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="fed17-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="fed17-130">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="fed17-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
