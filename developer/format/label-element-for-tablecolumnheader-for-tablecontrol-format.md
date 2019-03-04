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
ms.openlocfilehash: 59dfd40b95d5088a711eb89cf101eb31a4b159f5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856088"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="874f5-102">TableControl の TableColumnHeader の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="874f5-102">Label Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="874f5-103">列の上部に表示されるラベルを定義します。</span><span class="sxs-lookup"><span data-stu-id="874f5-103">Defines the label that is displayed at the top of a column.</span></span> <span data-ttu-id="874f5-104">この要素は、テーブル ビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="874f5-104">This element is used when defining a table view.</span></span>

<span data-ttu-id="874f5-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableHeaders 要素の要素に TableControl (形式) TableColumnHeader TableHeaders の TableControl (形式) ラベル要素のTableColumnHeader TablControl (形式) の</span><span class="sxs-lookup"><span data-stu-id="874f5-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format) Label Element  for TableColumnHeader for TablControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="874f5-106">構文</span><span class="sxs-lookup"><span data-stu-id="874f5-106">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="874f5-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="874f5-107">Attributes and Elements</span></span>

<span data-ttu-id="874f5-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`Label`要素。</span><span class="sxs-lookup"><span data-stu-id="874f5-108">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span> <span data-ttu-id="874f5-109">1 つだけのラベルには、各列は使用できます。</span><span class="sxs-lookup"><span data-stu-id="874f5-109">Only one label is allowed for each column.</span></span>

### <a name="attributes"></a><span data-ttu-id="874f5-110">属性</span><span class="sxs-lookup"><span data-stu-id="874f5-110">Attributes</span></span>

<span data-ttu-id="874f5-111">なし。</span><span class="sxs-lookup"><span data-stu-id="874f5-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="874f5-112">子要素</span><span class="sxs-lookup"><span data-stu-id="874f5-112">Child Elements</span></span>

<span data-ttu-id="874f5-113">なし。</span><span class="sxs-lookup"><span data-stu-id="874f5-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="874f5-114">親要素</span><span class="sxs-lookup"><span data-stu-id="874f5-114">Parent Elements</span></span>

|<span data-ttu-id="874f5-115">要素</span><span class="sxs-lookup"><span data-stu-id="874f5-115">Element</span></span>|<span data-ttu-id="874f5-116">説明</span><span class="sxs-lookup"><span data-stu-id="874f5-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="874f5-117">TableControl (形式) の TableHeaders TableColumnHeader 要素</span><span class="sxs-lookup"><span data-stu-id="874f5-117">TableColumnHeader Element for TableHeaders for TableControl  (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="874f5-118">ラベル、幅、およびテーブルの列のデータのアラインメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="874f5-118">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="874f5-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="874f5-119">Text Value</span></span>

<span data-ttu-id="874f5-120">テーブルの列の上部に表示されるテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="874f5-120">Specify the text that is displayed at the top of the column of the table.</span></span> <span data-ttu-id="874f5-121">列のラベルの文字の制限はありません。</span><span class="sxs-lookup"><span data-stu-id="874f5-121">There are no restricted characters for the column label.</span></span>

## <a name="remarks"></a><span data-ttu-id="874f5-122">コメント</span><span class="sxs-lookup"><span data-stu-id="874f5-122">Remarks</span></span>

<span data-ttu-id="874f5-123">ラベルが指定されていない場合は、行の値を持つが表示されるプロパティの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="874f5-123">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>

<span data-ttu-id="874f5-124">テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="874f5-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="874f5-125">例</span><span class="sxs-lookup"><span data-stu-id="874f5-125">Example</span></span>

<span data-ttu-id="874f5-126">この例では、`TableColumnHeader`要素のラベルは"Column 1"です。</span><span class="sxs-lookup"><span data-stu-id="874f5-126">This example shows a `TableColumnHeader` element whose label is "Column 1".</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="874f5-127">参照</span><span class="sxs-lookup"><span data-stu-id="874f5-127">See Also</span></span>

[<span data-ttu-id="874f5-128">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="874f5-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="874f5-129">TableColumnHeader 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="874f5-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="874f5-130">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="874f5-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
