---
title: TableControl (形式) の TableColumnHeader の要素にラベルを付ける |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7196f039-2f6a-41fd-b252-5b1623ebb9f9
caps.latest.revision: 11
ms.openlocfilehash: 09183a538c179f19347c3f1ed45b4ad38c2ca451
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065752"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="4504a-102">TableControl の TableColumnHeader の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4504a-102">Label Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="4504a-103">列の上部に表示されるラベルを定義します。</span><span class="sxs-lookup"><span data-stu-id="4504a-103">Defines the label that is displayed at the top of a column.</span></span> <span data-ttu-id="4504a-104">この要素は、テーブル ビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4504a-104">This element is used when defining a table view.</span></span>

<span data-ttu-id="4504a-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableHeaders 要素の要素に TableControl (形式) TableColumnHeader TableHeaders の TableControl (形式) ラベル要素のTableControl (形式) の TableColumnHeader</span><span class="sxs-lookup"><span data-stu-id="4504a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format) Label Element  for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4504a-106">構文</span><span class="sxs-lookup"><span data-stu-id="4504a-106">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="4504a-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4504a-107">Attributes and Elements</span></span>

<span data-ttu-id="4504a-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`Label`要素。</span><span class="sxs-lookup"><span data-stu-id="4504a-108">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span> <span data-ttu-id="4504a-109">1 つだけのラベルには、各列は使用できます。</span><span class="sxs-lookup"><span data-stu-id="4504a-109">Only one label is allowed for each column.</span></span>

### <a name="attributes"></a><span data-ttu-id="4504a-110">属性</span><span class="sxs-lookup"><span data-stu-id="4504a-110">Attributes</span></span>

<span data-ttu-id="4504a-111">なし。</span><span class="sxs-lookup"><span data-stu-id="4504a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4504a-112">子要素</span><span class="sxs-lookup"><span data-stu-id="4504a-112">Child Elements</span></span>

<span data-ttu-id="4504a-113">なし。</span><span class="sxs-lookup"><span data-stu-id="4504a-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4504a-114">親要素</span><span class="sxs-lookup"><span data-stu-id="4504a-114">Parent Elements</span></span>

|<span data-ttu-id="4504a-115">要素</span><span class="sxs-lookup"><span data-stu-id="4504a-115">Element</span></span>|<span data-ttu-id="4504a-116">説明</span><span class="sxs-lookup"><span data-stu-id="4504a-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4504a-117">TableControl (形式) の TableHeaders TableColumnHeader 要素</span><span class="sxs-lookup"><span data-stu-id="4504a-117">TableColumnHeader Element for TableHeaders for TableControl  (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="4504a-118">ラベル、幅、およびテーブルの列のデータのアラインメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="4504a-118">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4504a-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="4504a-119">Text Value</span></span>

<span data-ttu-id="4504a-120">テーブルの列の上部に表示されるテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="4504a-120">Specify the text that is displayed at the top of the column of the table.</span></span> <span data-ttu-id="4504a-121">列のラベルの文字の制限はありません。</span><span class="sxs-lookup"><span data-stu-id="4504a-121">There are no restricted characters for the column label.</span></span>

## <a name="remarks"></a><span data-ttu-id="4504a-122">コメント</span><span class="sxs-lookup"><span data-stu-id="4504a-122">Remarks</span></span>

<span data-ttu-id="4504a-123">ラベルが指定されていない場合は、行の値を持つが表示されるプロパティの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4504a-123">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>

<span data-ttu-id="4504a-124">テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="4504a-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="4504a-125">例</span><span class="sxs-lookup"><span data-stu-id="4504a-125">Example</span></span>

<span data-ttu-id="4504a-126">この例では、`TableColumnHeader`要素のラベルは"Column 1"です。</span><span class="sxs-lookup"><span data-stu-id="4504a-126">This example shows a `TableColumnHeader` element whose label is "Column 1".</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="4504a-127">参照</span><span class="sxs-lookup"><span data-stu-id="4504a-127">See Also</span></span>

[<span data-ttu-id="4504a-128">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="4504a-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="4504a-129">TableColumnHeader 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="4504a-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="4504a-130">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="4504a-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
