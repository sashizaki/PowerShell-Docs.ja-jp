---
ms.date: 09/13/2016
ms.topic: reference
title: TableControl の TableColumnHeader の Width 要素 (書式)
description: TableControl の TableColumnHeader の Width 要素 (書式)
ms.openlocfilehash: bde84f1d33b3d6b3b8c4462f870f978611cb434b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658249"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="2dfbc-103">TableControl の TableColumnHeader の Width 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2dfbc-103">Width Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="2dfbc-104">列の幅 (文字数) を定義します。</span><span class="sxs-lookup"><span data-stu-id="2dfbc-104">Defines the width (in characters) of a column.</span></span>

<span data-ttu-id="2dfbc-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素 tablecontrol (format) TableColumnHeader 要素 TableHeaders for tablecontrol (format) TableColumnHeader for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="2dfbc-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element TableHeaders for TableControl (Format) Width Element for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2dfbc-106">構文</span><span class="sxs-lookup"><span data-stu-id="2dfbc-106">Syntax</span></span>

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2dfbc-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2dfbc-107">Attributes and Elements</span></span>

<span data-ttu-id="2dfbc-108">以下のセクションでは、 `Width` 列ヘッダーを定義するときに使用する要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2dfbc-108">The following sections describe the attributes, child elements, and parent element of the `Width` element used when defining column headers.</span></span>

### <a name="attributes"></a><span data-ttu-id="2dfbc-109">属性</span><span class="sxs-lookup"><span data-stu-id="2dfbc-109">Attributes</span></span>

<span data-ttu-id="2dfbc-110">なし。</span><span class="sxs-lookup"><span data-stu-id="2dfbc-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2dfbc-111">子要素</span><span class="sxs-lookup"><span data-stu-id="2dfbc-111">Child Elements</span></span>

<span data-ttu-id="2dfbc-112">なし。</span><span class="sxs-lookup"><span data-stu-id="2dfbc-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2dfbc-113">親要素</span><span class="sxs-lookup"><span data-stu-id="2dfbc-113">Parent Elements</span></span>

|<span data-ttu-id="2dfbc-114">要素</span><span class="sxs-lookup"><span data-stu-id="2dfbc-114">Element</span></span>|<span data-ttu-id="2dfbc-115">説明</span><span class="sxs-lookup"><span data-stu-id="2dfbc-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2dfbc-116">TableControl の TableHeaders の TableColumnHeader 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="2dfbc-116">TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="2dfbc-117">テーブルの列のデータのラベル、幅、および配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="2dfbc-117">Defines a label, width, and alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2dfbc-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="2dfbc-118">Text Value</span></span>

<span data-ttu-id="2dfbc-119">可能な限り、表示されるプロパティ値の長さを超える幅 (文字数) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2dfbc-119">When at all possible, specify a width (in characters) that is greater than the length of the displayed property values.</span></span>

## <a name="remarks"></a><span data-ttu-id="2dfbc-120">解説</span><span class="sxs-lookup"><span data-stu-id="2dfbc-120">Remarks</span></span>

<span data-ttu-id="2dfbc-121">テーブルビューのコンポーネントの詳細については、「 [テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dfbc-121">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="2dfbc-122">例</span><span class="sxs-lookup"><span data-stu-id="2dfbc-122">Example</span></span>

<span data-ttu-id="2dfbc-123">次の例は、 `TableColumnHeader` 幅が16文字の要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="2dfbc-123">The following example shows a `TableColumnHeader` element whose width is 16 characters.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="2dfbc-124">参照</span><span class="sxs-lookup"><span data-stu-id="2dfbc-124">See Also</span></span>

[<span data-ttu-id="2dfbc-125">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="2dfbc-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="2dfbc-126">TableControl の TableHeader の TableColumnHeader 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="2dfbc-126">TableColumnHeader Element for TableHeader for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="2dfbc-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="2dfbc-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
