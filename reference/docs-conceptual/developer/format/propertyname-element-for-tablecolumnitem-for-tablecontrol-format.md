---
ms.date: 09/13/2016
ms.topic: reference
title: TableControl の TableColumnItem の PropertyName 要素 (書式)
description: TableControl の TableColumnItem の PropertyName 要素 (書式)
ms.openlocfilehash: e83bbdb96d2755013cb9fe065cb98731ba44917f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665585"
---
# <a name="propertyname-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="20fc7-103">TableControl の TableColumnItem の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="20fc7-103">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="20fc7-104">行の列に値を表示するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="20fc7-104">Specifies the property whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="20fc7-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) TableColumnItems Element (format) TableColumnItem Element (format) TableColumnItem (Format) の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="20fc7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) PropertyName Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="20fc7-106">構文</span><span class="sxs-lookup"><span data-stu-id="20fc7-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="20fc7-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="20fc7-107">Attributes and Elements</span></span>

<span data-ttu-id="20fc7-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="20fc7-108">The following sections describe attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="20fc7-109">属性</span><span class="sxs-lookup"><span data-stu-id="20fc7-109">Attributes</span></span>

<span data-ttu-id="20fc7-110">なし。</span><span class="sxs-lookup"><span data-stu-id="20fc7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="20fc7-111">子要素</span><span class="sxs-lookup"><span data-stu-id="20fc7-111">Child Elements</span></span>

<span data-ttu-id="20fc7-112">なし。</span><span class="sxs-lookup"><span data-stu-id="20fc7-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="20fc7-113">親要素</span><span class="sxs-lookup"><span data-stu-id="20fc7-113">Parent Elements</span></span>

|<span data-ttu-id="20fc7-114">要素</span><span class="sxs-lookup"><span data-stu-id="20fc7-114">Element</span></span>|<span data-ttu-id="20fc7-115">説明</span><span class="sxs-lookup"><span data-stu-id="20fc7-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="20fc7-116">TableColumnItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="20fc7-116">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="20fc7-117">行の列に値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="20fc7-117">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="20fc7-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="20fc7-118">Text Value</span></span>

<span data-ttu-id="20fc7-119">値が表示されるプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="20fc7-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="20fc7-120">解説</span><span class="sxs-lookup"><span data-stu-id="20fc7-120">Remarks</span></span>

<span data-ttu-id="20fc7-121">テーブルビューのコンポーネントの詳細については、「 [テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20fc7-121">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="20fc7-122">例</span><span class="sxs-lookup"><span data-stu-id="20fc7-122">Example</span></span>

<span data-ttu-id="20fc7-123">この例は、 `TableColumnItem` `Status` system.object オブジェクトのプロパティを指定する[](/dotnet/api/System.Diagnostics.Process)要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="20fc7-123">This example shows a `TableColumnItem` element that specifies the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="20fc7-124">参照</span><span class="sxs-lookup"><span data-stu-id="20fc7-124">See Also</span></span>

[<span data-ttu-id="20fc7-125">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="20fc7-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="20fc7-126">TableColumnItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="20fc7-126">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="20fc7-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="20fc7-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
