---
ms.date: 09/13/2016
ms.topic: reference
title: ViewSelectedBy の TypeName 要素 (書式)
description: ViewSelectedBy の TypeName 要素 (書式)
ms.openlocfilehash: 62edc2fe4b4c1c5f1b17dd2f8b0943f28ff5dfb7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667727"
---
# <a name="typename-element-for-viewselectedby-format"></a><span data-ttu-id="7c5d4-103">ViewSelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7c5d4-103">TypeName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="7c5d4-104">ビューに表示される .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c5d4-104">Specifies a .NET object that is displayed by the view.</span></span>

<span data-ttu-id="7c5d4-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) ViewSelectedBy 要素 (Format) ViewSelectedBy (形式) の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="7c5d4-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) TypeName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7c5d4-106">構文</span><span class="sxs-lookup"><span data-stu-id="7c5d4-106">Syntax</span></span>

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7c5d4-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7c5d4-107">Attributes and Elements</span></span>

<span data-ttu-id="7c5d4-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="7c5d4-108">The following sections describe attributes, child elements, and the parent elements of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7c5d4-109">属性</span><span class="sxs-lookup"><span data-stu-id="7c5d4-109">Attributes</span></span>

<span data-ttu-id="7c5d4-110">なし。</span><span class="sxs-lookup"><span data-stu-id="7c5d4-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7c5d4-111">子要素</span><span class="sxs-lookup"><span data-stu-id="7c5d4-111">Child Elements</span></span>

<span data-ttu-id="7c5d4-112">なし。</span><span class="sxs-lookup"><span data-stu-id="7c5d4-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7c5d4-113">親要素</span><span class="sxs-lookup"><span data-stu-id="7c5d4-113">Parent Elements</span></span>

|<span data-ttu-id="7c5d4-114">要素</span><span class="sxs-lookup"><span data-stu-id="7c5d4-114">Element</span></span>|<span data-ttu-id="7c5d4-115">説明</span><span class="sxs-lookup"><span data-stu-id="7c5d4-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7c5d4-116">ViewSelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7c5d4-116">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="7c5d4-117">ビューに表示される .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="7c5d4-117">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7c5d4-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="7c5d4-118">Text Value</span></span>

<span data-ttu-id="7c5d4-119">.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="7c5d4-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7c5d4-120">解説</span><span class="sxs-lookup"><span data-stu-id="7c5d4-120">Remarks</span></span>

<span data-ttu-id="7c5d4-121">この要素をさまざまなビューで使用する方法の詳細については、「 [テーブルビューの作成](./creating-a-table-view.md)」、「 [リストビュー](./creating-a-list-view.md)の作成」、「 [ワイドビューの作成](./creating-a-wide-view.md)」、および「 [カスタムビューコンポーネント](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c5d4-121">For more information about how this element is used in different views, see [Creating a Table View](./creating-a-table-view.md), [Creating a List View](./creating-a-list-view.md), [Creating a Wide View](./creating-a-wide-view.md), and [Custom View Components](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="7c5d4-122">例</span><span class="sxs-lookup"><span data-stu-id="7c5d4-122">Example</span></span>

<span data-ttu-id="7c5d4-123">リストビューの [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) オブジェクトを指定する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="7c5d4-123">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="7c5d4-124">テーブル、ワイド、およびカスタムビューでも同じスキーマが使用されます。</span><span class="sxs-lookup"><span data-stu-id="7c5d4-124">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="7c5d4-125">参照</span><span class="sxs-lookup"><span data-stu-id="7c5d4-125">See Also</span></span>

[<span data-ttu-id="7c5d4-126">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="7c5d4-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="7c5d4-127">テーブル ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="7c5d4-127">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="7c5d4-128">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="7c5d4-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="7c5d4-129">カスタム コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="7c5d4-129">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="7c5d4-130">ViewSelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7c5d4-130">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="7c5d4-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="7c5d4-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
