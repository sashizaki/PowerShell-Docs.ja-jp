---
title: TableControl (Format) の TableColumnItem の FormatString 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a150731-d4b4-4d63-8db5-f14d463c8c37
caps.latest.revision: 13
ms.openlocfilehash: b7e1d0adc43254141056a729e1c1cc9699b6ac9b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363711"
---
# <a name="formatstring-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="fe4dd-102">TableControl の TableColumnItem の FormatString 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="fe4dd-102">FormatString Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="fe4dd-103">テーブルのプロパティまたはスクリプトの値の表示方法を定義する形式パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe4dd-103">Specifies a format pattern that defines how the property or script value of the table is displayed.</span></span>

<span data-ttu-id="fe4dd-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) TableColumnItems Element (format) TableColumnItem Element (Format)TableColumnItem の FormatString 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="fe4dd-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) FormatString Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fe4dd-105">構文</span><span class="sxs-lookup"><span data-stu-id="fe4dd-105">Syntax</span></span>

```xml
<FormatString>FormatPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fe4dd-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="fe4dd-106">Attributes and Elements</span></span>

<span data-ttu-id="fe4dd-107">次のセクションでは、属性、子要素、`FormatString` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe4dd-107">The following sections describe attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fe4dd-108">属性</span><span class="sxs-lookup"><span data-stu-id="fe4dd-108">Attributes</span></span>

<span data-ttu-id="fe4dd-109">なし。</span><span class="sxs-lookup"><span data-stu-id="fe4dd-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fe4dd-110">子要素</span><span class="sxs-lookup"><span data-stu-id="fe4dd-110">Child Elements</span></span>

<span data-ttu-id="fe4dd-111">なし。</span><span class="sxs-lookup"><span data-stu-id="fe4dd-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fe4dd-112">親要素</span><span class="sxs-lookup"><span data-stu-id="fe4dd-112">Parent Elements</span></span>

|<span data-ttu-id="fe4dd-113">要素</span><span class="sxs-lookup"><span data-stu-id="fe4dd-113">Element</span></span>|<span data-ttu-id="fe4dd-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="fe4dd-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fe4dd-115">TableColumnItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="fe4dd-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="fe4dd-116">行の列に値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="fe4dd-116">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fe4dd-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="fe4dd-117">Text Value</span></span>

<span data-ttu-id="fe4dd-118">データの書式設定に使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe4dd-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="fe4dd-119">たとえば、このパターンを使用して、型が system.string のプロパティの値を書式設定することができ[ます。 Timespan](/dotnet/api/System.TimeSpan): {0: MMM} {0: dd} {0: HH}: {0: mm}。</span><span class="sxs-lookup"><span data-stu-id="fe4dd-119">For example, this pattern can be used to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="fe4dd-120">コメント</span><span class="sxs-lookup"><span data-stu-id="fe4dd-120">Remarks</span></span>

<span data-ttu-id="fe4dd-121">書式指定文字列は、テーブルビュー、リストビュー、ワイドビュー、またはカスタムビューを作成するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe4dd-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="fe4dd-122">ビューに表示される値の書式設定の詳細については、「[表示されるデータの書式設定](./formatting-displayed-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe4dd-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="fe4dd-123">テーブルビューのコンポーネントの詳細については、「[テーブルビュー](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe4dd-123">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="fe4dd-124">例</span><span class="sxs-lookup"><span data-stu-id="fe4dd-124">Example</span></span>

<span data-ttu-id="fe4dd-125">次の例は、`StartTime` プロパティの値の書式設定文字列を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fe4dd-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

## <a name="see-also"></a><span data-ttu-id="fe4dd-126">参照</span><span class="sxs-lookup"><span data-stu-id="fe4dd-126">See Also</span></span>

[<span data-ttu-id="fe4dd-127">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="fe4dd-127">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="fe4dd-128">表示データの書式設定</span><span class="sxs-lookup"><span data-stu-id="fe4dd-128">Formatting Displayed Data</span></span>](./formatting-displayed-data.md)

[<span data-ttu-id="fe4dd-129">TableColumnItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="fe4dd-129">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="fe4dd-130">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="fe4dd-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
