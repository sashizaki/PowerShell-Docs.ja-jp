---
title: ListControl の ListItem の Label 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c693ff46-d1ad-4dc7-93ac-41ff2fc6c103
caps.latest.revision: 9
ms.openlocfilehash: c1293d5a1f942704ac01388c66bd9009fd340e82
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362891"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="479aa-102">ListControl の ListItem の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="479aa-102">Label Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="479aa-103">行内のプロパティまたはスクリプト値の左側に表示されるラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="479aa-103">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>

<span data-ttu-id="479aa-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (Format) ListEntries 要素の ListControl (format) ListEntry 要素の ListControl (Format) ListItems for ListEntry 要素 (Format) ListControl の ListItem の ListItems for ListControl (Format) Label 要素の ListItem 要素をフォーマットします。</span><span class="sxs-lookup"><span data-stu-id="479aa-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems for ListEntry for ListControl Element (Format) ListItem Element for ListItems for ListControl (Format) Label Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="479aa-105">構文</span><span class="sxs-lookup"><span data-stu-id="479aa-105">Syntax</span></span>

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="479aa-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="479aa-106">Attributes and Elements</span></span>

<span data-ttu-id="479aa-107">次のセクションでは、`Label` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="479aa-107">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="479aa-108">属性</span><span class="sxs-lookup"><span data-stu-id="479aa-108">Attributes</span></span>

<span data-ttu-id="479aa-109">なし。</span><span class="sxs-lookup"><span data-stu-id="479aa-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="479aa-110">子要素</span><span class="sxs-lookup"><span data-stu-id="479aa-110">Child Elements</span></span>

<span data-ttu-id="479aa-111">なし。</span><span class="sxs-lookup"><span data-stu-id="479aa-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="479aa-112">親要素</span><span class="sxs-lookup"><span data-stu-id="479aa-112">Parent Elements</span></span>

|<span data-ttu-id="479aa-113">要素</span><span class="sxs-lookup"><span data-stu-id="479aa-113">Element</span></span>|<span data-ttu-id="479aa-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="479aa-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="479aa-115">ListControl の ListItems の ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="479aa-115">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="479aa-116">リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="479aa-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="479aa-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="479aa-117">Text Value</span></span>

<span data-ttu-id="479aa-118">プロパティまたはスクリプト値の左側に表示するラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="479aa-118">Specify the label to be display to the left of the property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="479aa-119">コメント</span><span class="sxs-lookup"><span data-stu-id="479aa-119">Remarks</span></span>

<span data-ttu-id="479aa-120">ラベルが指定されていない場合は、プロパティまたはスクリプトの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="479aa-120">If a label is not specified, the name of the property or the script is displayed.</span></span> <span data-ttu-id="479aa-121">リストビューでのラベルの使用の詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="479aa-121">For more information about using labels in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="479aa-122">例</span><span class="sxs-lookup"><span data-stu-id="479aa-122">Example</span></span>

<span data-ttu-id="479aa-123">次の例では、ラベルを行に追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="479aa-123">The following example shows how to add a label to a row.</span></span>

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="479aa-124">参照</span><span class="sxs-lookup"><span data-stu-id="479aa-124">See Also</span></span>

[<span data-ttu-id="479aa-125">リストビューの作成</span><span class="sxs-lookup"><span data-stu-id="479aa-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="479aa-126">ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="479aa-126">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="479aa-127">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="479aa-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
