---
ms.date: 09/13/2016
ms.topic: reference
title: ListControl の ListItems の ListItem 要素 (書式)
description: ListControl の ListItems の ListItem 要素 (書式)
ms.openlocfilehash: 999491b7851aa4fa21667ad376d7e9853500ca08
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666554"
---
# <a name="listitem-element-for-listitems-for-listcontrol-format"></a><span data-ttu-id="a6f10-103">ListControl の ListItems の ListItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a6f10-103">ListItem Element for ListItems for ListControl (Format)</span></span>

<span data-ttu-id="a6f10-104">リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="a6f10-104">Defines the property or script whose value is displayed in a row of the list view.</span></span>

<span data-ttu-id="a6f10-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries 要素 for ListItems (format) ListControl element for ListControl (format) ListEntry Element for Element (format)。</span><span class="sxs-lookup"><span data-stu-id="a6f10-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem for ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a6f10-106">構文</span><span class="sxs-lookup"><span data-stu-id="a6f10-106">Syntax</span></span>

```xml
<ListItem>
  <PropertyName>PropertyToDisplay</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <Label>LabelToDisplay</Label>
  <FormatString>FormatPattern</FormatString>
  <ItemSelectionCondition>...</ItemSelectionCondition>
</ListItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a6f10-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a6f10-107">Attributes and Elements</span></span>

<span data-ttu-id="a6f10-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ListItem` ます。</span><span class="sxs-lookup"><span data-stu-id="a6f10-108">The following sections describe the attributes, child elements, and parent element of the `ListItem` element.</span></span> <span data-ttu-id="a6f10-109">1つのプロパティまたはスクリプトだけを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a6f10-109">Only one property or script can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="a6f10-110">属性</span><span class="sxs-lookup"><span data-stu-id="a6f10-110">Attributes</span></span>

<span data-ttu-id="a6f10-111">なし</span><span class="sxs-lookup"><span data-stu-id="a6f10-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="a6f10-112">子要素</span><span class="sxs-lookup"><span data-stu-id="a6f10-112">Child Elements</span></span>

|<span data-ttu-id="a6f10-113">要素</span><span class="sxs-lookup"><span data-stu-id="a6f10-113">Element</span></span>|<span data-ttu-id="a6f10-114">説明</span><span class="sxs-lookup"><span data-stu-id="a6f10-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a6f10-115">ListControl の ListItem の FormatString 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a6f10-115">FormatString Element for ListItem for ListControl (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="a6f10-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a6f10-116">Optional element.</span></span><br /><br /> <span data-ttu-id="a6f10-117">プロパティまたはスクリプトの値の表示方法を定義する書式設定文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6f10-117">Specifies a format string that defines how the property or script value is displayed.</span></span>|
|[<span data-ttu-id="a6f10-118">ListControl の ListItem の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a6f10-118">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="a6f10-119">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a6f10-119">Optional element.</span></span><br /><br /> <span data-ttu-id="a6f10-120">このリスト項目を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="a6f10-120">Defines the condition that must exist for this list item to be used.</span></span>|
|[<span data-ttu-id="a6f10-121">ListControl の ListItem の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a6f10-121">Label Element for ListItem for ListControl (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="a6f10-122">省略可能な要素</span><span class="sxs-lookup"><span data-stu-id="a6f10-122">Optional element</span></span><br /><br /> <span data-ttu-id="a6f10-123">行内のプロパティまたはスクリプト値の左側に表示されるラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="a6f10-123">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>|
|[<span data-ttu-id="a6f10-124">ListControl の ListItem の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a6f10-124">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="a6f10-125">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a6f10-125">Optional element.</span></span><br /><br /> <span data-ttu-id="a6f10-126">行に値が表示される .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="a6f10-126">Specifies the .NET property whose value is displayed in the row.</span></span>|
|[<span data-ttu-id="a6f10-127">ListControl の ListItem の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a6f10-127">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="a6f10-128">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a6f10-128">Optional element.</span></span><br /><br /> <span data-ttu-id="a6f10-129">行に値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a6f10-129">Specifies the script whose value is displayed in the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a6f10-130">親要素</span><span class="sxs-lookup"><span data-stu-id="a6f10-130">Parent Elements</span></span>

|<span data-ttu-id="a6f10-131">要素</span><span class="sxs-lookup"><span data-stu-id="a6f10-131">Element</span></span>|<span data-ttu-id="a6f10-132">説明</span><span class="sxs-lookup"><span data-stu-id="a6f10-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a6f10-133">リストコントロールの ListItems 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="a6f10-133">ListItems Element for List Control (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="a6f10-134">リストビューに値が表示されるプロパティとスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="a6f10-134">Defines the properties and scripts whose values are displayed in the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a6f10-135">解説</span><span class="sxs-lookup"><span data-stu-id="a6f10-135">Remarks</span></span>

<span data-ttu-id="a6f10-136">リストビューのコンポーネントの詳細については、「 [リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f10-136">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a6f10-137">例</span><span class="sxs-lookup"><span data-stu-id="a6f10-137">Example</span></span>

<span data-ttu-id="a6f10-138">この例は、リストビューの3つの行を定義する XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="a6f10-138">This example shows the XML elements that define three rows of the list view.</span></span> <span data-ttu-id="a6f10-139">最初の2行は .NET プロパティの値を表示し、最後の行にはスクリプトによって生成された値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6f10-139">The first two rows display the value of a .NET property, and the last row displays a value generated by a script.</span></span>

```xml
<ListEntry>
    <ListItems>
      <ListItem>
        <Label>Property1: </Label>
        <PropertyName>DotNetProperty1</PropertyName>
      </ListItem>
      <ListItem>
        <PropertyName>DotNetProperty2</PropertyName>
      </ListItem>
      <ListItem>
        <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
      </ListItem>
    </ListItems>
</ListEntry>

```

## <a name="see-also"></a><span data-ttu-id="a6f10-140">参照</span><span class="sxs-lookup"><span data-stu-id="a6f10-140">See Also</span></span>

[<span data-ttu-id="a6f10-141">ListItems 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="a6f10-141">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="a6f10-142">ListItem の FormatString 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a6f10-142">FormatString Element for ListItem (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="a6f10-143">ListItem の Label 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a6f10-143">Label Element for ListItem (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="a6f10-144">ListItem の PropertyName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="a6f10-144">PropertyName Element for ListItem (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="a6f10-145">ListItem の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a6f10-145">ScriptBlock Element for ListItem (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="a6f10-146">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="a6f10-146">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="a6f10-147">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="a6f10-147">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
