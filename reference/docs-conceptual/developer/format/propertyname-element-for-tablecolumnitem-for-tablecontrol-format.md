---
title: TableControl (Format) の TableColumnItem の PropertyName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb26d72c-2f77-4801-badf-0537ccc55e31
caps.latest.revision: 10
ms.openlocfilehash: 6e86b6a0874b385703121802bc8108a0410442cd
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362251"
---
# <a name="propertyname-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="496c7-102">TableControl の TableColumnItem の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="496c7-102">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="496c7-103">行の列に値を表示するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="496c7-103">Specifies the property whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="496c7-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) TableColumnItems Element (format) TableColumnItem Element (Format)TableColumnItem の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="496c7-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) PropertyName Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="496c7-105">構文</span><span class="sxs-lookup"><span data-stu-id="496c7-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="496c7-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="496c7-106">Attributes and Elements</span></span>

<span data-ttu-id="496c7-107">次のセクションでは、`PropertyName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="496c7-107">The following sections describe attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="496c7-108">属性</span><span class="sxs-lookup"><span data-stu-id="496c7-108">Attributes</span></span>

<span data-ttu-id="496c7-109">なし。</span><span class="sxs-lookup"><span data-stu-id="496c7-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="496c7-110">子要素</span><span class="sxs-lookup"><span data-stu-id="496c7-110">Child Elements</span></span>

<span data-ttu-id="496c7-111">なし。</span><span class="sxs-lookup"><span data-stu-id="496c7-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="496c7-112">親要素</span><span class="sxs-lookup"><span data-stu-id="496c7-112">Parent Elements</span></span>

|<span data-ttu-id="496c7-113">要素</span><span class="sxs-lookup"><span data-stu-id="496c7-113">Element</span></span>|<span data-ttu-id="496c7-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="496c7-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="496c7-115">TableColumnItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="496c7-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="496c7-116">行の列に値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="496c7-116">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="496c7-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="496c7-117">Text Value</span></span>

<span data-ttu-id="496c7-118">値が表示されるプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="496c7-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="496c7-119">コメント</span><span class="sxs-lookup"><span data-stu-id="496c7-119">Remarks</span></span>

<span data-ttu-id="496c7-120">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="496c7-120">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="496c7-121">例</span><span class="sxs-lookup"><span data-stu-id="496c7-121">Example</span></span>

<span data-ttu-id="496c7-122">この例では[、system.object オブジェクト](/dotnet/api/System.Diagnostics.Process)の `Status` プロパティを指定する @no__t 0 の要素を示します。</span><span class="sxs-lookup"><span data-stu-id="496c7-122">This example shows a `TableColumnItem` element that specifies the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="496c7-123">参照</span><span class="sxs-lookup"><span data-stu-id="496c7-123">See Also</span></span>

[<span data-ttu-id="496c7-124">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="496c7-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="496c7-125">TableColumnItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="496c7-125">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="496c7-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="496c7-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
