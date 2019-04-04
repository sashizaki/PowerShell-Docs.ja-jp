---
title: PropertyName ListControl (形式) を ListItem 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01ae8cbe-acdc-4043-bd6e-1118a5691a55
caps.latest.revision: 12
ms.openlocfilehash: 405184f7bdbf1955f1df7766bf2723c244dcc27f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855738"
---
# <a name="propertyname-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="c0e79-102">ListControl の ListItem の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c0e79-102">PropertyName Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="c0e79-103">値が一覧に表示、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0e79-103">Specifies the .NET property whose value is displayed in the list.</span></span>

<span data-ttu-id="c0e79-104">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素 (形式) ListEntry 要素 (形式) ListItems 要素 (形式) ListItem 要素 (形式) PropertyName の構成要素ListItem (形式)</span><span class="sxs-lookup"><span data-stu-id="c0e79-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) ListItems Element (Format) ListItem Element (Format) PropertyName Element for ListItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c0e79-105">構文</span><span class="sxs-lookup"><span data-stu-id="c0e79-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c0e79-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="c0e79-106">Attributes and Elements</span></span>

<span data-ttu-id="c0e79-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。</span><span class="sxs-lookup"><span data-stu-id="c0e79-107">The following sections describe the attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c0e79-108">属性</span><span class="sxs-lookup"><span data-stu-id="c0e79-108">Attributes</span></span>

<span data-ttu-id="c0e79-109">なし。</span><span class="sxs-lookup"><span data-stu-id="c0e79-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c0e79-110">子要素</span><span class="sxs-lookup"><span data-stu-id="c0e79-110">Child Elements</span></span>

<span data-ttu-id="c0e79-111">なし。</span><span class="sxs-lookup"><span data-stu-id="c0e79-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c0e79-112">親要素</span><span class="sxs-lookup"><span data-stu-id="c0e79-112">Parent Elements</span></span>

|<span data-ttu-id="c0e79-113">要素</span><span class="sxs-lookup"><span data-stu-id="c0e79-113">Element</span></span>|<span data-ttu-id="c0e79-114">説明</span><span class="sxs-lookup"><span data-stu-id="c0e79-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c0e79-115">ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="c0e79-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="c0e79-116">プロパティまたはリスト ビューの行の値が表示されているスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="c0e79-116">Defines the property or script whose value is displayed in the row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c0e79-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="c0e79-117">Text Value</span></span>

<span data-ttu-id="c0e79-118">値が表示されるプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0e79-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="c0e79-119">コメント</span><span class="sxs-lookup"><span data-stu-id="c0e79-119">Remarks</span></span>

<span data-ttu-id="c0e79-120">この要素が指定されている場合は指定できません、 [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="c0e79-120">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="c0e79-121">プロパティの値を表示するだけでなく、値または値の表示を変更するために使用する書式指定文字列のラベルを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c0e79-121">In addition to displaying the property value, you can also specify a label for the value or a format string that can be used to change the display of the value.</span></span> <span data-ttu-id="c0e79-122">リスト ビューでデータを指定する方法については、[リスト ビューを作成する](./creating-a-list-view.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0e79-122">For more information about specifying data in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="c0e79-123">例</span><span class="sxs-lookup"><span data-stu-id="c0e79-123">Example</span></span>

<span data-ttu-id="c0e79-124">次の例では、ラベルと値が表示されるプロパティを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c0e79-124">The following example shows how to specify the label and property whose value is displayed.</span></span>

```xml
ListItem>
  <Label>NameOfProperty</Label>
  <PropertyName>.NetTypeProperty</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="c0e79-125">参照</span><span class="sxs-lookup"><span data-stu-id="c0e79-125">See Also</span></span>

[<span data-ttu-id="c0e79-126">ScriptBlock ListControl (形式) を ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="c0e79-126">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="c0e79-127">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="c0e79-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="c0e79-128">ListControl(Format) の ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="c0e79-128">ListItem Element for ListControl(Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="c0e79-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="c0e79-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
