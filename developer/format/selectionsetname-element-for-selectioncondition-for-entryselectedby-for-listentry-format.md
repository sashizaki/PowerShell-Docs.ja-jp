---
title: EntrySelectedBy ListEntry (形式) 用の SelectionCondition SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eae67e47-6c60-4741-8430-78d2cb6067b1
caps.latest.revision: 10
ms.openlocfilehash: ccfc0b772ad3b2d1979c7c832a5153de870035d7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862198"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format"></a><span data-ttu-id="c4ed0-102">ListEntry の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c4ed0-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

<span data-ttu-id="c4ed0-103">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4ed0-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="c4ed0-104">このセット内の型のいずれかが存在して、条件が満たされると、リスト ビューのこの定義を使用して、オブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4ed0-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the list view.</span></span>

<span data-ttu-id="c4ed0-105">構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) ListControl 要素 (形式) ListEntries 要素 (形式) ListEntry 要素 (形式) EntrySelectedBy 要素の ListEntry (形式) SelectionCondition 要素EntrySelectedBy SelectionCondition EntrySelectedBy ListEntry (形式) のための ListEntry (形式) SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="c4ed0-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c4ed0-106">構文</span><span class="sxs-lookup"><span data-stu-id="c4ed0-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c4ed0-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="c4ed0-107">Attributes and Elements</span></span>

<span data-ttu-id="c4ed0-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。</span><span class="sxs-lookup"><span data-stu-id="c4ed0-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c4ed0-109">属性</span><span class="sxs-lookup"><span data-stu-id="c4ed0-109">Attributes</span></span>

<span data-ttu-id="c4ed0-110">なし。</span><span class="sxs-lookup"><span data-stu-id="c4ed0-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c4ed0-111">子要素</span><span class="sxs-lookup"><span data-stu-id="c4ed0-111">Child Elements</span></span>

<span data-ttu-id="c4ed0-112">なし。</span><span class="sxs-lookup"><span data-stu-id="c4ed0-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c4ed0-113">親要素</span><span class="sxs-lookup"><span data-stu-id="c4ed0-113">Parent Elements</span></span>

|<span data-ttu-id="c4ed0-114">要素</span><span class="sxs-lookup"><span data-stu-id="c4ed0-114">Element</span></span>|<span data-ttu-id="c4ed0-115">説明</span><span class="sxs-lookup"><span data-stu-id="c4ed0-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c4ed0-116">ListEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="c4ed0-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="c4ed0-117">リスト ビューのこの定義を使用する必要があります条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="c4ed0-117">Defines the condition that must exist to use this definition of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c4ed0-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="c4ed0-118">Text Value</span></span>

<span data-ttu-id="c4ed0-119">選択範囲のセットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c4ed0-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="c4ed0-120">コメント</span><span class="sxs-lookup"><span data-stu-id="c4ed0-120">Remarks</span></span>

<span data-ttu-id="c4ed0-121">選択条件では、選択範囲のセットまたは .NET の型を指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c4ed0-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="c4ed0-122">選択条件を使用する方法の詳細については、次を参照してください。[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="c4ed0-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="c4ed0-123">選択範囲のセットは、書式設定ファイルを定義する任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="c4ed0-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="c4ed0-124">作成と選択範囲のセットの参照の詳細については、次を参照してください。[オブジェクト設定を定義する](./defining-selection-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="c4ed0-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="c4ed0-125">リスト ビューの他のコンポーネントに関する詳細については、次を参照してください。[リスト ビューを作成する](./creating-a-list-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="c4ed0-125">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c4ed0-126">参照</span><span class="sxs-lookup"><span data-stu-id="c4ed0-126">See Also</span></span>

[<span data-ttu-id="c4ed0-127">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="c4ed0-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="c4ed0-128">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="c4ed0-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="c4ed0-129">ListEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="c4ed0-129">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="c4ed0-130">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="c4ed0-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
