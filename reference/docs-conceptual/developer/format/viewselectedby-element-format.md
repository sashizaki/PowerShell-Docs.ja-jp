---
title: ViewSelectedBy 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c8704c1504c6e24c9cac6bc8bc25e92a0d9110cc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785015"
---
# <a name="viewselectedby-element-format"></a><span data-ttu-id="e2ba4-102">ViewSelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e2ba4-102">ViewSelectedBy Element (Format)</span></span>

<span data-ttu-id="e2ba4-103">ビューに表示される .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="e2ba4-103">Defines the .NET objects that are displayed by the view.</span></span> <span data-ttu-id="e2ba4-104">各ビューには、少なくとも1つの .NET オブジェクトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2ba4-104">Each view must specify at least one .NET object.</span></span>

<span data-ttu-id="e2ba4-105">ViewDefinitions 要素 (Format) ビュー要素 (形式) ViewSelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e2ba4-105">ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e2ba4-106">構文</span><span class="sxs-lookup"><span data-stu-id="e2ba4-106">Syntax</span></span>

```xml
<ViewSelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
</ViewSelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e2ba4-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e2ba4-107">Attributes and Elements</span></span>

<span data-ttu-id="e2ba4-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ViewSelectedBy` ます。</span><span class="sxs-lookup"><span data-stu-id="e2ba4-108">The following sections describe the attributes, child elements, and parent element of the `ViewSelectedBy` element.</span></span> <span data-ttu-id="e2ba4-109">この要素に `TypeName` は、少なくとも1つの要素または子要素を含める必要があり `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="e2ba4-109">This element must contain at least one `TypeName` or `SelectionSetName` child element.</span></span> <span data-ttu-id="e2ba4-110">指定できる子要素の数に制限はありません。また、順序が重要でもありません。</span><span class="sxs-lookup"><span data-stu-id="e2ba4-110">There is no limit to the number of child elements that can be specified nor is their order significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="e2ba4-111">属性</span><span class="sxs-lookup"><span data-stu-id="e2ba4-111">Attributes</span></span>

<span data-ttu-id="e2ba4-112">なし。</span><span class="sxs-lookup"><span data-stu-id="e2ba4-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e2ba4-113">子要素</span><span class="sxs-lookup"><span data-stu-id="e2ba4-113">Child Elements</span></span>

|<span data-ttu-id="e2ba4-114">要素</span><span class="sxs-lookup"><span data-stu-id="e2ba4-114">Element</span></span>|<span data-ttu-id="e2ba4-115">説明</span><span class="sxs-lookup"><span data-stu-id="e2ba4-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e2ba4-116">ViewSelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e2ba4-116">TypeName Element for ViewSelectedBy (Format)</span></span>](./typename-element-for-viewselectedby-format.md)|<span data-ttu-id="e2ba4-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e2ba4-117">Optional element.</span></span><br /><br /> <span data-ttu-id="e2ba4-118">ビューに表示される .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e2ba4-118">Specifies a .NET object that is displayed by the view.</span></span>|
|[<span data-ttu-id="e2ba4-119">ViewSelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e2ba4-119">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)|<span data-ttu-id="e2ba4-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e2ba4-120">Optional element.</span></span><br /><br /> <span data-ttu-id="e2ba4-121">ビューに表示される一連の .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e2ba4-121">Specifies a set of .NET objects that are displayed by the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e2ba4-122">親要素</span><span class="sxs-lookup"><span data-stu-id="e2ba4-122">Parent Elements</span></span>

|<span data-ttu-id="e2ba4-123">要素</span><span class="sxs-lookup"><span data-stu-id="e2ba4-123">Element</span></span>|<span data-ttu-id="e2ba4-124">説明</span><span class="sxs-lookup"><span data-stu-id="e2ba4-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e2ba4-125">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e2ba4-125">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="e2ba4-126">1つ以上の .NET オブジェクトを表示するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="e2ba4-126">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e2ba4-127">解説</span><span class="sxs-lookup"><span data-stu-id="e2ba4-127">Remarks</span></span>

<span data-ttu-id="e2ba4-128">この要素をさまざまなビューで使用する方法の詳細については、「[テーブルビューコンポーネント](./creating-a-table-view.md)」、「[リストビュー](./creating-a-list-view.md)コンポーネント」、「[ワイドビューコンポーネント](./creating-a-wide-view.md)」、および「[カスタムコントロールコンポーネント](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2ba4-128">For more information about how this element is used in different views, see [Table View Components](./creating-a-table-view.md), [List View Components](./creating-a-list-view.md), [Wide View Components](./creating-a-wide-view.md), and [Custom Control Components](./creating-custom-controls.md).</span></span>

<span data-ttu-id="e2ba4-129">要素は、 `SelectionSetName` 書式設定ファイルが複数のビューによって表示されるオブジェクトのセットを定義する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2ba4-129">The `SelectionSetName` element is used when the formatting file defines a set of objects that are displayed by multiple views.</span></span> <span data-ttu-id="e2ba4-130">選択セットを定義および参照する方法の詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2ba4-130">For more information about how selection sets are defined and referenced, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="e2ba4-131">例</span><span class="sxs-lookup"><span data-stu-id="e2ba4-131">Example</span></span>

<span data-ttu-id="e2ba4-132">リストビューの[Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトを指定する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="e2ba4-132">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="e2ba4-133">テーブル、ワイド、およびカスタムビューでも同じスキーマが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2ba4-133">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="e2ba4-134">参照</span><span class="sxs-lookup"><span data-stu-id="e2ba4-134">See Also</span></span>

[<span data-ttu-id="e2ba4-135">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="e2ba4-135">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="e2ba4-136">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="e2ba4-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="e2ba4-137">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="e2ba4-137">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="e2ba4-138">カスタム コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="e2ba4-138">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="e2ba4-139">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="e2ba4-139">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="e2ba4-140">ViewSelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e2ba4-140">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

[<span data-ttu-id="e2ba4-141">TypeName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="e2ba4-141">TypeName Element (Format)</span></span>](./typename-element-for-viewselectedby-format.md)

[<span data-ttu-id="e2ba4-142">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="e2ba4-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
