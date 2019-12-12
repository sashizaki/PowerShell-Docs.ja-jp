---
title: ViewSelectedBy (Format) の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ad807a9-d7d8-4e96-b799-9c6a7677cc2d
caps.latest.revision: 12
ms.openlocfilehash: e2028c479103cc414295dc24a0f9bb69190bfc66
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361441"
---
# <a name="typename-element-for-viewselectedby-format"></a><span data-ttu-id="62fcf-102">ViewSelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="62fcf-102">TypeName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="62fcf-103">ビューに表示される .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="62fcf-103">Specifies a .NET object that is displayed by the view.</span></span>

<span data-ttu-id="62fcf-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) ViewSelectedBy 要素 (Format) ViewSelectedBy (形式) の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="62fcf-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) TypeName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="62fcf-105">構文</span><span class="sxs-lookup"><span data-stu-id="62fcf-105">Syntax</span></span>

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="62fcf-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="62fcf-106">Attributes and Elements</span></span>

<span data-ttu-id="62fcf-107">次のセクションでは、`TypeName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="62fcf-107">The following sections describe attributes, child elements, and the parent elements of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="62fcf-108">属性</span><span class="sxs-lookup"><span data-stu-id="62fcf-108">Attributes</span></span>

<span data-ttu-id="62fcf-109">なし。</span><span class="sxs-lookup"><span data-stu-id="62fcf-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="62fcf-110">子要素</span><span class="sxs-lookup"><span data-stu-id="62fcf-110">Child Elements</span></span>

<span data-ttu-id="62fcf-111">なし。</span><span class="sxs-lookup"><span data-stu-id="62fcf-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="62fcf-112">親要素</span><span class="sxs-lookup"><span data-stu-id="62fcf-112">Parent Elements</span></span>

|<span data-ttu-id="62fcf-113">要素</span><span class="sxs-lookup"><span data-stu-id="62fcf-113">Element</span></span>|<span data-ttu-id="62fcf-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="62fcf-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="62fcf-115">ViewSelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="62fcf-115">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="62fcf-116">ビューに表示される .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="62fcf-116">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="62fcf-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="62fcf-117">Text Value</span></span>

<span data-ttu-id="62fcf-118">`System.IO.DirectoryInfo`など、.NET 型の完全修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="62fcf-118">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="62fcf-119">コメント</span><span class="sxs-lookup"><span data-stu-id="62fcf-119">Remarks</span></span>

<span data-ttu-id="62fcf-120">この要素をさまざまなビューで使用する方法の詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」、「[リストビュー](./creating-a-list-view.md)の作成」、「[ワイドビューの作成](./creating-a-wide-view.md)」、および「[カスタムビューコンポーネント](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62fcf-120">For more information about how this element is used in different views, see [Creating a Table View](./creating-a-table-view.md), [Creating a List View](./creating-a-list-view.md), [Creating a Wide View](./creating-a-wide-view.md), and [Custom View Components](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="62fcf-121">例</span><span class="sxs-lookup"><span data-stu-id="62fcf-121">Example</span></span>

<span data-ttu-id="62fcf-122">リストビューの[Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトを指定する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="62fcf-122">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="62fcf-123">テーブル、ワイド、およびカスタムビューでも同じスキーマが使用されます。</span><span class="sxs-lookup"><span data-stu-id="62fcf-123">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="62fcf-124">参照</span><span class="sxs-lookup"><span data-stu-id="62fcf-124">See Also</span></span>

[<span data-ttu-id="62fcf-125">リストビューの作成</span><span class="sxs-lookup"><span data-stu-id="62fcf-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="62fcf-126">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="62fcf-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="62fcf-127">ワイドビューの作成</span><span class="sxs-lookup"><span data-stu-id="62fcf-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="62fcf-128">カスタム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="62fcf-128">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="62fcf-129">ViewSelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="62fcf-129">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="62fcf-130">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="62fcf-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
