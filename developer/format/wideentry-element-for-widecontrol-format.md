---
title: WideControl (形式) の要素を WideEntry |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 014763cb-7716-4931-899c-8375b5d7a3dd
caps.latest.revision: 15
ms.openlocfilehash: d1d13b5c3436871053353814293d9163ea13c7fb
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856528"
---
# <a name="wideentry-element-for-widecontrol-format"></a><span data-ttu-id="e3846-102">WideControl の WideEntry 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e3846-102">WideEntry Element for WideControl (Format)</span></span>

<span data-ttu-id="e3846-103">ワイド ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="e3846-103">Provides a definition of the wide view.</span></span>

<span data-ttu-id="e3846-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e3846-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e3846-105">構文</span><span class="sxs-lookup"><span data-stu-id="e3846-105">Syntax</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e3846-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="e3846-106">Attributes and Elements</span></span>

<span data-ttu-id="e3846-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`WideEntry`要素。</span><span class="sxs-lookup"><span data-stu-id="e3846-107">The following sections describe the attributes, child elements, and the parent element of the `WideEntry` element.</span></span> <span data-ttu-id="e3846-108">1 つを指定する必要があります`WideItem`子要素。</span><span class="sxs-lookup"><span data-stu-id="e3846-108">You must specify a single `WideItem` child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e3846-109">属性</span><span class="sxs-lookup"><span data-stu-id="e3846-109">Attributes</span></span>

<span data-ttu-id="e3846-110">なし。</span><span class="sxs-lookup"><span data-stu-id="e3846-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e3846-111">子要素</span><span class="sxs-lookup"><span data-stu-id="e3846-111">Child Elements</span></span>

|<span data-ttu-id="e3846-112">要素</span><span class="sxs-lookup"><span data-stu-id="e3846-112">Element</span></span>|<span data-ttu-id="e3846-113">説明</span><span class="sxs-lookup"><span data-stu-id="e3846-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e3846-114">WideEntry (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="e3846-114">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="e3846-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e3846-115">Optional element.</span></span><br /><br /> <span data-ttu-id="e3846-116">このエントリのワイド定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="e3846-116">Defines the .NET types that use this wide entry definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="e3846-117">WideItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e3846-117">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="e3846-118">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="e3846-118">Required element.</span></span><br /><br /> <span data-ttu-id="e3846-119">プロパティまたは値が表示されているスクリプトを定義します。</span><span class="sxs-lookup"><span data-stu-id="e3846-119">Defines the property or script whose value is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e3846-120">親要素</span><span class="sxs-lookup"><span data-stu-id="e3846-120">Parent Elements</span></span>

|<span data-ttu-id="e3846-121">要素</span><span class="sxs-lookup"><span data-stu-id="e3846-121">Element</span></span>|<span data-ttu-id="e3846-122">説明</span><span class="sxs-lookup"><span data-stu-id="e3846-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e3846-123">WideEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e3846-123">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="e3846-124">表示幅が広いの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="e3846-124">Provides the definitions of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e3846-125">コメント</span><span class="sxs-lookup"><span data-stu-id="e3846-125">Remarks</span></span>

<span data-ttu-id="e3846-126">ワイド ビューは、1 つのプロパティの値または各オブジェクトのスクリプト値を表示する一覧の形式です。</span><span class="sxs-lookup"><span data-stu-id="e3846-126">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="e3846-127">その他の種類のビューとは異なり、各ビューの定義の項目要素を 1 つだけを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e3846-127">Unlike other types of views, you can specify only one item element for each view definition.</span></span> <span data-ttu-id="e3846-128">ワイド ビューの他のコンポーネントの詳細については、次を参照してください。[ワイド ビューを作成する](./creating-a-wide-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="e3846-128">For more information about the other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e3846-129">例</span><span class="sxs-lookup"><span data-stu-id="e3846-129">Example</span></span>

<span data-ttu-id="e3846-130">次の例は、 `WideEntry` 、1 つを定義する要素`WideItem`要素。</span><span class="sxs-lookup"><span data-stu-id="e3846-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="e3846-131">`WideItem`要素値を持つが、ビューに表示プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="e3846-131">The `WideItem` element defines the property whose value is displayed in the view.</span></span>

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

<span data-ttu-id="e3846-132">ワイド ビューの完全な例を参照してください。[表示 (Basic) の幅が広い](./wide-view-basic.md)します。</span><span class="sxs-lookup"><span data-stu-id="e3846-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e3846-133">参照</span><span class="sxs-lookup"><span data-stu-id="e3846-133">See Also</span></span>

[<span data-ttu-id="e3846-134">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="e3846-134">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="e3846-135">WideEntry (形式) の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="e3846-135">SelectionCondition Element for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="e3846-136">WideEntry (形式) の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="e3846-136">SelectionSetName Element for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="e3846-137">WideEntry (形式) の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="e3846-137">TypeName Element for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="e3846-138">WideEntries 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e3846-138">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="e3846-139">WideItem 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e3846-139">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="e3846-140">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="e3846-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
