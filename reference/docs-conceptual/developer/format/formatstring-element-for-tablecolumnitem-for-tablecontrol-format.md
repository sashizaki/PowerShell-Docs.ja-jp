---
title: TableControl (Format) の TableColumnItem の FormatString 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 848583e697d0ab7bd5b017c14c47aba3c51a3c17
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781547"
---
# <a name="formatstring-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="46639-102">TableControl の TableColumnItem の FormatString 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="46639-102">FormatString Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="46639-103">テーブルのプロパティまたはスクリプトの値の表示方法を定義する形式パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="46639-103">Specifies a format pattern that defines how the property or script value of the table is displayed.</span></span>

<span data-ttu-id="46639-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) TableColumnItems Element (format) TableColumnItem Element (format) TableColumnItem (format) の FormatString 要素</span><span class="sxs-lookup"><span data-stu-id="46639-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) FormatString Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="46639-105">構文</span><span class="sxs-lookup"><span data-stu-id="46639-105">Syntax</span></span>

```xml
<FormatString>FormatPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="46639-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="46639-106">Attributes and Elements</span></span>

<span data-ttu-id="46639-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `FormatString` ます。</span><span class="sxs-lookup"><span data-stu-id="46639-107">The following sections describe attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="46639-108">属性</span><span class="sxs-lookup"><span data-stu-id="46639-108">Attributes</span></span>

<span data-ttu-id="46639-109">なし。</span><span class="sxs-lookup"><span data-stu-id="46639-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="46639-110">子要素</span><span class="sxs-lookup"><span data-stu-id="46639-110">Child Elements</span></span>

<span data-ttu-id="46639-111">なし。</span><span class="sxs-lookup"><span data-stu-id="46639-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="46639-112">親要素</span><span class="sxs-lookup"><span data-stu-id="46639-112">Parent Elements</span></span>

|<span data-ttu-id="46639-113">要素</span><span class="sxs-lookup"><span data-stu-id="46639-113">Element</span></span>|<span data-ttu-id="46639-114">説明</span><span class="sxs-lookup"><span data-stu-id="46639-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="46639-115">TableColumnItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="46639-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="46639-116">行の列に値が表示されるプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="46639-116">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="46639-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="46639-117">Text Value</span></span>

<span data-ttu-id="46639-118">データの書式設定に使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="46639-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="46639-119">たとえば、このパターンを使用して、型が system.string のプロパティの値を書式設定することができ[ます。 Timespan](/dotnet/api/System.TimeSpan): {0: MMM} {0: dd} {0: HH}: {0: mm}。</span><span class="sxs-lookup"><span data-stu-id="46639-119">For example, this pattern can be used to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="46639-120">解説</span><span class="sxs-lookup"><span data-stu-id="46639-120">Remarks</span></span>

<span data-ttu-id="46639-121">書式指定文字列は、テーブルビュー、リストビュー、ワイドビュー、またはカスタムビューを作成するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="46639-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="46639-122">ビューに表示される値の書式設定の詳細については、「[表示されるデータの書式設定](./formatting-displayed-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46639-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="46639-123">テーブルビューのコンポーネントの詳細については、「[テーブルビュー](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46639-123">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="46639-124">例</span><span class="sxs-lookup"><span data-stu-id="46639-124">Example</span></span>

<span data-ttu-id="46639-125">次の例は、プロパティの値の書式設定文字列を定義する方法を示して `StartTime` います。</span><span class="sxs-lookup"><span data-stu-id="46639-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

## <a name="see-also"></a><span data-ttu-id="46639-126">参照</span><span class="sxs-lookup"><span data-stu-id="46639-126">See Also</span></span>

[<span data-ttu-id="46639-127">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="46639-127">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="46639-128">表示されるデータの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="46639-128">Formatting Displayed Data</span></span>](./formatting-displayed-data.md)

[<span data-ttu-id="46639-129">TableColumnItem 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="46639-129">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="46639-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="46639-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
