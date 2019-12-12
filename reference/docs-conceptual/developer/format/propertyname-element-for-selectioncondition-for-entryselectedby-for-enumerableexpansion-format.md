---
title: 列挙 Able展開 (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ae11924-0072-451e-bf70-c5ffb25dccc0
caps.latest.revision: 13
ms.openlocfilehash: 0c20512e660c8d2b61d063dbd7078b55b23efeb8
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362321"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="ec9f5-102">EnumerableExpansion の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ec9f5-102">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="ec9f5-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="ec9f5-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="ec9f5-104">このプロパティが存在する場合、または `true`に評価された場合、条件が満たされ、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ec9f5-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="ec9f5-105">Configuration 要素 (Format) DefaultSettings 要素 (format) 列挙 Able膨張要素 (format) 列挙 able膨張拡張要素 (format) の Entryselectedby 要素の entryselectedby 要素の EntrySelectedBy 要素列挙 able膨張 (Format) の EntrySelectedBy の SelectionCondition の列挙 Able展開 (Format) PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="ec9f5-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ec9f5-106">構文</span><span class="sxs-lookup"><span data-stu-id="ec9f5-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ec9f5-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="ec9f5-107">Attributes and Elements</span></span>

<span data-ttu-id="ec9f5-108">次のセクションでは、`PropertyName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec9f5-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ec9f5-109">属性</span><span class="sxs-lookup"><span data-stu-id="ec9f5-109">Attributes</span></span>

<span data-ttu-id="ec9f5-110">なし。</span><span class="sxs-lookup"><span data-stu-id="ec9f5-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ec9f5-111">子要素</span><span class="sxs-lookup"><span data-stu-id="ec9f5-111">Child Elements</span></span>

<span data-ttu-id="ec9f5-112">なし。</span><span class="sxs-lookup"><span data-stu-id="ec9f5-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ec9f5-113">親要素</span><span class="sxs-lookup"><span data-stu-id="ec9f5-113">Parent Elements</span></span>

|<span data-ttu-id="ec9f5-114">要素</span><span class="sxs-lookup"><span data-stu-id="ec9f5-114">Element</span></span>|<span data-ttu-id="ec9f5-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="ec9f5-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ec9f5-116">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="ec9f5-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="ec9f5-117">この定義のコレクションオブジェクトを展開するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="ec9f5-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ec9f5-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="ec9f5-118">Text Value</span></span>

<span data-ttu-id="ec9f5-119">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ec9f5-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="ec9f5-120">コメント</span><span class="sxs-lookup"><span data-stu-id="ec9f5-120">Remarks</span></span>

<span data-ttu-id="ec9f5-121">選択条件では、少なくとも1つのプロパティ名または評価対象のスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="ec9f5-121">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="ec9f5-122">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec9f5-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ec9f5-123">参照</span><span class="sxs-lookup"><span data-stu-id="ec9f5-123">See Also</span></span>

[<span data-ttu-id="ec9f5-124">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="ec9f5-124">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="ec9f5-125">列挙 Able展開の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="ec9f5-125">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="ec9f5-126">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="ec9f5-126">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="ec9f5-127">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="ec9f5-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
