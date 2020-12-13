---
ms.date: 09/13/2016
ms.topic: reference
title: ViewDefinitions 要素 (書式)
description: ViewDefinitions 要素 (書式)
ms.openlocfilehash: fceef0e5ec91e8c59a7b2b90fd31ca422ff0c94d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664588"
---
# <a name="viewdefinitions-element-format"></a><span data-ttu-id="58c91-103">ViewDefinitions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="58c91-103">ViewDefinitions Element (Format)</span></span>

<span data-ttu-id="58c91-104">.NET オブジェクトの表示に使用するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="58c91-104">Defines the views used to display .NET objects.</span></span> <span data-ttu-id="58c91-105">これらのビューでは、オブジェクトのプロパティとスクリプト値をテーブル形式、リスト形式、ワイド形式、およびカスタムコントロール形式で表示できます。</span><span class="sxs-lookup"><span data-stu-id="58c91-105">These views can display the properties and script values of an object  in a table format, list format, wide format, and custom control format.</span></span>

<span data-ttu-id="58c91-106">Configuration 要素 (Format) ViewDefinitions (フォーマット XML) 要素</span><span class="sxs-lookup"><span data-stu-id="58c91-106">Configuration Element (Format) ViewDefinitions (Format XML) Element</span></span>

## <a name="syntax"></a><span data-ttu-id="58c91-107">構文</span><span class="sxs-lookup"><span data-stu-id="58c91-107">Syntax</span></span>

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="58c91-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="58c91-108">Attributes and Elements</span></span>

<span data-ttu-id="58c91-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ViewDefinitions` ます。</span><span class="sxs-lookup"><span data-stu-id="58c91-109">The following sections describe the attributes, child elements, and parent element of the `ViewDefinitions` element.</span></span> <span data-ttu-id="58c91-110">書式設定ファイルで定義できるビューの数に制限はありません。また、任意の順序で追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="58c91-110">There is no limit to the number of views that can be defined in a formatting file, and they can be added in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="58c91-111">属性</span><span class="sxs-lookup"><span data-stu-id="58c91-111">Attributes</span></span>

<span data-ttu-id="58c91-112">なし。</span><span class="sxs-lookup"><span data-stu-id="58c91-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="58c91-113">子要素</span><span class="sxs-lookup"><span data-stu-id="58c91-113">Child Elements</span></span>

|<span data-ttu-id="58c91-114">要素</span><span class="sxs-lookup"><span data-stu-id="58c91-114">Element</span></span>|<span data-ttu-id="58c91-115">説明</span><span class="sxs-lookup"><span data-stu-id="58c91-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="58c91-116">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="58c91-116">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="58c91-117">1つ以上の .NET オブジェクトを表示するために使用されるビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="58c91-117">Defines a view that is used to display one or more .NET objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="58c91-118">親要素</span><span class="sxs-lookup"><span data-stu-id="58c91-118">Parent Elements</span></span>

|<span data-ttu-id="58c91-119">要素</span><span class="sxs-lookup"><span data-stu-id="58c91-119">Element</span></span>|<span data-ttu-id="58c91-120">説明</span><span class="sxs-lookup"><span data-stu-id="58c91-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="58c91-121">Configuration 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="58c91-121">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="58c91-122">書式設定ファイルのトップレベルの要素を表します。</span><span class="sxs-lookup"><span data-stu-id="58c91-122">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="58c91-123">解説</span><span class="sxs-lookup"><span data-stu-id="58c91-123">Remarks</span></span>

<span data-ttu-id="58c91-124">さまざまな種類のビューのコンポーネントの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="58c91-124">For more information about the components of the different types of views, see the following topics:</span></span>

- [<span data-ttu-id="58c91-125">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="58c91-125">Creating a Table View</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="58c91-126">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="58c91-126">Creating a List View</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="58c91-127">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="58c91-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="58c91-128">カスタムコントロール</span><span class="sxs-lookup"><span data-stu-id="58c91-128">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="58c91-129">例</span><span class="sxs-lookup"><span data-stu-id="58c91-129">Example</span></span>

<span data-ttu-id="58c91-130">この例は、 `ViewDefinitions` テーブルビューとリストビューの親要素を含む要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="58c91-130">This example shows a `ViewDefinitions` element that contains the parent elements for a table view and a list view.</span></span>

```xml
<Configuration>
  <ViewDefinitions>
    <View>
      <TableControl>...</TableControl>
    </View>
    <View>
      <ListControl>...</ListControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

## <a name="see-also"></a><span data-ttu-id="58c91-131">参照</span><span class="sxs-lookup"><span data-stu-id="58c91-131">See Also</span></span>

[<span data-ttu-id="58c91-132">Configuration 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="58c91-132">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="58c91-133">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="58c91-133">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="58c91-134">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="58c91-134">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="58c91-135">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="58c91-135">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="58c91-136">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="58c91-136">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="58c91-137">カスタムコントロール</span><span class="sxs-lookup"><span data-stu-id="58c91-137">Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="58c91-138">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="58c91-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
