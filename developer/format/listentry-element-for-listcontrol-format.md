---
title: ListControl (形式) の要素を ListEntry |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d16bca8-d025-432d-aa84-8b607b8af3ae
caps.latest.revision: 12
ms.openlocfilehash: 1a3bafd4ca94aee70e869c699f7a4ef8befc5511
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862248"
---
# <a name="listentry-element-for-listcontrol-format"></a><span data-ttu-id="72200-102">ListControl の ListEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="72200-102">ListEntry Element for ListControl (Format)</span></span>

<span data-ttu-id="72200-103">リスト ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="72200-103">Provides a definition of the list view.</span></span>

<span data-ttu-id="72200-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素 (形式) ListEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="72200-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="72200-105">構文</span><span class="sxs-lookup"><span data-stu-id="72200-105">Syntax</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="72200-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="72200-106">Attributes and Elements</span></span>

<span data-ttu-id="72200-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`ListEntry`要素。</span><span class="sxs-lookup"><span data-stu-id="72200-107">The following sections describe the attributes, child elements, and the parent element of the `ListEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="72200-108">属性</span><span class="sxs-lookup"><span data-stu-id="72200-108">Attributes</span></span>

<span data-ttu-id="72200-109">なし。</span><span class="sxs-lookup"><span data-stu-id="72200-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="72200-110">子要素</span><span class="sxs-lookup"><span data-stu-id="72200-110">Child Elements</span></span>

|<span data-ttu-id="72200-111">要素</span><span class="sxs-lookup"><span data-stu-id="72200-111">Element</span></span>|<span data-ttu-id="72200-112">説明</span><span class="sxs-lookup"><span data-stu-id="72200-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="72200-113">ListEntry (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="72200-113">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="72200-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="72200-114">Optional element.</span></span><br /><br /> <span data-ttu-id="72200-115">このリスト ビューの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="72200-115">Defines the .NET objects that use this list view definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="72200-116">リスト項目要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="72200-116">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="72200-117">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="72200-117">Required element.</span></span><br /><br /> <span data-ttu-id="72200-118">リスト ビューで表示値を持つスクリプトとプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="72200-118">Defines the properties and scripts whose values are displayed by the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="72200-119">親要素</span><span class="sxs-lookup"><span data-stu-id="72200-119">Parent Elements</span></span>

|<span data-ttu-id="72200-120">要素</span><span class="sxs-lookup"><span data-stu-id="72200-120">Element</span></span>|<span data-ttu-id="72200-121">説明</span><span class="sxs-lookup"><span data-stu-id="72200-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="72200-122">ListEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="72200-122">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="72200-123">リスト ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="72200-123">Provides the definitions of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="72200-124">コメント</span><span class="sxs-lookup"><span data-stu-id="72200-124">Remarks</span></span>

<span data-ttu-id="72200-125">リスト ビューは、プロパティ値または各オブジェクトのスクリプトの値を表示するリスト形式です。</span><span class="sxs-lookup"><span data-stu-id="72200-125">A list view is a list format that displays property values or script values for each object.</span></span> <span data-ttu-id="72200-126">リスト ビューの詳細については、[リスト ビューを作成する](./creating-a-list-view.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72200-126">For more information about list views, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="72200-127">例</span><span class="sxs-lookup"><span data-stu-id="72200-127">Example</span></span>

<span data-ttu-id="72200-128">この例のリスト ビューを定義する XML 要素を示しています、 [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="72200-128">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="72200-129">参照</span><span class="sxs-lookup"><span data-stu-id="72200-129">See Also</span></span>

[<span data-ttu-id="72200-130">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="72200-130">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="72200-131">ListEntry (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="72200-131">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="72200-132">ListEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="72200-132">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="72200-133">リスト項目要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="72200-133">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="72200-134">Windows PowerShell の書式設定の書き込みとファイルの種類</span><span class="sxs-lookup"><span data-stu-id="72200-134">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
