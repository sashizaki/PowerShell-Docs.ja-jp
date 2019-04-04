---
title: PropertyName 要素 EntrySelectedBy EnumerableExpansion (形式) 用の SelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ae11924-0072-451e-bf70-c5ffb25dccc0
caps.latest.revision: 13
ms.openlocfilehash: 0c20512e660c8d2b61d063dbd7078b55b23efeb8
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859628"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="13d7a-102">EnumerableExpansion の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="13d7a-102">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="13d7a-103">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="13d7a-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="13d7a-104">このプロパティが存在するかを評価すると`true`条件が満たされ、定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="13d7a-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="13d7a-105">構成要素 (形式) DefaultSettings 要素 (形式) EnumerableExpansions 要素 (形式) EnumerableExpansion 要素 (形式) EntrySelectedBy 要素の EntrySelectedBy の EnumerableExpansion (形式) SelectionCondition 要素EntrySelectedBy EnumerableExpansion (形式) 用の SelectionCondition EnumerableExpansion (形式) PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="13d7a-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="13d7a-106">構文</span><span class="sxs-lookup"><span data-stu-id="13d7a-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="13d7a-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="13d7a-107">Attributes and Elements</span></span>

<span data-ttu-id="13d7a-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。</span><span class="sxs-lookup"><span data-stu-id="13d7a-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="13d7a-109">属性</span><span class="sxs-lookup"><span data-stu-id="13d7a-109">Attributes</span></span>

<span data-ttu-id="13d7a-110">なし。</span><span class="sxs-lookup"><span data-stu-id="13d7a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="13d7a-111">子要素</span><span class="sxs-lookup"><span data-stu-id="13d7a-111">Child Elements</span></span>

<span data-ttu-id="13d7a-112">なし。</span><span class="sxs-lookup"><span data-stu-id="13d7a-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="13d7a-113">親要素</span><span class="sxs-lookup"><span data-stu-id="13d7a-113">Parent Elements</span></span>

|<span data-ttu-id="13d7a-114">要素</span><span class="sxs-lookup"><span data-stu-id="13d7a-114">Element</span></span>|<span data-ttu-id="13d7a-115">説明</span><span class="sxs-lookup"><span data-stu-id="13d7a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="13d7a-116">EnumerableExpansion (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="13d7a-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="13d7a-117">この定義のコレクション オブジェクトの展開に必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="13d7a-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="13d7a-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="13d7a-118">Text Value</span></span>

<span data-ttu-id="13d7a-119">.NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="13d7a-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="13d7a-120">コメント</span><span class="sxs-lookup"><span data-stu-id="13d7a-120">Remarks</span></span>

<span data-ttu-id="13d7a-121">少なくとも 1 つのプロパティ名またはスクリプトを評価する選択条件を指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="13d7a-121">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="13d7a-122">選択条件を使用する方法の詳細については、[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13d7a-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="13d7a-123">参照</span><span class="sxs-lookup"><span data-stu-id="13d7a-123">See Also</span></span>

[<span data-ttu-id="13d7a-124">ときにデータの条件の定義が表示されます。</span><span class="sxs-lookup"><span data-stu-id="13d7a-124">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="13d7a-125">SelectionCondition EntrySelectedBy EnumerableExpansion (形式) のためのスクリプト ブロックの要素</span><span class="sxs-lookup"><span data-stu-id="13d7a-125">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="13d7a-126">EnumerableExpansion (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="13d7a-126">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="13d7a-127">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="13d7a-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
