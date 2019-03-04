---
title: SelectionCondition EntrySelectedBy EnumerableExpansion (形式) のためのスクリプト ブロックの要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4126b799-c43d-4175-8513-6d761c65437e
caps.latest.revision: 9
ms.openlocfilehash: a51d8d22fa8b0c7f303a5e8f37edcc5e57724063
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854798"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="4e2e7-102">EnumerableExpansion の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="4e2e7-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="4e2e7-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="4e2e7-103">Specifies the script that triggers the condition.</span></span>

<span data-ttu-id="4e2e7-104">構成要素 (形式) DefaultSettings 要素 (形式) EnumerableExpansions 要素 (形式) EnumerableExpansion 要素 (形式) EntrySelectedBy 要素の EntrySelectedBy の EnumerableExpansion (形式) SelectionCondition 要素EntrySelectedBy EnumerableExpansion (形式) 用の SelectionCondition EnumerableExpansion (形式) ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="4e2e7-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4e2e7-105">構文</span><span class="sxs-lookup"><span data-stu-id="4e2e7-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4e2e7-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="4e2e7-106">Attributes and Elements</span></span>

<span data-ttu-id="4e2e7-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。</span><span class="sxs-lookup"><span data-stu-id="4e2e7-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4e2e7-108">属性</span><span class="sxs-lookup"><span data-stu-id="4e2e7-108">Attributes</span></span>

<span data-ttu-id="4e2e7-109">なし。</span><span class="sxs-lookup"><span data-stu-id="4e2e7-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4e2e7-110">子要素</span><span class="sxs-lookup"><span data-stu-id="4e2e7-110">Child Elements</span></span>

<span data-ttu-id="4e2e7-111">なし。</span><span class="sxs-lookup"><span data-stu-id="4e2e7-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4e2e7-112">親要素</span><span class="sxs-lookup"><span data-stu-id="4e2e7-112">Parent Elements</span></span>

|<span data-ttu-id="4e2e7-113">要素</span><span class="sxs-lookup"><span data-stu-id="4e2e7-113">Element</span></span>|<span data-ttu-id="4e2e7-114">説明</span><span class="sxs-lookup"><span data-stu-id="4e2e7-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4e2e7-115">EnumerableExpansion (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="4e2e7-115">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="4e2e7-116">この定義のコレクション オブジェクトの展開に必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="4e2e7-116">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4e2e7-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="4e2e7-117">Text Value</span></span>

<span data-ttu-id="4e2e7-118">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="4e2e7-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e2e7-119">コメント</span><span class="sxs-lookup"><span data-stu-id="4e2e7-119">Remarks</span></span>

<span data-ttu-id="4e2e7-120">選択条件を評価するために、少なくとも 1 つのスクリプトまたはプロパティ名を指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="4e2e7-120">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="4e2e7-121">選択条件を使用する方法の詳細については、次を参照してください。[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="4e2e7-121">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4e2e7-122">参照</span><span class="sxs-lookup"><span data-stu-id="4e2e7-122">See Also</span></span>

[<span data-ttu-id="4e2e7-123">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="4e2e7-123">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="4e2e7-124">SelectionCondition EntrySelectedBy EnumerableExpansion (形式) のための PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="4e2e7-124">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="4e2e7-125">EnumerableExpansion (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="4e2e7-125">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="4e2e7-126">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="4e2e7-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
