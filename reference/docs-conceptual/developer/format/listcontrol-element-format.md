---
ms.date: 09/13/2016
ms.topic: reference
title: ListControl 要素 (書式)
description: ListControl 要素 (書式)
ms.openlocfilehash: cd5687ac8e94e2245d1ae2de8b2206185e5b8ca4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666588"
---
# <a name="listcontrol-element-format"></a><span data-ttu-id="2558f-103">ListControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2558f-103">ListControl Element (Format)</span></span>

<span data-ttu-id="2558f-104">ビューのリスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="2558f-104">Defines a list format for the view.</span></span>

<span data-ttu-id="2558f-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="2558f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2558f-106">構文</span><span class="sxs-lookup"><span data-stu-id="2558f-106">Syntax</span></span>

```xml
<ListControl>
  <ListEntries>...</ListEntries>
</ListControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="2558f-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2558f-107">Attributes and Elements</span></span>

<span data-ttu-id="2558f-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ListControl` ます。</span><span class="sxs-lookup"><span data-stu-id="2558f-108">The following sections describe the attributes, child elements, and the parent element of the `ListControl` element.</span></span> <span data-ttu-id="2558f-109">この要素には、1つの子要素のみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="2558f-109">This element must contain only a single child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2558f-110">属性</span><span class="sxs-lookup"><span data-stu-id="2558f-110">Attributes</span></span>

<span data-ttu-id="2558f-111">なし。</span><span class="sxs-lookup"><span data-stu-id="2558f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2558f-112">子要素</span><span class="sxs-lookup"><span data-stu-id="2558f-112">Child Elements</span></span>

|<span data-ttu-id="2558f-113">要素</span><span class="sxs-lookup"><span data-stu-id="2558f-113">Element</span></span>|<span data-ttu-id="2558f-114">説明</span><span class="sxs-lookup"><span data-stu-id="2558f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2558f-115">ListEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2558f-115">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="2558f-116">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="2558f-116">Required element.</span></span><br /><br /> <span data-ttu-id="2558f-117">リストビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="2558f-117">Provides the definitions of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2558f-118">親要素</span><span class="sxs-lookup"><span data-stu-id="2558f-118">Parent Elements</span></span>

|<span data-ttu-id="2558f-119">要素</span><span class="sxs-lookup"><span data-stu-id="2558f-119">Element</span></span>|<span data-ttu-id="2558f-120">説明</span><span class="sxs-lookup"><span data-stu-id="2558f-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2558f-121">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2558f-121">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="2558f-122">1つ以上のオブジェクトのメンバーを表示するために使用されるビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="2558f-122">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2558f-123">解説</span><span class="sxs-lookup"><span data-stu-id="2558f-123">Remarks</span></span>

<span data-ttu-id="2558f-124">リストビューの作成の詳細については、「 [リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2558f-124">For more information about creating a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="2558f-125">例</span><span class="sxs-lookup"><span data-stu-id="2558f-125">Example</span></span>

<span data-ttu-id="2558f-126">この例では、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) オブジェクトのリストビューを示します。</span><span class="sxs-lookup"><span data-stu-id="2558f-126">This example shows a list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2558f-127">参照</span><span class="sxs-lookup"><span data-stu-id="2558f-127">See Also</span></span>

[<span data-ttu-id="2558f-128">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2558f-128">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="2558f-129">ListEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2558f-129">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="2558f-130">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="2558f-130">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="2558f-131">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="2558f-131">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
