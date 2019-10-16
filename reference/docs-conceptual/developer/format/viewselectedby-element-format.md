---
title: ViewSelectedBy 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acdeef4d-3554-4f39-a7e6-a684e3848fd7
caps.latest.revision: 19
ms.openlocfilehash: efc1c5d1338889ecd0be7150b7733842ce78979e
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367971"
---
# <a name="viewselectedby-element-format"></a><span data-ttu-id="ab418-102">ViewSelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ab418-102">ViewSelectedBy Element (Format)</span></span>

<span data-ttu-id="ab418-103">ビューに表示される .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="ab418-103">Defines the .NET objects that are displayed by the view.</span></span> <span data-ttu-id="ab418-104">各ビューには、少なくとも1つの .NET オブジェクトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab418-104">Each view must specify at least one .NET object.</span></span>

<span data-ttu-id="ab418-105">ViewDefinitions 要素 (Format) ビュー要素 (形式) ViewSelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ab418-105">ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ab418-106">構文</span><span class="sxs-lookup"><span data-stu-id="ab418-106">Syntax</span></span>

```xml
<ViewSelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
</ViewSelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ab418-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="ab418-107">Attributes and Elements</span></span>

<span data-ttu-id="ab418-108">次のセクションでは、`ViewSelectedBy` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab418-108">The following sections describe the attributes, child elements, and parent element of the `ViewSelectedBy` element.</span></span> <span data-ttu-id="ab418-109">この要素には、少なくとも1つの @no__t 0 または @no__t 1 つの子要素が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab418-109">This element must contain at least one `TypeName` or `SelectionSetName` child element.</span></span> <span data-ttu-id="ab418-110">指定できる子要素の数に制限はありません。また、順序が重要でもありません。</span><span class="sxs-lookup"><span data-stu-id="ab418-110">There is no limit to the number of child elements that can be specified nor is their order significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="ab418-111">属性</span><span class="sxs-lookup"><span data-stu-id="ab418-111">Attributes</span></span>

<span data-ttu-id="ab418-112">なし。</span><span class="sxs-lookup"><span data-stu-id="ab418-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ab418-113">子要素</span><span class="sxs-lookup"><span data-stu-id="ab418-113">Child Elements</span></span>

|<span data-ttu-id="ab418-114">要素</span><span class="sxs-lookup"><span data-stu-id="ab418-114">Element</span></span>|<span data-ttu-id="ab418-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="ab418-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ab418-116">ViewSelectedBy (Format) の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="ab418-116">TypeName Element for ViewSelectedBy (Format)</span></span>](./typename-element-for-viewselectedby-format.md)|<span data-ttu-id="ab418-117">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="ab418-117">Optional element.</span></span><br /><br /> <span data-ttu-id="ab418-118">ビューに表示される .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab418-118">Specifies a .NET object that is displayed by the view.</span></span>|
|[<span data-ttu-id="ab418-119">ViewSelectedBy (Format) の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="ab418-119">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)|<span data-ttu-id="ab418-120">省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="ab418-120">Optional element.</span></span><br /><br /> <span data-ttu-id="ab418-121">ビューに表示される一連の .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab418-121">Specifies a set of .NET objects that are displayed by the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ab418-122">親要素</span><span class="sxs-lookup"><span data-stu-id="ab418-122">Parent Elements</span></span>

|<span data-ttu-id="ab418-123">要素</span><span class="sxs-lookup"><span data-stu-id="ab418-123">Element</span></span>|<span data-ttu-id="ab418-124">[説明]</span><span class="sxs-lookup"><span data-stu-id="ab418-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ab418-125">View 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ab418-125">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="ab418-126">1つ以上の .NET オブジェクトを表示するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="ab418-126">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ab418-127">コメント</span><span class="sxs-lookup"><span data-stu-id="ab418-127">Remarks</span></span>

<span data-ttu-id="ab418-128">この要素をさまざまなビューで使用する方法の詳細については、「[テーブルビューコンポーネント](./creating-a-table-view.md)」、「[リストビュー](./creating-a-list-view.md)コンポーネント」、「[ワイドビューコンポーネント](./creating-a-wide-view.md)」、および「[カスタムコントロールコンポーネント](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab418-128">For more information about how this element is used in different views, see [Table View Components](./creating-a-table-view.md), [List View Components](./creating-a-list-view.md), [Wide View Components](./creating-a-wide-view.md), and [Custom Control Components](./creating-custom-controls.md).</span></span>

<span data-ttu-id="ab418-129">@No__t-0 要素は、書式設定ファイルが複数のビューによって表示されるオブジェクトのセットを定義する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab418-129">The `SelectionSetName` element is used when the formatting file defines a set of objects that are displayed by multiple views.</span></span> <span data-ttu-id="ab418-130">選択セットを定義および参照する方法の詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab418-130">For more information about how selection sets are defined and referenced, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="ab418-131">例</span><span class="sxs-lookup"><span data-stu-id="ab418-131">Example</span></span>

<span data-ttu-id="ab418-132">リストビューの[Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトを指定する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="ab418-132">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="ab418-133">テーブル、ワイド、およびカスタムビューでも同じスキーマが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab418-133">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="ab418-134">参照</span><span class="sxs-lookup"><span data-stu-id="ab418-134">See Also</span></span>

[<span data-ttu-id="ab418-135">リストビューの作成</span><span class="sxs-lookup"><span data-stu-id="ab418-135">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="ab418-136">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="ab418-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="ab418-137">ワイドビューの作成</span><span class="sxs-lookup"><span data-stu-id="ab418-137">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="ab418-138">カスタムコントロールの作成</span><span class="sxs-lookup"><span data-stu-id="ab418-138">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="ab418-139">選択セットの定義</span><span class="sxs-lookup"><span data-stu-id="ab418-139">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="ab418-140">ViewSelectedBy (Format) の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="ab418-140">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

[<span data-ttu-id="ab418-141">TypeName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="ab418-141">TypeName Element (Format)</span></span>](./typename-element-for-viewselectedby-format.md)

[<span data-ttu-id="ab418-142">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="ab418-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
