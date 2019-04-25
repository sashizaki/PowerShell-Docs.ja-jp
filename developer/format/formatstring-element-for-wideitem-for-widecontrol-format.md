---
title: FormatString 要素 WideControl (形式) の WideItem |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5bc6ea26-3ca6-4bab-8a13-29189821ba15
caps.latest.revision: 7
ms.openlocfilehash: a1dc145864a6904fd4af6c3b9187819c49e224b0
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065684"
---
# <a name="formatstring-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="9f948-102">WideControl の WideItem の FormatString 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9f948-102">FormatString Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="9f948-103">ビューで、プロパティまたはスクリプトの値を表示する方法を定義するフォーマット パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="9f948-103">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>

<span data-ttu-id="9f948-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素の要素に WideControl (形式) WideItem WideControl (形式) FormatString 要素WideItem WideControl (形式) 用の</span><span class="sxs-lookup"><span data-stu-id="9f948-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element for WideControl (Format) WideItem Element for WideControl (Format) FormatString Element for WideItem for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9f948-105">構文</span><span class="sxs-lookup"><span data-stu-id="9f948-105">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9f948-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9f948-106">Attributes and Elements</span></span>

<span data-ttu-id="9f948-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`FormatString`要素。</span><span class="sxs-lookup"><span data-stu-id="9f948-107">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9f948-108">属性</span><span class="sxs-lookup"><span data-stu-id="9f948-108">Attributes</span></span>

<span data-ttu-id="9f948-109">なし。</span><span class="sxs-lookup"><span data-stu-id="9f948-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9f948-110">子要素</span><span class="sxs-lookup"><span data-stu-id="9f948-110">Child Elements</span></span>

<span data-ttu-id="9f948-111">なし。</span><span class="sxs-lookup"><span data-stu-id="9f948-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9f948-112">親要素</span><span class="sxs-lookup"><span data-stu-id="9f948-112">Parent Elements</span></span>

|<span data-ttu-id="9f948-113">要素</span><span class="sxs-lookup"><span data-stu-id="9f948-113">Element</span></span>|<span data-ttu-id="9f948-114">説明</span><span class="sxs-lookup"><span data-stu-id="9f948-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9f948-115">WideControl (形式) の WideItem 要素</span><span class="sxs-lookup"><span data-stu-id="9f948-115">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="9f948-116">プロパティまたはリスト ビューの行の値が表示されているスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="9f948-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9f948-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="9f948-117">Text Value</span></span>

<span data-ttu-id="9f948-118">データの書式設定に使用されるパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="9f948-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="9f948-119">たとえば、このパターンを使用型の任意のプロパティの値の書式[System.Timespan](/dotnet/api/System.TimeSpan): {0: MMM} {0:dd} {0:HH}: {0:mm}。</span><span class="sxs-lookup"><span data-stu-id="9f948-119">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="9f948-120">コメント</span><span class="sxs-lookup"><span data-stu-id="9f948-120">Remarks</span></span>

<span data-ttu-id="9f948-121">テーブルのビューやリスト ビュー、ワイド ビューは、カスタム ビューを作成するときに、書式指定文字列を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f948-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="9f948-122">ビューに表示される値の書式設定に関する詳細については、次を参照してください。[表示されるデータの書式設定](./formatting-displayed-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="9f948-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="9f948-123">ワイド ビューで書式指定文字列の使用に関する詳細については、次を参照してください。[ワイド ビューを作成する](./creating-a-wide-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="9f948-123">For more information about using format strings in wide views, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="9f948-124">例</span><span class="sxs-lookup"><span data-stu-id="9f948-124">Example</span></span>

<span data-ttu-id="9f948-125">次の例の値の書式指定文字列を定義する方法を示しています、`StartTime`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="9f948-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="9f948-126">参照</span><span class="sxs-lookup"><span data-stu-id="9f948-126">See Also</span></span>

[<span data-ttu-id="9f948-127">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="9f948-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="9f948-128">WideControl (形式) の WideItem 要素</span><span class="sxs-lookup"><span data-stu-id="9f948-128">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="9f948-129">Windows PowerShell の書式設定の書き込みとファイルの種類</span><span class="sxs-lookup"><span data-stu-id="9f948-129">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
