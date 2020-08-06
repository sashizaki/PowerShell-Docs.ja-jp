---
title: ListControl の ListItem の Label 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: ad80cc0478e7567b12d264ab661d843248ba48e1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783638"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="f706c-102">ListControl の ListItem の Label 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f706c-102">Label Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="f706c-103">行内のプロパティまたはスクリプト値の左側に表示されるラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="f706c-103">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>

<span data-ttu-id="f706c-104">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl Element (format) ListEntries 要素の ListControl (format) ListEntry 要素の ListControl (format) ListItems の ListEntry 要素 (format) の ListItem 要素 ListControl for ListItems (format) の ListItem 要素を ListControl (format) に設定します。</span><span class="sxs-lookup"><span data-stu-id="f706c-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems for ListEntry for ListControl Element (Format) ListItem Element for ListItems for ListControl (Format) Label Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f706c-105">構文</span><span class="sxs-lookup"><span data-stu-id="f706c-105">Syntax</span></span>

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f706c-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f706c-106">Attributes and Elements</span></span>

<span data-ttu-id="f706c-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `Label` ます。</span><span class="sxs-lookup"><span data-stu-id="f706c-107">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f706c-108">属性</span><span class="sxs-lookup"><span data-stu-id="f706c-108">Attributes</span></span>

<span data-ttu-id="f706c-109">なし。</span><span class="sxs-lookup"><span data-stu-id="f706c-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f706c-110">子要素</span><span class="sxs-lookup"><span data-stu-id="f706c-110">Child Elements</span></span>

<span data-ttu-id="f706c-111">なし。</span><span class="sxs-lookup"><span data-stu-id="f706c-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f706c-112">親要素</span><span class="sxs-lookup"><span data-stu-id="f706c-112">Parent Elements</span></span>

|<span data-ttu-id="f706c-113">要素</span><span class="sxs-lookup"><span data-stu-id="f706c-113">Element</span></span>|<span data-ttu-id="f706c-114">説明</span><span class="sxs-lookup"><span data-stu-id="f706c-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f706c-115">ListControl の ListItems の ListItem 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f706c-115">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="f706c-116">リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="f706c-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f706c-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="f706c-117">Text Value</span></span>

<span data-ttu-id="f706c-118">プロパティまたはスクリプト値の左側に表示するラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="f706c-118">Specify the label to be display to the left of the property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="f706c-119">解説</span><span class="sxs-lookup"><span data-stu-id="f706c-119">Remarks</span></span>

<span data-ttu-id="f706c-120">ラベルが指定されていない場合は、プロパティまたはスクリプトの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f706c-120">If a label is not specified, the name of the property or the script is displayed.</span></span> <span data-ttu-id="f706c-121">リストビューでのラベルの使用の詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f706c-121">For more information about using labels in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="f706c-122">例</span><span class="sxs-lookup"><span data-stu-id="f706c-122">Example</span></span>

<span data-ttu-id="f706c-123">次の例では、ラベルを行に追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f706c-123">The following example shows how to add a label to a row.</span></span>

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="f706c-124">参照</span><span class="sxs-lookup"><span data-stu-id="f706c-124">See Also</span></span>

[<span data-ttu-id="f706c-125">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="f706c-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="f706c-126">ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="f706c-126">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="f706c-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="f706c-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
