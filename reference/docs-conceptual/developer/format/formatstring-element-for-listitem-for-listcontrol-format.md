---
title: ListControl の ListItem の FormatString 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd2cac66-88bb-449f-9d47-bd2cd4fe1801
caps.latest.revision: 13
ms.openlocfilehash: e6024ec4f7fc490c92408047c8c15c775e45bf9d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363021"
---
# <a name="formatstring-element-for-listitem-for-listcontrol--format"></a><span data-ttu-id="c4718-102">ListControl の ListItem の FormatString 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c4718-102">FormatString Element for ListItem for ListControl  (Format)</span></span>

<span data-ttu-id="c4718-103">プロパティまたはスクリプトの値の表示方法を定義する形式パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4718-103">Specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="c4718-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (Format) ListEntry Element for ListControl (format) Element for ListItems (format) ListControl Element for (format)ListControl の ListItem の ListControl (Format) FormatString 要素の ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c4718-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem Element for ListControl (Format) FormatString Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c4718-105">構文</span><span class="sxs-lookup"><span data-stu-id="c4718-105">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c4718-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="c4718-106">Attributes and Elements</span></span>

<span data-ttu-id="c4718-107">次のセクションでは、`FormatString` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4718-107">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c4718-108">属性</span><span class="sxs-lookup"><span data-stu-id="c4718-108">Attributes</span></span>

<span data-ttu-id="c4718-109">なし。</span><span class="sxs-lookup"><span data-stu-id="c4718-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c4718-110">子要素</span><span class="sxs-lookup"><span data-stu-id="c4718-110">Child Elements</span></span>

<span data-ttu-id="c4718-111">なし。</span><span class="sxs-lookup"><span data-stu-id="c4718-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c4718-112">親要素</span><span class="sxs-lookup"><span data-stu-id="c4718-112">Parent Elements</span></span>

|<span data-ttu-id="c4718-113">要素</span><span class="sxs-lookup"><span data-stu-id="c4718-113">Element</span></span>|<span data-ttu-id="c4718-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="c4718-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c4718-115">ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c4718-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="c4718-116">リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="c4718-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c4718-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="c4718-117">Text Value</span></span>

<span data-ttu-id="c4718-118">データの書式設定に使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4718-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="c4718-119">たとえば、このパターンを使用すると、型 system.string: {0: MMM} {0: dd} {0: HH}: {0: mm} のプロパティの値を書式設定[できます。](/dotnet/api/System.TimeSpan)</span><span class="sxs-lookup"><span data-stu-id="c4718-119">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="c4718-120">コメント</span><span class="sxs-lookup"><span data-stu-id="c4718-120">Remarks</span></span>

<span data-ttu-id="c4718-121">書式指定文字列は、テーブルビュー、リストビュー、ワイドビュー、またはカスタムビューを作成するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4718-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="c4718-122">ビューに表示される値の書式設定の詳細については、「[表示されるデータの書式設定](./formatting-displayed-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4718-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="c4718-123">リストビューでの書式指定文字列の使用の詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4718-123">For more information about using format strings in list views, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="c4718-124">例</span><span class="sxs-lookup"><span data-stu-id="c4718-124">Example</span></span>

<span data-ttu-id="c4718-125">次の例は、`StartTime` プロパティの値の書式設定文字列を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c4718-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

## <a name="see-also"></a><span data-ttu-id="c4718-126">参照</span><span class="sxs-lookup"><span data-stu-id="c4718-126">See Also</span></span>

[<span data-ttu-id="c4718-127">リストビューの作成</span><span class="sxs-lookup"><span data-stu-id="c4718-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="c4718-128">ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c4718-128">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="c4718-129">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="c4718-129">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
