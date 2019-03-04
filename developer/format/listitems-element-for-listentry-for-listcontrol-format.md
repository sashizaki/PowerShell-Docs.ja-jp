---
title: ListEntry ListControl (形式) のリスト項目要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2c1da6d-acc7-4fe8-9e7d-6dcddc2787cd
caps.latest.revision: 9
ms.openlocfilehash: c25f18489d9c7abd8889758499dbbacd6ee29304
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858588"
---
# <a name="listitems-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="220df-102">ListControl の ListEntry の ListItems 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="220df-102">ListItems Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="220df-103">リスト ビュー内の行の表示が値を持つスクリプトとプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="220df-103">Defines the properties and scripts whose values are displayed in the rows of the list view.</span></span>

<span data-ttu-id="220df-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素の要素リスト コントロール (形式) ListEntry ListControl (形式) のリスト項目要素を ListControl (形式)</span><span class="sxs-lookup"><span data-stu-id="220df-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for List Control (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="220df-105">構文</span><span class="sxs-lookup"><span data-stu-id="220df-105">Syntax</span></span>

```xml
<ListItems>
  <ListItem>...</ListItem>
</ListItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="220df-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="220df-106">Attributes and Elements</span></span>

<span data-ttu-id="220df-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`ListItems`要素。</span><span class="sxs-lookup"><span data-stu-id="220df-107">The following sections describe the attributes, child elements, and parent element of the `ListItems` element.</span></span> <span data-ttu-id="220df-108">指定できる子要素の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="220df-108">There is no limit to the number of child elements that can be specified.</span></span> <span data-ttu-id="220df-109">子要素の順序は、値がリスト ビューに表示される順序を定義します。</span><span class="sxs-lookup"><span data-stu-id="220df-109">The order of the child elements defines the order that values are displayed in the list view.</span></span>

### <a name="attributes"></a><span data-ttu-id="220df-110">属性</span><span class="sxs-lookup"><span data-stu-id="220df-110">Attributes</span></span>

<span data-ttu-id="220df-111">なし。</span><span class="sxs-lookup"><span data-stu-id="220df-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="220df-112">子要素</span><span class="sxs-lookup"><span data-stu-id="220df-112">Child Elements</span></span>

|<span data-ttu-id="220df-113">要素</span><span class="sxs-lookup"><span data-stu-id="220df-113">Element</span></span>|<span data-ttu-id="220df-114">説明</span><span class="sxs-lookup"><span data-stu-id="220df-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="220df-115">ListControl (形式) を ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="220df-115">ListItem Element for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="220df-116">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="220df-116">Required element.</span></span><br /><br /> <span data-ttu-id="220df-117">プロパティまたは値がリスト ビューで表示されているスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="220df-117">Defines the property or script whose value is displayed by the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="220df-118">親要素</span><span class="sxs-lookup"><span data-stu-id="220df-118">Parent Elements</span></span>

|<span data-ttu-id="220df-119">要素</span><span class="sxs-lookup"><span data-stu-id="220df-119">Element</span></span>|<span data-ttu-id="220df-120">説明</span><span class="sxs-lookup"><span data-stu-id="220df-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="220df-121">ListControl (形式) の ListEntry 要素</span><span class="sxs-lookup"><span data-stu-id="220df-121">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="220df-122">リスト ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="220df-122">Provides a definition of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="220df-123">コメント</span><span class="sxs-lookup"><span data-stu-id="220df-123">Remarks</span></span>

<span data-ttu-id="220df-124">この種類のビューの詳細については、次を参照してください。[リスト ビューを作成する](./creating-a-list-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="220df-124">For more information about this type of view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="220df-125">例</span><span class="sxs-lookup"><span data-stu-id="220df-125">Example</span></span>

<span data-ttu-id="220df-126">この例では、リスト ビューの 3 つの行を定義する XML 要素を示します。</span><span class="sxs-lookup"><span data-stu-id="220df-126">This example shows the XML elements that define three rows of the list view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="220df-127">参照</span><span class="sxs-lookup"><span data-stu-id="220df-127">See Also</span></span>

[<span data-ttu-id="220df-128">ListControl (形式) の ListEntry 要素</span><span class="sxs-lookup"><span data-stu-id="220df-128">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="220df-129">ListControl (形式) を ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="220df-129">ListItem Element for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="220df-130">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="220df-130">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="220df-131">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="220df-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
