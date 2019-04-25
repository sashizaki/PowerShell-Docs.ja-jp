---
title: PropertyName 要素 EntrySelectedBy WideEntry (形式) 用の SelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 340abb12-6df1-42f4-bdae-b0509c90952c
caps.latest.revision: 11
ms.openlocfilehash: 196877b97db9ed0592e357486c1318dc1e7efd31
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064681"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="f2820-102">WideEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f2820-102">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="f2820-103">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="f2820-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="f2820-104">このプロパティが存在するかを評価すると`true`条件が満たされ、定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="f2820-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="f2820-105">構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式) EntrySelectedBy 要素の WideEntry (形式) SelectionCondition 要素EntrySelectedBy SelectionCondition EntrySelectedBy WideEntry (形式) のための WideEntry (形式) PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="f2820-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f2820-106">構文</span><span class="sxs-lookup"><span data-stu-id="f2820-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

```csharp

```

## <a name="attributes-and-elements"></a><span data-ttu-id="f2820-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f2820-107">Attributes and Elements</span></span>

<span data-ttu-id="f2820-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。</span><span class="sxs-lookup"><span data-stu-id="f2820-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f2820-109">属性</span><span class="sxs-lookup"><span data-stu-id="f2820-109">Attributes</span></span>

<span data-ttu-id="f2820-110">なし。</span><span class="sxs-lookup"><span data-stu-id="f2820-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f2820-111">子要素</span><span class="sxs-lookup"><span data-stu-id="f2820-111">Child Elements</span></span>

<span data-ttu-id="f2820-112">なし。</span><span class="sxs-lookup"><span data-stu-id="f2820-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f2820-113">親要素</span><span class="sxs-lookup"><span data-stu-id="f2820-113">Parent Elements</span></span>

|<span data-ttu-id="f2820-114">要素</span><span class="sxs-lookup"><span data-stu-id="f2820-114">Element</span></span>|<span data-ttu-id="f2820-115">説明</span><span class="sxs-lookup"><span data-stu-id="f2820-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f2820-116">WideEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="f2820-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="f2820-117">この定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="f2820-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f2820-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="f2820-118">Text Value</span></span>

<span data-ttu-id="f2820-119">.NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f2820-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="f2820-120">コメント</span><span class="sxs-lookup"><span data-stu-id="f2820-120">Remarks</span></span>

<span data-ttu-id="f2820-121">少なくとも 1 つのプロパティ名またはスクリプトを評価する選択条件を指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f2820-121">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="f2820-122">選択条件を使用する方法の詳細については、次を参照してください。[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="f2820-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="f2820-123">ワイド ビューの他のコンポーネントに関する詳細については、次を参照してください。[表示幅が広い](./creating-a-wide-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="f2820-123">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f2820-124">参照</span><span class="sxs-lookup"><span data-stu-id="f2820-124">See Also</span></span>

[<span data-ttu-id="f2820-125">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="f2820-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="f2820-126">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="f2820-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="f2820-127">SelectionCondition EntrySelectedBy WideEntry (形式) のためのスクリプト ブロックの要素</span><span class="sxs-lookup"><span data-stu-id="f2820-127">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="f2820-128">WideEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="f2820-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="f2820-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="f2820-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
