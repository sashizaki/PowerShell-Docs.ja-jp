---
title: WideEntry (形式) の要素を EntrySelectedBy |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e0c98933-b7a5-4205-b811-06c0b0bf8988
caps.latest.revision: 9
ms.openlocfilehash: 54c7c261a23075721cd7bce75e530150dc0e0212
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854978"
---
# <a name="entryselectedby-element-for-wideentry-format"></a><span data-ttu-id="2b8da-102">WideEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2b8da-102">EntrySelectedBy Element for WideEntry (Format)</span></span>

<span data-ttu-id="2b8da-103">この定義の表示幅が広いまたは条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="2b8da-103">Defines the .NET types that use this definition of the wide view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="2b8da-104">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式) EntrySelectedBy 要素を WideEntry (形式)</span><span class="sxs-lookup"><span data-stu-id="2b8da-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2b8da-105">構文</span><span class="sxs-lookup"><span data-stu-id="2b8da-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2b8da-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="2b8da-106">Attributes and Elements</span></span>

<span data-ttu-id="2b8da-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`EntrySelectedBy`要素。</span><span class="sxs-lookup"><span data-stu-id="2b8da-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2b8da-108">属性</span><span class="sxs-lookup"><span data-stu-id="2b8da-108">Attributes</span></span>

<span data-ttu-id="2b8da-109">なし。</span><span class="sxs-lookup"><span data-stu-id="2b8da-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2b8da-110">子要素</span><span class="sxs-lookup"><span data-stu-id="2b8da-110">Child Elements</span></span>

|<span data-ttu-id="2b8da-111">要素</span><span class="sxs-lookup"><span data-stu-id="2b8da-111">Element</span></span>|<span data-ttu-id="2b8da-112">説明</span><span class="sxs-lookup"><span data-stu-id="2b8da-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2b8da-113">WideEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="2b8da-113">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="2b8da-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2b8da-114">Optional element.</span></span><br /><br /> <span data-ttu-id="2b8da-115">使用するには、この表示幅が広い定義を満たす必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="2b8da-115">Defines the condition that must exist for this wide view definition to be used.</span></span>|
|[<span data-ttu-id="2b8da-116">WideEntry (形式) の EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="2b8da-116">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="2b8da-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2b8da-117">Optional element.</span></span><br /><br /> <span data-ttu-id="2b8da-118">この表示幅が広い定義を使用する .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="2b8da-118">Specifies a set of .NET types that use this wide view definition.</span></span>|
|[<span data-ttu-id="2b8da-119">EntrySelectedBy WideEntry (形式) 用の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="2b8da-119">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="2b8da-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="2b8da-120">Optional element.</span></span><br /><br /> <span data-ttu-id="2b8da-121">この表示幅が広い定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="2b8da-121">Specifies a .NET type that uses this wide view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2b8da-122">親要素</span><span class="sxs-lookup"><span data-stu-id="2b8da-122">Parent Elements</span></span>

|<span data-ttu-id="2b8da-123">要素</span><span class="sxs-lookup"><span data-stu-id="2b8da-123">Element</span></span>|<span data-ttu-id="2b8da-124">説明</span><span class="sxs-lookup"><span data-stu-id="2b8da-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2b8da-125">WideEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="2b8da-125">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="2b8da-126">ワイド ビューの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="2b8da-126">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2b8da-127">コメント</span><span class="sxs-lookup"><span data-stu-id="2b8da-127">Remarks</span></span>

<span data-ttu-id="2b8da-128">少なくとも 1 つの型、選択範囲のセット、または表示幅が広い定義の選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b8da-128">You must specify at least one type, selection set, or selection condition for a wide view definition.</span></span> <span data-ttu-id="2b8da-129">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="2b8da-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="2b8da-130">選択条件を使用して、定義オブジェクトに特定のプロパティがある場合など、使用するのに必要な条件を定義または特定のプロパティの値またはスクリプトの値を評価する`true`します。</span><span class="sxs-lookup"><span data-stu-id="2b8da-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script value evaluates to `true`.</span></span> <span data-ttu-id="2b8da-131">選択条件の詳細については、[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b8da-131">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="2b8da-132">ワイド ビューの他のコンポーネントに関する詳細については、[ワイド ビューを作成する](./creating-a-wide-view.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b8da-132">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2b8da-133">参照</span><span class="sxs-lookup"><span data-stu-id="2b8da-133">See Also</span></span>

[<span data-ttu-id="2b8da-134">WideEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="2b8da-134">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="2b8da-135">WideEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="2b8da-135">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="2b8da-136">WideEntry (形式) の EntrySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="2b8da-136">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="2b8da-137">EntrySelectedBy WideEntry (形式) 用の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="2b8da-137">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="2b8da-138">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="2b8da-138">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="2b8da-139">データを表示するための条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="2b8da-139">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="2b8da-140">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="2b8da-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
