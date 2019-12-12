---
title: TableControl 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1550b068-dfbc-4ae0-9aa1-72c9a680ec59
caps.latest.revision: 15
ms.openlocfilehash: 3942c008e026b0b99db3c77af4a0152b50fffc4e
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368201"
---
# <a name="tablecontrol-element-format"></a><span data-ttu-id="afbf9-102">TableControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="afbf9-102">TableControl Element (Format)</span></span>

<span data-ttu-id="afbf9-103">ビューのテーブル形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="afbf9-103">Defines a table format for a view.</span></span>

<span data-ttu-id="afbf9-104">ViewDefinitions 要素 (Format) ビュー要素 (Format) TableControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="afbf9-104">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="afbf9-105">構文</span><span class="sxs-lookup"><span data-stu-id="afbf9-105">Syntax</span></span>

```xml
<TableControl>
  <AutoSize/>
  <HideTableHeaders/>
  <TableHeaders>...</TableHeaders>
  <TableRowEntries>...</TableRowEntries>
</TableControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="afbf9-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="afbf9-106">Attributes and Elements</span></span>

<span data-ttu-id="afbf9-107">次のセクションでは、`TableControl` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="afbf9-107">The following sections describe attributes, child elements, and parent element of the `TableControl` element.</span></span> <span data-ttu-id="afbf9-108">テーブルの行を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afbf9-108">You must specify the rows of the table.</span></span> <span data-ttu-id="afbf9-109">その他のすべての子要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="afbf9-109">All other child elements are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="afbf9-110">属性</span><span class="sxs-lookup"><span data-stu-id="afbf9-110">Attributes</span></span>

<span data-ttu-id="afbf9-111">なし。</span><span class="sxs-lookup"><span data-stu-id="afbf9-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="afbf9-112">子要素</span><span class="sxs-lookup"><span data-stu-id="afbf9-112">Child Elements</span></span>

|<span data-ttu-id="afbf9-113">要素</span><span class="sxs-lookup"><span data-stu-id="afbf9-113">Element</span></span>|<span data-ttu-id="afbf9-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="afbf9-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="afbf9-115">TableControl の AutoSize 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="afbf9-115">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)|<span data-ttu-id="afbf9-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="afbf9-116">Optional element.</span></span><br /><br /> <span data-ttu-id="afbf9-117">データのサイズに基づいて列のサイズと列の数を調整するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="afbf9-117">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="afbf9-118">TableControl (Format) の HideTableHeaders 要素</span><span class="sxs-lookup"><span data-stu-id="afbf9-118">HideTableHeaders Element for TableControl (Format)</span></span>](./hidetableheaders-element-format.md)|<span data-ttu-id="afbf9-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="afbf9-119">Optional element.</span></span><br /><br /> <span data-ttu-id="afbf9-120">テーブルのヘッダーが表示されていないかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="afbf9-120">Indicates whether the header of the table is not displayed.</span></span>|
|[<span data-ttu-id="afbf9-121">TableControl の TableHeaders 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="afbf9-121">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="afbf9-122">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="afbf9-122">Required element.</span></span><br /><br /> <span data-ttu-id="afbf9-123">テーブルビューの列のデータのラベル、幅、および配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="afbf9-123">Defines the labels, the widths, and the alignment of the data for the columns of the table view.</span></span>|
|[<span data-ttu-id="afbf9-124">TableControl (Format) の TableRowEntries 要素</span><span class="sxs-lookup"><span data-stu-id="afbf9-124">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)|<span data-ttu-id="afbf9-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="afbf9-125">Optional element.</span></span><br /><br /> <span data-ttu-id="afbf9-126">テーブルビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="afbf9-126">Provides the definitions of the table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="afbf9-127">親要素</span><span class="sxs-lookup"><span data-stu-id="afbf9-127">Parent Elements</span></span>

|<span data-ttu-id="afbf9-128">要素</span><span class="sxs-lookup"><span data-stu-id="afbf9-128">Element</span></span>|<span data-ttu-id="afbf9-129">[説明]</span><span class="sxs-lookup"><span data-stu-id="afbf9-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="afbf9-130">View 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="afbf9-130">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="afbf9-131">1つ以上のオブジェクトのメンバーを表示するために使用されるビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="afbf9-131">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="afbf9-132">コメント</span><span class="sxs-lookup"><span data-stu-id="afbf9-132">Remarks</span></span>

<span data-ttu-id="afbf9-133">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afbf9-133">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="afbf9-134">例</span><span class="sxs-lookup"><span data-stu-id="afbf9-134">Example</span></span>

<span data-ttu-id="afbf9-135">この例は、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトのプロパティを表示するために使用される `TableControl` 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="afbf9-135">This example shows a `TableControl` element that is used to display the properties of the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="afbf9-136">参照</span><span class="sxs-lookup"><span data-stu-id="afbf9-136">See Also</span></span>

[<span data-ttu-id="afbf9-137">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="afbf9-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="afbf9-138">View 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="afbf9-138">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="afbf9-139">TableControl の AutoSize 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="afbf9-139">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)

[<span data-ttu-id="afbf9-140">HideTableHeaders 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="afbf9-140">HideTableHeaders Element (Format)</span></span>](./hidetableheaders-element-format.md)

[<span data-ttu-id="afbf9-141">TableHeaders 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="afbf9-141">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="afbf9-142">TableRowEntries 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="afbf9-142">TableRowEntries Element (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)

[<span data-ttu-id="afbf9-143">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="afbf9-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
