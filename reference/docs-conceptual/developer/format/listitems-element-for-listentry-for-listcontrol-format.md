---
title: ListControl (Format) の ListEntry の ListItems 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 03b89a3df2ab0498533d0c00f303f643e0039b25
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781139"
---
# <a name="listitems-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="96a79-102">ListControl の ListEntry の ListItems 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="96a79-102">ListItems Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="96a79-103">リストビューの行に値が表示されるプロパティとスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="96a79-103">Defines the properties and scripts whose values are displayed in the rows of the list view.</span></span>

<span data-ttu-id="96a79-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (format) ListControl (format) ListItems 要素のリストコントロール (format) ListEntry 要素の ListEntries 要素を ListControl (Format) に設定します。</span><span class="sxs-lookup"><span data-stu-id="96a79-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for List Control (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="96a79-105">構文</span><span class="sxs-lookup"><span data-stu-id="96a79-105">Syntax</span></span>

```xml
<ListItems>
  <ListItem>...</ListItem>
</ListItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="96a79-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="96a79-106">Attributes and Elements</span></span>

<span data-ttu-id="96a79-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `ListItems` ます。</span><span class="sxs-lookup"><span data-stu-id="96a79-107">The following sections describe the attributes, child elements, and parent element of the `ListItems` element.</span></span> <span data-ttu-id="96a79-108">指定できる子要素の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="96a79-108">There is no limit to the number of child elements that can be specified.</span></span> <span data-ttu-id="96a79-109">子要素の順序は、リストビューに表示される値の順序を定義します。</span><span class="sxs-lookup"><span data-stu-id="96a79-109">The order of the child elements defines the order that values are displayed in the list view.</span></span>

### <a name="attributes"></a><span data-ttu-id="96a79-110">属性</span><span class="sxs-lookup"><span data-stu-id="96a79-110">Attributes</span></span>

<span data-ttu-id="96a79-111">なし。</span><span class="sxs-lookup"><span data-stu-id="96a79-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="96a79-112">子要素</span><span class="sxs-lookup"><span data-stu-id="96a79-112">Child Elements</span></span>

|<span data-ttu-id="96a79-113">要素</span><span class="sxs-lookup"><span data-stu-id="96a79-113">Element</span></span>|<span data-ttu-id="96a79-114">説明</span><span class="sxs-lookup"><span data-stu-id="96a79-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="96a79-115">ListControl の ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="96a79-115">ListItem Element for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="96a79-116">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="96a79-116">Required element.</span></span><br /><br /> <span data-ttu-id="96a79-117">リストビューによって表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="96a79-117">Defines the property or script whose value is displayed by the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="96a79-118">親要素</span><span class="sxs-lookup"><span data-stu-id="96a79-118">Parent Elements</span></span>

|<span data-ttu-id="96a79-119">要素</span><span class="sxs-lookup"><span data-stu-id="96a79-119">Element</span></span>|<span data-ttu-id="96a79-120">説明</span><span class="sxs-lookup"><span data-stu-id="96a79-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="96a79-121">ListControl の ListEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="96a79-121">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="96a79-122">リストビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="96a79-122">Provides a definition of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="96a79-123">解説</span><span class="sxs-lookup"><span data-stu-id="96a79-123">Remarks</span></span>

<span data-ttu-id="96a79-124">この種類のビューの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96a79-124">For more information about this type of view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="96a79-125">例</span><span class="sxs-lookup"><span data-stu-id="96a79-125">Example</span></span>

<span data-ttu-id="96a79-126">この例は、リストビューの3つの行を定義する XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="96a79-126">This example shows the XML elements that define three rows of the list view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="96a79-127">参照</span><span class="sxs-lookup"><span data-stu-id="96a79-127">See Also</span></span>

[<span data-ttu-id="96a79-128">ListControl の ListEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="96a79-128">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="96a79-129">ListControl の ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="96a79-129">ListItem Element for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="96a79-130">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="96a79-130">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="96a79-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="96a79-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
