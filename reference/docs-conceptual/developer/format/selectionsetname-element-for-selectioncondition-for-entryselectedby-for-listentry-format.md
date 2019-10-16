---
title: ListEntry (Format) の EntrySelectedBy の SelectionCondition の SelectionSetName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eae67e47-6c60-4741-8430-78d2cb6067b1
caps.latest.revision: 10
ms.openlocfilehash: ccfc0b772ad3b2d1979c7c832a5153de870035d7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368401"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format"></a><span data-ttu-id="1fa47-102">ListEntry の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1fa47-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

<span data-ttu-id="1fa47-103">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa47-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="1fa47-104">このセット内のいずれかの型が存在する場合、条件が満たされ、リストビューのこの定義を使用してオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1fa47-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the list view.</span></span>

<span data-ttu-id="1fa47-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (形式) ListEntries Element (format) ListEntry Element (format) ListEntry (Format) SelectionCondition 要素のエントリListEntry (format) の EntrySelectedBy for ListEntry (Format) の EntrySelectedBy の SelectionCondition の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="1fa47-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1fa47-106">構文</span><span class="sxs-lookup"><span data-stu-id="1fa47-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1fa47-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="1fa47-107">Attributes and Elements</span></span>

<span data-ttu-id="1fa47-108">次のセクションでは、属性、子要素、`SelectionSetName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1fa47-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1fa47-109">属性</span><span class="sxs-lookup"><span data-stu-id="1fa47-109">Attributes</span></span>

<span data-ttu-id="1fa47-110">なし。</span><span class="sxs-lookup"><span data-stu-id="1fa47-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1fa47-111">子要素</span><span class="sxs-lookup"><span data-stu-id="1fa47-111">Child Elements</span></span>

<span data-ttu-id="1fa47-112">なし。</span><span class="sxs-lookup"><span data-stu-id="1fa47-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1fa47-113">親要素</span><span class="sxs-lookup"><span data-stu-id="1fa47-113">Parent Elements</span></span>

|<span data-ttu-id="1fa47-114">要素</span><span class="sxs-lookup"><span data-stu-id="1fa47-114">Element</span></span>|<span data-ttu-id="1fa47-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="1fa47-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1fa47-116">ListEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="1fa47-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="1fa47-117">リストビューのこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="1fa47-117">Defines the condition that must exist to use this definition of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1fa47-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="1fa47-118">Text Value</span></span>

<span data-ttu-id="1fa47-119">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa47-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="1fa47-120">コメント</span><span class="sxs-lookup"><span data-stu-id="1fa47-120">Remarks</span></span>

<span data-ttu-id="1fa47-121">選択条件では、選択セットまたは .NET 型を指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="1fa47-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="1fa47-122">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fa47-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="1fa47-123">選択セットは、書式設定ファイルによって定義される任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="1fa47-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="1fa47-124">選択セットの作成と参照の詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fa47-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="1fa47-125">リストビューのその他のコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fa47-125">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1fa47-126">参照</span><span class="sxs-lookup"><span data-stu-id="1fa47-126">See Also</span></span>

[<span data-ttu-id="1fa47-127">リストビューの作成</span><span class="sxs-lookup"><span data-stu-id="1fa47-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="1fa47-128">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="1fa47-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="1fa47-129">ListEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="1fa47-129">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="1fa47-130">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="1fa47-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
