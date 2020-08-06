---
title: TableControl (Format) の TableColumnItem の PropertyName 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: bf267eeb83aef59abea2d945af12e849252309c8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772979"
---
# <a name="propertyname-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="5f2c3-102">TableControl の TableColumnItem の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5f2c3-102">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="5f2c3-103">行の列に値を表示するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="5f2c3-103">Specifies the property whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="5f2c3-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) TableColumnItems Element (format) TableColumnItem Element (format) TableColumnItem (Format) の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="5f2c3-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) PropertyName Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5f2c3-105">構文</span><span class="sxs-lookup"><span data-stu-id="5f2c3-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5f2c3-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5f2c3-106">Attributes and Elements</span></span>

<span data-ttu-id="5f2c3-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="5f2c3-107">The following sections describe attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5f2c3-108">属性</span><span class="sxs-lookup"><span data-stu-id="5f2c3-108">Attributes</span></span>

<span data-ttu-id="5f2c3-109">なし。</span><span class="sxs-lookup"><span data-stu-id="5f2c3-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5f2c3-110">子要素</span><span class="sxs-lookup"><span data-stu-id="5f2c3-110">Child Elements</span></span>

<span data-ttu-id="5f2c3-111">なし。</span><span class="sxs-lookup"><span data-stu-id="5f2c3-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5f2c3-112">親要素</span><span class="sxs-lookup"><span data-stu-id="5f2c3-112">Parent Elements</span></span>

|<span data-ttu-id="5f2c3-113">要素</span><span class="sxs-lookup"><span data-stu-id="5f2c3-113">Element</span></span>|<span data-ttu-id="5f2c3-114">説明</span><span class="sxs-lookup"><span data-stu-id="5f2c3-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5f2c3-115">TableColumnItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="5f2c3-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="5f2c3-116">行の列に値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="5f2c3-116">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5f2c3-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="5f2c3-117">Text Value</span></span>

<span data-ttu-id="5f2c3-118">値が表示されるプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f2c3-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="5f2c3-119">解説</span><span class="sxs-lookup"><span data-stu-id="5f2c3-119">Remarks</span></span>

<span data-ttu-id="5f2c3-120">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f2c3-120">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="5f2c3-121">例</span><span class="sxs-lookup"><span data-stu-id="5f2c3-121">Example</span></span>

<span data-ttu-id="5f2c3-122">この例は、 `TableColumnItem` `Status` system.object オブジェクトのプロパティを指定する[System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="5f2c3-122">This example shows a `TableColumnItem` element that specifies the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="5f2c3-123">参照</span><span class="sxs-lookup"><span data-stu-id="5f2c3-123">See Also</span></span>

[<span data-ttu-id="5f2c3-124">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="5f2c3-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="5f2c3-125">TableColumnItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="5f2c3-125">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="5f2c3-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="5f2c3-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
