---
ms.date: 09/13/2016
ms.topic: reference
title: TableControl 要素 (書式)
description: TableControl 要素 (書式)
ms.openlocfilehash: 93e05e22d61504d7781b6f3c07f9a3fd0b3c9e8a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651464"
---
# <a name="tablecontrol-element-format"></a><span data-ttu-id="97a61-103">TableControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="97a61-103">TableControl Element (Format)</span></span>

<span data-ttu-id="97a61-104">ビューのテーブル形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="97a61-104">Defines a table format for a view.</span></span>

<span data-ttu-id="97a61-105">ViewDefinitions 要素 (Format) ビュー要素 (Format) TableControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="97a61-105">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="97a61-106">構文</span><span class="sxs-lookup"><span data-stu-id="97a61-106">Syntax</span></span>

```xml
<TableControl>
  <AutoSize/>
  <HideTableHeaders/>
  <TableHeaders>...</TableHeaders>
  <TableRowEntries>...</TableRowEntries>
</TableControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="97a61-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="97a61-107">Attributes and Elements</span></span>

<span data-ttu-id="97a61-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `TableControl` ます。</span><span class="sxs-lookup"><span data-stu-id="97a61-108">The following sections describe attributes, child elements, and parent element of the `TableControl` element.</span></span> <span data-ttu-id="97a61-109">テーブルの行を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97a61-109">You must specify the rows of the table.</span></span> <span data-ttu-id="97a61-110">その他のすべての子要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="97a61-110">All other child elements are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="97a61-111">属性</span><span class="sxs-lookup"><span data-stu-id="97a61-111">Attributes</span></span>

<span data-ttu-id="97a61-112">なし。</span><span class="sxs-lookup"><span data-stu-id="97a61-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="97a61-113">子要素</span><span class="sxs-lookup"><span data-stu-id="97a61-113">Child Elements</span></span>

|<span data-ttu-id="97a61-114">要素</span><span class="sxs-lookup"><span data-stu-id="97a61-114">Element</span></span>|<span data-ttu-id="97a61-115">説明</span><span class="sxs-lookup"><span data-stu-id="97a61-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="97a61-116">TableControl の AutoSize 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="97a61-116">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)|<span data-ttu-id="97a61-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="97a61-117">Optional element.</span></span><br /><br /> <span data-ttu-id="97a61-118">データのサイズに基づいて列のサイズと列の数を調整するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="97a61-118">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="97a61-119">TableControl (Format) の HideTableHeaders 要素</span><span class="sxs-lookup"><span data-stu-id="97a61-119">HideTableHeaders Element for TableControl (Format)</span></span>](./hidetableheaders-element-format.md)|<span data-ttu-id="97a61-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="97a61-120">Optional element.</span></span><br /><br /> <span data-ttu-id="97a61-121">テーブルのヘッダーが表示されていないかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="97a61-121">Indicates whether the header of the table is not displayed.</span></span>|
|[<span data-ttu-id="97a61-122">TableControl の TableHeaders 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="97a61-122">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="97a61-123">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="97a61-123">Required element.</span></span><br /><br /> <span data-ttu-id="97a61-124">テーブルビューの列のデータのラベル、幅、および配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="97a61-124">Defines the labels, the widths, and the alignment of the data for the columns of the table view.</span></span>|
|[<span data-ttu-id="97a61-125">TableControl の TableRowEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="97a61-125">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)|<span data-ttu-id="97a61-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="97a61-126">Optional element.</span></span><br /><br /> <span data-ttu-id="97a61-127">テーブルビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="97a61-127">Provides the definitions of the table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="97a61-128">親要素</span><span class="sxs-lookup"><span data-stu-id="97a61-128">Parent Elements</span></span>

|<span data-ttu-id="97a61-129">要素</span><span class="sxs-lookup"><span data-stu-id="97a61-129">Element</span></span>|<span data-ttu-id="97a61-130">説明</span><span class="sxs-lookup"><span data-stu-id="97a61-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="97a61-131">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="97a61-131">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="97a61-132">1つ以上のオブジェクトのメンバーを表示するために使用されるビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="97a61-132">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="97a61-133">解説</span><span class="sxs-lookup"><span data-stu-id="97a61-133">Remarks</span></span>

<span data-ttu-id="97a61-134">テーブルビューのコンポーネントの詳細については、「 [テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97a61-134">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="97a61-135">例</span><span class="sxs-lookup"><span data-stu-id="97a61-135">Example</span></span>

<span data-ttu-id="97a61-136">この例は、 `TableControl` [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) オブジェクトのプロパティを表示するために使用される要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="97a61-136">This example shows a `TableControl` element that is used to display the properties of the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>...</TableHeaders>
    <TableRowEntries>...</TableRowEntries>
  </TableControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="97a61-137">参照</span><span class="sxs-lookup"><span data-stu-id="97a61-137">See Also</span></span>

[<span data-ttu-id="97a61-138">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="97a61-138">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="97a61-139">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="97a61-139">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="97a61-140">TableControl の AutoSize 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="97a61-140">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)

[<span data-ttu-id="97a61-141">HideTableHeaders 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="97a61-141">HideTableHeaders Element (Format)</span></span>](./hidetableheaders-element-format.md)

[<span data-ttu-id="97a61-142">TableHeaders 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="97a61-142">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="97a61-143">TableRowEntries 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="97a61-143">TableRowEntries Element (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)

[<span data-ttu-id="97a61-144">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="97a61-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
