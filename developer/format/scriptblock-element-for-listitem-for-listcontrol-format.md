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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064579"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="7b733-102">ListControl の ListItem の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7b733-102">ScriptBlock Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="7b733-103">行の値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7b733-103">Specifies the script whose value is displayed in the row.</span></span>

<span data-ttu-id="7b733-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素の要素に ListControl (形式) ListEntry ListEntries ListEntry の ListControl (形式) のリスト項目要素のListControl (形式) を ListItem の ListControl (形式) スクリプト ブロックの要素の ListItems の ListItem 要素を ListControl (形式)</span><span class="sxs-lookup"><span data-stu-id="7b733-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ScriptBlock Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7b733-105">構文</span><span class="sxs-lookup"><span data-stu-id="7b733-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7b733-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7b733-106">Attributes and Elements</span></span>

<span data-ttu-id="7b733-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。</span><span class="sxs-lookup"><span data-stu-id="7b733-107">The following sections describe the attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7b733-108">属性</span><span class="sxs-lookup"><span data-stu-id="7b733-108">Attributes</span></span>

<span data-ttu-id="7b733-109">なし。</span><span class="sxs-lookup"><span data-stu-id="7b733-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7b733-110">子要素</span><span class="sxs-lookup"><span data-stu-id="7b733-110">Child Elements</span></span>

<span data-ttu-id="7b733-111">なし。</span><span class="sxs-lookup"><span data-stu-id="7b733-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7b733-112">親要素</span><span class="sxs-lookup"><span data-stu-id="7b733-112">Parent Elements</span></span>

|<span data-ttu-id="7b733-113">要素</span><span class="sxs-lookup"><span data-stu-id="7b733-113">Element</span></span>|<span data-ttu-id="7b733-114">説明</span><span class="sxs-lookup"><span data-stu-id="7b733-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7b733-115">ListItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7b733-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="7b733-116">プロパティまたはリスト ビューの行の値が表示されているスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="7b733-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7b733-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="7b733-117">Text Value</span></span>

<span data-ttu-id="7b733-118">行の値が表示されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7b733-118">Specify the script whose value is displayed in the row.</span></span>

## <a name="remarks"></a><span data-ttu-id="7b733-119">コメント</span><span class="sxs-lookup"><span data-stu-id="7b733-119">Remarks</span></span>

<span data-ttu-id="7b733-120">この要素が指定されている場合は指定できません、 [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)要素。</span><span class="sxs-lookup"><span data-stu-id="7b733-120">When this element is specified, you cannot specify the [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="7b733-121">リスト ビューでスクリプトを指定する方法については、次を参照してください。[リスト ビュー](./creating-a-list-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="7b733-121">For more information about specifying scripts in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="7b733-122">例</span><span class="sxs-lookup"><span data-stu-id="7b733-122">Example</span></span>

<span data-ttu-id="7b733-123">次の例では、値が表示されるプロパティを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7b733-123">The following example shows how to specify the property whose value is displayed.</span></span>

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="7b733-124">参照</span><span class="sxs-lookup"><span data-stu-id="7b733-124">See Also</span></span>

[<span data-ttu-id="7b733-125">PropertyName ListControl (形式) を ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="7b733-125">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="7b733-126">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="7b733-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="7b733-127">ListControl (形式) のリスト項目の ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="7b733-127">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="7b733-128">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="7b733-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
