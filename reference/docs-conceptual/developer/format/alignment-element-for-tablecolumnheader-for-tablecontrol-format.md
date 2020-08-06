---
title: TableControl (Format) の TableColumnHeader の Alignment 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1bf395b84af90d725c14b2f0ef569f72b5fcc613
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783927"
---
# <a name="alignment-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="a2775-102">TableControl の TableColumnHeader の Alignment 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a2775-102">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="a2775-103">列ヘッダー内のデータを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="a2775-103">Defines how the data in a column header is displayed.</span></span>

<span data-ttu-id="a2775-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素 (format) TableColumnHeader Element (format) Alignment 要素 (format)</span><span class="sxs-lookup"><span data-stu-id="a2775-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element (Format) TableColumnHeader Element (Format) Alignment Element for TableColumnHeader (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a2775-105">構文</span><span class="sxs-lookup"><span data-stu-id="a2775-105">Syntax</span></span>

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a2775-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a2775-106">Attributes and Elements</span></span>

<span data-ttu-id="a2775-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `Alignment` ます。</span><span class="sxs-lookup"><span data-stu-id="a2775-107">The following sections describe the attributes, child elements, and parent element of the `Alignment` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a2775-108">属性</span><span class="sxs-lookup"><span data-stu-id="a2775-108">Attributes</span></span>

<span data-ttu-id="a2775-109">なし。</span><span class="sxs-lookup"><span data-stu-id="a2775-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a2775-110">子要素</span><span class="sxs-lookup"><span data-stu-id="a2775-110">Child Elements</span></span>

<span data-ttu-id="a2775-111">なし。</span><span class="sxs-lookup"><span data-stu-id="a2775-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a2775-112">親要素</span><span class="sxs-lookup"><span data-stu-id="a2775-112">Parent Elements</span></span>

|<span data-ttu-id="a2775-113">要素</span><span class="sxs-lookup"><span data-stu-id="a2775-113">Element</span></span>|<span data-ttu-id="a2775-114">説明</span><span class="sxs-lookup"><span data-stu-id="a2775-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a2775-115">TableColumnHeader 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a2775-115">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="a2775-116">テーブルの列のデータのラベル、幅、および配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="a2775-116">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a2775-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="a2775-117">Text Value</span></span>

<span data-ttu-id="a2775-118">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2775-118">Specify one of the following values.</span></span> <span data-ttu-id="a2775-119">これらの値では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="a2775-119">These values are not case-sensitive.</span></span>

<span data-ttu-id="a2775-120">左揃えこの要素が指定されていない場合は、左側の列に表示されるデータが既定値になります。</span><span class="sxs-lookup"><span data-stu-id="a2775-120">Left Aligns the data displayed in the column on the left This is the default if this element is not specified.</span></span>

<span data-ttu-id="a2775-121">右側の列に表示されるデータを右揃えにします。</span><span class="sxs-lookup"><span data-stu-id="a2775-121">Right Aligns the data displayed in the column on the right.</span></span>

<span data-ttu-id="a2775-122">中央には、列に表示されるデータが中央に配置されます。</span><span class="sxs-lookup"><span data-stu-id="a2775-122">Center Centers the data displayed in the column.</span></span>

## <a name="remarks"></a><span data-ttu-id="a2775-123">解説</span><span class="sxs-lookup"><span data-stu-id="a2775-123">Remarks</span></span>

<span data-ttu-id="a2775-124">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2775-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a2775-125">例</span><span class="sxs-lookup"><span data-stu-id="a2775-125">Example</span></span>

<span data-ttu-id="a2775-126">この例では、 `TableColumnHeader` データが左側に揃えられている要素を示します。</span><span class="sxs-lookup"><span data-stu-id="a2775-126">This example shows a `TableColumnHeader` element whose data is aligned on the left.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="a2775-127">参照</span><span class="sxs-lookup"><span data-stu-id="a2775-127">See Also</span></span>

[<span data-ttu-id="a2775-128">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="a2775-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="a2775-129">TableColumnHeader 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a2775-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="a2775-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="a2775-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
