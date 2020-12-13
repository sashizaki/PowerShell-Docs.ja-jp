---
ms.date: 09/13/2016
ms.topic: reference
title: ListControl の ListEntry の ListItems 要素 (書式)
description: ListControl の ListEntry の ListItems 要素 (書式)
ms.openlocfilehash: 1553c81bc559020223a3c1fea10336baf017c9a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666537"
---
# <a name="listitems-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="7c93b-103">ListControl の ListEntry の ListItems 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7c93b-103">ListItems Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="7c93b-104">リストビューの行に値が表示されるプロパティとスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="7c93b-104">Defines the properties and scripts whose values are displayed in the rows of the list view.</span></span>

<span data-ttu-id="7c93b-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (format) ListControl (format) ListItems 要素のリストコントロール (format) ListEntry 要素の ListEntries 要素を ListControl (Format) に設定します。</span><span class="sxs-lookup"><span data-stu-id="7c93b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for List Control (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7c93b-106">構文</span><span class="sxs-lookup"><span data-stu-id="7c93b-106">Syntax</span></span>

```xml
<ListItems>
  <ListItem>...</ListItem>
</ListItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7c93b-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7c93b-107">Attributes and Elements</span></span>

<span data-ttu-id="7c93b-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ListItems` ます。</span><span class="sxs-lookup"><span data-stu-id="7c93b-108">The following sections describe the attributes, child elements, and parent element of the `ListItems` element.</span></span> <span data-ttu-id="7c93b-109">指定できる子要素の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="7c93b-109">There is no limit to the number of child elements that can be specified.</span></span> <span data-ttu-id="7c93b-110">子要素の順序は、リストビューに表示される値の順序を定義します。</span><span class="sxs-lookup"><span data-stu-id="7c93b-110">The order of the child elements defines the order that values are displayed in the list view.</span></span>

### <a name="attributes"></a><span data-ttu-id="7c93b-111">属性</span><span class="sxs-lookup"><span data-stu-id="7c93b-111">Attributes</span></span>

<span data-ttu-id="7c93b-112">なし。</span><span class="sxs-lookup"><span data-stu-id="7c93b-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7c93b-113">子要素</span><span class="sxs-lookup"><span data-stu-id="7c93b-113">Child Elements</span></span>

|<span data-ttu-id="7c93b-114">要素</span><span class="sxs-lookup"><span data-stu-id="7c93b-114">Element</span></span>|<span data-ttu-id="7c93b-115">説明</span><span class="sxs-lookup"><span data-stu-id="7c93b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7c93b-116">ListControl の ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7c93b-116">ListItem Element for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="7c93b-117">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="7c93b-117">Required element.</span></span><br /><br /> <span data-ttu-id="7c93b-118">リストビューによって表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="7c93b-118">Defines the property or script whose value is displayed by the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7c93b-119">親要素</span><span class="sxs-lookup"><span data-stu-id="7c93b-119">Parent Elements</span></span>

|<span data-ttu-id="7c93b-120">要素</span><span class="sxs-lookup"><span data-stu-id="7c93b-120">Element</span></span>|<span data-ttu-id="7c93b-121">説明</span><span class="sxs-lookup"><span data-stu-id="7c93b-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7c93b-122">ListControl の ListEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7c93b-122">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="7c93b-123">リストビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="7c93b-123">Provides a definition of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7c93b-124">解説</span><span class="sxs-lookup"><span data-stu-id="7c93b-124">Remarks</span></span>

<span data-ttu-id="7c93b-125">この種類のビューの詳細については、「 [リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c93b-125">For more information about this type of view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="7c93b-126">例</span><span class="sxs-lookup"><span data-stu-id="7c93b-126">Example</span></span>

<span data-ttu-id="7c93b-127">この例は、リストビューの3つの行を定義する XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="7c93b-127">This example shows the XML elements that define three rows of the list view.</span></span>

```xml
<ListEntry>
    <ListItems>
      <ListItem>
        <Label>Property1: </Label>
        <PropertyName>.NetTypeProperty1</PropertyName>
      </ListItem>
      <ListItem>
        <PropertyName>.NetTypeProperty2</PropertyName>
      </ListItem>
      <ListItem>
        <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
      </ListItem>
  </ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="7c93b-128">参照</span><span class="sxs-lookup"><span data-stu-id="7c93b-128">See Also</span></span>

[<span data-ttu-id="7c93b-129">ListControl の ListEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7c93b-129">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="7c93b-130">ListControl の ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7c93b-130">ListItem Element for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="7c93b-131">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="7c93b-131">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="7c93b-132">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="7c93b-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
