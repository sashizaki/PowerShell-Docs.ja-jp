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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368611"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="e13b9-102">EnumerableExpansion の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e13b9-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="e13b9-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e13b9-103">Specifies the script that triggers the condition.</span></span>

<span data-ttu-id="e13b9-104">Configuration 要素 (Format) DefaultSettings 要素 (format) 列挙 Able膨張要素 (format) 列挙 able膨張拡張要素 (format) の Entryselectedby 要素の entryselectedby 要素の EntrySelectedBy 要素列挙 able膨張 (Format) の EntrySelectedBy の SelectionCondition に使用する EnumerableExpansion (Format) ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="e13b9-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e13b9-105">構文</span><span class="sxs-lookup"><span data-stu-id="e13b9-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e13b9-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="e13b9-106">Attributes and Elements</span></span>

<span data-ttu-id="e13b9-107">次のセクションでは、`ScriptBlock` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e13b9-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e13b9-108">属性</span><span class="sxs-lookup"><span data-stu-id="e13b9-108">Attributes</span></span>

<span data-ttu-id="e13b9-109">なし。</span><span class="sxs-lookup"><span data-stu-id="e13b9-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e13b9-110">子要素</span><span class="sxs-lookup"><span data-stu-id="e13b9-110">Child Elements</span></span>

<span data-ttu-id="e13b9-111">なし。</span><span class="sxs-lookup"><span data-stu-id="e13b9-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e13b9-112">親要素</span><span class="sxs-lookup"><span data-stu-id="e13b9-112">Parent Elements</span></span>

|<span data-ttu-id="e13b9-113">要素</span><span class="sxs-lookup"><span data-stu-id="e13b9-113">Element</span></span>|<span data-ttu-id="e13b9-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="e13b9-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e13b9-115">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="e13b9-115">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="e13b9-116">この定義のコレクションオブジェクトを展開するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="e13b9-116">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e13b9-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="e13b9-117">Text Value</span></span>

<span data-ttu-id="e13b9-118">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e13b9-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="e13b9-119">コメント</span><span class="sxs-lookup"><span data-stu-id="e13b9-119">Remarks</span></span>

<span data-ttu-id="e13b9-120">選択条件では、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e13b9-120">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="e13b9-121">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e13b9-121">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e13b9-122">参照</span><span class="sxs-lookup"><span data-stu-id="e13b9-122">See Also</span></span>

[<span data-ttu-id="e13b9-123">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="e13b9-123">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="e13b9-124">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="e13b9-124">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="e13b9-125">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="e13b9-125">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="e13b9-126">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="e13b9-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
