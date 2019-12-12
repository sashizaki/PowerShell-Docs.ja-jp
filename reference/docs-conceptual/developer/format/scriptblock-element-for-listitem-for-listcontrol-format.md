---
title: ListControl の ListItem の ScriptBlock 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 74e30938-00ef-46fd-84e5-f0a83706a50e
caps.latest.revision: 11
ms.openlocfilehash: 76b600256af3f957f7fe0578f9fef810262aa5d5
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364811"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="ac72b-102">ListControl の ListItem の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ac72b-102">ScriptBlock Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="ac72b-103">行に値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac72b-103">Specifies the script whose value is displayed in the row.</span></span>

<span data-ttu-id="ac72b-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (Format) ListControl (format) ListEntry 要素の listentries の ListControl (Format) ListItems 要素の listentries 要素for ListControl (Format) ListItem 要素 for ListItems for ListControl (Format) ScriptBlock for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ac72b-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ScriptBlock Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ac72b-105">構文</span><span class="sxs-lookup"><span data-stu-id="ac72b-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ac72b-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="ac72b-106">Attributes and Elements</span></span>

<span data-ttu-id="ac72b-107">次のセクションでは、`ScriptBlock` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac72b-107">The following sections describe the attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ac72b-108">属性</span><span class="sxs-lookup"><span data-stu-id="ac72b-108">Attributes</span></span>

<span data-ttu-id="ac72b-109">なし。</span><span class="sxs-lookup"><span data-stu-id="ac72b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ac72b-110">子要素</span><span class="sxs-lookup"><span data-stu-id="ac72b-110">Child Elements</span></span>

<span data-ttu-id="ac72b-111">なし。</span><span class="sxs-lookup"><span data-stu-id="ac72b-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ac72b-112">親要素</span><span class="sxs-lookup"><span data-stu-id="ac72b-112">Parent Elements</span></span>

|<span data-ttu-id="ac72b-113">要素</span><span class="sxs-lookup"><span data-stu-id="ac72b-113">Element</span></span>|<span data-ttu-id="ac72b-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="ac72b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ac72b-115">ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ac72b-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="ac72b-116">リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="ac72b-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ac72b-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="ac72b-117">Text Value</span></span>

<span data-ttu-id="ac72b-118">行に値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac72b-118">Specify the script whose value is displayed in the row.</span></span>

## <a name="remarks"></a><span data-ttu-id="ac72b-119">コメント</span><span class="sxs-lookup"><span data-stu-id="ac72b-119">Remarks</span></span>

<span data-ttu-id="ac72b-120">この要素が指定されている場合、 [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="ac72b-120">When this element is specified, you cannot specify the [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="ac72b-121">リストビューでのスクリプトの指定の詳細については、「[リストビュー](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac72b-121">For more information about specifying scripts in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ac72b-122">例</span><span class="sxs-lookup"><span data-stu-id="ac72b-122">Example</span></span>

<span data-ttu-id="ac72b-123">次の例は、値が表示されるプロパティを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ac72b-123">The following example shows how to specify the property whose value is displayed.</span></span>

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="ac72b-124">参照</span><span class="sxs-lookup"><span data-stu-id="ac72b-124">See Also</span></span>

[<span data-ttu-id="ac72b-125">ListControl の ListItem の PropertyName 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ac72b-125">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="ac72b-126">リストビューの作成</span><span class="sxs-lookup"><span data-stu-id="ac72b-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="ac72b-127">ListControl の ListItems の ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ac72b-127">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="ac72b-128">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="ac72b-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
