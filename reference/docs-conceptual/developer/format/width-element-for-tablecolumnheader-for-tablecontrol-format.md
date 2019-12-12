---
title: TableControl (Format) の TableColumnHeader の Width 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 94eb0535-8002-4f17-9a2b-4be75ec20e5c
caps.latest.revision: 18
ms.openlocfilehash: 4a25c9d81df670dc10955065bfb66766cdb1bd33
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367871"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="98349-102">TableControl の TableColumnHeader の Width 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="98349-102">Width Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="98349-103">列の幅 (文字数) を定義します。</span><span class="sxs-lookup"><span data-stu-id="98349-103">Defines the width (in characters) of a column.</span></span>

<span data-ttu-id="98349-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableHeaders 要素 TableControl (format) の TableColumnHeader 要素 TableHeaders for TableControl (Format) Width 要素TableControl (Format) の TableColumnHeader</span><span class="sxs-lookup"><span data-stu-id="98349-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element TableHeaders for TableControl (Format) Width Element for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="98349-105">構文</span><span class="sxs-lookup"><span data-stu-id="98349-105">Syntax</span></span>

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="98349-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="98349-106">Attributes and Elements</span></span>

<span data-ttu-id="98349-107">以下のセクションでは、列ヘッダーを定義するときに使用する `Width` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="98349-107">The following sections describe the attributes, child elements, and parent element of the `Width` element used when defining column headers.</span></span>

### <a name="attributes"></a><span data-ttu-id="98349-108">属性</span><span class="sxs-lookup"><span data-stu-id="98349-108">Attributes</span></span>

<span data-ttu-id="98349-109">なし。</span><span class="sxs-lookup"><span data-stu-id="98349-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="98349-110">子要素</span><span class="sxs-lookup"><span data-stu-id="98349-110">Child Elements</span></span>

<span data-ttu-id="98349-111">なし。</span><span class="sxs-lookup"><span data-stu-id="98349-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="98349-112">親要素</span><span class="sxs-lookup"><span data-stu-id="98349-112">Parent Elements</span></span>

|<span data-ttu-id="98349-113">要素</span><span class="sxs-lookup"><span data-stu-id="98349-113">Element</span></span>|<span data-ttu-id="98349-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="98349-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="98349-115">TableControl の TableHeaders の TableColumnHeader 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="98349-115">TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="98349-116">テーブルの列のデータのラベル、幅、および配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="98349-116">Defines a label, width, and alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="98349-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="98349-117">Text Value</span></span>

<span data-ttu-id="98349-118">可能な限り、表示されるプロパティ値の長さを超える幅 (文字数) を指定します。</span><span class="sxs-lookup"><span data-stu-id="98349-118">When at all possible, specify a width (in characters) that is greater than the length of the displayed property values.</span></span>

## <a name="remarks"></a><span data-ttu-id="98349-119">コメント</span><span class="sxs-lookup"><span data-stu-id="98349-119">Remarks</span></span>

<span data-ttu-id="98349-120">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98349-120">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="98349-121">例</span><span class="sxs-lookup"><span data-stu-id="98349-121">Example</span></span>

<span data-ttu-id="98349-122">次の例は、幅が16文字の `TableColumnHeader` 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="98349-122">The following example shows a `TableColumnHeader` element whose width is 16 characters.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="98349-123">参照</span><span class="sxs-lookup"><span data-stu-id="98349-123">See Also</span></span>

[<span data-ttu-id="98349-124">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="98349-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="98349-125">TableControl の TableHeader の TableColumnHeader 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="98349-125">TableColumnHeader Element for TableHeader for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="98349-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="98349-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
