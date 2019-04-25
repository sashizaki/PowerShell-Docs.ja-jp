---
title: TableControl (形式) の TableColumnItems TableColumnItem 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef8395aa-4b31-48c0-a0b8-b481fd0b3738
caps.latest.revision: 15
ms.openlocfilehash: 159f943f6bfb33c5403b5714380631351523789f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62063940"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a><span data-ttu-id="c47f6-102">TableControl の TableColumnItems の TableColumnItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c47f6-102">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

<span data-ttu-id="c47f6-103">プロパティまたは値を持つが、行の列に表示されているスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="c47f6-103">Defines the property or script whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="c47f6-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素の要素に TableControl (形式) TableRowEntry TableRowEntries TableControl (形式) 用のTableControl (形式) の TableColumnItems の TableControl (形式) TableColumnItem 要素 TableControlEntry TableColumnItems 要素</span><span class="sxs-lookup"><span data-stu-id="c47f6-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format) TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c47f6-105">構文</span><span class="sxs-lookup"><span data-stu-id="c47f6-105">Syntax</span></span>

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c47f6-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c47f6-106">Attributes and Elements</span></span>

<span data-ttu-id="c47f6-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`TableColumnItem`要素。</span><span class="sxs-lookup"><span data-stu-id="c47f6-107">The following sections describe the attributes, child elements, and parent element of the `TableColumnItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c47f6-108">属性</span><span class="sxs-lookup"><span data-stu-id="c47f6-108">Attributes</span></span>

<span data-ttu-id="c47f6-109">なし。</span><span class="sxs-lookup"><span data-stu-id="c47f6-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c47f6-110">子要素</span><span class="sxs-lookup"><span data-stu-id="c47f6-110">Child Elements</span></span>

|<span data-ttu-id="c47f6-111">要素</span><span class="sxs-lookup"><span data-stu-id="c47f6-111">Element</span></span>|<span data-ttu-id="c47f6-112">説明</span><span class="sxs-lookup"><span data-stu-id="c47f6-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c47f6-113">TableControl (形式) の TableColumnItem の alignment 要素</span><span class="sxs-lookup"><span data-stu-id="c47f6-113">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="c47f6-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c47f6-114">Optional element.</span></span><br /><br /> <span data-ttu-id="c47f6-115">行の列のデータを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="c47f6-115">Defines how the data in a column of the row is displayed.</span></span>|
|[<span data-ttu-id="c47f6-116">TableControl (形式) の TableColumnItem の FormatString 要素</span><span class="sxs-lookup"><span data-stu-id="c47f6-116">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="c47f6-117">行の列のデータを書式設定に使用される書式パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c47f6-117">Specifies a format pattern that is used to format the data in the column of the row.</span></span>|
|[<span data-ttu-id="c47f6-118">TableControl (形式) の TableColumnItem PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="c47f6-118">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="c47f6-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c47f6-119">Optional element.</span></span><br /><br /> <span data-ttu-id="c47f6-120">値が表示されるプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c47f6-120">Specifies the name of the property whose value is displayed.</span></span>|
|[<span data-ttu-id="c47f6-121">TableControl (形式) の TableColumnItem の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="c47f6-121">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="c47f6-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c47f6-122">Optional element.</span></span><br /><br /> <span data-ttu-id="c47f6-123">行の列で値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c47f6-123">Specifies the script whose value is displayed in the column of a row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c47f6-124">親要素</span><span class="sxs-lookup"><span data-stu-id="c47f6-124">Parent Elements</span></span>

|<span data-ttu-id="c47f6-125">要素</span><span class="sxs-lookup"><span data-stu-id="c47f6-125">Element</span></span>|<span data-ttu-id="c47f6-126">説明</span><span class="sxs-lookup"><span data-stu-id="c47f6-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c47f6-127">TableControl (形式) の TableControlEntry TableColumnItems 要素</span><span class="sxs-lookup"><span data-stu-id="c47f6-127">TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="c47f6-128">プロパティまたは行の表示が値を持つスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="c47f6-128">Defines the properties or scripts whose values are displayed in the row.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c47f6-129">コメント</span><span class="sxs-lookup"><span data-stu-id="c47f6-129">Remarks</span></span>

<span data-ttu-id="c47f6-130">行の各列では、オブジェクトまたはスクリプトのプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c47f6-130">You can specify a property of an object or a script in each column of the row.</span></span> <span data-ttu-id="c47f6-131">子要素が指定されていない場合は、項目が、プレース ホルダーとデータは表示されません。</span><span class="sxs-lookup"><span data-stu-id="c47f6-131">If no child elements are specified, the item is a placeholder, and no data is displayed.</span></span>

<span data-ttu-id="c47f6-132">テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="c47f6-132">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="c47f6-133">例</span><span class="sxs-lookup"><span data-stu-id="c47f6-133">Example</span></span>

<span data-ttu-id="c47f6-134">この例では、`TableColumnItem`要素の値を表示する、`Status`のプロパティ、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c47f6-134">This example shows a `TableColumnItem` element that displays the value of the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="c47f6-135">参照</span><span class="sxs-lookup"><span data-stu-id="c47f6-135">See Also</span></span>

[<span data-ttu-id="c47f6-136">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="c47f6-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="c47f6-137">TableControl (形式) の TableColumnItem の alignment 要素</span><span class="sxs-lookup"><span data-stu-id="c47f6-137">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="c47f6-138">TableColumnItems 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c47f6-138">TableColumnItems Element (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="c47f6-139">TableControl (形式) の TableColumnItem の FormatString 要素</span><span class="sxs-lookup"><span data-stu-id="c47f6-139">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="c47f6-140">TableControl (形式) の TableColumnItem PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="c47f6-140">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="c47f6-141">TableControl (形式) の TableColumnItem の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="c47f6-141">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="c47f6-142">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="c47f6-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
