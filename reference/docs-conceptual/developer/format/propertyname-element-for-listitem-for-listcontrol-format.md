---
ms.date: 09/13/2016
ms.topic: reference
title: ListControl の ListItem の PropertyName 要素 (書式)
description: ListControl の ListItem の PropertyName 要素 (書式)
ms.openlocfilehash: 30cd48f9549e1a091776cd5f8395e1a71314ea1b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665976"
---
# <a name="propertyname-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="30bd7-103">ListControl の ListItem の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="30bd7-103">PropertyName Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="30bd7-104">値が一覧に表示される .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="30bd7-104">Specifies the .NET property whose value is displayed in the list.</span></span>

<span data-ttu-id="30bd7-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries 要素 (format) ListEntry Element (Format) ListItems Element (Format) ListItem 要素 (format) ListItem (format) の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="30bd7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) ListItems Element (Format) ListItem Element (Format) PropertyName Element for ListItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="30bd7-106">構文</span><span class="sxs-lookup"><span data-stu-id="30bd7-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="30bd7-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="30bd7-107">Attributes and Elements</span></span>

<span data-ttu-id="30bd7-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="30bd7-108">The following sections describe the attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="30bd7-109">属性</span><span class="sxs-lookup"><span data-stu-id="30bd7-109">Attributes</span></span>

<span data-ttu-id="30bd7-110">なし。</span><span class="sxs-lookup"><span data-stu-id="30bd7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="30bd7-111">子要素</span><span class="sxs-lookup"><span data-stu-id="30bd7-111">Child Elements</span></span>

<span data-ttu-id="30bd7-112">なし。</span><span class="sxs-lookup"><span data-stu-id="30bd7-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="30bd7-113">親要素</span><span class="sxs-lookup"><span data-stu-id="30bd7-113">Parent Elements</span></span>

|<span data-ttu-id="30bd7-114">要素</span><span class="sxs-lookup"><span data-stu-id="30bd7-114">Element</span></span>|<span data-ttu-id="30bd7-115">説明</span><span class="sxs-lookup"><span data-stu-id="30bd7-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="30bd7-116">ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="30bd7-116">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="30bd7-117">リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="30bd7-117">Defines the property or script whose value is displayed in the row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="30bd7-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="30bd7-118">Text Value</span></span>

<span data-ttu-id="30bd7-119">値が表示されるプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="30bd7-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="30bd7-120">解説</span><span class="sxs-lookup"><span data-stu-id="30bd7-120">Remarks</span></span>

<span data-ttu-id="30bd7-121">この要素が指定されている場合、 [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) 要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="30bd7-121">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="30bd7-122">プロパティ値を表示するだけでなく、値のラベルや、値の表示を変更するために使用できる書式設定文字列を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="30bd7-122">In addition to displaying the property value, you can also specify a label for the value or a format string that can be used to change the display of the value.</span></span> <span data-ttu-id="30bd7-123">リストビューでのデータの指定の詳細については、「 [リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30bd7-123">For more information about specifying data in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="30bd7-124">例</span><span class="sxs-lookup"><span data-stu-id="30bd7-124">Example</span></span>

<span data-ttu-id="30bd7-125">次の例は、値が表示されるラベルとプロパティを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="30bd7-125">The following example shows how to specify the label and property whose value is displayed.</span></span>

```xml
ListItem>
  <Label>NameOfProperty</Label>
  <PropertyName>.NetTypeProperty</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="30bd7-126">参照</span><span class="sxs-lookup"><span data-stu-id="30bd7-126">See Also</span></span>

[<span data-ttu-id="30bd7-127">ListControl の ListItem の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="30bd7-127">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="30bd7-128">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="30bd7-128">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="30bd7-129">ListControl の ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="30bd7-129">ListItem Element for ListControl(Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="30bd7-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="30bd7-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
