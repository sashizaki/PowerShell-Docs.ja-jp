---
title: ListControl の ListEntries 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b62e81cc-4175-40fa-829f-634245b09f86
caps.latest.revision: 12
ms.openlocfilehash: aaf16702e485135b5299ccb43a2b62db2d9f5762
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362761"
---
# <a name="listentries-element-for-listcontrol-format"></a><span data-ttu-id="602ba-102">ListControl の ListEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="602ba-102">ListEntries Element for ListControl (Format)</span></span>

<span data-ttu-id="602ba-103">リストビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="602ba-103">Provides the definitions of the list view.</span></span> <span data-ttu-id="602ba-104">リストビューでは、1つまたは複数の定義を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="602ba-104">The list view must specify one or more definitions.</span></span>

<span data-ttu-id="602ba-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (Format) ListEntries 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="602ba-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="602ba-106">構文</span><span class="sxs-lookup"><span data-stu-id="602ba-106">Syntax</span></span>

```xml
<ListEntries>
  <ListEntry>...</ListEntry>
</ListEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="602ba-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="602ba-107">Attributes and Elements</span></span>

<span data-ttu-id="602ba-108">次のセクションでは、`ListEntries` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="602ba-108">The following sections describe the attributes, child elements, and the parent element of the `ListEntries` element.</span></span> <span data-ttu-id="602ba-109">少なくとも1つの子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="602ba-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="602ba-110">属性</span><span class="sxs-lookup"><span data-stu-id="602ba-110">Attributes</span></span>

<span data-ttu-id="602ba-111">なし。</span><span class="sxs-lookup"><span data-stu-id="602ba-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="602ba-112">子要素</span><span class="sxs-lookup"><span data-stu-id="602ba-112">Child Elements</span></span>

|<span data-ttu-id="602ba-113">要素</span><span class="sxs-lookup"><span data-stu-id="602ba-113">Element</span></span>|<span data-ttu-id="602ba-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="602ba-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="602ba-115">ListEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="602ba-115">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="602ba-116">リストビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="602ba-116">Provides a definition of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="602ba-117">親要素</span><span class="sxs-lookup"><span data-stu-id="602ba-117">Parent Elements</span></span>

|<span data-ttu-id="602ba-118">要素</span><span class="sxs-lookup"><span data-stu-id="602ba-118">Element</span></span>|<span data-ttu-id="602ba-119">[説明]</span><span class="sxs-lookup"><span data-stu-id="602ba-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="602ba-120">ListControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="602ba-120">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="602ba-121">ビューのリスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="602ba-121">Defines a list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="602ba-122">コメント</span><span class="sxs-lookup"><span data-stu-id="602ba-122">Remarks</span></span>

<span data-ttu-id="602ba-123">リストビューの詳細については、「[リストビュー](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="602ba-123">For more information about list views, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="602ba-124">例</span><span class="sxs-lookup"><span data-stu-id="602ba-124">Example</span></span>

<span data-ttu-id="602ba-125">この例は、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトのリストビューを定義する XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="602ba-125">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="602ba-126">参照</span><span class="sxs-lookup"><span data-stu-id="602ba-126">See Also</span></span>

[<span data-ttu-id="602ba-127">ListControl 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="602ba-127">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="602ba-128">ListEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="602ba-128">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="602ba-129">リストビュー</span><span class="sxs-lookup"><span data-stu-id="602ba-129">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="602ba-130">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="602ba-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)