---
ms.date: 09/13/2016
ms.topic: reference
title: ListControl の ListItem の Label 要素 (書式)
description: ListControl の ListItem の Label 要素 (書式)
ms.openlocfilehash: 01ff34c4129abe2c76a0a21794e756b77bff12bf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666656"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="817cb-103">ListControl の ListItem の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="817cb-103">Label Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="817cb-104">行内のプロパティまたはスクリプト値の左側に表示されるラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="817cb-104">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>

<span data-ttu-id="817cb-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries 要素の ListControl (format) ListEntry 要素の ListControl (format) ListItems の ListEntry 要素 (format) の ListItem 要素 ListControl for ListItems (format) の ListItem 要素を ListControl (format) に設定します。</span><span class="sxs-lookup"><span data-stu-id="817cb-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems for ListEntry for ListControl Element (Format) ListItem Element for ListItems for ListControl (Format) Label Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="817cb-106">構文</span><span class="sxs-lookup"><span data-stu-id="817cb-106">Syntax</span></span>

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="817cb-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="817cb-107">Attributes and Elements</span></span>

<span data-ttu-id="817cb-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `Label` ます。</span><span class="sxs-lookup"><span data-stu-id="817cb-108">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="817cb-109">属性</span><span class="sxs-lookup"><span data-stu-id="817cb-109">Attributes</span></span>

<span data-ttu-id="817cb-110">なし。</span><span class="sxs-lookup"><span data-stu-id="817cb-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="817cb-111">子要素</span><span class="sxs-lookup"><span data-stu-id="817cb-111">Child Elements</span></span>

<span data-ttu-id="817cb-112">なし。</span><span class="sxs-lookup"><span data-stu-id="817cb-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="817cb-113">親要素</span><span class="sxs-lookup"><span data-stu-id="817cb-113">Parent Elements</span></span>

|<span data-ttu-id="817cb-114">要素</span><span class="sxs-lookup"><span data-stu-id="817cb-114">Element</span></span>|<span data-ttu-id="817cb-115">説明</span><span class="sxs-lookup"><span data-stu-id="817cb-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="817cb-116">ListControl の ListItems の ListItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="817cb-116">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="817cb-117">リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="817cb-117">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="817cb-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="817cb-118">Text Value</span></span>

<span data-ttu-id="817cb-119">プロパティまたはスクリプト値の左側に表示するラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="817cb-119">Specify the label to be display to the left of the property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="817cb-120">解説</span><span class="sxs-lookup"><span data-stu-id="817cb-120">Remarks</span></span>

<span data-ttu-id="817cb-121">ラベルが指定されていない場合は、プロパティまたはスクリプトの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="817cb-121">If a label is not specified, the name of the property or the script is displayed.</span></span> <span data-ttu-id="817cb-122">リストビューでのラベルの使用の詳細については、「 [リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="817cb-122">For more information about using labels in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="817cb-123">例</span><span class="sxs-lookup"><span data-stu-id="817cb-123">Example</span></span>

<span data-ttu-id="817cb-124">次の例では、ラベルを行に追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="817cb-124">The following example shows how to add a label to a row.</span></span>

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="817cb-125">参照</span><span class="sxs-lookup"><span data-stu-id="817cb-125">See Also</span></span>

[<span data-ttu-id="817cb-126">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="817cb-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="817cb-127">ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="817cb-127">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="817cb-128">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="817cb-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
