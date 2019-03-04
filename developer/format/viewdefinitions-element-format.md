---
title: ViewDefinitions 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29840c10-2b30-4bb1-a8a0-ddf84d19c2d0
caps.latest.revision: 18
ms.openlocfilehash: c5ec80350c7707ccd41112ab5e1952e5dc198cca
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862088"
---
# <a name="viewdefinitions-element-format"></a><span data-ttu-id="f00b3-102">ViewDefinitions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f00b3-102">ViewDefinitions Element (Format)</span></span>

<span data-ttu-id="f00b3-103">.NET オブジェクトを表示するために使用するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="f00b3-103">Defines the views used to display .NET objects.</span></span> <span data-ttu-id="f00b3-104">これらのビューでは、プロパティとオブジェクトのスクリプトの値をテーブル形式、一覧の形式、ワイド形式、およびカスタム コントロールの形式で表示できます。</span><span class="sxs-lookup"><span data-stu-id="f00b3-104">These views can display the properties and script values of an object  in a table format, list format, wide format, and custom control format.</span></span>

<span data-ttu-id="f00b3-105">構成要素 (形式) (XML 形式) ViewDefinitions 要素</span><span class="sxs-lookup"><span data-stu-id="f00b3-105">Configuration Element (Format) ViewDefinitions (Format XML) Element</span></span>

## <a name="syntax"></a><span data-ttu-id="f00b3-106">構文</span><span class="sxs-lookup"><span data-stu-id="f00b3-106">Syntax</span></span>

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f00b3-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="f00b3-107">Attributes and Elements</span></span>

<span data-ttu-id="f00b3-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`ViewDefinitions`要素。</span><span class="sxs-lookup"><span data-stu-id="f00b3-108">The following sections describe the attributes, child elements, and parent element of the `ViewDefinitions` element.</span></span> <span data-ttu-id="f00b3-109">書式設定ファイルで定義できるビューの数に制限はありませんし、任意の順序で追加できます。</span><span class="sxs-lookup"><span data-stu-id="f00b3-109">There is no limit to the number of views that can be defined in a formatting file, and they can be added in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="f00b3-110">属性</span><span class="sxs-lookup"><span data-stu-id="f00b3-110">Attributes</span></span>

<span data-ttu-id="f00b3-111">なし。</span><span class="sxs-lookup"><span data-stu-id="f00b3-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f00b3-112">子要素</span><span class="sxs-lookup"><span data-stu-id="f00b3-112">Child Elements</span></span>

|<span data-ttu-id="f00b3-113">要素</span><span class="sxs-lookup"><span data-stu-id="f00b3-113">Element</span></span>|<span data-ttu-id="f00b3-114">説明</span><span class="sxs-lookup"><span data-stu-id="f00b3-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f00b3-115">ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="f00b3-115">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="f00b3-116">1 つまたは複数の .NET オブジェクトを表示するために使用するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="f00b3-116">Defines a view that is used to display one or more .NET objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f00b3-117">親要素</span><span class="sxs-lookup"><span data-stu-id="f00b3-117">Parent Elements</span></span>

|<span data-ttu-id="f00b3-118">要素</span><span class="sxs-lookup"><span data-stu-id="f00b3-118">Element</span></span>|<span data-ttu-id="f00b3-119">説明</span><span class="sxs-lookup"><span data-stu-id="f00b3-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f00b3-120">構成要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="f00b3-120">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="f00b3-121">書式設定ファイルの最上位の要素を表します。</span><span class="sxs-lookup"><span data-stu-id="f00b3-121">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f00b3-122">コメント</span><span class="sxs-lookup"><span data-stu-id="f00b3-122">Remarks</span></span>

<span data-ttu-id="f00b3-123">ビューのさまざまな種類のコンポーネントの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f00b3-123">For more information about the components of the different types of views, see the following topics:</span></span>

- [<span data-ttu-id="f00b3-124">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="f00b3-124">Creating a Table View</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="f00b3-125">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="f00b3-125">Creating a List View</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="f00b3-126">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="f00b3-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="f00b3-127">カスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="f00b3-127">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="f00b3-128">例</span><span class="sxs-lookup"><span data-stu-id="f00b3-128">Example</span></span>

<span data-ttu-id="f00b3-129">この例では、`ViewDefinitions`テーブル ビューとリスト ビューの親要素を含む要素。</span><span class="sxs-lookup"><span data-stu-id="f00b3-129">This example shows a `ViewDefinitions` element that contains the parent elements for a table view and a list view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f00b3-130">参照</span><span class="sxs-lookup"><span data-stu-id="f00b3-130">See Also</span></span>

[<span data-ttu-id="f00b3-131">構成要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="f00b3-131">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="f00b3-132">ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="f00b3-132">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="f00b3-133">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="f00b3-133">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="f00b3-134">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="f00b3-134">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="f00b3-135">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="f00b3-135">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="f00b3-136">カスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="f00b3-136">Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="f00b3-137">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="f00b3-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
