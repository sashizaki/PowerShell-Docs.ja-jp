---
title: ViewDefinitions 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a108c4f8b03e3dec3905181b390aee2c82ab0028
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772486"
---
# <a name="viewdefinitions-element-format"></a><span data-ttu-id="2867e-102">ViewDefinitions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2867e-102">ViewDefinitions Element (Format)</span></span>

<span data-ttu-id="2867e-103">.NET オブジェクトの表示に使用するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="2867e-103">Defines the views used to display .NET objects.</span></span> <span data-ttu-id="2867e-104">これらのビューでは、オブジェクトのプロパティとスクリプト値をテーブル形式、リスト形式、ワイド形式、およびカスタムコントロール形式で表示できます。</span><span class="sxs-lookup"><span data-stu-id="2867e-104">These views can display the properties and script values of an object  in a table format, list format, wide format, and custom control format.</span></span>

<span data-ttu-id="2867e-105">Configuration 要素 (Format) ViewDefinitions (フォーマット XML) 要素</span><span class="sxs-lookup"><span data-stu-id="2867e-105">Configuration Element (Format) ViewDefinitions (Format XML) Element</span></span>

## <a name="syntax"></a><span data-ttu-id="2867e-106">構文</span><span class="sxs-lookup"><span data-stu-id="2867e-106">Syntax</span></span>

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2867e-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2867e-107">Attributes and Elements</span></span>

<span data-ttu-id="2867e-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ViewDefinitions` ます。</span><span class="sxs-lookup"><span data-stu-id="2867e-108">The following sections describe the attributes, child elements, and parent element of the `ViewDefinitions` element.</span></span> <span data-ttu-id="2867e-109">書式設定ファイルで定義できるビューの数に制限はありません。また、任意の順序で追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="2867e-109">There is no limit to the number of views that can be defined in a formatting file, and they can be added in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="2867e-110">属性</span><span class="sxs-lookup"><span data-stu-id="2867e-110">Attributes</span></span>

<span data-ttu-id="2867e-111">なし。</span><span class="sxs-lookup"><span data-stu-id="2867e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2867e-112">子要素</span><span class="sxs-lookup"><span data-stu-id="2867e-112">Child Elements</span></span>

|<span data-ttu-id="2867e-113">要素</span><span class="sxs-lookup"><span data-stu-id="2867e-113">Element</span></span>|<span data-ttu-id="2867e-114">説明</span><span class="sxs-lookup"><span data-stu-id="2867e-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2867e-115">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2867e-115">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="2867e-116">1つ以上の .NET オブジェクトを表示するために使用されるビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="2867e-116">Defines a view that is used to display one or more .NET objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2867e-117">親要素</span><span class="sxs-lookup"><span data-stu-id="2867e-117">Parent Elements</span></span>

|<span data-ttu-id="2867e-118">要素</span><span class="sxs-lookup"><span data-stu-id="2867e-118">Element</span></span>|<span data-ttu-id="2867e-119">説明</span><span class="sxs-lookup"><span data-stu-id="2867e-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2867e-120">Configuration 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2867e-120">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="2867e-121">書式設定ファイルのトップレベルの要素を表します。</span><span class="sxs-lookup"><span data-stu-id="2867e-121">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2867e-122">解説</span><span class="sxs-lookup"><span data-stu-id="2867e-122">Remarks</span></span>

<span data-ttu-id="2867e-123">さまざまな種類のビューのコンポーネントの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2867e-123">For more information about the components of the different types of views, see the following topics:</span></span>

- [<span data-ttu-id="2867e-124">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="2867e-124">Creating a Table View</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="2867e-125">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="2867e-125">Creating a List View</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="2867e-126">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="2867e-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="2867e-127">カスタムコントロール</span><span class="sxs-lookup"><span data-stu-id="2867e-127">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="2867e-128">例</span><span class="sxs-lookup"><span data-stu-id="2867e-128">Example</span></span>

<span data-ttu-id="2867e-129">この例は、 `ViewDefinitions` テーブルビューとリストビューの親要素を含む要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="2867e-129">This example shows a `ViewDefinitions` element that contains the parent elements for a table view and a list view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2867e-130">参照</span><span class="sxs-lookup"><span data-stu-id="2867e-130">See Also</span></span>

[<span data-ttu-id="2867e-131">Configuration 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2867e-131">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="2867e-132">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2867e-132">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="2867e-133">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="2867e-133">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="2867e-134">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="2867e-134">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="2867e-135">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="2867e-135">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="2867e-136">カスタムコントロール</span><span class="sxs-lookup"><span data-stu-id="2867e-136">Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="2867e-137">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="2867e-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
