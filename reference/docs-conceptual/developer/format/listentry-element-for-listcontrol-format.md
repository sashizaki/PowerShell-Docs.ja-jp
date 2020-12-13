---
ms.date: 09/13/2016
ms.topic: reference
title: ListControl の ListEntry 要素 (書式)
description: ListControl の ListEntry 要素 (書式)
ms.openlocfilehash: 96ae5fcdd837d2491d6c7ff6a375fef1d83ae3e9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666571"
---
# <a name="listentry-element-for-listcontrol-format"></a><span data-ttu-id="cc333-103">ListControl の ListEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cc333-103">ListEntry Element for ListControl (Format)</span></span>

<span data-ttu-id="cc333-104">リストビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="cc333-104">Provides a definition of the list view.</span></span>

<span data-ttu-id="cc333-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (Format) ListEntries 要素 (format) ListEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="cc333-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cc333-106">構文</span><span class="sxs-lookup"><span data-stu-id="cc333-106">Syntax</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cc333-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cc333-107">Attributes and Elements</span></span>

<span data-ttu-id="cc333-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ListEntry` ます。</span><span class="sxs-lookup"><span data-stu-id="cc333-108">The following sections describe the attributes, child elements, and the parent element of the `ListEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cc333-109">属性</span><span class="sxs-lookup"><span data-stu-id="cc333-109">Attributes</span></span>

<span data-ttu-id="cc333-110">なし。</span><span class="sxs-lookup"><span data-stu-id="cc333-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cc333-111">子要素</span><span class="sxs-lookup"><span data-stu-id="cc333-111">Child Elements</span></span>

|<span data-ttu-id="cc333-112">要素</span><span class="sxs-lookup"><span data-stu-id="cc333-112">Element</span></span>|<span data-ttu-id="cc333-113">説明</span><span class="sxs-lookup"><span data-stu-id="cc333-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cc333-114">ListEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="cc333-114">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="cc333-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="cc333-115">Optional element.</span></span><br /><br /> <span data-ttu-id="cc333-116">このリストビュー定義を使用する .NET オブジェクト、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="cc333-116">Defines the .NET objects that use this list view definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="cc333-117">ListItems 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="cc333-117">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="cc333-118">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="cc333-118">Required element.</span></span><br /><br /> <span data-ttu-id="cc333-119">リストビューによって値が表示されるプロパティとスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="cc333-119">Defines the properties and scripts whose values are displayed by the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cc333-120">親要素</span><span class="sxs-lookup"><span data-stu-id="cc333-120">Parent Elements</span></span>

|<span data-ttu-id="cc333-121">要素</span><span class="sxs-lookup"><span data-stu-id="cc333-121">Element</span></span>|<span data-ttu-id="cc333-122">説明</span><span class="sxs-lookup"><span data-stu-id="cc333-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cc333-123">ListEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cc333-123">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="cc333-124">リストビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="cc333-124">Provides the definitions of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cc333-125">解説</span><span class="sxs-lookup"><span data-stu-id="cc333-125">Remarks</span></span>

<span data-ttu-id="cc333-126">リストビューは、各オブジェクトのプロパティ値またはスクリプト値を表示するリスト形式です。</span><span class="sxs-lookup"><span data-stu-id="cc333-126">A list view is a list format that displays property values or script values for each object.</span></span> <span data-ttu-id="cc333-127">リストビューの詳細については、「 [リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc333-127">For more information about list views, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="cc333-128">例</span><span class="sxs-lookup"><span data-stu-id="cc333-128">Example</span></span>

<span data-ttu-id="cc333-129">この例は、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) オブジェクトのリストビューを定義する XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="cc333-129">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="cc333-130">参照</span><span class="sxs-lookup"><span data-stu-id="cc333-130">See Also</span></span>

[<span data-ttu-id="cc333-131">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="cc333-131">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="cc333-132">ListEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="cc333-132">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="cc333-133">ListEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cc333-133">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="cc333-134">ListItems 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="cc333-134">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="cc333-135">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="cc333-135">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
