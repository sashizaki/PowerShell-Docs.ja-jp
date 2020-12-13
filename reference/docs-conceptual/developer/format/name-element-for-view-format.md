---
ms.date: 09/13/2016
ms.topic: reference
title: View の Name 要素 (書式)
description: View の Name 要素 (書式)
ms.openlocfilehash: 5781bcdf7a0e1eb5e9c7e97bb6acc0a383dc0262
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666461"
---
# <a name="name-element-for-view-format"></a><span data-ttu-id="7ecc4-103">View の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7ecc4-103">Name Element for View (Format)</span></span>

<span data-ttu-id="7ecc4-104">ビューを識別するために使用される名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ecc4-104">Specifies the name that is used to identify the view.</span></span>

<span data-ttu-id="7ecc4-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) Name 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7ecc4-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Name Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7ecc4-106">構文</span><span class="sxs-lookup"><span data-stu-id="7ecc4-106">Syntax</span></span>

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7ecc4-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7ecc4-107">Attributes and Elements</span></span>

<span data-ttu-id="7ecc4-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `Name` ます。</span><span class="sxs-lookup"><span data-stu-id="7ecc4-108">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span> <span data-ttu-id="7ecc4-109">`Name`各ビューで許可される要素は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="7ecc4-109">Only one `Name` element is allowed for each view.</span></span>

### <a name="attributes"></a><span data-ttu-id="7ecc4-110">属性</span><span class="sxs-lookup"><span data-stu-id="7ecc4-110">Attributes</span></span>

<span data-ttu-id="7ecc4-111">なし。</span><span class="sxs-lookup"><span data-stu-id="7ecc4-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7ecc4-112">子要素</span><span class="sxs-lookup"><span data-stu-id="7ecc4-112">Child Elements</span></span>

<span data-ttu-id="7ecc4-113">なし。</span><span class="sxs-lookup"><span data-stu-id="7ecc4-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7ecc4-114">親要素</span><span class="sxs-lookup"><span data-stu-id="7ecc4-114">Parent Elements</span></span>

|<span data-ttu-id="7ecc4-115">要素</span><span class="sxs-lookup"><span data-stu-id="7ecc4-115">Element</span></span>|<span data-ttu-id="7ecc4-116">説明</span><span class="sxs-lookup"><span data-stu-id="7ecc4-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7ecc4-117">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7ecc4-117">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="7ecc4-118">1つ以上の .NET オブジェクトのメンバーを表示するために使用されるビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="7ecc4-118">Defines a view that is used to display the members of one or more .NET objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7ecc4-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="7ecc4-119">Text Value</span></span>

<span data-ttu-id="7ecc4-120">ビューの一意の表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ecc4-120">Specify a unique friendly name for the view.</span></span> <span data-ttu-id="7ecc4-121">この名前には、ビューの種類 (テーブルビューやリストビューなど) への参照、ビューを使用するオブジェクトまたはオブジェクトのセット、オブジェクトを返すコマンド、またはこれらの組み合わせを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7ecc4-121">This name can include a reference to the type of the view (such as a table view or list view), which object or set of objects use the view, what command returns the objects, or a combination of these.</span></span>

## <a name="remarks"></a><span data-ttu-id="7ecc4-122">解説</span><span class="sxs-lookup"><span data-stu-id="7ecc4-122">Remarks</span></span>

<span data-ttu-id="7ecc4-123">さまざまな種類のビューの詳細については、次のトピックを参照してください。 [テーブルビュー](./creating-a-table-view.md)、 [リストビュー](./creating-a-list-view.md)、 [ワイドビュー](./creating-a-wide-view.md)、および [カスタムビュー](./creating-custom-controls.md)です。</span><span class="sxs-lookup"><span data-stu-id="7ecc4-123">For more information about the different types of views, see the following topics: [Table View](./creating-a-table-view.md), [List View](./creating-a-list-view.md), [Wide View](./creating-a-wide-view.md), and [Custom View](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="7ecc4-124">例</span><span class="sxs-lookup"><span data-stu-id="7ecc4-124">Example</span></span>

<span data-ttu-id="7ecc4-125">次の例は、 `View` [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) オブジェクトのテーブルビューを定義する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="7ecc4-125">The following example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="7ecc4-126">ビューの名前は "service" です。</span><span class="sxs-lookup"><span data-stu-id="7ecc4-126">The name of the view is "service".</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="7ecc4-127">参照</span><span class="sxs-lookup"><span data-stu-id="7ecc4-127">See Also</span></span>

[<span data-ttu-id="7ecc4-128">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="7ecc4-128">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="7ecc4-129">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="7ecc4-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="7ecc4-130">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="7ecc4-130">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="7ecc4-131">カスタム コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="7ecc4-131">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="7ecc4-132">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7ecc4-132">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="7ecc4-133">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="7ecc4-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
