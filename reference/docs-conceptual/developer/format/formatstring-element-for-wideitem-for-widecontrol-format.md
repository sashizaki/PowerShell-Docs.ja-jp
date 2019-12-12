---
title: WideControl の WideItem の FormatString 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5bc6ea26-3ca6-4bab-8a13-29189821ba15
caps.latest.revision: 7
ms.openlocfilehash: a1dc145864a6904fd4af6c3b9187819c49e224b0
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363031"
---
# <a name="formatstring-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="7764d-102">WideControl の WideItem の FormatString 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7764d-102">FormatString Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="7764d-103">プロパティまたはスクリプトの値をビューに表示する方法を定義する形式パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="7764d-103">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>

<span data-ttu-id="7764d-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl 要素 (format) WideEntries Element (format) WideEntry Element for WideItem (format) FormatString 要素の WideControl (Format) WideControl 要素for WideItem for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="7764d-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element for WideControl (Format) WideItem Element for WideControl (Format) FormatString Element for WideItem for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7764d-105">構文</span><span class="sxs-lookup"><span data-stu-id="7764d-105">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7764d-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="7764d-106">Attributes and Elements</span></span>

<span data-ttu-id="7764d-107">次のセクションでは、`FormatString` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7764d-107">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7764d-108">属性</span><span class="sxs-lookup"><span data-stu-id="7764d-108">Attributes</span></span>

<span data-ttu-id="7764d-109">なし。</span><span class="sxs-lookup"><span data-stu-id="7764d-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7764d-110">子要素</span><span class="sxs-lookup"><span data-stu-id="7764d-110">Child Elements</span></span>

<span data-ttu-id="7764d-111">なし。</span><span class="sxs-lookup"><span data-stu-id="7764d-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7764d-112">親要素</span><span class="sxs-lookup"><span data-stu-id="7764d-112">Parent Elements</span></span>

|<span data-ttu-id="7764d-113">要素</span><span class="sxs-lookup"><span data-stu-id="7764d-113">Element</span></span>|<span data-ttu-id="7764d-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="7764d-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7764d-115">WideControl の WideItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7764d-115">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="7764d-116">リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="7764d-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7764d-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="7764d-117">Text Value</span></span>

<span data-ttu-id="7764d-118">データの書式設定に使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="7764d-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="7764d-119">たとえば、このパターンを使用すると、型 system.string: {0: MMM} {0: dd} {0: HH}: {0: mm} のプロパティの値を書式設定[できます。](/dotnet/api/System.TimeSpan)</span><span class="sxs-lookup"><span data-stu-id="7764d-119">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="7764d-120">コメント</span><span class="sxs-lookup"><span data-stu-id="7764d-120">Remarks</span></span>

<span data-ttu-id="7764d-121">書式指定文字列は、テーブルビュー、リストビュー、ワイドビュー、またはカスタムビューを作成するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="7764d-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="7764d-122">ビューに表示される値の書式設定の詳細については、「[表示されるデータの書式設定](./formatting-displayed-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7764d-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="7764d-123">ワイドビューでの書式指定文字列の使用の詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7764d-123">For more information about using format strings in wide views, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="7764d-124">例</span><span class="sxs-lookup"><span data-stu-id="7764d-124">Example</span></span>

<span data-ttu-id="7764d-125">次の例は、`StartTime` プロパティの値の書式設定文字列を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7764d-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="7764d-126">参照</span><span class="sxs-lookup"><span data-stu-id="7764d-126">See Also</span></span>

[<span data-ttu-id="7764d-127">ワイドビューの作成</span><span class="sxs-lookup"><span data-stu-id="7764d-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="7764d-128">WideControl の WideItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7764d-128">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="7764d-129">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="7764d-129">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
