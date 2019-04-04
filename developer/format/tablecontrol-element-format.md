---
title: TableControl 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1550b068-dfbc-4ae0-9aa1-72c9a680ec59
caps.latest.revision: 15
ms.openlocfilehash: 3942c008e026b0b99db3c77af4a0152b50fffc4e
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054579"
---
# <a name="tablecontrol-element-format"></a><span data-ttu-id="c20a0-102">TableControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c20a0-102">TableControl Element (Format)</span></span>

<span data-ttu-id="c20a0-103">ビューのテーブル形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="c20a0-103">Defines a table format for a view.</span></span>

<span data-ttu-id="c20a0-104">ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c20a0-104">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c20a0-105">構文</span><span class="sxs-lookup"><span data-stu-id="c20a0-105">Syntax</span></span>

```xml
<TableControl>
  <AutoSize/>
  <HideTableHeaders/>
  <TableHeaders>...</TableHeaders>
  <TableRowEntries>...</TableRowEntries>
</TableControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="c20a0-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="c20a0-106">Attributes and Elements</span></span>

<span data-ttu-id="c20a0-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`TableControl`要素。</span><span class="sxs-lookup"><span data-stu-id="c20a0-107">The following sections describe attributes, child elements, and parent element of the `TableControl` element.</span></span> <span data-ttu-id="c20a0-108">テーブルの行を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c20a0-108">You must specify the rows of the table.</span></span> <span data-ttu-id="c20a0-109">その他のすべての子要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c20a0-109">All other child elements are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="c20a0-110">属性</span><span class="sxs-lookup"><span data-stu-id="c20a0-110">Attributes</span></span>

<span data-ttu-id="c20a0-111">なし。</span><span class="sxs-lookup"><span data-stu-id="c20a0-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c20a0-112">子要素</span><span class="sxs-lookup"><span data-stu-id="c20a0-112">Child Elements</span></span>

|<span data-ttu-id="c20a0-113">要素</span><span class="sxs-lookup"><span data-stu-id="c20a0-113">Element</span></span>|<span data-ttu-id="c20a0-114">説明</span><span class="sxs-lookup"><span data-stu-id="c20a0-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c20a0-115">TableControl (形式) の AutoSize 要素</span><span class="sxs-lookup"><span data-stu-id="c20a0-115">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)|<span data-ttu-id="c20a0-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c20a0-116">Optional element.</span></span><br /><br /> <span data-ttu-id="c20a0-117">かどうか、列のサイズと列の数が調整のデータのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="c20a0-117">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="c20a0-118">TableControl (形式) の HideTableHeaders 要素</span><span class="sxs-lookup"><span data-stu-id="c20a0-118">HideTableHeaders Element for TableControl (Format)</span></span>](./hidetableheaders-element-format.md)|<span data-ttu-id="c20a0-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c20a0-119">Optional element.</span></span><br /><br /> <span data-ttu-id="c20a0-120">テーブルのヘッダーは表示されないかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c20a0-120">Indicates whether the header of the table is not displayed.</span></span>|
|[<span data-ttu-id="c20a0-121">TableControl (形式) の TableHeaders 要素</span><span class="sxs-lookup"><span data-stu-id="c20a0-121">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="c20a0-122">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="c20a0-122">Required element.</span></span><br /><br /> <span data-ttu-id="c20a0-123">ラベル、幅、およびテーブル ビューの列のデータの配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="c20a0-123">Defines the labels, the widths, and the alignment of the data for the columns of the table view.</span></span>|
|[<span data-ttu-id="c20a0-124">TableControl (形式) の TableRowEntries 要素</span><span class="sxs-lookup"><span data-stu-id="c20a0-124">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)|<span data-ttu-id="c20a0-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c20a0-125">Optional element.</span></span><br /><br /> <span data-ttu-id="c20a0-126">テーブル ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="c20a0-126">Provides the definitions of the table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c20a0-127">親要素</span><span class="sxs-lookup"><span data-stu-id="c20a0-127">Parent Elements</span></span>

|<span data-ttu-id="c20a0-128">要素</span><span class="sxs-lookup"><span data-stu-id="c20a0-128">Element</span></span>|<span data-ttu-id="c20a0-129">説明</span><span class="sxs-lookup"><span data-stu-id="c20a0-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c20a0-130">ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c20a0-130">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="c20a0-131">1 つまたは複数のオブジェクトのメンバーを表示するために使用するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="c20a0-131">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c20a0-132">コメント</span><span class="sxs-lookup"><span data-stu-id="c20a0-132">Remarks</span></span>

<span data-ttu-id="c20a0-133">テーブル ビューのコンポーネントに関する詳細については、[テーブル ビューを作成する](./creating-a-table-view.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c20a0-133">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="c20a0-134">例</span><span class="sxs-lookup"><span data-stu-id="c20a0-134">Example</span></span>

<span data-ttu-id="c20a0-135">この例では、`TableControl`要素のプロパティを表示するために使用される、 [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c20a0-135">This example shows a `TableControl` element that is used to display the properties of the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c20a0-136">参照</span><span class="sxs-lookup"><span data-stu-id="c20a0-136">See Also</span></span>

[<span data-ttu-id="c20a0-137">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="c20a0-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="c20a0-138">ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c20a0-138">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="c20a0-139">TableControl (形式) の AutoSize 要素</span><span class="sxs-lookup"><span data-stu-id="c20a0-139">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)

[<span data-ttu-id="c20a0-140">HideTableHeaders 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c20a0-140">HideTableHeaders Element (Format)</span></span>](./hidetableheaders-element-format.md)

[<span data-ttu-id="c20a0-141">TableHeaders 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c20a0-141">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="c20a0-142">TableRowEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c20a0-142">TableRowEntries Element (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)

[<span data-ttu-id="c20a0-143">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="c20a0-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
