---
title: ListControl の ListEntries 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0fe07e739c2d2fec153599ec6c0c0b3ecc14df18
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785712"
---
# <a name="listentries-element-for-listcontrol-format"></a><span data-ttu-id="16a58-102">ListControl の ListEntries 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="16a58-102">ListEntries Element for ListControl (Format)</span></span>

<span data-ttu-id="16a58-103">リストビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="16a58-103">Provides the definitions of the list view.</span></span> <span data-ttu-id="16a58-104">リストビューでは、1つまたは複数の定義を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16a58-104">The list view must specify one or more definitions.</span></span>

<span data-ttu-id="16a58-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (Format) ListEntries 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="16a58-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="16a58-106">構文</span><span class="sxs-lookup"><span data-stu-id="16a58-106">Syntax</span></span>

```xml
<ListEntries>
  <ListEntry>...</ListEntry>
</ListEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="16a58-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="16a58-107">Attributes and Elements</span></span>

<span data-ttu-id="16a58-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ListEntries` ます。</span><span class="sxs-lookup"><span data-stu-id="16a58-108">The following sections describe the attributes, child elements, and the parent element of the `ListEntries` element.</span></span> <span data-ttu-id="16a58-109">少なくとも1つの子要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16a58-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="16a58-110">属性</span><span class="sxs-lookup"><span data-stu-id="16a58-110">Attributes</span></span>

<span data-ttu-id="16a58-111">なし。</span><span class="sxs-lookup"><span data-stu-id="16a58-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="16a58-112">子要素</span><span class="sxs-lookup"><span data-stu-id="16a58-112">Child Elements</span></span>

|<span data-ttu-id="16a58-113">要素</span><span class="sxs-lookup"><span data-stu-id="16a58-113">Element</span></span>|<span data-ttu-id="16a58-114">説明</span><span class="sxs-lookup"><span data-stu-id="16a58-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="16a58-115">ListEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="16a58-115">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="16a58-116">リストビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="16a58-116">Provides a definition of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="16a58-117">親要素</span><span class="sxs-lookup"><span data-stu-id="16a58-117">Parent Elements</span></span>

|<span data-ttu-id="16a58-118">要素</span><span class="sxs-lookup"><span data-stu-id="16a58-118">Element</span></span>|<span data-ttu-id="16a58-119">説明</span><span class="sxs-lookup"><span data-stu-id="16a58-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="16a58-120">ListControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="16a58-120">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="16a58-121">ビューのリスト形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="16a58-121">Defines a list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="16a58-122">解説</span><span class="sxs-lookup"><span data-stu-id="16a58-122">Remarks</span></span>

<span data-ttu-id="16a58-123">リストビューの詳細については、「[リストビュー](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16a58-123">For more information about list views, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="16a58-124">例</span><span class="sxs-lookup"><span data-stu-id="16a58-124">Example</span></span>

<span data-ttu-id="16a58-125">この例は、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトのリストビューを定義する XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="16a58-125">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="16a58-126">参照</span><span class="sxs-lookup"><span data-stu-id="16a58-126">See Also</span></span>

[<span data-ttu-id="16a58-127">ListControl 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="16a58-127">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="16a58-128">ListEntry 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="16a58-128">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="16a58-129">リストビュー</span><span class="sxs-lookup"><span data-stu-id="16a58-129">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="16a58-130">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="16a58-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
