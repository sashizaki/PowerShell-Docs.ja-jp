---
title: TableControl (Format) の TableColumnItems の TableColumnItem 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef8395aa-4b31-48c0-a0b8-b481fd0b3738
caps.latest.revision: 15
ms.openlocfilehash: 9e6cffc7476ef01124d95ecbf287d9788b0324c9
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368231"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a><span data-ttu-id="8363a-102">TableControl の TableColumnItems の TableColumnItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8363a-102">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

<span data-ttu-id="8363a-103">行の列に値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="8363a-103">Defines the property or script whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="8363a-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries の TableControl (format) TableRowEntry 要素の TableRowEntries for TableControl (Format)TableColumnItems for TableControl (Format) の TableControlEntry の TableColumnItems 要素 (Format) TableColumnItem 要素</span><span class="sxs-lookup"><span data-stu-id="8363a-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format) TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8363a-105">構文</span><span class="sxs-lookup"><span data-stu-id="8363a-105">Syntax</span></span>

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <FormatString>FormatPattern</FormatString>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8363a-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="8363a-106">Attributes and Elements</span></span>

<span data-ttu-id="8363a-107">次のセクションでは、`TableColumnItem` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8363a-107">The following sections describe the attributes, child elements, and parent element of the `TableColumnItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8363a-108">属性</span><span class="sxs-lookup"><span data-stu-id="8363a-108">Attributes</span></span>

<span data-ttu-id="8363a-109">なし。</span><span class="sxs-lookup"><span data-stu-id="8363a-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8363a-110">子要素</span><span class="sxs-lookup"><span data-stu-id="8363a-110">Child Elements</span></span>

|<span data-ttu-id="8363a-111">要素</span><span class="sxs-lookup"><span data-stu-id="8363a-111">Element</span></span>|<span data-ttu-id="8363a-112">説明</span><span class="sxs-lookup"><span data-stu-id="8363a-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8363a-113">TableControl (Format) の TableColumnItem の Alignment 要素</span><span class="sxs-lookup"><span data-stu-id="8363a-113">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="8363a-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="8363a-114">Optional element.</span></span><br /><br /> <span data-ttu-id="8363a-115">行の列のデータをどのように表示するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="8363a-115">Defines how the data in a column of the row is displayed.</span></span>|
|[<span data-ttu-id="8363a-116">TableControl (Format) の TableColumnItem の FormatString 要素</span><span class="sxs-lookup"><span data-stu-id="8363a-116">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="8363a-117">行の列のデータの書式設定に使用する形式パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="8363a-117">Specifies a format pattern that is used to format the data in the column of the row.</span></span>|
|[<span data-ttu-id="8363a-118">TableControl (Format) の TableColumnItem の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="8363a-118">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="8363a-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="8363a-119">Optional element.</span></span><br /><br /> <span data-ttu-id="8363a-120">値が表示されるプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8363a-120">Specifies the name of the property whose value is displayed.</span></span>|
|[<span data-ttu-id="8363a-121">TableControl (Format) の TableColumnItem の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="8363a-121">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="8363a-122">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="8363a-122">Optional element.</span></span><br /><br /> <span data-ttu-id="8363a-123">行の列に値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="8363a-123">Specifies the script whose value is displayed in the column of a row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8363a-124">親要素</span><span class="sxs-lookup"><span data-stu-id="8363a-124">Parent Elements</span></span>

|<span data-ttu-id="8363a-125">要素</span><span class="sxs-lookup"><span data-stu-id="8363a-125">Element</span></span>|<span data-ttu-id="8363a-126">説明</span><span class="sxs-lookup"><span data-stu-id="8363a-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8363a-127">TableControl (Format) の TableControlEntry の TableColumnItems 要素</span><span class="sxs-lookup"><span data-stu-id="8363a-127">TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="8363a-128">値が行内に表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="8363a-128">Defines the properties or scripts whose values are displayed in the row.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8363a-129">コメント</span><span class="sxs-lookup"><span data-stu-id="8363a-129">Remarks</span></span>

<span data-ttu-id="8363a-130">行の各列に、オブジェクトまたはスクリプトのプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8363a-130">You can specify a property of an object or a script in each column of the row.</span></span> <span data-ttu-id="8363a-131">子要素が指定されていない場合、項目はプレースホルダーであり、データは表示されません。</span><span class="sxs-lookup"><span data-stu-id="8363a-131">If no child elements are specified, the item is a placeholder, and no data is displayed.</span></span>

<span data-ttu-id="8363a-132">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8363a-132">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="8363a-133">例</span><span class="sxs-lookup"><span data-stu-id="8363a-133">Example</span></span>

<span data-ttu-id="8363a-134">次の例[は、`TableColumnItem`](/dotnet/api/System.Diagnostics.Process)の `Status` プロパティの値を表示する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="8363a-134">This example shows a `TableColumnItem` element that displays the value of the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="8363a-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="8363a-135">See Also</span></span>

[<span data-ttu-id="8363a-136">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="8363a-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="8363a-137">TableControl (Format) の TableColumnItem の Alignment 要素</span><span class="sxs-lookup"><span data-stu-id="8363a-137">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="8363a-138">TableColumnItems 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="8363a-138">TableColumnItems Element (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="8363a-139">TableControl (Format) の TableColumnItem の FormatString 要素</span><span class="sxs-lookup"><span data-stu-id="8363a-139">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="8363a-140">TableControl (Format) の TableColumnItem の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="8363a-140">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="8363a-141">TableControl (Format) の TableColumnItem の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="8363a-141">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="8363a-142">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="8363a-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
