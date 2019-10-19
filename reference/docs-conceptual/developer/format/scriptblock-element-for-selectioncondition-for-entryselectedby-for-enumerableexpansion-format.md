---
title: 列挙 Able展開の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4126b799-c43d-4175-8513-6d761c65437e
caps.latest.revision: 9
ms.openlocfilehash: a51d8d22fa8b0c7f303a5e8f37edcc5e57724063
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368611"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="2999e-102">EnumerableExpansion の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2999e-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="2999e-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="2999e-103">Specifies the script that triggers the condition.</span></span>

<span data-ttu-id="2999e-104">Configuration 要素 (Format) DefaultSettings 要素 (format) 列挙 Able膨張要素 (format) 列挙 able膨張拡張要素 (format) の Entryselectedby 要素の entryselectedby 要素の EntrySelectedBy 要素列挙 able膨張 (Format) の EntrySelectedBy の SelectionCondition に使用する EnumerableExpansion (Format) ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="2999e-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2999e-105">構文</span><span class="sxs-lookup"><span data-stu-id="2999e-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2999e-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="2999e-106">Attributes and Elements</span></span>

<span data-ttu-id="2999e-107">次のセクションでは、属性、子要素、`ScriptBlock` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2999e-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2999e-108">属性</span><span class="sxs-lookup"><span data-stu-id="2999e-108">Attributes</span></span>

<span data-ttu-id="2999e-109">なし。</span><span class="sxs-lookup"><span data-stu-id="2999e-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2999e-110">子要素</span><span class="sxs-lookup"><span data-stu-id="2999e-110">Child Elements</span></span>

<span data-ttu-id="2999e-111">なし。</span><span class="sxs-lookup"><span data-stu-id="2999e-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2999e-112">親要素</span><span class="sxs-lookup"><span data-stu-id="2999e-112">Parent Elements</span></span>

|<span data-ttu-id="2999e-113">要素</span><span class="sxs-lookup"><span data-stu-id="2999e-113">Element</span></span>|<span data-ttu-id="2999e-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="2999e-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2999e-115">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="2999e-115">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="2999e-116">この定義のコレクションオブジェクトを展開するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="2999e-116">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2999e-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="2999e-117">Text Value</span></span>

<span data-ttu-id="2999e-118">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="2999e-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="2999e-119">コメント</span><span class="sxs-lookup"><span data-stu-id="2999e-119">Remarks</span></span>

<span data-ttu-id="2999e-120">選択条件では、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="2999e-120">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="2999e-121">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2999e-121">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2999e-122">参照</span><span class="sxs-lookup"><span data-stu-id="2999e-122">See Also</span></span>

[<span data-ttu-id="2999e-123">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="2999e-123">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="2999e-124">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="2999e-124">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="2999e-125">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="2999e-125">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="2999e-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="2999e-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)