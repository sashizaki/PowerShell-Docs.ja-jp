---
title: PropertyName 要素 EntrySelectedBy ListControl (形式) 用の SelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71c3f1f6-6fe2-42f1-8260-6974d3871748
caps.latest.revision: 11
ms.openlocfilehash: f857f5944b9e971215a06d6f5c39f7c22c6cf99f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853298"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="5162c-102">ListControl の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="5162c-102">PropertyName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="5162c-103">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="5162c-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="5162c-104">このプロパティが存在するかを評価すると`true`条件が満たされ、一覧のエントリを使用します。</span><span class="sxs-lookup"><span data-stu-id="5162c-104">When this property is present or when it evaluates to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="5162c-105">構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) ListControl 要素 (形式) ListEntries 要素 (形式) ListEntry 要素 (形式) EntrySelectedBy 要素の ListEntry (形式) SelectionCondition 要素EntrySelectedBy SelectionCondition EmtrySelectedBy ListEntry (形式) のための ListEntry (形式) PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="5162c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) PropertyName Element for SelectionCondition for EmtrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5162c-106">構文</span><span class="sxs-lookup"><span data-stu-id="5162c-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5162c-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="5162c-107">Attributes and Elements</span></span>

<span data-ttu-id="5162c-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。</span><span class="sxs-lookup"><span data-stu-id="5162c-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5162c-109">属性</span><span class="sxs-lookup"><span data-stu-id="5162c-109">Attributes</span></span>

<span data-ttu-id="5162c-110">なし。</span><span class="sxs-lookup"><span data-stu-id="5162c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5162c-111">子要素</span><span class="sxs-lookup"><span data-stu-id="5162c-111">Child Elements</span></span>

<span data-ttu-id="5162c-112">なし。</span><span class="sxs-lookup"><span data-stu-id="5162c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5162c-113">親要素</span><span class="sxs-lookup"><span data-stu-id="5162c-113">Parent Elements</span></span>

|<span data-ttu-id="5162c-114">要素</span><span class="sxs-lookup"><span data-stu-id="5162c-114">Element</span></span>|<span data-ttu-id="5162c-115">説明</span><span class="sxs-lookup"><span data-stu-id="5162c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5162c-116">ListEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="5162c-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="5162c-117">このリストのエントリを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="5162c-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5162c-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="5162c-118">Text Value</span></span>

<span data-ttu-id="5162c-119">.NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5162c-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="5162c-120">コメント</span><span class="sxs-lookup"><span data-stu-id="5162c-120">Remarks</span></span>

<span data-ttu-id="5162c-121">選択条件では、少なくとも 1 つのプロパティの名前またはスクリプト ブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="5162c-121">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="5162c-122">選択条件を使用する方法の詳細については、次を参照してください。[とビューのエントリの定義の条件またはアイテムが使用されて](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="5162c-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="5162c-123">リスト ビューの他のコンポーネントに関する詳細については、次を参照してください。[リスト ビューの作成](./creating-a-list-view.md)です。</span><span class="sxs-lookup"><span data-stu-id="5162c-123">For more information about other components of a list view, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5162c-124">参照</span><span class="sxs-lookup"><span data-stu-id="5162c-124">See Also</span></span>

[<span data-ttu-id="5162c-125">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="5162c-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="5162c-126">ときにデータの条件の定義が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5162c-126">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="5162c-127">ListEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="5162c-127">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="5162c-128">SelectionCondition EntrySelectedBy ListEntry (形式) のためのスクリプト ブロックの要素</span><span class="sxs-lookup"><span data-stu-id="5162c-128">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="5162c-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="5162c-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
