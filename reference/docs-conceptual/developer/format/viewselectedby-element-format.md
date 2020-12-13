---
ms.date: 09/13/2016
ms.topic: reference
title: ViewSelectedBy 要素 (書式)
description: ViewSelectedBy 要素 (書式)
ms.openlocfilehash: ac3c7de299b3009a067a476a024c6a6fcb5dce02
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667710"
---
# <a name="viewselectedby-element-format"></a><span data-ttu-id="c4eb8-103">ViewSelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c4eb8-103">ViewSelectedBy Element (Format)</span></span>

<span data-ttu-id="c4eb8-104">ビューに表示される .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="c4eb8-104">Defines the .NET objects that are displayed by the view.</span></span> <span data-ttu-id="c4eb8-105">各ビューには、少なくとも1つの .NET オブジェクトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4eb8-105">Each view must specify at least one .NET object.</span></span>

<span data-ttu-id="c4eb8-106">ViewDefinitions 要素 (Format) ビュー要素 (形式) ViewSelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c4eb8-106">ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c4eb8-107">構文</span><span class="sxs-lookup"><span data-stu-id="c4eb8-107">Syntax</span></span>

```xml
<ViewSelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
</ViewSelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c4eb8-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c4eb8-108">Attributes and Elements</span></span>

<span data-ttu-id="c4eb8-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ViewSelectedBy` ます。</span><span class="sxs-lookup"><span data-stu-id="c4eb8-109">The following sections describe the attributes, child elements, and parent element of the `ViewSelectedBy` element.</span></span> <span data-ttu-id="c4eb8-110">この要素に `TypeName` は、少なくとも1つの要素または子要素を含める必要があり `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="c4eb8-110">This element must contain at least one `TypeName` or `SelectionSetName` child element.</span></span> <span data-ttu-id="c4eb8-111">指定できる子要素の数に制限はありません。また、順序が重要でもありません。</span><span class="sxs-lookup"><span data-stu-id="c4eb8-111">There is no limit to the number of child elements that can be specified nor is their order significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="c4eb8-112">属性</span><span class="sxs-lookup"><span data-stu-id="c4eb8-112">Attributes</span></span>

<span data-ttu-id="c4eb8-113">なし。</span><span class="sxs-lookup"><span data-stu-id="c4eb8-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c4eb8-114">子要素</span><span class="sxs-lookup"><span data-stu-id="c4eb8-114">Child Elements</span></span>

|<span data-ttu-id="c4eb8-115">要素</span><span class="sxs-lookup"><span data-stu-id="c4eb8-115">Element</span></span>|<span data-ttu-id="c4eb8-116">説明</span><span class="sxs-lookup"><span data-stu-id="c4eb8-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c4eb8-117">ViewSelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c4eb8-117">TypeName Element for ViewSelectedBy (Format)</span></span>](./typename-element-for-viewselectedby-format.md)|<span data-ttu-id="c4eb8-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c4eb8-118">Optional element.</span></span><br /><br /> <span data-ttu-id="c4eb8-119">ビューに表示される .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4eb8-119">Specifies a .NET object that is displayed by the view.</span></span>|
|[<span data-ttu-id="c4eb8-120">ViewSelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c4eb8-120">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)|<span data-ttu-id="c4eb8-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="c4eb8-121">Optional element.</span></span><br /><br /> <span data-ttu-id="c4eb8-122">ビューに表示される一連の .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4eb8-122">Specifies a set of .NET objects that are displayed by the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c4eb8-123">親要素</span><span class="sxs-lookup"><span data-stu-id="c4eb8-123">Parent Elements</span></span>

|<span data-ttu-id="c4eb8-124">要素</span><span class="sxs-lookup"><span data-stu-id="c4eb8-124">Element</span></span>|<span data-ttu-id="c4eb8-125">説明</span><span class="sxs-lookup"><span data-stu-id="c4eb8-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c4eb8-126">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c4eb8-126">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="c4eb8-127">1つ以上の .NET オブジェクトを表示するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="c4eb8-127">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c4eb8-128">解説</span><span class="sxs-lookup"><span data-stu-id="c4eb8-128">Remarks</span></span>

<span data-ttu-id="c4eb8-129">この要素をさまざまなビューで使用する方法の詳細については、「 [テーブルビューコンポーネント](./creating-a-table-view.md)」、「 [リストビュー](./creating-a-list-view.md)コンポーネント」、「 [ワイドビューコンポーネント](./creating-a-wide-view.md)」、および「 [カスタムコントロールコンポーネント](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4eb8-129">For more information about how this element is used in different views, see [Table View Components](./creating-a-table-view.md), [List View Components](./creating-a-list-view.md), [Wide View Components](./creating-a-wide-view.md), and [Custom Control Components](./creating-custom-controls.md).</span></span>

<span data-ttu-id="c4eb8-130">要素は、 `SelectionSetName` 書式設定ファイルが複数のビューによって表示されるオブジェクトのセットを定義する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4eb8-130">The `SelectionSetName` element is used when the formatting file defines a set of objects that are displayed by multiple views.</span></span> <span data-ttu-id="c4eb8-131">選択セットを定義および参照する方法の詳細については、「 [オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4eb8-131">For more information about how selection sets are defined and referenced, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="c4eb8-132">例</span><span class="sxs-lookup"><span data-stu-id="c4eb8-132">Example</span></span>

<span data-ttu-id="c4eb8-133">リストビューの [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) オブジェクトを指定する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="c4eb8-133">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="c4eb8-134">テーブル、ワイド、およびカスタムビューでも同じスキーマが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4eb8-134">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="c4eb8-135">参照</span><span class="sxs-lookup"><span data-stu-id="c4eb8-135">See Also</span></span>

[<span data-ttu-id="c4eb8-136">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="c4eb8-136">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="c4eb8-137">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="c4eb8-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="c4eb8-138">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="c4eb8-138">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="c4eb8-139">カスタム コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="c4eb8-139">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="c4eb8-140">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="c4eb8-140">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="c4eb8-141">ViewSelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c4eb8-141">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

[<span data-ttu-id="c4eb8-142">TypeName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c4eb8-142">TypeName Element (Format)</span></span>](./typename-element-for-viewselectedby-format.md)

[<span data-ttu-id="c4eb8-143">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="c4eb8-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
