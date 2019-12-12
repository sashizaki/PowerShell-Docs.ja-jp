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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362641"
---
# <a name="name-element-for-view-format"></a><span data-ttu-id="c9ce3-102">View の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c9ce3-102">Name Element for View (Format)</span></span>

<span data-ttu-id="c9ce3-103">ビューを識別するために使用される名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c9ce3-103">Specifies the name that is used to identify the view.</span></span>

<span data-ttu-id="c9ce3-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) Name 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c9ce3-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Name Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c9ce3-105">構文</span><span class="sxs-lookup"><span data-stu-id="c9ce3-105">Syntax</span></span>

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c9ce3-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="c9ce3-106">Attributes and Elements</span></span>

<span data-ttu-id="c9ce3-107">次のセクションでは、`Name` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9ce3-107">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span> <span data-ttu-id="c9ce3-108">各ビューには、1つの `Name` 要素のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="c9ce3-108">Only one `Name` element is allowed for each view.</span></span>

### <a name="attributes"></a><span data-ttu-id="c9ce3-109">属性</span><span class="sxs-lookup"><span data-stu-id="c9ce3-109">Attributes</span></span>

<span data-ttu-id="c9ce3-110">なし。</span><span class="sxs-lookup"><span data-stu-id="c9ce3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c9ce3-111">子要素</span><span class="sxs-lookup"><span data-stu-id="c9ce3-111">Child Elements</span></span>

<span data-ttu-id="c9ce3-112">なし。</span><span class="sxs-lookup"><span data-stu-id="c9ce3-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c9ce3-113">親要素</span><span class="sxs-lookup"><span data-stu-id="c9ce3-113">Parent Elements</span></span>

|<span data-ttu-id="c9ce3-114">要素</span><span class="sxs-lookup"><span data-stu-id="c9ce3-114">Element</span></span>|<span data-ttu-id="c9ce3-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="c9ce3-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c9ce3-116">View 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c9ce3-116">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="c9ce3-117">1つ以上の .NET オブジェクトのメンバーを表示するために使用されるビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="c9ce3-117">Defines a view that is used to display the members of one or more .NET objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c9ce3-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="c9ce3-118">Text Value</span></span>

<span data-ttu-id="c9ce3-119">ビューの一意の表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="c9ce3-119">Specify a unique friendly name for the view.</span></span> <span data-ttu-id="c9ce3-120">この名前には、ビューの種類 (テーブルビューやリストビューなど) への参照、ビューを使用するオブジェクトまたはオブジェクトのセット、オブジェクトを返すコマンド、またはこれらの組み合わせを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c9ce3-120">This name can include a reference to the type of the view (such as a table view or list view), which object or set of objects use the view, what command returns the objects, or a combination of these.</span></span>

## <a name="remarks"></a><span data-ttu-id="c9ce3-121">コメント</span><span class="sxs-lookup"><span data-stu-id="c9ce3-121">Remarks</span></span>

<span data-ttu-id="c9ce3-122">さまざまな種類のビューの詳細については、次のトピックを参照してください。[テーブルビュー](./creating-a-table-view.md)、[リストビュー](./creating-a-list-view.md)、[ワイドビュー](./creating-a-wide-view.md)、および[カスタムビュー](./creating-custom-controls.md)です。</span><span class="sxs-lookup"><span data-stu-id="c9ce3-122">For more information about the different types of views, see the following topics: [Table View](./creating-a-table-view.md), [List View](./creating-a-list-view.md), [Wide View](./creating-a-wide-view.md), and [Custom View](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="c9ce3-123">例</span><span class="sxs-lookup"><span data-stu-id="c9ce3-123">Example</span></span>

<span data-ttu-id="c9ce3-124">[Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトのテーブルビューを定義する `View` 要素の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c9ce3-124">The following example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="c9ce3-125">ビューの名前は "service" です。</span><span class="sxs-lookup"><span data-stu-id="c9ce3-125">The name of the view is "service".</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="c9ce3-126">参照</span><span class="sxs-lookup"><span data-stu-id="c9ce3-126">See Also</span></span>

[<span data-ttu-id="c9ce3-127">リストビューの作成</span><span class="sxs-lookup"><span data-stu-id="c9ce3-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="c9ce3-128">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="c9ce3-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="c9ce3-129">ワイドビューの作成</span><span class="sxs-lookup"><span data-stu-id="c9ce3-129">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="c9ce3-130">カスタム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="c9ce3-130">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="c9ce3-131">View 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="c9ce3-131">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="c9ce3-132">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="c9ce3-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
