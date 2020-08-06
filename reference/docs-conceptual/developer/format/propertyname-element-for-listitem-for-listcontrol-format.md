---
title: ListControl の ListItem の PropertyName 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 9ee466d7f73e53b129f8d46f49a21549683bb32c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780833"
---
# <a name="propertyname-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="1025c-102">ListControl の ListItem の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1025c-102">PropertyName Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="1025c-103">値が一覧に表示される .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="1025c-103">Specifies the .NET property whose value is displayed in the list.</span></span>

<span data-ttu-id="1025c-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries 要素 (format) ListEntry Element (Format) ListItems Element (Format) ListItem 要素 (format) ListItem (format) の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="1025c-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) ListItems Element (Format) ListItem Element (Format) PropertyName Element for ListItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1025c-105">構文</span><span class="sxs-lookup"><span data-stu-id="1025c-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1025c-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1025c-106">Attributes and Elements</span></span>

<span data-ttu-id="1025c-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="1025c-107">The following sections describe the attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1025c-108">属性</span><span class="sxs-lookup"><span data-stu-id="1025c-108">Attributes</span></span>

<span data-ttu-id="1025c-109">なし。</span><span class="sxs-lookup"><span data-stu-id="1025c-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1025c-110">子要素</span><span class="sxs-lookup"><span data-stu-id="1025c-110">Child Elements</span></span>

<span data-ttu-id="1025c-111">なし。</span><span class="sxs-lookup"><span data-stu-id="1025c-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1025c-112">親要素</span><span class="sxs-lookup"><span data-stu-id="1025c-112">Parent Elements</span></span>

|<span data-ttu-id="1025c-113">要素</span><span class="sxs-lookup"><span data-stu-id="1025c-113">Element</span></span>|<span data-ttu-id="1025c-114">説明</span><span class="sxs-lookup"><span data-stu-id="1025c-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1025c-115">ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="1025c-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="1025c-116">リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="1025c-116">Defines the property or script whose value is displayed in the row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1025c-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="1025c-117">Text Value</span></span>

<span data-ttu-id="1025c-118">値が表示されるプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1025c-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="1025c-119">解説</span><span class="sxs-lookup"><span data-stu-id="1025c-119">Remarks</span></span>

<span data-ttu-id="1025c-120">この要素が指定されている場合、 [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="1025c-120">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="1025c-121">プロパティ値を表示するだけでなく、値のラベルや、値の表示を変更するために使用できる書式設定文字列を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1025c-121">In addition to displaying the property value, you can also specify a label for the value or a format string that can be used to change the display of the value.</span></span> <span data-ttu-id="1025c-122">リストビューでのデータの指定の詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1025c-122">For more information about specifying data in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="1025c-123">例</span><span class="sxs-lookup"><span data-stu-id="1025c-123">Example</span></span>

<span data-ttu-id="1025c-124">次の例は、値が表示されるラベルとプロパティを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1025c-124">The following example shows how to specify the label and property whose value is displayed.</span></span>

```xml
ListItem>
  <Label>NameOfProperty</Label>
  <PropertyName>.NetTypeProperty</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="1025c-125">参照</span><span class="sxs-lookup"><span data-stu-id="1025c-125">See Also</span></span>

[<span data-ttu-id="1025c-126">ListControl の ListItem の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1025c-126">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="1025c-127">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="1025c-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="1025c-128">ListControl の ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="1025c-128">ListItem Element for ListControl(Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="1025c-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="1025c-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
