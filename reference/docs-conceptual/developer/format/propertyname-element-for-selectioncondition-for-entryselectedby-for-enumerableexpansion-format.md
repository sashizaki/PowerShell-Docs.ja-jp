---
title: 列挙 Able展開 (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c0081cb724ccaf1c04241aafa177880d7c0e5dbe
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783468"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="9b378-102">EnumerableExpansion の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9b378-102">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="9b378-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b378-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="9b378-104">このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="9b378-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="9b378-105">Configuration 要素 (Format) DefaultSettings Element (format) 列挙 able膨張要素 (format) 列挙 able膨張の要素 (format) entryselectedby の要素 (format) の entryselectedby の Selectionselectedby 要素に対して、entryselectedby (format) の selectioncondition 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b378-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9b378-106">構文</span><span class="sxs-lookup"><span data-stu-id="9b378-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9b378-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9b378-107">Attributes and Elements</span></span>

<span data-ttu-id="9b378-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="9b378-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9b378-109">属性</span><span class="sxs-lookup"><span data-stu-id="9b378-109">Attributes</span></span>

<span data-ttu-id="9b378-110">なし。</span><span class="sxs-lookup"><span data-stu-id="9b378-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9b378-111">子要素</span><span class="sxs-lookup"><span data-stu-id="9b378-111">Child Elements</span></span>

<span data-ttu-id="9b378-112">なし。</span><span class="sxs-lookup"><span data-stu-id="9b378-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9b378-113">親要素</span><span class="sxs-lookup"><span data-stu-id="9b378-113">Parent Elements</span></span>

|<span data-ttu-id="9b378-114">要素</span><span class="sxs-lookup"><span data-stu-id="9b378-114">Element</span></span>|<span data-ttu-id="9b378-115">説明</span><span class="sxs-lookup"><span data-stu-id="9b378-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9b378-116">EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9b378-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="9b378-117">この定義のコレクションオブジェクトを展開するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="9b378-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9b378-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="9b378-118">Text Value</span></span>

<span data-ttu-id="9b378-119">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b378-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="9b378-120">解説</span><span class="sxs-lookup"><span data-stu-id="9b378-120">Remarks</span></span>

<span data-ttu-id="9b378-121">選択条件では、少なくとも1つのプロパティ名または評価対象のスクリプトを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="9b378-121">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="9b378-122">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b378-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9b378-123">参照</span><span class="sxs-lookup"><span data-stu-id="9b378-123">See Also</span></span>

[<span data-ttu-id="9b378-124">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="9b378-124">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="9b378-125">EnumerableExpansion の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9b378-125">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="9b378-126">EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="9b378-126">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="9b378-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="9b378-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
