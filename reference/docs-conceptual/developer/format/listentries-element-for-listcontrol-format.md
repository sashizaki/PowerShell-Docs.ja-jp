---
ms.date: 09/13/2016
ms.topic: reference
title: ListControl の ListEntries 要素 (書式)
description: ListControl の ListEntries 要素 (書式)
ms.openlocfilehash: d4d6625bb92ea27863fc30d5bf5625f9275e4f69
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666605"
---
# <a name="listentries-element-for-listcontrol-format"></a><span data-ttu-id="cd88e-103">ListControl の ListEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cd88e-103">ListEntries Element for ListControl (Format)</span></span>

<span data-ttu-id="cd88e-104">リストビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="cd88e-104">Provides the definitions of the list view.</span></span> <span data-ttu-id="cd88e-105">リストビューでは、1つまたは複数の定義を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd88e-105">The list view must specify one or more definitions.</span></span>

<span data-ttu-id="cd88e-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (Format) ListEntries 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="cd88e-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cd88e-107">構文</span><span class="sxs-lookup"><span data-stu-id="cd88e-107">Syntax</span></span>

```xml
<ListEntries>
  <ListEntry>...</ListEntry>
</ListEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cd88e-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cd88e-108">Attributes and Elements</span></span>

<span data-ttu-id="cd88e-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `ListEntries` ます。</span><span class="sxs-lookup"><span data-stu-id="cd88e-109">The following sections describe the attributes, child elements, and the parent element of the `ListEntries` element.</span></span> <span data-ttu-id="cd88e-110">少なくとも1つの子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd88e-110">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="cd88e-111">属性</span><span class="sxs-lookup"><span data-stu-id="cd88e-111">Attributes</span></span>

<span data-ttu-id="cd88e-112">なし。</span><span class="sxs-lookup"><span data-stu-id="cd88e-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cd88e-113">子要素</span><span class="sxs-lookup"><span data-stu-id="cd88e-113">Child Elements</span></span>

|<span data-ttu-id="cd88e-114">要素</span><span class="sxs-lookup"><span data-stu-id="cd88e-114">Element</span></span>|<span data-ttu-id="cd88e-115">説明</span><span class="sxs-lookup"><span data-stu-id="cd88e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cd88e-116">ListEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="cd88e-116">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="cd88e-117">リストビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="cd88e-117">Provides a definition of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cd88e-118">親要素</span><span class="sxs-lookup"><span data-stu-id="cd88e-118">Parent Elements</span></span>

|<span data-ttu-id="cd88e-119">要素</span><span class="sxs-lookup"><span data-stu-id="cd88e-119">Element</span></span>|<span data-ttu-id="cd88e-120">説明</span><span class="sxs-lookup"><span data-stu-id="cd88e-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cd88e-121">ListControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cd88e-121">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="cd88e-122">ビューのリスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="cd88e-122">Defines a list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cd88e-123">解説</span><span class="sxs-lookup"><span data-stu-id="cd88e-123">Remarks</span></span>

<span data-ttu-id="cd88e-124">リストビューの詳細については、「 [リストビュー](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd88e-124">For more information about list views, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="cd88e-125">例</span><span class="sxs-lookup"><span data-stu-id="cd88e-125">Example</span></span>

<span data-ttu-id="cd88e-126">この例は、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) オブジェクトのリストビューを定義する XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="cd88e-126">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="cd88e-127">参照</span><span class="sxs-lookup"><span data-stu-id="cd88e-127">See Also</span></span>

[<span data-ttu-id="cd88e-128">ListControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cd88e-128">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="cd88e-129">ListEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="cd88e-129">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="cd88e-130">リストビュー</span><span class="sxs-lookup"><span data-stu-id="cd88e-130">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="cd88e-131">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="cd88e-131">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
