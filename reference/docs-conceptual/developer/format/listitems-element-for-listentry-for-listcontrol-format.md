---
title: ListControl (Format) の ListEntry の ListItems 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2c1da6d-acc7-4fe8-9e7d-6dcddc2787cd
caps.latest.revision: 9
ms.openlocfilehash: c25f18489d9c7abd8889758499dbbacd6ee29304
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362741"
---
# <a name="listitems-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="bc3a0-102">ListControl の ListEntry の ListItems 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bc3a0-102">ListItems Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="bc3a0-103">リストビューの行に値が表示されるプロパティとスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="bc3a0-103">Defines the properties and scripts whose values are displayed in the rows of the list view.</span></span>

<span data-ttu-id="bc3a0-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (format) ListControl (format) ListItems 要素のリストコントロール (format) ListEntry 要素の ListEntries 要素を ListControl (Format) に設定します。</span><span class="sxs-lookup"><span data-stu-id="bc3a0-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for List Control (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bc3a0-105">構文</span><span class="sxs-lookup"><span data-stu-id="bc3a0-105">Syntax</span></span>

```xml
<ListItems>
  <ListItem>...</ListItem>
</ListItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bc3a0-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="bc3a0-106">Attributes and Elements</span></span>

<span data-ttu-id="bc3a0-107">次のセクションでは、`ListItems` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc3a0-107">The following sections describe the attributes, child elements, and parent element of the `ListItems` element.</span></span> <span data-ttu-id="bc3a0-108">指定できる子要素の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="bc3a0-108">There is no limit to the number of child elements that can be specified.</span></span> <span data-ttu-id="bc3a0-109">子要素の順序は、リストビューに表示される値の順序を定義します。</span><span class="sxs-lookup"><span data-stu-id="bc3a0-109">The order of the child elements defines the order that values are displayed in the list view.</span></span>

### <a name="attributes"></a><span data-ttu-id="bc3a0-110">属性</span><span class="sxs-lookup"><span data-stu-id="bc3a0-110">Attributes</span></span>

<span data-ttu-id="bc3a0-111">なし。</span><span class="sxs-lookup"><span data-stu-id="bc3a0-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bc3a0-112">子要素</span><span class="sxs-lookup"><span data-stu-id="bc3a0-112">Child Elements</span></span>

|<span data-ttu-id="bc3a0-113">要素</span><span class="sxs-lookup"><span data-stu-id="bc3a0-113">Element</span></span>|<span data-ttu-id="bc3a0-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="bc3a0-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bc3a0-115">ListControl の ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bc3a0-115">ListItem Element for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="bc3a0-116">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="bc3a0-116">Required element.</span></span><br /><br /> <span data-ttu-id="bc3a0-117">リストビューによって表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="bc3a0-117">Defines the property or script whose value is displayed by the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bc3a0-118">親要素</span><span class="sxs-lookup"><span data-stu-id="bc3a0-118">Parent Elements</span></span>

|<span data-ttu-id="bc3a0-119">要素</span><span class="sxs-lookup"><span data-stu-id="bc3a0-119">Element</span></span>|<span data-ttu-id="bc3a0-120">[説明]</span><span class="sxs-lookup"><span data-stu-id="bc3a0-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bc3a0-121">ListControl の ListEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bc3a0-121">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="bc3a0-122">リストビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="bc3a0-122">Provides a definition of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bc3a0-123">コメント</span><span class="sxs-lookup"><span data-stu-id="bc3a0-123">Remarks</span></span>

<span data-ttu-id="bc3a0-124">この種類のビューの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc3a0-124">For more information about this type of view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="bc3a0-125">例</span><span class="sxs-lookup"><span data-stu-id="bc3a0-125">Example</span></span>

<span data-ttu-id="bc3a0-126">この例は、リストビューの3つの行を定義する XML 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="bc3a0-126">This example shows the XML elements that define three rows of the list view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="bc3a0-127">参照</span><span class="sxs-lookup"><span data-stu-id="bc3a0-127">See Also</span></span>

[<span data-ttu-id="bc3a0-128">ListControl の ListEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bc3a0-128">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="bc3a0-129">ListControl の ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="bc3a0-129">ListItem Element for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="bc3a0-130">リストビューの作成</span><span class="sxs-lookup"><span data-stu-id="bc3a0-130">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="bc3a0-131">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="bc3a0-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
