---
title: TableControl (形式) の TableColumnHeader 幅要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 94eb0535-8002-4f17-9a2b-4be75ec20e5c
caps.latest.revision: 18
ms.openlocfilehash: 4a25c9d81df670dc10955065bfb66766cdb1bd33
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055191"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="34a2e-102">TableControl の TableColumnHeader の Width 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="34a2e-102">Width Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="34a2e-103">列の幅 (文字) で定義します。</span><span class="sxs-lookup"><span data-stu-id="34a2e-103">Defines the width (in characters) of a column.</span></span>

<span data-ttu-id="34a2e-104">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableHeaders の構成要素の Width 要素によって TableControl (形式) の TableColumnHeader 要素 TableHeaders を TableControl (形式)TableControl (形式) の TableColumnHeader</span><span class="sxs-lookup"><span data-stu-id="34a2e-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element TableHeaders for TableControl (Format) Width Element for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="34a2e-105">構文</span><span class="sxs-lookup"><span data-stu-id="34a2e-105">Syntax</span></span>

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="34a2e-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="34a2e-106">Attributes and Elements</span></span>

<span data-ttu-id="34a2e-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`Width`列ヘッダーを定義するときに使用される要素。</span><span class="sxs-lookup"><span data-stu-id="34a2e-107">The following sections describe the attributes, child elements, and parent element of the `Width` element used when defining column headers.</span></span>

### <a name="attributes"></a><span data-ttu-id="34a2e-108">属性</span><span class="sxs-lookup"><span data-stu-id="34a2e-108">Attributes</span></span>

<span data-ttu-id="34a2e-109">なし。</span><span class="sxs-lookup"><span data-stu-id="34a2e-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="34a2e-110">子要素</span><span class="sxs-lookup"><span data-stu-id="34a2e-110">Child Elements</span></span>

<span data-ttu-id="34a2e-111">なし。</span><span class="sxs-lookup"><span data-stu-id="34a2e-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="34a2e-112">親要素</span><span class="sxs-lookup"><span data-stu-id="34a2e-112">Parent Elements</span></span>

|<span data-ttu-id="34a2e-113">要素</span><span class="sxs-lookup"><span data-stu-id="34a2e-113">Element</span></span>|<span data-ttu-id="34a2e-114">説明</span><span class="sxs-lookup"><span data-stu-id="34a2e-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="34a2e-115">TableControl (形式) の TableHeaders TableColumnHeader 要素</span><span class="sxs-lookup"><span data-stu-id="34a2e-115">TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="34a2e-116">ラベル、幅、およびテーブルの列のデータのアラインメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="34a2e-116">Defines a label, width, and alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="34a2e-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="34a2e-117">Text Value</span></span>

<span data-ttu-id="34a2e-118">すべての可能なである場合に、表示されるプロパティの値の長さを超えている (文字) で幅を指定します。</span><span class="sxs-lookup"><span data-stu-id="34a2e-118">When at all possible, specify a width (in characters) that is greater than the length of the displayed property values.</span></span>

## <a name="remarks"></a><span data-ttu-id="34a2e-119">コメント</span><span class="sxs-lookup"><span data-stu-id="34a2e-119">Remarks</span></span>

<span data-ttu-id="34a2e-120">テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="34a2e-120">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="34a2e-121">例</span><span class="sxs-lookup"><span data-stu-id="34a2e-121">Example</span></span>

<span data-ttu-id="34a2e-122">次の例は、`TableColumnHeader`要素の幅が 16 文字です。</span><span class="sxs-lookup"><span data-stu-id="34a2e-122">The following example shows a `TableColumnHeader` element whose width is 16 characters.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="34a2e-123">参照</span><span class="sxs-lookup"><span data-stu-id="34a2e-123">See Also</span></span>

[<span data-ttu-id="34a2e-124">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="34a2e-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="34a2e-125">TableControl (形式) の TableHeader TableColumnHeader 要素</span><span class="sxs-lookup"><span data-stu-id="34a2e-125">TableColumnHeader Element for TableHeader for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="34a2e-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="34a2e-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
