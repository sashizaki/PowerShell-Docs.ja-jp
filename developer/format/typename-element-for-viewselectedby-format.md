---
title: ViewSelectedBy (形式) の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ad807a9-d7d8-4e96-b799-9c6a7677cc2d
caps.latest.revision: 12
ms.openlocfilehash: e2028c479103cc414295dc24a0f9bb69190bfc66
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083758"
---
# <a name="typename-element-for-viewselectedby-format"></a><span data-ttu-id="93515-102">ViewSelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="93515-102">TypeName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="93515-103">ビューが表示されている .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="93515-103">Specifies a .NET object that is displayed by the view.</span></span>

<span data-ttu-id="93515-104">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ViewSelectedBy 要素 (形式) TypeName の構成要素 ViewSelectedBy (形式)</span><span class="sxs-lookup"><span data-stu-id="93515-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) TypeName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="93515-105">構文</span><span class="sxs-lookup"><span data-stu-id="93515-105">Syntax</span></span>

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="93515-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="93515-106">Attributes and Elements</span></span>

<span data-ttu-id="93515-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。</span><span class="sxs-lookup"><span data-stu-id="93515-107">The following sections describe attributes, child elements, and the parent elements of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="93515-108">属性</span><span class="sxs-lookup"><span data-stu-id="93515-108">Attributes</span></span>

<span data-ttu-id="93515-109">なし。</span><span class="sxs-lookup"><span data-stu-id="93515-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="93515-110">子要素</span><span class="sxs-lookup"><span data-stu-id="93515-110">Child Elements</span></span>

<span data-ttu-id="93515-111">なし。</span><span class="sxs-lookup"><span data-stu-id="93515-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="93515-112">親要素</span><span class="sxs-lookup"><span data-stu-id="93515-112">Parent Elements</span></span>

|<span data-ttu-id="93515-113">要素</span><span class="sxs-lookup"><span data-stu-id="93515-113">Element</span></span>|<span data-ttu-id="93515-114">説明</span><span class="sxs-lookup"><span data-stu-id="93515-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="93515-115">ViewSelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="93515-115">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="93515-116">ビューが表示されている .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="93515-116">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="93515-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="93515-117">Text Value</span></span>

<span data-ttu-id="93515-118">.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。</span><span class="sxs-lookup"><span data-stu-id="93515-118">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="93515-119">コメント</span><span class="sxs-lookup"><span data-stu-id="93515-119">Remarks</span></span>

<span data-ttu-id="93515-120">この要素はさまざまなビューで使用する方法の詳細については、次を参照してください[テーブル ビューを作成する](./creating-a-table-view.md)、[リスト ビューを作成する](./creating-a-list-view.md)、[ワイド ビューを作成する](./creating-a-wide-view.md)、および[。カスタム ビュー コンポーネント](./creating-custom-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="93515-120">For more information about how this element is used in different views, see [Creating a Table View](./creating-a-table-view.md), [Creating a List View](./creating-a-list-view.md), [Creating a Wide View](./creating-a-wide-view.md), and [Custom View Components](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="93515-121">例</span><span class="sxs-lookup"><span data-stu-id="93515-121">Example</span></span>

<span data-ttu-id="93515-122">次の例は、指定する方法を示します、 [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)のリスト ビューのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="93515-122">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="93515-123">テーブルの幅をカスタム ビューに同じスキーマが使用されます。</span><span class="sxs-lookup"><span data-stu-id="93515-123">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="93515-124">参照</span><span class="sxs-lookup"><span data-stu-id="93515-124">See Also</span></span>

[<span data-ttu-id="93515-125">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="93515-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="93515-126">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="93515-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="93515-127">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="93515-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="93515-128">カスタム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="93515-128">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="93515-129">ViewSelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="93515-129">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="93515-130">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="93515-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
