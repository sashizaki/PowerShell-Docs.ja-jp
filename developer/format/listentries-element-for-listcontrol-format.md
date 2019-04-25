---
title: ListControl (形式) の要素を ListEntries |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b62e81cc-4175-40fa-829f-634245b09f86
caps.latest.revision: 12
ms.openlocfilehash: aaf16702e485135b5299ccb43a2b62db2d9f5762
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065395"
---
# <a name="listentries-element-for-listcontrol-format"></a><span data-ttu-id="83d0a-102">ListControl の ListEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="83d0a-102">ListEntries Element for ListControl (Format)</span></span>

<span data-ttu-id="83d0a-103">リスト ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="83d0a-103">Provides the definitions of the list view.</span></span> <span data-ttu-id="83d0a-104">リスト ビューには、1 つまたは複数の定義を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83d0a-104">The list view must specify one or more definitions.</span></span>

<span data-ttu-id="83d0a-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="83d0a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="83d0a-106">構文</span><span class="sxs-lookup"><span data-stu-id="83d0a-106">Syntax</span></span>

```xml
<ListEntries>
  <ListEntry>...</ListEntry>
</ListEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="83d0a-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="83d0a-107">Attributes and Elements</span></span>

<span data-ttu-id="83d0a-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`ListEntries`要素。</span><span class="sxs-lookup"><span data-stu-id="83d0a-108">The following sections describe the attributes, child elements, and the parent element of the `ListEntries` element.</span></span> <span data-ttu-id="83d0a-109">少なくとも 1 つの子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83d0a-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="83d0a-110">属性</span><span class="sxs-lookup"><span data-stu-id="83d0a-110">Attributes</span></span>

<span data-ttu-id="83d0a-111">なし。</span><span class="sxs-lookup"><span data-stu-id="83d0a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="83d0a-112">子要素</span><span class="sxs-lookup"><span data-stu-id="83d0a-112">Child Elements</span></span>

|<span data-ttu-id="83d0a-113">要素</span><span class="sxs-lookup"><span data-stu-id="83d0a-113">Element</span></span>|<span data-ttu-id="83d0a-114">説明</span><span class="sxs-lookup"><span data-stu-id="83d0a-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="83d0a-115">ListEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="83d0a-115">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="83d0a-116">リスト ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="83d0a-116">Provides a definition of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="83d0a-117">親要素</span><span class="sxs-lookup"><span data-stu-id="83d0a-117">Parent Elements</span></span>

|<span data-ttu-id="83d0a-118">要素</span><span class="sxs-lookup"><span data-stu-id="83d0a-118">Element</span></span>|<span data-ttu-id="83d0a-119">説明</span><span class="sxs-lookup"><span data-stu-id="83d0a-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="83d0a-120">ListControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="83d0a-120">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="83d0a-121">ビューの一覧の形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="83d0a-121">Defines a list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="83d0a-122">コメント</span><span class="sxs-lookup"><span data-stu-id="83d0a-122">Remarks</span></span>

<span data-ttu-id="83d0a-123">リスト ビューの詳細については、次を参照してください。[リスト ビュー](./creating-a-list-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="83d0a-123">For more information about list views, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="83d0a-124">例</span><span class="sxs-lookup"><span data-stu-id="83d0a-124">Example</span></span>

<span data-ttu-id="83d0a-125">この例のリスト ビューを定義する XML 要素を示しています、 [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="83d0a-125">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>...</ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="83d0a-126">参照</span><span class="sxs-lookup"><span data-stu-id="83d0a-126">See Also</span></span>

[<span data-ttu-id="83d0a-127">ListControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="83d0a-127">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="83d0a-128">ListEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="83d0a-128">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="83d0a-129">リスト ビュー</span><span class="sxs-lookup"><span data-stu-id="83d0a-129">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="83d0a-130">Windows PowerShell の書式設定の書き込みとファイルの種類</span><span class="sxs-lookup"><span data-stu-id="83d0a-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
