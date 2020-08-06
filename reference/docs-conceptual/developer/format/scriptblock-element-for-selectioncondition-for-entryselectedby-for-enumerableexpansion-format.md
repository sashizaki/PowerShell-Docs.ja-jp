---
title: 列挙 Able展開の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 71fd969fd3e5c0a4e39762c9a026982a8ca2a9d1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785372"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="a0528-102">EnumerableExpansion の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a0528-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="a0528-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a0528-103">Specifies the script that triggers the condition.</span></span>

<span data-ttu-id="a0528-104">Configuration 要素 (Format) DefaultSettings 要素 (format) の列挙 able膨張要素 (format) 列挙 able膨張拡張要素 (format) の entryselectedby 要素 (format) に対して、enumerableexpansions (format) に対して、entryselectedby の Selectionselectedby を指定します。</span><span class="sxs-lookup"><span data-stu-id="a0528-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a0528-105">構文</span><span class="sxs-lookup"><span data-stu-id="a0528-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a0528-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a0528-106">Attributes and Elements</span></span>

<span data-ttu-id="a0528-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="a0528-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a0528-108">属性</span><span class="sxs-lookup"><span data-stu-id="a0528-108">Attributes</span></span>

<span data-ttu-id="a0528-109">なし。</span><span class="sxs-lookup"><span data-stu-id="a0528-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a0528-110">子要素</span><span class="sxs-lookup"><span data-stu-id="a0528-110">Child Elements</span></span>

<span data-ttu-id="a0528-111">なし。</span><span class="sxs-lookup"><span data-stu-id="a0528-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a0528-112">親要素</span><span class="sxs-lookup"><span data-stu-id="a0528-112">Parent Elements</span></span>

|<span data-ttu-id="a0528-113">要素</span><span class="sxs-lookup"><span data-stu-id="a0528-113">Element</span></span>|<span data-ttu-id="a0528-114">説明</span><span class="sxs-lookup"><span data-stu-id="a0528-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a0528-115">EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a0528-115">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="a0528-116">この定義のコレクションオブジェクトを展開するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="a0528-116">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a0528-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="a0528-117">Text Value</span></span>

<span data-ttu-id="a0528-118">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a0528-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="a0528-119">解説</span><span class="sxs-lookup"><span data-stu-id="a0528-119">Remarks</span></span>

<span data-ttu-id="a0528-120">選択条件では、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a0528-120">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="a0528-121">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0528-121">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a0528-122">参照</span><span class="sxs-lookup"><span data-stu-id="a0528-122">See Also</span></span>

[<span data-ttu-id="a0528-123">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="a0528-123">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="a0528-124">EnumerableExpansion の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a0528-124">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="a0528-125">EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a0528-125">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="a0528-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="a0528-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
