---
title: ListControl 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37beeb0b-7a81-4747-becb-e309e17278fb
caps.latest.revision: 12
ms.openlocfilehash: 7a117c25b0d117dc846ba8e060e31e838b5edd52
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857458"
---
# <a name="listcontrol-element-format"></a><span data-ttu-id="a832f-102">ListControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a832f-102">ListControl Element (Format)</span></span>

<span data-ttu-id="a832f-103">ビューの一覧の形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="a832f-103">Defines a list format for the view.</span></span>

<span data-ttu-id="a832f-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a832f-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a832f-105">構文</span><span class="sxs-lookup"><span data-stu-id="a832f-105">Syntax</span></span>

```xml
<ListControl>
  <ListEntries>...</ListEntries>
</ListControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="a832f-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="a832f-106">Attributes and Elements</span></span>

<span data-ttu-id="a832f-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`ListControl`要素。</span><span class="sxs-lookup"><span data-stu-id="a832f-107">The following sections describe the attributes, child elements, and the parent element of the `ListControl` element.</span></span> <span data-ttu-id="a832f-108">この要素は、1 つの子要素のみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a832f-108">This element must contain only a single child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a832f-109">属性</span><span class="sxs-lookup"><span data-stu-id="a832f-109">Attributes</span></span>

<span data-ttu-id="a832f-110">なし。</span><span class="sxs-lookup"><span data-stu-id="a832f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a832f-111">子要素</span><span class="sxs-lookup"><span data-stu-id="a832f-111">Child Elements</span></span>

|<span data-ttu-id="a832f-112">要素</span><span class="sxs-lookup"><span data-stu-id="a832f-112">Element</span></span>|<span data-ttu-id="a832f-113">説明</span><span class="sxs-lookup"><span data-stu-id="a832f-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a832f-114">ListEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a832f-114">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="a832f-115">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="a832f-115">Required element.</span></span><br /><br /> <span data-ttu-id="a832f-116">リスト ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="a832f-116">Provides the definitions of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a832f-117">親要素</span><span class="sxs-lookup"><span data-stu-id="a832f-117">Parent Elements</span></span>

|<span data-ttu-id="a832f-118">要素</span><span class="sxs-lookup"><span data-stu-id="a832f-118">Element</span></span>|<span data-ttu-id="a832f-119">説明</span><span class="sxs-lookup"><span data-stu-id="a832f-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a832f-120">ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a832f-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="a832f-121">1 つまたは複数のオブジェクトのメンバーを表示するために使用するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="a832f-121">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a832f-122">コメント</span><span class="sxs-lookup"><span data-stu-id="a832f-122">Remarks</span></span>

<span data-ttu-id="a832f-123">リスト ビューの作成方法の詳細については、次を参照してください。[リスト ビューを作成する](./creating-a-list-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="a832f-123">For more information about creating a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a832f-124">例</span><span class="sxs-lookup"><span data-stu-id="a832f-124">Example</span></span>

<span data-ttu-id="a832f-125">この例の一覧表示、 [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a832f-125">This example shows a list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>...</ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="a832f-126">参照</span><span class="sxs-lookup"><span data-stu-id="a832f-126">See Also</span></span>

[<span data-ttu-id="a832f-127">ビュー要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a832f-127">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="a832f-128">ListEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a832f-128">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="a832f-129">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="a832f-129">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="a832f-130">Windows PowerShell の書式設定の書き込みとファイルの種類</span><span class="sxs-lookup"><span data-stu-id="a832f-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
