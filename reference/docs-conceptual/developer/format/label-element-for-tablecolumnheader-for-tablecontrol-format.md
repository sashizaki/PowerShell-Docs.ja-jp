---
ms.date: 09/13/2016
ms.topic: reference
title: TableControl の TableColumnHeader の Label 要素 (書式)
description: TableControl の TableColumnHeader の Label 要素 (書式)
ms.openlocfilehash: fe4c209903c04e683b44e2bdcbf381adb6874ace
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667795"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="ee925-103">TableControl の TableColumnHeader の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ee925-103">Label Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="ee925-104">列の上部に表示されるラベルを定義します。</span><span class="sxs-lookup"><span data-stu-id="ee925-104">Defines the label that is displayed at the top of a column.</span></span> <span data-ttu-id="ee925-105">この要素は、テーブルビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ee925-105">This element is used when defining a table view.</span></span>

<span data-ttu-id="ee925-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素の tablecontrol (format) TableColumnHeader for tablecontrol (format) Label Element for tablecontrol (Format) の TableColumnHeader 要素</span><span class="sxs-lookup"><span data-stu-id="ee925-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format) Label Element  for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ee925-107">構文</span><span class="sxs-lookup"><span data-stu-id="ee925-107">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="ee925-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ee925-108">Attributes and Elements</span></span>

<span data-ttu-id="ee925-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `Label` ます。</span><span class="sxs-lookup"><span data-stu-id="ee925-109">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span> <span data-ttu-id="ee925-110">各列に対して使用できるラベルは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="ee925-110">Only one label is allowed for each column.</span></span>

### <a name="attributes"></a><span data-ttu-id="ee925-111">属性</span><span class="sxs-lookup"><span data-stu-id="ee925-111">Attributes</span></span>

<span data-ttu-id="ee925-112">なし。</span><span class="sxs-lookup"><span data-stu-id="ee925-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ee925-113">子要素</span><span class="sxs-lookup"><span data-stu-id="ee925-113">Child Elements</span></span>

<span data-ttu-id="ee925-114">なし。</span><span class="sxs-lookup"><span data-stu-id="ee925-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ee925-115">親要素</span><span class="sxs-lookup"><span data-stu-id="ee925-115">Parent Elements</span></span>

|<span data-ttu-id="ee925-116">要素</span><span class="sxs-lookup"><span data-stu-id="ee925-116">Element</span></span>|<span data-ttu-id="ee925-117">説明</span><span class="sxs-lookup"><span data-stu-id="ee925-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ee925-118">TableControl の TableHeaders の TableColumnHeader 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ee925-118">TableColumnHeader Element for TableHeaders for TableControl  (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="ee925-119">テーブルの列のデータのラベル、幅、および配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="ee925-119">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ee925-120">テキスト値</span><span class="sxs-lookup"><span data-stu-id="ee925-120">Text Value</span></span>

<span data-ttu-id="ee925-121">テーブルの列の上部に表示されるテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="ee925-121">Specify the text that is displayed at the top of the column of the table.</span></span> <span data-ttu-id="ee925-122">列ラベルに使用できる文字は制限されていません。</span><span class="sxs-lookup"><span data-stu-id="ee925-122">There are no restricted characters for the column label.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee925-123">解説</span><span class="sxs-lookup"><span data-stu-id="ee925-123">Remarks</span></span>

<span data-ttu-id="ee925-124">ラベルが指定されていない場合は、行に表示される値を持つプロパティの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ee925-124">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>

<span data-ttu-id="ee925-125">テーブルビューのコンポーネントの詳細については、「 [テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee925-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ee925-126">例</span><span class="sxs-lookup"><span data-stu-id="ee925-126">Example</span></span>

<span data-ttu-id="ee925-127">この例で `TableColumnHeader` は、ラベルが "Column 1" である要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="ee925-127">This example shows a `TableColumnHeader` element whose label is "Column 1".</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="ee925-128">参照</span><span class="sxs-lookup"><span data-stu-id="ee925-128">See Also</span></span>

[<span data-ttu-id="ee925-129">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="ee925-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="ee925-130">TableColumnHeader 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ee925-130">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="ee925-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="ee925-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
