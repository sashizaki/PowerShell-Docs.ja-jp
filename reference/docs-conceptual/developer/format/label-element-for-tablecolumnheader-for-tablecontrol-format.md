---
title: TableControl (Format) の TableColumnHeader の Label 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: b7b1d6825d3bca0e36b230415d19c2ac48377a46
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785746"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="70a00-102">TableControl の TableColumnHeader の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="70a00-102">Label Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="70a00-103">列の上部に表示されるラベルを定義します。</span><span class="sxs-lookup"><span data-stu-id="70a00-103">Defines the label that is displayed at the top of a column.</span></span> <span data-ttu-id="70a00-104">この要素は、テーブルビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="70a00-104">This element is used when defining a table view.</span></span>

<span data-ttu-id="70a00-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素の tablecontrol (format) TableColumnHeader for tablecontrol (format) Label Element for tablecontrol (Format) の TableColumnHeader 要素</span><span class="sxs-lookup"><span data-stu-id="70a00-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format) Label Element  for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="70a00-106">構文</span><span class="sxs-lookup"><span data-stu-id="70a00-106">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="70a00-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="70a00-107">Attributes and Elements</span></span>

<span data-ttu-id="70a00-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `Label` ます。</span><span class="sxs-lookup"><span data-stu-id="70a00-108">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span> <span data-ttu-id="70a00-109">各列に対して使用できるラベルは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="70a00-109">Only one label is allowed for each column.</span></span>

### <a name="attributes"></a><span data-ttu-id="70a00-110">属性</span><span class="sxs-lookup"><span data-stu-id="70a00-110">Attributes</span></span>

<span data-ttu-id="70a00-111">なし。</span><span class="sxs-lookup"><span data-stu-id="70a00-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="70a00-112">子要素</span><span class="sxs-lookup"><span data-stu-id="70a00-112">Child Elements</span></span>

<span data-ttu-id="70a00-113">なし。</span><span class="sxs-lookup"><span data-stu-id="70a00-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="70a00-114">親要素</span><span class="sxs-lookup"><span data-stu-id="70a00-114">Parent Elements</span></span>

|<span data-ttu-id="70a00-115">要素</span><span class="sxs-lookup"><span data-stu-id="70a00-115">Element</span></span>|<span data-ttu-id="70a00-116">説明</span><span class="sxs-lookup"><span data-stu-id="70a00-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="70a00-117">TableControl の TableHeaders の TableColumnHeader 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="70a00-117">TableColumnHeader Element for TableHeaders for TableControl  (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="70a00-118">テーブルの列のデータのラベル、幅、および配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="70a00-118">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="70a00-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="70a00-119">Text Value</span></span>

<span data-ttu-id="70a00-120">テーブルの列の上部に表示されるテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="70a00-120">Specify the text that is displayed at the top of the column of the table.</span></span> <span data-ttu-id="70a00-121">列ラベルに使用できる文字は制限されていません。</span><span class="sxs-lookup"><span data-stu-id="70a00-121">There are no restricted characters for the column label.</span></span>

## <a name="remarks"></a><span data-ttu-id="70a00-122">解説</span><span class="sxs-lookup"><span data-stu-id="70a00-122">Remarks</span></span>

<span data-ttu-id="70a00-123">ラベルが指定されていない場合は、行に表示される値を持つプロパティの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="70a00-123">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>

<span data-ttu-id="70a00-124">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70a00-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="70a00-125">例</span><span class="sxs-lookup"><span data-stu-id="70a00-125">Example</span></span>

<span data-ttu-id="70a00-126">この例で `TableColumnHeader` は、ラベルが "Column 1" である要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="70a00-126">This example shows a `TableColumnHeader` element whose label is "Column 1".</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="70a00-127">参照</span><span class="sxs-lookup"><span data-stu-id="70a00-127">See Also</span></span>

[<span data-ttu-id="70a00-128">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="70a00-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="70a00-129">TableColumnHeader 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="70a00-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="70a00-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="70a00-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
