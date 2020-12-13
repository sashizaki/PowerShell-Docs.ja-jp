---
ms.date: 09/13/2016
ms.topic: reference
title: WideControl の WideItem の FormatString 要素 (書式)
description: WideControl の WideItem の FormatString 要素 (書式)
ms.openlocfilehash: f67a18e3ec4f1323e7f9be8904db518c679d53e5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667880"
---
# <a name="formatstring-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="5fbcd-103">WideControl の WideItem の FormatString 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5fbcd-103">FormatString Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="5fbcd-104">プロパティまたはスクリプトの値をビューに表示する方法を定義する形式パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="5fbcd-104">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>

<span data-ttu-id="5fbcd-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element for WideItem (format) FormatString Element for WideControl (format) WideItem for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="5fbcd-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element for WideControl (Format) WideItem Element for WideControl (Format) FormatString Element for WideItem for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5fbcd-106">構文</span><span class="sxs-lookup"><span data-stu-id="5fbcd-106">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5fbcd-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5fbcd-107">Attributes and Elements</span></span>

<span data-ttu-id="5fbcd-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `FormatString` ます。</span><span class="sxs-lookup"><span data-stu-id="5fbcd-108">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5fbcd-109">属性</span><span class="sxs-lookup"><span data-stu-id="5fbcd-109">Attributes</span></span>

<span data-ttu-id="5fbcd-110">なし。</span><span class="sxs-lookup"><span data-stu-id="5fbcd-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5fbcd-111">子要素</span><span class="sxs-lookup"><span data-stu-id="5fbcd-111">Child Elements</span></span>

<span data-ttu-id="5fbcd-112">なし。</span><span class="sxs-lookup"><span data-stu-id="5fbcd-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5fbcd-113">親要素</span><span class="sxs-lookup"><span data-stu-id="5fbcd-113">Parent Elements</span></span>

|<span data-ttu-id="5fbcd-114">要素</span><span class="sxs-lookup"><span data-stu-id="5fbcd-114">Element</span></span>|<span data-ttu-id="5fbcd-115">説明</span><span class="sxs-lookup"><span data-stu-id="5fbcd-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5fbcd-116">WideControl の WideItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5fbcd-116">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="5fbcd-117">リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="5fbcd-117">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5fbcd-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="5fbcd-118">Text Value</span></span>

<span data-ttu-id="5fbcd-119">データの書式設定に使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="5fbcd-119">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="5fbcd-120">たとえば、このパターンを使用すると、型 system.string: {0: MMM} {0: dd} {0: HH}: {0: mm} のプロパティの値を書式設定[できます。](/dotnet/api/System.TimeSpan)</span><span class="sxs-lookup"><span data-stu-id="5fbcd-120">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="5fbcd-121">解説</span><span class="sxs-lookup"><span data-stu-id="5fbcd-121">Remarks</span></span>

<span data-ttu-id="5fbcd-122">書式指定文字列は、テーブルビュー、リストビュー、ワイドビュー、またはカスタムビューを作成するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="5fbcd-122">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="5fbcd-123">ビューに表示される値の書式設定の詳細については、「 [表示されるデータの書式設定](./formatting-displayed-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fbcd-123">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="5fbcd-124">ワイドビューでの書式指定文字列の使用の詳細については、「 [ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fbcd-124">For more information about using format strings in wide views, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="5fbcd-125">例</span><span class="sxs-lookup"><span data-stu-id="5fbcd-125">Example</span></span>

<span data-ttu-id="5fbcd-126">次の例は、プロパティの値の書式設定文字列を定義する方法を示して `StartTime` います。</span><span class="sxs-lookup"><span data-stu-id="5fbcd-126">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="5fbcd-127">参照</span><span class="sxs-lookup"><span data-stu-id="5fbcd-127">See Also</span></span>

[<span data-ttu-id="5fbcd-128">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="5fbcd-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="5fbcd-129">WideControl の WideItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5fbcd-129">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="5fbcd-130">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="5fbcd-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
