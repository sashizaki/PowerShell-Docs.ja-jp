---
title: ViewSelectedBy 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acdeef4d-3554-4f39-a7e6-a684e3848fd7
caps.latest.revision: 19
ms.openlocfilehash: efc1c5d1338889ecd0be7150b7733842ce78979e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083826"
---
# <a name="viewselectedby-element-format"></a><span data-ttu-id="4f95a-102">ViewSelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4f95a-102">ViewSelectedBy Element (Format)</span></span>

<span data-ttu-id="4f95a-103">ビューが表示されている .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="4f95a-103">Defines the .NET objects that are displayed by the view.</span></span> <span data-ttu-id="4f95a-104">それぞれのビューには、少なくとも 1 つの .NET オブジェクトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f95a-104">Each view must specify at least one .NET object.</span></span>

<span data-ttu-id="4f95a-105">ViewDefinitions 要素 (形式) 表示要素 (形式) ViewSelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="4f95a-105">ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4f95a-106">構文</span><span class="sxs-lookup"><span data-stu-id="4f95a-106">Syntax</span></span>

```xml
<ViewSelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
</ViewSelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4f95a-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4f95a-107">Attributes and Elements</span></span>

<span data-ttu-id="4f95a-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`ViewSelectedBy`要素。</span><span class="sxs-lookup"><span data-stu-id="4f95a-108">The following sections describe the attributes, child elements, and parent element of the `ViewSelectedBy` element.</span></span> <span data-ttu-id="4f95a-109">この要素には、少なくとも 1 つ含める必要があります`TypeName`または`SelectionSetName`子要素。</span><span class="sxs-lookup"><span data-stu-id="4f95a-109">This element must contain at least one `TypeName` or `SelectionSetName` child element.</span></span> <span data-ttu-id="4f95a-110">指定できる子要素の数に制限はありません、順序は重要ではもします。</span><span class="sxs-lookup"><span data-stu-id="4f95a-110">There is no limit to the number of child elements that can be specified nor is their order significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="4f95a-111">属性</span><span class="sxs-lookup"><span data-stu-id="4f95a-111">Attributes</span></span>

<span data-ttu-id="4f95a-112">なし。</span><span class="sxs-lookup"><span data-stu-id="4f95a-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4f95a-113">子要素</span><span class="sxs-lookup"><span data-stu-id="4f95a-113">Child Elements</span></span>

|<span data-ttu-id="4f95a-114">要素</span><span class="sxs-lookup"><span data-stu-id="4f95a-114">Element</span></span>|<span data-ttu-id="4f95a-115">説明</span><span class="sxs-lookup"><span data-stu-id="4f95a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4f95a-116">ViewSelectedBy (形式) の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="4f95a-116">TypeName Element for ViewSelectedBy (Format)</span></span>](./typename-element-for-viewselectedby-format.md)|<span data-ttu-id="4f95a-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4f95a-117">Optional element.</span></span><br /><br /> <span data-ttu-id="4f95a-118">ビューが表示されている .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f95a-118">Specifies a .NET object that is displayed by the view.</span></span>|
|[<span data-ttu-id="4f95a-119">ViewSelectedBy (形式) の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="4f95a-119">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)|<span data-ttu-id="4f95a-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="4f95a-120">Optional element.</span></span><br /><br /> <span data-ttu-id="4f95a-121">ビューが表示されている .NET オブジェクトのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f95a-121">Specifies a set of .NET objects that are displayed by the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4f95a-122">親要素</span><span class="sxs-lookup"><span data-stu-id="4f95a-122">Parent Elements</span></span>

|<span data-ttu-id="4f95a-123">要素</span><span class="sxs-lookup"><span data-stu-id="4f95a-123">Element</span></span>|<span data-ttu-id="4f95a-124">説明</span><span class="sxs-lookup"><span data-stu-id="4f95a-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4f95a-125">ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="4f95a-125">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="4f95a-126">1 つまたは複数の .NET オブジェクトを表示するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="4f95a-126">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4f95a-127">コメント</span><span class="sxs-lookup"><span data-stu-id="4f95a-127">Remarks</span></span>

<span data-ttu-id="4f95a-128">さまざまなビューでこの要素の使用方法の詳細については、次を参照してください[テーブル ビュー コンポーネント](./creating-a-table-view.md)、[一覧ビュー コンポーネント](./creating-a-list-view.md)、[ワイド ビュー コンポーネント](./creating-a-wide-view.md)、および[。カスタム コントロール コンポーネント](./creating-custom-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="4f95a-128">For more information about how this element is used in different views, see [Table View Components](./creating-a-table-view.md), [List View Components](./creating-a-list-view.md), [Wide View Components](./creating-a-wide-view.md), and [Custom Control Components](./creating-custom-controls.md).</span></span>

<span data-ttu-id="4f95a-129">`SelectionSetName`要素が書式設定ファイルが複数のビューによって表示されるオブジェクトのセットを定義する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f95a-129">The `SelectionSetName` element is used when the formatting file defines a set of objects that are displayed by multiple views.</span></span> <span data-ttu-id="4f95a-130">選択範囲のセットを定義し、参照する方法の詳細については、次を参照してください。[オブジェクト設定を定義する](./defining-selection-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="4f95a-130">For more information about how selection sets are defined and referenced, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="4f95a-131">例</span><span class="sxs-lookup"><span data-stu-id="4f95a-131">Example</span></span>

<span data-ttu-id="4f95a-132">次の例は、指定する方法を示します、 [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)のリスト ビューのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4f95a-132">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="4f95a-133">テーブルの幅をカスタム ビューに同じスキーマが使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f95a-133">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="4f95a-134">参照</span><span class="sxs-lookup"><span data-stu-id="4f95a-134">See Also</span></span>

[<span data-ttu-id="4f95a-135">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="4f95a-135">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="4f95a-136">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f95a-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="4f95a-137">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f95a-137">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="4f95a-138">カスタム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="4f95a-138">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="4f95a-139">選択範囲のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="4f95a-139">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="4f95a-140">ViewSelectedBy (形式) の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="4f95a-140">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

[<span data-ttu-id="4f95a-141">TypeName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="4f95a-141">TypeName Element (Format)</span></span>](./typename-element-for-viewselectedby-format.md)

[<span data-ttu-id="4f95a-142">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="4f95a-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
