---
title: EntrySelectedBy WideEntry (形式) 用の SelectionCondition SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a13a429c-a31b-4e29-828c-c0c0917b5415
caps.latest.revision: 11
ms.openlocfilehash: baea89e4b259611dfa45b6bcf94fa0bf2df6b9de
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854128"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="82d00-102">WideEntry の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="82d00-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="82d00-103">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="82d00-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="82d00-104">このセット内の型のいずれかが存在して、条件が満たされると、表示幅が広いは、この定義を使用して、オブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82d00-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the wide view.</span></span>

<span data-ttu-id="82d00-105">構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式) EntrySelectedBy 要素の WideEntry (形式) SelectionCondition 要素EntrySelectedBy SelectionCondition EntrySelectedBy WideEntry (形式) のための WideEntry (形式) SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="82d00-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="82d00-106">構文</span><span class="sxs-lookup"><span data-stu-id="82d00-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="82d00-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="82d00-107">Attributes and Elements</span></span>

<span data-ttu-id="82d00-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。</span><span class="sxs-lookup"><span data-stu-id="82d00-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="82d00-109">属性</span><span class="sxs-lookup"><span data-stu-id="82d00-109">Attributes</span></span>

<span data-ttu-id="82d00-110">なし。</span><span class="sxs-lookup"><span data-stu-id="82d00-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="82d00-111">子要素</span><span class="sxs-lookup"><span data-stu-id="82d00-111">Child Elements</span></span>

<span data-ttu-id="82d00-112">なし。</span><span class="sxs-lookup"><span data-stu-id="82d00-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="82d00-113">親要素</span><span class="sxs-lookup"><span data-stu-id="82d00-113">Parent Elements</span></span>

|<span data-ttu-id="82d00-114">要素</span><span class="sxs-lookup"><span data-stu-id="82d00-114">Element</span></span>|<span data-ttu-id="82d00-115">説明</span><span class="sxs-lookup"><span data-stu-id="82d00-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="82d00-116">WideEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="82d00-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="82d00-117">この定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="82d00-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="82d00-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="82d00-118">Text Value</span></span>

<span data-ttu-id="82d00-119">選択範囲のセットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="82d00-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="82d00-120">コメント</span><span class="sxs-lookup"><span data-stu-id="82d00-120">Remarks</span></span>

<span data-ttu-id="82d00-121">選択条件では、選択範囲のセットまたは .NET の型を指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="82d00-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="82d00-122">選択条件を使用する方法の詳細については、[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82d00-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="82d00-123">選択範囲のセットは、書式設定ファイルを定義する任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="82d00-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="82d00-124">作成と選択範囲のセットの参照の詳細については、[オブジェクト設定を定義する](./defining-selection-sets.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82d00-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="82d00-125">ワイド ビューの他のコンポーネントに関する詳細については、[ワイド ビューを作成する](./creating-a-wide-view.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82d00-125">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="82d00-126">参照</span><span class="sxs-lookup"><span data-stu-id="82d00-126">See Also</span></span>

[<span data-ttu-id="82d00-127">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="82d00-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="82d00-128">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="82d00-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="82d00-129">選択範囲のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="82d00-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="82d00-130">WideEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="82d00-130">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="82d00-131">SelectionCondition EntrySelectedBy WideEntry (形式) のための TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="82d00-131">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="82d00-132">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="82d00-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
