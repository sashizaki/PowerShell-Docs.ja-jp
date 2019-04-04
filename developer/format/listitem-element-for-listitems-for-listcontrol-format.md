---
title: ListItem 要素の ListItems ListControl (形式) の |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f96f4f5-8bd5-43ed-95e7-a7358115999a
caps.latest.revision: 11
ms.openlocfilehash: 1e0a1b2d20853650328b8cfd1513a08f7e167cd6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855158"
---
# <a name="listitem-element-for-listitems-for-listcontrol-format"></a><span data-ttu-id="5db41-102">ListControl の ListItems の ListItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5db41-102">ListItem Element for ListItems for ListControl (Format)</span></span>

<span data-ttu-id="5db41-103">プロパティまたはリスト ビューの行の値が表示されているスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="5db41-103">Defines the property or script whose value is displayed in a row of the list view.</span></span>

<span data-ttu-id="5db41-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素の要素に ListControl (形式) ListEntry ListControl (形式) のリスト項目要素を ListControl (形式)ListItem ListControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="5db41-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem for ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5db41-105">構文</span><span class="sxs-lookup"><span data-stu-id="5db41-105">Syntax</span></span>

```xml
<ListItem>
  <PropertyName>PropertyToDisplay</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <Label>LabelToDisplay</Label>
  <FormatString>FormatPattern</FormatString>
  <ItemSelectionCondition>...</ItemSelectionCondition>
</ListItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5db41-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="5db41-106">Attributes and Elements</span></span>

<span data-ttu-id="5db41-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`ListItem`要素。</span><span class="sxs-lookup"><span data-stu-id="5db41-107">The following sections describe the attributes, child elements, and parent element of the `ListItem` element.</span></span> <span data-ttu-id="5db41-108">1 つだけのプロパティまたはスクリプトを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="5db41-108">Only one property or script can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="5db41-109">属性</span><span class="sxs-lookup"><span data-stu-id="5db41-109">Attributes</span></span>

<span data-ttu-id="5db41-110">None</span><span class="sxs-lookup"><span data-stu-id="5db41-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="5db41-111">子要素</span><span class="sxs-lookup"><span data-stu-id="5db41-111">Child Elements</span></span>

|<span data-ttu-id="5db41-112">要素</span><span class="sxs-lookup"><span data-stu-id="5db41-112">Element</span></span>|<span data-ttu-id="5db41-113">説明</span><span class="sxs-lookup"><span data-stu-id="5db41-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5db41-114">ListControl (形式) を ListItem の FormatString 要素</span><span class="sxs-lookup"><span data-stu-id="5db41-114">FormatString Element for ListItem for ListControl (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="5db41-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="5db41-115">Optional element.</span></span><br /><br /> <span data-ttu-id="5db41-116">プロパティまたはスクリプトの値を表示する方法を定義する書式指定文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="5db41-116">Specifies a format string that defines how the property or script value is displayed.</span></span>|
|[<span data-ttu-id="5db41-117">ItemSelectionCondition ListControl (形式) を ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="5db41-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="5db41-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="5db41-118">Optional element.</span></span><br /><br /> <span data-ttu-id="5db41-119">使用するには、このリスト項目の存在する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="5db41-119">Defines the condition that must exist for this list item to be used.</span></span>|
|[<span data-ttu-id="5db41-120">Label ListControl (形式) を ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="5db41-120">Label Element for ListItem for ListControl (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="5db41-121">省略可能な要素</span><span class="sxs-lookup"><span data-stu-id="5db41-121">Optional element</span></span><br /><br /> <span data-ttu-id="5db41-122">行のプロパティまたはスクリプトの値の左側に表示されるラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="5db41-122">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>|
|[<span data-ttu-id="5db41-123">PropertyName ListControl (形式) を ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="5db41-123">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="5db41-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="5db41-124">Optional element.</span></span><br /><br /> <span data-ttu-id="5db41-125">行の値が表示される、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="5db41-125">Specifies the .NET property whose value is displayed in the row.</span></span>|
|[<span data-ttu-id="5db41-126">ScriptBlock ListControl (形式) を ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="5db41-126">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="5db41-127">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="5db41-127">Optional element.</span></span><br /><br /> <span data-ttu-id="5db41-128">行の値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="5db41-128">Specifies the script whose value is displayed in the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5db41-129">親要素</span><span class="sxs-lookup"><span data-stu-id="5db41-129">Parent Elements</span></span>

|<span data-ttu-id="5db41-130">要素</span><span class="sxs-lookup"><span data-stu-id="5db41-130">Element</span></span>|<span data-ttu-id="5db41-131">説明</span><span class="sxs-lookup"><span data-stu-id="5db41-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5db41-132">リスト コントロール (形式) のリスト項目要素</span><span class="sxs-lookup"><span data-stu-id="5db41-132">ListItems Element for List Control (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="5db41-133">プロパティと値を持つが、一覧に表示されるスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="5db41-133">Defines the properties and scripts whose values are displayed in the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5db41-134">コメント</span><span class="sxs-lookup"><span data-stu-id="5db41-134">Remarks</span></span>

<span data-ttu-id="5db41-135">リスト ビューのコンポーネントに関する詳細については、[リスト ビューを作成する](./creating-a-list-view.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5db41-135">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="5db41-136">例</span><span class="sxs-lookup"><span data-stu-id="5db41-136">Example</span></span>

<span data-ttu-id="5db41-137">この例では、リスト ビューの 3 つの行を定義する XML 要素を示します。</span><span class="sxs-lookup"><span data-stu-id="5db41-137">This example shows the XML elements that define three rows of the list view.</span></span> <span data-ttu-id="5db41-138">最初の 2 つの行は、.NET プロパティの値を表示し、最後の行がスクリプトによって生成される値を表示します。</span><span class="sxs-lookup"><span data-stu-id="5db41-138">The first two rows display the value of a .NET property, and the last row displays a value generated by a script.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5db41-139">参照</span><span class="sxs-lookup"><span data-stu-id="5db41-139">See Also</span></span>

[<span data-ttu-id="5db41-140">リスト項目要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="5db41-140">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="5db41-141">ListItem (形式) の FormatString 要素</span><span class="sxs-lookup"><span data-stu-id="5db41-141">FormatString Element for ListItem (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="5db41-142">ListItem (形式) のラベル要素</span><span class="sxs-lookup"><span data-stu-id="5db41-142">Label Element for ListItem (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="5db41-143">ListItem (形式) の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="5db41-143">PropertyName Element for ListItem (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="5db41-144">ListItem (形式) の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="5db41-144">ScriptBlock Element for ListItem (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="5db41-145">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="5db41-145">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="5db41-146">Windows PowerShell の書式設定の書き込みとファイルの種類</span><span class="sxs-lookup"><span data-stu-id="5db41-146">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
