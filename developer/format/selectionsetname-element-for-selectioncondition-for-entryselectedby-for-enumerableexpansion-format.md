---
title: EntrySelectedBy EnumerableExpansion (形式) 用の SelectionCondition SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b7af0b2-68e6-43c3-adcc-7c58007fced8
caps.latest.revision: 13
ms.openlocfilehash: 6f7c8d9af3c1c2fbda0208148b0088161701fdbe
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861218"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="cdfe2-102">EnumerableExpansion の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cdfe2-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="cdfe2-103">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="cdfe2-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="cdfe2-104">このセット内の型のいずれかが存在するときに、条件が満たされます。</span><span class="sxs-lookup"><span data-stu-id="cdfe2-104">When any of the types in this set are present, the condition is met.</span></span>

<span data-ttu-id="cdfe2-105">構成要素 DefaultSettings 要素 (形式) EnumerableExpansions 要素 (形式) EnumerableExpansions 要素 (形式) EntrySelectedBy 要素の EntrySelectedBy の EnumerableExpansion (形式) SelectionCondition 要素EntrySelectedBy EnumerableExpansion (形式) 用の SelectionCondition EnumerableExpansion (形式) SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="cdfe2-105">Configuration Element DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansions Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cdfe2-106">構文</span><span class="sxs-lookup"><span data-stu-id="cdfe2-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cdfe2-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="cdfe2-107">Attributes and Elements</span></span>

<span data-ttu-id="cdfe2-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。</span><span class="sxs-lookup"><span data-stu-id="cdfe2-108">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cdfe2-109">属性</span><span class="sxs-lookup"><span data-stu-id="cdfe2-109">Attributes</span></span>

<span data-ttu-id="cdfe2-110">なし。</span><span class="sxs-lookup"><span data-stu-id="cdfe2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cdfe2-111">子要素</span><span class="sxs-lookup"><span data-stu-id="cdfe2-111">Child Elements</span></span>

<span data-ttu-id="cdfe2-112">なし。</span><span class="sxs-lookup"><span data-stu-id="cdfe2-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cdfe2-113">親要素</span><span class="sxs-lookup"><span data-stu-id="cdfe2-113">Parent Elements</span></span>

|<span data-ttu-id="cdfe2-114">要素</span><span class="sxs-lookup"><span data-stu-id="cdfe2-114">Element</span></span>|<span data-ttu-id="cdfe2-115">説明</span><span class="sxs-lookup"><span data-stu-id="cdfe2-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cdfe2-116">EnumerableExpansion (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="cdfe2-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="cdfe2-117">この定義のコレクション オブジェクトの展開に必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="cdfe2-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="cdfe2-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="cdfe2-118">Text Value</span></span>

<span data-ttu-id="cdfe2-119">選択範囲のセットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cdfe2-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="cdfe2-120">コメント</span><span class="sxs-lookup"><span data-stu-id="cdfe2-120">Remarks</span></span>

<span data-ttu-id="cdfe2-121">選択条件では、選択範囲のセットまたは .NET の型を指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="cdfe2-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="cdfe2-122">選択条件を使用する方法の詳細については、[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdfe2-122">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="cdfe2-123">選択範囲のセットは、書式設定ファイルを定義する任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="cdfe2-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="cdfe2-124">作成と選択範囲のセットの参照の詳細については、[選択範囲の設定を定義する](./defining-selection-sets.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdfe2-124">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cdfe2-125">参照</span><span class="sxs-lookup"><span data-stu-id="cdfe2-125">See Also</span></span>

[<span data-ttu-id="cdfe2-126">選択範囲のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="cdfe2-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="cdfe2-127">EnumerableExpansion (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="cdfe2-127">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="cdfe2-128">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="cdfe2-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
