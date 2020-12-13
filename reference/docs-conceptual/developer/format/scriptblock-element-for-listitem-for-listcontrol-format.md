---
ms.date: 09/13/2016
ms.topic: reference
title: ListControl の ListItem の ScriptBlock 要素 (書式)
description: ListControl の ListItem の ScriptBlock 要素 (書式)
ms.openlocfilehash: 0635ac2622cc203a2dc895873621901d956f87da
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664968"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="3c974-103">ListControl の ListItem の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3c974-103">ScriptBlock Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="3c974-104">行に値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="3c974-104">Specifies the script whose value is displayed in the row.</span></span>

<span data-ttu-id="3c974-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (形式) の listentries ListControl (format) ListItems 要素の ListEntries for ListEntry (format) ListEntry 要素の ListControl for ListItems (format) の listitem 要素の ListControl for ListControl (形式) の ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="3c974-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ScriptBlock Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3c974-106">構文</span><span class="sxs-lookup"><span data-stu-id="3c974-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3c974-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3c974-107">Attributes and Elements</span></span>

<span data-ttu-id="3c974-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="3c974-108">The following sections describe the attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3c974-109">属性</span><span class="sxs-lookup"><span data-stu-id="3c974-109">Attributes</span></span>

<span data-ttu-id="3c974-110">なし。</span><span class="sxs-lookup"><span data-stu-id="3c974-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3c974-111">子要素</span><span class="sxs-lookup"><span data-stu-id="3c974-111">Child Elements</span></span>

<span data-ttu-id="3c974-112">なし。</span><span class="sxs-lookup"><span data-stu-id="3c974-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3c974-113">親要素</span><span class="sxs-lookup"><span data-stu-id="3c974-113">Parent Elements</span></span>

|<span data-ttu-id="3c974-114">要素</span><span class="sxs-lookup"><span data-stu-id="3c974-114">Element</span></span>|<span data-ttu-id="3c974-115">説明</span><span class="sxs-lookup"><span data-stu-id="3c974-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3c974-116">ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="3c974-116">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="3c974-117">リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="3c974-117">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3c974-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="3c974-118">Text Value</span></span>

<span data-ttu-id="3c974-119">行に値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="3c974-119">Specify the script whose value is displayed in the row.</span></span>

## <a name="remarks"></a><span data-ttu-id="3c974-120">解説</span><span class="sxs-lookup"><span data-stu-id="3c974-120">Remarks</span></span>

<span data-ttu-id="3c974-121">この要素が指定されている場合、 [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) 要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3c974-121">When this element is specified, you cannot specify the [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="3c974-122">リストビューでのスクリプトの指定の詳細については、「 [リストビュー](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c974-122">For more information about specifying scripts in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="3c974-123">例</span><span class="sxs-lookup"><span data-stu-id="3c974-123">Example</span></span>

<span data-ttu-id="3c974-124">次の例は、値が表示されるプロパティを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3c974-124">The following example shows how to specify the property whose value is displayed.</span></span>

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="3c974-125">参照</span><span class="sxs-lookup"><span data-stu-id="3c974-125">See Also</span></span>

[<span data-ttu-id="3c974-126">ListControl の ListItem の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3c974-126">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="3c974-127">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="3c974-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="3c974-128">ListControl の ListItems の ListItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="3c974-128">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="3c974-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="3c974-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
