---
title: ScriptBlock ListControl (形式) を ListItem 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 74e30938-00ef-46fd-84e5-f0a83706a50e
caps.latest.revision: 11
ms.openlocfilehash: 76b600256af3f957f7fe0578f9fef810262aa5d5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855558"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="d25eb-102">ListControl の ListItem の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d25eb-102">ScriptBlock Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="d25eb-103">行の値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d25eb-103">Specifies the script whose value is displayed in the row.</span></span>

<span data-ttu-id="d25eb-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素の要素に ListControl (形式) ListEntry ListEntries ListEntry の ListControl (形式) のリスト項目要素のListControl (形式) を ListItem の ListControl (形式) スクリプト ブロックの要素の ListItems の ListItem 要素を ListControl (形式)</span><span class="sxs-lookup"><span data-stu-id="d25eb-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ScriptBlock Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d25eb-105">構文</span><span class="sxs-lookup"><span data-stu-id="d25eb-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d25eb-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="d25eb-106">Attributes and Elements</span></span>

<span data-ttu-id="d25eb-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。</span><span class="sxs-lookup"><span data-stu-id="d25eb-107">The following sections describe the attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d25eb-108">属性</span><span class="sxs-lookup"><span data-stu-id="d25eb-108">Attributes</span></span>

<span data-ttu-id="d25eb-109">なし。</span><span class="sxs-lookup"><span data-stu-id="d25eb-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d25eb-110">子要素</span><span class="sxs-lookup"><span data-stu-id="d25eb-110">Child Elements</span></span>

<span data-ttu-id="d25eb-111">なし。</span><span class="sxs-lookup"><span data-stu-id="d25eb-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d25eb-112">親要素</span><span class="sxs-lookup"><span data-stu-id="d25eb-112">Parent Elements</span></span>

|<span data-ttu-id="d25eb-113">要素</span><span class="sxs-lookup"><span data-stu-id="d25eb-113">Element</span></span>|<span data-ttu-id="d25eb-114">説明</span><span class="sxs-lookup"><span data-stu-id="d25eb-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d25eb-115">ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="d25eb-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="d25eb-116">プロパティまたはリスト ビューの行の値が表示されているスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="d25eb-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d25eb-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="d25eb-117">Text Value</span></span>

<span data-ttu-id="d25eb-118">行の値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d25eb-118">Specify the script whose value is displayed in the row.</span></span>

## <a name="remarks"></a><span data-ttu-id="d25eb-119">コメント</span><span class="sxs-lookup"><span data-stu-id="d25eb-119">Remarks</span></span>

<span data-ttu-id="d25eb-120">この要素が指定されている場合は指定できません、 [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="d25eb-120">When this element is specified, you cannot specify the [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="d25eb-121">リスト ビューでスクリプトを指定する方法については、次を参照してください。[リスト ビュー](./creating-a-list-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="d25eb-121">For more information about specifying scripts in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="d25eb-122">例</span><span class="sxs-lookup"><span data-stu-id="d25eb-122">Example</span></span>

<span data-ttu-id="d25eb-123">次の例では、値が表示されるプロパティを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d25eb-123">The following example shows how to specify the property whose value is displayed.</span></span>

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="d25eb-124">参照</span><span class="sxs-lookup"><span data-stu-id="d25eb-124">See Also</span></span>

[<span data-ttu-id="d25eb-125">PropertyName ListControl (形式) を ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="d25eb-125">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="d25eb-126">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="d25eb-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="d25eb-127">ListControl (形式) のリスト項目の ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="d25eb-127">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="d25eb-128">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="d25eb-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
