---
title: ListControl の ListItems の ListItem 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e72a887e8bd1f93bacb663e3079eeaec34bdfa51
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785678"
---
# <a name="listitem-element-for-listitems-for-listcontrol-format"></a><span data-ttu-id="a4404-102">ListControl の ListItems の ListItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a4404-102">ListItem Element for ListItems for ListControl (Format)</span></span>

<span data-ttu-id="a4404-103">リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="a4404-103">Defines the property or script whose value is displayed in a row of the list view.</span></span>

<span data-ttu-id="a4404-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries 要素 for ListItems (format) ListControl element for ListControl (format) ListEntry Element for Element (format)。</span><span class="sxs-lookup"><span data-stu-id="a4404-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem for ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a4404-105">構文</span><span class="sxs-lookup"><span data-stu-id="a4404-105">Syntax</span></span>

```xml
<ListItem>
  <PropertyName>PropertyToDisplay</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <Label>LabelToDisplay</Label>
  <FormatString>FormatPattern</FormatString>
  <ItemSelectionCondition>...</ItemSelectionCondition>
</ListItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a4404-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a4404-106">Attributes and Elements</span></span>

<span data-ttu-id="a4404-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `ListItem` ます。</span><span class="sxs-lookup"><span data-stu-id="a4404-107">The following sections describe the attributes, child elements, and parent element of the `ListItem` element.</span></span> <span data-ttu-id="a4404-108">1つのプロパティまたはスクリプトだけを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a4404-108">Only one property or script can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="a4404-109">属性</span><span class="sxs-lookup"><span data-stu-id="a4404-109">Attributes</span></span>

<span data-ttu-id="a4404-110">なし</span><span class="sxs-lookup"><span data-stu-id="a4404-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="a4404-111">子要素</span><span class="sxs-lookup"><span data-stu-id="a4404-111">Child Elements</span></span>

|<span data-ttu-id="a4404-112">要素</span><span class="sxs-lookup"><span data-stu-id="a4404-112">Element</span></span>|<span data-ttu-id="a4404-113">説明</span><span class="sxs-lookup"><span data-stu-id="a4404-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a4404-114">ListControl の ListItem の FormatString 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a4404-114">FormatString Element for ListItem for ListControl (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="a4404-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a4404-115">Optional element.</span></span><br /><br /> <span data-ttu-id="a4404-116">プロパティまたはスクリプトの値の表示方法を定義する書式設定文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4404-116">Specifies a format string that defines how the property or script value is displayed.</span></span>|
|[<span data-ttu-id="a4404-117">ListControl の ListItem の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a4404-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="a4404-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a4404-118">Optional element.</span></span><br /><br /> <span data-ttu-id="a4404-119">このリスト項目を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="a4404-119">Defines the condition that must exist for this list item to be used.</span></span>|
|[<span data-ttu-id="a4404-120">ListControl の ListItem の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a4404-120">Label Element for ListItem for ListControl (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="a4404-121">省略可能な要素</span><span class="sxs-lookup"><span data-stu-id="a4404-121">Optional element</span></span><br /><br /> <span data-ttu-id="a4404-122">行内のプロパティまたはスクリプト値の左側に表示されるラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4404-122">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>|
|[<span data-ttu-id="a4404-123">ListControl の ListItem の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a4404-123">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="a4404-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a4404-124">Optional element.</span></span><br /><br /> <span data-ttu-id="a4404-125">行に値が表示される .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4404-125">Specifies the .NET property whose value is displayed in the row.</span></span>|
|[<span data-ttu-id="a4404-126">ListControl の ListItem の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a4404-126">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="a4404-127">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="a4404-127">Optional element.</span></span><br /><br /> <span data-ttu-id="a4404-128">行に値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4404-128">Specifies the script whose value is displayed in the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a4404-129">親要素</span><span class="sxs-lookup"><span data-stu-id="a4404-129">Parent Elements</span></span>

|<span data-ttu-id="a4404-130">要素</span><span class="sxs-lookup"><span data-stu-id="a4404-130">Element</span></span>|<span data-ttu-id="a4404-131">説明</span><span class="sxs-lookup"><span data-stu-id="a4404-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a4404-132">リストコントロールの ListItems 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="a4404-132">ListItems Element for List Control (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="a4404-133">リストビューに値が表示されるプロパティとスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="a4404-133">Defines the properties and scripts whose values are displayed in the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a4404-134">解説</span><span class="sxs-lookup"><span data-stu-id="a4404-134">Remarks</span></span>

<span data-ttu-id="a4404-135">リストビューのコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4404-135">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a4404-136">例</span><span class="sxs-lookup"><span data-stu-id="a4404-136">Example</span></span>

<span data-ttu-id="a4404-137">この例は、リストビューの3つの行を定義する XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="a4404-137">This example shows the XML elements that define three rows of the list view.</span></span> <span data-ttu-id="a4404-138">最初の2行は .NET プロパティの値を表示し、最後の行にはスクリプトによって生成された値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4404-138">The first two rows display the value of a .NET property, and the last row displays a value generated by a script.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a4404-139">参照</span><span class="sxs-lookup"><span data-stu-id="a4404-139">See Also</span></span>

[<span data-ttu-id="a4404-140">ListItems 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="a4404-140">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="a4404-141">ListItem の FormatString 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a4404-141">FormatString Element for ListItem (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="a4404-142">ListItem の Label 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a4404-142">Label Element for ListItem (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="a4404-143">ListItem の PropertyName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="a4404-143">PropertyName Element for ListItem (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="a4404-144">ListItem の ScriptBlock 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="a4404-144">ScriptBlock Element for ListItem (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="a4404-145">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="a4404-145">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="a4404-146">Windows PowerShell のフォーマットファイルと型ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="a4404-146">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
