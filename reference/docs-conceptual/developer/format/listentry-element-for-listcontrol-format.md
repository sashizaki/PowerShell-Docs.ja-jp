---
title: ListControl の ListEntry 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d16bca8-d025-432d-aa84-8b607b8af3ae
caps.latest.revision: 12
ms.openlocfilehash: 1a3bafd4ca94aee70e869c699f7a4ef8befc5511
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362751"
---
# <a name="listentry-element-for-listcontrol-format"></a><span data-ttu-id="cb607-102">ListControl の ListEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cb607-102">ListEntry Element for ListControl (Format)</span></span>

<span data-ttu-id="cb607-103">リストビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="cb607-103">Provides a definition of the list view.</span></span>

<span data-ttu-id="cb607-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (Format) ListEntries 要素 (format) ListEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="cb607-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cb607-105">構文</span><span class="sxs-lookup"><span data-stu-id="cb607-105">Syntax</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cb607-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="cb607-106">Attributes and Elements</span></span>

<span data-ttu-id="cb607-107">次のセクションでは、`ListEntry` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cb607-107">The following sections describe the attributes, child elements, and the parent element of the `ListEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cb607-108">属性</span><span class="sxs-lookup"><span data-stu-id="cb607-108">Attributes</span></span>

<span data-ttu-id="cb607-109">なし。</span><span class="sxs-lookup"><span data-stu-id="cb607-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cb607-110">子要素</span><span class="sxs-lookup"><span data-stu-id="cb607-110">Child Elements</span></span>

|<span data-ttu-id="cb607-111">要素</span><span class="sxs-lookup"><span data-stu-id="cb607-111">Element</span></span>|<span data-ttu-id="cb607-112">[説明]</span><span class="sxs-lookup"><span data-stu-id="cb607-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cb607-113">ListEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="cb607-113">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="cb607-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="cb607-114">Optional element.</span></span><br /><br /> <span data-ttu-id="cb607-115">このリストビュー定義を使用する .NET オブジェクト、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="cb607-115">Defines the .NET objects that use this list view definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="cb607-116">ListItems 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="cb607-116">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="cb607-117">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="cb607-117">Required element.</span></span><br /><br /> <span data-ttu-id="cb607-118">リストビューによって値が表示されるプロパティとスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="cb607-118">Defines the properties and scripts whose values are displayed by the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cb607-119">親要素</span><span class="sxs-lookup"><span data-stu-id="cb607-119">Parent Elements</span></span>

|<span data-ttu-id="cb607-120">要素</span><span class="sxs-lookup"><span data-stu-id="cb607-120">Element</span></span>|<span data-ttu-id="cb607-121">[説明]</span><span class="sxs-lookup"><span data-stu-id="cb607-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cb607-122">ListEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cb607-122">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="cb607-123">リストビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="cb607-123">Provides the definitions of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cb607-124">コメント</span><span class="sxs-lookup"><span data-stu-id="cb607-124">Remarks</span></span>

<span data-ttu-id="cb607-125">リストビューは、各オブジェクトのプロパティ値またはスクリプト値を表示するリスト形式です。</span><span class="sxs-lookup"><span data-stu-id="cb607-125">A list view is a list format that displays property values or script values for each object.</span></span> <span data-ttu-id="cb607-126">リストビューの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb607-126">For more information about list views, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="cb607-127">例</span><span class="sxs-lookup"><span data-stu-id="cb607-127">Example</span></span>

<span data-ttu-id="cb607-128">この例は、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトのリストビューを定義する XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="cb607-128">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="cb607-129">参照</span><span class="sxs-lookup"><span data-stu-id="cb607-129">See Also</span></span>

[<span data-ttu-id="cb607-130">リストビューの作成</span><span class="sxs-lookup"><span data-stu-id="cb607-130">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="cb607-131">ListEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="cb607-131">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="cb607-132">ListEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cb607-132">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="cb607-133">ListItems 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="cb607-133">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="cb607-134">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="cb607-134">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
