---
title: ListControl の ListItem の ScriptBlock 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 249d3e36b4246b7baa410815122f8e30340f1862
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785457"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="41996-102">ListControl の ListItem の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="41996-102">ScriptBlock Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="41996-103">行に値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="41996-103">Specifies the script whose value is displayed in the row.</span></span>

<span data-ttu-id="41996-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (形式) の listentries ListControl (format) ListItems 要素の ListEntries for ListEntry (format) ListEntry 要素の ListControl for ListItems (format) の listitem 要素の ListControl for ListControl (形式) の ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="41996-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ScriptBlock Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="41996-105">構文</span><span class="sxs-lookup"><span data-stu-id="41996-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="41996-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="41996-106">Attributes and Elements</span></span>

<span data-ttu-id="41996-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="41996-107">The following sections describe the attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="41996-108">属性</span><span class="sxs-lookup"><span data-stu-id="41996-108">Attributes</span></span>

<span data-ttu-id="41996-109">なし。</span><span class="sxs-lookup"><span data-stu-id="41996-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="41996-110">子要素</span><span class="sxs-lookup"><span data-stu-id="41996-110">Child Elements</span></span>

<span data-ttu-id="41996-111">なし。</span><span class="sxs-lookup"><span data-stu-id="41996-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="41996-112">親要素</span><span class="sxs-lookup"><span data-stu-id="41996-112">Parent Elements</span></span>

|<span data-ttu-id="41996-113">要素</span><span class="sxs-lookup"><span data-stu-id="41996-113">Element</span></span>|<span data-ttu-id="41996-114">説明</span><span class="sxs-lookup"><span data-stu-id="41996-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="41996-115">ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="41996-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="41996-116">リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="41996-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="41996-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="41996-117">Text Value</span></span>

<span data-ttu-id="41996-118">行に値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="41996-118">Specify the script whose value is displayed in the row.</span></span>

## <a name="remarks"></a><span data-ttu-id="41996-119">解説</span><span class="sxs-lookup"><span data-stu-id="41996-119">Remarks</span></span>

<span data-ttu-id="41996-120">この要素が指定されている場合、 [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="41996-120">When this element is specified, you cannot specify the [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="41996-121">リストビューでのスクリプトの指定の詳細については、「[リストビュー](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41996-121">For more information about specifying scripts in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="41996-122">例</span><span class="sxs-lookup"><span data-stu-id="41996-122">Example</span></span>

<span data-ttu-id="41996-123">次の例は、値が表示されるプロパティを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="41996-123">The following example shows how to specify the property whose value is displayed.</span></span>

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="41996-124">参照</span><span class="sxs-lookup"><span data-stu-id="41996-124">See Also</span></span>

[<span data-ttu-id="41996-125">ListControl の ListItem の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="41996-125">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="41996-126">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="41996-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="41996-127">ListControl の ListItems の ListItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="41996-127">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="41996-128">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="41996-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
