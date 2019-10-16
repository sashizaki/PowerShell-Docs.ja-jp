---
title: ビューの Name 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a31010d-1db9-44ae-a7f3-6ed32cb641cb
caps.latest.revision: 16
ms.openlocfilehash: 097d20cb6a04635124d1f96823248df6095ca1af
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362641"
---
# <a name="name-element-for-view-format"></a><span data-ttu-id="30d59-102">View の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="30d59-102">Name Element for View (Format)</span></span>

<span data-ttu-id="30d59-103">ビューを識別するために使用される名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="30d59-103">Specifies the name that is used to identify the view.</span></span>

<span data-ttu-id="30d59-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) Name 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="30d59-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Name Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="30d59-105">構文</span><span class="sxs-lookup"><span data-stu-id="30d59-105">Syntax</span></span>

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="30d59-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="30d59-106">Attributes and Elements</span></span>

<span data-ttu-id="30d59-107">次のセクションでは、属性、子要素、`Name` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="30d59-107">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span> <span data-ttu-id="30d59-108">各ビューで許可される `Name` 要素は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="30d59-108">Only one `Name` element is allowed for each view.</span></span>

### <a name="attributes"></a><span data-ttu-id="30d59-109">属性</span><span class="sxs-lookup"><span data-stu-id="30d59-109">Attributes</span></span>

<span data-ttu-id="30d59-110">なし。</span><span class="sxs-lookup"><span data-stu-id="30d59-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="30d59-111">子要素</span><span class="sxs-lookup"><span data-stu-id="30d59-111">Child Elements</span></span>

<span data-ttu-id="30d59-112">なし。</span><span class="sxs-lookup"><span data-stu-id="30d59-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="30d59-113">親要素</span><span class="sxs-lookup"><span data-stu-id="30d59-113">Parent Elements</span></span>

|<span data-ttu-id="30d59-114">要素</span><span class="sxs-lookup"><span data-stu-id="30d59-114">Element</span></span>|<span data-ttu-id="30d59-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="30d59-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="30d59-116">View 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="30d59-116">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="30d59-117">1つ以上の .NET オブジェクトのメンバーを表示するために使用されるビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="30d59-117">Defines a view that is used to display the members of one or more .NET objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="30d59-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="30d59-118">Text Value</span></span>

<span data-ttu-id="30d59-119">ビューの一意の表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="30d59-119">Specify a unique friendly name for the view.</span></span> <span data-ttu-id="30d59-120">この名前には、ビューの種類 (テーブルビューやリストビューなど) への参照、ビューを使用するオブジェクトまたはオブジェクトのセット、オブジェクトを返すコマンド、またはこれらの組み合わせを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="30d59-120">This name can include a reference to the type of the view (such as a table view or list view), which object or set of objects use the view, what command returns the objects, or a combination of these.</span></span>

## <a name="remarks"></a><span data-ttu-id="30d59-121">コメント</span><span class="sxs-lookup"><span data-stu-id="30d59-121">Remarks</span></span>

<span data-ttu-id="30d59-122">さまざまな種類のビューの詳細については、次のトピックを参照してください。[テーブルビュー](./creating-a-table-view.md)、[リストビュー](./creating-a-list-view.md)、[ワイドビュー](./creating-a-wide-view.md)、および[カスタムビュー](./creating-custom-controls.md)です。</span><span class="sxs-lookup"><span data-stu-id="30d59-122">For more information about the different types of views, see the following topics: [Table View](./creating-a-table-view.md), [List View](./creating-a-list-view.md), [Wide View](./creating-a-wide-view.md), and [Custom View](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="30d59-123">例</span><span class="sxs-lookup"><span data-stu-id="30d59-123">Example</span></span>

<span data-ttu-id="30d59-124">次の例は、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトのテーブルビューを定義する @no__t 0 の要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="30d59-124">The following example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="30d59-125">ビューの名前は "service" です。</span><span class="sxs-lookup"><span data-stu-id="30d59-125">The name of the view is "service".</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="30d59-126">参照</span><span class="sxs-lookup"><span data-stu-id="30d59-126">See Also</span></span>

[<span data-ttu-id="30d59-127">リストビューの作成</span><span class="sxs-lookup"><span data-stu-id="30d59-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="30d59-128">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="30d59-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="30d59-129">ワイドビューの作成</span><span class="sxs-lookup"><span data-stu-id="30d59-129">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="30d59-130">カスタムコントロールの作成</span><span class="sxs-lookup"><span data-stu-id="30d59-130">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="30d59-131">View 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="30d59-131">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="30d59-132">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="30d59-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
