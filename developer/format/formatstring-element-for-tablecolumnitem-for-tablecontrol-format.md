---
title: FormatString 要素 TableControl (形式) の TableColumnItem |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a150731-d4b4-4d63-8db5-f14d463c8c37
caps.latest.revision: 13
ms.openlocfilehash: b7e1d0adc43254141056a729e1c1cc9699b6ac9b
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065633"
---
# <a name="formatstring-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="e11fc-102">TableControl の TableColumnItem の FormatString 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e11fc-102">FormatString Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="e11fc-103">テーブルのプロパティまたはスクリプトの値を表示する方法を定義するフォーマット パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e11fc-103">Specifies a format pattern that defines how the property or script value of the table is displayed.</span></span>

<span data-ttu-id="e11fc-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素 (形式) TableRowEntry 要素 (形式) TableColumnItems 要素 (形式) TableColumnItem 要素 (形式)TableColumnItem (形式) の FormatString 要素</span><span class="sxs-lookup"><span data-stu-id="e11fc-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) FormatString Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e11fc-105">構文</span><span class="sxs-lookup"><span data-stu-id="e11fc-105">Syntax</span></span>

```xml
<FormatString>FormatPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e11fc-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e11fc-106">Attributes and Elements</span></span>

<span data-ttu-id="e11fc-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`FormatString`要素。</span><span class="sxs-lookup"><span data-stu-id="e11fc-107">The following sections describe attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e11fc-108">属性</span><span class="sxs-lookup"><span data-stu-id="e11fc-108">Attributes</span></span>

<span data-ttu-id="e11fc-109">なし。</span><span class="sxs-lookup"><span data-stu-id="e11fc-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e11fc-110">子要素</span><span class="sxs-lookup"><span data-stu-id="e11fc-110">Child Elements</span></span>

<span data-ttu-id="e11fc-111">なし。</span><span class="sxs-lookup"><span data-stu-id="e11fc-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e11fc-112">親要素</span><span class="sxs-lookup"><span data-stu-id="e11fc-112">Parent Elements</span></span>

|<span data-ttu-id="e11fc-113">要素</span><span class="sxs-lookup"><span data-stu-id="e11fc-113">Element</span></span>|<span data-ttu-id="e11fc-114">説明</span><span class="sxs-lookup"><span data-stu-id="e11fc-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e11fc-115">TableColumnItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e11fc-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="e11fc-116">プロパティまたは値を持つが、行の列に表示されているスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="e11fc-116">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e11fc-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="e11fc-117">Text Value</span></span>

<span data-ttu-id="e11fc-118">データの書式設定に使用されるパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e11fc-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="e11fc-119">このパターンを使用して、型の任意のプロパティの値の書式など[System.Timespan](/dotnet/api/System.TimeSpan): {0: MMM} {0:dd} {0:HH}: {0:mm}。</span><span class="sxs-lookup"><span data-stu-id="e11fc-119">For example, this pattern can be used to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="e11fc-120">コメント</span><span class="sxs-lookup"><span data-stu-id="e11fc-120">Remarks</span></span>

<span data-ttu-id="e11fc-121">テーブルのビューやリスト ビュー、ワイド ビューは、カスタム ビューを作成するときに、書式指定文字列を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e11fc-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="e11fc-122">ビューに表示される値の書式設定に関する詳細については、次を参照してください。[表示されるデータの書式設定](./formatting-displayed-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="e11fc-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="e11fc-123">テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビュー](./creating-a-table-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="e11fc-123">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e11fc-124">例</span><span class="sxs-lookup"><span data-stu-id="e11fc-124">Example</span></span>

<span data-ttu-id="e11fc-125">次の例の値の書式指定文字列を定義する方法を示しています、`StartTime`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e11fc-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

## <a name="see-also"></a><span data-ttu-id="e11fc-126">参照</span><span class="sxs-lookup"><span data-stu-id="e11fc-126">See Also</span></span>

[<span data-ttu-id="e11fc-127">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="e11fc-127">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="e11fc-128">表示されるデータの書式設定</span><span class="sxs-lookup"><span data-stu-id="e11fc-128">Formatting Displayed Data</span></span>](./formatting-displayed-data.md)

[<span data-ttu-id="e11fc-129">TableColumnItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e11fc-129">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="e11fc-130">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="e11fc-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
