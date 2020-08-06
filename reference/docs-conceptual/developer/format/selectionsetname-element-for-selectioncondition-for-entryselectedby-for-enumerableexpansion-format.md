---
title: 列挙 Able膨張 (Format) の EntrySelectedBy の SelectionCondition の SelectionSetName 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e18c74bb95c658f2c3e7b7454628f78d523f7609
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787497"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="78f49-102">EnumerableExpansion の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="78f49-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="78f49-103">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="78f49-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="78f49-104">このセット内のいずれかの型が存在する場合、条件が満たされます。</span><span class="sxs-lookup"><span data-stu-id="78f49-104">When any of the types in this set are present, the condition is met.</span></span>

<span data-ttu-id="78f49-105">Configuration 要素 DefaultSettings (Format) 列挙 able展開要素 (format) 列挙 able展開要素 (format) Entryselectedby 要素 (format) の entryselectedby 要素 (format) SelectionSetName 要素を指定します。 EntrySelectedBy には、entryselectedby の Selectionselectedby の SelectionCondition を指定します。</span><span class="sxs-lookup"><span data-stu-id="78f49-105">Configuration Element DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansions Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="78f49-106">構文</span><span class="sxs-lookup"><span data-stu-id="78f49-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="78f49-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="78f49-107">Attributes and Elements</span></span>

<span data-ttu-id="78f49-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="78f49-108">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="78f49-109">属性</span><span class="sxs-lookup"><span data-stu-id="78f49-109">Attributes</span></span>

<span data-ttu-id="78f49-110">なし。</span><span class="sxs-lookup"><span data-stu-id="78f49-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="78f49-111">子要素</span><span class="sxs-lookup"><span data-stu-id="78f49-111">Child Elements</span></span>

<span data-ttu-id="78f49-112">なし。</span><span class="sxs-lookup"><span data-stu-id="78f49-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="78f49-113">親要素</span><span class="sxs-lookup"><span data-stu-id="78f49-113">Parent Elements</span></span>

|<span data-ttu-id="78f49-114">要素</span><span class="sxs-lookup"><span data-stu-id="78f49-114">Element</span></span>|<span data-ttu-id="78f49-115">説明</span><span class="sxs-lookup"><span data-stu-id="78f49-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="78f49-116">EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="78f49-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="78f49-117">この定義のコレクションオブジェクトを展開するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="78f49-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="78f49-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="78f49-118">Text Value</span></span>

<span data-ttu-id="78f49-119">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="78f49-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="78f49-120">解説</span><span class="sxs-lookup"><span data-stu-id="78f49-120">Remarks</span></span>

<span data-ttu-id="78f49-121">選択条件では、選択セットまたは .NET 型を指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="78f49-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="78f49-122">選択条件の使用方法の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78f49-122">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="78f49-123">選択セットは、書式設定ファイルによって定義される任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="78f49-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="78f49-124">選択セットの作成と参照の詳細については、「[選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78f49-124">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="78f49-125">参照</span><span class="sxs-lookup"><span data-stu-id="78f49-125">See Also</span></span>

[<span data-ttu-id="78f49-126">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="78f49-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="78f49-127">EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="78f49-127">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="78f49-128">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="78f49-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
