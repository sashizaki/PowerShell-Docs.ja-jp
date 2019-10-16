---
title: TableControl (Format) の TableColumnHeader の Alignment 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff85e83a-c9c2-4c37-accc-e6a27c182f3c
caps.latest.revision: 19
ms.openlocfilehash: 16b41535109ca503e679a135f5ba30054e33de5b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364381"
---
# <a name="alignment-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="24807-102">TableControl の TableColumnHeader の Alignment 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="24807-102">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="24807-103">列ヘッダー内のデータを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="24807-103">Defines how the data in a column header is displayed.</span></span>

<span data-ttu-id="24807-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素 (format) TableColumnHeader Element (format) Alignment 要素 (format)</span><span class="sxs-lookup"><span data-stu-id="24807-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element (Format) TableColumnHeader Element (Format) Alignment Element for TableColumnHeader (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="24807-105">構文</span><span class="sxs-lookup"><span data-stu-id="24807-105">Syntax</span></span>

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="24807-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="24807-106">Attributes and Elements</span></span>

<span data-ttu-id="24807-107">次のセクションでは、`Alignment` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="24807-107">The following sections describe the attributes, child elements, and parent element of the `Alignment` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="24807-108">属性</span><span class="sxs-lookup"><span data-stu-id="24807-108">Attributes</span></span>

<span data-ttu-id="24807-109">なし。</span><span class="sxs-lookup"><span data-stu-id="24807-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="24807-110">子要素</span><span class="sxs-lookup"><span data-stu-id="24807-110">Child Elements</span></span>

<span data-ttu-id="24807-111">なし。</span><span class="sxs-lookup"><span data-stu-id="24807-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="24807-112">親要素</span><span class="sxs-lookup"><span data-stu-id="24807-112">Parent Elements</span></span>

|<span data-ttu-id="24807-113">要素</span><span class="sxs-lookup"><span data-stu-id="24807-113">Element</span></span>|<span data-ttu-id="24807-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="24807-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="24807-115">TableColumnHeader 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="24807-115">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="24807-116">テーブルの列のデータのラベル、幅、および配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="24807-116">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="24807-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="24807-117">Text Value</span></span>

<span data-ttu-id="24807-118">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="24807-118">Specify one of the following values.</span></span> <span data-ttu-id="24807-119">これらの値の大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="24807-119">These values are not case-sensitive.</span></span>

<span data-ttu-id="24807-120">左揃えこの要素が指定されていない場合は、左側の列に表示されるデータが既定値になります。</span><span class="sxs-lookup"><span data-stu-id="24807-120">Left Aligns the data displayed in the column on the left This is the default if this element is not specified.</span></span>

<span data-ttu-id="24807-121">右側の列に表示されるデータを右揃えにします。</span><span class="sxs-lookup"><span data-stu-id="24807-121">Right Aligns the data displayed in the column on the right.</span></span>

<span data-ttu-id="24807-122">中央には、列に表示されるデータが中央に配置されます。</span><span class="sxs-lookup"><span data-stu-id="24807-122">Center Centers the data displayed in the column.</span></span>

## <a name="remarks"></a><span data-ttu-id="24807-123">コメント</span><span class="sxs-lookup"><span data-stu-id="24807-123">Remarks</span></span>

<span data-ttu-id="24807-124">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24807-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="24807-125">例</span><span class="sxs-lookup"><span data-stu-id="24807-125">Example</span></span>

<span data-ttu-id="24807-126">この例は、データが左側に揃えられている @no__t 0 の要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="24807-126">This example shows a `TableColumnHeader` element whose data is aligned on the left.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="24807-127">参照</span><span class="sxs-lookup"><span data-stu-id="24807-127">See Also</span></span>

[<span data-ttu-id="24807-128">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="24807-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="24807-129">TableColumnHeader 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="24807-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="24807-130">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="24807-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
