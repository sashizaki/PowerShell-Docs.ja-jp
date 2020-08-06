---
title: TableControl 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 34e20006a7501650f2a22f71a3d7e999fb8b2337
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785134"
---
# <a name="tablecontrol-element-format"></a><span data-ttu-id="b4775-102">TableControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b4775-102">TableControl Element (Format)</span></span>

<span data-ttu-id="b4775-103">ビューのテーブル形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="b4775-103">Defines a table format for a view.</span></span>

<span data-ttu-id="b4775-104">ViewDefinitions 要素 (Format) ビュー要素 (Format) TableControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="b4775-104">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b4775-105">構文</span><span class="sxs-lookup"><span data-stu-id="b4775-105">Syntax</span></span>

```xml
<TableControl>
  <AutoSize/>
  <HideTableHeaders/>
  <TableHeaders>...</TableHeaders>
  <TableRowEntries>...</TableRowEntries>
</TableControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="b4775-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b4775-106">Attributes and Elements</span></span>

<span data-ttu-id="b4775-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `TableControl` ます。</span><span class="sxs-lookup"><span data-stu-id="b4775-107">The following sections describe attributes, child elements, and parent element of the `TableControl` element.</span></span> <span data-ttu-id="b4775-108">テーブルの行を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4775-108">You must specify the rows of the table.</span></span> <span data-ttu-id="b4775-109">その他のすべての子要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b4775-109">All other child elements are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="b4775-110">属性</span><span class="sxs-lookup"><span data-stu-id="b4775-110">Attributes</span></span>

<span data-ttu-id="b4775-111">なし。</span><span class="sxs-lookup"><span data-stu-id="b4775-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b4775-112">子要素</span><span class="sxs-lookup"><span data-stu-id="b4775-112">Child Elements</span></span>

|<span data-ttu-id="b4775-113">要素</span><span class="sxs-lookup"><span data-stu-id="b4775-113">Element</span></span>|<span data-ttu-id="b4775-114">説明</span><span class="sxs-lookup"><span data-stu-id="b4775-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b4775-115">TableControl の AutoSize 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b4775-115">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)|<span data-ttu-id="b4775-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="b4775-116">Optional element.</span></span><br /><br /> <span data-ttu-id="b4775-117">データのサイズに基づいて列のサイズと列の数を調整するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b4775-117">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="b4775-118">TableControl (Format) の HideTableHeaders 要素</span><span class="sxs-lookup"><span data-stu-id="b4775-118">HideTableHeaders Element for TableControl (Format)</span></span>](./hidetableheaders-element-format.md)|<span data-ttu-id="b4775-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="b4775-119">Optional element.</span></span><br /><br /> <span data-ttu-id="b4775-120">テーブルのヘッダーが表示されていないかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b4775-120">Indicates whether the header of the table is not displayed.</span></span>|
|[<span data-ttu-id="b4775-121">TableControl の TableHeaders 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="b4775-121">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="b4775-122">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="b4775-122">Required element.</span></span><br /><br /> <span data-ttu-id="b4775-123">テーブルビューの列のデータのラベル、幅、および配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="b4775-123">Defines the labels, the widths, and the alignment of the data for the columns of the table view.</span></span>|
|[<span data-ttu-id="b4775-124">TableControl の TableRowEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b4775-124">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)|<span data-ttu-id="b4775-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="b4775-125">Optional element.</span></span><br /><br /> <span data-ttu-id="b4775-126">テーブルビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="b4775-126">Provides the definitions of the table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b4775-127">親要素</span><span class="sxs-lookup"><span data-stu-id="b4775-127">Parent Elements</span></span>

|<span data-ttu-id="b4775-128">要素</span><span class="sxs-lookup"><span data-stu-id="b4775-128">Element</span></span>|<span data-ttu-id="b4775-129">説明</span><span class="sxs-lookup"><span data-stu-id="b4775-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b4775-130">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b4775-130">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="b4775-131">1つ以上のオブジェクトのメンバーを表示するために使用されるビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="b4775-131">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b4775-132">解説</span><span class="sxs-lookup"><span data-stu-id="b4775-132">Remarks</span></span>

<span data-ttu-id="b4775-133">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4775-133">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="b4775-134">例</span><span class="sxs-lookup"><span data-stu-id="b4775-134">Example</span></span>

<span data-ttu-id="b4775-135">この例は、 `TableControl` [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトのプロパティを表示するために使用される要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="b4775-135">This example shows a `TableControl` element that is used to display the properties of the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b4775-136">参照</span><span class="sxs-lookup"><span data-stu-id="b4775-136">See Also</span></span>

[<span data-ttu-id="b4775-137">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="b4775-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="b4775-138">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b4775-138">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="b4775-139">TableControl の AutoSize 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b4775-139">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)

[<span data-ttu-id="b4775-140">HideTableHeaders 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="b4775-140">HideTableHeaders Element (Format)</span></span>](./hidetableheaders-element-format.md)

[<span data-ttu-id="b4775-141">TableHeaders 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="b4775-141">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="b4775-142">TableRowEntries 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="b4775-142">TableRowEntries Element (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)

[<span data-ttu-id="b4775-143">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="b4775-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
