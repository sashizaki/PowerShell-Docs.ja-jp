---
title: 要素の名前を表示 (形式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a31010d-1db9-44ae-a7f3-6ed32cb641cb
caps.latest.revision: 16
ms.openlocfilehash: 097d20cb6a04635124d1f96823248df6095ca1af
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065072"
---
# <a name="name-element-for-view-format"></a><span data-ttu-id="1afbf-102">View の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1afbf-102">Name Element for View (Format)</span></span>

<span data-ttu-id="1afbf-103">ビューを識別するために使用される名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1afbf-103">Specifies the name that is used to identify the view.</span></span>

<span data-ttu-id="1afbf-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) Name 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="1afbf-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Name Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1afbf-105">構文</span><span class="sxs-lookup"><span data-stu-id="1afbf-105">Syntax</span></span>

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1afbf-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1afbf-106">Attributes and Elements</span></span>

<span data-ttu-id="1afbf-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`Name`要素。</span><span class="sxs-lookup"><span data-stu-id="1afbf-107">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span> <span data-ttu-id="1afbf-108">1 つだけ`Name`要素は、それぞれのビューを使用します。</span><span class="sxs-lookup"><span data-stu-id="1afbf-108">Only one `Name` element is allowed for each view.</span></span>

### <a name="attributes"></a><span data-ttu-id="1afbf-109">属性</span><span class="sxs-lookup"><span data-stu-id="1afbf-109">Attributes</span></span>

<span data-ttu-id="1afbf-110">なし。</span><span class="sxs-lookup"><span data-stu-id="1afbf-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1afbf-111">子要素</span><span class="sxs-lookup"><span data-stu-id="1afbf-111">Child Elements</span></span>

<span data-ttu-id="1afbf-112">なし。</span><span class="sxs-lookup"><span data-stu-id="1afbf-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1afbf-113">親要素</span><span class="sxs-lookup"><span data-stu-id="1afbf-113">Parent Elements</span></span>

|<span data-ttu-id="1afbf-114">要素</span><span class="sxs-lookup"><span data-stu-id="1afbf-114">Element</span></span>|<span data-ttu-id="1afbf-115">説明</span><span class="sxs-lookup"><span data-stu-id="1afbf-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1afbf-116">ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="1afbf-116">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="1afbf-117">1 つまたは複数の .NET オブジェクトのメンバーを表示するために使用するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="1afbf-117">Defines a view that is used to display the members of one or more .NET objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1afbf-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="1afbf-118">Text Value</span></span>

<span data-ttu-id="1afbf-119">ビューの一意のフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="1afbf-119">Specify a unique friendly name for the view.</span></span> <span data-ttu-id="1afbf-120">この名前は、どのようなコマンドは、オブジェクト、またはこれらの組み合わせを返します、ビューを使用するオブジェクトまたは一連のオブジェクト (テーブル ビューやリスト ビュー)、ビューの種類への参照を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1afbf-120">This name can include a reference to the type of the view (such as a table view or list view), which object or set of objects use the view, what command returns the objects, or a combination of these.</span></span>

## <a name="remarks"></a><span data-ttu-id="1afbf-121">コメント</span><span class="sxs-lookup"><span data-stu-id="1afbf-121">Remarks</span></span>

<span data-ttu-id="1afbf-122">ビューのさまざまな種類の詳細については、次のトピックを参照してください。[テーブル ビュー](./creating-a-table-view.md)、[リスト ビュー](./creating-a-list-view.md)、[表示幅が広い](./creating-a-wide-view.md)、および[カスタム ビュー](./creating-custom-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="1afbf-122">For more information about the different types of views, see the following topics: [Table View](./creating-a-table-view.md), [List View](./creating-a-list-view.md), [Wide View](./creating-a-wide-view.md), and [Custom View](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="1afbf-123">例</span><span class="sxs-lookup"><span data-stu-id="1afbf-123">Example</span></span>

<span data-ttu-id="1afbf-124">次の例は、`View`のテーブル ビューを定義する要素、 [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1afbf-124">The following example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="1afbf-125">ビューの名前は、"service"です。</span><span class="sxs-lookup"><span data-stu-id="1afbf-125">The name of the view is "service".</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="1afbf-126">参照</span><span class="sxs-lookup"><span data-stu-id="1afbf-126">See Also</span></span>

[<span data-ttu-id="1afbf-127">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="1afbf-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="1afbf-128">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="1afbf-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="1afbf-129">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="1afbf-129">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="1afbf-130">カスタム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="1afbf-130">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="1afbf-131">ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="1afbf-131">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="1afbf-132">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="1afbf-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
