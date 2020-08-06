---
title: TableControl (Format) の TableColumnHeader の Width 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e9540d3d351041ad7cb98a21bb360ebea7eca117
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779915"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="c1292-102">TableControl の TableColumnHeader の Width 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c1292-102">Width Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="c1292-103">列の幅 (文字数) を定義します。</span><span class="sxs-lookup"><span data-stu-id="c1292-103">Defines the width (in characters) of a column.</span></span>

<span data-ttu-id="c1292-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素 tablecontrol (format) TableColumnHeader 要素 TableHeaders for tablecontrol (format) TableColumnHeader for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="c1292-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element TableHeaders for TableControl (Format) Width Element for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c1292-105">構文</span><span class="sxs-lookup"><span data-stu-id="c1292-105">Syntax</span></span>

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c1292-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c1292-106">Attributes and Elements</span></span>

<span data-ttu-id="c1292-107">以下のセクションでは、 `Width` 列ヘッダーを定義するときに使用する要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c1292-107">The following sections describe the attributes, child elements, and parent element of the `Width` element used when defining column headers.</span></span>

### <a name="attributes"></a><span data-ttu-id="c1292-108">属性</span><span class="sxs-lookup"><span data-stu-id="c1292-108">Attributes</span></span>

<span data-ttu-id="c1292-109">なし。</span><span class="sxs-lookup"><span data-stu-id="c1292-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c1292-110">子要素</span><span class="sxs-lookup"><span data-stu-id="c1292-110">Child Elements</span></span>

<span data-ttu-id="c1292-111">なし。</span><span class="sxs-lookup"><span data-stu-id="c1292-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c1292-112">親要素</span><span class="sxs-lookup"><span data-stu-id="c1292-112">Parent Elements</span></span>

|<span data-ttu-id="c1292-113">要素</span><span class="sxs-lookup"><span data-stu-id="c1292-113">Element</span></span>|<span data-ttu-id="c1292-114">説明</span><span class="sxs-lookup"><span data-stu-id="c1292-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c1292-115">TableControl の TableHeaders の TableColumnHeader 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c1292-115">TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="c1292-116">テーブルの列のデータのラベル、幅、および配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="c1292-116">Defines a label, width, and alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c1292-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="c1292-117">Text Value</span></span>

<span data-ttu-id="c1292-118">可能な限り、表示されるプロパティ値の長さを超える幅 (文字数) を指定します。</span><span class="sxs-lookup"><span data-stu-id="c1292-118">When at all possible, specify a width (in characters) that is greater than the length of the displayed property values.</span></span>

## <a name="remarks"></a><span data-ttu-id="c1292-119">解説</span><span class="sxs-lookup"><span data-stu-id="c1292-119">Remarks</span></span>

<span data-ttu-id="c1292-120">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1292-120">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="c1292-121">例</span><span class="sxs-lookup"><span data-stu-id="c1292-121">Example</span></span>

<span data-ttu-id="c1292-122">次の例は、 `TableColumnHeader` 幅が16文字の要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="c1292-122">The following example shows a `TableColumnHeader` element whose width is 16 characters.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="c1292-123">参照</span><span class="sxs-lookup"><span data-stu-id="c1292-123">See Also</span></span>

[<span data-ttu-id="c1292-124">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="c1292-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="c1292-125">TableControl の TableHeader の TableColumnHeader 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c1292-125">TableColumnHeader Element for TableHeader for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="c1292-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="c1292-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
